---
title: Actualización de datos PowerPivot | Documentos de Microsoft
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- unattended data refresh [Analysis Services with SharePoint]
- scheduled data refresh [Analysis Services with SharePoint]
- data refresh [Analysis Services with SharePoint]
ms.assetid: ac8358a3-ee71-44c7-8ee6-ac7afe3ebaa4
caps.latest.revision: 22
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: ec63b777759c8fbfb9cb66e70d3d96a129402e15
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36199450"
---
# <a name="powerpivot-data-refresh"></a>Actualización de datos PowerPivot
  Después de crear un libro que contiene datos PowerPivot, puede que desee actualizar los datos volviendo a ejecutar una consulta o comando periódicamente para conseguir información actualizada de los orígenes que se usaron originalmente para crear el libro. Este proceso se denomina `data refresh` y permite actualizar datos a petición en [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)] o como una operación programada que se ejecuta como un proceso de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en un servidor de aplicaciones de una granja de servidores de SharePoint. Para obtener más información, vea:  
  
-   [Actualización de datos de PowerPivot con SharePoint 2010](../powerpivot-data-refresh-with-sharepoint-2010.md)  
  
-   [Configurar PowerPivot cuenta de actualización de datos desatendida &#40;PowerPivot para SharePoint&#41;](../configure-unattended-data-refresh-account-powerpivot-sharepoint.md)  
  
-   [Configurar credenciales almacenadas para la actualización de datos en PowerPivot &#40;PowerPivot para SharePoint&#41;](../configure-stored-credentials-data-refresh-powerpivot-sharepoint.md)  
  
-   [Programar una actualización de datos &#40;PowerPivot para SharePoint&#41;](../schedule-a-data-refresh-powerpivot-for-sharepoint.md)  
  
-   [Ver el historial de actualización de datos &#40;PowerPivot para SharePoint&#41;](view-data-refresh-history-power-pivot-for-sharepoint.md)  
  
> [!NOTE]  
>  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] y SharePoint Server 2013 Excel Services usan una arquitectura diferente para la actualización de datos de modelos de datos de PowerPivot. La arquitectura admitida de SharePoint 2013 emplea Excel Services como componente principal para cargar modelos de datos de PowerPivot. La arquitectura usada anteriormente para la actualización de datos se basaba en un servidor que ejecutaba el Servicio de sistema de PowerPivot y [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en modo de SharePoint para cargar los modelos de datos. Para obtener más información, vea:  
>   
>  -   [Actualización de datos de PowerPivot con SharePoint 2013](power-pivot-data-refresh-with-sharepoint-2013.md)  
> -   [Actualizar libros y actualización de datos programada &#40;SharePoint 2013&#41;](../instances/install-windows/upgrade-workbooks-and-scheduled-data-refresh-sharepoint-2013.md)  
  
  