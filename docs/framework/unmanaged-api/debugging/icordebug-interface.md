---
title: ICorDebug 接口
ms.date: 03/30/2017
api_name:
- ICorDebug
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug
helpviewer_keywords:
- ICorDebug interface [.NET Framework debugging]
ms.assetid: 33f431d7-ab1a-494d-8af2-20ab15aba194
topic_type:
- apiref
ms.openlocfilehash: ee6bcbc9f3377735ed289d52afddb6efa755b16d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134073"
---
# <a name="icordebug-interface"></a>ICorDebug 接口
提供允许开发人员在公共语言运行时（CLR）环境中调试应用程序的方法。  
  
> [!NOTE]
> Windows 95、Windows 98 或 Windows ME 或非 x86 平台（如 IA64 和 AMD64）不支持混合模式（托管和本机代码）调试。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CanLaunchOrAttach 方法](../../../../docs/framework/unmanaged-api/debugging/icordebug-canlaunchorattach-method.md)|确定是否可以在当前计算机和运行时配置的上下文中启动新进程或附加到给定进程。|  
|[CreateProcess 方法](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)|在调试器的控制下启动进程及其主线程。|  
|[DebugActiveProcess 方法](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)|将调试器附加到现有进程。|  
|[EnumerateProcesses 方法](../../../../docs/framework/unmanaged-api/debugging/icordebug-enumerateprocesses-method.md)|获取正在调试的进程的枚举器。|  
|[GetProcess 方法](../../../../docs/framework/unmanaged-api/debugging/icordebug-getprocess-method.md)|返回具有给定进程 ID 的 "ICorDebugProcess" 对象。|  
|[Initialize 方法](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)|初始化 `ICorDebug` 对象。|  
|[SetManagedHandler 方法](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)|指定托管事件的事件处理程序对象。|  
|[SetUnmanagedHandler 方法](../../../../docs/framework/unmanaged-api/debugging/icordebug-setunmanagedhandler-method.md)|指定非托管事件的事件处理程序对象。|  
|[Terminate 方法](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)|终止 `ICorDebug` 的对象。|  
  
## <a name="remarks"></a>备注  
 `ICorDebug` 表示调试器进程的事件处理循环。 调试程序必须等待所有正在调试的进程中的[ICorDebugManagedCallback：： ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)回调，然后释放此接口。  
  
 `ICorDebug` 对象是用于控制所有进一步托管调试的初始对象。 在 .NET Framework 版本1.0 和1.1 中，此对象是从 COM 创建的 `CoClass` 对象。 在 .NET Framework 版本2.0 中，此对象不再是 `CoClass` 对象。 它必须通过[CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)函数创建，该函数更易于识别。 此新创建函数使客户端可以获取 `ICorDebug`的特定实现，这也会模拟调试 API 的特定版本。  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
