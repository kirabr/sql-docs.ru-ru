---
title: Интерфейс ADOStreamConstruction | Документы Microsoft
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
- ADOStreamConstruction
helpviewer_keywords:
- ADOStreamConstruction interface [ADO]
ms.assetid: 92f5a939-3e1a-4b14-a9dd-90e6ce2dec74
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 73c5e698ecebee93e6b78d884b0b2978750db63e
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2018
ms.locfileid: "35275693"
---
# <a name="adostreamconstruction-interface"></a>Интерфейс ADOStreamConstruction
**ADOStreamConstruction** интерфейса используется для создания объекта ADO **поток** объектов из поставщика OLE DB **IStream** объекта в приложении C/C++.  
  
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|[Свойство Stream](../../../ado/reference/ado-api/stream-property.md)|Чтение и запись. Получает или задает поставщика OLE DB **поток** объекта.|  
  
## <a name="methods"></a>Методы  
 Нет.  
  
## <a name="events"></a>События  
 Нет.  
  
## <a name="remarks"></a>Примечания  
 Получает OLE DB **IStream** объекта (`pStream`), построении ADO **поток** объекта (`adoStr`) суммы следующие три основные операции:  
  
1.  Создание объекта ADO **поток** объекта:  
  
    ```  
    Stream20Ptr adoStr;  
    adoStr.CreateInstance(__uuidof(Stream));  
    ```  
  
2.  Запрос **IADOStreamConstruction** интерфейс **поток** объекта:  
  
    ```  
    adoStreamConstructionPtr adoStrConstruct=NULL;  
    adoStr->QueryInterface(__uuidof(ADOStreamConstruction),  
                         (void**)&adoStrConstruct);  
    ```  
  
 Вызовите `IADOStreamConstruction::get_Stream` метод свойство, чтобы задать OLE DB **IStream** объекта ADO **поток** объекта:  
  
```  
IUnknown *pUnk=NULL;  
pRowset->QueryInterface(IID_IUnknown, (void**)&pUnk);  
adoStrConstruct->put_Stream(pUnk);  
```  
  
 Итоговые `adoStr` теперь представляет объект ADO **поток** объекта, построенным на основе OLE DB **IStream** объекта.  
  
## <a name="requirements"></a>Требования  
 **Версия:** ADO 2.0 или более поздней версии  
  
 **Библиотека:** msado15.dll  
  
 **UUID:** 00000283-0000-0010-8000-00AA006D2EA4  
  
## <a name="see-also"></a>См. также  
 [Справочник по API ADO](../../../ado/reference/ado-api/ado-api-reference.md)
