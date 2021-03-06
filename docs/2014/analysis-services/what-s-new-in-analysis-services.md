---
title: Что&#39;возможности служб Analysis Services и бизнес-аналитики | Документация Майкрософт
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: aa69c299-b8f4-4969-86d8-b3292fe13f08
caps.latest.revision: 14
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 30789972454ecc6c32ef4cb109bfbb20a2523e37
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37323114"
---
# <a name="what39s-new-in-analysis-services-and-business-intelligence"></a>Что&#39;возможности служб Analysis Services и бизнес-аналитики
  За исключением добавленной функции поддержки отчетов Power View в многомерных моделях [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] не отличается от предыдущего выпуска.  
  
 Дополнительные сведения о других [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] продуктов и технологий, которые отличаются в этом выпуске см. в разделе [новые возможности в SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).  
  
## <a name="updates-to-design-tool-installation"></a>Изменения установки средства проектирования  
 Среда [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] для бизнес-аналитики (SSDT-BI), которая ранее называлась Business Intelligence Development Studio (BIDS), используется для создания моделей служб Analysis Services, отчетов служб Reporting Services и пакетов служб Integration Services. Загрузить SSDT-BI можно из следующих расположений:  
  
-   [Скачать SSDT-BI для Visual Studio 2013](http://go.microsoft.com/fwlink/p/?LinkId=396526)  
  
-   [Скачать SSDT-BI для Visual Studio 2012](http://go.microsoft.com/fwlink/p/?LinkID=273673)  
  
 Если на компьютере установлена прежняя версия SSDT-BI или BIDS, то новая версия устанавливается параллельно с предыдущей. Часто новые и старые версии средств проектирования используются на одной рабочей станции, чтобы можно было работать с проектами и решениями, которые рассчитаны на определенную версию сервера.  
  
> [!NOTE]  
>  Имеется несколько сайтов для загрузки версий SSDT для Visual Studio 2012 и для Visual Studio 2013. Большинство загрузок не содержат шаблоны проектов бизнес-аналитики. С помощью приведенных выше ссылок можно получить правильную версию. Чтобы узнать, установлена ли правильная версия SSDT-BI, проверьте папку шаблонов проектов бизнес-аналитики. Эта папка содержит шаблоны проектов для служб Analysis Services, Reporting Services и Integration Services. В зависимости от способа установки SSDT-BI также может отображаться дополнительный шаблон проекта для баз данных SQL Server.  
  
 ![Новые шаблоны проекта в SSDT](media/ssdt-biprojects.png "Новые шаблоны проекта в SSDT")  
  
## <a name="features-recently-added-power-view-for-multidimensional-models"></a>Недавно добавленные функции: Power View для многомерных моделей  
 Возможность создания отчетов Power View на основе многомерных моделей впервые появилась в накопительном обновлении 4 с пакетом обновления 1 (SP1) для [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]. Power View для многомерных моделей теперь является частью [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].  
  
 **Отчет Power View для многомерных моделей**  
  
 ![Отчет Power View](media/powerviewreport-wn.gif "отчет Power View")  
  
 Эта функция позволяет организациям максимально эффективно использовать инвестиции в средства бизнес-аналитики, позволяя использовать многомерные модели (кубы OLAP) с последними версиями клиентских средств отчетности. В зависимости от типов данных в многомерной модели пользователи могут легко создавать различные динамические визуализации данных — от таблиц и матриц до пузырьковых диаграмм и географических карт. Теперь многомерные модели также поддерживают запросы с использованием выражений анализа данных (DAX).  
  
 Power View для многомерных моделей требуются встроенные возможности создания отчетов Power View в [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] (в режиме интеграции с SharePoint). Другие версии Power View, в частности надстройка Power View в Excel 2013, не поддерживают многомерные модели.  
  
 Дополнительные сведения см. в разделе [Power View для многомерных моделей](http://msdn.microsoft.com/library/dn140246.aspx).  
  
  
