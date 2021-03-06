---
title: Классифицированных столбцов (интеллектуальный анализ данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- content types [data mining]
- STDEV column
- VARIANCE column
- PROBABLILITY column
- PROBABILITY_STDEV column
- columns [data mining], classified
- classified columns [data mining]
- PROBABILITY_VARIANCE column
- SUPPORT column
ms.assetid: 68bf3b78-dc12-497c-898f-b43a45646123
caps.latest.revision: 26
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 403ab773012d9e9370959bd7094db51f9785e8d0
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37210344"
---
# <a name="classified-columns-data-mining"></a>Классифицированные столбцы (интеллектуальный анализ данных)
  При определении классифицированного столбца создается связь между текущим столбцом и другим столбцом в структуре интеллектуального анализа данных. Данные в столбце структуры интеллектуального анализа, обозначенном как классифицированный столбец, содержат сведения о разбивке по категориям, описывающие значения в другом столбце структуры интеллектуального анализа данных.  
  
 Например, предположим, что есть два столбца с числовыми данными. Первый столбец, [Yearly Purchases], содержит все покупки каждого заказчика в течение определенного года, а второй столбец, [Standard Deviations], содержит стандартные отклонения для этих значений. В этом случае можно обозначить столбец [Yearly Purchases] в качестве классифицированного, чтобы модель позволяла использовать эту связь в анализе.  
  
> [!NOTE]  
>  Алгоритмы в [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] не поддерживают использование классифицированных столбцов. Эта функция предназначена для использования при создании пользовательских алгоритмов.  
  
## <a name="defining-a-classified-column"></a>Определение классифицированного столбца  
 Тип данных классифицированного столбца должен быть либо `Long` или `Double`.  
  
 В следующем списке описываются типы содержимого, поддерживаемые службами [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] для классифицированных столбцов.  
  
 **PROBABILITY**  
 Значение в столбце является вероятностью связанного значения и представлено числом от 0 до 1.  
  
 **VARIANCE**  
 Значение в столбце является отклонением связанного значения.  
  
 **STDEV**  
 Значение в столбце является среднеквадратичным отклонением связанного значения.  
  
 **PROBABILITY_VARIANCE**  
 Значение в столбце является отклонением вероятности для связанного значения.  
  
 **PROBABILITY_STDEV**  
 Значение в столбце является среднеквадратичным отклонением вероятности для связанного значения.  
  
 **Псевдоним**  
 Значение в столбце является весом, коэффициентом репликации объекта, связанного значения.  
  
## <a name="see-also"></a>См. также  
 [Типы содержимого &#40;интеллектуального анализа данных&#41;](content-types-data-mining.md)   
 [Структуры интеллектуального анализа данных &#40;службы Analysis Services — Интеллектуальный анализ данных&#41;](mining-structures-analysis-services-data-mining.md)   
 [Типы данных &#40;интеллектуального анализа данных&#41;](data-types-data-mining.md)  
  
  
