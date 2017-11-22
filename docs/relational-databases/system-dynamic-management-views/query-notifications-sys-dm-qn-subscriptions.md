---
title: Sys.dm_qn_subscriptions (Transact-SQL) | Documentos de Microsoft
ms.custom: 
ms.date: 03/15/2017
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
- dm_qn_subscriptions
- dm_qn_subscriptions_TSQL
- sys.dm_qn_subscriptions
- sys.dm_qn_subscriptions_TSQL
dev_langs: TSQL
helpviewer_keywords: sys.dm_qn_subscriptions dynamic management view
ms.assetid: a3040ce6-f5af-48fc-8835-c418912f830c
caps.latest.revision: "26"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: bd318140e5c3eed17a5440ebf1a3135e7e01dc90
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2017
---
# <a name="query-notifications---sysdmqnsubscriptions"></a>Consultar las notificaciones - sys.dm_qn_subscriptions
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Devuelve información acerca de las suscripciones de notificaciones de consultas activas en el servidor. Puede usar esta vista para comprobar si hay suscripciones activas en el servidor o en una base de datos especificada, o para comprobar una entidad de seguridad de servidor especificada.  
  
|Nombre de columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**id**|**int**|Id. de una suscripción.|  
|**database_id**|**int**|Id. de la base de datos en la que se ha ejecutado la notificación. Esta base de datos almacena información relacionada con esta suscripción.|  
|**SID**|**varbinary (85)**|Id. de seguridad de la entidad de seguridad del servidor que creó y es propietaria de esta suscripción.|  
|**object_id**|**int**|Id. de la tabla interna que almacena información acerca de los parámetros de suscripción.|  
|**creado**|**datetime**|Fecha y hora en que se creó la suscripción.|  
|**tiempo de espera**|**int**|Tiempo de espera de la suscripción en segundos. La notificación se marcará para activarse después de transcurrido este tiempo.<br /><br /> Nota: El tiempo de activación real puede ser mayor que el tiempo de espera especificado. No obstante, si tiene lugar un cambio que invalida la suscripción después el tiempo de espera especificado, pero antes de que se active la suscripción, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] garantiza que la activación tiene lugar en el momento en que se realiza el cambio.|  
|**status**|**int**|Indica el estado de la suscripción. Vea la tabla bajo las notas para obtener la lista de códigos.|  
  
## <a name="relationship-cardinalities"></a>Cardinalidades de relación  
  
|De|Para|Activado|Tipo|  
|----------|--------|--------|----------|  
|**sys.dm_qn_subscriptions**|**sys.databases**|**database_id**|Varios a uno|  
|**sys.dm_qn_subscriptions**|**sys.internal_tables**|**object_id**|Varios a uno|  
  
## <a name="remarks"></a>Comentarios  
 El código de estado 0 indica un estado indefinido.  
  
 Los siguientes códigos de estado indican que una suscripción se desencadenó debido a un cambio:  
  
|código|Estado secundario|Información|  
|----------|------------------|----------|  
|65798|La suscripción se desencadenó porque los datos cambiaron|La suscripción se activó al realizar la inserción|  
|65799|La suscripción se desencadenó porque los datos cambiaron|DELETE|  
|65800|La suscripción se desencadenó porque los datos cambiaron|Update|  
|65801|La suscripción se desencadenó porque los datos cambiaron|Mezcla|  
|65802|La suscripción se desencadenó porque los datos cambiaron|Truncar tabla|  
|66048|La suscripción se desencadenó porque el tiempo de espera expiró|Modo de información indefinido|  
|66315|La suscripción se desencadenó porque el objeto cambió|Se quitó el objeto o el usuario|  
|66316|La suscripción se desencadenó porque el objeto cambió|Se modificó el objeto|  
|66565|La suscripción se desencadenó porque la base de datos se desasoció o se quitó|Se reinició el servidor o la base de datos|  
|66571|La suscripción se desencadenó porque la base de datos se desasoció o se quitó|Se quitó el objeto o el usuario|  
|66572|La suscripción se desencadenó porque la base de datos se desasoció o se quitó|Se modificó el objeto|  
|67341|La suscripción se desencadenó debido a la falta de recursos en el servidor|La suscripción se desencadenó debido a la falta de recursos en el servidor|  
  
 Los siguientes códigos de estado indican que una suscripción no pudo crearse:  
  
|código|Estado secundario|Información|  
|----------|------------------|----------|  
|132609|Se produjo un error en la creación de la suscripción porque no se admite la instrucción|La consulta es demasiado compleja|  
|132610|Se produjo un error en la creación de la suscripción porque no se admite la instrucción|Instrucción no válida para la suscripción|  
|132611|Se produjo un error en la creación de la suscripción porque no se admite la instrucción|Se establecieron opciones no válidas para la suscripción|  
|132612|Se produjo un error en la creación de la suscripción porque no se admite la instrucción|Nivel de aislamiento no válido|  
|132622|Se produjo un error en la creación de la suscripción porque no se admite la instrucción|Se utiliza internamente|  
|132623|Se produjo un error en la creación de la suscripción porque no se admite la instrucción|Por encima del límite de plantilla por tabla|  
  
 Los siguientes códigos de estado se utilizan internamente y se clasifican como modos de iniciación y de comprobación de eliminación:  
  
|código|Estado secundario|Información|  
|----------|------------------|----------|  
|198656|Se utiliza internamente: modos de iniciación y de comprobación de eliminación|Modo de información indefinido|  
|198928|La subscription se destruyó|La suscripción se desencadenó porque la base de datos se adjuntó|  
|198929|La subscription se destruyó|La suscripción se desencadenó porque se quitó el usuario|  
|198930|La subscription se destruyó|La suscripción se quitó debido a que se volvió a realizar la suscripción|  
|198931|La subscription se destruyó|Se eliminó la suscripción|  
|199168|La suscripción está activa|Modo de información indefinido|  
|199424|La suscripción se inicializó pero no aún no está activa|Modo de información indefinido|  
  
## <a name="permissions"></a>Permissions  
 Requiere el permiso VIEW SERVER STATE en el servidor.  
  
> [!NOTE]  
>  Si el usuario no tiene el permiso VIEW SERVER STATE, esta vista devuelve información acerca de suscripciones que son propiedad del usuario actual.  
  
## <a name="examples"></a>Ejemplos  
  
### <a name="a-return-active-query-notification-subscriptions-for-the-current-user"></a>A. Devolver las suscripciones de notificación de consultas activas del usuario actual  
 En el ejemplo siguiente se devuelven las suscripciones de notificación de consultas activas del usuario actual. Si el usuario tiene permisos VIEW SERVER STATE, se devuelven todas las suscripciones activas del servidor.  
  
```  
SELECT id, database_id, sid, object_id, created, timeout, status  
FROM sys.dm_qn_subscriptions;  
GO  
```  
  
### <a name="b-returning-active-query-notification-subscriptions-for-a-specified-user"></a>B. Devolver las suscripciones de notificación de consultas activas del usuario especificado  
 En el ejemplo siguiente se devuelven las suscripciones de notificación de consultas activas suscritas por el inicio de sesión `Ruth0`.  
  
```  
SELECT id, database_id, sid, object_id, created, timeout, status  
FROM sys.dm_qn_subscriptions  
WHERE sid = SUSER_SID('Ruth0');  
GO  
```  
  
### <a name="c-returning-internal-table-metadata-for-query-notification-subscriptions"></a>C. Devolver los metadatos de las tablas internas para las suscripciones de notificación de consultas  
 En el ejemplo siguiente se devuelven los metadatos de la tabla interna para las suscripciones de notificación de consultas.  
  
```  
SELECT qn.id AS query_subscription_id  
    ,it.name AS internal_table_name  
    ,it.object_id AS internal_table_id  
FROM sys.internal_tables AS it  
JOIN sys.dm_qn_subscriptions AS qn ON it.object_id = qn.object_id  
WHERE it.internal_type_desc = 'QUERY_NOTIFICATION';  
GO  
```  
  
## <a name="see-also"></a>Vea también  
 [Funciones y vistas de administración dinámica &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [Las notificaciones de consulta relacionadas con vistas de administración dinámica &#40; Transact-SQL &#41;](http://msdn.microsoft.com/library/92eb22d8-33f3-4c17-b32e-e23acdfbd8f4)   
 [Eliminar suscripción de notificación de consulta &#40; Transact-SQL &#41;](../../t-sql/language-elements/kill-query-notification-subscription-transact-sql.md)  
  
  