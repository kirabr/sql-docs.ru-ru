---
title: sp_enumeratependingschemachanges (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
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
- sp_enumeratependingschemachanges
- sp_enumeratependingschemachanges_TSQL
helpviewer_keywords:
- sp_enumeratependingschemachanges
ms.assetid: df169b21-d10a-41df-b3a1-654cfb58bc21
caps.latest.revision: 23
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: f99b1ae2545c347414f50efde62f97d344d5696c
ms.sourcegitcommit: 182b8f68bfb345e9e69547b6d507840ec8ddfd8b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "43021814"
---
# <a name="spenumeratependingschemachanges-transact-sql"></a>sp_enumeratependingschemachanges (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Возвращает список всех ожидающих изменений схемы. Эта хранимая процедура может использоваться с [sp_markpendingschemachange](../../relational-databases/system-stored-procedures/sp-markpendingschemachange-transact-sql.md), что позволяет администратору пропустить выбранные изменения схемы, ожидающие завершения, чтобы они не реплицируются. Эта хранимая процедура выполняется на издателе в базе данных публикации.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_enumeratependingschemachanges [ @publication = ] 'publication'   
    [ , [ @starting_schemaversion = ] starting_schemaversion ]  
```  
  
## <a name="arguments"></a>Аргументы  
 [  **@publication=** ] **"***публикации***"**  
 Имя публикации. *Публикация* — **sysname**, не имеет значения по умолчанию.  
  
 [  **@starting_schemaversion=** ] *starting_schemaversion*  
 Минимальное количество изменений схемы для включения в результирующий набор.  
  
## <a name="result-set"></a>Результирующий набор  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**имя_статьи**|**sysname**|Имя статьи, к которому применяется изменение схемы, или **всей публикации** для изменения схемы, которые применяются ко всей публикации.|  
|**schemaversion**|**int**|Количество изменений схемы, ожидающих завершения.|  
|**SchemaType**|**sysname**|Текстовое значение, представляющее тип изменения схемы.|  
|**schematext**|**nvarchar(max)**|Код [!INCLUDE[tsql](../../includes/tsql-md.md)], описывающий изменение схемы.|  
|**schemastatus**|**nvarchar(10)**|Указывает, ожидает ли своего завершения изменение схемы для данной статьи; может иметь следующие значения:<br /><br /> **Active** = изменение схемы находится в состоянии ожидания<br /><br /> **Неактивные** = изменение схемы неактивно<br /><br /> **Пропустить** = изменение схемы не реплицируется.|  
|**schemaguid**|**uniqueidentifier**|Идентифицирует изменение схемы.|  
  
## <a name="return-code-values"></a>Значения кода возврата  
 **0** (успешное завершение) или **1** (неуспешное завершение)  
  
## <a name="remarks"></a>Примечания  
 **sp_enumeratependingschemachanges** используется в репликации слиянием.  
  
 **sp_enumeratependingschemachanges**, которое используется с [sp_markpendingschemachange](../../relational-databases/system-stored-procedures/sp-markpendingschemachange-transact-sql.md), предназначенной для поддержки репликации слиянием и должна использоваться только тогда, когда другие действия по исправлению, такие как Повторная инициализация, не удалось исправить ситуацию.  
  
## <a name="permissions"></a>Разрешения  
 Только члены **sysadmin** предопределенной роли сервера или **db_owner** предопределенной роли базы данных могут выполнять процедуру **sp_enumeratependingschemachanges**.  
  
## <a name="see-also"></a>См. также  
 [Хранимые процедуры репликации (Transact-SQL)](../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md)   
 [sysmergeschemachange &#40;Transact-SQL&#41;](../../relational-databases/system-tables/sysmergeschemachange-transact-sql.md)  
  
  
