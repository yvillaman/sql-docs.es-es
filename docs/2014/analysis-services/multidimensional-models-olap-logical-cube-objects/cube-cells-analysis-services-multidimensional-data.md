---
title: Celdas (Analysis Services - datos multidimensionales) del cubo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
helpviewer_keywords:
- storing data [Analysis Services], cells
- hierarchies [Analysis Services], cells
- OLAP objects [Analysis Services], cells
- data members [Analysis Services]
- cubes [Analysis Services], cells
- empty cells [Analysis Services]
- nonleaf members
- cubes [Analysis Services], examples
- storage [Analysis Services], cells
- nonleaf cells
- calculated cells [Analysis Services]
- dimensions [Analysis Services], cells
- cells [Analysis Services]
- leaf members
- leaf cells
ms.assetid: 9945773c-a43b-40d4-91cf-3d2ebc90bca5
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 2fc955cda7ff4151992a1149ce2b732c18052ef0
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48141810"
---
# <a name="cube-cells-analysis-services---multidimensional-data"></a>Celdas de cubos (Analysis Services - Datos multidimensionales)
  Un cubo se compone de celdas organizadas por grupos de medida y dimensiones. Una celda representa la intersección lógica única de un miembro de cada dimensión del cubo en el mismo. Por ejemplo, el cubo que se describe en el siguiente diagrama contiene un grupo de medida con dos medidas, organizadas en tres dimensiones llamadas Source, Route y Time.  
  
 ![Diagrama de cubo que identifica una sola celda](../../../2014/analysis-services/dev-guide/media/as-cubeintro5.gif "diagrama de cubo que identifica una sola celda")  
  
 La celda sombreada única del diagrama es la intersección de los siguientes miembros:  
  
-   El miembro air de la dimensión Route.  
  
-   El miembro Africa de la dimensión Source.  
  
-   El miembro 4th quarter de la dimensión Time.  
  
-   La medida Packages.  
  
## <a name="leaf-and-nonleaf-cells"></a>Celdas hoja y no hoja  
 El valor de una celda en un cubo se puede obtener de varias formas. En el ejemplo anterior, el valor de la celda puede obtenerse directamente de la tabla de hechos del cubo, dado que todos los miembros utilizados para identificar la celda son *miembros hoja*. Un miembro hoja no tiene miembros secundarios, jerárquicamente hablando, y normalmente hace referencia a un solo registro de una tabla de dimensiones. Este tipo de celda se conoce como un *celda hoja*.  
  
 Sin embargo, una celda también pueden identificarse mediante el uso de *miembros no hoja*. Un miembro no hoja es un miembro que tiene uno o más miembros secundarios. En este caso, el valor de la celda se deriva normalmente de la agregación de miembros secundarios asociados al miembro no hoja. Por ejemplo, la intersección de los siguientes miembros y dimensiones hace referencia a una celda cuyo valor suministra la agregación:  
  
-   El miembro air de la dimensión Route.  
  
-   El miembro Africa de la dimensión Source.  
  
-   El miembro 2nd half de la dimensión Time.  
  
-   El miembro Packages.  
  
 El miembro 2nd half de la dimensión Time es un miembro no hoja. Por lo tanto, todos los valores asociados a él deben ser valores agregados, como se muestra en el siguiente diagrama.  
  
 ![las celdas de 3rd y 4th quarter para el miembro 2nd half](../../../2014/analysis-services/dev-guide/media/as-cubeintro6.gif "las celdas de 3rd y 4th quarter para el miembro 2nd half")  
  
 Si consideramos que las agregaciones de los miembros 3rd quarter y 4th quarter son sumas, el valor de la celda especificada es 400, que es el total de todas las celdas hoja sombreadas del diagrama anterior. Dado que el valor de la celda se deriva de la agregación de otras celdas, la celda especificada se considera un *celda no hoja*.  
  
 Los valores de celdas derivados para miembros que utilizan grupos de miembros y resúmenes personalizados, además de miembros personalizados, se controlan de la misma manera. Sin embargo, los valores de celdas derivados para miembros calculados se basan totalmente en la expresión MDX (Expresiones multidimensionales) utilizada para definir el miembro calculado; en algunos casos, puede que no intervenga ningún dato de celda real. Para obtener más información, consulte [operadores de resúmenes personalizados en dimensiones de elementos primarios y secundarios](../multidimensional-models/parent-child-dimension-attributes-custom-rollup-operators.md), [definir fórmulas de miembro personalizado](../multidimensional-models/attribute-properties-define-custom-member-formulas.md), y [cálculos](../multidimensional-models-olap-logical-cube-objects/calculations.md).  
  
## <a name="empty-cells"></a>Celdas vacías  
 No es necesario que todas las celdas de un cubo contengan un valor; puede haber intersecciones del cubo sin datos. Estas intersecciones, denominadas celdas vacías, se dan con frecuencia en los cubos debido a que no todas las intersecciones de un atributo de dimensión con una medida de un cubo contienen un registro correspondiente en una tabla de hechos. La proporción de celdas vacías en un cubo para el número total de celdas de un cubo con frecuencia se conoce como el *dispersión* de un cubo.  
  
 Por ejemplo, la estructura del cubo que aparece en el siguiente diagrama es parecida a otros ejemplos de este tema. Sin embargo, en este ejemplo, no existían embarques aéreos a Africa en el tercer trimestre (3rd quarter) o a Australia en el cuarto (4th quarter). No existen datos en la tabla de hechos que admitan las intersecciones de estas dimensiones y medidas, por lo que las celdas de estas intersecciones están vacías.  
  
 ![Diagrama de cubo que identifica las celdas vacías](../../../2014/analysis-services/dev-guide/media/as-cubeintro7.gif "diagrama de cubo que identifica las celdas vacías")  
  
 En [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], una celda vacía es una celda con características especiales. Como las celdas vacías pueden sesgar los resultados de combinaciones cruzadas, recuentos, etc. muchas funciones de MDX proporcionan la capacidad de omitir las celdas vacías para los cálculos. Para obtener más información, consulte [expresiones multidimensionales &#40;MDX&#41; referencia](/sql/mdx/multidimensional-expressions-mdx-reference), y [conceptos clave de MDX &#40;Analysis Services&#41;](../multidimensional-models/key-concepts-in-mdx-analysis-services.md).  
  
## <a name="security"></a>Seguridad  
 El acceso a los datos de las celdas se administra en [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en el nivel de rol y se puede controlar con precisión mediante el uso de expresiones MDX. Para obtener más información, consulte [otorgar acceso personalizado a datos de dimensión &#40;Analysis Services&#41;](../multidimensional-models/grant-custom-access-to-dimension-data-analysis-services.md), y [otorgar acceso personalizado a datos de la celda &#40;Analysis Services&#41;](../multidimensional-models/grant-custom-access-to-cell-data-analysis-services.md).  
  
## <a name="see-also"></a>Vea también  
 [Almacenamiento de cubos &#40;Analysis Services - datos multidimensionales&#41;](../multidimensional-models-olap-logical-cube-objects/cube-storage-analysis-services-multidimensional-data.md)   
 [Agregaciones y diseños de agregaciones](../multidimensional-models-olap-logical-cube-objects/aggregations-and-aggregation-designs.md)  
  
  
