---
title: Control de errores | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 8fd5b5ef-d939-4b78-b900-5b7b6ddb3eb9
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 066aa64a529d2066c0dcce50cd2f2aff12dcf948
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47758993"
---
# <a name="handling-errors"></a>Control de errores
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  Cuando se usa el [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)], todas las condiciones de error de la base de datos se devuelven a la aplicación Java como excepciones mediante la clase [SQLServerException](../../connect/jdbc/reference/sqlserverexception-class.md). Los siguientes métodos de la clase SQLServerException están heredados de java.sql.SQLException y java.lang.Throwable y se pueden emplear para devolver información específica sobre el error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se ha producido:  
  
-   getSQLState devuelve el código de estado X/Open o SQL99 de la excepción.  
  
-   getErrorCode devuelve el número específico del error de la base de datos.  
  
-   getMessage devuelve el texto completo de la excepción. El texto del mensaje de error describe el problema y, con frecuencia, incluye marcadores de posición de información tales como nombres de objetos, que se incluyen en el mensaje de error cuando se muestra.  
  
-   getNextException devuelve el siguiente objeto SQLServerException o null si no hay ningún objeto de excepción más para devolver.  
  
 En el siguiente ejemplo, se pasa a la función una conexión abierta a la base de datos de ejemplo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal_md.md)] y se construye una instrucción SQL incorrecta que no incluye una cláusula FROM. A continuación, se ejecuta la instrucción de SQL y se procesa una excepción de SQL.  
  
 [!code[JDBC#HandlingErrors1](../../connect/jdbc/codesnippet/Java/handling-errors_1.java)]  
  
## <a name="see-also"></a>Ver también  
 [Diagnosticar problemas del controlador JDBC](../../connect/jdbc/diagnosing-problems-with-the-jdbc-driver.md)  
  
  
