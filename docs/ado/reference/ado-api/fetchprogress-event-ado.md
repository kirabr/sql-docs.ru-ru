---
title: Событие FetchProgress (ADO) | Документы Microsoft
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
- FetchProgress
- Recordset::FetchProgress
helpviewer_keywords:
- FetchProgress event [ADO]
ms.assetid: 301716fd-81fc-40eb-8a04-221ef7ab410e
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 88f5fafb3bc6f4a244d642c0ca18204977a79161
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2018
ms.locfileid: "35278503"
---
# <a name="fetchprogress-event-ado"></a>Событие FetchProgress (ADO)
**FetchProgress**событие вызывается периодически во время продолжительной операции асинхронного сообщить, сколько дополнительные строки в данный момент были получены в [записей](../../../ado/reference/ado-api/recordset-object-ado.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
FetchProgress Progress, MaxProgress, adStatus, pRecordset  
```  
  
#### <a name="parameters"></a>Параметры  
 *Ход выполнения*  
 Объект **длинные** значение, указывающее количество записей, которые в настоящее время после извлечения пользователем операции выборки.  
  
 *MaxProgress*  
 Объект **длинные** должно получить значение, указывающее максимальное количество записей.  
  
 *adStatus*  
 [EventStatusEnum](../../../ado/reference/ado-api/eventstatusenum.md) значение состояния.  
  
 *pRecordset*  
 Объект **записей** объект, являющийся объектом, для которого извлекаются записи.  
  
## <a name="remarks"></a>Примечания  
 При использовании **FetchProgress** с дочерним **записей**, имейте в виду, *выполняется* и *MaxProgress* производных значений параметров из основного [службы курсора](../../../ado/guide/appendixes/microsoft-cursor-service-for-ole-db-ado-service-component.md) набора строк. Возвращаемые значения представляют общее количество записей в базовом наборе строк, не только число записей в текущем.  
  
> [!NOTE]
>  Для использования **FetchProgress** с помощью Microsoft Visual Basic, Visual Basic 6.0 или более поздней версии не требуется.  
  
## <a name="see-also"></a>См. также  
 [Пример модели событий ADO (VC ++)](../../../ado/reference/ado-api/ado-events-model-example-vc.md)   
 [Общие сведения об обработчике событий ADO](../../../ado/guide/data/ado-event-handler-summary.md)
