---
title: Работать с FilesExecuting сценария образец консоли консоли SSMA | Документы Microsoft
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
ms.assetid: ad75b648-d119-4119-98f0-d18f058be68d
caps.latest.revision: 10
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: 8b6ebe456c8dc7f678740ab479c317eff041e132
ms.sourcegitcommit: 8aa151e3280eb6372bf95fab63ecbab9dd3f2e5e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "34774270"
---
# <a name="working-with-the-sample-console-script-filesexecuting-the-ssma-console-accesstosql"></a>Работа с FilesExecuting сценария образец консоли SSMA консоли (AccessToSQL)
Несколько файлов образец предоставляется вместе с продуктом использования и справочник по пользовательскому. Этот раздел описывает способ легко настроить эти сценарии, в соответствии с потребностями пользователя.  
  
## <a name="sample-console-script-files"></a>Файлы скриптов образца консоли  
Следующие примеры сценариев файлов консоли охватывают различные сценарии были предоставлены для ссылки на пользователя:  
  
-   ServersConnectionFileSample.xml  
  
-   VariableValueFileSample.xml  
  
-   AssessmentReportGenerationSample.xml  
  
-   ConversionAndDataMigrationSample.xml  
  
-   **ServersConnectionFileSample.xml:**  
  
    -   Этот образец предоставляет различные режимы доступного подключения к исходной и целевой базы данных и пользователь может выбрать любой режим в соответствии с требованием. Этот пример содержит определениями сервера.  
  
    -   Пользователь может подключиться к базе данных требуется, просто изменив значения требуемых исходных и определения целевого сервера. В приведенном примере все значения были предоставлены значения как переменных, которые доступны в **VariableValueFileSample.xml**. Другие параметры соединения можно удалить из файла соединения пользователя рабочего сервера.  
  
    -   Дополнительные сведения о подключении к исходным и целевым сервером см. в разделе [Создание файлов подключения сервера &#40;AccessToSQL&#41; ](../../ssma/access/creating-the-server-connection-files-accesstosql.md) .  
  
-   **VariableValueFileSample.xml:** файлы скриптов, все переменные, которые были использованы в образец консоли и `ServersConnectionFileSample.xml` были сортируются в этот файл. Чтобы выполнить примеры сценариев консоли, он просто заменить образец переменной значения с пользователем определенных областей и передать этот файл в качестве дополнительного аргумента командной строки вместе с файлом сценария.  
  
    Дополнительные сведения о файле значения переменных см. в разделе [Создание переменной значение файлов &#40;AccessToSQL&#41;](../../ssma/access/creating-variable-value-files-accesstosql.md).  
  
-   **AssessmentReportGenerationSample.xml:** этот образец позволяет пользователю создавать XML-отчета оценки, который может использоваться пользователем для анализа прежде чем он начнет преобразование и перенос данных.  
  
    В `generate-assessment-report` команды, пользователь должен mandatorily измените значение переменной (см. **VariableValueFileSample.xml**) в `object-name` атрибут имя базы данных, который используется со стороны пользователя. В зависимости от типа объекта `object-type` значение также должны быть изменены.  
  
    Если пользователь имеет для оценки нескольких объектов и баз данных, он можно указать несколько `metabase-object` узлов, как показано в `generate-assessment-report` 4 пример команды консоли образца файла скрипта.  
  
    Дополнительные сведения о создании отчетов см. в разделе [создания отчетами &#40;AccessToSQL&#41;](../../ssma/access/generating-reports-accesstosql.md).  
  
    > [!NOTE]  
    > -   Убедитесь, что аргумент командной строки файла значение переменной передается в консольном приложении и VariableValueFileSample.xml обновляется пользователя, указанного значения.  
    > -   Убедитесь, что аргумент командной строки файла подключения сервера передается в консольном приложении и ServersConnectionFileSample.xml обновляется значениями параметра правильный сервер.  
  
-   **ConversionAndDataMigrationSample.xml:** в этом примере пользователь может выполнить миграцию комплексных преобразование для переноса данных. Список значения обязательных атрибутов, которые потребуется изменить перечисленные ниже.  
  
    |Имя команды|Описание|attribute|  
    |----------------|---------------|-------------|  
    |`map-schema`|Сопоставление схемы базы данных-источника в целевую схему.|`source-schema:` Указывает, требуется для преобразования базы данных-источника.<br /><br />`sql-server-schema`: Указывает, перемещаются в целевой базе данных|  
    |`convert-schema`|Выполняет преобразование схемы из источника в целевую схему.<br /><br />Если пользователь имеет для оценки нескольких объектов и баз данных, он можно указать несколько `metabase-object` узлов, как показано в `convert-schema` 4 пример команды консоли образца файла скрипта.|`object-name`Для указания базы данных-источника или имя, которое требуется для преобразования объекта. Убедитесь, что соответствующие `object-type` изменяется в зависимости от типа объекта, указанного в `object-name`|  
    |`synchronize-target`|Синхронизирует целевых объектов с целевой базы данных.<br /><br />Если пользователь имеет для оценки нескольких объектов и баз данных, он можно указать несколько `metabase-object` узлов, как показано в `synchronize-target` 3 пример команды консоли образца файла скрипта.|`object-name:` Укажите базы данных sql server / объекта имя, которое требуется создать. Убедитесь, что соответствующие `object-type` изменяется в зависимости от типа объекта, указанного в `object-name`|  
    |`migrate-data`|Переносит данные источника в целевой объект.<br /><br />Если пользователь имеет для оценки нескольких объектов и баз данных, он может указать несколько `metabase-object` узлов, как показано в `migrate-data` команды пример 2 файла скрипта образец консоли.|`object-name:` Указывает базы данных-источника или имя, которое требуется для переноса таблиц. Убедитесь, что соответствующие `object-type` изменяется в зависимости от типа объекта, указанного в `object-name`|  
  
## <a name="see-also"></a>См. также  
[Создание файлов значение переменной &#40;AccessToSQL&#41;](../../ssma/access/creating-variable-value-files-accesstosql.md)  
[Создание файлов подключения сервера &#40;AccessToSQL&#41;](../../ssma/access/creating-the-server-connection-files-accesstosql.md)  
[Создание отчетов &#40;AccessToSQL&#41;](../../ssma/access/generating-reports-accesstosql.md)  
  
