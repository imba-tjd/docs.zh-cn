---
title: DynamicResource 标记扩展
ms.date: 03/30/2017
f1_keywords:
- DynamicResource
- DynamicResourceExtension
helpviewer_keywords:
- XAML [WPF], DynamicResource markup extension
- DynamicResource markup extensions [WPF]
ms.assetid: 7324f243-03af-4c2b-b0db-26ac6cdfcbe4
ms.openlocfilehash: a04e1569f77fed73a480fda3d63cabf6dbc30664
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460519"
---
# <a name="dynamicresource-markup-extension"></a>DynamicResource 标记扩展
通过将值推迟为对已定义资源的引用来为任何 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 属性特性提供一个值。 该资源的查找行为类似于运行时查找。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xml  
<object property="{DynamicResource key}" .../>  
```  
  
## <a name="xaml-property-element-usage"></a>XAML 属性元素用法  
  
```xml  
<object>  
  <object.property>  
    <DynamicResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`key`|所请求资源的密钥。 如果在标记中创建了资源，则此密钥最初由[X：Key 指令](../../xaml-services/x-key-directive.md)分配，或在调用 <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> 时作为 `key` 参数提供（如果资源是在代码中创建的）。|  
  
## <a name="remarks"></a>备注  
 `DynamicResource` 将在初始编译期间创建一个临时表达式，因而延迟对资源的查找，直到实际需要请求的资源值才能构造对象。 这可能在加载 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页面之后。 将基于从当前页范围开始的所有活动资源字典的键搜索来找到资源值，并将其替换为编译中的占位符表达式。  
  
> [!IMPORTANT]
> 就依赖属性优先级而言，`DynamicResource` 表达式等效于应用动态资源引用的位置。 如果为先前具有 `DynamicResource` 表达式作为本地值的属性设置本地值，则 `DynamicResource` 将被完全删除。 有关详细信息，请参阅[依赖属性值优先级](dependency-property-value-precedence.md)。  
  
 某些资源访问方案特别适用于 `DynamicResource` 而不是[StaticResource 标记扩展](staticresource-markup-extension.md)。 请参阅[XAML 资源](xaml-resources.md)，以了解有关 `DynamicResource` 和 `StaticResource`相对的优点和性能影响的讨论。  
  
 指定的 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 应对应于在页面、应用程序、可用控件主题和外部资源或系统资源的某个级别由[X：Key 指令](../../xaml-services/x-key-directive.md)确定的现有资源，以及资源查找将在顺序。 有关静态和动态资源的资源查找的详细信息，请参阅[XAML 资源](xaml-resources.md)。  
  
 资源键可以是[XamlName 语法](../../xaml-services/xamlname-grammar.md)中定义的任何字符串。 资源键还可以是其他对象类型，如 <xref:System.Type>。 <xref:System.Type> 的关键是主题如何对控件进行样式设计的基础。 有关详细信息，请参阅[控件创作概述](../controls/control-authoring-overview.md)。  
  
 用于查找资源值的 Api （如 <xref:System.Windows.FrameworkElement.FindResource%2A>）遵循 `DynamicResource`所使用的相同资源查找逻辑。  
  
 引用资源的替代声明方法是作为[StaticResource 标记扩展](staticresource-markup-extension.md)。  
  
 特性语法是最常用于该标记扩展的语法。 在 `DynamicResource` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 扩展类的 <xref:System.Windows.DynamicResourceExtension> 值。  
  
 `DynamicResource` 可以在对象元素语法中使用。 在这种情况下，需要指定 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 属性的值。  
  
 `DynamicResource` 还可以在详细特性用法中使用，以便将 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 属性指定为一个 property=value 对：  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 如果扩展具有一个以上的可设置属性，或者某些属性是可选的，则详细用法通常会很有用。 由于 `DynamicResource` 仅有一个可设置的属性，并且此属性是必需的，因此该详细用法不具有典型性。  
  
 在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器实现中，对此标记扩展的处理由 <xref:System.Windows.DynamicResourceExtension> 类定义。  
  
 `DynamicResource` 是标记扩展。 当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的所有标记扩展在其特性语法中都使用 { 和 } 字符，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器通过这一约定确认标记扩展必须处理该特性。 有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。  
  
## <a name="see-also"></a>请参阅

- [XAML 资源](xaml-resources.md)
- [资源和代码](resources-and-code.md)
- [x:Key 指令](../../xaml-services/x-key-directive.md)
- [XAML 概述 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)
- [StaticResource 标记扩展](staticresource-markup-extension.md)
- [标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)
