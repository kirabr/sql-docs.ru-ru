---
title: sp_dropdistributor (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- sp_dropdistributor
- sp_dropdistributor_TSQL
helpviewer_keywords:
- sp_dropdistributor
ms.assetid: 0644032f-5ff0-4718-8dde-321bc9967a03
caps.latest.revision: 33
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: e321b5e5976192146f9cd8d993304d5f5ae55e67
ms.sourcegitcommit: 182b8f68bfb345e9e69547b6d507840ec8ddfd8b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "43029064"
---
# <a name="spdropdistributor-transact-sql"></a>sp_dropdistributor (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Удаляет распространитель. Эта хранимая процедура выполняется на распространителе в любой базе данных, за исключением базы данных распространителя.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_dropdistributor [ [ @no_checks= ] no_checks ]   
    [ , [ @ignore_distributor= ] ignore_distributor ]  
```  
  
## <a name="arguments"></a>Аргументы  
 [  **@no_checks=**] *no_checks*  
 Показывает, нужно ли проверять зависимые объекты перед удалением распространителя. *no_checks* — **бит**, значение по умолчанию 0.  
  
 Если **0**, **sp_dropdistributor** проверок, чтобы убедиться в том, что все объекты публикации и распространения вместе с распространителем, был удален.  
  
 Если **1**, **sp_dropdistributor** удаляет все объекты публикации и распространения перед удалением распространителя.  
  
 [  **@ignore_distributor=**] *ignore_distributor*  
 Указывает, исполняется ли данная хранимая процедура без подключения к распространителю. *ignore_distributor* — **бит**, значение по умолчанию **0**.  
  
 Если **0**, **sp_dropdistributor** подключается к распространителю и удаляет все объекты репликации. Если **sp_dropdistributor** не удалось соединиться с распространителем, хранимая процедура завершается ошибкой.  
  
 Если **1**, не подключается к распространителю и объекты репликации не удаляются. Этот вариант используется при удалении распространителя или если он постоянно работает в режиме «вне сети». Объекты издателя на распространителе не удаляются до тех пор, пока распространитель не будет переустановлен.  
  
## <a name="return-code-values"></a>Значения кода возврата  
 **0** (успешное завершение) или **1** (неуспешное завершение)  
  
## <a name="remarks"></a>Примечания  
 **sp_dropdistributor** используется во всех типах репликации.  
  
 Если других объектов издателя или распространения существует на сервере, **sp_dropdistributor** завершается ошибкой, если **@no_checks** присваивается **1**.  
  
 Эта хранимая процедура должна выполняться после удаления базы данных распространителя, выполнив **sp_dropdistributiondb**.  
  
## <a name="example"></a>Пример  
 [!code-sql[HowTo#sp_DropDistPub](../../relational-databases/replication/codesnippet/tsql/sp-dropdistributor-trans_1.sql)]  
  
## <a name="permissions"></a>Разрешения  
 Только члены **sysadmin** предопределенной роли сервера могут выполнять процедуру **sp_dropdistributor**.  
  
## <a name="see-also"></a>См. также  
 [Disable Publishing and Distribution](../../relational-databases/replication/disable-publishing-and-distribution.md)  (Отключение публикации и распространения)  
 [sp_adddistributor &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-adddistributor-transact-sql.md)   
 [sp_changedistributor_property &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-changedistributor-property-transact-sql.md)   
 [sp_helpdistributor (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-helpdistributor-transact-sql.md)   
 [Хранимые процедуры репликации (Transact-SQL)](../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md)  
  
  
