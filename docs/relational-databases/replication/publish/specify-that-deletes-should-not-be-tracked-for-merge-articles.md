---
title: Отключение отслеживания операций удаления для статей публикации слиянием | Документация Майкрософт
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
dev_langs:
- TSQL
helpviewer_keywords:
- conditional delete tracking [SQL Server replication]
- merge replication [SQL Server replication], conditional delete tracking
ms.assetid: 0fe330ca-5fb5-422e-ad6f-92fb5d6a3b6c
caps.latest.revision: 34
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 3a81e51c99540d8cc174341610a2163bf2aaf428
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "37968636"
---
# <a name="specify-that-deletes-should-not-be-tracked-for-merge-articles"></a>Отключение отслеживания операций удаления для статей публикации слиянием
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
 По умолчанию репликация слиянием производит синхронизацию команд DELETE между издателем и подписчиком. Репликация слиянием позволяет извлекать строки из базы данных подписки даже в том случае, если они были удалены из публикации (и наоборот). При создании новой статьи можно отключить выполнение команд DELETE программным путем, либо сделать это позже с помощью хранимых процедур репликации.  
  
> [!IMPORTANT]  
>  Включение этой функции приведет к потере конвергенции, то есть возникнет несоответствие данных, содержащихся на подписчике и на издателе. Потребуется реализация собственного механизма очистки удаленных строк.  
  
### <a name="to-specify-that-deletes-be-ignored-for-a-new-merge-article"></a>Отключение обработки команд удаления для новой статьи слияния  
  
1.  В базе данных публикации на издателе выполните процедуру [sp_addmergearticle (Transact-SQL)](../../../relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql.md). В параметре **@delete_tracking** @delete_tracking **@delete_tracking**). Дополнительные сведения см. в статье [определить статью](../../../relational-databases/replication/publish/define-an-article.md).  
  
    > [!NOTE]  
    >  Если исходная таблица для статьи уже опубликована в другой публикации, значение **delete_tracking** должно быть одинаковым для обеих статей.  
  
### <a name="to-specify-that-deletes-be-ignored-for-an-existing-merge-article"></a>Отключение обработки команд удаления для существующих статей слияния  
  
1.  Чтобы определить, включена ли компенсация ошибок для статьи, выполните хранимую процедуру [sp_helpmergearticle &#40;Transact-SQL&#41;](../../../relational-databases/system-stored-procedures/sp-helpmergearticle-transact-sql.md) и в полученных результатах проверьте значение параметра **delete_tracking**. Если это значение равно **0**, то команды удаления уже не обрабатываются.  
  
2.  Если на шаге 1 получено значение [1](../../../relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql.md), в базе данных публикации на издателе выполните процедуру **sp_changemergearticle &#1;Transact-SQL&#1;**. В параметре **delete_tracking** @delete_tracking **@property**, а в параметре **@delete_tracking** @delete_tracking **@value**).  
  
    > [!NOTE]  
    >  Если исходная таблица для статьи уже опубликована в другой публикации, значение **delete_tracking** должно быть одинаковым для обеих статей.  
  
## <a name="see-also"></a>См. также:  
 [Оптимизация производительности репликации слиянием с помощью отслеживания условного удаления](../../../relational-databases/replication/merge/optimize-merge-replication-performance-with-conditional-delete-tracking.md)  
  
  
