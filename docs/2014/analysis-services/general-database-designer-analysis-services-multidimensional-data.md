---
title: Общие (конструктор баз данных) (службы Analysis Services — многомерные данные) | Документация Майкрософт
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
- sql12.asvs.databasedesigner.dbconfigurationpane.f1
helpviewer_keywords:
- Database Designer
ms.assetid: 00c9c42b-db2b-4620-8fb6-1e165ff0cbdd
caps.latest.revision: 25
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 8a2af00d2dcdb6d28ab311067172e808e49539a0
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37234274"
---
# <a name="general-database-designer-analysis-services---multidimensional-data"></a>Общие (конструктор баз данных) (службы Analysis Services — многомерные данные)
  Используйте вкладку **Общие** , чтобы изменить свойства базы данных служб [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .  
  
 **Отображение вкладки «Общие»**  
  
1.  В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .  
  
2.  В **обозревателе решений**щелкните правой кнопкой мыши проект служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , нажмите **Изменить базу данных**, а затем перейдите на вкладку **Общие** .  
  
## <a name="basic-options"></a>Основные параметры  
 Откройте раздел **Основные** для изменения основных сведений о базе данных. Этот подраздел содержит следующие параметры.  
  
 **Имя базы данных**  
 Отображается имя базы данных.  
  
> [!NOTE]  
>  Чтобы переименовать базу данных, щелкните правой кнопкой мыши в окне **Обозреватель решений**нужный проект, затем выберите **Свойства**. В диалоговом окне **Страницы свойств** для этой базы данных на странице **Развертывание** измените свойство **База данных** на ее новое имя.  
  
 **Описание**  
 Введите описание базы данных.  
  
## <a name="translations-options"></a>Параметры перевода  
 Разверните раздел **Переводы** для создания и изменения переводов для заголовка и описания базы данных. Этот раздел содержит сетку со следующими столбцами.  
  
 **Язык**  
 Выберите язык для данной транзакции.  
  
 Чтобы добавить новый перевод в сетке, щелкните  **\<добавить новый перевод >**.  
  
 **Переведенный заголовок**  
 Введите заголовок базы данных на соответствующем языке для перевода. Если это поле оставить пустым, будет использоваться заголовок базы данных по умолчанию.  
  
 **Переведенное описание**  
 Введите описание базы данных на соответствующем языке для перевода. Если это поле оставить пустым, будет использоваться описание базы данных по умолчанию.  
  
## <a name="account-type-mapping-options"></a>Параметры сопоставления типов учетных счетов  
 Разверните раздел **Сопоставление типов учетных записей** , чтобы изменить используемую по умолчанию статистическую функцию, связанную с каждым **типом** учетных записей в выбранной базе данных.  
  
> [!NOTE]  
>  Данный параметр применяется только к кубам, в которых одна или более мер используют статистическую функцию *ByAccount* .  
  
 Этот раздел содержит сетку со следующими столбцами.  
  
 **Название**  
 Введите имя типа учетной записи.  
  
 Чтобы добавить новый тип учетной записи, щелкните  **\<добавить новый тип счета >**.  
  
 **Псевдоним**  
 Задает имя типа учетной записи по умолчанию для использования в мастере бизнес-аналитики. Если оставить этот столбец пустым, будет использоваться столбец **Имя** .  
  
 **Статистическая функция**  
 Задает статистическую функцию, используемую с выбранным типом учетной записи.  
  
## <a name="see-also"></a>См. также  
 [Конструкторы и диалоговые окна служб Analysis Services &#40;многомерных данных&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)   
 [Многомерный шаблон баз данных &#40;SSAS&#41;](multidimensional-models/multidimensional-model-databases-ssas.md)   
 [Предупреждения &#40;базы данных конструктор&#41; &#40;службы Analysis Services — многомерные данные&#41;](warnings-database-designer-analysis-services-multidimensional-data.md)  
  
  
