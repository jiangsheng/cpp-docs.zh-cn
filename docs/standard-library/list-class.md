---
title: "list 类 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.list
- list
- std::list
- list/std::list
dev_langs:
- C++
helpviewer_keywords:
- list class
ms.assetid: d3707f4a-10fd-444f-b856-f9ca2077c1cd
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 16d9bb63aac40bc4494f8d748fd752cde85d79d9
ms.lasthandoff: 02/24/2017

---
# <a name="list-class"></a>list 类
C++ 标准库列表类是序列容器的一个模板类，用于将它们的元素保持为线性排列，并允许在序列的任何位置高效插入和删除。 序列存储为双向链接的元素列表，每个包含一些 *Type* 类型的成员。  
  
## <a name="syntax"></a>语法  
  
```cpp  
template <class Type, class Allocator= allocator<Type>>  
class list  
```  
  
#### <a name="parameters"></a>参数  
 *类型*  
 要存储在列表中的元素数据类型。  
  
 `Allocator`  
 表示所存储分配器对象的类型，该分配器对象封装有关列表的内存分配和解除分配的详细信息。 此自变量是可选自变量，且默认值为 **allocator**\< *Type*> 。  
  
## <a name="remarks"></a>备注  
 容器类型选择通常应根据应用程序所需的搜索和插入的类型。 当对任何元素的随机访问超出限制并且仅要求在序列的末尾插入或删除元素时，矢量应作为用于管理序列的首选容器。 当需要随机访问并且在序列起始处和末尾处插入和删除元素已到达极限时，应首选类 deque 容器进行操作。  
  
 列表成员函数 [merge](#list__merge)、[reverse](#list__reverse)、[unique](#list__unique)、[remove](#list__remove) 和 [remove_if](#list__remove_if) 已针对对列表的操作进行了优化，它们可作为泛型对应函数的高性能替代函数。  
  
 当成员函数必须插入或删除列表中的元素时，将发生列表的重新分配。 在所有这类情况下，仅指向受控制序列被消除部分的迭代器或引用将变为无效。  
  
 包括 C++ 标准库标准标头 \<list>，以定义 [container](../standard-library/stl-containers.md) 模板类列表和多个支持模板。  
  
### <a name="constructors"></a>构造函数  
  
|||  
|-|-|  
|[list](#list__list)|构造一个列表，它具有特定大小或它的元素具有特定值，或具有特定 `allocator` 或作为某个其他列表副本。|  
  
### <a name="typedefs"></a>Typedef  
  
|||  
|-|-|  
|[allocator_type](#list__allocator_type)|表示列表对象的 `allocator` 类的类型。|  
|[const_iterator](#list__const_iterator)|提供可读取列表中 `const` 元素的双向迭代器的类型。|  
|[const_pointer](#list__const_pointer)|提供指向列表中 `const` 元素的指针的类型。|  
|[const_reference](#list__const_reference)|提供对存储于列表中供读取和执行 `const` 操作的 `const` 元素的引用的类型。|  
|[const_reverse_iterator](#list__const_reverse_iterator)|提供可读取列表中任何 `const` 元素的双向迭代器的类型。|  
|[difference_type](#list__difference_type)|提供引用同一列表中的元素的两个迭代器之间的差异的类型。|  
|[iterator](#list__iterator)|提供可读取或修改列表中任何元素的双向迭代器的类型。|  
|[pointer](#list__pointer)|提供指向列表中元素的指针的类型。|  
|[reference](#list__reference)|提供对存储于列表中供读取和执行 `const` 操作的 `const` 元素的引用的类型。|  
|[reverse_iterator](#list__reverse_iterator)|提供可读取或修改反向列表中的元素的双向迭代器的类型。|  
|[size_type](#list__size_type)|计算列表中元素的数目的类型。|  
|[value_type](#list__value_type)|表示列表中存储的数据类型的类型。|  
  
### <a name="member-functions"></a>成员函数  
  
|||  
|-|-|  
|[assign](#list__assign)|将元素从列表中擦除并将一组新的元素复制到目标列表。|  
|[back](#list__back)|返回对列表中最后一个元素的引用。|  
|[begin](#list__begin)|返回发现列表中第一个元素的位置的迭代器。|  
|[list::cbegin](#list__cbegin)|返回发现列表中第一个元素的位置的常量迭代器。|  
|[list::cend](#list__cend)|返回发现一个列表中最后一个元素之后的位置的敞亮表达式。|  
|[list::clear](#list__clear)|消除列表中的全部元素。|  
|[list::crbegin](#list__crbegin)|返回发现反向列表中第一个元素的位置的常量迭代器。|  
|[list::crend](#list__crend)|返回用于发现反向列表中最后一个元素之后的位置的常量迭代器。|  
|[list::emplace](#list__emplace)|将构造的元素插入到列表中的指定位置。|  
|[list::emplace_back](#list__emplace_back)|在列表的结尾处添加一个就地构造的元素。|  
|[list::emplace_front](#list__emplace_front)|在列表的起始位置添加一个就地构造的元素。|  
|[empty](#list__empty)|测试列表是否为空。|  
|[end](#list__end)|返回用于发现列表中最后一个元素之后的位置的迭代器。|  
|[erase](#list__erase)|从列表中的指定位置移除一个或一系列元素。|  
|[front](#list__front)|返回对列表中第一个元素的引用。|  
|[get_allocator](#list__get_allocator)|返回用于构造列表的 `allocator` 对象的一个副本。|  
|[insert](#list__insert)|将一个、几个或一系列元素插入列表中的指定位置。|  
|[max_size](#list__max_size)|返回列表的最大长度。|  
|[merge](#list__merge)|将元素从参数列表移除，将它们插入目标列表，将新的组合元素集以升序或其他指定顺序排序。|  
|[pop_back](#list__pop_back)|删除列表末尾的元素。|  
|[pop_front](#list__pop_front)|删除列表起始处的一个元素。|  
|[push_back](#list__push_back)|在列表的末尾添加元素。|  
|[push_front](#list__push_front)|在列表的开头添加元素。|  
|[rbegin](#list__rbegin)|返回发现反向列表中第一个元素的位置的迭代器。|  
|[remove](#list__remove)|清除列表中与指定值匹配的元素。|  
|[remove_if](#list__remove_if)|将满足指定谓词的元素从列表中消除。|  
|[rend](#list__rend)|返回发现反向列表中最后一个元素之后的位置的迭代器。|  
|[resize](#list__resize)|为列表指定新的大小。|  
|[reverse](#list__reverse)|反转列表中元素的顺序。|  
|[size](#list__size)|返回列表中元素的数目。|  
|[sort](#list__sort)|按升序或其他顺序关系排列列表中的元素。|  
|[splice](#list__splice)|将元素从自变量列表中删除或将它们插入目标列表。|  
|[swap](#list__swap)|交换两个列表的元素。|  
|[unique](#list__unique)|从列表中删除满足某些其他二元谓词的相邻重复元素或相邻元素。|  
  
### <a name="operators"></a>运算符  
  
|||  
|-|-|  
|[list::operator=](#list__operator_eq)|用另一个列表的副本替换列表中的元素。|  
  
## <a name="requirements"></a>要求  
 **标头**：\<list>  
  
##  <a name="a-namelistallocatortypea--listallocatortype"></a><a name="list__allocator_type"></a>list::allocator_type  
 表示列表对象的分配器类的类型。  
  
```  
typedef Allocator allocator_type;  
```  
  
### <a name="remarks"></a>备注  
 `allocator_type` 是模板参数 **Allocator** 的同义词。  
  
### <a name="example"></a>示例  
  请参阅 [get_allocator](#list__get_allocator) 的示例。  
  
##  <a name="a-namelistassigna--listassign"></a><a name="list__assign"></a>list::assign  
 清除列表中的元素，并将一组新元素复制到目标列表。  
  
```  
void assign(
    size_type Count,  
    const Type& Val);

void assign  
    initializer_list<Type> IList);

template <class InputIterator>  
void assign(
    InputIterator First,  
    InputIterator Last);
```  
  
### <a name="parameters"></a>参数  
 `First`  
 要从自变量列表中复制的一系列元素中的第一个元素的位置。  
  
 `Last`  
 超出要从参数列表中复制的一系列元素的范围的第一个元素的位置。  
  
 `Count`  
 要插入列表中的元素副本的数目。  
  
 `Val`  
 要插入到列表中的元素的值。  
  
 `IList`  
 包含要插入的元素的 initializer_list。  
  
### <a name="remarks"></a>备注  
 清除目标列表中的任何现有元素后，将原始列表或其他列表中的一系列指定的元素插入目标列表中，或将指定值的新元素的副本插入目标列表中  
  
### <a name="example"></a>示例  
  
```cpp  
// list_assign.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    list<int> c1, c2;  
    list<int>::const_iterator cIter;  
  
    c1.push_back(10);  
    c1.push_back(20);  
    c1.push_back(30);  
    c2.push_back(40);  
    c2.push_back(50);  
    c2.push_back(60);  
  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    c1.assign(++c2.begin(), c2.end());  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    c1.assign(7, 4);  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    c1.assign({ 10, 20, 30, 40 });  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
}  
```  
  
```Output  
c1 = 10 20 30c1 = 50 60c1 = 4 4 4 4 4 4 4c1 = 10 20 30 40  
```  
  
##  <a name="a-namelistbacka--listback"></a><a name="list__back"></a>list::back  
 返回对列表中最后一个元素的引用。  
  
```  
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>返回值  
 列表的最后一个元素。 如果列表为空，则返回值不确定。  
  
### <a name="remarks"></a>备注  
 如果 **back** 的返回值赋给了 `const_reference`，则不能修改列表对象。 如果 **back** 的返回值赋给了 **reference**，则可以修改列表对象。  
  
 当使用定义为 1 或 2 的 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) 进行编译时，如果试图访问空列表中的元素，则将发生运行时错误。  有关详细信息，请参阅[经过检查的迭代器](../standard-library/checked-iterators.md)。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_back.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 11 );  
  
   int& i = c1.back( );  
   const int& ii = c1.front( );  
  
   cout << "The last integer of c1 is " << i << endl;  
   i--;  
   cout << "The next-to-last integer of c1 is " << ii << endl;  
}  
```  
  
```Output  
The last integer of c1 is 11  
The next-to-last integer of c1 is 10  
```  
  
##  <a name="a-namelistbegina--listbegin"></a><a name="list__begin"></a>list::begin  
 返回发现列表中第一个元素的位置的迭代器。  
  
```  
const_iterator begin() const;

iterator begin();
```  
  
### <a name="return-value"></a>返回值  
 发现列表中第一个元素的位置或空列表之后的位置的双向迭代器。  
  
### <a name="remarks"></a>备注  
 如果 **begin** 的返回值赋给了 `const_iterator`，则无法修改列表对象中的元素。 如果 **begin** 的返回值赋给了 **iterator**，则可以修改列表对象中的元素。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_begin.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter;  
   list <int>::const_iterator c1_cIter;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
  
   c1_Iter = c1.begin( );  
   cout << "The first element of c1 is " << *c1_Iter << endl;  
  
 *c1_Iter = 20;  
   c1_Iter = c1.begin( );  
   cout << "The first element of c1 is now " << *c1_Iter << endl;  
  
   // The following line would be an error because iterator is const  
   // *c1_cIter = 200;  
}  
```  
  
```Output  
The first element of c1 is 1  
The first element of c1 is now 20  
```  
  
##  <a name="a-namelistcbegina--listcbegin"></a><a name="list__cbegin"></a>list::cbegin  
 返回确定范围中第一个元素地址的 `const` 迭代器。  
  
```  
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>返回值  
 `const` 双向访问迭代器，指向范围的第一个元素，或刚超出空范围末尾的位置（对于空范围，`cbegin() == cend()`）。  
  
### <a name="remarks"></a>备注  
 由于使用 `cbegin` 的返回值，因此不能修改范围中的元素。  
  
 可以使用此成员函数替代 `begin()` 成员函数，以保证返回值为 `const_iterator`。 它一般与 [auto](../cpp/auto-cpp.md) 类型推导关键字联合使用，如下例所示。 在该示例中，将 `Container` 视为支持 `begin()` 和 `cbegin()` 的任何类型的可修改（非 `const`）的容器。  
  
```cpp  
auto i1 = Container.begin();
// i1 is Container<T>::iterator   
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator  
```  
  
##  <a name="a-namelistcenda--listcend"></a><a name="list__cend"></a>list::cend  
 返回一个 `const` 迭代器，此迭代器用于发现刚超出范围中最后一个元素的位置。  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>返回值  
 指向刚超出范围末尾的位置的 `const` 双向访问迭代器。  
  
### <a name="remarks"></a>备注  
 `cend` 用于测试迭代器是否超过了其范围的末尾。  
  
 可以使用此成员函数替代 `end()` 成员函数，以保证返回值为 `const_iterator`。 它一般与 [auto](../cpp/auto-cpp.md) 类型推导关键字联合使用，如下例所示。 在此示例中，将 `Container` 视为支持 `end()` 和 `cend()` 的可修改的 (non- `const`) 任何类型的容器。  
  
```cpp  
auto i1 = Container.end();
// i1 is Container<T>::iterator   
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator  
```  
  
 不应对 `cend` 返回的值取消引用。  
  
##  <a name="a-namelistcleara--listclear"></a><a name="list__clear"></a>list::clear  
 消除列表中的全部元素。  
  
```  
void clear();
```  
  
### <a name="example"></a>示例  
  
```cpp  
// list_clear.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main() {  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   cout << "The size of the list is initially " << c1.size( ) << endl;  
   c1.clear( );  
   cout << "The size of list after clearing is " << c1.size( ) << endl;  
}  
```  
  
```Output  
The size of the list is initially 3  
The size of list after clearing is 0  
```  
  
##  <a name="a-namelistconstiteratora--listconstiterator"></a><a name="list__const_iterator"></a>list::const_iterator  
 提供可读取列表中 **const** 元素的双向迭代器的类型。  
  
```  
typedef implementation-defined const_iterator;  
```  
  
### <a name="remarks"></a>备注  
 `const_iterator` 类型不能用于修改元素的值。  
  
### <a name="example"></a>示例  
  请参阅 [back](#list__back) 的示例。  
  
##  <a name="a-namelistconstpointera--listconstpointer"></a><a name="list__const_pointer"></a>list::const_pointer  
 提供指向列表中 `const` 元素的指针。  
  
``` 
typedef typename Allocator::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>备注  
 `const_pointer` 类型不能用于修改元素的值。  
  
 在大多数情况下，应使用 [iterator](#list__iterator) 访问列表对象中的元素。  
  
##  <a name="a-namelistconstreferencea--listconstreference"></a><a name="list__const_reference"></a>list::const_reference  
 提供对存储于列表中供读取和执行 **const** 操作的 **const** 元素的引用的类型。  
  
```  
typedef typename Allocator::const_reference const_reference;  
```  
  
### <a name="remarks"></a>备注  
 `const_reference` 类型不能用于修改元素的值。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_const_ref.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
  
   const list <int> c2 = c1;  
   const int &i = c2.front( );  
   const int &j = c2.back( );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
  
   // The following line would cause an error because c2 is const  
   // c2.push_back( 30 );  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namelistconstreverseiteratora--listconstreverseiterator"></a><a name="list__const_reverse_iterator"></a>list::const_reverse_iterator  
 提供可读取列表中任何 **const** 元素的双向迭代器的类型。  
  
```  
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;  
```  
  
### <a name="remarks"></a>备注  
 `const_reverse_iterator` 类型无法修改元素的值，它用于反向循环访问列表。  
  
### <a name="example"></a>示例  
  请参阅 [rbegin](#list__rbegin) 的示例。  
  
##  <a name="a-namelistcrbegina--listcrbegin"></a><a name="list__crbegin"></a>list::crbegin  
 返回发现反向列表中第一个元素的位置的常量迭代器。  
  
```  
const_reverse_iterator rbegin() const;
```  
  
### <a name="return-value"></a>返回值  
 一个常量反向双向迭代器，用于发现反向 `list` 中的第一个元素（或发现非反向列表中的最后一个元素的内容）。  
  
### <a name="remarks"></a>备注  
 `crbegin` 用于反向列表，正如 [list::begin](#list__begin) 用于 `list` 一样。  
  
 返回值为 `crbegin` 时，无法修改列表对象。 [list::rbegin](#list__rbegin) 可用于向后循环访问列表。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_crbegin.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::const_reverse_iterator c1_crIter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1_crIter = c1.crbegin( );  
   cout << "The last element in the list is " << *c1_crIter << "." << endl;  
}  
```  
  
```Output  
The last element in the list is 30.  
```  
  
##  <a name="a-namelistcrenda--listcrend"></a><a name="list__crend"></a>list::crend  
 返回用于发现反向列表中最后一个元素之后的位置的常量迭代器。  
  
```  
const_reverse_iterator rend() const;
```  
  
### <a name="return-value"></a>返回值  
 一个常量反向双向迭代器，用于发现反向 [list](../standard-library/list-class.md) 中最后一个元素之后的位置（非反向 `list` 中第一个元素之前的位置）。  
  
### <a name="remarks"></a>备注  
 `crend` 用于反向列表，正如 [list::end](#list__end) 用于 `list` 一样。  
  
 返回值为 `crend` 时，无法修改 `list` 对象。  
  
 `crend` 可用于测试反向迭代器是否已到达其 `list` 的末尾。  
  
 不应对 `crend` 返回的值取消引用。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_crend.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::const_reverse_iterator c1_crIter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_crIter = c1.crend( );  
   c1_crIter --;  // Decrementing a reverse iterator moves it forward in   
                 // the list (to point to the first element here)  
   cout << "The first element in the list is: " << *c1_crIter << endl;  
}  
```  
  
```Output  
The first element in the list is: 10  
```  
  
##  <a name="a-namelistdifferencetypea--listdifferencetype"></a><a name="list__difference_type"></a>list::difference_type  
 可用于表示列表中迭代器所指向元素之间元素数目的有符号整数类型。  
  
```  
typedef typename Allocator::difference_type difference_type;  
```  
  
### <a name="remarks"></a>备注  
 `difference_type` 是通过容器迭代器减少或递增时返回的类型。 `difference_type` 通常用于表示迭代器 ` first` 和 ` last` 之间的范围 [ ` first`, ` last`) 内元素的数目，包括 ` first` 指向的元素以及那一系列元素，但不包括 ` last` 指向的元素。  
  
 注意，尽管 `difference_type` 适用于满足输入迭代器（包括可逆容器支持的双向迭代器的类，如集）需求的所有迭代器，迭代器之间的减法仅受随机访问容器（如 [vector 类](../standard-library/vector-class.md)）提供的随机访问迭代器支持。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_diff_type.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <list>  
#include <algorithm>  
  
int main( )   
{  
   using namespace std;  
  
   list <int> c1;  
   list <int>::iterator   c1_Iter, c2_Iter;  
  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1.push_back( 10 );  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
  
   c1_Iter = c1.begin( );  
   c2_Iter = c1.end( );  
  
    list <int>::difference_type df_typ1, df_typ2, df_typ3;  
  
   df_typ1 = count( c1_Iter, c2_Iter, 10 );  
   df_typ2 = count( c1_Iter, c2_Iter, 20 );  
   df_typ3 = count( c1_Iter, c2_Iter, 30 );  
   cout << "The number '10' is in c1 collection " << df_typ1 << " times.\n";  
   cout << "The number '20' is in c1 collection " << df_typ2 << " times.\n";  
   cout << "The number '30' is in c1 collection " << df_typ3 << " times.\n";  
}  
```  
  
```Output  
The number '10' is in c1 collection 1 times.  
The number '20' is in c1 collection 2 times.  
The number '30' is in c1 collection 3 times.  
```  
  
##  <a name="a-namelistemplacea--listemplace"></a><a name="list__emplace"></a>list::emplace  
 将构造的元素插入到列表中的指定位置。  
  
```  
void emplace_back(iterator Where, Type&& val);
```  
  
### <a name="parameters"></a>参数  
  
|||  
|-|-|  
|参数|描述|  
|`Where`|目标 [list](../standard-library/list-class.md) 中插入第一个元素的位置。|  
|` val`|添加到 `list` 末尾的元素。|  
  
### <a name="remarks"></a>备注  
 如果引发了异常，`list` 将保持不变，该异常将被重新引发。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_emplace.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
#include <string>  
  
int main( )   
{  
   using namespace std;  
   list <string> c2;  
   string str("a");  
  
   c2.emplace(c2.begin(), move( str ) );  
   cout << "Moved first element: " << c2.back( ) << endl;  
}  
```  
  
```Output  
Moved first element: a  
```  
  
##  <a name="a-namelistemplacebacka--listemplaceback"></a><a name="list__emplace_back"></a>list::emplace_back  
 在列表的起始位置添加一个就地构造的元素。  
  
```  
void emplace_back(Type&& val);
```  
  
### <a name="parameters"></a>参数  
  
|||  
|-|-|  
|参数|描述|  
|` val`|添加到 [list](../standard-library/list-class.md) 末尾的元素。|  
  
### <a name="remarks"></a>备注  
 如果引发了异常，`list` 将保持不变，该异常将被重新引发。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_emplace_back.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
#include <string>  
  
int main( )   
{  
   using namespace std;  
   list <string> c2;  
   string str("a");  
  
   c2.emplace_back( move( str ) );  
   cout << "Moved first element: " << c2.back( ) << endl;  
}  
```  
  
```Output  
Moved first element: a  
```  
  
##  <a name="a-namelistemplacefronta--listemplacefront"></a><a name="list__emplace_front"></a>list::emplace_front  
 在列表的起始位置添加一个就地构造的元素。  
  
```  
void emplace_front(Type&& val);
```  
  
### <a name="parameters"></a>参数  
  
|||  
|-|-|  
|参数|描述|  
|` val`|要添加到 [list](../standard-library/list-class.md) 开头的元素。|  
  
### <a name="remarks"></a>备注  
 如果引发了异常，`list` 将保持不变，该异常将被重新引发。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_emplace_front.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
#include <string>  
  
int main( )   
{  
   using namespace std;  
   list <string> c2;  
   string str("a");  
  
   c2.emplace_front( move( str ) );  
   cout << "Moved first element: " << c2.front( ) << endl;  
}  
```  
  
```Output  
Moved first element: a  
```  
  
##  <a name="a-namelistemptya--listempty"></a><a name="list__empty"></a>list::empty  
 测试列表是否为空。  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>返回值  
 如果列表为空，则为 **true**；如果列表不为空，则为 **false**。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_empty.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 10 );  
   if ( c1.empty( ) )  
      cout << "The list is empty." << endl;  
   else  
      cout << "The list is not empty." << endl;  
}  
```  
  
```Output  
The list is not empty.  
```  
  
##  <a name="a-namelistenda--listend"></a><a name="list__end"></a>list::end  
 返回用于发现列表中最后一个元素之后的位置的迭代器。  
  
```  
const_iterator end() const;
iterator end();
```  
  
### <a name="return-value"></a>返回值  
 用于发现列表中最后一个元素之后的位置的双向迭代器。 如果列表为空，则 `list::end == list::begin`。  
  
### <a name="remarks"></a>备注  
 **end** 用于测试迭代器是否已到达列表的末尾。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_end.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_Iter = c1.end( );  
   c1_Iter--;  
   cout << "The last integer of c1 is " << *c1_Iter << endl;  
  
   c1_Iter--;  
 *c1_Iter = 400;  
   cout << "The new next-to-last integer of c1 is "  
        << *c1_Iter << endl;  
  
   // If a const iterator had been declared instead with the line:  
   // list <int>::const_iterator c1_Iter;  
   // an error would have resulted when inserting the 400  
  
   cout << "The list is now:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
}  
```  
  
```Output  
The last integer of c1 is 30  
The new next-to-last integer of c1 is 400  
The list is now: 10 400 30  
```  
  
##  <a name="a-namelisterasea--listerase"></a><a name="list__erase"></a>list::erase  
 从列表中的指定位置移除一个或一系列元素。  
  
```  
iterator erase(iterator Where);
iterator erase(iterator first, iterator last);
```  
  
### <a name="parameters"></a>参数  
 `Where`  
 要从列表中移除的元素的位置。  
  
 ` first`  
 要从列表中移除的第一个元素的位置。  
  
 ` last`  
 要从列表中移除的刚超出最后一个元素的位置。  
  
### <a name="return-value"></a>返回值  
 指定已移除的任何元素之外保留的第一个元素的双向迭代器；如果不存在此类元素，则为指向列表末尾的指针。  
  
### <a name="remarks"></a>备注  
 不发生重新分配，因此迭代器和引用仅对已清除元素无效。  
  
 **erase** 永远不会引发异常。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_erase.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator Iter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1.push_back( 40 );  
   c1.push_back( 50 );  
   cout << "The initial list is:";  
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
   c1.erase( c1.begin( ) );  
   cout << "After erasing the first element, the list becomes:";  
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
   Iter = c1.begin( );  
   Iter++;  
   c1.erase( Iter, c1.end( ) );  
   cout << "After erasing all elements but the first, the list becomes: ";  
   for (Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
}  
```  
  
```Output  
The initial list is: 10 20 30 40 50  
After erasing the first element, the list becomes: 20 30 40 50  
After erasing all elements but the first, the list becomes:  20  
```  
  
##  <a name="a-namelistfronta--listfront"></a><a name="list__front"></a>list::front  
 返回对列表中第一个元素的引用。  
  
```  
reference front();
const_reference front() const;
```  
  
### <a name="return-value"></a>返回值  
 如果列表为空，返回的结果则不确定。  
  
### <a name="remarks"></a>备注  
 如果将 `front` 的返回值分配给 `const_reference`，则无法修改列表对象。 如果 `front` 的返回值赋给了 **reference**，则无法修改列表对象。  
  
 当使用定义为 1 或 2 的 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) 进行编译时，如果试图访问空列表中的元素，则将发生运行时错误。  有关详细信息，请参阅[经过检查的迭代器](../standard-library/checked-iterators.md)。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_front.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main() {  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 10 );  
  
   int& i = c1.front();  
   const int& ii = c1.front();  
  
   cout << "The first integer of c1 is " << i << endl;  
   i++;  
   cout << "The first integer of c1 is " << ii << endl;  
}  
```  
  
```Output  
The first integer of c1 is 10  
The first integer of c1 is 11  
```  
  
##  <a name="a-namelistgetallocatora--listgetallocator"></a><a name="list__get_allocator"></a>list::get_allocator  
 返回用于构造列表的分配器对象的一个副本。  
  
```  
Allocator get_allocator() const;
```  
  
### <a name="return-value"></a>返回值  
 列表使用的分配器。  
  
### <a name="remarks"></a>备注  
 列表类的分配器指定类管理存储的方式。 C++ 标准库容器类提供的默认分配器足以满足大多编程需求。 编写和使用你自己的分配器类是高级 C++ 主题。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_get_allocator.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   // The following lines declare objects   
   // that use the default allocator.  
   list <int> c1;  
   list <int, allocator<int> > c2 = list <int, allocator<int> >( allocator<int>( ) );  
  
   // c3 will use the same allocator class as c1  
   list <int> c3( c1.get_allocator( ) );  
  
   list<int>::allocator_type xlst = c1.get_allocator( );  
   // You can now call functions on the allocator class used by c1  
}  
```  
  
##  <a name="a-namelistinserta--listinsert"></a><a name="list__insert"></a>list::insert  
 将一个、几个或一系列元素插入列表中的指定位置。  
  
```  
iterator insert(iterator Where, const Type& Val);
iterator insert(iterator Where, Type&& Val);

void insert(iterator Where, size_type Count, const Type& Val);
iterator insert(iterator Where, initializer_list<Type> IList);

template <class InputIterator>  
void insert(iterator Where, InputIterator First, InputIterator Last);
```  
  
### <a name="parameters"></a>参数  
  
|||  
|-|-|  
|参数|描述|  
|`Where`|目标列表中插入第一个元素的位置。|  
|`Val`|要插入到列表中的元素的值。|  
|`Count`|要插入列表中的元素数目。|  
|`First`|要从参数列表中复制的一系列元素中第一个元素的位置。|  
|`Last`|要从自变量列表中复制的一系列元素以外的第一个元素的位置。|  
  
### <a name="return-value"></a>返回值  
 前两个插入函数返回一个迭代器，该迭代器指向新元素插入到列表中的位置。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_class_insert.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
#include <string>  
  
int main()  
{  
    using namespace std;  
    list <int> c1, c2;  
    list <int>::iterator Iter;  
  
    c1.push_back(10);  
    c1.push_back(20);  
    c1.push_back(30);  
    c2.push_back(40);  
    c2.push_back(50);  
    c2.push_back(60);  
  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    Iter = c1.begin();  
    Iter++;  
    c1.insert(Iter, 100);  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    Iter = c1.begin();  
    Iter++;  
    Iter++;  
    c1.insert(Iter, 2, 200);  
  
    cout << "c1 =";  
    for(auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    c1.insert(++c1.begin(), c2.begin(), --c2.end());  
  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    // initialize a list of strings by moving  
    list < string > c3;  
    string str("a");  
  
    c3.insert(c3.begin(), move(str));  
    cout << "Moved first element: " << c3.front() << endl;  
  
    // Assign with an initializer_list  
    list <int> c4{ {1, 2, 3, 4} };  
    c4.insert(c4.begin(), { 5, 6, 7, 8 });  
  
    cout << "c4 =";  
    for (auto c : c4)  
        cout << " " << c;  
    cout << endl;  
}  
```  
  
##  <a name="a-namelistiteratora--listiterator"></a><a name="list__iterator"></a>list::iterator  
 提供可读取或修改列表中任何元素的双向迭代器的类型。  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="remarks"></a>备注  
 **iterator** 类型可用于修改元素的值。  
  
### <a name="example"></a>示例  
  请参阅 [begin](#list__begin) 的示例。  
  
##  <a name="a-namelistlista--listlist"></a><a name="list__list"></a>list::list  
 构造一个列表，它具有特定大小或它的元素具有特定值，或具有特定分配器或作为其他列表的全部或部分副本。  
  
```  
list();
explicit list(const Allocator& Al);
explicit list(size_type Count);
list(size_type Count, const Type& Val);
list(size_type Count, const Type& Val, const Allocator& Al);

list(const list& Right);
list(list&& Right);
list(initializer_list<Type> IList, const Allocator& Al);

template <class InputIterator>  
list(InputIterator First, InputIterator Last);

template <class InputIterator>  
list(InputIterator First, InputIterator Last, const Allocator& Al);
```  
  
### <a name="parameters"></a>参数  
  
|||  
|-|-|  
|参数|描述|  
|`Al`|要用于此对象的分配器类。|  
|`Count`|所构造列表中元素的数目。|  
|`Val`|列表中元素的值。|  
|`Right`|所构造列表要作为其副本的列表。|  
|`First`|要复制的范围元素中的第一个元素的位置。|  
|`Last`|要复制的元素范围以外的第一个元素的位置。|  
|`IList`|包含要复制的元素的 initializer_list。|  
  
### <a name="remarks"></a>备注  
 所有构造函数都存储一个分配器对象 (`Al`) 并初始化列表。  
  
 [get_allocator](#list__get_allocator) 返回用于构造列表的分配器对象的副本。  
  
 第一个构造函数指定一个空的初始列表，第二个指定要使用的分配器类型 (`Al`)。  
  
 第三个构造函数指定特定数目 (`Count`) 的元素的重复，这些元素具有类 **Type** 的默认值。  
  
 第四个和第五个构造函数指定 (`Count`) 元素的重复，元素的值为 `Val`。  
  
 第六个构造函数指定列表 `Right` 的副本。  
  
 第七个构造函数移动列表 `Right`。  
  
 第八个构造函数使用 initializer_list 指定元素。  
  
 接下来的两个构造函数复制列表的范围 `[First, Last)`。  
  
 所有构造函数均不执行任何临时重新分配。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_class_list.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    // Create an empty list c0  
    list <int> c0;  
  
    // Create a list c1 with 3 elements of default value 0  
    list <int> c1(3);  
  
    // Create a list c2 with 5 elements of value 2  
    list <int> c2(5, 2);  
  
    // Create a list c3 with 3 elements of value 1 and with the   
    // allocator of list c2  
    list <int> c3(3, 1, c2.get_allocator());  
  
    // Create a copy, list c4, of list c2  
    list <int> c4(c2);  
  
    // Create a list c5 by copying the range c4[ first,  last)  
    list <int>::iterator c4_Iter = c4.begin();  
    c4_Iter++;  
    c4_Iter++;  
    list <int> c5(c4.begin(), c4_Iter);  
  
    // Create a list c6 by copying the range c4[ first,  last) and with   
    // the allocator of list c2  
    c4_Iter = c4.begin();  
    c4_Iter++;  
    c4_Iter++;  
    c4_Iter++;  
    list <int> c6(c4.begin(), c4_Iter, c2.get_allocator());  
  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    cout << "c2 =";  
    for (auto c : c2)  
        cout << " " << c;  
    cout << endl;  
  
    cout << "c3 =";  
    for (auto c : c3)  
        cout << " " << c;  
    cout << endl;  
  
    cout << "c4 =";  
    for (auto c : c4)  
        cout << " " << c;  
    cout << endl;  
  
    cout << "c5 =";  
    for (auto c : c5)  
        cout << " " << c;  
    cout << endl;  
  
    cout << "c6 =";  
    for (auto c : c6)  
        cout << " " << c;  
    cout << endl;  
  
    // Move list c6 to list c7  
    list <int> c7(move(c6));  
    cout << "c7 =";  
    for (auto c : c7)  
        cout << " " << c;  
    cout << endl;  
  
    // Construct with initializer_list  
    list<int> c8({ 1, 2, 3, 4 });  
    cout << "c8 =";  
    for (auto c : c8)  
        cout << " " << c;  
    cout << endl;  
}  
```  
  
```Output  
c1 = 0 0 0c2 = 2 2 2 2 2c3 = 1 1 1c4 = 2 2 2 2 2c5 = 2 2c6 = 2 2 2c7 = 2 2 2c8 = 1 2 3 4  
```  
  
##  <a name="a-namelistmaxsizea--listmaxsize"></a><a name="list__max_size"></a>list::max_size  
 返回列表的最大长度。  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>返回值  
 列表的最大可取长度。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_max_size.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::size_type i;  
  
   i = c1.max_size( );  
   cout << "Maximum possible length of the list is " << i << "." << endl;  
}  
```  
  
##  <a name="a-namelistmergea--listmerge"></a><a name="list__merge"></a>list::merge  
 将元素从参数列表移除，将它们插入目标列表，将新的组合元素集以升序或其他指定顺序排序。  
  
```  
void merge(list<Type, Allocator>& right);

template <class Traits>  
void merge(list<Type, Allocator>& right, Traits comp);
```  
  
### <a name="parameters"></a>参数  
 ` right`  
 要与目标列表合并的自变量列表。  
  
 ` comp`  
 用于排列目标列表元素的比较运算符。  
  
### <a name="remarks"></a>备注  
 参数列表 ` right` 与目标列表合并。  
  
 参数列表和目标列表必须用相同的比较关系进行排序，生成的序列将以这种关系进行排序。 第一个成员函数的默认排列顺序是升序。 第二个成员函数执行 **Traits** 类中用户指定的比较运算 ` comp`。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_merge.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1, c2, c3;  
   list <int>::iterator c1_Iter, c2_Iter, c3_Iter;  
  
   c1.push_back( 3 );  
   c1.push_back( 6 );  
   c2.push_back( 2 );  
   c2.push_back( 4 );  
   c3.push_back( 5 );  
   c3.push_back( 1 );  
  
   cout << "c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   cout << "c2 =";  
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )  
      cout << " " << *c2_Iter;  
   cout << endl;  
  
   c2.merge( c1 );  // Merge c1 into c2 in (default) ascending order  
   c2.sort( greater<int>( ) );  
   cout << "After merging c1 with c2 and sorting with >: c2 =";  
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )  
      cout << " " << *c2_Iter;  
   cout << endl;  
  
   cout << "c3 =";  
   for ( c3_Iter = c3.begin( ); c3_Iter != c3.end( ); c3_Iter++ )  
      cout << " " << *c3_Iter;  
   cout << endl;  
  
   c2.merge( c3, greater<int>( ) );  
   cout << "After merging c3 with c2 according to the '>' comparison relation: c2 =";  
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )  
      cout << " " << *c2_Iter;  
   cout << endl;  
}  
```  
  
```Output  
c1 = 3 6  
c2 = 2 4  
After merging c1 with c2 and sorting with >: c2 = 6 4 3 2  
c3 = 5 1  
After merging c3 with c2 according to the '>' comparison relation: c2 = 6 5 4 3 2 1  
```  
  
##  <a name="a-namelistoperatoreqa--listoperator"></a><a name="list__operator_eq"></a>list::operator=  
 用另一个列表的副本替换列表中的元素。  
  
```  
list& operator=(const list& right);
list& operator=(list&& right);
```  
  
### <a name="parameters"></a>参数  
  
|||  
|-|-|  
|参数|说明|  
|` right`|要复制到 `list` 中的 [list](../standard-library/list-class.md)。|  
  
### <a name="remarks"></a>备注  
 消除 `list` 中的任何现有元素后，运算符会将 ` right` 的内容复制或移动到 `list` 内。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_operator_as.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   list<int> v1, v2, v3;  
   list<int>::iterator iter;  
  
   v1.push_back(10);  
   v1.push_back(20);  
   v1.push_back(30);  
   v1.push_back(40);  
   v1.push_back(50);  
  
   cout << "v1 = " ;  
   for (iter = v1.begin(); iter != v1.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
  
   v2 = v1;  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
  
// move v1 into v2  
   v2.clear();  
   v2 = forward< list<int> >(v1);  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
}  
```  
  
##  <a name="a-namelistpointera--listpointer"></a><a name="list__pointer"></a>list::pointer  
 提供指向列表元素的指针。  
  
```
typedef typename Allocator::pointer pointer;  
```  
  
### <a name="remarks"></a>备注  
 **pointer** 类型可用于修改元素的值。  
  
 在大多数情况下，应使用 [iterator](#list__iterator) 访问列表对象中的元素。  
  
##  <a name="a-namelistpopbacka--listpopback"></a><a name="list__pop_back"></a>list::pop_back  
 删除列表末尾的元素。  
  
``` 
void pop_back();
```  
  
### <a name="remarks"></a>备注  
 最后一个元素不得为空。 `pop_back` 绝不会引发异常。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_pop_back.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   cout << "The first element is: " << c1.front( ) << endl;  
   cout << "The last element is: " << c1.back( ) << endl;  
  
   c1.pop_back( );  
   cout << "After deleting the element at the end of the list, "  
           "the last element is: " << c1.back( ) << endl;  
}  
```  
  
```Output  
The first element is: 1  
The last element is: 2  
After deleting the element at the end of the list, the last element is: 1  
```  
  
##  <a name="a-namelistpopfronta--listpopfront"></a><a name="list__pop_front"></a>list::pop_front  
 删除列表起始处的一个元素。  
  
``` 
void pop_front();
```  
  
### <a name="remarks"></a>备注  
 第一个元素不得为空。 `pop_front` 绝不会引发异常。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_pop_front.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   cout << "The first element is: " << c1.front( ) << endl;  
   cout << "The second element is: " << c1.back( ) << endl;  
  
   c1.pop_front( );  
   cout << "After deleting the element at the beginning of the list, "  
         "the first element is: " << c1.front( ) << endl;  
}  
```  
  
```Output  
The first element is: 1  
The second element is: 2  
After deleting the element at the beginning of the list, the first element is: 2  
```  
  
##  <a name="a-namelistpushbacka--listpushback"></a><a name="list__push_back"></a>list::push_back  
 在列表的末尾添加元素。  
  
```  
void push_back(void push_back(Type&& val);
```  
  
### <a name="parameters"></a>参数  
  
|||  
|-|-|  
|参数|描述|  
|` val`|添加到列表末尾的元素。|  
  
### <a name="remarks"></a>备注  
 如果引发异常，列表将保持不变，该异常将被重新引发。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_push_back.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
#include <string>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 1 );  
   if ( c1.size( ) != 0 )  
      cout << "Last element: " << c1.back( ) << endl;  
  
   c1.push_back( 2 );  
   if ( c1.size( ) != 0 )  
      cout << "New last element: " << c1.back( ) << endl;  
  
// move initialize a list of strings  
   list <string> c2;  
   string str("a");  
  
   c2.push_back( move( str ) );  
   cout << "Moved first element: " << c2.back( ) << endl;  
}  
```  
  
```Output  
Last element: 1  
New last element: 2  
Moved first element: a  
```  
  
##  <a name="a-namelistpushfronta--listpushfront"></a><a name="list__push_front"></a>list::push_front  
 在列表的开头添加元素。  
  
```  
void push_front(const Type& val);
void push_front(Type&& val);
```  
  
### <a name="parameters"></a>参数  
  
|||  
|-|-|  
|参数|描述|  
|` val`|要添加到列表开头的元素。|  
  
### <a name="remarks"></a>备注  
 如果引发异常，列表将保持不变，该异常将被重新引发。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_push_front.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
#include <string>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_front( 1 );  
   if ( c1.size( ) != 0 )  
      cout << "First element: " << c1.front( ) << endl;  
  
   c1.push_front( 2 );  
   if ( c1.size( ) != 0 )  
      cout << "New first element: " << c1.front( ) << endl;  
  
// move initialize a list of strings  
   list <string> c2;  
   string str("a");  
  
   c2.push_front( move( str ) );  
   cout << "Moved first element: " << c2.front( ) << endl;  
}  
```  
  
```Output  
First element: 1  
New first element: 2  
Moved first element: a  
```  
  
##  <a name="a-namelistrbegina--listrbegin"></a><a name="list__rbegin"></a>list::rbegin  
 返回一个迭代器，此迭代器用于发现反向列表中的第一个元素。  
  
``` 
const_reverse_iterator rbegin() const;
reverse_iterator rbegin();
```  
  
### <a name="return-value"></a>返回值  
 一个发现反向列表中的第一个元素（或发现非反向列表中的最后一个元素的内容）的反向双向迭代器。  
  
### <a name="remarks"></a>备注  
 `rbegin` 用于反向列表，正如 [begin](#list__begin) 用于列表一样。  
  
 如果将 `rbegin` 的返回值分配给 `const_reverse_iterator`，则无法修改列表对象。 如果将 `rbegin` 的返回值分配给 `reverse_iterator`，则可修改列表对象。  
  
 `rbegin` 可用于向后循环访问列表。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_rbegin.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter;  
   list <int>::reverse_iterator c1_rIter;  
  
   // If the following line replaced the line above, *c1_rIter = 40;  
   // (below) would be an error  
   //list <int>::const_reverse_iterator c1_rIter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1_rIter = c1.rbegin( );  
   cout << "The last element in the list is " << *c1_rIter << "." << endl;  
  
   cout << "The list is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   // rbegin can be used to start an iteration through a list in   
   // reverse order  
   cout << "The reversed list is:";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << " " << *c1_rIter;  
   cout << endl;  
  
   c1_rIter = c1.rbegin( );  
 *c1_rIter = 40;  
   cout << "The last element in the list is now " << *c1_rIter << "." << endl;  
}  
```  
  
```Output  
The last element in the list is 30.  
The list is: 10 20 30  
The reversed list is: 30 20 10  
The last element in the list is now 40.  
```  
  
##  <a name="a-namelistreferencea--listreference"></a><a name="list__reference"></a>list::reference  
 提供对存储在列表中的元素的引用的类型。  
  
```  
typedef typename Allocator::reference reference;  
```  
  
### <a name="example"></a>示例  
  
```cpp  
// list_ref.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
  
   int &i = c1.front( );  
   int &j = c1.back( );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namelistremovea--listremove"></a><a name="list__remove"></a>list::remove  
 清除列表中与指定值匹配的元素。  
  
``` 
void remove(const Type& val);
```  
  
### <a name="parameters"></a>参数  
 ` val`  
 一个值，如果某个元素包含该值，则会导致从列表中删除该元素。  
  
### <a name="remarks"></a>备注  
 剩余元素的排序不受影响。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_remove.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter, c2_Iter;  
  
   c1.push_back( 5 );  
   c1.push_back( 100 );  
   c1.push_back( 5 );  
   c1.push_back( 200 );  
   c1.push_back( 5 );  
   c1.push_back( 300 );  
  
   cout << "The initial list is c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   list <int> c2 = c1;  
   c2.remove( 5 );  
   cout << "After removing elements with value 5, the list becomes c2 =";  
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )  
      cout << " " << *c2_Iter;  
   cout << endl;  
}  
```  
  
```Output  
The initial list is c1 = 5 100 5 200 5 300  
After removing elements with value 5, the list becomes c2 = 100 200 300  
```  
  
##  <a name="a-namelistremoveifa--listremoveif"></a><a name="list__remove_if"></a>list::remove_if  
 将满足指定谓词的元素从列表中消除。  
  
``` 
template <class Predicate>  
void remove_if(Predicate pred)  
```  
  
### <a name="parameters"></a>参数  
 ` pred`  
 一元谓词，如果元素满足该谓词，则该谓词会导致此元素从列表删除。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_remove_if.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
template <class T> class is_odd : public std::unary_function<T, bool>   
{  
public:  
   bool operator( ) ( T& val )   
   {  
   return ( val % 2 ) == 1;  
   }  
};  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter, c2_Iter;  
  
   c1.push_back( 3 );  
   c1.push_back( 4 );  
   c1.push_back( 5 );  
   c1.push_back( 6 );  
   c1.push_back( 7 );  
   c1.push_back( 8 );  
  
   cout << "The initial list is c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   list <int> c2 = c1;  
   c2.remove_if( is_odd<int>( ) );  
  
   cout << "After removing the odd elements, "  
        << "the list becomes c2 =";  
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )  
      cout << " " << *c2_Iter;  
   cout << endl;  
}  
```  
  
```Output  
The initial list is c1 = 3 4 5 6 7 8  
After removing the odd elements, the list becomes c2 = 4 6 8  
```  
  
##  <a name="a-namelistrenda--listrend"></a><a name="list__rend"></a>list::rend  
 返回发现反向列表中最后一个元素之后的位置的迭代器。  
  
``` 
const_reverse_iterator rend() const;
reverse_iterator rend();
```  
  
### <a name="return-value"></a>返回值  
 一个反向双向迭代器，用于发现反向列表中最后一个元素之后的位置（非反向列表中第一个元素之前的位置）。  
  
### <a name="remarks"></a>备注  
 `rend` 用于反向列表，正如 [end](#list__end) 用于列表一样。  
  
 如果将 `rend` 的返回值分配给 `const_reverse_iterator`，则无法修改列表对象。 如果将 `rend` 的返回值分配给 `reverse_iterator`，则可修改列表对象。  
  
 `rend` 可用于测试反向迭代器是否已到达其列表的末尾。  
  
 不应对 `rend` 返回的值取消引用。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_rend.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter;  
   list <int>::reverse_iterator c1_rIter;  
  
   // If the following line had replaced the line above, an error would   
   // have resulted in the line modifying an element (commented below)  
   // because the iterator would have been const  
   // list <int>::const_reverse_iterator c1_rIter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_rIter = c1.rend( );  
   c1_rIter --;  // Decrementing a reverse iterator moves it forward in   
                 // the list (to point to the first element here)  
   cout << "The first element in the list is: " << *c1_rIter << endl;  
  
   cout << "The list is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   // rend can be used to test if an iteration is through all of the   
   // elements of a reversed list  
   cout << "The reversed list is:";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << " " << *c1_rIter;  
   cout << endl;  
  
   c1_rIter = c1.rend( );  
   c1_rIter--;  // Decrementing the reverse iterator moves it backward   
                // in the reversed list (to the last element here)  
  
 *c1_rIter = 40;  // This modification of the last element would have   
                    // caused an error if a const_reverse iterator had   
                    // been declared (as noted above)  
  
   cout << "The modified reversed list is:";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << " " << *c1_rIter;  
   cout << endl;  
}  
```  
  
```Output  
The first element in the list is: 10  
The list is: 10 20 30  
The reversed list is: 30 20 10  
The modified reversed list is: 30 20 40  
```  
  
##  <a name="a-namelistresizea--listresize"></a><a name="list__resize"></a>list::resize  
 为列表指定新的大小。  
  
``` 
void resize(size_type _Newsize);
void resize(size_type _Newsize, Type val);
```  
  
### <a name="parameters"></a>参数  
 `_Newsize`  
 列表的新大小。  
  
 ` val`  
 新的大小大于原始大小时要添加至列表的新元素的值。 如果省略此值，则会赋给新元素此类的默认值。  
  
### <a name="remarks"></a>备注  
 如果列表的大小小于请求的大小 `_Newsize`，那么会在列表中添加元素，直到该列表达到请求的大小。  
  
 如果列表的大小大于请求的大小，最接近列表末尾的元素将被删除，直到该列表达到 `_Newsize` 大小。  
  
 如果列表的当前大小与请求的大小相同，则不采取任何操作。  
  
 [size](#list__size) 表示列表的当前大小。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_resize.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{   
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1.resize( 4,40 );  
   cout << "The size of c1 is " << c1.size( ) << endl;  
   cout << "The value of the last element is " << c1.back( ) << endl;  
  
   c1.resize( 5 );  
   cout << "The size of c1 is now " << c1.size( ) << endl;  
   cout << "The value of the last element is now " << c1.back( ) << endl;  
  
   c1.resize( 2 );  
   cout << "The reduced size of c1 is: " << c1.size( ) << endl;  
   cout << "The value of the last element is now " << c1.back( ) << endl;  
}  
```  
  
```Output  
The size of c1 is 4  
The value of the last element is 40  
The size of c1 is now 5  
The value of the last element is now 0  
The reduced size of c1 is: 2  
The value of the last element is now 20  
```  
  
##  <a name="a-namelistreversea--listreverse"></a><a name="list__reverse"></a>list::reverse  
 反转列表中元素的顺序。  
  
``` 
void reverse();
```  
  
### <a name="example"></a>示例  
  
```cpp  
// list_reverse.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   cout << "c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   c1.reverse( );  
   cout << "Reversed c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
}  
```  
  
```Output  
c1 = 10 20 30  
Reversed c1 = 30 20 10  
```  
  
##  <a name="a-namelistreverseiteratora--listreverseiterator"></a><a name="list__reverse_iterator"></a>list::reverse_iterator  
 提供可读取或修改反向列表中的元素的双向迭代器的类型。  
  
```  
typedef std::reverse_iterator<iterator> reverse_iterator;  
```  
  
### <a name="remarks"></a>备注  
 `reverse_iterator` 类型用于反向循环访问列表。  
  
### <a name="example"></a>示例  
  请参阅 [rbegin](#list__rbegin) 的示例。  
  
##  <a name="a-namelistsizea--listsize"></a><a name="list__size"></a>list::size  
 返回列表中元素的数目。  
  
``` 
size_type size() const;
```  
  
### <a name="return-value"></a>返回值  
 列表的当前长度。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_size.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   list <int> c1;  
   list <int>::size_type i;  
  
   c1.push_back( 5 );  
   i = c1.size( );  
   cout << "List length is " << i << "." << endl;  
  
   c1.push_back( 7 );  
   i = c1.size( );  
   cout << "List length is now " << i << "." << endl;  
}  
```  
  
```Output  
List length is 1.  
List length is now 2.  
```  
  
##  <a name="a-namelistsizetypea--listsizetype"></a><a name="list__size_type"></a>list::size_type  
 计算列表中元素的数目的类型。  
  
```  
typedef typename Allocator::size_type size_type;  
```  
  
### <a name="example"></a>示例  
  请参阅 [size](#list__size) 的示例。  
  
##  <a name="a-namelistsorta--listsort"></a><a name="list__sort"></a>list::sort  
 按升序或用户指定的其他顺序排列列表元素。  
  
``` 
void sort();

template <class Traits>  
void sort(Traits comp);
```  
  
### <a name="parameters"></a>参数  
 ` comp`  
 用于排列连续元素的比较运算符。  
  
### <a name="remarks"></a>备注  
 默认情况下，第一个成员函数将按升序排列元素。  
  
 成员模板函数将根据 **Traits** 类中用户指定的比较运算 ` comp` 排列元素。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_sort.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter;  
  
   c1.push_back( 20 );  
   c1.push_back( 10 );  
   c1.push_back( 30 );  
  
   cout << "Before sorting: c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   c1.sort( );  
   cout << "After sorting c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   c1.sort( greater<int>( ) );  
   cout << "After sorting with 'greater than' operation, c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
}  
```  
  
```Output  
Before sorting: c1 = 20 10 30  
After sorting c1 = 10 20 30  
After sorting with 'greater than' operation, c1 = 30 20 10  
```  
  
##  <a name="a-namelistsplicea--listsplice"></a><a name="list__splice"></a>list::splice  
 从源列表中删除元素并将其插入到目标列表中。  
  
```  
// insert the entire source list  
void splice(const_iterator Where, list<Type, Allocator>& Source);
void splice(const_iterator Where, list<Type, Allocator>&& Source); 

// insert one element of the source list  
void splice(const_iterator Where, list<Type, Allocator>& Source, const_iterator Iter);
void splice(const_iterator Where, list<Type, Allocator>&& Source, const_iterator Iter);
 
// insert a range of elements from the source list  
void splice(const_iterator Where, list<Type, Allocator>& Source, const_iterator First, const_iterator Last);
void splice(const_iterator Where, list<Type, Allocator>&& Source, const_iterator First, const_iterator Last);
```  
  
### <a name="parameters"></a>参数  
 `Where`  
 目标列表中要在其前面进行插入的位置。  
  
 `Source`  
 要插入目标列表中的源列表。  
  
 `Iter`  
 要从源列表中进行插入的元素。  
  
 `First`  
 要从源列表中进行插入的范围中的第一个元素。  
  
 `Last`  
 要从源列表中进行插入的范围中的最后一个元素之外的第一个位置。  
  
### <a name="remarks"></a>备注  
 第一对成员函数在 `Where` 所引用的位置之前，将源列表中的所有元素插入到目标列表中，然后从源列表中删除所有元素。 （`&Source` 不得等于 `this`。）  
  
 第二对成员函数将在 `Iter` 所引用的目标列表中的位置之前，插入 `Where` 所引用的元素，然后从源列表中删除 `Iter`。 （如果 `Where == Iter || Where == ++Iter`，则不会发生更改。）  
  
 第三对成员函数将在 `Where` 所引用的目标列表中的元素之前，插入由 [ `First`, `Last`) 指定的范围，然后从源列表中删除该元素范围。 （如果 `&Source == this`，则范围 `[First, Last)` 不得包含 `Where` 所指向的元素。）  
  
 如果范围接合插入 `N` 个元素和 `&Source != this`，则类 [iterator](../standard-library/forward-list-class.md#forward_list__iterator) 的对象会递增 `N` 次。  
  
 在所有情况下，迭代器、指针或引用接合的元素的引用都会保持有效状态且会转换为目标容器。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_splice.cpp  
// compile with: /EHsc /W4  
#include <list>  
#include <iostream>  
  
using namespace std;  
  
template <typename S> void print(const S& s) {  
    cout << s.size() << " elements: ";  
  
    for (const auto& p : s) {  
        cout << "(" << p << ") ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
    list<int> c1{10,11};  
    list<int> c2{20,21,22};  
    list<int> c3{30,31};  
    list<int> c4{40,41,42,43};  
  
    list<int>::iterator where_iter;  
    list<int>::iterator first_iter;  
    list<int>::iterator last_iter;  
  
    cout << "Beginning state of lists:" << endl;  
    cout << "c1 = ";  
    print(c1);  
    cout << "c2 = ";  
    print(c2);  
    cout << "c3 = ";  
    print(c3);  
    cout << "c4 = ";  
    print(c4);  
  
    where_iter = c2.begin();  
    ++where_iter; // start at second element  
    c2.splice(where_iter, c1);  
    cout << "After splicing c1 into c2:" << endl;  
    cout << "c1 = ";  
    print(c1);  
    cout << "c2 = ";  
    print(c2);  
  
    first_iter = c3.begin();  
    c2.splice(where_iter, c3, first_iter);  
    cout << "After splicing the first element of c3 into c2:" << endl;  
    cout << "c3 = ";  
    print(c3);  
    cout << "c2 = ";  
    print(c2);  
  
    first_iter = c4.begin();  
    last_iter = c4.end();  
    // set up to get the middle elements  
    ++first_iter;  
    --last_iter;  
    c2.splice(where_iter, c4, first_iter, last_iter);  
    cout << "After splicing a range of c4 into c2:" << endl;  
    cout << "c4 = ";  
    print(c4);  
    cout << "c2 = ";  
    print(c2);  
}  
  
```  
  
```Output  
Beginning state of lists:c1 = 2 elements: (10) (11)c2 = 3 elements: (20) (21) (22)c3 = 2 elements: (30) (31)c4 = 4 elements: (40) (41) (42) (43)After splicing c1 into c2:c1 = 0 elements:c2 = 5 elements: (20) (10) (11) (21) (22)After splicing the first element of c3 into c2:c3 = 1 elements: (31)c2 = 6 elements: (20) (10) (11) (30) (21) (22)After splicing a range of c4 into c2:c4 = 2 elements: (40) (43)c2 = 8 elements: (20) (10) (11) (30) (41) (42) (21) (22)  
```  
  
##  <a name="a-namelistswapa--listswap"></a><a name="list__swap"></a>list::swap  
 交换两个列表的元素。  
  
``` 
void swap(list<Type, Allocator>& right);
friend void swap(list<Type, Allocator>& left, list<Type, Allocator>& right)  
```  
  
### <a name="parameters"></a>参数  
 ` right`  
 提供要交换的元素的列表，或其元素将要与列表 ` left` 的元素交换的列表。  
  
 ` left`  
 其元素将与列表 ` right` 的进行交换的列表。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_swap.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   list <int> c1, c2, c3;  
   list <int>::iterator c1_Iter;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   c1.push_back( 3 );  
   c2.push_back( 10 );  
   c2.push_back( 20 );  
   c3.push_back( 100 );  
  
   cout << "The original list c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   c1.swap( c2 );  
  
   cout << "After swapping with c2, list c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   swap( c1,c3 );  
  
   cout << "After swapping with c3, list c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
}  
```  
  
```Output  
The original list c1 is: 1 2 3  
After swapping with c2, list c1 is: 10 20  
After swapping with c3, list c1 is: 100  
```  
  
##  <a name="a-namelistuniquea--listunique"></a><a name="list__unique"></a>list::unique  
 从列表中删除满足某些其他二元谓词的相邻重复元素或相邻元素。  
  
```  
void unique();

template <class BinaryPredicate>  
void unique(BinaryPredicate pred);
```  
  
### <a name="parameters"></a>参数  
 ` pred`  
 用于比较连续元素的二元谓词。  
  
### <a name="remarks"></a>备注  
 此函数假设列表是经过排序的，因此所有重复元素都是相邻的。 不相邻的重复元素将不被删除。  
  
 第一个成员函数删除比较等于其前一个元素的每个元素。  
  
 第二个成员函数删除与前一个元素比较时满足谓词函数 ` pred` 的元素。 可以使用在 pred 自变量的 `<functional>` 标头中声明的任何二元函数对象，也可以创建自己的二元函数对象。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_unique.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter, c2_Iter,c3_Iter;  
   not_equal_to<int> mypred;  
  
   c1.push_back( -10 );  
   c1.push_back( 10 );  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 20 );  
   c1.push_back( -10 );  
  
   cout << "The initial list is c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   list <int> c2 = c1;  
   c2.unique( );  
   cout << "After removing successive duplicate elements, c2 =";  
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )  
      cout << " " << *c2_Iter;  
   cout << endl;  
  
   list <int> c3 = c2;  
   c3.unique( mypred );  
   cout << "After removing successive unequal elements, c3 =";  
   for ( c3_Iter = c3.begin( ); c3_Iter != c3.end( ); c3_Iter++ )  
      cout << " " << *c3_Iter;  
   cout << endl;  
}  
```  
  
```Output  
The initial list is c1 = -10 10 10 20 20 -10  
After removing successive duplicate elements, c2 = -10 10 20 -10  
After removing successive unequal elements, c3 = -10 -10  
```  
  
##  <a name="a-namelistvaluetypea--listvaluetype"></a><a name="list__value_type"></a>list::value_type  
 表示列表中存储的数据类型的类型。  
  
```  
typedef typename Allocator::value_type value_type;  
```  
  
### <a name="remarks"></a>备注  
 `value_type` 是模板参数 **Type** 的同义词。  
  
### <a name="example"></a>示例  
  
```cpp  
// list_value_type.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list<int>::value_type AnInt;  
   AnInt = 44;  
   cout << AnInt << endl;  
}  
```  
  
```Output  
44  
```  
  
## <a name="see-also"></a>另请参阅  
 [\<list>](../standard-library/list.md)   
 [C++ 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 标准库参考](../standard-library/cpp-standard-library-reference.md)

