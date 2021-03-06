---
title: Использование WQL и языков сценариев с поставщиком WMI для управления конфигурацией | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- queries [WMI]
- scripts [WMI]
- query language [WMI]
- WMI Query Language [WMI]
- WQL [WMI]
- WMI Provider for Configuration Management, WQL
- WMI Provider for Configuration Management, scripts
ms.assetid: c1e64905-3c2b-4974-88f4-abf17cf7e289
caps.latest.revision: 17
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: 7a55fc42e5186615dbe3e455668eb8cc5f7c199c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37202884"
---
# <a name="using-wql-and-scripting-languages-with-the-wmi-provider-for-configuration-management"></a>Использование WQL и языков сценариев с поставщиком WMI для управления конфигурациями
  Управляющие приложения получают доступ к службам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и сетевым настройкам, используя поставщик инструментария управления Windows (WMI) для объектов управления конфигурацией двумя способами.  
  
-   С помощью редактора WQL или средства создания запросов, например WBEMTest.exe, создается запрос к набору объектов на языке WQL (языке запросов к инструментарию управления Windows).  
  
-   С помощью языка для создания сценариев (например, VBScript).  
  
 Другой способ — управлять службами и сетевыми настройками [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] программным образом, используя управляемые объекты WMI в SMO. Дополнительные сведения о программировании WMI управляемых объектов, см. в разделе [управление службами и сетевыми настройками с помощью поставщика WMI](../server-management-objects-smo/tasks/managing-services-and-network-settings-by-using-wmi-provider.md).  
  
 Поставщик WMI для управления конфигурацией может осуществляться с помощью [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager и [!INCLUDE[msCoName](../../includes/msconame-md.md)] консоли управления. Дополнительные сведения о доступе к поставщику WMI с помощью пользовательского интерфейса см. в разделе [разделы руководства по управлению службами &#40;диспетчер конфигурации SQL Server&#41;](../../database-engine/managing-services-how-to-topics-sql-server-configuration-manager.md).  
  
## <a name="see-also"></a>См. также  
 [Доступ к поставщику WMI для управления конфигурацией с использованием WQL](access-wmi-provider-for-configuration-management-using-wql.md)   
 [Изменение расширенных свойств службы SQL Server с помощью VBScript](access-wmi-provider-for-configuration-management-using-vbscript.md)  
  
  
