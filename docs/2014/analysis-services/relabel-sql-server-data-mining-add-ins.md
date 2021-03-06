---
title: Переразметка (SQL Server Data Mining Add-ins) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- data preparation
- relabel
- data cleaning
ms.assetid: af041b39-fdd1-4cb5-a5ef-2f3ddab84614
caps.latest.revision: 14
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 46a05e8f54a6c307dba5b82572ad8158b305f4bb
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37157175"
---
# <a name="relabel-sql-server-data-mining-add-ins"></a>Переразметка (надстройки интеллектуального анализа данных SQL Server)
  ![Значок Office 13 для средства переразметки](media/dm13-relabel.gif "значок Office 13 для средства переразметки")  
  
 С помощью клиента интеллектуального анализа данных для Excel можно создать для данных новые метки, чтобы облегчить понимание результатов анализа.  
  
 Причины для переразметки:  
  
-   Данные содержат закодированные результаты, например 1 — мужчины, 2 — женщины.  
  
-   Вы группируете числовые значения и хотите указать описательные имена для диапазонов.  
  
-   Вы хотите упростить длинные имена.  
  
## <a name="using-the-relabel-wizard"></a>Использование мастера переразметки  
  
1.  В **интеллектуального анализа данных** ленты, нажмите кнопку **Очистить** , а затем выберите **Переразметка**.  
  
2.  Выберите таблицу или диапазон данных, содержащий данные, которые необходимо исправить.  
  
3.  В **Переразметка** страницы мастера, выберите один столбец, выбрав столбец из раскрывающегося списка или, щелкнув столбец в **образцы данных** области.  
  
     **Образцы данных** панели отображаются только около 50 строк данных, но они применяется выборка для получения репрезентативного подмножества значений.  
  
     Щелкните заголовок столбца для **число** сортировать по числу каждого значения.  
  
     Также можно отсортировать по **исходные метки**, удобным, если вы хотите сначала выполнить переразметку все наибольшие или наименьшие значения.  
  
4.  В **Переразметка** данных страницы мастера, просмотрите значения в **исходные метки** столбца и решить, как вы хотите сгруппировать или изменить данные.  
  
5.  Введите новое значение в строке в списке **новые метки**. Также можно выбрать значение из списка существующих значений. При вводе новых значений они сразу же становятся доступными для повторного использования.  
  
6.  При вводе достаточное количество строк, нажмите кнопку **Далее**, а затем на **Выбор места расположения** выберите место сохранения переразмеченных данных.  
  
    -   **Добавление нового столбца на текущий лист**  
  
         Щелкните, чтобы добавить новый столбец в таблицу, содержащую новые значения.  
  
    -   **Копирование данных листа с изменениями на новый лист**  
  
         Щелкните, чтобы создать новый лист, содержащий обновленные данные.  
  
    -   **Изменение данных на месте**  
  
         Щелкните, чтобы заменить исходные данные новыми значениями.  
  
## <a name="see-also"></a>См. также  
 [Исследование и очистка данных](exploring-and-cleaning-data.md)  
  
  
