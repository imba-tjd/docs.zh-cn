---
title: 如何：转换元素
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: 9c1b873a89820e85efb99789f483c4832fb23cf7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051437"
---
# <a name="how-to-translate-an-element"></a>如何：转换元素
以下示例显示如何平移 （移动） 元素来使用<xref:System.Windows.Media.TranslateTransform>。  
  
 <xref:System.Windows.Media.TranslateTransform>类是对于不支持绝对定位的面板内移动元素特别有用。 例如，通过应用<xref:System.Windows.Media.TranslateTransform>到<xref:System.Windows.UIElement.RenderTransform%2A>元素的属性，可以移动中的某个元素<xref:System.Windows.Controls.StackPanel>或<xref:System.Windows.Controls.DockPanel>。  
  
 使用<xref:System.Windows.Media.TranslateTransform.X%2A>属性的<xref:System.Windows.Media.TranslateTransform>指定量，以像素为单位，若要沿 x 轴移动元素。 使用<xref:System.Windows.Media.TranslateTransform.Y%2A>属性来指定量，以像素为单位，若要沿 y 轴移动元素。 最后，将应用<xref:System.Windows.Media.TranslateTransform>到<xref:System.Windows.UIElement.RenderTransform%2A>元素的属性。  
  
 下面的示例使用<xref:System.Windows.Media.TranslateTransform>可以向下移动到右和 50 个像素的元素 50 像素。  
  
## <a name="example"></a>示例  
 [!code-xaml[transformsSample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 有关完整示例，请参阅 [2D 转换示例](https://go.microsoft.com/fwlink/?LinkID=158252)。  
  
## <a name="see-also"></a>请参阅

- [转换概述](transforms-overview.md)
