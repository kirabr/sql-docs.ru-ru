---
title: Свойство (ADO) Number | Документация Майкрософт
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
- Error::Number
- Error::GetNumber
- Error::get_Number
helpviewer_keywords:
- number property [ADO]
ms.assetid: f92323c5-dd11-4a63-a505-d9014a0f067f
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 2547f22251d9137dc8ca57e8ed29f7aa36251267
ms.sourcegitcommit: c7a98ef59b3bc46245b8c3f5643fad85a082debe
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2018
ms.locfileid: "38985346"
---
# <a name="number-property-ado"></a>Свойство Number (ADO)
Указывает число, которое однозначно определяет [ошибка](../../../ado/reference/ado-api/error-object.md) объекта.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает **Long** значение, которое может соответствовать одному из [ErrorValueEnum](../../../ado/reference/ado-api/errorvalueenum.md) константы.  
  
## <a name="remarks"></a>Примечания  
 Используйте **номер** свойства, чтобы определить, какая ошибка произошла. Значение свойства — это уникальное число, соответствующее условие ошибки.  
  
 [Ошибки](../../../ado/reference/ado-api/errors-collection-ado.md) коллекции возвращает значение HRESULT в шестнадцатеричном формате (например, 0x80004005) или длинное целое значение (например, 2147467259). Эти значения HRESULT может быть инициировано базовые компоненты, например OLE DB или даже OLE, сам. Дополнительные сведения об этих номерах см. в разделе [ошибки (OLE DB)](http://msdn.microsoft.com/ed74e62d-4948-4eeb-a7c9-fd7ad46af7fd) в [Справочник программиста OLE DB по](http://msdn.microsoft.com/3c5e2dd5-35e5-4a93-ac3a-3818bb43bbf8)*.*  
  
## <a name="applies-to"></a>Объект применения  
 [Объект Error](../../../ado/reference/ado-api/error-object.md)  
  
## <a name="see-also"></a>См. также  
 [Description, HelpContext, HelpFile, NativeError, номер, источника и SQLState свойства пример (Visual Basic)](../../../ado/reference/ado-api/description-helpcontext-helpfile-nativeerror-number-source-example-vb.md)   
 [Описание, HelpContext, HelpFile, NativeError, номер, источника и пример свойства SQLState (Visual C++)](../../../ado/reference/ado-api/description-helpcontext-helpfile-nativeerror-number-source-example-vc.md)   
 [Свойство Description](../../../ado/reference/ado-api/description-property.md)   
 [Свойства HelpContext и HelpFile](../../../ado/reference/ado-api/helpcontext-helpfile-properties.md)   
 [Свойство Source (объект Error ADO)](../../../ado/reference/ado-api/source-property-ado-error.md)
