---
title: Quite las referencias a los procedimientos almacenados del sistema desaprobados | Documentos de Microsoft
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- undocumented system stored procedures [SQL Server]
- system stored procedures [SQL Server]
ms.assetid: 487d24fc-41d5-495e-843c-0ac974ec472f
caps.latest.revision: 20
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 45f10d9ab7697e84017da43d8767e52be23101bc
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36200291"
---
# <a name="remove-references-to-deprecated-system-stored-procedures"></a>Quitar referencias a procedimientos almacenados del sistema desusados
  El Asesor de actualizaciones ha detectado instrucciones que hacen referencia a procedimientos almacenados del sistema y a procedimientos almacenados extendidos no documentados que ya no están disponibles en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Las instrucciones que hagan referencia a dichos objetos producirán un error. No utilice objetos de sistema o API no documentados, ya que en futuras versiones podría cambiar o quitarse esta funcionalidad sin previo aviso.  
  
## <a name="component"></a>Componente  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a>Descripción  
  
### <a name="documented-system-stored-procedures"></a>Procedimientos almacenados del sistema documentados  
 Se han quitado los siguientes procedimientos almacenados del sistema documentados:  
  
-   sp_addalias  
  
-   sp_addgroup  
  
-   sp_changegroup  
  
-   sp_dropgroup  
  
-   sp_helpgroup  
  
### <a name="undocumented-system-stored-procedures"></a>Procedimientos almacenados del sistema no documentados  
 Se han quitado los siguientes procedimientos almacenados del sistema y procedimientos almacenados extendidos no documentados:  
  
-   sp_articlesynctranprocs  
  
-   sp_diskdefault  
  
-   sp_EventLog  
  
-   sp_GetMBCSCharLen  
  
-   sp_helplog  
  
-   sp_helpsql  
  
-   sp_IsMBCSLeadByte  
  
-   sp_lock2  
  
-   sp_MSget_current_activity  
  
-   sp_MSset_current_activity  
  
-   sp_MSobjessearch  
  
-   xp_enum_ActiveScriptEngines  
  
-   xp_eventlog  
  
-   xp_GetAdminGroupName  
  
-   xp_GetFileDetails  
  
-   xp_GetLocalSystemAccountName  
  
-   xp_IsNTAdmin  
  
-   xp_MSLocalSystem  
  
-   xp_MSnt2000  
  
-   xp_MSplatform  
  
-   xp_SetSecurity  
  
-   xp_varbintohexstr  
  
## <a name="corrective-action"></a>Acción correctora  
  
### <a name="documented-system-stored-procedures"></a>Procedimientos almacenados del sistema documentados  
 Modifique las aplicaciones según la tabla siguiente.  
  
|En lugar de|Haga esto|  
|----------------|-------------|  
|sp_addalias|Reemplace los alias por una combinación de cuentas de usuario y roles de la base de datos. Para obtener más información, vea "CREATE USER (Transact-SQL)" y "CREATE ROLE (Transact-SQL)" en los Libros en pantalla de SQL Server. Quite los alias de las bases de datos actualizadas usando sp_dropalias.|  
|sp_addgroupsp_changegroup<br /><br /> sp_dropgroup<br /><br /> sp_helpgroup|Utilice roles. Para obtener más información, vea "Roles de nivel de servidor" y "Roles de nivel de base de datos" en los Libros en pantalla de SQL Server.|  
  
### <a name="undocmented-system-stored-procedures"></a>Procedimientos almacenados del sistema de Undocmented  
 Puede crear procedimientos almacenados de CLR con una funcionalidad equivalente para reemplazar a los procedimientos almacenados del sistema no documentados. Para obtener más información, consulte el tema "Procedimientos almacenados del CLR" en los Libros en pantalla de SQL Server.  
  
## <a name="see-also"></a>Vea también  
 [Problemas de actualización de motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md)   
 [Asesor de actualizaciones de SQL Server 2014 &#91;nuevo&#93;](/sql/2014/sql-server/install/sql-server-2014-upgrade-advisor)  
  
  