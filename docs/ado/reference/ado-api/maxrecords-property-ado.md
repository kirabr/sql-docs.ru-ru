---
title: Свойство MaxRecords (ADO) | Документы Microsoft
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
- Recordset15::MaxRecords
helpviewer_keywords:
- MaxRecords property [ADO]
ms.assetid: 20c76571-8c9a-482c-a99e-726ab1d93f8b
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: b83fad35d6bc237e932dad9ed40ab2ae6f4ea279
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2018
ms.locfileid: "35279243"
---
# <a name="maxrecords-property-ado"></a>Свойство MaxRecords (ADO)
Указывает максимальное число записей, чтобы вернуться к [записей](../../../ado/reference/ado-api/recordset-object-ado.md) из запроса.  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Возвращает или задает **длинные** значение, указывающее максимальное количество возвращаемых записей. По умолчанию равно нулю (**0**), что означает отсутствие ограничений.  
  
## <a name="remarks"></a>Примечания  
 Используйте **MaxRecords** свойство, чтобы ограничить количество записей, поставщик возвращает из источника данных. Значение по умолчанию этого свойства равно нулю, это означает, что поставщик возвращает все запрошенные записей.  
  
 **MaxRecords** свойство доступно для чтения/записи при **записей** будет закрыто, только для чтения при открытом.  
  
## <a name="applies-to"></a>Объект применения  
 [Объект Recordset (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>См. также  
 [Пример свойства MaxRecords (Visual Basic)](../../../ado/reference/ado-api/maxrecords-property-example-vb.md)   
 [Пример свойства MaxRecords (Visual C++)](../../../ado/reference/ado-api/maxrecords-property-example-vc.md)   
