---
title: Generar (MDX) | Documentos de Microsoft
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 222479dd03263f61a603e30202f2abf54307b0bc
ms.sourcegitcommit: 97bef3f248abce57422f15530c1685f91392b494
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34740894"
---
# <a name="generate-mdx"></a>Generate (MDX)


  Aplica un conjunto a cada miembro de otro conjunto y a continuación combina los conjuntos resultantes mediante unión. Alternativamente, esta función devuelve una cadena concatenada que se creó evaluando una expresión de cadena en un conjunto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
Set expression syntax  
Generate( Set_Expression1 ,  Set_Expression2 [ , ALL ]  )  
  
String expression syntax  
Generate( Set_Expression1 ,  String_Expression [ ,Delimiter ]  )  
```  
  
## <a name="arguments"></a>Argumentos  
 *Set_Expression1*  
 Expresión MDX (Expresiones multidimensionales) válida que devuelve un conjunto.  
  
 *Set_Expression2*  
 Expresión MDX (Expresiones multidimensionales) válida que devuelve un conjunto.  
  
 *String_Expression*  
 Expresión de cadena válida que suele ser el nombre del miembro actual (CurrentMember.Name) de cada tupla del conjunto especificado.  
  
 *Delimitador*  
 Delimitador válido expresado como expresión de cadena.  
  
## <a name="remarks"></a>Notas  
 Si se especifica un segundo conjunto, la **generar** función devuelve un conjunto generado al aplicar las tuplas del segundo conjunto a cada tupla del primer conjunto *,* y, a continuación, combinar los conjuntos resultantes mediante unión. Si **todos los** se especifica, la función conserva los duplicados en el conjunto resultante.  
  
 Si se especifica una expresión de cadena, la **generar** función devuelve una cadena generada al evaluar la expresión de cadena especificada con cada tupla del primer conjunto *,* y, a continuación, concatenar los resultados. De forma opcional, la cadena se puede delimitar al separar cada resultado de la cadena concatenada resultante.  
  
## <a name="examples"></a>Ejemplos  
  
### <a name="set"></a>Establecer  
 En el ejemplo siguiente, la consulta devuelve un conjunto que contiene cuatro veces la medida Internet Sales Amount, porque hay cuatro miembros en el conjunto [Date].[Calendar Year].[Calendar Year].MEMBERS:  
  
```  
SELECT   
GENERATE( [Date].[Calendar Year].[Calendar Year].MEMBERS  
, {[Measures].[Internet Sales Amount]}, ALL)  
ON 0  
FROM [Adventure Works]  
```  
  
 Al quitar ALL, se modifica la consulta de modo que devuelva Internet Sales Amount una sola vez:  
  
```  
SELECT   
GENERATE( [Date].[Calendar Year].[Calendar Year].MEMBERS  
, {[Measures].[Internet Sales Amount]})  
ON 0  
FROM [Adventure Works]  
```  
  
 El uso práctico más común de **generar** está establecido evaluar una compleja expresión, como TopCount, en un conjunto de miembros. La consulta de ejemplo siguiente muestra los 10 productos más vendidos de cada año natural (Calendar Year) en filas:  
  
```  
SELECT   
{[Measures].[Internet Sales Amount]}  
ON 0,  
GENERATE(   
[Date].[Calendar Year].[Calendar Year].MEMBERS  
, TOPCOUNT(  
[Date].[Calendar Year].CURRENTMEMBER  
*  
[Product].[Product].[Product].MEMBERS  
,10, [Measures].[Internet Sales Amount]))  
ON 1  
FROM [Adventure Works]  
```  
  
 Tenga en cuenta que se muestran un 10 mejores diferente para cada año y que el uso de **generar** es la única manera de obtener este resultado. Basta con unir de forma cruzada los años naturales para que el conjunto de los 10 productos más vendidos muestre los 10 productos más vendidos de todo el tiempo, repetidos para cada año, tal y como se muestra en el ejemplo siguiente:  
  
```  
SELECT   
{[Measures].[Internet Sales Amount]}  
ON 0,  
[Date].[Calendar Year].[Calendar Year].MEMBERS  
*   
TOPCOUNT(  
[Product].[Product].[Product].MEMBERS  
,10, [Measures].[Internet Sales Amount])  
ON 1  
FROM [Adventure Works]  
```  
  
### <a name="string"></a>String  
 En el ejemplo siguiente se muestra el uso de **generar** para devolver una cadena:  
  
```  
WITH   
MEMBER MEASURES.GENERATESTRINGDEMO AS  
GENERATE(   
[Date].[Calendar Year].[Calendar Year].MEMBERS,  
[Date].[Calendar Year].CURRENTMEMBER.NAME)  
MEMBER MEASURES.GENERATEDELIMITEDSTRINGDEMO AS  
GENERATE(   
[Date].[Calendar Year].[Calendar Year].MEMBERS,  
[Date].[Calendar Year].CURRENTMEMBER.NAME, " AND ")  
SELECT   
{MEASURES.GENERATESTRINGDEMO, MEASURES.GENERATEDELIMITEDSTRINGDEMO}  
ON 0  
FROM [Adventure Works]  
```  
  
> [!NOTE]  
>  Esta forma de la **generar** función puede resultar útil al depurar cálculos, puesto que permite devolver una cadena que muestra los nombres de todos los miembros de un conjunto. Esto puede resultar más fácil de leer que la representación MDX estricta de un conjunto que el [SetToStr &#40;MDX&#41; ](../mdx/settostr-mdx.md) función devuelve.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de funciones MDX &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
