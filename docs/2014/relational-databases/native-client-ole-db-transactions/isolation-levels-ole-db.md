---
title: Уровни изоляции (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- isolation levels [OLE DB]
- transactions [OLE DB]
- SQL Server Native Client OLE DB provider, transactions
ms.assetid: d70ee72c-6e2a-4bcd-9456-4a697a866361
caps.latest.revision: 32
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: ec099f18afd80bd07f059d3e87b18598b36b1117
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2018
ms.locfileid: "37420729"
---
# <a name="isolation-levels-ole-db"></a>Уровни изоляции (OLE DB)
  Клиенты [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] могут управлять уровнями изоляции транзакций для соединения. Чтобы управлять уровнем изоляции транзакций, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] потребитель вызывает поставщик OLE DB для собственного клиента:  
  
-   Свойство DBPROP_SESS_AUTOCOMMITISOLEVELS параметра DBPROPSET_SESSION для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] режим автоматической фиксации по умолчанию поставщик OLE DB для собственного клиента.  
  
     [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] По умолчанию поставщик OLE DB для собственного клиента для уровня — DBPROPVAL_TI_READCOMMITTED.  
  
-   *IsoLevel* параметр **ITransactionLocal::StartTransaction** метод для локальных транзакций ручной фиксации.  
  
-   *IsoLevel* параметр **ITransactionDispenser::BeginTransaction** метод координацией MS DTC распределенные транзакции.  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] разрешает доступ только для чтения на уровне изоляции чтения «грязных» данных. Все другие уровни ограничивают параллелизм применением блокировок к объектам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Если клиент требует более высоких уровней параллелизма, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] применяет более строгие ограничения на параллельные обращения к данным. Для поддержания высочайшего уровня параллельного доступа к данным, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] потребителем поставщика OLE DB для собственного клиента должен интеллектуально управлять запросами для конкретных уровней параллелизма.  
  
> [!NOTE]  
>  В [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] появился уровень изоляции моментального снимка. Дополнительные сведения см. в разделе [работа с изоляцией моментального снимка](../native-client/features/working-with-snapshot-isolation.md).  
  
## <a name="see-also"></a>См. также  
 [Transactions](transactions.md)  
  
  
