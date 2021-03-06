---
title: Параметры SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Engine analysis [Upgrade Advisor]
- SQL Server Upgrade Advisor, Database Engine
- Upgrade Advisor [SQL Server], Database Engine
- analyzing system [Upgrade Advisor], Database Engine
ms.assetid: 44a18bfe-e593-47a5-995f-382c01d3f618
caps.latest.revision: 36
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: f6c34842d1a157629b123b813779a7c3fd3ee142
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37261920"
---
# <a name="sql-server-parameters"></a>Параметры SQL Server
  На этой странице можно установить параметры, которые будут использованы для анализа компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)]. Можно выполнить анализ одной, нескольких или всех баз данных, проанализировать файлы трассировки, созданные программой [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], и пакетные файлы SQL.  
  
> [!NOTE]  
>  Некоторые проблемы обновления можно обнаружить только с помощью анализа файлов трассировки или пакетных файлов SQL.  
  
## <a name="options"></a>Параметры  
 **Базы данных для анализа**  
 Чтобы проанализировать все базы данных, выберите **всех баз данных** "флажок". Чтобы выполнить анализ выбранных баз данных, установите флажок рядом с каждой просматриваемой базой данной.  
  
 **Анализировать файлы трассировки**  
 Установите этот флажок, чтобы выполнить анализ файлов трассировки в файловой системе.  
  
 **Путь к файлам трассировки**  
 Можно выполнить анализ одного или нескольких файлов. Можно выполнить обзор и выбрать несколько файлов или же задать несколько имен файлов. Для каждого файла следует указывать полный путь, включая имя файла. Отдельные записи разделяются символом вертикальной черты (|).  
  
 Если вы включаете **анализировать файлы трассировки**, **Далее** отключена, пока не будет введено имя пути и имени файла.  
  
 **Анализ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] файлы**  
 Установите этот флажок, чтобы выполнить анализ пакетных файлов [!INCLUDE[tsql](../../includes/tsql-md.md)] в файловой системе.  
  
 **Путь к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] файлы**  
 Можно выполнить анализ одного или нескольких пакетных файлов. Можно выполнить обзор и выбрать несколько файлов или же задать несколько имен файлов. Для каждого файла следует указывать полный путь, включая имя файла. Отдельные записи разделяются символом вертикальной черты (|).  
  
 Если вы включаете **SQL анализировать пакетные файлы**, **Далее** кнопка отключена, пока не будет введено имя пути и имени файла.  
  
 **Разделитель пакетов SQL**  
 Текст, используемый для разделения пакетов инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)]. Значение по умолчанию — **GO**.  
  
## <a name="see-also"></a>См. также  
 [Работа с помощником по обновлению](../../../2014/sql-server/install/working-with-upgrade-advisor.md)   
 [Справочник по пользовательскому интерфейсу помощника по обновлению](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
