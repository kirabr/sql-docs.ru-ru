---
title: MSrepl_errors (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-tables
ms.reviewer: ''
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- MSrepl_errors
- MSrepl_errors_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- MSrepl_errors system table
ms.assetid: c6e023c1-2c32-4269-8d76-e442ea309e4b
caps.latest.revision: 16
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 992e5594f208cd64ef48d90f2b29e7018719a6da
ms.sourcegitcommit: a431ca21eac82117492d7b84c398ddb3fced53cc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2018
ms.locfileid: "39103722"
---
# <a name="msreplerrors-transact-sql"></a>MSrepl_errors (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  **MSrepl_errors** таблица содержит строки с расширенные сведения сбой агента распространителя и агента слияния. Эта таблица хранится в базе данных распространителя.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**идентификатор**|**int**|Идентификатор ошибки.|  
|**time**|**datetime**|Время возникновения ошибки.|  
|**error_type_id**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**source_type_id**|**int**|Идентификатор типа источника ошибки.|  
|**source_name**|**Nvarchar(100)**|Имя источника ошибки.|  
|**error_code**|**sysname**|Код ошибки.|  
|**текст_ошибки**|**ntext**|Сообщение об ошибке.|  
|**xact_seqno**|**varbinary(16)**|Порядковый номер транзакции в журнале начальной транзакции для пакета, завершенного с ошибкой. Это последовательный номер журнала транзакций, содержащего первую транзакцию в пакете, выполненном с ошибкой. Он используется только агентами распространителя.|  
|**command_id**|**int**|Идентификатор команды пакета, завершенного с ошибкой. Это идентификатор первой команды в пакете, завершенном с ошибкой, используемый только агентами распространителя.|  
|**session_id**|**int**|Идентификатор сеанса агента, в котором возникла ошибка.|  
  
## <a name="see-also"></a>См. также  
 [Таблицы репликации &#40;Transact-SQL&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Представления репликации (Transact-SQL)](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
