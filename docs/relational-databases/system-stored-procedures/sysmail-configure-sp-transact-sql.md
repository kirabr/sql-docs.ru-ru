---
title: sysmail_configure_sp (Transact-SQL) | Документы Microsoft
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
- sysmail_configure_sp_TSQL
- sysmail_configure_sp
dev_langs:
- TSQL
helpviewer_keywords:
- sysmail_configure_sp
ms.assetid: 73b33c56-2bff-446a-b495-ae198ad74db1
caps.latest.revision: 46
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: d0121f82f7ec06dabb3958e5f8407daa5979e89e
ms.sourcegitcommit: f1caaa156db2b16e817e0a3884394e7b30fb642f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33259544"
---
# <a name="sysmailconfiguresp-transact-sql"></a>sysmail_configure_sp (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Изменяет настройки конфигурации компонента Database Mail. Параметры конфигурации, указанный с **sysmail_configure_sp** применяются ко всей [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] экземпляра.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sysmail_configure_sp [ [ @parameter_name = ] 'parameter_name' ]  
    [ , [ @parameter_value = ] 'parameter_value' ]  
    [ , [ @description = ] 'description' ]  
```  
  
## <a name="arguments"></a>Аргументы  
 [**@parameter_name** =] **"***parameter_name***"**  
 Имя параметра, которое необходимо изменить.  
  
 [**@parameter_value** =] **"***parameter_value***"**  
 Новое значение параметра.  
  
 [**@description** =] **"***описание***"**  
 Описание параметра.  
  
## <a name="return-code-values"></a>Значения кода возврата  
 **0** (успешное завершение) или **1** (неуспешное завершение)  
  
## <a name="result-sets"></a>Результирующие наборы  
 Нет  
  
## <a name="remarks"></a>Замечания  
 Компонент Database Mail использует следующие параметры:  
  
||||  
|-|-|-|  
|Имя параметра|Описание|Значение по умолчанию|  
|*AccountRetryAttempts*|Число попыток, предпринимаемых процессом внешней почты для отправки сообщения электронной почты с использованием каждой учетной записи в указанном профиле.|**1**|  
|*AccountRetryDelay*|Время ожидания процесса внешней почты между попытками отправить сообщение (в секундах).|**5000**|  
|*DatabaseMailExeMinimumLifeTime*|Минимальное время в секундах, в течение которого остается активным процесс внешней почты. Когда компонент Database Mail рассылает большое количество сообщений, необходимо увеличить это значение, чтобы поддержать этот компонент в активном состоянии и избежать дополнительной нагрузки из-за частых остановок и запусков.|**600**|  
|*DefaultAttachmentEncoding*|Кодировка для вложений электронной почты, используемая по умолчанию.|MIME|  
|*MaxFileSize*|Максимальный размер вложения в байтах.|**1000000**|  
|*ProhibitedExtensions*|Разделенный запятыми список расширений файлов, которые невозможно отправить в виде вложений в сообщение электронной почты.|**exe, dll, vbs, js**|  
|*LoggingLevel*|Укажите, какие сообщения записываются в журнал компонента Database Mail. Одно из следующих цифровых значений:<br /><br /> 1 — Обычный режим. Регистрируются только ошибки.<br /><br /> 2 — Расширенный режим. Регистрируются ошибки, предупреждения и информационные сообщения.<br /><br /> 3 — Подробный режим. Регистрируются ошибки, предупреждения, информационные сообщения, сообщения об успешном выполнении и дополнительные внутренние сообщения. Используйте данный режим для диагностики.|**2**|  
  
 Хранимая процедура **sysmail_configure_sp** в **msdb** базы данных и принадлежит **dbo** схемы. Процедуру следует выполнять с трехкомпонентным именем, если текущая база данных не является **msdb**.  
  
## <a name="permissions"></a>Разрешения  
 Разрешения для этой процедуры по умолчанию членам выполнение **sysadmin** предопределенной роли сервера.  
  
## <a name="examples"></a>Примеры  
 **А. Настройка компонента Database Mail попытки 10 раз каждой учетной записи**  
  
 В следующем примере показана настройка компонента Database Mail на повторение попытки для каждой учетной записи десять раз, прежде чем она будет воспринята как недоступная.  
  
```  
EXECUTE msdb.dbo.sysmail_configure_sp  
    'AccountRetryAttempts', '10' ;  
```  
  
 **Б. Установка максимального размера вложения на 2 мегабайта**  
  
 В следующем примере показана установка максимального размера вложения на 2 мегабайта.  
  
```  
EXECUTE msdb.dbo.sysmail_configure_sp  
    'MaxFileSize', '2097152' ;  
```  
  
## <a name="see-also"></a>См. также  
 [Database Mail](../../relational-databases/database-mail/database-mail.md)   
 [sysmail_help_configure_sp &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sysmail-help-configure-sp-transact-sql.md)   
 [Хранимые процедуры Database Mail &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/database-mail-stored-procedures-transact-sql.md)  
  
  
