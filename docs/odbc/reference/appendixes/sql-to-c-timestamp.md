---
title: 'SQL с отметкой времени C: | Документы Microsoft'
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- timestamp data type [ODBC]
- converting data from SQL to C types [ODBC], timestamp
- data conversions from SQL to C types [ODBC], timestamp
ms.assetid: 6a0617cf-d8c0-4316-8bb4-e6ddb45d7bf1
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 5582bf0e3c3b498799c229176b824770eec27433
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32912359"
---
# <a name="sql-to-c-timestamp"></a>SQL с отметкой времени C:
Идентификатор для типа данных ODBC SQL timestamp является:  
  
 SQL_TYPE_TIMESTAMP  
  
 Следующая таблица показывает ODBC C типы данных, к которым могут быть преобразованы данные отметок времени SQL. Объяснение столбцы и условия в таблице см. в разделе [преобразование данных из SQL в типы данных C](../../../odbc/reference/appendixes/converting-data-from-sql-to-c-data-types.md).  
  
|Идентификатор типа C|Тест|**TargetValuePtr*|**StrLen_or_IndPtr*|SQLSTATE|  
|-----------------------|----------|------------------------|----------------------------|--------------|  
|SQL_C_CHAR|*BufferLength* > байт символов<br /><br /> 20 < = *BufferLength* < = байт символов<br /><br /> *BufferLength* < 20|Данные <br /><br /> Усеченные данные [b]<br /><br /> Не определено.|Длина данных в байтах<br /><br /> Длина данных в байтах<br /><br /> Не определено.|н/д<br /><br /> 01004<br /><br /> 22003|  
|SQL_C_WCHAR|*BufferLength* > Длина символьной<br /><br /> 20 < = *BufferLength* < = Длина символьной строки<br /><br /> *BufferLength* < 20|Данные <br /><br /> Усеченные данные [b]<br /><br /> Не определено.|Длина данных в символах<br /><br /> Длина данных в символах<br /><br /> Не определено.|н/д<br /><br /> 01004<br /><br /> 22003|  
|SQL_C_BINARY|Байтовая длина данных < = *BufferLength*<br /><br /> Байтовая длина данных > *BufferLength*|Данные <br /><br /> Не определено.|Длина данных в байтах<br /><br /> Не определено.|н/д<br /><br /> 22003|  
|SQL_C_TYPE_DATE|Часть времени timestamp равно нулю []<br /><br /> Часть времени отметка времени имеет ненулевое значение, [a]|Данные <br /><br /> Усеченные данные [c]|6 [f]<br /><br /> 6 [f]|н/д<br /><br /> 01S07|  
|SQL_C_TYPE_TIME|Часть долей секунды timestamp равно нулю []<br /><br /> Доли секунды часть отметка времени является ненулевое значение, [a]|Данные [d]<br /><br /> Усеченные данные [d], [e]|6 [f]<br /><br /> 6 [f]|н/д<br /><br /> 01S07|  
_C_TYPE_TIMESTAMP|Часть долей секунды отметки времени не усекается []<br /><br /> Усечение долей секунды часть отметок времени []|Данные [e]<br /><br /> Усеченные данные [e]|16 [f]<br /><br /> 16 [f]|н/д<br /><br /> 01S07|  
  
 [] значение *BufferLength* учитывается для этого преобразования. Драйвер предполагает, что размер **TargetValuePtr* — это размер типа данных C.  
  
 [b] доли секунды отметка времени, усекаются.  
  
 [c часть времени временная метка усекается.  
  
 [d] часть даты отметка времени учитывается.  
  
 [e долей секунды отметок времени округляются.  
  
 [f] это размер соответствующие типы данных C.  
  
 При преобразовании в символьный C данных timestamp SQL результирующая строка находится в «*гггг*-*мм*-*дд* *hh* :*мм*:*ss*[.*f...*]» формат, где можно использовать до девяти цифр для долей секунды. Этот формат не влияют настройки Windows® страны. (За исключением десятичного разделителя и долей секунды, весь формат должно использоваться, независимо от того, точность типа данных timestamp SQL.)
