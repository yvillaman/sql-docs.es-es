---
title: Recuperación del tipo de fecha y hora como cadenas con el controlador SQLSRV | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- date and time types, retrieving as strings
ms.assetid: 58a974ea-4daf-4e3b-98ed-9731b9c9250f
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 29e36f2246556da7a43c3b8335f7a4e3479ae63c
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47686993"
---
# <a name="how-to-retrieve-date-and-time-type-as-strings-using-the-sqlsrv-driver"></a>Cómo recuperar el tipo de fecha y hora como cadenas con el controlador SQLSRV
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Esta característica se agregó en la versión 1.1 de los [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] y solo es válida cuando se utiliza el controlador SQLSRV para dichos [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)]. No se debe utilizar la opción de conexión ReturnDatesAsStrings con el controlador PDO_SQLSRV.  
  
Puede recuperar tipos de fecha y hora (**datetime**, **date**, **time**, **datetime2** y **datetimeoffset**) como cadenas especificando una opción en la cadena de conexión.  
  
### <a name="to-retrieve-date-and-time-types-as-strings"></a>Pasos para recuperar los tipos de fecha y hora como cadenas  
  
-   Utilice la opción de conexión siguiente:  
  
    ```  
    'ReturnDatesAsStrings'=>true  
    ```  
  
    El valor predeterminado es **False**, lo que significa que los tipos **datetime**, **Date**, **Time**, **DateTime2**y **DateTimeOffset** se devolverán como tipos de datos PHP **Datetime** .  
  
## <a name="example"></a>Ejemplo  
En el ejemplo siguiente se muestra la sintaxis que especifica cómo recuperar tipos de fecha y hora como cadenas.  
  
```  
<?php  
$serverName = "MyServer";  
$connectionInfo = array( "Database"=>"AdventureWorks", 'ReturnDatesAsStrings '=> true);  
$conn = sqlsrv_connect( $serverName, $connectionInfo);  
if( $conn === false )  
{  
   echo "Could not connect.\n";  
   die( print_r( sqlsrv_errors(), true));  
}  
  
sqlsrv_close( $conn);  
?>  
```  
  
## <a name="example"></a>Ejemplo  
En el ejemplo siguiente se muestra que se pueden recuperar las fechas como cadenas especificando UTF-8 al recuperar dichas cadenas, incluso cuando la conexión se realiza con `"ReturnDatesAsStrings" => false`.  
  
```  
<?php  
$serverName = "MyServer";  
$connectionInfo = array( "Database"=>"AdventureWorks", "ReturnDatesAsStrings" => false);  
$conn = sqlsrv_connect( $serverName, $connectionInfo);  
if( $conn === false ) {  
   echo "Could not connect.\n";  
   die( print_r( sqlsrv_errors(), true));  
}  
  
$tsql = "SELECT VersionDate FROM AWBuildVersion";  
  
$stmt = sqlsrv_query( $conn, $tsql);  
  
if ( $stmt === false ) {  
   echo "Error in statement preparation/execution.\n";  
   die( print_r( sqlsrv_errors(), true));  
}  
  
sqlsrv_fetch( $stmt );  
  
// retrieve date as string  
$date = sqlsrv_get_field( $stmt, 0, SQLSRV_PHPTYPE_STRING("UTF-8"));  
  
if( $date === false ) {  
   die( print_r( sqlsrv_errors(), true ));  
}  
  
echo $date;  
  
sqlsrv_close( $conn);  
?>  
```  
  
## <a name="example"></a>Ejemplo  
En el ejemplo siguiente se muestra cómo recuperar las fechas como cadenas especificando UTF-8 y `"ReturnDatesAsStrings" => true` en la cadena de conexión.  
  
```  
<?php  
$serverName = "MyServer";  
$connectionInfo = array( "Database"=>"AdventureWorks", 'ReturnDatesAsStrings'=> true, "CharacterSet" => 'utf-8' );  
$conn = sqlsrv_connect( $serverName, $connectionInfo);  
if( $conn === false ) {  
   echo "Could not connect.\n";  
   die( print_r( sqlsrv_errors(), true));  
}  
  
$tsql = "SELECT VersionDate FROM AWBuildVersion";  
  
$stmt = sqlsrv_query( $conn, $tsql);  
  
if ( $stmt === false ) {  
   echo "Error in statement preparation/execution.\n";  
   die( print_r( sqlsrv_errors(), true));  
}  
  
sqlsrv_fetch( $stmt );  
  
// retrieve date as string  
$date = sqlsrv_get_field( $stmt, 0 );  
  
if ( $date === false ) {  
   die( print_r( sqlsrv_errors(), true ));  
}  
  
echo $date;  
sqlsrv_close( $conn);  
?>  
```  
  
## <a name="example"></a>Ejemplo  
En el ejemplo siguiente se muestra cómo recuperar la fecha como un tipo de datos PHP. `'ReturnDatesAsStrings'=> false` está activado.  
  
```  
<?php  
$serverName = "MyServer";  
$connectionInfo = array( "Database"=>"AdventureWorks");  
$conn = sqlsrv_connect( $serverName, $connectionInfo);  
if( $conn === false ) {  
   echo "Could not connect.\n";  
   die( print_r( sqlsrv_errors(), true));  
}  
  
$tsql = "SELECT VersionDate FROM AWBuildVersion";  
  
$stmt = sqlsrv_query( $conn, $tsql);  
  
if ( $stmt === false ) {  
   echo "Error in statement preparation/execution.\n";  
   die( print_r( sqlsrv_errors(), true));  
}  
  
sqlsrv_fetch( $stmt );  
  
// retrieve date as string  
$date = sqlsrv_get_field( $stmt, 0 );  
  
if ( $date === false ) {  
   die( print_r( sqlsrv_errors(), true ));  
}  
  
$date_string = date_format( $date, 'jS, F Y' );  
echo "Date = $date_string\n";  
  
sqlsrv_close( $conn);  
?>  
```  
  
## <a name="see-also"></a>Ver también  
[Recuperación de datos](../../connect/php/retrieving-data.md)  
  
