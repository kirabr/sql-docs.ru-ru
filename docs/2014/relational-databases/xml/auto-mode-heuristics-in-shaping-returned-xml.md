---
title: Эвристические методы режима AUTO, используемые при формировании возвращаемого XML-кода | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: xml
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- AUTO FOR XML mode, heuristics in shaping returned XML
ms.assetid: 6c5cb6c1-2921-4ba1-8100-0bf8074f9103
caps.latest.revision: 7
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 86e03044d610d109906ae6bfc1f0408eeb72ba8d
ms.sourcegitcommit: 2666ca7660705271ec5b59cc5e35f6b35eca0a96
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43890170"
---
# <a name="auto-mode-heuristics-in-shaping-returned-xml"></a>Эвристические методы режима AUTO, используемые при формировании возвращаемого XML-кода
  Режим AUTO определяет основанную на запросе структуру возвращаемого XML. При определении схемы вложения элементов применяемые в режиме AUTO эвристические процедуры сравнивают значения столбцов в соседних строках. Сравниваются столбцы всех типов, за исключением **ntext**, **text**, **image**и **xml**. Проводится также сравнение столбцов **(n)varchar(max)** и **varbinary(max)** .  
  
 В следующем примере иллюстрируются эвристики режима AUTO, определяющие структуру результирующего XML:  
  
```  
SELECT T1.Id, T2.Id, T1.Name  
FROM   T1, T2  
WHERE ...  
FOR XML AUTO  
ORDER BY T1.Id  
```  
  
 Для определения начала нового элемента <`T1`> сравниваются все значения столбцов таблицы T1, за исключением столбцов типов данных **ntext**, **text**, **image** и **xml**, если ключ таблицы Т1 не задан. Далее предположим, что столбец **Name** имеет тип данных **nvarchar(40)** и инструкция SELECT возвращает следующий набор строк:  
  
```  
T1.Id  T1.Name  T2.Id  
-----------------------  
1       Andrew    2  
1       Andrew    3  
1       Nancy     4  
```  
  
 Эвристики режима AUTO сравнивают все значения столбцов Id и Name таблицы Т1. Так как первые две строки имеют одинаковые значения столбцов Id и Name, в результат добавляется один элемент \<T1>, имеющий два дочерних элемента \<T2>.  
  
 Далее показан возвращенный XML:  
  
```  
<T1 Id="1" Name="Andrew">  
    <T2 Id="2" />  
    <T2 Id="3" />  
</T1>  
<T1 Id="1" Name="Nancy" >  
      <T2 Id="4" />  
</T>  
```  
  
 Теперь предположим, что столбец Name имеет тип данных **text** . Эвристики режима AUTO не выполняют сравнения для этого типа. Вместо этого в них предполагается, что значения различны. Это приводит к формированию приведенного ниже XML:  
  
```  
<T1 Id="1" Name="Andrew" >  
  <T2 Id="2" />  
</T1>  
<T1 Id="1" Name="Andrew" >  
  <T2 Id="3" />  
</T1>  
<T1 Id="1" Name="Nancy" >  
  <T2 Id="4" />  
</T1>  
```  
  
## <a name="see-also"></a>См. также  
 [Использование режима AUTO совместно с FOR XML](use-auto-mode-with-for-xml.md)  
  
  
