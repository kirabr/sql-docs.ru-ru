---
title: Глобальные параметры (тестировщик) (OracleToSQL) | Документы Microsoft
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.technology: ssma
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 4acc0f2a-85ba-4c99-856a-89030f5c418e
caps.latest.revision: 6
author: Shamikg
ms.author: Shamikg
manager: v-thobro
ms.openlocfilehash: 05abc5ee6dac21880645bff60f867b67493e7361
ms.sourcegitcommit: 8aa151e3280eb6372bf95fab63ecbab9dd3f2e5e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "34777520"
---
# <a name="global-settings-tester-oracletosql"></a>Глобальные параметры (тестировщик) (OracleToSQL)
Используйте страницу тест-инженер **глобальные параметры** диалогового окна для задания параметров для тест-инженера SSMA.  
  
Для доступа к параметрам тестировщик, на **средства** последовательно выберите пункты **глобальные параметры**и нажмите кнопку **тест-инженер** в нижней части левой панели.  
  
## <a name="options"></a>Параметры  
**Тестируемый объект анализа**  
Этот параметр указывает, следует ли выполнять анализ тестируемых объектов. Выберите **Да** если инженер-испытатель SSMA для анализа и автоматически проверять зависимые объекты. Набор параметров по умолчанию — **Да**.  
  
Для этого параметра доступны следующие параметры:  
  
1.  Да  
  
2.  Нет  
  
**Дополнительные таблицы, в режиме энергосбережения**  
Этот параметр определяет способ сохранения внутренних вспомогательных таблицах, созданному в ходе выполнения тестового случая. Для этого конкретного значения параметра можно задать следующие параметры:  
  
1.  Всегда удалять  
  
2.  Всегда сохранять  
  
3.  Сохранить, если не удалось выполнить сравнение таблиц  
  
4.  Попросите пользователя, если не удалось выполнить сравнение таблиц  
  
Является набором параметров по умолчанию: **всегда удалять**.  
  
**Выполнить откат данных**  
Этот параметр указывает, следует ли выполнять откат после выполнения каждого тестового случая. Набор параметров по умолчанию — **нет**.  
  
Для этого параметра доступны следующие параметры:  
  
1.  Да  
  
2.  Нет  
  
**Остановить выполнение теста после первой ошибки**  
Этот параметр указывает, следует ли остановить текущее выполнение тестового случая, если произошла ошибка во время выполнения. Набор параметров по умолчанию — **Да**.  
  
Для этого параметра доступны следующие параметры:  
  
1.  Да  
  
2.  Нет  
  
## <a name="see-also"></a>См. также  
[Завершение подготовки тестовый случай &#40;OracleToSQL&#41;](../../ssma/oracle/finishing-test-case-preparation-oracletosql.md)  
  
