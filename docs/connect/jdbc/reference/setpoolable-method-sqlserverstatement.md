---
title: Método setPoolable (SQLServerStatement) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: f0f798c8-cafb-4acc-b85d-2e0059c91d92
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 809e16fce7cac83b6ba09fcef676c8da920b0dc3
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47759683"
---
# <a name="setpoolable-method-sqlserverstatement"></a>Método setPoolable (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Solicita que una instrucción se agrupe o no.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public void setPoolable(boolean poolable) throws SQLException  
```  
  
#### <a name="parameters"></a>Parámetros  
 *Puede agrupar*  
  
 Si es **false**, solicita que la instrucción se agrupe. Si es **false**, solicita que la instrucción no se agrupe.  
  
## <a name="exceptions"></a>Excepciones  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notas  
 El valor especificado en el parámetro *poolable* es una sugerencia de implementación para el grupo de instrucciones que indica si la aplicación quiere que se agrupe la instrucción. El administrador del grupo de instrucciones decide si va a utilizar la sugerencia.  
  
 El valor del grupo de una instrucción se aplica a las memorias caché de instrucciones internas que implementa el controlador y a las memorias caché de instrucciones externas que implementan los servidores y otras aplicaciones.  
  
 De forma predeterminada, no es puede agrupar cuando se crea un objeto SQLServerStatement. Los objetos SQLServerPreparedStatement y SQLServerCallableStatement son puede agrupables cuando se creó.  
  
 Se produce una excepción [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md) si se llama a este método en una instrucción cerrada.  
  
 [isPoolable](../../../connect/jdbc/reference/ispoolable-method-sqlserverstatement.md) devuelve un valor que indica si el objeto se puede agrupar.  
  
## <a name="see-also"></a>Ver también  
 [Miembros SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [Clase SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
