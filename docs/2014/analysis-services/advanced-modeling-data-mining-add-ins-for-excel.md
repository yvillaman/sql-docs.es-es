---
title: Avanzadas de modelado (minería de datos a los complementos para Excel) | Documentos de Microsoft
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- mining structures, creating
ms.assetid: 042270a3-6ec7-4b52-b2ba-2adb6c4740d5
caps.latest.revision: 16
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: de7eea9099b458a9f16e6928c1535dc4a03eb81a
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36106242"
---
# <a name="advanced-modeling-data-mining-add-ins-for-excel"></a>Modelado avanzado (Complementos de minería de datos para Excel)
  Puede usar el **avanzadas** opciones para crear modelos y estructuras de minería de datos personalizados con parámetros diferentes de las creadas por los asistentes de modelado de datos. Los dos asistentes descritos en esta sección le ayudan a crear una estructura de minería de datos completamente nueva y un nuevo modelo de minería de datos para aplicarlos a una estructura de minería de datos existente.  
  
## <a name="create-mining-structure"></a>Crear estructura de minería de datos  
 ![Botón de crear estructura de minería de datos, cinta de opciones de minería de datos](media/dmc-createstruct.gif "botón Crear estructura de minería de datos, cinta de opciones de minería de datos")  
  
 El **Asistente para crear la estructura de minería de datos** le permite crear una nueva estructura de minería de datos. Una estructura es una colección de datos extraídos de un origen de datos especificado.  Una estructura de minería de datos se puede actualizar con datos nuevos en el origen, pero al crear la estructura de minería de datos, debe definir tipos y nombres de datos que especifiquen cómo se utilizarán los datos para el análisis.  
  
 Puede utilizar los siguientes orígenes de datos para generar la estructura: una tabla de Excel, un intervalo de Excel o los datos en un origen de datos externo que ya se haya definido como una vista de origen de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].  
  
 Para cada estructura, tiene la opción de apartar algunos de los datos que se utilizarán para las pruebas y la validación. Al crear este *conjunto de datos de exclusión* al configurar los orígenes de datos, también puede asegurarse de que todos los modelos que se basan en la estructura se puede utilizar un conjunto de datos coherente para las pruebas.  
  
 Una vez creada una estructura de minería de datos, puede agregar varios modelos para aplicar distintos métodos de análisis.  
  
 Para obtener más información sobre cómo usar el **crear Asistente para la estructura de minería de datos**, consulte [Create Mining Structure &#40;complementos de minería de datos de SQL Server&#41;](create-mining-structure-sql-server-data-mining-add-ins.md).  
  
## <a name="add-model-to-structure"></a>Agregar modelo a estructura  
 ![Agregar modelo a botón estructura](media/dmc-addmodel.gif "Add Model al botón de estructura")  
  
 Cuando se agrega un modelo nuevo a una estructura, se analizan los datos mediante un algoritmo diferente o con otros parámetros. Esta opción es especialmente útil si desea crear un modelo mediante uno de los algoritmos que no se exponen en las herramientas del Cliente de minería de datos.  
  
 Por ejemplo, puede usar los algoritmos que admite [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], por ejemplo:  
  
-   Regresión lineal  
  
-   Agrupación en clústeres de secuencia  
  
-   Análisis de asociación en conjuntos de datos anidados  
  
 Para ver qué tipo de estructuras de minería de datos están disponibles, puede examinar los modelos y estructuras almacenados en [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] haciendo clic en **administrar modelos** o **examinar**.  
  
 Está limitado a las estructuras de minería de datos que se crearon durante la sesión actual o a las estructuras de minería de datos que se guardaron en una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].  
  
 Para obtener más información, consulte [Agregar modelo a estructura &#40;complementos minería de datos para Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md).  
  
## <a name="see-also"></a>Vea también  
 [Administrar modelos &#40;complementos de minería de datos de SQL Server&#41;](manage-models-sql-server-data-mining-add-ins.md)   
 [Examinar modelos en Excel &#40;complementos de minería de datos de SQL Server&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  