---
title: Метод Prepare (SQLServerXAResource) | Документы Microsoft
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
apiname:
- SQLServerXAResource.prepare
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: f800c966-3fae-41b3-963a-464988f80da3
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 8ed9542ce0f81f477c5626b54ce79f846b5b74a1
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32839519"
---
# <a name="prepare-method-sqlserverxaresource"></a>Метод prepare (SQLServerXAResource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Запросы, в диспетчере ресурсов подготовку к фиксации транзакции, заданное в заданном объекте Xid.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public int prepare(javax.transaction.xa.Xid xid)  
```  
  
#### <a name="parameters"></a>Параметры  
 *XID*  
  
 Объект Xid.  
  
## <a name="return-value"></a>Возвращаемое значение  
 **Int** значение.  
  
## <a name="exceptions"></a>Исключения  
 javax.transaction.xa.XAException  
  
## <a name="remarks"></a>Замечания  
 Этот метод подготовки указывается с помощью метода подготовки в интерфейсе javax.transaction.xa.XAResource.  
  
## <a name="see-also"></a>См. также  
 [Методы SQLServerXAResource](../../../connect/jdbc/reference/sqlserverxaresource-methods.md)   
 [Элементы SQLServerXAResource](../../../connect/jdbc/reference/sqlserverxaresource-members.md)   
 [Класс SQLServerXAResource](../../../connect/jdbc/reference/sqlserverxaresource-class.md)  
  
  
