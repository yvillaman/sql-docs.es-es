---
title: Los archivos de base de datos de origen | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferdatabasetask.sourcedbfiles.f1
ms.assetid: 7dc6bfeb-37c1-45e8-a705-a87564922265
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 42ac066ede8be2af8f08106ed358e63821a92c54
ms.sourcegitcommit: 2429fbcdb751211313bd655a4825ffb33354bda3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "52533941"
---
# <a name="source-database-files"></a>Archivos de base de datos de origen
  Utilice el cuadro de diálogo **Archivos de base de datos de origen** para ver los nombres y las ubicaciones de los archivos de la base de datos en el servidor de origen o para especificar una ubicación del recurso compartido de archivos de red para la tarea Transferir bases de datos. Para más información sobre esta tarea, vea [Tarea Transferir bases de datos](control-flow/transfer-database-task.md).  
  
 Para llenar este cuadro de diálogo con los nombres y las ubicaciones de los archivos de la base de datos del servidor de origen, especifique **SourceConnection** y **SourceDatabaseName** primero en la página **Bases de datos** del cuadro de diálogo **Editor de la tarea Transferir bases de datos** .  
  
## <a name="options"></a>Opciones  
 **Archivo de origen**  
 Nombres de los archivos de la base de datos del servidor de origen que se van a transferir. El**Archivo de origen** es de solo lectura.  
  
 **Carpeta de origen**  
 Carpeta del servidor de origen en la que se encuentran los archivos de la base de datos que se van a transferir. La**Carpeta de origen** es de solo lectura.  
  
 **Recurso compartido de archivos de red**  
 Carpeta compartida de red del servidor de origen desde donde se transferirán los archivos de la base de datos. Utilice **Recurso compartido de archivos de red** cuando transfiera una base de datos en el modo sin conexión especificando el **Método** **DatabaseOffline** en la página **Bases de datos** del cuadro de diálogo **Editor de la tarea Transferir bases de datos** .  
  
 Especifique la ubicación del recurso compartido de archivos de red, o bien haga clic en el botón Examinar **(…)** para buscar la ubicación del recurso compartido de archivos de red.  
  
 Cuando transfiere una base de datos en modo sin conexión, los archivos de la base de datos se copian a la ubicación **Recurso compartido de archivos de red** del servidor de origen antes de ser transferidos al servidor de destino.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Editor de la tarea Transferir bases de datos &#40;página General&#41;](general-page-of-integration-services-designers-options.md)   
 [Editor de la tarea Transferir bases de datos &#40;página Bases de datos&#41;](../../2014/integration-services/transfer-database-task-editor-databases-page.md)  
  
  
