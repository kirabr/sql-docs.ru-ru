---
title: FLOOR (Transact-SQL) | Документы Майкрософт
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: sql-data-warehouse, pdw, sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- FLOOR_TSQL
- FLOOR
dev_langs:
- TSQL
helpviewer_keywords:
- integers [SQL Server]
- largest integers
- FLOOR function [Transact-SQL]
ms.assetid: 4f26c784-9240-491f-b854-754be3fccae4
caps.latest.revision: 30
author: MashaMSFT
ms.author: mathoma
manager: craigg
monikerRange: '>=aps-pdw-2016||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 79af90b3419bce31e68c4205d5ee662234ef9e07
ms.sourcegitcommit: 4183dc18999ad243c40c907ce736f0b7b7f98235
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "43088845"
---
# <a name="floor-transact-sql"></a>FLOOR (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2008-xxxx-asdw-pdw-md.md)]

  Возвращает наибольшее целое число, меньшее или равное указанному числовому выражению.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
FLOOR ( numeric_expression )  
```  
  
## <a name="arguments"></a>Аргументы  
 *numeric_expression*  
 Выражение категории точного числового или приблизительного числового типа данных, за исключением типа данных **bit**.  
  
## <a name="return-types"></a>Типы возвращаемых данных  
 Возвращает тот же тип, что и аргумент *numeric_expression*.  
  
## <a name="examples"></a>Примеры  
 В следующем примере показаны положительные числовые, отрицательные числовые и денежные значения при помощи функции `FLOOR`.  
  
```  
SELECT FLOOR(123.45), FLOOR(-123.45), FLOOR($123.45);  
```  
  
 Результат представляет собой целую часть вычисляемого значения и имеет тот же тип данных, что и *numeric_expression*.  
  
```  
---------      ---------     -----------  
123            -124          123.0000     
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Примеры: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] и [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
 В приведенном ниже примере с помощью функции `FLOOR` отображаются положительные числовые, отрицательные числовые и денежные значения.  
  
```  
SELECT FLOOR(123.45), FLOOR(-123.45), FLOOR($123.45);  
```  
  
 Результат представляет собой целую часть вычисляемого значения и имеет тот же тип данных, что и *numeric_expression*.  
  
 ```
 -----   ---------    -----------  
  
 123     -124         123
 ```  
  
## <a name="see-also"></a>См. также:  
 [Математические функции (Transact-SQL)](../../t-sql/functions/mathematical-functions-transact-sql.md)  
  
  

