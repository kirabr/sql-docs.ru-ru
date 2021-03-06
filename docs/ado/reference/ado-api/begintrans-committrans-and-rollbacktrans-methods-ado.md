---
title: BeginTrans CommitTrans и методы RollbackTrans (ADO) | Документы Microsoft
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
- Connection15::raw_RollbackTrans
- Connection15::CommitTrans
- Connection15::raw_CommitTrans
- Connection15::raw_BeginTrans
- Connection15::BeginTrans
- Connection15::RollbackTrans
helpviewer_keywords:
- BeginTrans method [ADO]
- CommitTrans method [ADO]
- RollbackTrans method [ADO]
ms.assetid: d4683472-4120-4236-8640-fa9ae289e23e
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 42f43c3dfc508ac6885f0e42811af26d89cd6692
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2018
ms.locfileid: "35275983"
---
# <a name="begintrans-committrans-and-rollbacktrans-methods-ado"></a>BeginTrans CommitTrans и методы RollbackTrans (ADO)
Эти методы транзакции управление обработки в пределах транзакций [подключения](../../../ado/reference/ado-api/connection-object-ado.md) объекта следующим образом:  
  
-   **BeginTrans** начинает новую транзакцию.  
  
-   **CommitTrans** сохраняет все изменения и завершает текущую транзакцию. Он также может запустить новую транзакцию.  
  
-   **RollbackTrans** отменяет все изменения, внесенные во время текущей транзакции и завершает транзакцию. Он также может запустить новую транзакцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
level = object.BeginTrans()  
object.BeginTrans  
object.CommitTrans  
object.RollbackTrans  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 **BeginTrans** можно вызывать как функцию, возвращающую **длинные** переменной, показывающей, уровень вложенности транзакции.  
  
#### <a name="parameters"></a>Параметры  
 *object*  
 Объект **подключения** объекта.  
  
## <a name="connection"></a>Соединение  
 Используйте эти методы с **подключения** объекта, если вы хотите сохранить или отменить ряд изменений, внесенных в источник данных как единое целое. Например для передачи денег между счетами, можно вычесть сумму из одного и добавьте величину, заданную в другую. Если либо неудаче обновления, учетные записи больше не балансировку. Эти изменения в открытой транзакции гарантирует, что все или никакие изменения проходят через.  
  
> [!NOTE]
>  Не все поставщики поддерживают транзакции. Убедитесь, что свойство, определенное поставщиком "**операции DDL**» отображается в **подключения** объекта [свойства](../../../ado/reference/ado-api/properties-collection-ado.md) коллекции, указывающее на то, что поставщик поддерживает транзакции. Если поставщик не поддерживает транзакции, вызвав один из этих методов возвращает ошибку.  
  
 После вызова метода **BeginTrans** , поставщик будет фиксировать больше не мгновенно изменения, сделанные до вызова **CommitTrans** или **RollbackTrans** до конца транзакция.  
  
 Для поставщиков, которые поддерживают вложенные транзакции вызова **BeginTrans** метод в открытой транзакции запускает новую, вложенные транзакции. Возвращает значение, указывающее уровень вложенности: «1» возвращает значение, указывающее, был открыт транзакцией верхнего уровня (то есть транзакция не является вложенным в другой транзакции), «2» означает, что вы открыли транзакции второго уровня ( транзакция вложена в рамках транзакции верхнего уровня), и т. д. Вызов **CommitTrans** или **RollbackTrans** затрагивает только последний открытый транзакции; необходимо закрыть или откат текущей транзакции, чтобы связать все более высокого уровня транзакции.  
  
 Вызов **CommitTrans** метод сохраняет изменения, внесенные в открытые транзакции в соединении и завершает транзакцию. Вызов **RollbackTrans** метод отменяет все изменения, внесенные в открытые транзакции и завершает транзакцию. Вызов любого метода, если нет открытых транзакций приводит к ошибке.  
  
 В зависимости от **подключения** объекта [атрибуты](../../../ado/reference/ado-api/attributes-property-ado.md) свойство с помощью вызова **CommitTrans** или **RollbackTrans** может методы автоматически запускает новую транзакцию. Если **атрибуты** свойству **adXactCommitRetaining**, поставщик автоматически запускает новую транзакцию после **CommitTrans** вызова. Если **атрибуты** свойству **adXactAbortRetaining**, поставщик автоматически запускает новую транзакцию после **RollbackTrans** вызова.  
  
## <a name="remote-data-service"></a>Удаленный канал передачи данных  
 **BeginTrans**, **CommitTrans**, и **RollbackTrans** методы доступны не на стороне клиента **подключения** объекта.  
  
## <a name="applies-to"></a>Объект применения  
 [Объект Connection (ADO)](../../../ado/reference/ado-api/connection-object-ado.md)  
  
## <a name="see-also"></a>См. также  
 [BeginTrans CommitTrans и пример RollbackTrans методы (Visual Basic)](../../../ado/reference/ado-api/begintrans-committrans-and-rollbacktrans-methods-example-vb.md)   
 [BeginTrans CommitTrans и примере методы RollbackTrans (VC ++)](../../../ado/reference/ado-api/begintrans-committrans-and-rollbacktrans-methods-example-vc.md)   
 [Свойство Attributes (ADO)](../../../ado/reference/ado-api/attributes-property-ado.md)
