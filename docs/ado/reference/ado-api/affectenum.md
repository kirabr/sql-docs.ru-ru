---
title: AffectEnum | Документы Microsoft
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
- AffectEnum
helpviewer_keywords:
- AffectEnum enumeration [ADO]
ms.assetid: 1ab921a0-6c57-43b4-9291-701b2599f3e8
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 797ee0a58457848b3dec133c695d1d36dc579bbe
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2018
ms.locfileid: "35275703"
---
# <a name="affectenum"></a>AffectEnum
Указывает, какие записи подвержены операции.  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**adAffectAll**|3|Если не [фильтра](../../../ado/reference/ado-api/filter-property.md) применены к **записей**, влияет на все записи.<br /><br /> Если **фильтра** свойству условий строки (такие как «автор = 'Smith'»), то операция затрагивает видимые записи в текущем.<br /><br /> Если **фильтра** свойству членом [FilterGroupEnum](../../../ado/reference/ado-api/filtergroupenum.md) или массив закладки, то операция повлияет на все строки **записей**. **Примечание:****adAffectAll** скрыт в обозревателе объектов Visual Basic.|  
|**adAffectAllChapters**|4|Влияет на все записи из всех главах того же уровня **записей**, включая те, которые не видны через любой **фильтра** , применяется в данный момент.|  
|**adAffectCurrent**|1|Затрагивает только текущую запись.|  
|**adAffectGroup**|2|Затрагивает только те записи, которые удовлетворяют текущего [фильтра](../../../ado/reference/ado-api/filter-property.md) значение свойства. Необходимо задать **фильтра** свойства **FilterGroupEnum** значение или массив **закладки** для использования этого параметра.|  
  
## <a name="adowfc-equivalent"></a>Эквивалент ADO/WFC  
 Пакет: **com.ms.wfc.data**  
  
|Константа|  
|--------------|  
|AdoEnums.Affect.ALL|  
|AdoEnums.Affect.ALLCHAPTERS|  
|AdoEnums.Affect.CURRENT|  
|AdoEnums.Affect.GROUP|  
  
## <a name="applies-to"></a>Объект применения  
  
|||  
|-|-|  
|[Метод CancelBatch (ADO)](../../../ado/reference/ado-api/cancelbatch-method-ado.md)|[Метод Delete (объект Recordset ADO)](../../../ado/reference/ado-api/delete-method-ado-recordset.md)|  
|[Метод Resync](../../../ado/reference/ado-api/resync-method.md)|[Метод UpdateBatch](../../../ado/reference/ado-api/updatebatch-method.md)|
