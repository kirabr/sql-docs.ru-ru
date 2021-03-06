---
title: Установка SQL Server Native Client | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client, uninstalling
- SQLNCLI, installing
- SQLNCLI, uninstalling
- Setup [SQL Server Native Client]
- uninstalling SQL Server Native Client
- data access [SQL Server Native Client], uninstalling SQL Server Native Client
- installing SQL Server Native Client
- SQL Server Native Client, installing
- data access [SQL Server Native Client], installing SQL Server Native Client
- removing SQL Server Native Client
ms.assetid: c6abeab2-0052-49c9-be79-cfbc50bff5c1
caps.latest.revision: 43
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: a4023294d52724e5cd132ab4a47b8b8e7f910e3a
ms.sourcegitcommit: 79d4dc820767f7836720ce26a61097ba5a5f23f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/16/2018
ms.locfileid: "40392207"
---
# <a name="installing-sql-server-native-client"></a>Установка собственного клиента SQL Server
  Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 11.0 устанавливается при установке [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)]. Не существует собственного клиента [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)]. Дополнительные сведения см. в разделе [новые возможности в SQL Server Native Client](../sql-server-native-client.md). Также можно извлечь файл sqlncli.msi с веб-страницы пакета дополнительных компонентов SQL Server 2012. Чтобы загрузить самую последнюю версию SQL Server Native Client, перейдите к [пакет дополнительных компонентов Microsoft® SQL Server® 2012 с пакетом обновления 2](http://www.microsoft.com/en-us/download/details.aspx?id=43339). Если предыдущая версия [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] раньше, чем SQL Server 2012 также устанавливается на компьютере, собственный клиент [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 11.0 будет установленных side-by-side с более ранней версии.  
  
 Файлы собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (sqlncli11.dll, sqlnclir11.rll и s11ch_sqlncli.chm) устанавливаются в следующий каталог.  
  
 `%SYSTEMROOT%\system32\`  
  
> [!NOTE]  
>  Все необходимые настройки реестра для поставщика OLE DB собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и драйвера ODBC собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] выполняются в процессе установки.  
  
 Заголовочный файл и библиотека собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (sqlncli.h и sqlncli11.lib) устанавливаются в следующий каталог.  
  
 `%PROGRAMFILES%\Microsoft SQL Server\110\SDK`  
  
 Помимо установки [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] собственный клиент как часть [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] установки, также имеется распространяемый установщик SQLNCLI.msi, который можно найти на [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] установочного диска в следующем расположении: `%CD%\Setup\`.  
  
 Собственный клиент [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] можно распространять в виде файла sqlncli.msi. При развертывании приложения может потребоваться установка собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. Один из способов установки нескольких пакетов в одном (с точки зрения пользователя) сеансе установки состоит в применении технологии построителей цепочек и загрузчиков. Дополнительные сведения см. в статьях [Разработка пользовательского пакета начального загрузчика для Visual Studio 2005](http://go.microsoft.com/fwlink/?LinkId=115667) и [Добавление настраиваемых необходимых компонентов](http://go.microsoft.com/fwlink/?LinkId=115668).  
  
 Версии файла sqlncli.msi для архитектур x64 и Itanium устанавливают и 64-разрядную версию, и 32-разрядную версию собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. Если приложение планируется использовать на платформе, отличной от той, на которой оно разрабатывалось, можно скачать из центра загрузки Майкрософт версии sqlncli.msi for x64, Itanium и x86.  
  
 При инициировании sqlncli.msi по умолчанию устанавливаются только компоненты клиентской части. Этими компонентами служат файлы, поддерживающие работу приложения, разработанного с помощью собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. Чтобы установить также компоненты пакета SDK, укажите в командной строке `ADDLOCAL=All`. Пример:  
  
 `msiexec /i sqlncli.msi ADDLOCAL=ALL APPGUID={0CC618CE-F36A-415E-84B4-FB1BFF6967E1}`  
  
## <a name="silent-install"></a>Автоматическая установка  
 При использовании параметров /passive, /qn, /qb или /qr программы msiexec необходимо также указать параметр IACCEPTSQLNCLILICENSETERMS=YES, тем самым явно подтверждая принятие условий соглашения конечного пользователя. Этот параметр указывается только прописными буквами.  
  
## <a name="uninstalling-sql-server-native-client"></a>Удаление SQL Server Native Client  
 Так как приложения, такие как [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] сервера и [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] средства зависят от [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, важно не удалить [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client до того, все зависимые приложения удаляются. Чтобы предупредить пользователей о том, что ваше приложение зависит [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, воспользуйтесь параметром установки APPGUID в MSI-ФАЙЛЕ, как показано ниже:  
  
 `msiexec /i sqlncli.msi APPGUID={0CC618CE-F36A-415E-84B4-FB1BFF6967E1}`  
  
 Значением, передаваемым в APPGUID, служит код продукта. Код продукта необходимо создать при использовании установщика (Майкрософт) для формирования пакета установки приложения.  
  
## <a name="see-also"></a>См. также  
 [Создание приложений с помощью собственного клиента SQL Server](installing-sql-server-native-client.md)   
 [Инструкции по установке](../../../sql-server/install/installation-how-to-topics.md)  
  
  
