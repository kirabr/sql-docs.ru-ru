---
title: Источник "Файл HDFS" | Документы Майкрософт
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
- sql13.ssis.designer.hdfsfilesrc.f1
ms.assetid: f8cda200-c389-4a2e-8ee9-5d59b326aac1
caps.latest.revision: 8
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 3a91a00dad5cb2299aaa11e14d0e952c1b363ec3
ms.sourcegitcommit: cc46afa12e890edbc1733febeec87438d6051bf9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2018
ms.locfileid: "35399876"
---
# <a name="hdfs-file-source"></a>Источник "Файл HDFS"
  Компонент "Источник "Файл HDFS" позволяет пакету служб SSIS считывать данные из файла HDFS. Поддерживаются следующие форматы файлов: TEXT и AVRO. Источники данных ORC не поддерживаются.  
  
 Чтобы настроить источник "Файл HDFS", перетащите источник "Файл HDFS" в конструктор потоков данных и дважды щелкните этот компонент, чтобы открыть редактор.  
  
 ![Редактор источника "Файл HDFS"](../../integration-services/data-flow/media/hdfs-file-source.png "Редактор источника \"Файл HDFS\"")  
  
## <a name="options"></a>Параметры  
 Настройте следующие параметры на вкладке **Общие** в диалоговом окне **Редактор источника "Файл Hadoop"** .  
  
|Поле|Описание|  
|-----------|-----------------|  
|**Hadoop Connection (Подключение Hadoop)**|Укажите существующий диспетчер подключений Hadoop или создайте новый. Этот диспетчер подключений указывает, где размещены HDFS-файлы.|  
|**Путь к файлу**|Укажите имя HDFS-файла.|  
|**Формат файла**|Укажите формат HDFS-файла. Доступны следующие значения: TEXT и AVRO. Источники данных ORC не поддерживаются.|  
|**Знак-разделитель столбцов**|Если выбран текстовый формат, укажите знак-разделитель столбцов.|  
|**Имена столбцов в первой строке данных**|Если выбран текстовый формат, укажите, будет ли первая строка файла содержать имена столбцов.|  
  
 После настройки этих параметров перейдите на вкладку **Столбцы** , чтобы сопоставить исходные столбцы с целевыми столбцами в потоке данных.  
  
## <a name="see-also"></a>См. также:  
 [Диспетчер подключений Hadoop](../../integration-services/connection-manager/hadoop-connection-manager.md)   
 [Назначение «Файл HDFS»](../../integration-services/data-flow/hdfs-file-destination.md)  
  
  
