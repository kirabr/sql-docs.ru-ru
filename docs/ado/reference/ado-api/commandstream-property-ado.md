---
title: Свойство CommandStream (ADO) | Документы Microsoft
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _Command::CommandStream
helpviewer_keywords:
- CommandStream property [ADO]
ms.assetid: f78f61b6-87e0-48dc-961e-83d0e20da58e
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: f8696706c0a785c77d7ca6a811811e1aba5fe133
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2018
ms.locfileid: "35276703"
---
# <a name="commandstream-property-ado"></a>Свойство CommandStream (ADO)
Указывает поток, используемый в качестве входного для [команда](../../../ado/reference/ado-api/command-object-ado.md) объекта.  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Задает или возвращает поток, используемый в качестве входного для **команда** объекта. Формат для этого потока поставщика; см. сведения в документации поставщика. Это свойство аналогично [CommandText](../../../ado/reference/ado-api/commandtext-property-ado.md) свойства, которое используется, чтобы указать строку ввода **команда**.  
  
## <a name="remarks"></a>Примечания  
 **CommandStream** и **CommandText** являются взаимоисключающими. Когда пользователь задает **CommandStream** свойства **CommandText** свойство задается пустая строка (»»). Если пользователь задает **CommandText** свойства **CommandStream** свойству будет присвоено **ничего не**.  
  
 Поведение **Command.Parameters.Refresh** и **Command.Prepare** методы определяются поставщиком. Значения параметров в потоке не могут быть обновлены.  
  
 Входной поток недоступен для других объектов ADO, которые возвращают источника **команда**. Например если [источника](../../../ado/reference/ado-api/source-property-ado-recordset.md) из [записей](../../../ado/reference/ado-api/recordset-object-ado.md) задано значение **команда** объекта, имеющего потока в качестве входных данных, **Recordset.Source** по-прежнему возвращает **CommandText** свойство, которое содержит пустую строку ("»), вместо содержимого потока **CommandStream** свойство.  
  
 При использовании поток команды (как указано в **CommandStream**), единственным допустимым [CommandTypeEnum](../../../ado/reference/ado-api/commandtypeenum.md) значения для [CommandType](../../../ado/reference/ado-api/commandtype-property-ado.md) свойства  **adCmdText** и **adCmdUnknown**. Любое другое значение приводит к ошибке.  
  
## <a name="applies-to"></a>Объект применения  
 [Объект Command (ADO)](../../../ado/reference/ado-api/command-object-ado.md)  
  
## <a name="see-also"></a>См. также  
 [Свойства CommandText (ADO)](../../../ado/reference/ado-api/commandtext-property-ado.md)   
 [Свойство Dialect](../../../ado/reference/ado-api/dialect-property.md)   
 [CommandTypeEnum](../../../ado/reference/ado-api/commandtypeenum.md)
