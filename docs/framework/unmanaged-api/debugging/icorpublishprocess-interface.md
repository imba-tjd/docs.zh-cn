---
title: ICorPublishProcess 接口
ms.date: 03/30/2017
api_name:
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
ms.openlocfilehash: 04f6a088c5bbe96e3909ba600aa8ffab937abe2d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140398"
---
# <a name="icorpublishprocess-interface"></a>ICorPublishProcess 接口
提供用于访问要显示的有关进程的信息的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[EnumAppDomains 方法](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|获取一个[ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)实例，它包含此 `ICorPublishProcess`所引用的进程中的应用程序域。|  
|[GetDisplayName 方法](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|获取此 `ICorPublishProcess`所引用的进程的可执行文件的完整路径。|  
|[GetProcessID 方法](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|获取此 `ICorPublishProcess`所引用的进程的操作系统标识符。|  
|[IsManaged 方法](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|获取一个值，该值指示此 `ICorPublishProcess` 引用的进程是否已知正在运行托管代码。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorPub，CorPub  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [CorpubPublish 组件类](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
