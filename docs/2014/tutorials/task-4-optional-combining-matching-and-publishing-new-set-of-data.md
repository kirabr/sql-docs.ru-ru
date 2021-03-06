---
title: 'Задача 4 (необязательно): объединение, сопоставление и публикация нового набора данных | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- data-quality-services
- integration-services
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 13a13f03-b307-4555-8e33-6d98c459d994
caps.latest.revision: 6
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 207f6141338c4d9e44c4fc7763177276ea623686
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37167775"
---
# <a name="task-4-optional-combining-matching-and-publishing-new-set-of-data"></a>Задача 4 (дополнительно). Объединение, сопоставление и публикация нового набора данных
  Со временем в репозиторий MDS потребуется добавить дополнительные данные. Перед добавлением может быть полезно сравнить новые данные с данными, которые уже управляются в MDS, чтобы избежать повторения или добавления неточных данных. В надстройке служб Master Data Services для Excel можно объединять данные из двух листов, а также сравнивать данные для обнаружения и удаления повторений перед публикацией данных в MDS. Функция сопоставления надстройки MDS для Excel использует функциональность сопоставления служб DQS для выявления совпадений в данных. В этой задаче будет выполнено объединение данных из двух листов в один, а затем будет выполнено действие для выявления и удаления повторений перед публикацией в MDS. См. в разделе [сопоставление качества данных в надстройке MDS для Excel](http://msdn.microsoft.com/library/hh548681.aspx) и [объединение данных](http://msdn.microsoft.com/library/hh548680.aspx) разделы для получения дополнительных сведений.  
  
1.  Запустите новый экземпляр **Excel**. Нажмите кнопку **запустить**, пункты **запуска**, тип **Excel**и нажмите кнопку **ОК**.  
  
2.  Переключиться в режим **основных данных** , щелкнув **основных данных** в строке меню.  
  
3.  Нажмите кнопку **Connect** на ленте в **подключение и загрузка** группы для подключения к **сервер MDS**. Это соединение было настроено ранее на этом занятии.  
  
     ![Excel — Показывать кнопку обозревателя на основных данных](../../2014/tutorials/media/et-combinematchandpublishnewsod-01.jpg "Excel — Показывать кнопку обозревателя на основных данных")  
  
4.  Вы должны увидеть **обозреватель основных данных** панели справа. Если вы не видите обозреватель основных данных, нажмите кнопку **Показать обозреватель** кнопку на ленте.  
  
5.  В **обозреватель основных данных** выберите **поставщики** в раскрывающемся списке для **модели**. Вы увидите, что модель имеет одну сущность: **поставщика**.  
  
     ![Excel — окно обозревателя основных данных](../../2014/tutorials/media/et-combinematchandpublishnewsod-02.jpg "Excel — окно обозревателя основных данных")  
  
6.  Дважды щелкните **поставщика** в списке сущность, чтобы загрузить элементы сущности на лист Excel.  
  
7.  Нажмите кнопку **Лист2** внизу, чтобы переключиться в режим **Лист2** вкладки. Если вы не видите **Лист2**, добавьте новый лист.  
  
8.  Откройте **Suppliers.xls** файле (исходный входной файл, включенный в файлы учебника) и скопируйте все строки (3) из **CombineAndCleanse** листа **Лист2**.  
  
9. Вернитесь в **поставщика** листа **книге 1 — Microsoft Excel** (не **Cleansed and Matched Supplier List** Excel), подключенный к **MDS**.  
  
10. Нажмите кнопку **основных данных** в строке меню.  
  
11. Нажмите кнопку **объединение данных** на ленте. Вы увидите **объединение данных** диалоговое окно.  
  
12. В **объединение данных** диалоговом окне нажмите кнопку рядом с полем **диапазон для объединения с данными MDS** текстового поля, как показано на следующем рисунке.  
  
     ![Excel — объединение данных диалоговое окно](../../2014/tutorials/media/et-combinematchandpublishnewsod-03.jpg "Excel — объединение данных диалоговое окно")  
  
13. Теперь должно отобразиться свернутое диалоговое окно. Теперь щелкните **Лист2** переключиться на **Лист2** вкладку, которая имеет новые данные поставщика с 4 строками (включая одну строку заголовков).  
  
14. В **Лист2**выберите **все строки, включая строку заголовка** (даже если кажется, что уже выделены). Вы должны увидеть **диапазон для объединения с данными MDS** автоматически обновляется.  
  
     ![Excel — объединение данных диалоговое окно — свести к минимуму](../../2014/tutorials/media/et-combinematchandpublishnewsod-04.jpg "Excel — объединение данных диалоговое окно — свести к минимуму")  
  
15. Вернитесь в **поставщики** вкладки, не закрывая **объединение данных** диалоговое окно.  
  
16. Нажмите кнопку **кнопку** рядом с полем **текстовое поле**. Убедитесь, что диалоговое окно развернуто. Вы должны увидеть все сопоставления между столбцами **поставщика** MDS **сущности** для **Excel** столбцы заполняются автоматически.  
  
     ![Excel — объединение данных диалоговое окно, заполненный данными](../../2014/tutorials/media/et-combinematchandpublishnewsod-05.jpg "Excel — объединение данных диалоговое окно, заполненный данными")  
  
17. Убедитесь, что **кода** столбец сущности сопоставляется **SupplierID** столбец на листе и **почтовый индекс** столбец сущности сопоставляется **почтовый индекс** столбец на рабочем листе.  
  
18. На **объединение данных** диалоговом окне щелкните **объединить**.  
  
19. Убедитесь, что 3 строки данных были помещены в конец листа. Они должны быть выделены цветом.  
  
     ![Excel — новые элементы после объединения](../../2014/tutorials/media/et-combinematchandpublishnewsod-06.jpg "Excel — новые элементы после объединения")  
  
20. Нажмите кнопку **сопоставить данные** на ленте для обнаружения дубликатов. Эта функция использует функции сопоставления служб DQS.  
  
21. В **сопоставить данные** выберите **поставщики** для **базы знаний DQS**.  
  
     ![Excel — диалоговое окно сопоставления данных](../../2014/tutorials/media/et-combinematchandpublishnewsod-07.jpg "Excel — диалоговое окно сопоставления данных")  
  
22. Сопоставьте столбцы листа с доменами, как показано в следующей таблице.  
  
    |Столбец листа|Домен|  
    |----------------------|------------|  
    |Code (Supplier ID был загружен как Code для сущности Supplier в MDS)|Supplier ID|  
    |Name (Supplier Name было загружено как Name для сущности Supplier в MDS)|Имя поставщика|  
    |ContactEmailAddress|ContactEmail|  
  
23. Выберите **готовности к установке** для **кода** сопоставление столбцов.  
  
24. Введите **70%** как **вес** для **Supplier Name** и **30%** как **вес** для **Контактный адрес электронной почты** как показано на рисунке.  
  
25. Нажмите кнопку **ОК**.  
  
26. Процесс сопоставления должен определить одно повторение для поставщика с **кода: S1**.  
  
     ![Excel — результаты сопоставления](../../2014/tutorials/media/et-combinematchandpublishnewsod-08.jpg "Excel — результаты сопоставления")  
  
27. Выберите **повторяющуюся строку (оранжевый)**, щелкните правой кнопкой мыши и нажмите кнопку **удалить** для удаления строки.  
  
28. Удалить **CLUSTER_ID** столбец, так как вы оно больше не требуется.  
  
29. Нажмите кнопку **публикации** опубликовать две новые записи с **кодами S66** и **S57** в MDS.  
  
30. В **публикация и заметки** диалоговое окно, добавьте **заметки**и нажмите кнопку **публикации**.  
  
31. Переключиться в режим **веб-приложения диспетчера основных данных**.  
  
32. Убедитесь, что на домашней странице **поставщики** выбран для **модели**и нажмите кнопку **Explorer**. Если у вас уже есть **Explorer** откройте, обновите Интернет-браузер.  
  
33. **Сортировка** список по **кода** и найдите записи с **S57** и **S66** как коды. Можно также использовать **фильтра** на панели инструментов для поиска определенной записи в списке.  
  
34. Теперь закройте **Книга1 — Microsoft Excel** окно без сохранения файла.  
  
## <a name="next-step"></a>Следующий шаг  
 [Задача 5. Создание атрибута на основе домена из Excel](../../2014/tutorials/task-5-creating-a-domain-based-attribute-from-excel.md)  
  
  
