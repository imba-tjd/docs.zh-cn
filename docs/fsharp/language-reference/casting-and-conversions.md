---
title: 强制转换和转换
description: 了解F#编程语言如何提供各种基元类型之间算术转换的转换运算符。
ms.date: 05/16/2016
ms.openlocfilehash: ee4df588caabf58c7b9e18961e217ef8f15fcf93
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630434"
---
# <a name="casting-and-conversions-f"></a>强制转换和转换 (F#)

本主题介绍中F#对类型转换的支持。

## <a name="arithmetic-types"></a>算术类型

F#提供各种基元类型 (如整型和浮点类型之间) 的算术转换的转换运算符。 整数和字符转换运算符具有 checked 和 unchecked 形式;浮点运算符和`enum`转换运算符不能。 中`Microsoft.FSharp.Core.Operators`定义了未检查的窗体, 并在中`Microsoft.FSharp.Core.Operators.Checked`定义了选中的窗体。 如果生成的值超出了目标类型的限制, 则选中的窗体将检查溢出并生成运行时异常。

其中每个运算符都具有与目标类型名称相同的名称。 例如, 在下面的代码中, 这些类型已显式批注, `byte`以两种不同的含义显示。 第一次出现类型, 第二个是转换运算符。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

下表显示了在中定义的F#转换运算符。

|运算符|描述|
|--------|-----------|
|`byte`|转换为字节, 即8位无符号类型。|
|`sbyte`|转换为有符号字节。|
|`int16`|转换为16位带符号整数。|
|`uint16`|转换为16位无符号整数。|
|`int32, int`|转换为32位有符号整数。|
|`uint32`|转换为32位无符号整数。|
|`int64`|转换为64位有符号整数。|
|`uint64`|转换为64位无符号整数。|
|`nativeint`|转换为本机整数。|
|`unativeint`|转换为无符号本机整数。|
|`float, double`|转换为64位双精度 IEEE 浮点数。|
|`float32, single`|转换为32位单精度 IEEE 浮点数。|
|`decimal`|转换为`System.Decimal`。|
|`char`|将转换`System.Char`为 Unicode 字符。|
|`enum`|转换为枚举类型。|

除了内置基元类型外, 还可以将这些运算符用于实现`op_Explicit`的类型或`op_Implicit`使用适当签名的方法。 例如, `int`转换运算符适用于任何类型, 该类型提供将类型作为`op_Explicit`参数并返回`int`的静态方法。 作为一般规则, 不能通过返回类型重载方法, 可以对`op_Explicit`和`op_Implicit`执行此操作。

## <a name="enumerated-types"></a>枚举类型

运算符是一个泛型运算符, 它采用一个类型参数来表示要转换为的`enum`类型。 `enum` 当它转换为枚举类型时, 类型推理将尝试确定要转换为的`enum`类型。 在下面的示例中, 变量`col1`未显式批注, 但其类型是从后面的相等测试推断出来的。 因此, 编译器可以推断出要转换为`Color`枚举。 另外, 还可以提供类型批注, 如下面的`col2`示例中所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]

你还可以将目标枚举类型显式指定为类型参数, 如以下代码所示:

```fsharp
let col3 = enum<Color> 3
```

请注意, 仅当枚举的基础类型与正在转换的类型兼容时, 才会转换枚举。 在下面的代码中, 由于和`int32` `uint32`之间的不匹配, 转换无法编译。

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

有关详细信息, 请参阅[枚举](enumerations.md)。

## <a name="casting-object-types"></a>强制转换对象类型

对象层次结构中的类型之间的转换是面向对象编程的基础。 有两种基本类型的转换: 强制转换 (向上转换) 和强制转换 (downcasting)。 向上转换层次结构意味着将派生对象引用强制转换为基对象引用。 只要基类位于派生类的继承层次结构中, 此类强制转换就可以正常工作。 将层次结构向下强制转换为派生对象引用后, 仅当对象实际上是正确目标 (派生) 类型或派生自目标类型的类型的实例时, 才会成功。

F#为这些类型的转换提供运算符。 运算符`:>`在层次结构中向上转换, `:?>`运算符沿层次结构向下转换。

### <a name="upcasting"></a>向上转换

在许多面向对象的语言中, 向上转换是隐式的;在F#中, 规则略有不同。 将参数传递给对象类型上的方法时, 会自动应用向上转换。 但是, 对于模块中的 let 绑定函数, 向上转换不是自动的, 除非将参数类型声明为可变类型。 有关详细信息, 请参阅[可变类型](flexible-Types.md)。

`:>`运算符执行静态强制转换, 这意味着在编译时确定强制转换是否成功。 如果成功使用`:>`编译的强制转换, 则它是有效的强制转换, 并且在运行时没有任何可能失败。

你还可以使用`upcast`运算符来执行此类转换。 以下表达式指定了层次结构中的转换:

```fsharp
upcast expression
```

当使用向上转换运算符时, 编译器将尝试推断从上下文转换为的类型。 如果编译器无法确定目标类型, 则编译器将报告错误。

### <a name="downcasting"></a>Downcasting

`:?>`运算符执行动态强制转换, 这意味着在运行时确定强制转换是否成功。 在编译时不检查`:?>`使用运算符的强制转换, 但在运行时, 尝试强制转换为指定的类型。 如果对象与目标类型兼容, 则强制转换成功。 如果对象与目标类型不兼容, 则运行时将引发`InvalidCastException`。

你还可以使用`downcast`运算符来执行动态类型转换。 以下表达式指定向下转换到从程序上下文推断出的类型的层次结构:

```fsharp
downcast expression
```

对于`upcast`运算符, 如果编译器无法从上下文推断特定目标类型, 则会报告错误。

下面的代码演示如何使用`:>`和`:?>`运算符。 此代码说明`:?>` , 当你知道转换将会成功时, 运算符最适用, 因为如果转换`InvalidCastException`失败, 则会引发。 如果您不知道转换将会成功, 则使用`match`表达式的类型测试将更好, 因为这样可以避免生成异常的开销。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

由于泛型运算符`downcast`和`upcast`依赖类型推理来确定参数和返回类型, 因此, 在上面的代码中, 可以替换

```fsharp
let base1 = d1 :> Base1
```

替换为

```fsharp
let base1 = upcast d1
```

在前面的代码中, 参数类型和返回类型分别`Derived1`为`Base1`和。

有关类型测试的详细信息, 请参阅[Match 表达式](match-Expressions.md)。

## <a name="see-also"></a>请参阅

- [F# 语言参考](index.md)
