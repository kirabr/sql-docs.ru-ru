---
title: Параметры для средства проверки конфигурации системы | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- installing SQL Server, system configuration checks
- failed system configuration checks [SQL Server]
- verifying configuration before installation
- SCC [SQL Server]
- system configuration checker
- scanning computer before installation [SQL Server]
- checking configuration before installation
- status information [SQL Server], system configuration checker
- parameters [SQL Server], system configuration checker
- configuration checkers [SQL Server]
- Setup [SQL Server], system configuration checker
ms.assetid: 8e712c15-6bfa-4d71-b303-9526101e5594
caps.latest.revision: 44
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: f3846ae220bc1e0e412185daca57f576a7a2e030
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37197804"
---
# <a name="check-parameters-for-the-system-configuration-checker"></a>Параметры для средства проверки конфигурации системы
  Во время установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] средство проверки конфигурации системы (SCC) просматривает компьютер, на котором устанавливается [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Средство SCC проверяет наличие условий, препятствующих успешной установке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Прежде чем программа установки запустит мастер установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , SCC получает сведения о состоянии каждого элемента. Затем оно сравнивает результаты с требуемыми условиями и предоставляет рекомендации по устранению критических препятствий.  
  
 Средство проверки конфигурации создает отчет, содержащий краткое описание всех выполненных правил и состояние выполнения. Отчет о проверке конфигурации системы находится в каталоге % programfiles %\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\< ггггммдд_ччмм >\\.  
  
## <a name="see-also"></a>См. также  
 [Оборудованию и программному обеспечению для установки SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md)   
 [Вопросы безопасности при установке SQL Server](../../sql-server/install/security-considerations-for-a-sql-server-installation.md)   
 [Поддерживаемые обновления версий и выпусков](supported-version-and-edition-upgrades.md)  
  
  
