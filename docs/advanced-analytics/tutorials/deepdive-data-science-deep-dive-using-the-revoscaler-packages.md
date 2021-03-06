---
title: Руководство по RevoScaleR функции с помощью машинного обучения SQL Server | Документация Майкрософт
description: В этом учебнике вы научитесь вызовите функцию RevoScaleR в машинного обучения SQL Server с помощью R поддерживаются включена.
ms.prod: sql
ms.technology: machine-learning
ms.date: 07/15/2018
ms.topic: tutorial
author: HeidiSteen
ms.author: heidist
manager: cgronlun
ms.openlocfilehash: 4aa45d7ee690d55672c86be256e66d454860c2b6
ms.sourcegitcommit: b8e2e3e6e04368aac54100c403cc15fd4e4ec13a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "45563902"
---
# <a name="tutorial-use-revoscaler-r-functions-with-sql-server-data"></a>Руководство: Функции RevoScaleR использующих R с данными SQL Server
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

RevoScaleR — это пакет Microsoft R, предоставляя распределенной и параллельной обработки для обработки и анализа данных и машинного обучения рабочих нагрузок. Для разработки R в SQL Server, RevoScaleR является одним из основных встроенных пакетов, с функциями для настройки контекста вычислений, управление пакетами и самое главное: работа с данных end-to-end, из импорта для визуализации и анализа. Алгоритмы машинного обучения в SQL Server имеет зависимости от источников данных RevoScaleR. Важность RevoScaleR, зная, когда и как вызывать его функции является важным навыком. 

В этом руководстве вы узнаете, как создать контекст удаленных вычислений, перемещать данные между контекстами локальных и удаленных вычислений и выполнять код R на удаленном экземпляре SQL Server. Вы также узнаете, как анализировать и отображать данные как локально, так и на удаленном сервере, а также как создавать и развертывать модели.

+ Данные изначально получаются из CSV- или XDF-файлов. Импортировать данные в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью функций из пакета RevoScaleR.
+ Обучение и оценка модели выполняется с помощью [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] контекста вычислений. 
+ Использование функций RevoScaleR для создания новых [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] таблицы для сохранения результатов оценки.
+ Создание графиков обоих на сервере и в локальном контексте вычислений.
+ Обучить модель на основе данных в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] базы данных, выполнении кода R в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] экземпляра.
+ Извлечение подмножества данных и сохраните его как файл XDF для повторного использования при анализе на локальной рабочей станции.
+ Получить новые данные для оценки, откройте подключение ODBC к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] базы данных. Оценка выполняется на локальной рабочей станции.
+ Создайте пользовательскую функцию R и запустите его на сервере контекста вычислений для выполнения моделирования.

## <a name="target-audience"></a>Целевая аудитория

Этот учебник предназначен для специалистов по анализу данных или для тех, кто знаком с языком R и выполнять задачи обработки и анализа данных, например сводок и создания модели. Тем не менее весь код предоставляется, поэтому даже если вы не знакомы с R, можно выполнить код и дальнейшей работы при условии наличия необходимых серверных и клиентских сред.

Вы также должны чувствовать себя комфортно с [!INCLUDE[tsql](../../includes/tsql-md.md)] синтаксис и знать, как получить доступ к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] базы данных с помощью средств, таких:

+ [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] 
+ Инструменты для баз данных в Visual Studio 
+ Бесплатный [расширение mssql для Visual Studio Code](https://docs.microsoft.com/sql/linux/sql-server-linux-develop-use-vscode).
  
> [!TIP]
> Сохраняйте рабочее пространство R после прохождения уроков, чтобы можно было легко продолжить работу с того места, на котором вы остановились.

## <a name="prerequisites"></a>предварительные требования

- **SQL Server с поддержкой языка R**
  
    Установка [службы машинного обучения SQL Server 2017](../install/sql-machine-learning-services-windows-install.md) с помощью функции R, или установите [SQL Server 2016 R Services (в базе данных)](../install/sql-r-services-windows-install.md).

    Убедитесь в том, что внешние сценарии разрешены, запущена служба панели запуска и наличие разрешений для доступа к службе.
  
-  **Разрешения базы данных**
  
    Для выполнения запросов, используемых для обучения модели, требуются права **db_datareader** в базе данных, в которой хранятся данные. Чтобы запустить R, ваш пользователь должен иметь разрешение EXECUTE ANY EXTERNAL SCRIPT.

-   **Компьютер разработки обработки и анализа данных**
  
    Чтобы переключаться между контекстами локальных и удаленных вычислений, вам потребуется две системы. Локальным обычно называется рабочей станции разработки с недостаточно заряда аккумулятора для рабочих нагрузок обработки и анализа данных. Удаленный в этом случае SQL Server 2017 или SQL Server 2016 с включенной функцией R. 
    
    Переключение контекстов вычисления объявлено в необходимости RevoScaleR же версии на локальных и удаленных системах. На локальной рабочей станции, можно получить пакеты RevoScaleR и связанные поставщики путем установки или с помощью любого из следующих: [виртуальной Машины обработки и анализа данных в Azure](https://docs.microsoft.com/azure/machine-learning/data-science-virtual-machine/overview), [Microsoft R Client (бесплатно)](https://docs.microsoft.com/machine-learning-server/r-client/what-is-microsoft-r-client), или [ Microsoft Machine Learning Server (изолированный)](https://docs.microsoft.com/machine-learning-server/install/machine-learning-server-install). Значение параметра автономного сервера установите бесплатный developer edition на языке Windows или Linux-установщики. Программа установки SQL Server может использоваться для установки изолированного сервера.
      
-   **Дополнительные пакеты R**
  
    В этом руководстве вы установите следующие пакеты: **dplyr**, **ggplot2**, **ggthemes**, **reshape2**, и **e1071** . Инструкции приводятся в рамках учебника.
  
    Все пакеты должны быть установлены в двух местах: на рабочей станции, используемом для разработки решений R и на компьютере SQL Server, где выполняются R-скриптов. Если у вас нет разрешения на установку пакетов на компьютере сервера, попросите администратора. 
    
    **Не устанавливайте эти пакеты в пользовательской библиотеке.** Пакеты должны устанавливаться в библиотеке пакетов R, который используется экземпляром SQL Server.

## <a name="r-development-tools"></a>Средства разработки R

Обычно разработчикам R использовать интегрированные среды разработки для написания и отладки кода на языке R. Вот несколько советов:

- **Инструменты R для Visual Studio** (RTVS) — это бесплатный подключаемый модуль, который предоставляет Intellisense, отладку и поддержку Microsoft R. Его можно использовать с R Server и службы машинного обучения SQL Server. Чтобы скачать эти средства, перейдите на страницу [Средства R для Visual Studio](https://www.visualstudio.com/vs/rtvs/).

- **RStudio** — одна из наиболее популярных сред для разработки на языке R. Дополнительные сведения см. в разделе [ https://www.rstudio.com/products/RStudio/ ](https://www.rstudio.com/products/RStudio/).

- Базовые средства R (R.exe, RTerm.exe, RScripts.exe) также устанавливаются по умолчанию при установке R в SQL Server или R Client. Если вы не хотите устанавливать интегрированную среду разработки, можно использовать встроенные средства R для выполнения кода в этом руководстве.

Помните, что требуется RevoScaleR на локальных и удаленных компьютерах. Не удается завершить этот учебник, с помощью универсальной установки RStudio или другой среды, в котором отсутствует библиотеки Microsoft R. Дополнительные сведения см. в разделе [Настройка клиента обработки и анализа данных](../r/set-up-a-data-science-client.md).

## <a name="next-steps"></a>Следующие шаги

> [!div class="nextstepaction"]
> [Занятие 1: Создание базы данных и разрешения](deepdive-work-with-sql-server-data-using-r.md)

