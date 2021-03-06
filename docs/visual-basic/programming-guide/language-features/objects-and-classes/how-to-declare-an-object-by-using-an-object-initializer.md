---
title: 如何：使用对象初始值设定项声明对象
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: ae04d338b61027c3917ad3a7f62ff40f0a95e53e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347128"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a>如何：使用对象初始值设定项声明对象 (Visual Basic)
使用对象初始值设定项可在单个语句中声明和实例化类的实例。 此外，您可以同时初始化实例的一个或多个成员，而无需调用参数化的构造函数。  
  
 使用对象初始值设定项创建命名类型的实例时，将调用类的无参数构造函数，然后按照指定的顺序初始化指定成员。  
  
 下面的过程演示了如何通过三种不同的方式创建 `Student` 类的实例。 类具有名字、姓氏和类年属性以及其他属性。 这三个声明都创建 `Student`的新实例，并将属性 `First` 设置为 "Michael"，将 `Last` 属性设置为 "Tucker"，将所有其他成员设置为其默认值。 此过程中每个声明的结果等效于下面的示例，该示例不使用对象初始值设定项。  
  
 [!code-vb[VbVbalrObjectInit#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#20)]  
  
 有关 `Student` 类的实现，请参阅[如何：创建项列表](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)。 你可以从该主题复制代码以设置类，并创建要使用的 `Student` 对象的列表。  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a>使用对象初始值设定项创建命名类的对象  
  
1. 开始声明，就像计划使用构造函数一样。  
  
     `Dim student1 As New Student`  
  
2. 键入关键字 `With`，后跟一个用大括号括起来的初始化列表。  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3. 在初始化列表中，包含要初始化的每个属性，并为其分配初始值。 属性的名称前面有一个句点。  
  
     [!code-vb[VbVbalrObjectInit#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#21)]  
  
     可以初始化类的一个或多个成员。  
  
4. 或者，可以声明类的新实例，然后为其赋值。 首先，将 `Student`的实例声明为：  
  
     `Dim student2 As Student`  
  
5. 以正常方式开始创建 `Student` 实例。  
  
     `Dim student2 As Student = New Student`  
  
6. 键入 `With` 然后使用对象初始值设定项来初始化新实例的一个或多个成员。  
  
     [!code-vb[VbVbalrObjectInit#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#22)]  
  
7. 您可以通过省略 `As Student`来简化前一步骤中的定义。 如果执行此操作，编译器将通过使用局部类型推理来确定 `student3` 是 `Student` 的实例。  
  
     [!code-vb[VbVbalrObjectInit#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#23)]  
  
     有关详细信息，请参阅[局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。  
  
## <a name="see-also"></a>另请参阅

- [局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [如何：创建项列表](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)
- [对象初始值设定项：命名类型和匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
