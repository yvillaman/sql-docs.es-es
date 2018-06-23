---
title: Actualizar Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- upgrading databases
- databases [Analysis Services], upgrading
- installing Analysis Services, side-by-side installations
- Analysis Services upgrades
- Analysis Services upgrades, about upgrading Analysis Services
- SSAS, database migration
- upgrading Analysis Services
- installing Analysis Services, upgrading
- SSAS, upgrading
ms.assetid: a131d329-386e-4470-aaa9-ffcde4e5ec0c
caps.latest.revision: 63
author: markingmyname
ms.author: maghan
manager: jhubbard
ms.openlocfilehash: dd4ae8ef0eb99859885dfbd33af284c843c282d4
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36105437"
---
# <a name="upgrade-analysis-services"></a>Actualizar Analysis Services
  Use el programa de instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para actualizar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Para obtener información detallada acerca de la actualización [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en modo de SharePoint, vea [actualizar PowerPivot para SharePoint](upgrade-power-pivot-for-sharepoint.md). Para obtener más información acerca de cómo actualizar un servidor SQL existente de la instancia, consulte [actualizar a SQL Server 2014 mediante el Asistente para la instalación &#40;el programa de instalación&#41;](upgrade-sql-server-using-the-installation-wizard-setup.md).  
  
## <a name="known-upgrade-issues"></a>Problemas de actualización conocidos  
 Antes de actualizarse a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], revise lo siguiente:  
  
-   [Notas de la versión de SQL Server 2014](http://go.microsoft.com/fwlink/?LinkID=296445).  
  
-   Para saber qué [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] características y funcionalidades se han eliminado, en desuso o cambiado vea [compatibilidad con versiones anteriores de Analysis Services](../../analysis-services/analysis-services-backward-compatibility.md).  
  
## <a name="pre-upgrade-checklist"></a>Lista de comprobación previa a la actualización  
 Antes de actualizar, revise la información siguiente:  
  
-   [Actualizaciones de ediciones y versiones admitidas](supported-version-and-edition-upgrades.md)  
  
-   [Requisitos de hardware y Software para instalar SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md)  
  
-   [Comprobar los parámetros del Comprobador de configuración del sistema](check-parameters-for-the-system-configuration-checker.md)  
  
-   [Consideraciones de seguridad para una instalación de SQL Server](../../sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
-   [Realizar una copia de seguridad y restaurar las bases de datos de Analysis Services](../../analysis-services/multidimensional-models/backup-and-restore-of-analysis-services-databases.md)  
  
-   [Usar el Asesor de actualizaciones para preparar las actualizaciones](../../sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md)  
  
## <a name="upgrading-analysis-services"></a>Actualizar Analysis Services  
 Puede elegir entre varios enfoques para actualizar el servidor y los datos:  
  
-   Un **actualización in situ** reemplaza archivos de programa existentes con [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] archivos de programa. Las bases de datos permanecen en la misma ubicación. Las carpetas de programas se actualizan para reflejar el nuevo nombre.  
  
-   A **actualización side-by-side** es una nueva instalación de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] en el mismo equipo que tenga una instancia de Analysis Services existente. Puede mover bases de datos a la nueva instancia en el mismo equipo y desinstalar después la versión anterior si ya no la utiliza.  
  
-   También puede instalar Analysis Services en el nuevo hardware y migrar después las bases de datos existentes a ese servidor.  
  
## <a name="in-place-upgrade"></a>Actualización en contexto  
 Puede actualizar una instancia existente de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y, como parte del proceso de actualización, migrar automáticamente las bases de datos existentes de la antigua instancia a la nueva. Dado que los metadatos y los datos binarios son compatibles entre las dos versiones, después de actualizar se conservarán los datos y no es necesario migrarlos manualmente.  
  
 Para actualizar una instancia existente, ejecute el programa de instalación y especifique el nombre de la instancia existente como nombre de la nueva instancia.  
  
## <a name="upgrading-databases"></a>Actualizar bases de datos  
 Las bases de datos creadas en versiones anteriores de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] se ejecutan en el servidor actualizado con la configuración de nivel de compatibilidad de base de datos más antigua. Las bases de datos creadas en las siguientes versiones tienen un nivel de compatibilidad de base de datos de 105. Puede cambiar el nivel de compatibilidad si desea utilizar las características que requieren un nivel de compatibilidad de base de datos más reciente. De lo contrario, puede ejecutar las bases de datos del servidor actualizado utilizando la configuración original. Para obtener más información, consulte [establecer el nivel de compatibilidad de una base de datos multidimensionales &#40;Analysis Services&#41;](../../analysis-services/multidimensional-models/compatibility-level-of-a-multidimensional-database-analysis-services.md).  
  
-   [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]  
  
-   [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]  
  
-   [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]  
  
-   [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Características compatibles con las ediciones de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md)   
 [Planear una instalación de SQL Server](../../sql-server/install/planning-a-sql-server-installation.md)   
 [Descripción de la arquitectura OLAP de Microsoft](../../analysis-services/multidimensional-models/olap-physical/understanding-microsoft-olap-architecture.md)   
 [Actualizar PowerPivot para SharePoint](upgrade-power-pivot-for-sharepoint.md)   
 [Instalar Analysis Services en el modo de minería de datos y multidimensional](../../sql-server/install/install-analysis-services-in-multidimensional-and-data-mining-mode.md)   
 [PowerPivot para SharePoint 2010](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
  
  