---
title: Параметры (Загрузка системных объектов) проекта (DB2ToSQL) | Документация Майкрософт
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
ms.assetid: 9a545233-1b0a-488a-a1ec-c33aa608dcc1
caps.latest.revision: 4
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: 3b2398732bc920b926a3db3352eacca6e39f7399
ms.sourcegitcommit: 603d2e588ac7b36060fa0cc9c8621ff2a6c0fcc7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "40395538"
---
# <a name="project-settingsloading-system-objects-db2tosql"></a>Параметры (Загрузка системных объектов) проекта (DB2ToSQL)
На странице загрузки Системные объекты **параметры проекта** диалоговое окно позволяет указать, какие объекты системы DB2 SSMA преобразует и загружает в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
Загрузка системных объектов области доступен в **параметры проекта** и **параметры проекта по умолчанию** диалоговые окна:  
  
-   Чтобы указать параметры для всех проектов SSMA на **средства** меню, выберите **параметры проекта по умолчанию**, выберите тип проекта миграции, для которого требуются параметры для просмотра и изменения из **Целевой версии миграции** раскрывающемся списке щелкните **Общие** в нижней части левой панели, а затем нажмите кнопку **Загрузка системных объектов**.  
  
-   Для задания параметров для текущего проекта на **средства** меню, выберите **параметры проекта**, нажмите кнопку **Общие** в нижней части левой панели и нажмите кнопку **Загрузка системных объектов**.  
  
## <a name="default-settings"></a>Параметры по умолчанию  
Преобразование объектов системы потребляет системные ресурсы и занимает время. Для повышения производительности SSMA выбирает только наиболее часто используемые системные объекты, как показано в следующем списке:  
  
-   SYS.DBMS_OUTPUT  
  
-   SYS.DBMS_PIPE  
  
-   SYS. DBMS_UTILITY  
  
-   SYS. STANDARD  
  
-   SYS. UTL_FILE  
  
-   SYS.DBMS_LOB  
  
-   SYS.DBMS_SQL  
  
-   SYS. DBMS_SESSION  
  
Если ваши объекты DB2 ссылаются на дополнительные системные объекты, следует выбрать эти объекты. Если системные объекты, на которые ссылается объектов базы данных DB2 не выбран, SSMA будет сообщать об ошибках преобразования. При появлении ошибки преобразования из-за отсутствующих системных объектов, выберите объекты, отсутствующие в этом диалоговом окне. Затем можно повторить преобразование при необходимости.  
  
