---
title: Класс событий Broker:Remote Message Ack | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Broker:Remote Message Ack event class
ms.assetid: 3d67efe1-74b4-4633-b029-c6e05b19f4dc
caps.latest.revision: 29
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 6193e937af7e678fdc69f674b263c02a37ee7f55
ms.sourcegitcommit: 4183dc18999ad243c40c907ce736f0b7b7f98235
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "43078136"
---
# <a name="brokerremote-message-ack-event-class"></a>Broker:Remote Message Ack, класс событий
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] формирует событие **Broker:Remote Message Ack** , когда компонент [!INCLUDE[ssSB](../../includes/sssb-md.md)] отправляет или получает подтверждение сообщения.  
  
## <a name="brokerremote-message-ack-event-class-data-columns"></a>Столбцы данных класса событий Broker:Remote Message Ack  
  
|Столбец данных|Тип|Описание|Номер столбца|Фильтруемый|  
|-----------------|----------|-----------------|-------------------|----------------|  
|**ApplicationName**|**nvarchar**|Имя клиентского приложения, установившего соединение с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Этот столбец заполняется значениями, передаваемыми приложением, а не отображаемым именем программы.|10|Да|  
|**BigintData1**|**bigint**|Последовательный номер сообщения, содержащего подтверждение.|52|нет|  
|**BigintData2**|**bigint**|Последовательный номер подтверждаемого сообщения.|53|нет|  
|**ClientProcessID**|**int**|Идентификатор, присвоенный компьютером сервера процессу, в котором работает клиентское приложение. Этот столбец данных заполняется в том случае, если клиент вводит идентификатор клиентского процесса.|9|Да|  
|**DatabaseID**|**int**|Идентификатор базы данных, указанный в инструкции USE *database* . Если инструкция USE *database* не выполнялась для этого экземпляра, тогда это идентификатор базы данных по умолчанию. [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] отображает имя базы данных, если столбец данных **ServerName** захвачен при трассировке и сервер доступен. Определите значение для базы данных, используя функцию DB_ID.|3|Да|  
|**EventClass**|**int**|Тип захваченного класса событий. Всегда **149** или **Broker:Message Ack**.|27|нет|  
|**EventSequence**|**int**|Порядковый номер этого события.|51|нет|  
|**EventSubClass**|**nvarchar**|Тип подкласса события, предоставляющий дополнительные сведения о каждом классе событий. Этот столбец может содержать следующие значения.<br /><br /> **Message With Acknowledgement Sent**:<br />                    [!INCLUDE[ssSB](../../includes/sssb-md.md)] отправил подтверждение как часть обычного последовательного сообщения.<br /><br /> **Acknowledgement Sent**:<br />                    [!INCLUDE[ssSB](../../includes/sssb-md.md)] отправил подтверждение вне обычного последовательного сообщения.<br /><br /> **Message With Acknowledgement Received**:<br />                  [!INCLUDE[ssSB](../../includes/sssb-md.md)] получил подтверждение как часть обычного последовательного сообщения.<br /><br /> **Acknowledgement Received**:<br />                  [!INCLUDE[ssSB](../../includes/sssb-md.md)] получил подтверждение вне обычного последовательного сообщения.|21|Да|  
|**GUID**|**uniqueidentifier**|Идентификатор диалога. Этот идентификатор передается в составе сообщения и является общим для обоих участников диалога.|54|нет|  
|**HonorBrokerPriority**|**Int**|Текущее значение параметра базы данных HONOR_BROKER_PRIORITY: 0 — отключено, 1 — включено.|32|Да|  
|**HostName**|**nvarchar**|Имя компьютера, на котором выполняется клиентская программа. Заполнение этого столбца данных производится в том случае, если клиент предоставляет имя узла. Чтобы определить имя узла, используйте функцию HOST_NAME.|8|Да|  
|**IntegerData**|**int**|Номер фрагмента сообщения, содержащего подтверждение.|25|нет|  
|**IntegerData2**|**int**|Номер фрагмента подтверждаемого сообщения.|55|нет|  
|**IsSystem**|**int**|Указывает, произошло событие в системном или в пользовательском процессе.<br /><br /> 0 = пользовательский процесс<br /><br /> 1 = системный процесс|60|нет|  
|**LoginSid**|**image**|Идентификатор безопасности вошедшего в систему пользователя. Значение идентификатора безопасности уникально для каждого имени входа на сервере.|41|Да|  
|**NTDomainName**|**nvarchar**|Домен Windows, к которому принадлежит пользователь.|7|Да|  
|**NTUserName**|**nvarchar**|Имя пользователя, которому принадлежит соединение, создавшее это событие.|6|Да|  
|**Приоритет**|**int**|Уровень приоритета диалога.|5|Да|  
|**RoleName**|**nvarchar**|Роль экземпляра, подтвердившего сообщение. Это либо **initiator** , либо **target**.|38|нет|  
|**ServerName**|**nvarchar**|Имя отслеживаемого экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .|26|нет|  
|**SPID**|**int**|Идентификатор процесса сервера, который [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] присвоил процессу, связанному с клиентом.|12|Да|  
|**StartTime**|**datetime**|Время начала события, если доступно.|14|Да|  
|**StarvationElevation**|**int**|Сообщение было отправлено с более высоким приоритетом, чем приоритет, настроенный для диалога: 0 — нет, 1 — да.|33|Да|  
|**TransactionID**|**bigint**|Назначенный системой идентификатор транзакции.|4|нет|  
  
  
