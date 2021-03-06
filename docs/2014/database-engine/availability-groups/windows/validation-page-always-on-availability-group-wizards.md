---
title: Страница проверки (мастера групп доступности AlwaysOn) | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: high-availability
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.newagwizard.validation.f1
- sql12.swb.addreplicawizard.validation.f1
- sql12.swb.adddatabasewizard.validation.f1
helpviewer_keywords:
- ', listeners'
ms.assetid: c8971556-240c-491a-bc86-9cc72f71a3dd
caps.latest.revision: 13
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 75d7350d12f2132a69e74f78223f844ba7580b42
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37280250"
---
# <a name="validation-page-alwayson-availability-group-wizards"></a>Страница проверки (мастера групп доступности AlwaysOn)
  В этом разделе описываются параметры, приведенные на странице **Проверка** . Эта тема относится к [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)], [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)]и [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]. Используйте эту страницу для проверки поддержки средой всех вариантов конфигурации, выбранных на предыдущей странице мастера.  
  
##  <a name="PageOptions"></a> Параметры страницы проверки  
 **Результаты проверки группы доступности.**  
 В этой сетке отображаются результаты каждого завершенного этапа проверки. Сетка содержит следующие столбцы.  
  
 **Название**  
 Отображает фразу, которая описывает конкретный шаг.  
  
 **Результат**  
 Отображает один из следующих текстов гиперссылки. Дополнительные сведения данного шага проверки можно просмотреть, щелкнув гиперссылку.  
  
|Результат|Описание|  
|------------|-----------------|  
|**Ошибка**|Указывает, что шаг проверки выполнен неудачно. Щелкните ссылку, чтобы просмотреть сообщение об ошибке.|  
|**Пропущено**|Указывает, что шаг проверки был пропущен, поскольку он не был отмечен в параметрах как необходимый. Щелкните ссылку для просмотра причины, по которой шаг был пропущен.|  
|**Успешно**|Указывает, что шаг проверки завершен удачно.|  
|**Предупреждение**|Указывает на наличие потенциальной проблемы с конфигурацией группы доступности.  Щелкните ссылку, чтобы просмотреть предупреждение.|  
  
 **Запустите проверку повторно**  
 Щелкните, чтобы повторить шаги проверки, если в ответ на выявленную ошибку были внесены изменения без использования средств мастера.  
  

  
##  <a name="RelatedTasks"></a> Связанные задачи  
  
-   [Использование диалогового окна "Создание группы доступности" (среда SQL Server Management Studio)](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [Использование мастера добавления реплики в группу доступности (среда SQL Server Management Studio)](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [Использование мастера добавления базы данных в группу доступности (среда SQL Server Management Studio)](availability-group-add-database-to-group-wizard.md)  
  
 
  
## <a name="see-also"></a>См. также  
 [Обзор групп доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md)  
  
  
