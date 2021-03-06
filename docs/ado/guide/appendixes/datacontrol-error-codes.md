---
title: Коды ошибок DataControl | Документы Microsoft
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- errors [ADO], DataControl
- DataControl errors [ADO]
ms.assetid: 293df9d5-e1a2-406d-9107-07bf7cdc6f96
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: f42d65ef0ff274ecf1e671315fc019347586e903
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2018
ms.locfileid: "35271134"
---
# <a name="datacontrol-object-error-codes"></a>Коды ошибок объекта DataControl
В следующей таблице перечислены [RDS. DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md) объекта коды ошибок. Положительное десятичное трансляции низкий два байта, показаны отрицательное десятичное преобразование кода ошибки переполнения и шестнадцатеричных значений.

|RDS. Коды ошибок DataControl|Количество|Описание|
|---------------------------------|------------|-----------------|
|**IDS_AsyncPending**|4107 -2146824175 0x800A1011|Не удается выполнить операцию, пока асинхронная операция находится в состоянии ожидания.|
|**IDS_BadInlineTablegram**|4105 -2146824183 0x800A1009|Неправильный встроенного tablegram.|
|**IDS_CantConnect**|4099 -2146824189 0x800A1003|Не удается подключиться к серверу.|
|**IDS_CantCreateObject**|4100 -2146824188 0x800A1004|Невозможно создать бизнес-объекта.|
|**IDS_CantFindDataspace**|4102 -2146824186 0x800A1006|Недопустимое свойство пространство данных.|
|**IDS_CantInvokeMethod**|4101 -2146824187 0x800A1005|Метод нельзя вызвать в бизнес-объекте.|
|**IDS_CrossDomainWarning**|4112 -2146824170 0x800A1016|Эта страница обращается к данным в другом домене. Вы действительно хотите разрешить это? Чтобы избежать появления этого сообщения в Internet Explorer, можно добавить безопасных веб-сайт в зону надежных узлов на **безопасности** вкладке **обозревателя** диалоговое окно.|
|**IDS_InvalidADCClientVersion**|4106 -2146824176 0x800A1010|Недопустимая версия клиента служб удаленных рабочих СТОЛОВ — Клиент более новой версии сервера.|
|**IDS_INVALIDARG**|5376 -2147019520 0x80071500|Один или несколько аргументов являются недопустимыми.|
|**IDS_InvalidBindings**|4097 -2146824191 0x800A1001|Ошибка в свойства привязки.|
|**IDS_InvalidParam**|4110 -2146824172 0x800A1014|Один или несколько аргументов являются недопустимыми.|
|**IDS_NOINTERFACE**|5377 -2147019519 0x80071501|Такой интерфейс не поддерживается.|
|**IDS_NotReentrant**|4111 -2146824171 0x800A1015|Невозможно выполнить запрос, пока обработчик событий по-прежнему обрабатывается.|
|**IDS_ObjectNotSafe**|4103 -2146824185 0x800A1007|Параметры безопасности на этом компьютере запрещают создание бизнес-объекта.|
|**IDS_RecordsetNotOpen**|4109 -2146824173 0x800A1013|**Набор записей** не открыт.|
|**IDS_ResetInvalidField**|4108 -2146824174 0x800A1012|Столбец, указанный в **SortColumn** или **FilterColumn** не существует.|
|**IDS_RowsetNotUpdateable**|4104 -2146824184 0x800A1008|Набор строк не поддерживает обновление.|
|**IDS_UnexpectedError**|4351 -2146823937 0x800A10FF|Произошла непредвиденная ошибка.|
|**IDS_UpdatesFailed**|4098 -2146824190 0x800A1002|Не удалось обновить базу данных.|
|**IDS_URLMONNotFound**|4119 -2146824169 0x800A1017|DataControl **URL-адрес** свойства требуется системный файл Urlmon.dll, который не удается найти.|

## <a name="see-also"></a>См. также
 [Объект DataControl (служба удаленных рабочих столов)](../../../ado/reference/rds-api/datacontrol-object-rds.md)
