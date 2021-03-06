---
title: Зашифрованные базы данных с группами доступности AlwaysOn (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: high-availability
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Transparent Data Encryption, AlwaysOn Availability Groups
- TDE, AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 09eb6ebc-3051-4fff-86a5-93524507b1fc
caps.latest.revision: 8
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 548820b9a1cec29b09b55aa4d09f932344f14fef
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37171375"
---
# <a name="encrypted-databases-with-alwayson-availability-groups-sql-server"></a>Зашифрованные базы данных с группами доступности AlwaysOn (SQL Server)
  В этом разделе приведены сведения об использовании зашифрованных или недавно расшифрованных баз данных с использованием [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].  
  
 **В этом разделе.**  
  
-   [Ограничения](#Restrictions)  
  
-   [Связанные задачи](#RelatedTasks)  
  
##  <a name="Restrictions"></a> Ограничения  
  
-   Если база данных зашифрована или содержит ключ шифрования базы данных, то нельзя использовать [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] или [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] для добавления базы данных в группу доступности. Если зашифрованная база данных была расшифрована, то в резервных копиях ее журналов могут содержаться зашифрованные данные. В этом случае выполнение полной начальной синхронизации данных в базе данных может завершиться ошибкой. Причина этого заключается в том, что операции восстановления журнала может потребоваться сертификат, который был использован ключами шифрования базы данных, который в данный момент недоступен.  
  
     Чтобы сделать расшифрованную базу данных доступной для добавления в группу доступности с помощью мастера, выполните следующие шаги.  
  
    1.  Создайте резервную копию журнала базы данных-источника.  
  
    2.  Создайте полную резервную копию базы данных-источника.  
  
    3.  Восстановите резервную копию базы данных на экземпляре сервера, на котором размещается вторичная реплика.  
  
    4.  Создайте новую резервную копию журнала базы данных-источника.  
  
    5.  Восстановите эту резервную копию журнала в базе данных-получателе.  
  
##  <a name="RelatedTasks"></a> Связанные задачи  
  
-   [Подготовка базы данных-получателя для присоединения к группе доступности вручную (SQL Server)](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [Использование мастера групп доступности (среда SQL Server Management Studio)](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [Использование мастера добавления базы данных в группу доступности (среда SQL Server Management Studio)](availability-group-add-database-to-group-wizard.md)  
  
## <a name="see-also"></a>См. также  
 [Обзор групп доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md)   
 [Прозрачное шифрование данных (TDE)](../../../relational-databases/security/encryption/transparent-data-encryption.md)  
  
  
