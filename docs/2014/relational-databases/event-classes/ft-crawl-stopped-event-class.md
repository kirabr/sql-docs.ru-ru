---
title: Класс событий FT:Crawl Stopped | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Crawl Stopped event class
ms.assetid: dbc91bf7-687c-4083-9694-02f3e102c175
caps.latest.revision: 28
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 82935c5d032887afb580c81b9bf376eba5def47e
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37199544"
---
# <a name="ftcrawl-stopped-event-class"></a>Класс событий FT:Crawl Stopped
  Класс событий **:Crawl Stopped** указывает на то, что полнотекстовое сканирование (заполнение) было остановлено. Остановка может быть результатом успешного завершения сканирования или появления неустранимой ошибки.  
  
## <a name="ftcrawl-stopped-event-class-data-columns"></a>Столбцы данных класса событий FT:Crawl Stopped  
  
|Имя столбца данных|Тип данных|Описание|Идентификатор столбца|Фильтруемый|  
|----------------------|---------------|-----------------|---------------|----------------|  
|**DatabaseID**|**int**|Идентификатор базы данных, в которой было остановлено полнотекстовое сканирование. Определите значение для базы данных, используя функцию DB_ID.|3|Да|  
|**EventClass**|**int**|Тип события = 156.|27|Нет|  
|**EventSequence**|**int**|Последовательность данного события в запросе.|51|Нет|  
|**IsSystem**|**int**|Указывает, произошло событие в системном или в пользовательском процессе. 1 = системный, 0 = пользовательский.|60|Да|  
|**ObjectID**|**int**|Идентификатор объекта, назначенный системой. Полнотекстовое сканирование было остановлено до полнотекстового индекса на данном объекте.|22|Да|  
|**SessionLoginName**|**nvarchar**|Имя входа пользователя, создавшего этот сеанс. Например, при подключении к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] по имени "Имя_входа1" и при выполнении инструкции под именем "Имя_входа2" **SessionLoginName** содержит значение "Имя_входа1", а **LoginName** — значение "Имя_входа2". В этом столбце отображаются как имена входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , так и имена входа [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.|64|Да|  
|**SPID**|**int**|Идентификатор сеанса, в котором произошло событие.|12|Да|  
|**StartTime**|**datetime**|Время начала события, если оно известно.|14|Да|  
|**TransactionID**|**bigint**|Назначенный системой идентификатор транзакции.|4|Да|  
  
## <a name="see-also"></a>См. также  
 [Хранимая процедура sp_trace_setevent (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
