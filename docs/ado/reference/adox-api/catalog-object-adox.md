---
title: Каталога объектов (ADOX) | Документы Microsoft
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Catalog
helpviewer_keywords:
- Catalog object [ADOX]
ms.assetid: bb651639-a488-4e38-b6de-0ed99fa4dd92
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: ae03190406dd6a37a7670fe749d76762e6e6674d
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2018
ms.locfileid: "35285243"
---
# <a name="catalog-object-adox"></a>Объект каталога (ADOX)
Содержит коллекции ([таблиц](../../../ado/reference/adox-api/tables-collection-adox.md), [представления](../../../ado/reference/adox-api/views-collection-adox.md), [пользователей](../../../ado/reference/adox-api/users-collection-adox.md), [группы](../../../ado/reference/adox-api/groups-collection-adox.md), и [процедуры](../../../ado/reference/adox-api/procedures-collection-adox.md)), описания каталога схемы источника данных.  
  
## <a name="remarks"></a>Примечания  
 Вы можете изменить **каталога** объекта путем добавления или удаления объектов или изменения существующих объектов. Некоторые поставщики могут не поддерживать все **каталога** объектов или могут поддерживать только для просмотра сведений о схеме.  
  
 С помощью свойств и методов **каталога** объекта, вы можете:  
  
-   Открыть каталог, задав [ActiveConnection](../../../ado/reference/adox-api/activeconnection-property-adox.md) свойства ADO [подключения](../../../ado/reference/ado-api/connection-object-ado.md) объекта или допустимую строку соединения.  
  
-   Создать новый каталог с [создать](../../../ado/reference/adox-api/create-method-adox.md) метод.  
  
-   Определяют владельцев объектов в **каталога** с [GetObjectOwner](../../../ado/reference/adox-api/getobjectowner-method-adox.md) и [SetObjectOwner](../../../ado/reference/adox-api/setobjectowner-method.md) методы.  
  
 Этот раздел содержит следующий раздел.  
  
-   [Свойства, методы и события объекта Catalog](../../../ado/reference/adox-api/catalog-object-properties-methods-and-events.md)  
  
## <a name="see-also"></a>См. также  
 [Пример свойства ActiveConnection каталога (Visual Basic)](../../../ado/reference/adox-api/catalog-activeconnection-property-example-vb.md)   
 [Команда и пример свойства CommandText (Visual Basic)](../../../ado/reference/adox-api/command-and-commandtext-properties-example-vb.md)   
 [Подключение метода закрытия, пример свойство типа таблицы (Visual Basic)](../../../ado/reference/adox-api/connection-close-method-table-type-property-example-vb.md)   
 [Создайте пример метода (Visual Basic)](../../../ado/reference/adox-api/create-method-example-vb.md)   
 [Ключи добавить метод, тип ключа, RelatedColumn, RelatedTable и UpdateRule-пример свойства (Visual Basic)](../../../ado/reference/adox-api/keys-append-method-key-type-relatedcolumn-relatedtable-example-vb.md)   
 [Коллекция параметров, пример команды свойства (Visual Basic)](../../../ado/reference/adox-api/parameters-collection-command-property-example-vb.md)   
 [Пример свойства ParentCatalog (Visual Basic)](../../../ado/reference/adox-api/parentcatalog-property-example-vb.md)   
 [Процедуры добавления пример метода (Visual Basic)](../../../ado/reference/adox-api/procedures-append-method-example-vb.md)   
 [Процедуры удаления пример метода (Visual Basic)](../../../ado/reference/adox-api/procedures-delete-method-example-vb.md)   
 [Процедуры обновления пример метода (Visual Basic)](../../../ado/reference/adox-api/procedures-refresh-method-example-vb.md)   
 [Представления и пример поля коллекций (Visual Basic)](../../../ado/reference/adox-api/views-and-fields-collections-example-vb.md)   
 [Представления Append пример метода (Visual Basic)](../../../ado/reference/adox-api/views-append-method-example-vb.md)   
 [Коллекция представлений, пример свойства CommandText (Visual Basic)](../../../ado/reference/adox-api/views-collection-commandtext-property-example-vb.md)   
 [Представления удаления пример метода (Visual Basic)](../../../ado/reference/adox-api/views-delete-method-example-vb.md)   
 [Представления обновить пример метода (Visual Basic)](../../../ado/reference/adox-api/views-refresh-method-example-vb.md)   
 [Коллекция групп (ADOX)](../../../ado/reference/adox-api/groups-collection-adox.md)   
 [Коллекция процедур (ADOX)](../../../ado/reference/adox-api/procedures-collection-adox.md)   
 [Коллекция таблиц (ADOX)](../../../ado/reference/adox-api/tables-collection-adox.md)   
 [Коллекции пользователей (ADOX)](../../../ado/reference/adox-api/users-collection-adox.md)   
 [Коллекция Views (ADOX)](../../../ado/reference/adox-api/views-collection-adox.md)
