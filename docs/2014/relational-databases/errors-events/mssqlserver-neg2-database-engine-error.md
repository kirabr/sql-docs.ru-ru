---
title: MSSQLSERVER_-2 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- "2"
helpviewer_keywords:
- -2 (Database Engine error)
ms.assetid: f37a7b7d-26e1-4b9e-bcb4-57f7805393d2
caps.latest.revision: 10
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 38c551b7d45d18a7c60ab3de15b62c27f80f521e
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2018
ms.locfileid: "37410903"
---
# <a name="mssqlserver-2"></a>MSSQLSERVER_-2
    
## <a name="details"></a>Сведения  
  
|||  
|-|-|  
|Название продукта|SQL Server|  
|Идентификатор события|-2|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя||  
|Текст сообщения|Время ожидания истекло.  Время ожидания истекло до завершения операции, либо сервер не отвечает. (Microsoft SQL Server, ошибка: –2)|   
  
## <a name="explanation"></a>Объяснение  
 Клиенту [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не удается установить соединение с сервером. Эта ошибка возникает, если брандмауэр сервера отказывает в соединении. 
  
## <a name="user-action"></a>Действие пользователя  
 Убедитесь, что в брандмауэре на экземпляре сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] разрешен прием соединений.  
  
## <a name="see-also"></a>См. также  
 [Настройка брандмауэра Windows для разрешения доступа к SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md)   
 [Настройка брандмауэра Windows для доступа к ядру СУБД](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md)   
 [Настройка клиентских протоколов](../../database-engine/configure-windows/configure-client-protocols.md)   
 [Сетевые протоколы и библиотеки](../../sql-server/install/network-protocols-and-network-libraries.md)   
 [Конфигурация клиентской сети](../../database-engine/configure-windows/client-network-configuration.md)   
 [Настройка клиентских протоколов](../../database-engine/configure-windows/configure-client-protocols.md)   
 [Включение или отключение сетевого протокола сервера](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
