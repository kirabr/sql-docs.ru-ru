---
title: Подключение к SQL Server (AccessToSQL) | Документация Майкрософт
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.technology: ssma
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: ceb77a97-d6d5-4a92-90a6-342e97d12b54
caps.latest.revision: 3
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: 3b5e50e47f7a6be774e56952f6fcd00ac3b960c2
ms.sourcegitcommit: 603d2e588ac7b36060fa0cc9c8621ff2a6c0fcc7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "40395146"
---
# <a name="connect-to-sql-server-accesstosql"></a>Подключение к SQL Server (AccessToSQL)
Используйте **подключение к SQL Server** диалоговое окно для подключения к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , необходимо выполнить перенос. Для доступа к **подключение к SQL Server** диалоговом окне **файл** меню, щелкните **подключение к SQL Server**.  
  
## <a name="options"></a>Параметры  
**Имя сервера**  
Введите или выберите экземпляр SQL Server для подключения к. По умолчанию отображается экземпляр, который вы подключились к последним.  
  
-   Если вы подключаетесь к экземпляру по умолчанию на локальном компьютере, при вводе любого **localhost** или точку (**.**).  
  
-   Если вы подключаетесь к экземпляру по умолчанию на другом компьютере, введите имя компьютера.  
  
-   Если вы подключаетесь к именованному экземпляру на другом компьютере, введите имя компьютера, обратную косую черту и имя экземпляра, например *MyServer*\\*MyInstance*.  
  
**Порт сервера**  
Если экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не настроен на прием подключений по умолчанию порт (1433), введите номер порта. В противном случае оставьте это поле пустым.  
  
**База данных**  
Укажите базу данных для переноса объектов и данных. Этот параметр недоступен при подключении к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
**Проверка подлинности**  
Выберите метод проверки подлинности, который используется для подключения к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Для использования текущей учетной записи Windows, выберите проверку подлинности Windows. Чтобы указать [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имя входа и пароль, выберите [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] проверки подлинности.  
  
**Имя пользователя**  
Если вы используете [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] проверки подлинности, введите имя входа для текущего экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. При использовании проверки подлинности Windows, этот параметр недоступен.  
  
**Пароль**  
Если вы используете [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] проверки подлинности, введите пароль для имени входа на этом экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. При использовании проверки подлинности Windows, этот параметр недоступен.  
  
**Шифровать соединение**  
Если вы хотите для безопасного подключения к SQL Server, использовать соединения Encrypt, установив флажок **шифровать соединение** флажок.  
  
**Надежный сертификат сервера**  
Если вы хотите использовать этот параметр, выберите **доверять сертификату сервера** флажок.  
  
> [!NOTE]  
> Чтобы включить **доверять сертификату сервера**, «Зашифровать» должно быть присвоено **True**.  
  
