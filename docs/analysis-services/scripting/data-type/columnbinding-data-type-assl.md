---
title: Тип данных ColumnBinding (ASSL) | Документы Microsoft
ms.date: 05/03/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 55c16d18e7ffbe9a53ec80af12f4c111788dc6f4
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2018
---
# <a name="columnbinding-data-type-assl"></a>Тип данных ColumnBinding (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  Определяет производный тип данных, представляющий привязку столбца в представлении источника данных для [DataItem](../../../analysis-services/scripting/data-type/dataitem-data-type-assl.md) элемента.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
  
<ColumnBinding>  
   <!-- The following elements extend Binding -->  
   <TableID>...</TableID>  
      <ColumnID>...</ColumnID>  
</ColumnBinding>  
```  
  
## <a name="data-type-characteristics"></a>Характеристики типа данных  
  
|Характеристика|Описание|  
|--------------------|-----------------|  
|Базовые типы данных|[Привязки](../../../analysis-services/scripting/data-type/binding-data-type-assl.md)|  
|Производные типы данных|None|  
  
## <a name="data-type-relationships"></a>Связи типа данных  
  
|Связь|Элемент|  
|------------------|-------------|  
|Родительские элементы|None|  
|Дочерние элементы|[ColumnID](../../../analysis-services/scripting/properties/columnid-element-eventcolumn-assl.md), [TableID](../../../analysis-services/scripting/properties/tableid-element-assl.md)|  
|Производные элементы|См. раздел [Binding](../../../analysis-services/scripting/data-type/binding-data-type-assl.md)|  
  
## <a name="remarks"></a>Примечания  
 Чтобы создать допустимые имена элементов XML, [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] **DataSet** объектов кодирования имен таблиц, как происходит их сериализация для определения схемы XML (XSD); например, имя «Order Details» преобразуется в «Order_x0020_Details». Аналогичным образом **ColumnID** и **TableID** элементы, содержащиеся в **ColumnBinding** элемент и ссылающихся на объекты в представлении источника данных (DSV), также необходимо закодировать имена во время сериализации, чтобы убедиться, что имена напрямую соответствуют текст в представлении источника данных. Эти имена декодируются в экземпляре служб Analysis Services как **DataSet** модели объектов.  
  
 Объект **TableDefinitions** элемента, содержащегося в элементе с помощью **TableBinding** тип данных и ссылающийся на таблицы в представлении источника данных необходимо также выполняться кодирование имен как происходит их сериализация в XSD. Тем не менее, имена таблиц в **секции** привязки не должны быть закодированы, поскольку эти имена являются просто именами таблиц, которые существуют в базе данных и не должны обязательно находиться в представлении источника данных. Не кодирования имен таблиц в **секции** привязки также осуществляет следующие:  
  
-   Библиотека определения данных для секций становится проще.  
  
-   Обеспечивается большая согласованность, поскольку секции могут содержать либо имена таблиц, либо инструкции SELECT, а инструкции SELECT не должны быть закодированы.  
  
 Имена таблиц и имена столбцов не содержат разделителей (например «[» для [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]).  
  
 Дополнительные сведения о **привязки** типа, включая таблицы объектов языка сценариев служб Analysis Services (ASSL) **привязки** тип и иерархию наследования  **Привязка** типов, в разделе [тип данных привязки &#40;ASSL&#41;](../../../analysis-services/scripting/data-type/binding-data-type-assl.md).  
  
 Обзор привязок данных в ASSL см. в разделе [& #40; источники данных и привязки Многомерные службы SSAS & #41; ](../../../analysis-services/multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md).  
  
 Соответствующим элементом в модели объектов AMO является <xref:Microsoft.AnalysisServices.ColumnBinding>.  
  
## <a name="see-also"></a>См. также  
 [Службы Analysis Services сценариев типы данных XML в & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
