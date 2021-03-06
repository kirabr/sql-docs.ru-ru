---
title: DROP EXTERNAL RESOURCE POOL (Transact-SQL) | Документы Майкрософт
ms.custom: ''
ms.date: 03/17/2016
ms.prod: sql
ms.prod_service: sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- DROP EXTERNAL RESOURCE POOL
- DROP_EXTERNAL_RESOURCE_POOL_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- DROP EXTERNAL RESOURCE POOL statement
ms.assetid: e2fa01bd-96ff-4ea9-bb08-6cb6b6adf68c
caps.latest.revision: 6
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: 0dbab88c740ed7b1f1e202bd3ad5e97b8bd8cd05
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38057918"
---
# <a name="drop-external-resource-pool-transact-sql"></a>DROP EXTERNAL RESOURCE POOL (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  Удаляет внешний пул ресурсов Resource Governor, используемый для определения ресурсов для внешних процессов. Для служб R внешний пул управляет `rterm.exe`, `BxlServer.exe` и другими сформированными процессами. Внешние пулы ресурсов создаются с помощью [CREATE EXTERNAL RESOURCE POOL (Transact-SQL) ](../../t-sql/statements/create-external-resource-pool-transact-sql.md) и изменяются с помощью [ALTER EXTERNAL RESOURCE POOL (Transact-SQL)](../../t-sql/statements/alter-external-resource-pool-transact-sql.md).  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
DROP EXTERNAL RESOURCE POOL pool_name  
```  
  
## <a name="arguments"></a>Аргументы  
 *pool_name*  
 Имя удаляемого внешнего пула ресурсов.  
  
## <a name="remarks"></a>Примечания  
 Нельзя удалить пул внешний ресурсов, если он содержит группы рабочей нагрузки.  
  
 Нельзя удалить внутренний пул или пул по умолчанию Resource Governor.  
  
 Перенастройка  
  
 При выполнении инструкций DDL рекомендуется иметь представление о состояниях регулятора ресурсов. Дополнительные сведения см. в разделе [Resource Governor](../../relational-databases/resource-governor/resource-governor.md) (Регулятор ресурсов).  
  
## <a name="permissions"></a>Разрешения  
 Требуется разрешение `CONTROL SERVER`.  
  
## <a name="examples"></a>Примеры  
 В следующем примере удаляется внешний пул ресурсов с именем `ex_pool`.  
  
```  
DROP EXTERNAL RESOURCE POOL ex_pool;  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a>См. также  
 [Параметр конфигурации сервера external scripts enabled](../../database-engine/configure-windows/external-scripts-enabled-server-configuration-option.md)   
 [Службы R SQL Server](../../advanced-analytics/r-services/sql-server-r-services.md)   
 [Известные проблемы со службами R SQL Server](../../advanced-analytics/r-services/known-issues-for-sql-server-r-services.md)   
 [CREATE EXTERNAL RESOURCE POOL (Transact-SQL)](../../t-sql/statements/create-external-resource-pool-transact-sql.md)   
 [ALTER EXTERNAL RESOURCE POOL (Transact-SQL)](../../t-sql/statements/alter-external-resource-pool-transact-sql.md)   
 [DROP WORKLOAD GROUP (Transact-SQL)](../../t-sql/statements/drop-workload-group-transact-sql.md)   
 [DROP RESOURCE POOL (Transact-SQL)](../../t-sql/statements/drop-resource-pool-transact-sql.md)  
  
  
