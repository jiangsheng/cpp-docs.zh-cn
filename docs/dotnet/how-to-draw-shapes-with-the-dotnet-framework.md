---
title: "如何： 使用.NET Framework 绘制形状 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- GDI+, drawing shapes
- drawing, shapes
- shapes
- shapes, drawing
ms.assetid: ffad5ae7-6ef4-4550-8940-be3f209a101d
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9c9c2fedb4bb07fa2301368e4bd7b62fb636d3fb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-draw-shapes-with-the-net-framework"></a>如何：使用 .NET Framework 绘制形状
下面的代码示例使用<xref:System.Drawing.Graphics>类来修改<xref:System.Windows.Forms.Form.OnPaint%2A>事件处理程序来检索指向<xref:System.Drawing.Graphics>主窗体的对象。 此指针然后用于设置窗体的背景色和绘制直线和弧线使用<xref:System.Drawing.Graphics.DrawLine%2A?displayProperty=fullName>和<xref:System.Drawing.Graphics.DrawArc%2A>方法。  
  
> [!NOTE]
>  GDI + 随 Windows XP 附带，可用作 Windows NT 4.0 SP 6、 Windows 2000、 Windows 98 和 Windows me 的可再发行 若要下载最新可再发行组件，请参阅[http://go.microsoft.com/fwlink/?linkid=11232](http://go.microsoft.com/fwlink/?linkid=11232)。 
  
## <a name="example"></a>示例  
  
```  
#using <system.drawing.dll>  
using namespace System;  
using namespace System::Drawing;  
// ...  
protected:   
virtual Void Form1::OnPaint(PaintEventArgs^ pe ) override  
{  
   Graphics^ g = pe->Graphics;  
   g->Clear(Color::AntiqueWhite);  
  
   Rectangle rect = Form::ClientRectangle;  
   Rectangle smallRect;  
   smallRect.X = rect.X + rect.Width / 4;  
   smallRect.Y = rect.Y + rect.Height / 4;  
   smallRect.Width = rect.Width / 2;  
   smallRect.Height = rect.Height / 2;  
  
   Pen^ redPen = gcnew Pen(Color::Red);  
   redPen->Width = 4;  
   g->DrawLine(redPen, 0, 0, rect.Width, rect.Height);  
  
   Pen^ bluePen = gcnew Pen(Color::Blue);  
   bluePen->Width = 10;  
   g->DrawArc( bluePen, smallRect, 90, 270 );  
}  
```  
  
## <a name="see-also"></a>另请参阅  
 [.NET 编程使用 C + + /cli （Visual c + +）](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [System::Drawing 命名空间](https://msdn.microsoft.com/en-us/library/system.drawing.aspx)