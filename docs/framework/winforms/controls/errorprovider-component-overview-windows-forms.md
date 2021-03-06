---
title: ErrorProvider 组件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
ms.openlocfilehash: 3cfd3f306d4a18ce8a194b5197060fbca1d157d9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965288"
---
# <a name="errorprovider-component-overview-windows-forms"></a>ErrorProvider 组件概述（Windows 窗体）
Windows 窗体[ErrorProvider](errorprovider-component-windows-forms.md)组件用于验证窗体或控件上的用户输入。 它通常与验证窗体上的用户输入, 或在数据集内显示错误一起使用。 错误提供程序是一种比在消息框中显示错误消息的更好的替代方法, 因为一旦关闭消息框, 错误消息就不再可见。 组件<xref:System.Windows.Forms.ErrorProvider>在相关控件的旁边显示![错误图标 (红色圆圈内的一个白色](./media/errorprovider-component-overview-windows-forms/vb-error-provider-icon.gif)感叹号)。在用户将鼠标指针放置在错误图标上时, 将显示一个工具提示,显示错误消息字符串。  
  
## <a name="key-properties"></a>键属性  
 组件的键属性为<xref:System.Windows.Forms.ErrorProvider.DataSource%2A>、 <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>和<xref:System.Windows.Forms.ErrorProvider.Icon%2A>。 <xref:System.Windows.Forms.ErrorProvider> 将组件<xref:System.Windows.Forms.ErrorProvider>与数据绑定控件一起使用时<xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> , 必须将属性设置为适当的容器 (通常为 Windows 窗体), 以便组件在窗体上显示错误图标。 将组件添加到设计器中时, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>属性将设置为包含窗体; 如果您在代码中添加控件, 则必须自行设置。  
  
 <xref:System.Windows.Forms.ErrorProvider.Icon%2A>属性可以设置为自定义错误图标而不是默认值。 设置属性时<xref:System.Windows.Forms.ErrorProvider> , 组件可以显示数据集的错误消息。 <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> <xref:System.Windows.Forms.ErrorProvider>组件的关键方法<xref:System.Windows.Forms.ErrorProvider.SetError%2A>是方法, 它指定错误消息字符串和应显示错误图标的位置。  
  
> [!NOTE]
> <xref:System.Windows.Forms.ErrorProvider>组件不为辅助功能客户端提供内置支持。 若要使应用程序在使用此组件时可访问, 你必须提供其他可访问的反馈机制。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.ErrorProvider>
- [如何：使用 Windows 窗体 ErrorProvider 组件查看数据集中的错误](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
- [如何：显示用于通过 Windows 窗体 ErrorProvider 组件进行的窗体验证的错误图标](display-error-icons-for-form-validation-with-wf-errorprovider.md)
