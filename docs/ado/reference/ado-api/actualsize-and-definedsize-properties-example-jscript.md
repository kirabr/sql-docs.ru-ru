---
title: ActualSize и пример свойства DefinedSize (JScript) | Документы Microsoft
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
dev_langs:
- JScript
helpviewer_keywords:
- ActualSize property [ADO], JScript example
- DefinedSize property [ADO], JScript example
ms.assetid: 23575e70-2304-43b4-b8be-99d9a6842589
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 4c04e9179c1d040581a8447ea8309e59ef3e4754
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2018
ms.locfileid: "35275053"
---
# <a name="actualsize-and-definedsize-properties-example-jscript"></a>ActualSize и пример свойства DefinedSize (JScript)
В этом примере используется [ActualSize](../../../ado/reference/ado-api/actualsize-property-ado.md) и [DefinedSize](../../../ado/reference/ado-api/definedsize-property.md) свойства для отображения определенный размер и фактический размер поля. Вырежьте и вставьте следующий код в блокноте или другом текстовом редакторе и сохраните его в **ActualSizeJS.asp**.  
  
```  
<!-- BeginActualSizeJS -->  
<%@LANGUAGE="JScript" %>  
<%// use this meta tag instead of adojavas.inc%>  
<!--METADATA TYPE="typelib" uuid="00000205-0000-0010-8000-00AA006D2EA4" -->  
<html>  
  
<head>  
    <title>ActualSize and DefinedSize Properties Example (JScript)</title>  
<style>  
<!--  
body {  
   font-family: 'Verdana','Arial','Helvetica',sans-serif;  
   BACKGROUND-COLOR:white;  
   COLOR:black;  
    }  
.thead2 {  
   background-color: #800000;   
   font-family: 'Verdana','Arial','Helvetica',sans-serif;   
   font-size: x-small;  
   color: white;  
   }  
.tbody {   
   text-align: center;  
   background-color: #f7efde;  
   font-family: 'Verdana','Arial','Helvetica',sans-serif;   
   font-size: x-small;  
    }  
-->  
</style>  
</head>  
  
<body bgcolor="White">  
  
<h1>ADO ActualSize and DefinedSize Properties (JScript)</h1>  
<%  
    // connection and recordset variables  
    var Cnxn = Server.CreateObject("ADODB.Connection")  
    var strCnxn = "Provider='sqloledb';Data Source=" + Request.ServerVariables("SERVER_NAME") + ";" +  
            "Initial Catalog='Northwind';Integrated Security='SSPI';";  
    var rsSuppliers = Server.CreateObject("ADODB.Recordset");  
    // display variables  
    var fld, strMessage;          
  
    try  
    {  
        // open connection  
        Cnxn.Open(strCnxn);  
  
        // Open a recordset on the stores table      
        rsSuppliers.Open("Suppliers", strCnxn);  
  
        // build table headers  
        Response.Write("<table>");  
        Response.Write('<tr class="thead2"><th>Field Value</th>');  
        Response.Write("<th>Defined Size</th>");  
        Response.Write("<th>Actual Size</th></tr>");  
  
        while (!rsSuppliers.EOF)  
        {  
            // start a new line  
            strMessage = '<tr class="tbody">';  
  
            // Display the contents of the chosen field with  
            // its defined size and actual size  
            fld = rsSuppliers("CompanyName");  
            strMessage += '<td align="left">' + fld.Value + "</td>"   
            strMessage += "<td>" + fld.DefinedSize + "</td>";  
            strMessage += "<td>" + fld.ActualSize + "</td>";  
  
            // end the line  
            strMessage += "</tr>";  
  
            // display data  
            Response.Write(strMessage);  
  
            // get next record  
            rsSuppliers.MoveNext;  
  
        }  
         // close the table  
        Response.Write("</table>");  
    }  
    catch (e)  
    {  
        Response.Write(e.message);  
    }  
    finally  
    {  
        // clean up  
        if (rsSuppliers.State == adStateOpen)  
            rsSuppliers.Close;  
        if (Cnxn.State == adStateOpen)  
            Cnxn.Close;  
        rsSuppliers = null;  
        Cnxn = null;  
    }  
%>  
  
</body>  
  
</html>  
<!-- EndActualSizeJS -->  
```  
  
## <a name="see-also"></a>См. также  
 [Свойство ActualSize (ADO)](../../../ado/reference/ado-api/actualsize-property-ado.md)   
 [Свойство DefinedSize](../../../ado/reference/ado-api/definedsize-property.md)   
 [Объект Field](../../../ado/reference/ado-api/field-object.md)
