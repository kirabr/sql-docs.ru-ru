---
title: Принудительный опрос главного сервера целевым сервером | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- forcing master server polling
- polling master servers [SQL Server]
- master servers [SQL Server], polling
- target servers [SQL Server], polling the master server
ms.assetid: f1189a47-5ac3-45e2-9c5f-847810672279
caps.latest.revision: 29
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: b7facaebe5395e57b0cc278a8cf75fbe5208efbc
ms.sourcegitcommit: 8ae6e6618a7e9186aab3c6a37ea43776aa9a382b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43814520"
---
# <a name="force-a-target-server-to-poll-the-master-server"></a>Принудительный опрос главного сервера целевым сервером
  В этом подразделе описана реализация принудительного опроса главного сервера целевым сервером. Целевой сервер должен быть зарегистрирован на главном.  
  
 Задание — это указанная последовательность действий, выполняемых агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Многосерверное задание — это задание, которое главный сервер выполняет на одном или нескольких целевых серверах. На каждом целевом сервере может одновременно выполняться только один экземпляр одного и того же задания. Каждый целевой сервер периодически опрашивает главный сервер, загружает копию новых назначенных ему заданий и отключается. Целевой сервер выполняет задание локально, а затем снова подключается к главному серверу, чтобы передать результирующее состояние задания.  
  
> [!NOTE]  
>  Если главный сервер недоступен в момент, когда целевой сервер пытается передать состояние задания, то сведения о состоянии задания помещаются в очередь, пока главный сервер не станет доступен.  
  
-   **Перед началом:**  [Ограничения](#Restrictions), [Безопасность](#Security)  
  
-   **Для принудительного опроса главного сервера целевым сервером с помощью:**[SQL Server Management Studio  ](#SSMS)  
  
##  <a name="BeforeYouBegin"></a> Перед началом  
  
###  <a name="Restrictions"></a> Ограничения  
 Целевой сервер должен быть зарегистрирован на главном. Инструкции, приведенные в этом разделе, необходимо запускать с главного сервера.  
  
###  <a name="Security"></a> безопасность  
 Дополнительные сведения см. в разделах [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) и [Выбор правильной учетной записи службы агента SQL Server для многосерверной среды](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).  
  
##  <a name="SSMS"></a> Использование среды SQL Server Management Studio  
 **Принудительный опрос главного сервера целевым сервером**  
  
1.  В **Обозревателе объектов**разверните главный сервер.  
  
2.  Щелкните правой кнопкой мыши элемент **Агент SQL Server**, укажите пункт **Администрирование нескольких серверов**, а затем выберите пункт **Управление целевыми серверами**.  
  
3.  Щелкните целевой сервер, а затем нажмите кнопку **Опрос**.  
  
  
