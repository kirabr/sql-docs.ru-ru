---
title: MSSQLSERVER_833 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: language-reference
helpviewer_keywords:
- 833 (Database Engine error)
ms.assetid: 14129cc4-be80-4772-9e3f-0e5da4d0696b
caps.latest.revision: 19
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 4a3150b74f2574ffc660ea9013612a5345c26560
ms.sourcegitcommit: ee661730fb695774b9c483c3dd0a6c314e17ddf8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2018
ms.locfileid: "34329885"
---
# <a name="mssqlserver833"></a>MSSQLSERVER_833
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Сведения  
  
|||  
|-|-|  
|Название продукта|SQL Server|  
|Идентификатор события|833|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|BUF_LONG_IO|  
|Текст сообщения|SQL Server обнаружил запросы ввода-вывода (%d), занявшие более %d с, для завершения обработки файла [%ls] в базе данных `[%ls] (%d)`.  Дескриптором файла ОС является 0x%p.  Смещение последней длительной операции ввода-вывода: %#016I64x.|  
  
## <a name="explanation"></a>Объяснение  
Это сообщение указывает, что [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] издал запрос чтения или записи на диск, и выполнение запроса заняло более 15 секунд. Данная ошибка возвращается [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и говорит о проблеме с подсистемой ввода-вывода.  
  
### <a name="possible-causes"></a>Возможные причины  
Причиной этой ошибки могут быть проблемы с производительностью системы, ошибки оборудования, ошибки встроенного ПО, проблемы с драйверами устройств или вмешательство фильтров в процессы ввода-вывода.  
  
## <a name="user-action"></a>Действие пользователя  
Для устранения этой ошибки найдите в журнале системных событий сообщения об ошибках, связанных с оборудованием. Также изучите журналы оборудования, если они доступны.  
  
При помощи системного монитора проверьте следующие счетчики.  
  
-   **Среднее время обращения к диску (сек)**  
  
-   **Средняя длина очереди диска**  
  
-   **Текущая длина очереди диска**  
  
Например, на компьютере, где выполняется [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], значение **среднего времени обращения к диску** обычно не превышает 15 миллисекунд. Если значение **среднего времени обращения к диску** увеличивается, значит подсистема ввода-вывода не справляется с числом запросов на операции ввода-вывода.  
  
> [!NOTE]  
> Доступ к диску может замедляться антивирусной программой. Чтобы увеличить скорость доступа, исключите из активных заданий сканирования на вирусы файлы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], указанные в сообщении об ошибке.  
  
Дополнительные сведения об ошибках ввода-вывода см. в [главе 2 документации Microsoft SQL Server по основным операциям ввода-вывода](http://go.microsoft.com/fwlink/?LinkId=69370) и в статье базы знаний по адресу [http://support.microsoft.com/kb/897284/en-us](http://support.microsoft.com/kb/897284/en-us).  
  
