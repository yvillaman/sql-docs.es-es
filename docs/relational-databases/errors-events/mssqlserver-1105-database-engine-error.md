---
title: MSSQLSERVER_1105 | Microsoft Docs
ms.custom: 
ms.date: 04/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords:
- 1105 (Database Engine error)
ms.assetid: e7f4ad02-8c7f-4bb9-9781-2c86253f2138
caps.latest.revision: 19
author: BYHAM
ms.author: rickbyh
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 6351998ecebd4a63c6fff509cb535f6107247513
ms.lasthandoff: 04/11/2017

---
# <a name="mssqlserver1105"></a>MSSQLSERVER_1105
  
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|SQL Server|  
|Identificador del evento|1105|  
|Origen del evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nombre simbólico|NO_MORE_SPACE_IN_FG|  
|Texto del mensaje|No se pudo asignar espacio para el objeto '%.*ls'%.\*ls de la base de datos '%.\*ls' porque el grupo de archivos '%.\*ls' está lleno. Elimine archivos innecesarios, quite objetos del grupo de archivos, agregue archivos adicionales al grupo de archivos o establezca la opción de crecimiento automático para los archivos existentes en el grupo de archivos con el fin de crear espacio en el disco.|  
  
## <a name="explanation"></a>Explicación  
No hay espacio en disco disponible en un grupo de archivos.  
  
## <a name="user-action"></a>Acción del usuario  
Las siguientes acciones pueden crear espacio disponible en el grupo de archivos:  
  
-   Active el crecimiento automático.  
  
-   Agregue más archivos al grupo de archivos.  
  
-   Libere espacio en disco quitando índices o tablas que ya no sean necesarios.  
  
-   Para obtener más información, vea el tema "Solucionar problemas de espacio en disco insuficiente para datos" en los Libros en pantalla de SQL Server.  
  
> [!NOTE]  
> Cuando un índice se encuentra en varios archivos, **ALTER INDEX REORGANIZE** puede devolver el error 1105 si uno de los archivos está lleno. El proceso de reorganización se bloquea cuando el proceso trata de mover filas al archivo que está lleno. Para solucionar esta limitación, realice una operación **ALTER INDEX REBUILD** en lugar de **ALTER INDEX REORGANIZE** o incremente el límite de crecimiento de los archivos que estén llenos.  
  
