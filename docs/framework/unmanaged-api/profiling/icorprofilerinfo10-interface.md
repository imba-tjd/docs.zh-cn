---
title: ICorProfilerInfo10 接口
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: f2bc716110c14972e5b2c32bceb3123b16e87c61
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449840"
---
# <a name="icorprofilerinfo10-interface"></a>ICorProfilerInfo10 接口

[ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)的子类，提供用于修改函数 IL、从运行时查询信息以及挂起和恢复运行时的方法。

## <a name="methods"></a>方法  

| 方法|说明|  
| ------------|-----------------|  
|[EnumerateObjectReferences 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-enumerateobjectreferences-method.md)|给定 ObjectID、callback 和 clientData，枚举每个对象引用（如果有）。 |
|[IsFrozenObject 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-isfrozenobject-method.md)|给定 ObjectID，确定对象是否位于只读段。 |
|[GetLOHObjectSizeThreshold 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-getlohobjectsizethreshold-method.md)|获取配置的 LOH 阈值的值。 |
|[RequestReJITWithInliners 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md)| ReJITs 请求的方法，以及所请求的方法的任何 inliners。  |
|[SuspendRuntime 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-suspendruntime-method.md)| 挂起运行时，而不执行 GC。 |
|[ResumeRuntime 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-resumeruntime-method.md)| 恢复运行时，而不执行 GC。 |

## <a name="requirements"></a>要求  
**平台：** 请参阅[支持 .Net Core 的操作系统](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)。  
**头文件：** CorProf.idl、CorProf.h  
**.Net 版本：** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)] 

## <a name="see-also"></a>另请参阅

- [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
