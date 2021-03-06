---
title: Соединение с базой данных Informix (SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.conninformixdb.f1
ms.assetid: b01d537c-1c04-4d7d-9146-051c249b08e4
caps.latest.revision: 10
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: c36a378d229b30d65113512581d52c13deef1b6c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37216194"
---
# <a name="connect-to-an-informix-database-ssas"></a>Соединени с базой данных Informix (SSAS)
  Эта страница **мастера импорта таблиц** используется для задания параметров для соединения с базой данных Informix. Для доступа к мастеру из [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.  
  
 Для соединения с источником данных на компьютере должен быть установлен соответствующий поставщик.  
  
> [!NOTE]  
>  При выборе базы данных на этой странице используются учетные данные текущего пользователя. Тем не менее импорт не будет успешным, если пользователь, указанный на странице сведений об олицетворении, не имеет достаточных прав для чтения из выбранной базы данных.  
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
 **Понятное имя соединения**  
 Введите уникальное имя для соединения с источником данных. Это поле является обязательным.  
  
 **Имя сервера**  
 Введите или выберите имя экземпляра сервера для подключения.  
  
 **Имя пользователя**  
 Укажите имя пользователя для подключения к базе данных.  
  
 Это имя пользователя используется при создании строки подключения для источника данных. Эти учетные данные также используются при просмотре и фильтрации данных в окне «Свойства таблицы» и в мастере импорта. Эти учетные данные не используются для импорта или обновления данных. Вместо них используются учетные данные Windows, указанные на странице сведений об олицетворении.  
  
 **Пароль**  
 Укажите пароль для подключения к базе данных.  
  
 **Сохранить пароль**  
 Укажите, нужно ли сохранить пароль, введенный в поле **Пароль** .  
  
 **Дополнительно**  
 Задайте дополнительные свойства соединения в диалоговом окне **Задание дополнительных свойств** . Дополнительные сведения см. в разделе [Установка дополнительных свойств (SSAS)](set-advanced-properties-ssas.md).  
  
 **Проверка соединения**  
 Установите соединение с источником данных с использованием текущих параметров. Появится сообщение об успешном или неуспешном соединении.  
  
  
