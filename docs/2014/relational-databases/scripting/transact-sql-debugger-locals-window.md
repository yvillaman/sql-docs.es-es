---
title: Variables locales (ventana) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.locals
helpviewer_keywords:
- Locals Window [Transact-SQL]
ms.assetid: 59bea640-7823-4b4d-832c-f384d83cca2f
caps.latest.revision: 15
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: 618881f9c81614edf73624aeb79762fe97ef12f5
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36103758"
---
# <a name="locals-window"></a>Ventana de locales
  La ventana **Variables locales** muestra información sobre las expresiones locales en el ámbito actual del depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] . El ámbito está establecido en el marco de la pila de llamadas actual que está seleccionado en la ventana **Pila de llamadas** . Debe estar en modo de depuración para mostrar las expresiones locales.  
  
## <a name="task-list"></a>Lista de tareas  
 **Para tener acceso a la ventana Variables locales**  
  
-   En el menú **Depurar** , haga clic en **Ventanas**y, a continuación, haga clic en **Variables locales**.  
  
 **Para cambiar el valor de una expresión**  
  
-   Haga clic con el botón derecho en la expresión y, después, seleccione **Editar valor**.  
  
## <a name="columns"></a>Columnas  
 **Nombre**  
 Es el nombre de la expresión local. El depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] muestra las variables, los parámetros y las funciones de sistema cuyos nombres comienzan por @@.  
  
 **Value**  
 Muestra el valor que está asignado actualmente a la expresión local. Esta columna está en blanco cuando no se ha asignado ningún valor a la expresión.  
  
 Si la longitud de una expresión es mayor que el ancho de la columna **Valor** , una información sobre herramientas muestra el valor completo al mover el puntero sobre la celda **Valor** para esa expresión.  
  
 Un icono de lupa en una celda **Valor** indica que el visualizador del depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] está disponible. En la lista, puede especificar **Visualizador de texto**, **Visualizador XML**o **Visualizador HTML**. Para iniciar un visualizador del depurador, haga clic en el icono de lupa. El depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] abre un cuadro de diálogo que muestra los datos en un formato adecuado al tipo de datos.  
  
 **Tipo**  
 Muestra el tipo de datos de la expresión.  
  
## <a name="see-also"></a>Vea también  
 [Depurador de Transact-SQL](transact-sql-debugger.md)   
 [Ver información del depurador de Transact-SQL](transact-sql-debugger-information.md)   
 [Ventana de inspección](transact-sql-debugger-watch-window.md)   
 [Ventana de pila de llamadas](transact-sql-debugger-call-stack-window.md)   
 [Cuadro de diálogo Inspección rápida](transact-sql-debugger-quickwatch-dialog-box.md)   
 [Expresiones &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/expressions-transact-sql)  
  
  