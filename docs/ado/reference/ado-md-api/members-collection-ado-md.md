---
title: Члены коллекции (ADO MD) | Документы Microsoft
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
- Level::Members
- Members
- Position::Members
helpviewer_keywords:
- Members collection [ADO MD]
ms.assetid: 3a647cde-efdc-4394-b1b9-8cbb1b9d689f
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: d6b4a6902ebf9efae5b02eccb14f1d06e9279cc6
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2018
ms.locfileid: "35284655"
---
# <a name="members-collection-ado-md"></a>Члены коллекции (ADO MD)
Содержит [член](../../../ado/reference/ado-md-api/member-object-ado-md.md) объекты уровня или положение вдоль оси.  
  
## <a name="remarks"></a>Примечания  
 Объект **члены** коллекции служит для хранения следующих типов элементов:  
  
-   Элементы, которые составляют уровень в кубе. Они содержатся в **элементы** коллекцию [уровень](../../../ado/reference/ado-md-api/level-object-ado-md.md) объекта. Например, с помощью образца из [Общие сведения о многомерных схемы и данные](../../../ado/guide/multidimensional/overview-of-multidimensional-schemas-and-data.md), четыре элемента уровня странах, Канада, США, Соединенное Королевство и Германии.  
  
-   Элементы, являющиеся дочерними для элемента в иерархии. Эти члены возвращаются [дочерних](../../../ado/reference/ado-md-api/children-property-ado-md.md) свойство родительского объекта **член** объекта. Например два дочерних элемента Канада снова с помощью тех же, являются Востоке Канады и Западная Канады.  
  
-   Элементы, определяющие заданное положение по оси [ячеек](../../../ado/reference/ado-md-api/cellset-object-ado-md.md). С помощью набора ячеек из [работа с многомерными данными](../../../ado/guide/multidimensional/working-with-multidimensional-data.md) в качестве примера двух члены первая позиция по оси x имеют любимая и Сиэтл. Эти элементы, содержащиеся в **элементы** коллекцию [позиции](../../../ado/reference/ado-md-api/position-object-ado-md.md) объекта.  
  
 **Члены** — это обычная коллекция ADO. С помощью свойств и методов в коллекции можно сделать следующее:  
  
-   Получить число объектов в коллекции с [число](../../../ado/reference/ado-api/count-property-ado.md) свойство.  
  
-   Вернуть объект из коллекции с заданным по умолчанию [элемент](../../../ado/reference/ado-api/item-property-ado.md) свойство.  
  
-   Обновление объектов в коллекции из поставщика с [обновление](../../../ado/reference/ado-api/refresh-method-ado.md) метод.  
  
 Этот раздел содержит следующий раздел.  
  
-   [Свойства, методы и события](../../../ado/reference/ado-md-api/members-collection-properties-methods-and-events.md)  
  
## <a name="see-also"></a>См. также  
 [Пример (VBScript)](../../../ado/reference/ado-md-api/members-example-vbscript.md)   
 [Объект Member (многомерные объекты ADO)](../../../ado/reference/ado-md-api/member-object-ado-md.md)
