---
title: ExecuteOptionEnum | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- ExecuteOptionEnum
helpviewer_keywords:
- ExecuteOptionEnum enumeration [ADO]
ms.assetid: 68bfa83a-5df4-4bef-8736-0f88ae8c29ea
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 7512f456d1423caf6318903119c2ad55c1938dec
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47719123"
---
# <a name="executeoptionenum"></a>ExecuteOptionEnum
Especifica cómo un proveedor debe ejecutar un comando.  
  
|Constante|Valor|Descripción|  
|--------------|-----------|-----------------|  
|**adAsyncExecute**|0x10|Indica que el comando debería ejecutarse de forma asincrónica.<br /><br /> Este valor no puede combinarse con el [CommandTypeEnum](../../../ado/reference/ado-api/commandtypeenum.md) valor **adCmdTableDirect**.|  
|**adAsyncFetch**|0x20|Indica que las filas restantes después de la cantidad inicial especificado en el [CacheSize](../../../ado/reference/ado-api/cachesize-property-ado.md) propiedad se debe recuperar de forma asincrónica.|  
|**adAsyncFetchNonBlocking**|0x40|Indica que el subproceso principal bloquee nunca al recuperar. Si la fila solicitada no se ha recuperado, la fila actual se desplaza automáticamente al final del archivo.<br /><br /> Si abre un [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md) desde un [Stream](../../../ado/reference/ado-api/stream-object-ado.md) que contiene una forma persistente almacenado **Recordset**, **adAsyncFetchNonBlocking** no tendrán un efecto. la operación será sincrónica y de bloqueo.<br /><br /> **adAsynchFetchNonBlocking** no tiene ningún efecto cuando el [adCmdTableDirect](../../../ado/reference/ado-api/commandtypeenum.md) opción se utiliza para abrir el **Recordset**.|  
|**adExecuteNoRecords**|0x80|Indica que el texto del comando es un comando o procedimiento almacenado que no devuelve filas (por ejemplo, un comando que sólo inserta datos). Si se recuperan las filas, se descartan y no se devuelve.<br /><br /> **adExecuteNoRecords** sólo se puede pasar como un parámetro opcional para el **comando** o **conexión ejecute** método.|  
|**adExecuteStream**|0x400|Indica que se deben devolver los resultados de una ejecución de comandos como una secuencia.<br /><br /> **adExecuteStream** sólo se puede pasar como un parámetro opcional para el **ejecutar comando** método.|  
|**adExecuteRecord**||Indica que el **CommandText** es un comando o procedimiento almacenado que devuelve una sola fila que se debe devolver como un **registro** objeto.|  
|**realiza la consulta**|-1|Indica que el comando no está especificado.|  
  
## <a name="adowfc-equivalent"></a>Equivalente de ADO y WFC  
 Paquete: **com.ms.wfc.data**  
  
|Constante|  
|--------------|  
|AdoEnums.ExecuteOption.ASYNCEXECUTE|  
|AdoEnums.ExecuteOption.ASYNCFETCH|  
|AdoEnums.ExecuteOption.ASYNCFETCHNONBLOCKING|  
|AdoEnums.ExecuteOption.NORECORDS|  
|AdoEnums.ExecuteOption.UNSPECIFIED|  
  
## <a name="applies-to"></a>Se aplica a  
  
|||  
|-|-|  
|[Método Execute (Command ADO)](../../../ado/reference/ado-api/execute-method-ado-command.md)|[Execute (método) (conexión de ADO)](../../../ado/reference/ado-api/execute-method-ado-connection.md)|  
|[Open (método) (conjunto de registros ADO)](../../../ado/reference/ado-api/open-method-ado-recordset.md)|[Requery (método)](../../../ado/reference/ado-api/requery-method.md)|
