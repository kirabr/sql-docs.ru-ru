---
title: Обнаружение и разрешение конфликтов репликации слиянием | Документация Майкрософт
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
- merge replication conflict resolution [SQL Server replication], about conflict resolution
- default conflict resolver
- conflict resolution [SQL Server replication]
- viewing merge replication conflicts
- resolving merge replication conflicts
- articles [SQL Server replication], conflict resolution
- merge replication conflict resolution [SQL Server replication]
- conflict resolution [SQL Server replication], merge replication
ms.assetid: 0d033c76-e8c9-4e35-ab95-4d335abb18c1
caps.latest.revision: 37
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 86c1c4b3c9aa50abaffb242e750986ff75c6933c
ms.sourcegitcommit: 022d67cfbc4fdadaa65b499aa7a6a8a942bc502d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2018
ms.locfileid: "37358806"
---
# <a name="advanced-merge-replication---resolve-merge-replication-conflicts"></a>Расширенная репликация слиянием: разрешение конфликтов
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Когда издатель и подписчик соединяются и происходит синхронизация, агент слияния проверяет наличие конфликтов. При обнаружении конфликтов агент слияния использует сопоставитель конфликтов для определения данных, которые будут приняты и распространены на другие сайты.  
  
> [!NOTE]  
>  Несмотря на то, что подписчик обычно синхронизируется с издателем, конфликты возникают между обновлениями, осуществляемыми у различных подписчиков, а не между обновлениями, осуществляемыми у подписчика и издателя.  
  
 Репликация слиянием предлагает множество методов для обнаружения и разрешения конфликтов. Для большинства приложений подходит метод по умолчанию:  
  
-   Если конфликт возникает между издателем и подписчиком, принимается изменение издателя, а изменение подписчика отклоняется.  
  
-   Если конфликт происходит между двумя подписчиками, использующими клиентские подписки (тип подписок по запросу, используемых по умолчанию), принимается изменение первого подписчика для синхронизации с издателем, а изменение второго подписчика отклоняется. Сведения об указании клиентских и серверных подписок см. в статье [Указание типа подписки на публикацию слиянием и приоритета разрешения конфликтов (SQL Server Management Studio)](../../../relational-databases/replication/specify-a-merge-subscription-type-and-conflict-resolution-priority.md).  
  
-   Если конфликт возникает между двумя подписчиками, использующими серверные подписки (тип принудительных подписок по умолчанию), принимается изменение подписчика с наибольшим значением приоритета, а изменение второго подписчика отклоняется. Если значения приоритетов равны, принимается изменение первого подписчика для синхронизации с издателем.  
  
 Дополнительные сведения об обнаружении и разрешении конфликтов репликации слиянием см. в разделе [Advanced Merge Replication Conflict Detection and Resolution](../../../relational-databases/replication/merge/advanced-merge-replication-conflict-detection-and-resolution.md).  
  
## <a name="see-also"></a>См. также:  
 [Параметры статьи для репликации слиянием](../../../relational-databases/replication/merge/article-options-for-merge-replication.md)   
 [Подписка на публикации](../../../relational-databases/replication/subscribe-to-publications.md)  
  
  
