---
title: sp_help_log_shipping_primary_secondary (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_help_log_shipping_primary_secondary
- sp_help_log_shipping_primary_secondary_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_help_log_shipping_primary_secondary
ms.assetid: bc0044b4-7831-4ff9-8856-825c76aa9893
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 43880bb1fac1de9fb9d8657f5fcc143cf96645f3
ms.sourcegitcommit: 182b8f68bfb345e9e69547b6d507840ec8ddfd8b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "43022164"
---
# <a name="sphelplogshippingprimarysecondary-transact-sql"></a>sp_help_log_shipping_primary_secondary (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Эта хранимая процедура возвращает сведения обо всех базах данных-получателях для данной базы данных-источника.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_help_log_shipping_primary_secondary  
[ @primary_database = ] 'primary_database'  
```  
  
## <a name="arguments"></a>Аргументы  
 [  **@primary_database =** ] "*primary_database*"  
 Имя базы данных на сервере-источнике. *primary_database* — **sysname**, не имеет значения по умолчанию.  
  
## <a name="return-code-values"></a>Значения кода возврата  
 0 (успешное завершение) или 1 (неуспешное завершение)  
  
## <a name="result-sets"></a>Результирующие наборы  
  
|Имя столбца|Описание|  
|-----------------|-----------------|  
|**secondary_server**|Имя экземпляра-получателя из [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] в конфигурации доставки журналов.|  
|**secondary_database**|Имя базы данных-получателя в конфигурации доставки журналов.|  
  
## <a name="remarks"></a>Примечания  
 **sp_help_log_shipping_primary_secondary** должна запускаться из **master** базы данных на сервере-источнике.  
  
## <a name="permissions"></a>Разрешения  
 Только члены **sysadmin** предопределенной роли сервера могут выполнять эту процедуру.  
  
## <a name="examples"></a>Примеры  
 Этот пример иллюстрирует использование **sp_help_log_shipping_primary_secondary** для получения списка базы данных-получателя баз данных, связанных с основной базой данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].  
  
```  
EXECUTE master.dbo.sp_help_log_shipping_primary_secondary @primary_database=N'AdventureWorks';  
GO  
```  
  
## <a name="see-also"></a>См. также  
 [О доставке журналов &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md)   
 [Системные хранимые процедуры (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
