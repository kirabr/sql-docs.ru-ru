---
title: Назначение стартовой учетной записи службы агента SQL Server (диспетчер конфигурации SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, service accounts
- startup accounts [SQL Server]
- service startup accounts [SQL Server Agent]
ms.assetid: 46ffe818-ebb5-43a0-840b-923f219a2472
caps.latest.revision: 42
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: f1c47045f0be910cd6e97f845a258b0606e3ef9b
ms.sourcegitcommit: 8ae6e6618a7e9186aab3c6a37ea43776aa9a382b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43809570"
---
# <a name="set-the-service-startup-account-for-sql-server-agent-sql-server-configuration-manager"></a>Set the Service Startup Account for SQL Server Agent (SQL Server Configuration Manager)
  Стартовая учетная запись службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] определяет учетную запись Windows, которая запускает агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , а также его сетевые разрешения. Этот раздел посвящен назначению учетных записей службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощи среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].  
  
 **В этом разделе**  
  
-   **Перед началом работы**  
  
     [Ограничения](#Restrictions)  
  
     [безопасность](#Security)  
  
-   [Назначение стартовой учетной записи службы для службы агента SQL Server при помощи среды SQL Server Management Studio](#SSMSProcedure)  
  
##  <a name="BeforeYouBegin"></a> Перед началом  
  
###  <a name="Restrictions"></a> Ограничения  
  
-   Начиная с [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] больше не требует, чтобы стартовая учетная запись была элементом группы администраторов [!INCLUDE[msCoName](../../includes/msconame-md.md)] . Однако стартовая учетная запись службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должна быть членом предопределенной роли сервера sysadmin [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Чтобы использовать обработку заданий в многосерверной среде, учетная запись должна быть членом роли "TargetServersRole" базы данных "msdb" на главном сервере.  
  
-   Узел агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] отображается в обозревателе объектов только при наличии у пользователя разрешения на использование узла.  
  
###  <a name="Security"></a> безопасность  
  
####  <a name="Permissions"></a> Permissions  
 Для выполнения своих функций [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] агент должен быть настроен на использование учетных данных учетной записи, которая является членом `sysadmin` предопределенной роли сервера в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Эта учетная запись должна иметь следующие разрешения Windows.  
  
-   Вход в систему в качестве службы (SeServiceLogonRight)  
  
-   Замена токена уровня процесса (SeAssignPrimaryTokenPrivilege)  
  
-   Обход проходной проверки (SeChangeNotifyPrivilege)  
  
-   Назначение квот памяти процессам (SeIncreaseQuotaPrivilege)  
  
 Дополнительные сведения о разрешениях Windows, необходимых для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] учетная запись службы агента, см. в разделе [выберите учетную запись для службы агента SQL Server](select-an-account-for-the-sql-server-agent-service.md) и [Настройка учетных записей службы Windows и Разрешения](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).  
  
##  <a name="SSMSProcedure"></a> Использование среды SQL Server Management Studio  
  
#### <a name="to-set-the-service-startup-account-for-sql-server-agent"></a>Назначение стартовой учетной записи службы агента SQL Server  
  
1.  В списке **Зарегистрированные серверы**щелкните знак «плюс», чтобы развернуть **Ядро СУБД**.  
  
2.  Чтобы развернуть папку **Группы локальных серверов** , щелкните знак «плюс» (+).  
  
3.  Щелкните правой кнопкой мыши экземпляр сервера, в котором нужно назначить стартовую учетную запись службы, и выберите **Диспетчер конфигурации SQL Server...**  
  
4.  В диалоговом окне **Контроль учетных записей** нажмите кнопку **Да**.  
  
5.  В диспетчере конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на панели консоли выберите **Службы SQL Server**.  
  
6.  В области сведений щелкните правой кнопкой *Агент SQL Server***(имя_сервера)*, где *имя_сервера* — это имя экземпляра агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], для которого нужно изменить стартовую учетную запись службы, и выберите пункт **Свойства**.  
  
7.  В диалоговом окне **Свойства агента SQL Server***(имя_сервера)* **выберите** на вкладке **Вход в систему** один из следующих параметров в разделе **Использовать для входа**:  
  
    -   **Встроенная учетная запись**. Выберите этот параметр, если заданиям требуются ресурсы только с локального сервера. Дополнительные сведения о выборе типа встроенной учетной записи Windows см. в разделе [Выбор учетной записи для службы агента SQL Server.](http://msdn.microsoft.com/library/ms191543.aspx)  
  
        > [!IMPORTANT]  
        >  Служба агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не поддерживает учетную запись **Локальная служба** в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].  
  
    -   **Указанная учетная запись**. Выберите этот параметр, если заданиям требуются сетевые ресурсы (в том числе ресурсы приложений), а также если необходимо передавать события журналам других программ Windows или уведомлять операторов по электронной почте или на пейджер.  
  
         В случае использования этого параметра:  
  
        1.  В поле **Имя учетной записи** введите учетную запись, которая будет использоваться для запуска агента SQL Server. Или нажмите кнопку **Обзор** , чтобы открыть диалоговое окно **Выбор пользователя или группы** , и выберите учетную запись для использования.  
  
        2.  В поле **Пароль** введите пароль, соответствующий учетной записи. Повторно введите пароль в поле **Подтверждение пароля** .  
  
8.  Нажмите кнопку **ОК**.  
  
9. В диспетчере конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] нажмите кнопку **Закрыть** .  
  
  
