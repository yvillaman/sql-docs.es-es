---
title: Diseñar procedimientos almacenados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
helpviewer_keywords:
- stored procedures [Analysis Services], designing
- dependent assemblies [Analysis Services]
- assemblies [Analysis Services]
ms.assetid: af4e7bd5-041b-4a40-9942-0ef6a3af46c6
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: b05a4b7b1fe1c8ee70692472dc69105f01a275e0
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48164435"
---
# <a name="designing-stored-procedures"></a>Diseñar procedimientos almacenados
  El modelo de objeto administrativo Objetos de administración de análisis (AMO) y el modelo de objeto orientado al cliente Objetos de datos [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX® (Multidimensional) (ADO MD) se incluyen en los procedimientos almacenados.  
  
 Los procedimientos almacenados deben estar en el ámbito (el servidor o la base de datos) para ser visibles en el nivel de Expresiones multidimensionales (MDX) para ser llamados. Sin embargo, cuando se invoca un procedimiento almacenado, su ámbito no se limita a acciones bajo su elemento primario. Un procedimiento almacenado puede realizar cambios o modificaciones en cualquier lugar del servidor, sujeto únicamente a las limitaciones de seguridad del proceso de usuario que lo invoca o a las limitaciones de la transacción en la que opera.  
  
 Los procedimientos del ámbito del servidor están disponibles en todos los contextos del servidor. Los procedimientos almacenados del ámbito de la base de datos solamente están visibles en el contexto de la base de datos en la que se definen.  
  
 Al igual que con cualquier función MDX, para que pueda continuar una sesión MDX se debe resolver el procedimiento almacenado; los procedimientos almacenados bloquean las sesiones MDX mientras se ejecutan. A menos que exista una razón específica para detener una sesión MDX pendiente de interacción del usuario, se desaconsejan las interacciones del usuario (como los cuadros de diálogo).  
  
## <a name="dependent-assemblies"></a>Ensamblados dependientes  
 Todos los ensamblados dependientes se deben cargar en una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para que los encuentre Common Language Runtime (CLR). [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] almacena los ensamblados dependientes en la misma carpeta que el ensamblado principal, de manera que CLR resuelve automáticamente todas las referencias de función a las funciones en esos ensamblados.  
  
## <a name="see-also"></a>Vea también  
 [Administración de los ensamblados de modelos multidimensionales](../multidimensional-models/multidimensional-model-assemblies-management.md)   
 [Definición de procedimientos almacenados](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
