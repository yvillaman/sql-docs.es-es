---
title: Administrador de conexiones de caché | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Cache connection manager
ms.assetid: bdc92038-3720-4795-8a5c-79b963f2c952
caps.latest.revision: 23
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 9abbf2c25ca9029765e3726f8c767f2af7a3f2c5
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36198483"
---
# <a name="cache-connection-manager"></a>Administrador de conexiones de caché
  El administrador de conexiones de caché lee datos a partir de la transformación de caché o de un archivo caché (.caw) y puede guardar los datos en un archivo caché. Si configura el administrador de conexiones de caché para que utilice un archivo caché, los datos siempre se almacenan en memoria.  
  
 La transformación de caché escribe los datos procedentes de un origen de datos conectado del flujo de datos en un administrador de conexiones de caché. La transformación Búsqueda de un paquete realiza búsquedas en los datos.  
  
> [!NOTE]  
>  El administrador de conexiones de caché no admite los tipos de datos de objetos binarios grandes (BLOB) DT_TEXT, DT_NTEXT y DT_IMAGE. Si el conjunto de datos de referencia contiene un tipo de datos BLOB, se producirá un error en el componente al ejecutar el paquete. Puede utilizar el **Editor del administrador de conexiones de caché** para modificar los tipos de datos de columna. Para obtener más información, vea [Cache Connection Manager Editor](../cache-connection-manager-editor.md).  
  
> [!NOTE]  
>  El nivel de protección del paquete no se aplica al archivo caché. Si el archivo caché contiene información confidencial, utilice una lista de control de acceso (ACL) para restringir el acceso a la ubicación o carpeta en la que almacena el archivo. Solo debería permitir el acceso a ciertas cuentas. Para obtener más información, vea [Acceso a los archivos usados por los paquetes](../access-to-files-used-by-packages.md).  
  
## <a name="configuration-of-the-cache-connection-manager"></a>Configuración del administrador de conexiones de caché  
 Puede configurar el administrador de conexiones de caché de las siguientes maneras:  
  
-   Indicar si se ha de utilizar un archivo caché.  
  
     Si configura el administrador de conexiones de caché para utilizar un archivo caché, el administrador de conexiones realizará una de las siguientes acciones:  
  
    -   Guardar los datos en el archivo cuando se haya configurado una transformación de caché para escribir los datos procedentes de un origen de datos del flujo de datos en el administrador de conexiones de caché.  
  
    -   Leer los datos desde el archivo caché.  
  
     Para obtener más información, vea [Cache Transform](../data-flow/transformations/cache-transform.md).  
  
-   Cambiar los metadatos de las columnas almacenadas en la caché.  
  
-   Actualizar el nombre del archivo caché en tiempo de ejecución con una expresión para establecer la propiedad ConnectionString. Para obtener más información, vea [Usar expresiones de propiedad en paquetes](../expressions/use-property-expressions-in-packages.md).  
  
 Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] o mediante programación.  
  
 Para obtener más información acerca de las propiedades que puede configurar en el Diseñador [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , vea [Editor del administrador de conexiones de caché](../cache-connection-manager-editor.md).  
  
 Para obtener más información sobre cómo configurar un administrador de conexiones mediante programación, vea <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> y [Agregar conexiones mediante programación](../building-packages-programmatically/adding-connections-programmatically.md).  
  
## <a name="related-tasks"></a>Related Tasks  
 [Implementación de una transformación Búsqueda en el modo Caché completa con el Administrador de conexiones de caché](lookup-transformation-full-cache-mode-ole-db-connection-manager.md)  
  
  