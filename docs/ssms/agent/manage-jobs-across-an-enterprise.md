---
title: Управление заданиями в масштабе предприятия | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.component: ssms-agent
ms.reviewer: ''
ms.suite: sql
ms.technology: ssms
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- multiserver job management [SQL Server]
- jobs [SQL Server Agent], modifying
- modifying jobs
- SQL Server Agent jobs, modifying
- target servers [SQL Server], job changes
ms.assetid: 4fe7f6c6-f89b-4430-979c-4994a5dcf7a6
caps.latest.revision: 5
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: = azuresqldb-mi-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: e719267e0d774ce04e0c42049f5d9b16a4e9a479
ms.sourcegitcommit: 79d4dc820767f7836720ce26a61097ba5a5f23f2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/16/2018
ms.locfileid: "42774609"
---
# <a name="manage-jobs-across-an-enterprise"></a>Управление заданиями в масштабе предприятия
[!INCLUDE[appliesto-ss-asdbmi-xxxx-xxx-md](../../includes/appliesto-ss-asdbmi-xxxx-xxx-md.md)]

> [!IMPORTANT]  
> Сейчас в [управляемом экземпляре базы данных SQL Azure](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance) поддерживается большинство функций агента SQL Server (но не все). Подробные сведения см. в статье [Различия T-SQL между управляемым экземпляром базы данных SQL Azure и SQL Server](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent).

При внесении изменений в определения многосерверных задач вне среды [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] необходимо поместить их в список скачивания, чтобы целевые серверы могли скачать обновленную задачу. Чтобы убедиться в том, что целевые серверы получили текущие определения заданий, после обновления многосерверной задачи разместите инструкцию INSERT следующим образом:  
  
```  
EXECUTE sp_post_msx_operation 'INSERT', 'JOB', '<job id>'  
```  
  
Чтобы уведомить целевой сервер об изменении многосерверной задачи, необходимо выполнить указанную выше команду после использования одной из этих процедур:  
  
-   [sp_add_jobstep (Transact-SQL)](http://msdn.microsoft.com/97900032-523d-49d6-9865-2734fba1c755)  
  
-   [sp_update_jobstep (Transact-SQL)](http://msdn.microsoft.com/e158802c-c347-4a5d-bf75-c03e5ae56e6b)  
  
-   [sp_delete_jobstep (Transact-SQL)](http://msdn.microsoft.com/421ede8e-ad57-474a-9fb9-92f70a3e77e3)  
  
-   [Управление событиями](../../relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql.md)  
  
-   [sp_detach_schedule (Transact-SQL)](http://msdn.microsoft.com/9a1fc335-1bef-4638-a33a-771c54a5dd19)  
  
    > [!NOTE]  
    > Необязательно вызывать процедуру **sp_post_msx_operation** после вызова **sp_update_job** или **sp_delete_job**, поскольку эти хранимые процедуры автоматически размещают необходимые изменения в списке скачивания.  
  
Типичные задачи для управления задачами в масштабах предприятия:  
  
**Проверка состояния целевого сервера**  
  
-   [Transact-SQL](http://msdn.microsoft.com/f841d3bd-901a-4980-ad0b-1c6eeba3f717)  
  
-   [Управляющие объекты SQL Server (SMO)](http://msdn.microsoft.com/4cde2b85-2a31-4cac-8d16-7a4196066193)  
  
**Изменение целевого сервера для задания**  
  
-   [Среда SQL Server Management Studio](../../ssms/agent/modify-the-target-servers-for-a-job.md)  
  
-   [Transact-SQL](http://msdn.microsoft.com/485252cc-0081-490a-9bd1-cbbd68eea286)  
  
-   [Управляющие объекты SQL Server (SMO)](http://msdn.microsoft.com/4cde2b85-2a31-4cac-8d16-7a4196066193)  
  
**Изменение местоположения целевого сервера**  
  
-   [Среда SQL Server Management Studio](../../ssms/agent/specify-a-target-server-s-location-sql-server-management-studio.md)  
  
-   [Transact-SQL](http://msdn.microsoft.com/ceb3b2bc-0cc4-48d8-9bdc-6a809556e35f)  
  
-   [Управляющие объекты SQL Server (SMO)](http://msdn.microsoft.com/4cde2b85-2a31-4cac-8d16-7a4196066193)  
  
**Синхронизация часов целевых серверов**  
  
-   [Среда SQL Server Management Studio](../../ssms/agent/synchronize-target-server-clocks-sql-server-management-studio.md)  
  
-   [Transact-SQL](http://msdn.microsoft.com/40e44df7-d3e3-44ee-b149-08aba629a21f)  
  
**Принудительный опрос главного сервера целевым сервером**  
  
-   [Среда SQL Server Management Studio](../../ssms/agent/force-a-target-server-to-poll-the-master-server.md)  
  
-   [Transact-SQL](http://msdn.microsoft.com/085deef8-2709-4da9-bb97-9ab32effdacf)  
  
## <a name="see-also"></a>См. также:  
[Управление событиями](../../ssms/agent/manage-events.md)  
  
