---
title: IMetaDataTables 接口
ms.date: 03/30/2017
api_name:
- IMetaDataTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables
helpviewer_keywords:
- IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 31272cce-506a-4f18-bcbf-01ee45e36356
topic_type:
- apiref
ms.openlocfilehash: 17305f2c088dd6f479da4c823d3db0fd50c0b3d7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443217"
---
# <a name="imetadatatables-interface"></a>IMetaDataTables 接口
提供存储和检索表中元数据信息的方法。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[GetBlob 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|获取一个指针，该指针指向指定列索引处的二进制大型对象（BLOB）。|  
|[GetBlobHeapSize 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|获取 BLOB 堆的大小（以字节为单位）。|  
|[GetCodedTokenInfo 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|获取一个指针，该指针指向与指定的行索引相关联的标记的数组。|  
|[GetColumn 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|获取一个指针，该指针指向指定表索引处的表中指定列索引处的列中包含的值。|  
|[GetColumnInfo 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|获取有关指定表中指定列的数据。|  
|[GetGuid 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|获取指定索引处的行的 GUID。|  
|[GetGuidHeapSize 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|获取 GUID 堆的大小（以字节为单位）。|  
|[GetNextBlob 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|获取表中下一个 BLOB 的索引。|  
|[GetNextGuid 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|获取当前表列中的下一个 GUID 值的索引。|  
|[GetNextString 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|获取当前表列中的下一个字符串的索引。|  
|[GetNextUserString 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|获取包含当前表列中的下一个硬编码字符串的行的索引。|  
|[GetNumTables 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|获取当前 `IMetaDataTables` 实例的范围中的表数。|  
|[GetRow 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|获取位于指定表索引处的表中指定行索引处的行。|  
|[GetString 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|从当前引用范围内的表列中获取指定索引处的字符串。|  
|[GetStringHeapSize 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|获取字符串堆的大小（以字节为单位）。|  
|[GetTableIndex 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|获取指定的标记所引用的表的索引。|  
|[GetTableInfo 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|获取指定表索引处的表的名称、行大小、行数、列数和键列索引。|  
|[GetUserString 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|获取当前范围内字符串列中指定索引处的硬编码字符串。|  
|[GetUserStringHeapSize 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|获取用户字符串堆的大小（以字节为单位）。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataTables2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
