---
title: Параметры моментального снимка | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: replication
ms.reviewer: ''
ms.suite: sql
ms.technology: replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- snapshot replication [SQL Server], options
- snapshots [SQL Server replication], options
ms.assetid: 759fab42-66c7-4541-a7a3-bb6fb868493c
caps.latest.revision: 28
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: c658f7898af62407a2c5458951aa14263ab94e7b
ms.sourcegitcommit: 022d67cfbc4fdadaa65b499aa7a6a8a942bc502d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2018
ms.locfileid: "37353106"
---
# <a name="snapshot-options"></a>Параметры моментального снимка
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  При инициализации подписки с помощью моментального снимка можно выполнить следующие действия:  
  
-   Указать другое расположение папки моментальных снимков вместо папки по умолчанию или в дополнение к ней. Дополнительные сведения см. в статье [Alternate Snapshot Folder Locations](../../relational-databases/replication/alternate-snapshot-folder-locations.md).  
  
-   Сжать моментальные снимки для хранения на съемном носителе или для передачи по медленной сети. Дополнительные сведения см. в разделе [Compressed Snapshots](../../relational-databases/replication/compressed-snapshots.md).  
  
-   Выполнить скрипты [!INCLUDE[tsql](../../includes/tsql-md.md)] до или после применения моментального снимка. Дополнительные сведения см. в статье [Выполнение скриптов до и после применения моментального снимка](../../relational-databases/replication/execute-scripts-before-and-after-the-snapshot-is-applied.md).  
  
-   Передать файлы моментальных снимков с помощью протокола передачи файлов (FTP). Дополнительные сведения см. в статье [Передача моментальных снимков через FTP](../../relational-databases/replication/transfer-snapshots-through-ftp.md).  
  
## <a name="see-also"></a>См. также:  
 [Инициализация подписки с помощью моментального снимка](../../relational-databases/replication/initialize-a-subscription-with-a-snapshot.md)  
  
  
