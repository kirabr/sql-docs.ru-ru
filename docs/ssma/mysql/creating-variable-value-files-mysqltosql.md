---
title: Создание файлов значение переменной (MySQLToSQL) | Документы Microsoft
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
helpviewer_keywords:
- Creating variable value files
- variable value file validation
ms.assetid: 1dc56a7b-8e3a-4576-ad4f-47050bf7e28a
caps.latest.revision: 16
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: 9d350957cb1590fa2aec5fcd31028849191d8f5d
ms.sourcegitcommit: 8aa151e3280eb6372bf95fab63ecbab9dd3f2e5e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "34775876"
---
# <a name="creating-variable-value-files-mysqltosql"></a>Создание файлов значение переменной (MySQLToSQL)
Файл значение переменной является XML-файл, состоящий из значений параметра команд как имя сервера источника или назначения, которые часто изменяются в зависимости от одного сервера миграции. При возникновении большое количество миграции базы данных, несколько файлов переменной для хранения значения каждого исходного сервера создается, на которые ссылается файл сценария master **– v** переключения командной строки. Это помогает при ведении статических значений в несколько файлов скриптов, если значения переменных в нескольких файлах переменной.  
  
> [!NOTE]  
> 1.  Имена переменных префиксом и суффиксом символом $ (доллара). Если переменные не будут назначены значения в файле значение переменной, возникает ошибка при синтаксическом разборе файла скрипта, возникающие в процесс выполнения консоли остановился.  
> 2.  The escape character for **$** is **$$**. Если значение переменной или статической значение параметра содержит **$** символ (доллара), затем **$$** должен быть указан следует считать символ вместо переменной.  
> 3.  В целях удобства переменные могут быть объявлены внутри `‘variable-group’` элементы для логического разделения пользователя определены переменные.  Использование этого элемента не является обязательным.  
  
**Примеры:**  
  
**Пример 1.**  
  
```xml  
<!--Sample of variable value file commands-->  
  
<variables>  
  
  <variable-group name="ProjectSpecs">  
  
    <variable name="$project_folder$" value="<folder-name>"/>  
  
    <variable name="$project_name$" value="<project-name>"/>  
  
    <variable name="$project_overwrite$" value="<true/false>"/>  
  
    <variable name="$project_type$" value="<project-type>"/>  
  
  </variable-group>  
  
</variables>  
```  
**Пример 2.**  
  
```xml  
<!--Sample of variable value file commands-->  
  
<variables>  
  
  <variable-group name="SQLServerParams">  
  
    <variable-group name="SqlServerConnectionParams">  
  
      <variable name="$TargetUserName$ value="<user-name>"/>  
  
      <variable name="$TargetServerName$" value="<server-name>"/>  
  
      <variable name="$TargetDB$" value="<database-name>"/>  
  
      <variable name="$TargetPassword$" value="<password>"/>  
  
      <variable name="$TrustedConnection$" value="<true/false>"/>  
  
    </variable-group>  
  
    <variable-group name="SqlServerObjectParams">  
  
      <variable name="$ObjectName1$" value="<object-name>"/>  
  
      <variable name="$ObjectName2$" value="<object-name>"/>  
  
    </variable-group>  
  
  </variable-group>  
  
</variables>  
```  
  
## <a name="variable-value-file-validation"></a>Проверка файла значения переменной  
Пользователь может легко проверить свой файл значение переменной, соответствие файлу определения схемы **«ConsoleScriptVariablesSchema.xsd»** доступны в папке «Схемы».  
  
## <a name="next-step"></a>Следующий шаг  
Следующий шаг в работе консоли — [Создание файлов подключения сервера &#40;MySQLToSQL&#41;](../../ssma/mysql/creating-the-server-connection-files-mysqltosql.md)  
  
## <a name="see-also"></a>См. также  
[Создание файлов подключения сервера (MySQL)](http://msdn.microsoft.com/en-us/df0e970c-da0b-4118-b359-c9dcbbad16d6)  
  
