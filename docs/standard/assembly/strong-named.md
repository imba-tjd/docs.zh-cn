---
title: 具有强名称的程序集
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, about strong-named assemblies
- assemblies [.NET Framework], strong-named
ms.assetid: d4a80263-f3e0-4d81-9b61-f0cbeae3797b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 67beeba6ce33fb1a8c3d02337d98282ccf30341a
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991291"
---
# <a name="strong-named-assemblies"></a>具有强名称的程序集

强命名一个程序集可为程序集创建唯一的标识，并且可以防止程序集冲突。

## <a name="what-makes-a-strong-named-assembly"></a>如何创建强名称程序集？

强名称程序集通过使用私钥以及程序集本身生成，此私钥对应于与该程序集一起分发的公钥。 程序集包括程序集清单，此清单包含所有组成该程序集的文件的名称和哈希。 具有相同强名称的程序集应该完全相同。

你可以使用 Visual Studio 或命令行工具强命名程序集。 有关详细信息，请参阅[如何：使用强名称](sign-strong-name.md)或 [Sn.exe（强名称工具）](../../framework/tools/sn-exe-strong-name-tool.md)为程序集签名。

在创建强名称程序集时，它包含程序集的简单文本名称、版本号、可选区域性信息、数字签名，以及对应于用于签名的私钥的公钥。

> [!WARNING]
> 不要依赖于通过强名称实现安全性。 它们仅提供唯一的标识。

## <a name="why-strong-name-your-assemblies"></a>为何强命名程序集？

在引用具有强名称的程序集时，你应该可以从中获得某些益处，例如版本控制和命名保护。 在 .NET Framework 中，强名称程序集可安装在需要启用一些方案的全局程序集缓存中。

强名称程序集在以下方案中有用：

- 你希望启用强名称程序集将引用的程序集，或希望允许其他强名称程序集 `friend` 访问你的程序集。

- 应用程序需要访问同一程序集的各种版本。 这意味着你需要在同一应用程序域中并排加载某程序集的不同版本，且各版本互不冲突。 例如，如果在具有相同简单名称的程序集中存在 API 的不同扩展，强命名将为该程序集的每个版本提供唯一标识。

- 你不希望程序集的使用对应用程序性能产生负面影响，所以你想要非特定于域的程序集。 这就要求进行强命名，因为非特定于域的程序集必须安装在全局程序集缓存中。

- 建议通过应用发布服务器策略来集中应用程序的服务，这意味着程序集必须安装在全局程序集缓存中。

如果你是开放源代码开发人员且希望利用强命名程序集的标识优势，不妨签入与源代码管理系统内程序集相关联的私钥。

## <a name="see-also"></a>请参阅

- [全局程序集缓存](../../framework/app-domains/gac.md)
- [如何：使用强名称为程序集签名](sign-strong-name.md)
- [Sn.exe（强名称工具）](../../framework/tools/sn-exe-strong-name-tool.md)
- [创建和使用具有强名称的程序集](create-use-strong-named.md)
