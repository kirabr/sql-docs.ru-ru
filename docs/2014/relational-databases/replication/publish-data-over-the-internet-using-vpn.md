---
title: Публикация данных через Интернет с помощью виртуальных частных сетей | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- VPNs [SQL Server replication]
- Web publishing [SQL Server replication], VPNs
- Internet [SQL Server replication], VPNs
ms.assetid: 9ffb6546-9973-4574-aaa0-8fe0017e3601
caps.latest.revision: 32
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 0e4893511cb952fb40fe129fd4e8b8c8f67502c6
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37199164"
---
# <a name="publish-data-over-the-internet-using-vpn"></a>Публикация данных через Интернет с помощью виртуальных частных сетей
  Обеспечивая защищенный обмен данными, технология виртуальных частных сетей (Virtual Private Networking, VPN) предоставляет работающим дома пользователям, филиалам компании, удаленным пользователям и другим компаниям возможность подключения к корпоративной сети через Интернет. Пользователи могут использовать проверку подлинности Windows, как если бы они находились в локальной сети. Репликации [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] всех типов могут реплицировать данные через виртуальную частную сеть, но для репликации слиянием необходимо предусмотреть веб-синхронизацию, так как в этом случае применение виртуальной частной сети не требуется. Дополнительные сведения см. в статье [Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md).  
  
 Виртуальная частная сеть включает клиентское программное обеспечение, так что компьютеры подключаются к программному обеспечению выделенного компьютера или сервера через Интернет (или, в особых случаях, даже через корпоративную сеть). При желании можно использовать как шифрование с обеих сторон, так и пользовательские методы проверки подлинности. Соединение с виртуальной частной сетью через Интернет логически функционирует как соединение глобальной сети (WAN) между сайтами.  
  
 Виртуальная частная сеть связывает компоненты сети с помощью другой сети. Чтобы подключиться, пользователь осуществляет связь через Интернет или иную общедоступную сеть, используя протоколы, такие как [!INCLUDE[msCoName](../../includes/msconame-md.md)] PPTP (Point-to-Point Tunneling Protocol) или L2TP (Layer Two Tunneling Protocol). Этот процесс предоставляет такую же безопасность и возможности, которые были доступны ранее только в частных сетях. Протокол PPTP доступен в операционных системах Microsoft Windows NT 4.0 и [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2000 (или более поздних версиях); протокол L2TP доступен в операционных системах Windows 2000 (или более поздних версиях).  
  
 Промежуточная инфраструктура маршрутизации Интернета остается невидимой для пользователя и ему кажется, будто данные посылаются через выделенную частную линию. С точки зрения пользователей виртуальная частная сеть представляет собой двухточечное соединение между компьютером пользователя и корпоративным сервером.  
  
 После того как у удаленного клиента выполнена настройка для подключения с использованием виртуальной частной сети и клиент, имеющий доступ в Интернет, зарегистрировался в корпоративной сети, можно настроить репликацию так, будто удаленный пользователь напрямую подключен к локальной сети. По соображениям безопасности можно предоставить доступ к разным сетевым ресурсам для пользователей, подключающихся через виртуальную частную сеть и для тех, кто подключается непосредственно к локальной сети.  
  
 Дополнительные сведения о настройке виртуальных частных сетей см. в документации по [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.  
  
## <a name="see-also"></a>См. также  
 [Репликация через Интернет](replication-over-the-internet.md)  
  
  
