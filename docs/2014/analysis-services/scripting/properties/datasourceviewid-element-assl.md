---
title: Элемент DataSourceViewID (ASSL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- DataSourceViewID Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- DataSourceViewID
helpviewer_keywords:
- DataSourceViewID element
ms.assetid: dcf617fe-0bf6-4767-af35-07c0c7fd96e5
caps.latest.revision: 35
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: a5f74aa1a747dedce0d3b9beae8b8aa9886bb681
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37271550"
---
# <a name="datasourceviewid-element-assl"></a>Элемент DataSourceViewID (ASSL)
  Идентифицирует [DataSourceView](../objects/datasourceview-element-assl.md) элемент, связанный с [привязки](../data-type/binding-data-type-assl.md) родительского элемента.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
  
<DataSourceViewBinding> <!-- or DSVTableBinding -->  
   ...  
   <DataSourceViewID>...</DataSourceViewID>  
   ...  
</DataSourceViewBinding>  
```  
  
## <a name="element-characteristics"></a>Характеристики элемента  
  
|Характеристика|Описание|  
|--------------------|-----------------|  
|Тип данных и длина|String|  
|Значение по умолчанию|None|  
|Количество элементов|0-1: необязательный элемент, который может встречаться только один раз.|  
  
## <a name="element-relationships"></a>Связи элемента  
  
|Связь|Элемент|  
|------------------|-------------|  
|Родительский элемент|[DataSourceViewBinding](../data-type/datasourceviewbinding-data-type-assl.md), [DSVTableBinding](../data-type/tablebinding-data-type-assl.md)|  
|Дочерние элементы|None|  
  
## <a name="remarks"></a>Примечания  
 Элементы, соответствующие родителям элемента `DataSourceViewID` в модели объектов объекты управления Analysis AMO — это <xref:Microsoft.AnalysisServices.DataSourceViewBinding> и <xref:Microsoft.AnalysisServices.DSVTableBinding>.  
  
## <a name="see-also"></a>См. также  
 [Свойства &#40;ASSL&#41;](properties-assl.md)  
  
  
