---
title: "ARM ABI 约定概述 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 23f4ae8c-3148-4657-8c47-e933a9f387de
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cf5ef9c9d9e122b23dc1b39d6e6092168f2c9381
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="overview-of-arm-abi-conventions"></a>ARM ABI 约定概述
针对 ARM 上 Windows 处理器编译的代码的应用程序二进制接口 (ABI) 基于标准 ARM EABI。 本文突出显示了 ARM 上的 Windows 与标准之间的主要差异。 有关标准 ARM EABI 的详细信息，请参阅[应用程序二进制接口 (ABI) ARM 体系结构](http://infocenter.arm.com/help/index.jsp?topic=/com.arm.doc.subset.swdev.abi/index.html)。  
  
## <a name="base-requirements"></a>基本需求  
 ARM 上的 Windows 假定始终都在 ARMv7 体系结构上运行。 VFPv3-D32 或更高版本的形式的浮点支持必须存在于硬件中。 VFP 必须同时支持硬件中的单精度和双精度浮点。 Windows 运行时不支持要在非 VFP 硬件上运行的浮点的模拟。  
  
 高级 SIMD 扩展 (NEON) 支持（包括整数运算和浮点运算）也必须存在于硬件中。 不提供对于模拟的运行时支持。  
  
 强烈建议使用整数除法支持 (UDIV/SDIV)，但它不是必需的。 缺少整数除法支持的平台可能会导致性能下降，因为这些运算必须被捕获并且可能需要进行修补。  
  
## <a name="endianness"></a>字节排序方式  
 在 Little-endian 模式下执行 ARM 上的 Windows。 Visual C++ 编译器和 Windows 运行时始终都需要 Little-endian 数据。 尽管 ARM 指令集体系结构 (ISA) 中的 SETEND 指令甚至允许用户模式代码更改当前字节排序方式，但不鼓励执行此操作，因为这对于应用程序很危险。 如果在 Big-endian 模式下生成某个异常，则该行为将不可预测，并且可能会导致用户模式中出现应用程序错误或者内核模式中出现 bugcheck。  
  
## <a name="alignment"></a>对齐  
 尽管 Windows 使 ARM 硬件可以透明地处理未对齐的整数访问，但在某些情况下，可能仍然会生成对齐错误。 遵循下列对齐规则：  
  
-   不必对半字大小（16 位）和字大小（32 位）整数的加载和存储进行对齐。 硬件会以高效且透明地方式处理它们。  
  
-   浮点的加载和存储应对齐。 内核会以透明方式处理未对齐的加载和存储，但会带来很大的开销。  
  
-   加载或存储双字 (LDRD/STRD) 运算和多重数据 (LDM/STM) 运算应进行对齐。 内核会以透明方式处理它们中的大多数运算，但会带来很大的开销。  
  
-   所有未缓存的内存访问必须对齐，即使对于整数访问也是如此。 未对齐的访问会导致对齐错误。  
  
## <a name="instruction-set"></a>指令集  
 适用于 ARM 上 Windows 的指令集严格限制为 Thumb-2。 在此平台上执行的所有代码都应始终在 Thumb 模式下启动并且继续处于该模式下。 切换到旧版 ARM 指令集的尝试可能会成功，但是如果成功，则发生的异常或中断可能会导致用户模式中出现应用程序错误或者内核模式中出现 bugcheck。  
  
 此要求的副作用是所有代码指针必须设置低位。 这是为了在通过 BLX 或 BX 对其进行加载和分支时，处理器将继续处于 Thumb 模式下并且不会尝试按照 32 位 ARM 指令执行目标代码。  
  
### <a name="it-instructions"></a>IT 指令  
 不允许在 Thumb-2 代码中使用 IT 指令，但以下特定情况除外：  
  
-   IT 指令只能用于修改某个目标指令。  
  
-   该目标指令必须为 16 位指令。  
  
-   该目标指令必须为以下项之一：  
  
    |16 位操作代码|类|限制|  
    |---------------------|-----------|------------------|  
    |MOV、MVN|移动|Rm != PC、Rd != PC|  
    |LDR、LDR[S]B、LDR[S]H|从内存中加载|但不是 LDR 文本格式|  
    |STR、STRB、STRH|存储到内存||  
    |ADD、ADC、RSB、SBC、SUB|加法或减法|但不是 ADD/SUB SP、SP 和 imm7 形式<br /><br /> Rm != PC、Rdn != PC、Rdm != PC|  
    |CMP、CMN|比较|Rm != PC、Rn != PC|  
    |MUL|相乘||  
    |ASR、LSL、LSR、ROR|移位||  
    |AND、BIC、EOR、ORR、TST|按位算术运算||  
    |BX|寄存器的分支|Rm != PC|  
  
 尽管当前 ARMv7 CPU 无法报告禁用指令格式的使用情况，但以后的处理器应该能实现。 若已检测到这些格式，则使用这些格式的所有程序可能会以未定义的指令异常终止。  
  
### <a name="sdivudiv-instructions"></a>SDIV/UDIV 指令  
 完全支持整数除法指令 SDIV 和 UDIV 的使用，即使是在没有用于处理它们的本机硬件的平台上也是如此。 除了整体除法时间 20-250 个周期（具体取决于输入）外，Cortex-A9 处理器上的每个 SDIV 或 UDIV 除法的开销近似于 80 个周期。  
  
## <a name="integer-registers"></a>整数寄存器  
 ARM 处理器支持 16 个整数寄存器：  
  
|寄存器|是否易失？|角色|  
|--------------|---------------|----------|  
|r0|易失的|参数寄存器、结果寄存器、临时寄存器 1|  
|r1|易失的|参数寄存器、结果寄存器、临时寄存器 2|  
|r2|易失的|参数寄存器、临时寄存器 3|  
|r3|易失的|参数寄存器、临时寄存器 4|  
|r4|非易失性的||  
|r5|非易失性的||  
|r6|非易失性的||  
|r7|非易失性的||  
|r8|非易失性的||  
|r9|非易失性的||  
|r10|非易失性的||  
|r11|非易失性的|帧指针|  
|r12|易失的|过程内部调用临时寄存器|  
|r13 (SP)|非易失性的|堆栈指针|  
|r14 (LR)|非易失性的|链接寄存器|  
|r15 (PC)|非易失性的|程序计数器|  
  
 有关如何使用参数寄存器和返回值寄存器的详细信息，请参阅本文中的“参数传递”部分。  
  
 Windows 使用 r11 以快速审核堆栈帧。 有关详细信息，请参阅“堆栈审核”部分。 由于此要求，因此 r11 必须始终指向链中的最顶层链接。 不要将 r11 用于常规用途 - 你的代码在分析期间将不会生成正确的堆栈审核。  
  
## <a name="vfp-registers"></a>VFP 寄存器  
 Windows 仅支持 ARM 变量，它们支持 VFPv3-D32 协处理器。 这意味着浮点寄存器始终存在且可用于参数传递，还表明完整的 32 位寄存器集可供使用。 下表中总结了 VFP 寄存器及其用法：  
  
|单精度值|双精度值|Quads|是否易失？|角色|  
|-------------|-------------|-----------|---------------|----------|  
|s0-s3|d0-d1|q0|易失的|参数寄存器、结果寄存器、临时寄存器|  
|s4-s7|d2-d3|q1|易失的|参数寄存器、临时寄存器|  
|s8-s11|d4-d5|q2|易失的|参数寄存器、临时寄存器|  
|s12-s15|d6-d7|q3|易失的|参数寄存器、临时寄存器|  
|s16-s19|d8-d9|q4|非易失性的||  
|s20-s23|d10-d11|q5|非易失性的||  
|s24-s27|d12-d13|q6|非易失性的||  
|s28-s31|d14-d15|q7|非易失性的||  
||d16-d31|q8-q15|易失的||  
  
 下一个表阐释了浮点状态和控制寄存器 (FPSCR) 位域：  
  
|位|含义|是否易失？|角色|  
|----------|-------------|---------------|----------|  
|31-28|NZCV|易失的|状态标志|  
|27|QC|易失的|累计饱和度|  
|26|AHP|非易失性的|备选半精度控制|  
|25|DN|非易失性的|默认 NaN 模式控制|  
|24|FZ|非易失性的|清零模式控制|  
|23-22|RMode|非易失性的|舍入模式控制|  
|21-20|跨距|非易失性的|矢量跨距必须始终为 0|  
|18-16|Len|非易失性的|矢量长度必须始终为 0|  
|15, 12-8|IDE、IXE 等|非易失性的|异常捕获启用位，必须始终为 0|  
|7, 4-0|IDC、IXC 等|易失的|累计异常标志|  
  
## <a name="floating-point-exceptions"></a>浮点异常  
 大多数 ARM 硬件不支持 IEEE 浮点异常。 在具有硬件浮点异常的处理器变量上，Windows 内核将以静默形式捕捉这些异常并在 FPSCR 寄存器中隐式地禁用它们。 这样可确保在处理器变量之间保持规范化行为。 否则，当在不支持异常的平台上开发的代码在支持异常的平台上运行时，它将收到意外的异常。  
  
## <a name="parameter-passing"></a>参数传递  
 对于不可变参数函数，ARM 上的 Windows ABI 将遵循参数传递的 ARM 规则，该规则包括 VFP 和高级 SIMD 扩展。 这些规则遵循[过程调用标准 ARM 体系结构](http://infocenter.arm.com/help/topic/com.arm.doc.ihi0042c/IHI0042C_aapcs.pdf)已与 VFP 扩展合并。 默认情况下，寄存器中可以传递前四个整数自变量以及最多八个浮点自变量或矢量自变量，而其他自变量在堆栈上传递。 使用此过程将参数分配给寄存器或堆栈：  
  
### <a name="stage-ainitialization"></a>阶段 A - 初始化  
 在参数处理开始之前需要正好执行一次初始化：  
  
1.  将下一个核心寄存器号 (NCRN) 设置为 r0。  
  
2.  VFP 寄存器标记为未分配。  
  
3.  将下一个堆叠参数地址 (NSAA) 设置为当前 SP。  
  
4.  如果调用在内存中返回结果的函数，则该结果的地址将被置于 r0 中并且 NCRN 将设置为 r1。  
  
### <a name="stage-bpre-padding-and-extension-of-arguments"></a>阶段 B - 参数的预填充和扩展  
 对于列表中的每个参数，将从以下列表中应用第一个匹配规则：  
  
1.  如果参数是其大小无法通过调用方和被调用方静态确定的复合类型，则该参数将被复制到内存，并由一个指向该参数副本的指针替换。  
  
2.  如果参数是 1 个字节或 16 位半字，则可通过零扩展或符号扩展使其成为 32 位全字并且可视为 4 字节参数。  
  
3.  如果参数为复合类型，则其大小将会舍入为 4 的最接近倍数。  
  
### <a name="stage-cassignment-of-arguments-to-registers-and-stack"></a>阶段 C - 将参数分配给寄存器和堆栈  
 对于列表中的每个参数，将依次应用以下规则，直到参数被分配：  
  
1.  如果参数为 VFP 类型且具有足够的、适当类型的连续未分配 VFP 寄存器，则该参数将分配到此类寄存器的最低编号序列。  
  
2.  如果参数为 VFP 类型，则所有剩余未分配的寄存器将标记为不可用。 向上调整 NSAA，直到它与参数类型正确对齐且参数已复制到位于调整后的 NSAA 的堆栈。 然后，NSAA 按参数的大小递增。  
  
3.  如果参数需要 8 字节对齐方式，则 NCRN 将会舍入为下一个偶数寄存器号。  
  
4.  如果参数的大小（以 32 位字的形式）不大于 r4 减去 NCRN 的值，则将在最低有效字节占用编号较低的寄存器的情况下，将该参数复制到从 NCRN 开始的核心寄存器中。 NCRN 按所使用的寄存器的数量递增。  
  
5.  如果 NCRN 小于 r4 且 NSAA 等于 SP，则参数将分布于核心寄存器和堆栈之间。 将参数的第一部分复制到核心寄存器中，从 NCRN 开始，直到 r3（包括 r3）。 该参数的其余部分将复制到从 NSAA 开始的堆栈中。 将 NCRN 设置为 r4，而 NSAA 按参数的大小减去寄存器中传递的参数量的值递增。  
  
6.  如果参数需要 8 字节对齐方式，则 NSAA 将会舍入为下一个 8 字节对齐地址。  
  
7.  将该参数复制到内存中的 NSAA 处。 NSAA 按参数的大小递增。  
  
 VFP 寄存器不用于可变参数函数，并且忽略阶段 C 规则 1 和 2。 这意味着，可变参数函数可以用一个可选的 push {r0-r3} 开头，以便将寄存器参数置于由调用方传递的其他任何参数之前，从而可以直接从堆栈中访问整个参数列表。  
  
 整数类型值将在 r0 中返回，并且可以选择扩展到用于 64 位返回值的 r1。 VFP/NEON 浮点值或 SIMD 类型值将以适当方式在 s0、d0 或 q0 中返回。  
  
## <a name="stack"></a>堆栈  
 堆栈必须始终保持 4 字节对齐，并且在任意函数边界处都必须为 8 字节对齐。 这是支持经常在 64 位堆栈变量上使用互锁操作所必需的。 ARM EABI 指示堆栈在任意公共接口处都需要为 8 字节对齐。 为了保持一致性，ARM 上的 Windows ABI 将所有函数边界都视为公共接口。  
  
 一些必须使用帧指针的函数（例如，调用 `alloca` 的函数或动态更改堆栈指针的函数）必须在函数序言中的 r11 中设置该帧指针，并且在函数尾声之前都必须使其保持不变。 对于不需要使用帧指针的函数，必须在序言中对所有堆栈执行更新操作，并且在函数尾声之前必须使堆栈指针保持不变。  
  
 在堆栈上分配 4 KB 或更大容量的函数必须确保在最后一页之前每页都需要按顺序进行处理。 这将确保任何代码都不能“跳过”Windows 用于扩展堆栈的受保护页。 通常，这是通过 `__chkstk` 帮助器完成的，后者将 r4 中已传递的总堆栈分配量（以字节为单位）除以 4，并且将最终堆栈分配量（以字节为单位）返回至 r4 中。  
  
### <a name="red-zone"></a>红色区域  
 保留紧跟在当前堆栈指针下方的 8 字节区域以供分析和动态修补。 这允许小心地插入生成的代码，它在 [sp, #-8] 中存储了 2 个寄存器并临时将其用于任意目的。 Windows 内核保证在用户模式和内核模式下出现异常或中断时不覆盖上述 8 个字节。  
  
### <a name="kernel-stack"></a>内核堆栈  
 Windows 中的内核模式堆栈默认为 3 个页面 (12 KB)。 请注意，不要在内核模式下创建具有大堆栈缓冲区的函数。 中断会随着非常小的堆栈空余空间一起出现，并且会导致堆栈应急 bugcheck。  
  
## <a name="cc-specifics"></a>C/C++ 详细信息  
 枚举为 32 位整数类型，除非枚举中至少有一个值需要 64 位双字存储。 在这种情况下，枚举将提升为 64 位整数类型。  
  
 `wchar_t` 定义为等效于 `unsigned short`，以保留与其他平台的兼容性。  
  
## <a name="stack-walking"></a>堆栈审核  
 使用帧指针启用 Windows 代码进行编译 ([/Oy （框架指针省略）](../build/reference/oy-frame-pointer-omission.md)) 以启用快速堆栈审核。 通常，r11 寄存器指向链中的下一个链接，它是指定指向堆栈上前一个帧的指针和返回地址的 {r11, lr} 对。 建议你的代码也启用帧指针以改进分析和跟踪。  
  
## <a name="exception-unwinding"></a>异常展开  
 在异常处理期间，通过使用展开代码堆栈可以启用堆栈展开。 展开代码是存储在可执行映像的 .xdata 部分中的字节的序列。 它们以抽象的方式描述了函数序言和尾声代码的操作，以便可以撤消函数序言的效果，从而准备展开调用方的堆栈帧。  
  
 ARM EABI 指定了使用展开代码的异常展开模式。 但是，在 Windows 中进行展开时此规范是不够的，此时必须处理处理器在函数序言或尾声中间的情况。 ARM 异常数据和展开 Windows 的详细信息，请参阅[ARM 异常处理](../build/arm-exception-handling.md)。  
  
 建议使用对 `RtlAddFunctionTable` 以及关联函数的调用中指定的动态函数表来描述动态生成的代码，以便生成的代码可以参与异常处理。  
  
## <a name="cycle-counter"></a>循环计数器  
 需要运行 Windows 的 ARM 处理器来支持循环计数器，但如果直接使用该计数器，则可能会出现问题。 若要避免这些问题，则 ARM 上的 Windows 可以使用未定义的操作码来请求规范化的 64 位循环计数器的值。 在 C 或 C++ 中，请使用 `__rdpmccntr64` 内部指令发出相应的操作码；在程序集中，请使用 `__rdpmccntr64` 指令。 在 Cortex-A9 上读取循环计数器耗时约为 60 个周期。  
  
 该计数器为真循环计数器，而非时钟，因此计数频率会随处理器的频率发生变化。 若要测量运行的时钟时间，请使用 `QueryPerformanceCounter`。  
  
## <a name="see-also"></a>另请参阅  
 [常见的 Visual c + + ARM 迁移问题](../build/common-visual-cpp-arm-migration-issues.md)   
 [ARM 异常处理](../build/arm-exception-handling.md)