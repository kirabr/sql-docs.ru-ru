---
title: Задача файловой системы Hadoop | Документы Майкрософт
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.suite: sql
ms.technology: integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql13.ssis.designer.hadoopfiletask.f1
ms.assetid: 594aaf5d-7703-4788-897d-fb95aca798c5
caps.latest.revision: 7
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: bcfab1333cc93562ed72608cb7fa66d29456c077
ms.sourcegitcommit: cc46afa12e890edbc1733febeec87438d6051bf9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2018
ms.locfileid: "35401596"
---
# <a name="hadoop-file-system-task"></a>Задача файловой системы Hadoop
  С помощью задачи файловой системы Hadoop можно копировать файлы из кластера Hadoop, в него и в нем в пакете служб SSIS.  
  
 Чтобы добавить задачу файловой системы Hadoop, перетащите ее в конструктор. Затем дважды щелкните задачу или щелкните правой кнопкой мыши и выберите команду **Изменить**, чтобы открыть диалоговое окно **Редактор задач файловой системы** .  
  
 ![Редактор задач файловой системы](../../integration-services/control-flow/media/hadoop-filesystem-task.png "Редактор задач файловой системы")  
  
## <a name="options"></a>Параметры  
 Настройте следующие параметры в диалоговом окне **Редактор задачи файловой системы Hadoop** .  
  
|Поле|Описание|  
|-----------|-----------------|  
|**Hadoop Connection (Подключение Hadoop)**|Укажите существующий диспетчер подключений Hadoop или создайте новый. Этот диспетчер подключений указывает, где размещены конечные файлы.|  
|**Hadoop File Path (Путь к файлу Hadoop)**|Укажите путь к файлу или каталогу HDFS.|  
|**Hadoop File Type (Тип файла Hadoop)**|Укажите, чем является объект файловой системы HDFS — файлом или каталогом.|  
|**Перезаписать назначение**|Укажите, следует ли перезаписать целевой файл, если он уже существует.|  
|**Операция**|Укажите операцию. Доступны следующие операции: **CopyToHDFS**, **CopyFromHDFS**и **CopyWithinHDFS**.|  
|**Local File Connection (Локальное подключение файлов)**|Укажите существующий диспетчер подключения файлов или создайте его. Этот диспетчер подключений указывает, где размещены исходные файлы.|  
|**С рекурсией**|Укажите, следует ли копировать вложенные папки рекурсивно.|  
  
## <a name="see-also"></a>См. также:  
 [Диспетчер подключений Hadoop](../../integration-services/connection-manager/hadoop-connection-manager.md)   
 [Диспетчер подключений файлов](../../integration-services/connection-manager/file-connection-manager.md)  
  
  
