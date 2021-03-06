---
title: ADO MD основы | Документы Microsoft
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 02/15/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- ADO MD, fundamentals
ms.assetid: f6a20d9f-c1ab-474c-b9f3-82277e2a126d
caps.latest.revision: 14
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: bf6cf507d47527e2ca6a72985b6f5bc817ba88e7
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2018
ms.locfileid: "35273513"
---
# <a name="ado-md-fundamentals"></a>Принципы работы ADO MD
Microsoft® ActiveX® Data Objects (ADO MD) (многомерные выражения) обеспечивает простой доступ к многомерным данным из языков, таких как Microsoft Visual Basic®, Microsoft Visual C++®. ADO MD расширяет Microsoft ActiveX® данных объектов (ADO) для включения объектов, относящихся к многомерным данным, например [CubeDef](../../../ado/reference/ado-md-api/cubedef-object-ado-md.md) и [ячеек](../../../ado/reference/ado-md-api/cellset-object-ado-md.md) объектов. С помощью ADO MD Обзор многомерной схемой, запроса куба и получения результатов.  
  
 Как ADO ADO MD использует поставщика OLE DB для получения доступа к данным. Для работы с ADO MD, поставщик должен быть поставщик многомерных данных (MDP) в соответствии с определением спецификации OLE DB для OLAP. MDP представляется данных в многомерные представления вместо табличных представлений, являющееся как поставщик табличных данных (TDP) представляет данные. Обратитесь к документации для поставщика OLE DB для OLAP, Дополнительные сведения о синтаксисе и поведении поддерживается поставщиком.  
  
 В этом документе предполагается знание языка программирования Visual Basic и общие знания ADO и OLAP. Дополнительные сведения см. в разделе [Руководство программиста ADO](../../../ado/guide/ado-programmer-s-guide.md) и [OLE DB для оперативной аналитической обработки (OLAP)](https://msdn.microsoft.com/library/windows/desktop/ms717005.aspx).  
  
 Этот раздел содержит следующие подразделы.  
  
-   [Общие сведения о многомерных схемах и данных](../../../ado/guide/multidimensional/overview-of-multidimensional-schemas-and-data.md)  
  
-   [Работа с многомерными данными](../../../ado/guide/multidimensional/working-with-multidimensional-data.md)  
  
-   [Использование ADO с объектами данных ActiveX (MD)](../../../ado/guide/multidimensional/using-ado-with-ado-md.md)  
  
-   [Программирование с объектами данных ActiveX (MD)](../../../ado/guide/multidimensional/programming-with-ado-md.md)  
  
## <a name="see-also"></a>См. также  
 [Объектная модель ADO MD](../../../ado/reference/ado-md-api/ado-md-object-model.md)   
 [Руководство программиста ADO](../../../ado/guide/ado-programmer-s-guide.md)   
 [ADO-расширений для языка определения данных и безопасности (ADOX)](../../../ado/guide/extensions/ado-extensions-for-data-definition-language-and-security-adox.md)   
 [Общие сведения о многомерных схем и данных](../../../ado/guide/multidimensional/overview-of-multidimensional-schemas-and-data.md)   
 [Программирование с использованием ADO MD](../../../ado/guide/multidimensional/programming-with-ado-md.md)   
 [Использование ADO с ADO MD](../../../ado/guide/multidimensional/using-ado-with-ado-md.md)   
 [Работа с многомерными данными](../../../ado/guide/multidimensional/working-with-multidimensional-data.md)
