---
title: Элемент DiscretizationMethod (ASSL) | Документация Майкрософт
ms.date: 5/8/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 81064689788574061f103b973a5435beb3e83893
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38002206"
---
# <a name="discretizationmethod-element-assl"></a>Элемент DiscretizationMethod (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  Определяет метод дискретизации.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
  
<DimensionAttribute> <!-- or ScalarMiningStructureColumn -->  
   ...  
   <DiscretizationMethod>...</DiscretizationMethod>  
   ...  
</DimensionAttribute>  
```  
  
## <a name="element-characteristics"></a>Характеристики элемента  
  
|Характеристика|Описание|  
|--------------------|-----------------|  
|Тип данных и длина|String (перечисление)|  
|Значение по умолчанию|*None*|  
|Количество элементов|0-1: необязательный элемент, который может встречаться только один раз.|  
  
## <a name="element-relationships"></a>Связи элемента  
  
|Связь|Элемент|  
|------------------|-------------|  
|Родительские элементы|[DimensionAttribute](../../../analysis-services/scripting/data-type/dimensionattribute-data-type-assl.md), [ScalarMiningStructureColumn](../../../analysis-services/scripting/data-type/scalarminingstructurecolumn-data-type-assl.md)|  
|Дочерние элементы|None|  
  
## <a name="remarks"></a>Примечания  
 Значение элемента **DiscretizationMethod** определяет, как выполняется дискретизация значений для элементов **DimensionAttribute** или **ScalarMiningStructureColumn** , либо организация в виде конкретного набора групп. Дополнительные сведения о методах дискретизации см. в разделе [методы дискретизации &#40;интеллектуального анализа данных&#41;](../../../analysis-services/data-mining/discretization-methods-data-mining.md).  
  
 Значением этого элемента может быть только одна из строк в следующей таблице.  
  
|Значение|Описание|  
|-----------|-----------------|  
|*Автоматически*|Эквивалентен методу дискретизации AUTOMATIC для столбцов структуры интеллектуального анализа данных.|  
|*EqualAreas*|Эквивалентен методу дискретизации EQUAL_AREAS для столбцов структуры интеллектуального анализа данных.|  
|*Кластеры*|Эквивалентен методу дискретизации CLUSTERS для столбцов структуры интеллектуального анализа данных.|  
|*Пороги*|Эквивалентен методу дискретизации THRESHOLDS для столбцов структуры интеллектуального анализа данных.|  
|*EqualRanges*|Эквивалентен методу дискретизации EQUAL_RANGES для столбцов структуры интеллектуального анализа данных.|  
  
 Перечисление, соответствующее допустимым значениям **DiscretizationMethod** в объекты управления Analysis AMO объектной модели это <xref:Microsoft.AnalysisServices.DiscretizationMethod>.  
  
## <a name="see-also"></a>См. также  
 [Свойства &#40;ASSL&#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
