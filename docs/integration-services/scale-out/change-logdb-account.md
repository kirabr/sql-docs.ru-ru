---
title: Изменение учетной записи для ведения журнала служб SSIS Scale Out | Документы Майкрософт
description: В этой статье описывается, как изменять настройки учетной записи пользователя для SSIS Scale Out.
ms.custom: performance
ms.date: 12/13/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: douglasl
ms.suite: sql
ms.technology: integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
caps.latest.revision: 1
author: haoqian
ms.author: haoqian
manager: craigg
ms.openlocfilehash: 6d2fa1e69ada0fe5e4ef66e01cd5322efbf38516
ms.sourcegitcommit: cc46afa12e890edbc1733febeec87438d6051bf9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2018
ms.locfileid: "35406586"
---
# <a name="change-the-account-for-scale-out-logging"></a>Изменение учетной записи для ведения журнала служб SSIS Scale Out
При выполнении пакетов SSIS в Scale Out сообщения о событиях записываются в базу данных SSISDB с помощью создаваемой автоматически учетной записи пользователя **##MS_SSISLogDBWorkerAgentLogin##**. Для входа этого пользователя в систему применяется проверка подлинности SQL Server.

Чтобы сменить учетную запись, используемую для ведения журнала Scale Out, выполните указанные ниже действия.

> [!NOTE]
> Если для ведения журналов применяется учетная запись пользователя Windows, используйте ту же учетную запись, что и для выполнения службы рабочей роли Scale Out. В противном случае произойдет ошибка входа в SQL Server.

## <a name="1-create-a-user-for-ssisdb"></a>1. Создание пользователя SSISDB
Инструкции по созданию пользователя базы данных см. в разделе [Создание пользователя базы данных](../../relational-databases/security/authentication-access/create-a-database-user.md).

## <a name="2-add-the-user-to-the-database-role-ssisclusterworker"></a>2. Добавление пользователя в роль базы данных ssis_cluster_worker

Инструкции по присоединению роли базы данных см. в разделе [Присоединение к роли](../../relational-databases/security/authentication-access/join-a-role.md).

## <a name="3-update-the-logging-information-in-ssisdb"></a>3. Обновление сведений о ведении журнала в SSISDB
Вызовите хранимую процедуру `[catalog].[update_logdb_info]` с именем SQL Server и строкой подключения в качестве параметров, как показано в следующем примере:

    ```sql
    SET @serverName = CONVERT(sysname, SERVERPROPERTY('servername'))
    SET @connectionString = 'Data Source=' + @serverName + ';Initial Catalog=SSISDB;Integrated Security=SSPI;'
    EXEC [internal].[update_logdb_info] @serverName, @connectionString
    GO
    ```

## <a name="4-restart-the-scale-out-worker-service"></a>4. Перезапуск службы рабочей роли Scale Out
Перезапустите службу рабочей роли Scale Out, чтобы изменение вступило в силу.

## <a name="next-steps"></a>Следующие шаги
-   [Диспетчер Integration Services Scale Out](integration-services-ssis-scale-out-manager.md)