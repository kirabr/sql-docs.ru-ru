---
title: SeekEnum | Документы Microsoft
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
- SeekEnum
helpviewer_keywords:
- SeekEnum enumeration [ADO]
ms.assetid: f0ec0c92-8253-47c6-9a14-e5dbccbad219
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 2f61e71b03a05a8e13c1b069e4880f362ff0985a
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2018
ms.locfileid: "35281593"
---
# <a name="seekenum"></a>SeekEnum
Указывает тип [Seek](../../../ado/reference/ado-api/seek-method.md) для выполнения.  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**adSeekFirstEQ**|1|Выполняет поиск первого ключа равно *KeyValues*.|  
|**adSeekLastEQ**|2|Выполняет поиск последнего ключа равно *KeyValues*.|  
|**adSeekAfterEQ**|4|Ищет ключ, равно *KeyValues* или после которой должны были произойти, соответствующие.|  
|**adSeekAfter**|8|Выполняет поиск ключа сразу после where сопоставление с *KeyValues* должны были произойти.|  
|**adSeekBeforeEQ**|16|Ищет ключ, равно *KeyValues*или перед ней где должны были произойти, соответствующие.|  
|**adSeekBefore**|32|Ищет ключ непосредственно перед где сопоставление с *KeyValues* должны были произойти.|  
  
## <a name="adowfc-equivalent"></a>Эквивалент ADO/WFC  
 Пакет: **com.ms.wfc.data**  
  
|Константа|  
|--------------|  
|AdoEnums.Seek.FIRSTEQ|  
|AdoEnums.Seek.LASTEQ|  
|AdoEnums.Seek.AFTEREQ|  
|AdoEnums.Seek.AFTER|  
|AdoEnums.Seek.BEFOREEQ|  
|AdoEnums.Seek.BEFORE|  
  
## <a name="applies-to"></a>Объект применения  
 [Метод Seek](../../../ado/reference/ado-api/seek-method.md)
