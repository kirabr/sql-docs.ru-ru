---
title: Создание атрибута на основе домена (надстройка MDS для Excel) | Документы Майкрософт
ms.custom: microsoft-excel-add-in
ms.date: 07/25/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.suite: sql
ms.technology: master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 7b3e30dc-8f41-4a5d-8009-ae5a4426a64b
caps.latest.revision: 6
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: ceb5721bfc7a4b99fba89e6ba9030a06e8fe0fc8
ms.sourcegitcommit: de5e726db2f287bb32b7910831a0c4649ccf3c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2018
ms.locfileid: "35334928"
---
# <a name="create-a-domain-based-attribute-mds-add-in-for-excel"></a>Создание атрибута на основе домена (надстройка MDS для Excel)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  В [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]администраторы могут создать атрибут на основе домена, чтобы ограничить значения в столбце определенным набором значений.  
  
 Значения могут уже находиться на листе или могут браться из имеющейся сущности.  
  
> [!NOTE]  
>  Если пользователь вводит значение в столбце с ограничением, а не выбирает его из списка, при публикации в столбце **$InputStatus$** отображаются ошибки.  
  
## <a name="prerequisites"></a>предварительные требования  
 Для выполнения этой процедуры:  
  
-   необходимо иметь разрешение на доступ к функциональным областям **Администрирование системы** и **Обозреватель** ;  
  
-   необходимо быть администратором модели. Дополнительные сведения см. в статье [Administrators &#40;Master Data Services&#41;](../../master-data-services/administrators-master-data-services.md).  
  
-   Модель и сущность должны быть созданы ранее.  
  
### <a name="to-perform-this-procedure"></a>Для выполнения этой процедуры:  
  
1.  В Excel загрузите сущность, содержащую столбец (атрибут), для которого нужно установить ограничение. Дополнительные сведения см. в разделе [Экспорт данных в Excel из служб Master Data Services](../../master-data-services/microsoft-excel-add-in/export-data-to-excel-from-master-data-services.md).  
  
2.  Щелкните любую ячейку в столбце, который нужно ограничить.  
  
3.  В группе **Построить модель** нажмите кнопку **Свойства атрибута**.  
  
4.  В диалоговом окне **Свойства атрибута** в списке **Тип атрибута** выберите пункт **Ограниченный лист (на основе домена)**.  
  
5.  В списке **Заполнить атрибут значениями из** сделайте следующее.  
  
    -   Чтобы использовать значения из листа, выберите **выбранный столбец**. Будут созданы новая сущность и новая промежуточная таблица со значениями из выбранного столбца.  
  
    -   Чтобы использовать значения из имеющейся сущности, выберите имя сущности.
    
    Если существует более пятидесяти сущностей, можно выполнить фильтрацию и поиск сущности. В противном случае выберите сущность в раскрывающемся списке.  
  
6.  Если на предыдущем шаге был указан **выбранный столбец** , в поле **Новое имя сущности** введите имя новой сущности. Оно может совпадать с именем столбца (атрибута).  
  
7.  Нажмите кнопку **ОК**. Теперь каждая ячейка в столбце имеет список значений, из которых могут выбирать пользователи.  
  
## <a name="next-steps"></a>Next Steps  
  
-   Чтобы удалить или добавить значения в списке с ограничениям, загрузите сущность, на которой основан атрибут. Дополнительные сведения о загрузке сущностей см. в разделе [Экспорт данных в Excel из служб Master Data Services](../../master-data-services/microsoft-excel-add-in/export-data-to-excel-from-master-data-services.md).  
  
## <a name="see-also"></a>См. также:  
 [Атрибуты на основе домена (службы Master Data Services)](../../master-data-services/domain-based-attributes-master-data-services.md)   
 [Создание сущности (надстройка MDS для Excel)](../../master-data-services/microsoft-excel-add-in/create-an-entity-mds-add-in-for-excel.md)   
 [Построение модели (надстройка MDS для Excel)](../../master-data-services/microsoft-excel-add-in/building-a-model-mds-add-in-for-excel.md)  
  
  
