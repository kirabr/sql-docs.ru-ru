---
title: sp_stop_job (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 08/01/2016
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_stop_job_TSQL
- sp_stop_job
dev_langs:
- TSQL
helpviewer_keywords:
- sp_stop_job
ms.assetid: 64b4cc75-99a0-421e-b418-94e37595bbb0
caps.latest.revision: 38
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 0e057b6c0178ca87803aede7d83c2054aac852f2
ms.sourcegitcommit: 79d4dc820767f7836720ce26a61097ba5a5f23f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/16/2018
ms.locfileid: "40394359"
---
# <a name="spstopjob-transact-sql"></a>sp_stop_job (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Дает указание агенту [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] остановить выполнение текущего задания.  

  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_stop_job   
      [@job_name =] 'job_name'  
    | [@job_id =] job_id   
    | [@originating_server =] 'master_server'  
    | [@server_name =] 'target_server'  
```  
  
## <a name="arguments"></a>Аргументы  
 [  **@job_name =**] **"***имя_задания***"**  
 Имя останавливаемого задания. *имя_задания* — **sysname**, значение по умолчанию NULL.  
  
 [  **@job_id =**] *job_id*  
 Идентификационный номер останавливаемого задания. *job_id* — **uniqueidentifier**, значение по умолчанию NULL.  
  
 [ **@originating_server =**] **'***master_server***'**  
 Имя главного сервера. Если указано, останавливаются все многосерверные задания. *master_server* — **nvarchar(128)**, значение по умолчанию NULL. Указывайте этот параметр только при вызове **sp_stop_job** на целевой сервер.  
  
> [!NOTE]  
>  Может быть задан только один из первых трех аргументов.  
  
 [ **@server_name =**] **'***target_server***'**  
 Имя конкретного целевого сервера, на котором следует остановить многосерверное задание. *target_server* — **nvarchar(128)**, значение по умолчанию NULL. Указывайте этот параметр только при вызове **sp_stop_job** на главном сервере для многосерверного задания.  
  
## <a name="return-code-values"></a>Значения кода возврата  
 **0** (успешное завершение) или **1** (неуспешное завершение)  
  
## <a name="result-sets"></a>Результирующие наборы  
 None  
  
## <a name="remarks"></a>Примечания  
 **sp_stop_job** отправляет сигнал об остановке в базу данных. Можно немедленно остановить некоторые процессы и некоторые должен достичь стабильный точки (или точку входа для пути кода), прежде чем их можно остановить. Для завершения некоторых длительных инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)], таких как BACKUP, RESTORE, и некоторых команд DBCC может потребоваться много времени. Если эти приложения работают, может занять некоторое время, прежде чем задание будет отменено. Остановка задания приведет к регистрации записи «Задание отменено» в журнале заданий.  
  
 Если задание в данный момент выполняет этап типа **CmdExec** или **PowerShell**, выполняемый процесс (например MyProgram.exe) принудительно завершается раньше времени. Преждевременное завершение может привести к непредсказуемому поведению, например файлы, используемые процессом, могут остаться открытыми. Следовательно **sp_stop_job** следует использовать только в экстренных ситуациях, если задание содержит шаги типа **CmdExec** или **PowerShell**.  
  
## <a name="permissions"></a>Разрешения  
 По умолчанию эту хранимую процедуру могут выполнять только члены предопределенной роли сервера **sysadmin** . Другим пользователям должна быть предоставлена одна из следующих предопределенных ролей базы данных агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в базе данных **msdb** :  
  
-   **SQLAgentUserRole**  
  
-   **SQLAgentReaderRole**  
  
-   **SQLAgentOperatorRole**  
  
 Дополнительные сведения о разрешениях этих ролей см. в разделе [Предопределенные роли базы данных агента SQL Server](../../ssms/agent/sql-server-agent-fixed-database-roles.md).  
  
 Членами **SQLAgentUserRole** и **SQLAgentReaderRole** могут останавливать задания, которыми они владеют. Членами **SQLAgentOperatorRole** можно останавливать все локальные задания, включая те, которыми владеют другие пользователи. Членами **sysadmin** могут останавливать все локальные и многосерверные задания.  
  
## <a name="examples"></a>Примеры  
 В следующем примере останавливается задание с именем `Weekly Sales Data Backup`.  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_stop_job  
    N'Weekly Sales Data Backup' ;  
GO  
```  
  
## <a name="see-also"></a>См. также  
 [sp_delete_job &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-delete-job-transact-sql.md)   
 [sp_help_job &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-help-job-transact-sql.md)   
 [sp_start_job &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-start-job-transact-sql.md)   
 [sp_update_job &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-update-job-transact-sql.md)   
 [Системные хранимые процедуры (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
