---
title: процедура sp_showpendingchanges (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/04/2017
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
- sp_showpendingchanges
- sp_showpendingchanges_TSQL
helpviewer_keywords:
- sp_showpendingchanges
ms.assetid: 8013a792-639d-4550-b262-e65d30f9d291
caps.latest.revision: 17
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 229136548d40e985869bd1f01685cb0c3dad6f4f
ms.sourcegitcommit: 182b8f68bfb345e9e69547b6d507840ec8ddfd8b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "43030705"
---
# <a name="spshowpendingchanges-transact-sql"></a>sp_showpendingchanges (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Возвращает результирующий набор, который показывает изменения, ожидающие репликации. Эта хранимая процедура выполняется на издателе в базе данных публикации и на подписчике в базе данных подписки.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
> [!NOTE]  
>  Эта процедура предоставляет приблизительное число изменений и строк, затронутых этими изменениями. Например, процедура получает сведения из издателя или подписчика, но не из обоих одновременно. Данные, которые хранятся в другом узле, могут привести к меньшему набору измерений для синхронизации, чем было рассчитано процедурой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_showpendingchanges [ [ @destination_server = ] 'destination_server' ]  
    [ , [ @publication = ] 'publication' ]  
    [ , [ @article = ] 'article']  
    [ , [ @show_rows = ] show_rows]  
```  
  
## <a name="arguments"></a>Аргументы  
 [ @destination_server **=** ] **"***destination_server***"**  
 Имя сервера, на котором применяются реплицированные изменения. *destination_server* — **sysname**, значение по умолчанию NULL.  
  
 [ @publication **=** ] **"***публикации***"**  
 Имя публикации. *Публикация* — **sysname**, со значением по умолчанию NULL. Когда *публикации* указан, результаты ограничены только указанной публикацией.  
  
 [ @article **=** ] **"***статье***"**  
 Имя статьи. *статья* — **sysname**, со значением по умолчанию NULL. Когда *статье* указан, результаты ограничены только указанной статьи.  
  
 [ @show_rows **=** ] *show_rows*  
 Указывает, содержит ли результирующий набор более конкретные сведения об ожидающих изменениях со значением по умолчанию **0**. Если значение **1** задан, результирующий набор содержит столбцы is_delete и rowguid.  
  
## <a name="result-set"></a>Результирующий набор  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|destination_server|**sysname**|Имя сервера, на который реплицируются изменения.|  
|pub_name|**sysname**|Имя публикации.|  
|destination_db_name|**sysname**|Название базы данных, к которой реплицируются изменения.|  
|is_dest_subscriber|**bit**|Свидетельствует об изменениях, реплицируемых на подписчика. Значение **1** указывает, что изменения реплицируются на подписчик. **0** означает, что изменения реплицируются на издатель.|  
|article_name|**sysname**|Название статьи для таблицы, где были произведены изменения.|  
|pending_deletes|**int**|Число удалений, ожидающих репликации.|  
|pending_ins_and_upd|**int**|Число вставок и обновлений, ожидающих репликации.|  
|is_delete|**bit**|Указывает, является ли ожидающее изменение удалением. Значение **1** указывает, что изменение является удалением. Должно быть задано значение **1** для @show_rows.|  
|rowguid|**uniqueidentifier**|Идентификатор GUID, который определяет измененную строку. Должно быть задано значение **1** для @show_rows.|  
  
## <a name="return-code-values"></a>Значения кода возврата  
 **0** (успешное завершение) или **1** (неуспешное завершение)  
  
## <a name="remarks"></a>Примечания  
 Процедура sp_showpendingchanges используется при репликации слиянием.  
  
 Процедура sp_showpendingchanges используется при диагностике и устранении неполадок в репликации слиянием.  
  
 Результат выполнения процедуры sp_showpendingchanges не включает строки в поколении 0.  
  
 Если статья, указанная для *статье* не принадлежит к публикации, указанной в *публикации* возвращаются счетчик 0 для pending_deletes и pending_ins_and_upd.  
  
## <a name="permissions"></a>Разрешения  
 Только члены предопределенной роли сервера sysadmin или предопределенной роли базы данных db_owner могут выполнять процедуру sp_showpendingchanges.  
  
## <a name="see-also"></a>См. также  
 [Хранимые процедуры репликации (Transact-SQL)](../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md)  
  
  
