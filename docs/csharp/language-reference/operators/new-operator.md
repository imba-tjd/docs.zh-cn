---
title: new 运算符 - C# 参考
ms.custom: seodec18
ms.date: 06/25/2019
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: c21132a6622ce697fe3c52a461a33f548e0c8f31
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73036391"
---
# <a name="new-operator-c-reference"></a>new 运算符（C# 参考）

`new` 运算符创建类型的新实例。

`new` 关键字还可用作[成员声明修饰符](../keywords/new-modifier.md)或[泛型类型约束](../keywords/new-constraint.md)。

## <a name="constructor-invocation"></a>构造函数调用

要创建类型的新实例，通常使用 `new` 运算符调用该类型的某个[构造函数](../../programming-guide/classes-and-structs/constructors.md)：

[!code-csharp-interactive[invoke constructor](~/samples/csharp/language-reference/operators/NewOperator.cs#Constructor)]

可以使用带有 `new` 运算符的[对象或集合初始值设定项](../../programming-guide/classes-and-structs/object-and-collection-initializers.md)实例化和初始化一个语句中的对象，如下例所示：

[!code-csharp-interactive[constructor with initializer](~/samples/csharp/language-reference/operators/NewOperator.cs#ConstructorWithInitializer)]

## <a name="array-creation"></a>数组创建

还可以使用 `new` 运算符创建数组实例，如下例所示：

[!code-csharp-interactive[create array](~/samples/csharp/language-reference/operators/NewOperator.cs#Array)]

使用数组初始化语法创建数组实例，并在一个语句中使用元素填充该实例。 以下示例显示可以执行该操作的各种方法：

[!code-csharp-interactive[initialize array](~/samples/csharp/language-reference/operators/NewOperator.cs#ArrayInitialization)]

有关数组的详细信息，请参阅[数组](../../programming-guide/arrays/index.md)。

## <a name="instantiation-of-anonymous-types"></a>匿名类型的实例化

要创建[匿名类型](../../programming-guide/classes-and-structs/anonymous-types.md)的实例，请使用 `new` 运算符和对象初始值设定项语法：

[!code-csharp-interactive[anonymous type](~/samples/csharp/language-reference/operators/NewOperator.cs#AnonymousType)]

## <a name="destruction-of-type-instances"></a>类型实例的析构

无需销毁此前创建的类型实例。 引用和值类型的实例将自动销毁。 包含值类型的上下文销毁后，值类型的实例随之销毁。 在引用类型的最后一次引用被删除后，[垃圾回收器](../../../standard/garbage-collection/index.md)会在非指定的时间销毁其实例。

对于包含非托管资源的类型实例（例如，文件句柄），建议采用确定性的清理来确保尽快释放其包含的资源。 有关详细信息，请参阅 <xref:System.IDisposable?displayProperty=nameWithType> API 参考和 [using 语句](../keywords/using-statement.md)一文。

## <a name="operator-overloadability"></a>运算符可重载性

用户定义的类型不能重载 `new` 运算符。

## <a name="c-language-specification"></a>C# 语言规范

有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的 [new 运算符](~/_csharplang/spec/expressions.md#the-new-operator)部分。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 运算符](index.md)
- [对象和集合初始值设定项](../../programming-guide/classes-and-structs/object-and-collection-initializers.md)
