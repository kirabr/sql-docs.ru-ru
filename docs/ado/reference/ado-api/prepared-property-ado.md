---
title: Подготовить свойство (ADO) | Документы Microsoft
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
- Command15::Prepared
helpviewer_keywords:
- Prepared property [ADO]
ms.assetid: 11ca8825-765e-4bb4-a6ce-3f6564ad8755
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 70557d20239eedef30abc280de563a03b39b4a81
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2018
ms.locfileid: "35280583"
---
# <a name="prepared-property-ado"></a>Свойства подготовленный (ADO)
Указывает, следует ли сохранить скомпилированную версию [команда](../../../ado/reference/ado-api/command-object-ado.md) перед выполнением.  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Возвращает или задает **логическое** значение, если значение **True**, указывает, что команда должно быть подготовлено.  
  
## <a name="remarks"></a>Примечания  
 Используйте **Готово** свойство, чтобы сохранить запрос, указанный в подготовленную (скомпилированную) версию поставщика [CommandText](../../../ado/reference/ado-api/commandtext-property-ado.md) свойства перед [команда](../../../ado/reference/ado-api/command-object-ado.md) объекта первого выполнения. Это может привести к снижению первого выполнения команды, но после поставщик компилирует команду, поставщик будет использовать скомпилированная версия команды для любого последующего выполнения, что приведет к повышению производительности.  
  
 Если свойство **False**, поставщик будет выполняться **команда** объекта непосредственно, без создания скомпилированная версия.  
  
 Если поставщик не поддерживает команду подготовки, его могут возвращать ошибку, если это свойство имеет значение **True**. Если поставщик не возвращает ошибку, просто игнорирует запрос на подготовку команды и наборы **Готово** свойства **False**.  
  
## <a name="applies-to"></a>Объект применения  
 [Объект Command (ADO)](../../../ado/reference/ado-api/command-object-ado.md)  
  
## <a name="see-also"></a>См. также  
 [Пример подготовленного свойства (Visual Basic)](../../../ado/reference/ado-api/prepared-property-example-vb.md)   
 [Пример свойства Prepared (Visual C++)](../../../ado/reference/ado-api/prepared-property-example-vc.md)   
