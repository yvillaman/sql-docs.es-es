---
title: Objeto Hierarchy (ADO MD) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Hierarchy
helpviewer_keywords:
- Hierarchy object [ADO MD]
ms.assetid: 034af340-ac79-494e-ba5e-2b57da1cb9de
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: d4f1ccb441da92c19b15a7e84b0fc0e451844d0a
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47851443"
---
# <a name="hierarchy-object-ado-md"></a>Objeto Hierarchy (ADO MD)
Representa una forma en que los miembros de un [dimensión](../../../ado/reference/ado-md-api/dimension-object-ado-md.md) puede agregar o "acumular." Una dimensión puede agregarse a una o más jerarquías.  
  
## <a name="remarks"></a>Comentarios  
 Con las colecciones y propiedades de un **jerarquía** objeto, puede hacer lo siguiente:  
  
-   Identificar el **jerarquía** con el [nombre](../../../ado/reference/ado-md-api/name-property-ado-md.md) y [UniqueName](../../../ado/reference/ado-md-api/uniquename-property-ado-md.md) propiedades.  
  
-   Devolver una cadena que describe el **jerarquía** con el [descripción](../../../ado/reference/ado-md-api/description-property-ado-md.md) propiedad.  
  
-   Devolver el [nivel](../../../ado/reference/ado-md-api/level-object-ado-md.md) objetos que componen el **jerarquía** con el [niveles](../../../ado/reference/ado-md-api/levels-collection-ado-md.md) colección.  
  
-   Usar el estándar de ADO [propiedades](../../../ado/reference/ado-api/properties-collection-ado.md) colección para obtener información adicional sobre el **jerarquía** objeto.  
  
 El **propiedades** colección contiene las propiedades proporcionadas por el proveedor. En la tabla siguiente se enumera las propiedades que podrían estar disponibles. La lista de propiedades reales puede variar en función de la implementación del proveedor. Consulte la documentación del proveedor para obtener una lista completa de las propiedades disponibles.  
  
|Nombre|Descripción|  
|----------|-----------------|  
|AllMember|El miembro en el nivel superior del resumen de la jerarquía.|  
|CatalogName|El nombre del catálogo al que pertenece este cubo.|  
|CubeName|Nombre del cubo.|  
|DefaultMember|El nombre único del miembro predeterminado para esta jerarquía.|  
|Descripción|Descripción de la jerarquía.|  
|DimensionType|El tipo de dimensión al que pertenece esta jerarquía.|  
|DimensionUniqueName|El nombre no ambiguo de la dimensión.|  
|HierarchyCaption|Etiqueta o título asociado a la jerarquía.|  
|HierarchyCardinality|Número de miembros de la jerarquía.|  
|HierarchyGUID|El GUID de la jerarquía.|  
|HierarchyName|Es el nombre de la jerarquía.|  
|HierarchyUniqueName|El nombre no ambiguo de la jerarquía.|  
|SchemaName|El nombre del esquema al que pertenece este cubo.|  
  
 Esta sección contiene el siguiente tema.  
  
-   [Propiedades, métodos y eventos](../../../ado/reference/ado-md-api/hierarchy-object-properties-methods-and-events.md)  
  
## <a name="see-also"></a>Vea también  
 [Ejemplo de CubeDef (VBScript)](../../../ado/reference/ado-md-api/cubedef-example-vbscript.md)   
 [Objeto de dimensión (ADO MD)](../../../ado/reference/ado-md-api/dimension-object-ado-md.md)   
 [Colección Hierarchies (ADO MD)](../../../ado/reference/ado-md-api/hierarchies-collection-ado-md.md)   
 [Colección de niveles (ADO MD)](../../../ado/reference/ado-md-api/levels-collection-ado-md.md)   
 [Colección de propiedades (ADO)](../../../ado/reference/ado-api/properties-collection-ado.md)
