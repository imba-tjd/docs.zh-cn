---
title: 连接到 ADO.NET 中的数据源
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 01e4048fb9c7b53b1b1907d1965f822b9a4644a4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786762"
---
# <a name="connecting-to-a-data-source-in-adonet"></a>连接到 ADO.NET 中的数据源
在 ADO.NET 中，可以通过在连接字符串中提供必要的身份验证信息来使用**连接**对象连接到特定数据源。 使用的**连接**对象取决于数据源的类型。  
  
 随 .NET Framework 提供的每个 .NET Framework 数据提供程序都具有一个 <xref:System.Data.Common.DbConnection> 对象：适用于 OLE DB 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.OleDb.OleDbConnection> 对象，适用于 SQL Server 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.SqlClient.SqlConnection> 对象，适用于 ODBC 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.Odbc.OdbcConnection> 对象，适用于 Oracle 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.OracleClient.OracleConnection> 对象。  
  
## <a name="in-this-section"></a>本节内容  
 [建立连接](establishing-the-connection.md)  
 介绍如何使用**连接**对象建立与数据源的连接。  
  
 [连接事件](connection-events.md)  
 介绍如何使用**InfoMessage**事件从数据源中检索信息性消息。  
  
## <a name="see-also"></a>请参阅

- [连接字符串](connection-strings.md)
- [连接池](connection-pooling.md)
- [命令和参数](commands-and-parameters.md)
- [DataAdapters 和 DataReaders](dataadapters-and-datareaders.md)
- [事务和并发性](transactions-and-concurrency.md)
- [ADO.NET 概述](ado-net-overview.md)
