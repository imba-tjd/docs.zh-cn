---
title: My.Forms 和 My.WebServices 提供的默认对象实例
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: d06df4bd023892429b2aaefdd624398a6546d06d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330205"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a>My.Forms 和 My.WebServices 提供的默认对象实例 (Visual Basic)

[My. forms](../../../visual-basic/language-reference/objects/my-forms-object.md)和[WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)对象提供对应用程序使用的窗体、数据源和 XML Web services 的访问权限。 它们通过提供每个对象的*默认实例*集合来实现此目的。  
  
## <a name="default-instances"></a>默认实例  

 默认实例是由运行时提供的类的实例，无需使用 `Dim` 和 `New` 语句进行声明和实例化。 下面的示例演示如何声明和实例化名为 `Form1`<xref:System.Windows.Forms.Form> 类的实例，以及你现在如何通过 `My.Forms`获取此 <xref:System.Windows.Forms.Form> 类的默认实例。  
  
 [!code-vb[VbVbcnMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#5)]  
  
 [!code-vb[VbVbcnMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#6)]  
  
 `My.Forms` 对象将为项目中存在的每个 `Form` 类返回默认实例的集合。 同样，`My.WebServices` 为已在应用程序中创建引用的每个 Web 服务提供代理类的默认实例。  
  
## <a name="see-also"></a>另请参阅

- [My.Forms 对象](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [My.WebServices 对象](../../../visual-basic/language-reference/objects/my-webservices-object.md)
- [My 对项目类型的依赖方式](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
