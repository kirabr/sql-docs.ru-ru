---
title: Элемент MiningStructurePermission (ASSL) | Документация Майкрософт
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
- MiningStructurePermission Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- MiningStructurePermission
helpviewer_keywords:
- MiningStructurePermission element
ms.assetid: 4ba2bfd2-9003-4eed-8049-a74d452894ea
caps.latest.revision: 43
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 2f3789cd5b5b72048b9c9163c11bebf4fe5a77d5
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37295494"
---
# <a name="miningstructurepermission-element-assl"></a>Элемент MiningStructurePermission (язык ASSL)
  Определяет разрешения членов элемента [роли](role-element-assl.md) имеют для отдельного [MiningStructure](miningstructure-element-assl.md) элемент.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
  
<MiningStructurePermissions>  
   <MiningStructurePermission xsi:type="Permission">  
      <AllowDrillthrough>...</AllowDrillthrough>  
  
      <!-- This element also inherits all the child elements listed in Permission -->  
   </MiningStructurePermission>  
</MiningStructurePermissions>  
```  
  
## <a name="element-characteristics"></a>Характеристики элемента  
  
|Характеристика|Описание|  
|--------------------|-----------------|  
|Тип данных и длина|[Разрешение](../data-type/permission-data-type-assl.md)|  
|Значение по умолчанию|None|  
|Количество элементов|от 0 до n: необязательный элемент, который может встречаться несколько раз.|  
  
## <a name="element-relationships"></a>Связи элемента  
  
|Связь|Элемент|  
|------------------|-------------|  
|Родительские элементы|[MiningStructurePermissions](../collections/miningstructurepermissions-element-assl.md)|  
|Дочерние элементы|None|  
  
## <a name="remarks"></a>Примечания  
 Соответствующий элемент в модели объектов объекты управления Analysis AMO — это <xref:Microsoft.AnalysisServices.MiningStructurePermission>.  
  
 В [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], разрешение `AllowDrillthrough` была расширена для применения к структуре интеллектуального анализа данных. При назначении роли разрешения любой пользователь, являющийся членом этой роли, может отправлять прямые запросы к структуре интеллектуального анализа данных с помощью следующего синтаксиса:  
  
```  
SELECT <structure column list> FROM <structure>.CASES  
```  
  
 Кроме того, если включено разрешение `AllowDrillthrough` как для структуры, так и для модели интеллектуального анализа данных, пользователи могут запрашивать столбцы структуры, не включенные в модель интеллектуального анализа данных, с помощью следующего синтаксиса:  
  
```  
SELECT StructureColumn('<structure column name>' FROM <model>.CASES  
```  
  
 Например, создается модель с использованием только столбцов, содержащих ключ клиента, доход клиента и покупки клиента. С помощью детализации пользователь может возвращать другие столбцы структуры, не включенные в модель интеллектуального анализа данных, например контактные сведения клиента.  
  
 Поэтому, чтобы защитить конфиденциальные или персональные данные, необходимо так сконструировать представление источника данных, чтобы замаскировать персональные данные, а разрешение `AllowDrillthrough` на структуру интеллектуального анализа данных предоставлять только при необходимости.  
  
 Дополнительные сведения см. в разделе [Drillthrough Queries &#40;Data Mining&#41;](../../data-mining/drillthrough-queries-data-mining.md).  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.AnalysisServices.MiningModel.AllowDrillThrough%2A>   
 <xref:Microsoft.AnalysisServices.AdomdClient.MiningModel.AllowDrillThrough%2A>   
 [Объекты &#40;ASSL&#41;](objects-assl.md)  
  
  
