---
title: MSSQL_ENG014144 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014144 error
ms.assetid: fdc744d5-530e-48c4-9420-cca032fd482b
caps.latest.revision: 11
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 49be2d02192109607ace90021bfd8901817091ff
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37217044"
---
# <a name="mssqleng014144"></a>MSSQL_ENG014144
    
## <a name="message-details"></a>Сведения о сообщении  
  
|||  
|-|-|  
|Название продукта|SQL Server|  
|Идентификатор события|14144|  
|Источник события|MSSQLSERVER|  
|Компонент|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|Символическое имя||  
|Текст сообщения|Невозможно удалить подписчик '%s'. В базе данных публикации '%s' для него есть подписки.|  
  
## <a name="explanation"></a>Объяснение  
 Экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , настроенный в качестве подписчика, не может быть удален из роли подписчика до тех пор, пока есть активные подписки, настроенные для данного экземпляра.  
  
## <a name="user-action"></a>Действие пользователя  
 Удалите все связанные подписки, прежде чем пытаться изменить состояние подписчика для экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
1.  Выполните [sp_helpsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) в базе данных публикации в издателе, чтобы найти подписки.  
  
2.  Выполните [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql) в базе данных публикации в издателе, чтобы удалить подписки.  
  
## <a name="see-also"></a>См. также  
 [Справочник по ошибкам и событиям (репликация)](errors-and-events-reference-replication.md)   
 [Подписка на публикации](subscribe-to-publications.md)  
  
  
