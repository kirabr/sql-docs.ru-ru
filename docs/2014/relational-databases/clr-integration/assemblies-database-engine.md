---
title: Сборки (ядро СУБД) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: clr
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- assemblies [CLR integration]
- assemblies [CLR integration], about assemblies
- managed code [SQL Server], assemblies
ms.assetid: 4b146437-3061-47f6-9e8c-26eeea10b54e
caps.latest.revision: 27
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 157f43f4646c6c935da7884a0fdae93c9676e6fe
ms.sourcegitcommit: 022d67cfbc4fdadaa65b499aa7a6a8a942bc502d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2018
ms.locfileid: "37354966"
---
# <a name="assemblies-database-engine"></a>Сборки (компонент Database Engine)
  В этом разделе содержатся сведения, которые помогут понять, сконструировать и применить сборки.  
  
 Сборки — это файлы DLL, используемые в экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] для развертывания функции, хранимые процедуры, триггеры, определяемые пользователем статистические функции и определяемые пользователем типы, написанные на одном из языков управляемого кода, проводимых [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Общеязыковая среда выполнения (CLR), а не в [!INCLUDE[tsql](../../../includes/tsql-md.md)].  
  
 Сборка в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] представляет собой объект, который ссылается на управляемый модуль приложений (DLL-файл), созданный в среде CLR [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]. Сборка содержит метаданные класса и управляемый код. Передача сборки на экземпляр SQL Server — это первый шаг к созданию любого из следующих объектов базы данных.  
  
-   Функции среды CLR. Дополнительные сведения см. в разделе [Создание функций CLR](../user-defined-functions/create-clr-functions.md).  
  
-   Хранимые процедуры среды CLR. Дополнительные сведения см. в разделе [хранимые процедуры CLR](../../database-engine/dev-guide/clr-stored-procedures.md).  
  
-   Триггеры среды CLR. Дополнительные сведения см. в разделе [Создание триггеров CLR](../triggers/create-clr-triggers.md).  
  
-   Определяемые пользователем агрегатные функции. Дополнительные сведения см. в разделе [создание определяемых пользователем статистических выражений](../user-defined-functions/create-user-defined-aggregates.md).  
  
-   Определяемые пользователем типы. Дополнительные сведения см. в разделе [Using User-Defined типы](../native-client/features/using-user-defined-types.md).  
  
 В [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] сборки выполняют следующие функции.  
  
-   Содержат управляемый код, который выполняет функциональность одного или нескольких объектов базы данных среды CLR, перечисленных ранее.  
  
-   Содержат метаданные, которые включают в себя номер версии и культуру сборки, дополнительный открытый ключ, который уникально идентифицирует список классов сборки, методы, определенные в сборке, и архитектуру процессора сборки.  
  
-   Управляют степенью, к которой управляемый код может получить доступ внешних ресурсов с помощью регулирования разрешений кода доступа.  
  
-   Содержат метаданные о зависимостях от других сборок, на которые ссылается сборка.  
  
## <a name="in-this-section"></a>в этом разделе  
  
|Раздел|Описание|  
|-----------|-----------------|  
|[Конструирование сборок](assemblies-designing.md)|Объясняет, что необходимо учесть перед созданием сборки. Включает в себя упаковку сборок, разрешения кода доступа и другие ограничения.|  
|[Реализация сборок](assemblies-implementing.md)|Объясняет, как правильно создать и удалить сборку, как и когда необходимо изменить сборку, а также как получить метаданные о сборке.|  
|[Получение сведений о сборках](assemblies-getting-information.md)|Перечисляет представления и функции каталога, которые могут запрашиваться для метаданных о сборках.|  
  
## <a name="see-also"></a>См. также  
 [Основные понятия о программировании интеграции со средой (CLR)](common-language-runtime-clr-integration-programming-concepts.md)  
  
  
