---
title: Элемент MiningStructurePermissions (ASSL) | Документация Майкрософт
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
- MiningStructurePermissions Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- MiningStructurePermissions
helpviewer_keywords:
- MiningStructurePermissions element
ms.assetid: 4db9a9b2-8525-441f-a202-fd253282f540
caps.latest.revision: 31
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 91beb4cef1679150255283621403b53abeadfa7e
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37324864"
---
# <a name="miningstructurepermissions-element-assl"></a>Элемент MiningStructurePermissions (ASSL)
  Содержит коллекцию разрешений на [MiningStructure](../objects/miningstructure-element-assl.md) элемент.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
  
<MiningStructure>  
   ...  
   <MiningStructurePermissions>  
      <MiningStructurePermission xsi:type="Permission">...</MiningStructurePermission>  
   </MiningStructurePermissions>  
   ...  
</MiningStructure>  
```  
  
## <a name="element-characteristics"></a>Характеристики элемента  
  
|Характеристика|Описание|  
|--------------------|-----------------|  
|Тип данных и длина|None|  
|Значение по умолчанию|None|  
|Количество элементов|0-1: необязательный элемент, который может встречаться только один раз.|  
  
## <a name="element-relationships"></a>Связи элемента  
  
|Связь|Элемент|  
|------------------|-------------|  
|Родительский элемент|[MiningStructure](../objects/miningstructure-element-assl.md)|  
|Дочерние элементы|[MiningStructurePermission](../objects/miningstructurepermission-element-assl.md) типа [разрешение](../data-type/permission-data-type-assl.md)|  
  
## <a name="remarks"></a>Примечания  
 Соответствующий элемент в модели объектов объекты управления Analysis AMO — это <xref:Microsoft.AnalysisServices.MiningStructurePermissionCollection>.  
  
## <a name="see-also"></a>См. также  
 [Тип данных Permission &#40;ASSL&#41;](../data-type/permission-data-type-assl.md)   
 [Коллекции &#40;ASSL&#41;](collections-assl.md)  
  
  
