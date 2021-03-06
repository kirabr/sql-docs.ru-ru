---
title: Метод CancelUpdate (ADO) | Документы Microsoft
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
- Recordset15::CancelUpdate
helpviewer_keywords:
- CancelUpdate method [ADO]
ms.assetid: eaa856cc-c786-462e-890c-c896261b1741
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 14557cb420d3a878ae6fa6e7cd70cce45fa6bd71
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2018
ms.locfileid: "35276323"
---
# <a name="cancelupdate-method-ado"></a>Метод CancelUpdate (ADO)
Отменяет все изменения, внесенные в текущем или новом строку из [записей](../../../ado/reference/ado-api/recordset-object-ado.md) объекта, или [поля](../../../ado/reference/ado-api/fields-collection-ado.md) коллекцию [запись](../../../ado/reference/ado-api/record-object-ado.md) объект перед вызовом [обновления ](../../../ado/reference/ado-api/update-method.md) метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
recordset.CancelUpdaterecord.Fields.CancelUpdate  
```  
  
## <a name="remarks"></a>Примечания  
  
## <a name="recordset"></a>набор записей  
 Используйте **CancelUpdate** метод отменить все изменения, внесенные в текущей строке или отменить вновь добавленной строкой. Нельзя отменить изменения в текущей строке или новую строку после вызова метода **обновление** метод, если изменения являются частью транзакции, можно выполнить откат с [RollbackTrans](../../../ado/reference/ado-api/begintrans-committrans-and-rollbacktrans-methods-ado.md) , или часть, метод обновления пакета. В случае пакетного обновления, вы можете отменить **обновление** с **CancelUpdate** или [CancelBatch](../../../ado/reference/ado-api/cancelbatch-method-ado.md) метод.  
  
 При добавлении новой строки при вызове **CancelUpdate** метод, текущая строка становится строка, которая была текущей до [AddNew](../../../ado/reference/ado-api/addnew-method-ado.md) вызова.  
  
 Если в режим редактирования и требуется перемещение текущей записи (например, с помощью [переместить](../../../ado/reference/ado-api/move-method-ado.md), [NextRecordset](../../../ado/reference/ado-api/nextrecordset-method-ado.md), или [закрыть](../../../ado/reference/ado-api/close-method-ado.md) методы), можно использовать  **CancelUpdate** к отмене всех ожидающих изменений. Может потребоваться в случае, если обновление успешно не могут быть зарегистрированы в источник данных. Например, попытка удаления будет закрыто, происходит сбой из-за нарушения ссылочной целостности **записей** в режиме редактирования после вызова [удалить](../../../ado/reference/ado-api/delete-method-ado-recordset.md).  
  
## <a name="record"></a>Записей  
 **CancelUpdate** метод отменяет все ожидающие операции вставки или удаления [поле](../../../ado/reference/ado-api/field-object.md) объектов и отменяет ожидающие обновления существующих полей и восстанавливает их исходные значения. [Состояние](../../../ado/reference/ado-api/status-property-ado-recordset.md) свойства всех полей в **поля** коллекции задано значение **adFieldOK**.  
  
## <a name="applies-to"></a>Объект применения  
  
|||  
|-|-|  
|[Коллекция Fields (ADO)](../../../ado/reference/ado-api/fields-collection-ado.md)|[Объект Recordset (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)|  
  
## <a name="see-also"></a>См. также  
 [Обновление и пример CancelUpdate методы (Visual Basic)](../../../ado/reference/ado-api/update-and-cancelupdate-methods-example-vb.md)   
 [Обновление и пример методы CancelUpdate (VC ++)](../../../ado/reference/ado-api/update-and-cancelupdate-methods-example-vc.md)   
 [Метод AddNew (ADO)](../../../ado/reference/ado-api/addnew-method-ado.md)   
 [Метод Cancel (ADO)](../../../ado/reference/ado-api/cancel-method-ado.md)   
 [Метод Cancel (RDS)](../../../ado/reference/rds-api/cancel-method-rds.md)   
 [Метод CancelBatch (ADO)](../../../ado/reference/ado-api/cancelbatch-method-ado.md)   
 [Метод CancelUpdate (RDS)](../../../ado/reference/rds-api/cancelupdate-method-rds.md)   
 [Свойство EditMode](../../../ado/reference/ado-api/editmode-property.md)   
 [Метод Update](../../../ado/reference/ado-api/update-method.md)
