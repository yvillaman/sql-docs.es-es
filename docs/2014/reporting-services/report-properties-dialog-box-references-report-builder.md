---
title: Informe de cuadro de diálogo de propiedades, las referencias (generador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10082"
ms.assetid: 3414c857-8ea6-4fc4-a6d5-b4883c039efa
author: maggiesmsft
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 7e6f4a3f590c196731ed186f95cf5dc4078a1fc0
ms.sourcegitcommit: 2429fbcdb751211313bd655a4825ffb33354bda3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "52504141"
---
# <a name="report-properties-dialog-box-references-report-builder"></a>Propiedades del informe (cuadro de diálogo), Referencias (Generador de informes)
  Seleccione **Referencias** en el cuadro de diálogo **Propiedades del informe** para agregar o quitar referencias a ensamblados personalizados u otros ensamblados externos, así como instancias de clases personalizadas que las expresiones usarán en la definición de informe. Los ensamblados personalizados no se admiten en el modo local en el Generador de informes. Para crear informes que usan los ensamblados personalizados, use el Diseñador de informes de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].  
  
## <a name="options"></a>Opciones  
 **Agregar o quitar ensamblados**  
 Muestra los ensamblados a los que el informe hace referencia. El ensamblado debe estar disponible en el equipo donde está instalada la herramienta que está usando para diseñar el informe y en el servidor de informes. El nombre de la referencia debe coincidir con el contenido de  **\<CodeModule >** exactamente las etiquetas en el archivo de lenguaje de definición de informe (.rdl).  
  
 **Agregar**  
 Haga clic en esta opción para agregar un ensamblado. Haga clic en el botón de puntos suspensivos (...) para abrir el **abrir** cuadro de diálogo y seleccionar los ensamblados necesarios para completar la evaluación de procesamiento y la expresión de informe.  
  
 **Quitar**  
 Para quitar una referencia de ensamblado de la lista, seleccione el nombre del ensamblado y haga clic en el botón **Quitar** .  
  
 **Agregar o quitar clases**  
 Muestra las instancias de clases que se utilizan en el informe. Solo los miembros basados en instancias, no los miembros estáticos, utilizan la lista de clases.  
  
 **Agregar**  
 Haga clic en esta opción para agregar una referencia de clase. Haga clic en el botón de puntos suspensivos (...) para abrir el **abrir** cuadro de diálogo y seleccionar las clases necesarias para completar la evaluación de procesamiento y la expresión de informe.  
  
 **Quitar**  
 Para eliminar la instancia de clase, selecciónela y haga clic en el botón **Quitar** .  
  
 **Subir**  
 Para las clases que tienen dependencias, puede mover esta referencia hacia arriba en la lista.  
  
 **Bajar**  
 Para las clases que tienen dependencias, puede mover esta referencia hacia abajo en la lista.  
  
## <a name="see-also"></a>Vea también  
 [Ayuda del Generador de informes para cuadros de diálogo, paneles y asistentes](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md)   
 [Expresiones &#40;Generador de informes y SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md)  
  
  
