---
title: Параметры конфигурации сервера "access check cache" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- access check cache option
ms.assetid: 0a992ea8-3ec6-4a4d-97b5-460ae7326247
caps.latest.revision: 8
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 0024a9d0f9999b372ff50d7144a23490529e472e
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37287900"
---
# <a name="access-check-cache-server-configuration-options"></a>Параметры конфигурации сервера «access check cache»
  При доступе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]к объектам базы данных проверка доступа кэшируется во внутренней структуре, которую называют **кэшем результатов проверки доступа**. Параметры **access check cache quota** и **access check cache bucket count** управляют количеством записей и числом сегментов хэша, которые используются в **кэше результатов проверки доступа**. В редких случаях можно добиться увеличения производительности, изменив эти параметры.  
  
 Значение по умолчанию 0 указывает на то, что этими параметрами управляет [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Майкрософт рекомендует изменять эти параметры только под руководством службы поддержки пользователей Майкрософт.  
  
## <a name="see-also"></a>См. также  
 [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md)   
 [sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
