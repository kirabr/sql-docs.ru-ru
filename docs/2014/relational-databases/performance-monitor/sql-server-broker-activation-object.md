---
title: Объект активации брокера (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:Broker Activation
- Broker Activation object
ms.assetid: cd9b6880-c924-42c7-b333-09c303317c0b
caps.latest.revision: 19
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 7799c0ebb5dce481da8257bf74700d2fe40caeee
ms.sourcegitcommit: 8ae6e6618a7e9186aab3c6a37ea43776aa9a382b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43816300"
---
# <a name="sql-server-broker-activation-object"></a>SQL Server, объект Broker Activation
  Объект производительности **SQLServer:BrokerActivation** содержит счетчики производительности, возвращающие сведения об активации хранимых процедур. В следующей таблице перечислены счетчики этого объекта.  
  
|Счетчики SQL Server Broker Activation|Описание|  
|-------------------------------------------|-----------------|  
|**Количество вызовов хранимых процедур/сек**|Этот счетчик возвращает общее количество хранимых процедур активации, вызываемых мониторами очереди в этом экземпляре за секунду.|  
|**Достигнут предел задач**|Этот счетчик возвращает общее число раз, когда монитор очереди должен был запустить новую задачу, но не сделал этого, так как уже выполнялось максимальное число задач для очереди.|  
|**Достигнут предел задач/сек**|Этот счетчик сообщает, сколько раз в секунду монитор очереди должен был запустить новую задачу, но не сделал этого, так как уже выполнялось максимальное число задач для очереди.|  
|**Прервано задач/сек**|Этот счетчик возвращает число задач хранимых процедур активации, завершившихся с ошибкой, либо тех, которые были прерваны монитором очереди из-за невозможности получать сообщения.|  
|**Задач работает**|Этот счетчик возвращает число хранимых процедур активации, работающих в настоящий момент.|  
|**Задач запущено/сек**|Этот счетчик возвращает число хранимых процедур активации, запущенных за секунду всеми мониторами очереди в этом экземпляре.|  
  
## <a name="see-also"></a>См. также  
 [sys.dm_broker_activated_tasks (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-activated-tasks-transact-sql)   
 [sys.dm_broker_queue_monitors (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-queue-monitors-transact-sql)   
 [Наблюдение за использованием ресурсов (системный монитор)](monitor-resource-usage-system-monitor.md)  
  
  
