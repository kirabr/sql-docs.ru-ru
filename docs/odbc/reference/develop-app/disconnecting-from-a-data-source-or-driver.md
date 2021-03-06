---
title: Отключение от данных источника или драйвер | Документы Microsoft
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- disconnecting from driver [ODBC]
- data sources [ODBC], disconnecting
- disconnecting from data source [ODBC]
- connecting to data source [ODBC], disconnecting
- connecting to driver [ODBC], disconnecting
- ODBC drivers [ODBC], disconnecting
ms.assetid: 83dbf0bf-b400-41fb-8537-9b016050dc3c
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 2118aac1d22df8a4fbf2fbda6679f960e7ced0ae
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32909856"
---
# <a name="disconnecting-from-a-data-source-or-driver"></a>Отключение от данных источника или драйвер
После завершения использования источника данных приложение вызывает **SQLDisconnect**. **SQLDisconnect** освобождает все инструкции, выделенные при соединении и отсоединяет драйвер от источника данных. Он возвращает ошибку, если транзакция находится в процессе.  
  
 После отсоединения приложение может вызвать **SQLFreeHandle** для освобождения соединения. После освобождения соединения, это ошибка программирования приложения для использования дескриптора соединения в вызове функции ODBC; Таким образом, это должна не определено, но, возможно, Неустранимая последствия. Когда **SQLFreeHandle** вызывается версиях драйвера, структура, используемая для хранения сведений о соединении.  
  
 Также приложение может повторно использовать соединения, чтобы подключиться к другому источнику данных или повторно подключиться к тому же источнику данных. Требуется решение остается подключенным, в отличие от отсоединения и присоединения в более поздней версии, что разработчик приложения должен рассмотреть сравнительную стоимость каждого варианта; соединение с источником данных и подключенном может быть сравнительно много ресурсов, в зависимости от носителя соединения. При принятии правильный баланс, приложение должно также делать предположения о вероятности и время дальнейших операций на том же источнике данных.
