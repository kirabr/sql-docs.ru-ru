---
title: Использование инструкций с драйвером JDBC | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 7f8f3e8f-841e-4449-9154-b5366870121f
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 983cf2bcbdbfd91f10331310dbf4318cd5b3fb5e
ms.sourcegitcommit: 603d2e588ac7b36060fa0cc9c8621ff2a6c0fcc7
ms.translationtype: MTE75
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42785707"
---
# <a name="using-statements-with-the-jdbc-driver"></a>Использование инструкций с драйвером JDBC

[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

[!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] можно использовать для разнообразных способов работы с данными в базах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Драйвер JDBC можно использовать для выполнений инструкций SQL для базы данных или вызова хранимых процедур в базе данных, используя как входные, так и выходные параметры. Драйвер JDBC также поддерживает использование escape-последовательностей SQL, счетчиков обновления, автоматически формируемых ключей, а также выполнение обновлений в рамках пакетной операции.  
  
Драйвер JDBC предоставляет три класса для получения данных из базы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:  
  
1. [SQLServerStatement](../../connect/jdbc/reference/sqlserverstatement-class.md) — используется для выполнения инструкций SQL без параметров.  
  
2. [SQLServerPreparedStatement](../../connect/jdbc/reference/sqlserverpreparedstatement-class.md) (наследуется от SQLServerStatement) — используется для выполнения скомпилированных инструкций SQL, которые могут содержать параметры IN.  
  
3. [SQLServerCallableStatement](../../connect/jdbc/reference/sqlservercallablestatement-class.md) (наследуется от SQLServerPreparedStatement) — используется для запуска хранимых процедур, которые могут содержать параметры IN, OUT либо и те, и другие.  
  
 В разделах этой статьи описано использование каждого из этих трех классов инструкций для работы с данными в базе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
## <a name="in-this-section"></a>в этом разделе  

| Раздел                                                                                                    | Описание                                                                                                                                            |
| -------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [Использование инструкций в SQL](../../connect/jdbc/using-statements-with-sql.md)                             | Описывает использование инструкций SQL с драйвером JDBC для работы с данными в базе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].    |
| [Использование инструкций с хранимыми процедурами](../../connect/jdbc/using-statements-with-stored-procedures.md) | Описывает использование хранимых процедур с драйвером JDBC для работы с данными в базе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. |
| [Использование нескольких результирующих наборов](../../connect/jdbc/using-multiple-result-sets.md)                           | Описывает использование драйвера JDBC для извлечения данных из нескольких результирующих наборов.                                                                       |
| [Использование escape-последовательностей SQL](../../connect/jdbc/using-sql-escape-sequences.md)                           | Описывает использование escape-последовательностей SQL, таких как литералы даты и времени и функции.                                                               |
| [Использование автоматически сформированных ключей](../../connect/jdbc/using-auto-generated-keys.md)                             | Описывает использование автоматически формируемых ключей.                                                                                                     |
| [Выполнение пакетных операций](../../connect/jdbc/performing-batch-operations.md)                         | Описывает использование драйвера JDBC для выполнения пакетных операций.                                                                                      |
| [Обработка сложных инструкций](../../connect/jdbc/handling-complex-statements.md)                         | Описывает использование драйвера JDBC для выполнения сложных инструкций, выполняющих несколько заданий и могущих вернуть различные типы данных.               |
  
## <a name="see-also"></a>См. также:

[Общие сведения о драйвере JDBC](../../connect/jdbc/overview-of-the-jdbc-driver.md)  
