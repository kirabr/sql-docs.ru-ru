---
title: Включение инициализации из резервной копии для публикаций транзакций | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: replication
ms.reviewer: ''
ms.suite: sql
ms.technology: replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- manual subscription initialization [SQL Server replication]
- subscriptions [SQL Server replication], initializing
- initializing subscriptions [SQL Server replication], without snapshots
- transactional replication, backup and restore
- backups [SQL Server replication], transactional replication
ms.assetid: 9df00514-aa9d-4ac6-9766-d226c9958175
caps.latest.revision: 30
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: dece6ed02ee7ca19e5eea93bcfdd3b81facea693
ms.sourcegitcommit: 022d67cfbc4fdadaa65b499aa7a6a8a942bc502d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2018
ms.locfileid: "37350306"
---
# <a name="enable-initialization-with-backup-for-transactional-publications"></a>Включение инициализации из резервной копии для публикаций транзакций
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Для инициализации подписки на публикацию транзакций из резервной копии сначала активизируйте публикацию, чтобы разрешить инициализацию из резервной копии, а затем, создавая подписку, укажите сведения о резервной копии:  
  
-   Включите публикацию на странице **Параметры подписки** диалогового окна **Свойства публикации — \<публикация>**. Дополнительные сведения о доступе к этому диалоговому окну см. в разделе [Просмотр и изменение свойств публикации](../../relational-databases/replication/publish/view-and-modify-publication-properties.md).  
  
-   Укажите сведения о резервной копии с помощью хранимой процедуры [sp_addsubscription (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-addsubscription-transact-sql.md). Дополнительные сведения о параметрах **sp_addsubscription** можно найти в статье [Инициализация транзакционной подписки из резервной копии (программирование репликации на языке Transact-SQL)](../../relational-databases/replication/initialize-a-transactional-subscription-from-a-backup.md).  
  
### <a name="to-enable-initialization-with-a-backup"></a>Включение инициализации с помощью резервной копии  
  
1.  На странице **Параметры подписки** диалогового окна **Свойства публикации — \<Публикация>** установите значение **True** для параметра **Разрешать инициализацию из файлов резервных копий**.  
  
## <a name="see-also"></a>См. также:  
 [Инициализация транзакционной подписки без моментального снимка](../../relational-databases/replication/initialize-a-transactional-subscription-without-a-snapshot.md)  
  
  
