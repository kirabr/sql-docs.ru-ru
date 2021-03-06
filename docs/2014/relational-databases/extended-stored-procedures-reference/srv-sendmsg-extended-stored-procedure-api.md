---
title: srv_sendmsg (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
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
api_name:
- srv_sendmsg
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_sendmsg
ms.assetid: efcb50b9-f8ff-4121-bf67-05830171b928
caps.latest.revision: 30
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: b7f30a780f0428754af82c6adf57fb1d4efd35fb
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37240734"
---
# <a name="srvsendmsg-extended-stored-procedure-api"></a>srv_sendmsg (API-интерфейс расширенных хранимых процедур)
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Используйте вместо этого интеграцию со средой CLR.  
  
 Отправляет клиенту сообщение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
int srv_sendmsg (  
SRV_PROC *  
srvproc  
,  
int  
msgtype  
,  
DBINT  
msgnum  
,  
DBTINYINT  
class  
,   
DBTINYINT  
state  
,  
DBCHAR *  
rpcname  
,  
int   
rpcnamelen  
,  
DBUSMALLINT  
linenum  
,  
DBCHAR *  
message  
,  
int  
msglen   
);  
  
```  
  
## <a name="arguments"></a>Аргументы  
 *srvproc*  
 Указатель на структуру SRV_PROC, который представляет собой дескриптор соединения с клиентом (в данном случае — дескриптор, который получил запрос языка). Структура содержит сведения, которые используются библиотекой API-интерфейса расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.  
  
 *msgtype*  
 Является либо SRV_MSG_INFO, либо SRV_MSG_ERROR, в зависимости от того, отправляет сервер информационное сообщение или сообщение об ошибке.  
  
 *msgnum*  
 4-байтовый номер сообщения.  
  
 *class*  
 Указывает серьезность ошибки. Серьезность, меньше или равная 10, считается информационным сообщением.  
  
 *state*  
 Предоставляет код состояния ошибки для текущего сообщения. Код состояния ошибки предоставляет информацию о контексте ошибки. Допустимые значения кода состояния — от 0 до 255.  
  
 *rpcname*  
 Не поддерживается в текущей версии.  
  
 *rpcnamelen*  
 Не поддерживается в текущей версии.  
  
 *linenum*  
 Представляет собой номер строки в пакете языковых команд, к которому относится сообщение. Номера строк начинаются с 1. Если параметр *linenum* не применяется к сообщению, установите его равным 0.  
  
 *message*  
 Является указателем на символьную строку, которая должна быть отправлена клиенту.  
  
 *msglen*  
 Задает длину *message* в байтах. Если *message*заканчивается нулевым байтом, задайте для параметра *msglen* значение SRV_NULLTERM.  
  
## <a name="returns"></a>Возвращает  
 SUCCEED или FAIL  
  
## <a name="remarks"></a>Примечания  
 Эта функция отправляет клиенту сообщение об ошибке или информационное сообщение. Она вызывается один раз для каждой отправки сообщения.  
  
 Можно отправлять сообщения клиенту при помощи функции **srv_sendmsg** в любой последовательности перед тем или после того, как были отправлены все строки (если таковые были) при помощи функции **srv_sendrow**. Все сообщения, если таковые имеются, должны быть отправлены клиенту перед тем, как функция **srv_senddone** отправит состояние завершения.  
  
 Для отправки сообщений в Юникоде лучше использовать функцию **srv_wsendmsg**, чем функцию **srv_sendmsg**.  
  
 Дополнительные сведения см. в статье [Данные в Юникоде и кодовые страницы сервера](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).  
  
> [!IMPORTANT]  
>  Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер. Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](http://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409http://msdn.microsoft.com/security/).  
  
  
