---
title: Пользовательские условия теста для модульных тестов SQL Server | Документация Майкрософт
ms.custom:
- SSDT
ms.date: 02/09/2017
ms.prod: sql
ms.technology: ssdt
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 32a15d61-e908-4ae1-a238-4fd0f988d8c8
caps.latest.revision: 13
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 8f42e25023a989489000b124a653beb69c1afb33
ms.sourcegitcommit: c8f7e9f05043ac10af8a742153e81ab81aa6a3c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2018
ms.locfileid: "39082566"
---
# <a name="custom-test-conditions--for-sql-server-unit-tests"></a>Пользовательские условия теста для модульных тестов SQL Server
Вы можете добавлять пользовательские условия теста для модульных тестов SQL Server. Однако, чтобы иметь возможность использовать условие теста, его сначала необходимо установить независимо от того, создали ли вы расширение сами, или это сделал кто-то другой.  
  
При установке условия теста, которое создали не вы, необходимо понимать следующие риски.  
  
-   Программа установки условия теста может быть небезопасной. Она может получить доступ к защищенным ресурсам, используя ваши разрешения на установку.  
  
-   Небезопасным может быть и само условие теста. Оно может взять под контроль защищенные ресурсы, если у пользователя, использующего расширение, есть достаточные разрешения.  
  
Чтобы свести риск к минимуму, следует устанавливать нестандартные условия теста, полученные только из известных источников. Если условие теста получено из недоверенного источника, то перед его установкой следует ознакомиться с исходным кодом этого условия теста и его программы установки (при ее наличии).  
  
Чтобы установить пользовательское условие теста, скопируйте подписанную сборку (DLL-файл) в папку %Program Files%\Microsoft Visual Studio <Version>\Common7\IDE\Extensions\Microsoft\SQLDB\TestConditions. Если такой папки не существует, создайте ее. Для копирования файлов в этот каталог пользователь должен обладать правами доступа администратора на компьютере.  
  
> [!NOTE]  
> Вам нужно установить версии условия теста Visual Studio 2010 и Visual Studio 2012, если:  
>   
> -   Вы устанавливаете пользовательские условия теста на компьютер, который может использоваться для создания модульных тестов SQL Server.  
> -   Эти модульные тесты используются в Visual Studio 2010 и Visual Studio 2012.  
  
Дополнительные сведения о пользовательских условиях тестов для модульных тестов SQL Server см. в следующих статьях:  
  
-   [Практическое руководство. Создание условий теста для конструктора модульных тестов SQL Server](../ssdt/how-to-create-test-conditions-for-the-sql-server-unit-test-designer.md)  
  
-   [Практическое руководство. Обновление пользовательского условия теста Visual Studio 2010 с предыдущего выпуска до SQL Server Data Tools](../ssdt/how-to-upgrade-visual-studio-2010-custom-test-condition-to-ssdt.md)  
  
-   [Пошаговое руководство. Использование пользовательского условия теста для проверки результатов выполнения хранимой процедуры](../ssdt/walkthrough-use-custom-test-condition-to-verify-stored-procedure-results.md)  
  
## <a name="see-also"></a>См. также:  
[Проверка кода базы данных с помощью модульных тестов SQL Server](../ssdt/verifying-database-code-by-using-sql-server-unit-tests.md)  
  
