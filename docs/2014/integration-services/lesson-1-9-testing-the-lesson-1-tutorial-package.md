---
title: Шаг 9. Проверка учебного пакета, созданного на занятии 1 | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 9aee7acf-797b-46f2-830d-80ab64a9f0b6
caps.latest.revision: 26
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: f5dc22149aab9dfd9d458ed8cd4ec958794d973b
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37193400"
---
# <a name="step-9-testing-the-lesson-1-tutorial-package"></a>Шаг 9. Проверка учебного пакета, созданного на занятии 1
  На этом занятии были выполнены представленные ниже задачи.  
  
-   Был создан проект служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .  
  
-   Была выполнена настройка диспетчеров соединений, используемых пакетом для подключения к исходным и целевым данным.  
  
-   Был добавлен поток данных, который получает данные от источника «неструктурированный файл», производит необходимые преобразования «Уточняющий запрос» и настраивает данные для назначения.  
  
 Создание пакета завершено. Теперь необходимо проверить пакет.  
  
## <a name="checking-the-package-layout"></a>Проверка макета пакета  
 Прежде чем проверить пакет, нужно убедиться в том, что потоки данных и управления в пакете занятия 1 содержат объекты, показанные на следующих диаграммах.  
  
 **Поток управления**  
  
 ![Поток управления в пакете](../../2014/tutorials/media/task9lesson1control.gif "Поток управления в пакете")  
  
 **Поток данных**  
  
 ![Поток данных в пакете](../../2014/tutorials/media/task9lesson1data.gif "Поток данных в пакете")  
  
### <a name="to-run-the-lesson-1-tutorial-package"></a>Выполнение учебного пакета занятия 1  
  
1.  В меню **Отладка** выберите команду **Начать отладку**.  
  
     В результате запуска пакета к таблице фактов **FactCurrency** в базе данных **AdventureWorksDW2012**будет добавлено 1097 строк.  
  
2.  После окончания работы пакета выберите в меню **Отладка** пункт **Остановить отладку**.  
  
## <a name="next-lesson"></a>Следующее занятие  
 [Занятие 2. Добавление циклов](../integration-services/lesson-2-adding-looping-with-ssis.md)  
  
## <a name="see-also"></a>См. также  
 [Запуск проектов и пакетов](packages/run-integration-services-ssis-packages.md)  
  
  
