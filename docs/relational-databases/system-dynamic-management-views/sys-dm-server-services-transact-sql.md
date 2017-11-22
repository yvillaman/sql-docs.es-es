---
title: Sys.dm_server_services (Transact-SQL) | Documentos de Microsoft
ms.custom: 
ms.date: 03/28/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- dm_server_services
- sys.dm_server_services
- sys.dm_server_services_TSQL
- dm_server_services_TSQL
dev_langs: TSQL
helpviewer_keywords: sys.dm_server_services dynamic management view
ms.assetid: 3f0defd0-478d-4e7f-96be-8795c9de4e3f
caps.latest.revision: "9"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: 8642cd9036fcaf7835c6dffc01f60817bdaa82bb
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmserverservices-transact-sql"></a>sys.dm_server_services (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Devuelve información sobre los servicios SQL Server, Texto completo y Agente SQL Server en la instancia actual de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Use esta vista de administración dinámica para notificar información de estado sobre estos servicios.  
  
 
|Nombre de columna|Tipo de datos|Description|  
|-----------------|---------------|-----------------|  
|servicename|**nvarchar(256)**|Nombre del servicio SQL Server, Texto completo o Agente SQL Server. No puede ser null.|  
|startup_type|**int**|Indica el modo de inicio del servicio. Éstos son los valores posibles y sus correspondientes descripciones.<br /><br /> 0: otros<br />1: otros<br />2: automática<br />3: manual<br />4: deshabilitado<br /><br /> Acepta valores NULL.|  
|startup_desc|**nvarchar(256)**|Describe el modo de inicio del servicio. Éstos son los valores posibles y sus correspondientes descripciones.<br /><br /> Otro: Otro (inicio del arranque)<br />Otro: Otro (inicio del sistema)<br />Automático: Inicio automático<br />Manual: Inicio por demanda<br />Deshabilitado: deshabilitado<br /><br /> No puede ser null.|  
|status|**int**|Indica el estado actual del servicio. Éstos son los valores posibles y sus correspondientes descripciones.<br /><br /> 1: detenido<br />2: otro (Inicio pendiente)<br />3: otro (detención pendiente)<br />4: ejecutar<br />5: otro (continuación pendiente)<br />6: otro (pausa pendiente)<br />7: en pausa<br /><br /> Acepta valores NULL.|  
|status_desc|**nvarchar(256)**|Describe el estado actual del servicio. Éstos son los valores posibles y sus correspondientes descripciones.<br /><br /> Detener: El servicio está detenido.<br />Otro (operación de inicio pendiente): el servicio se está iniciando.<br />Otro (operación de detención pendiente): el servicio está deteniéndose.<br />En ejecución: Se está ejecutando el servicio.<br />Otro (operaciones de continuación pendientes): el servicio está en un estado pendiente.<br />Otro (pausa pendiente): el servicio no está en el proceso de poner en pausa.<br />En pausa: El servicio está pausado.<br /><br /> No puede ser null.|  
|process_id|**int**|Identificador de proceso del servicio. No puede ser null.|  
|last_startup_time|**DateTimeOffset(7)**|Fecha y hora en que el servicio se inició por última vez. Acepta valores NULL.|  
|service_account|**nvarchar(256)**|Cuenta autorizada para controlar el servicio. Esta cuenta puede iniciar o detener el servicio, o puede modificar las propiedades del servicio. No puede ser null.|  
|filename|**nvarchar(256)**|Ruta de acceso y nombre del archivo ejecutable del servicio. No puede ser null.|  
|is_clustered|**nvarchar(1)**|Indica si el servicio está instalado como un recurso de un servidor en clúster. No puede ser null.|  
|cluster_nodename|**nvarchar(256)**|Nombre del nodo de clúster en el que está instalado el servicio. Acepta valores NULL.|
|instant_file_initialization_enabled|**nvarchar(1)**|**Se aplica a: [!INCLUDE[sssql11](../../includes/sssql11-md.md)] SP4 a partir [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] SP1**.<br /><br />Especifica si la inicialización instantánea de archivos está habilitada para el servicio de motor de base de datos de SQL Server. Esta propiedad no se aplica a los servicios (ejemplo: el Agente SQL Server) que no sea el servicio de motor de base de datos de SQL Server. acepta valores NULL.<br /><br />Y = inicialización instantánea de archivos está habilitada para el servicio.<br /><br />N = se deshabilita la inicialización instantánea de archivos para el servicio.|  
  
## <a name="security"></a>Seguridad  
  
### <a name="permissions"></a>Permissions  
 Requiere el permiso `VIEW SERVER STATE` en el servidor.  
  
## <a name="see-also"></a>Vea también  
 [Sys.dm_server_registry &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-server-registry-transact-sql.md)  
  
  