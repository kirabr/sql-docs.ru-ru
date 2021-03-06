---
title: С помощью функции (SQL Server машинного обучения) профилирования кода R | Документы Microsoft
ms.prod: sql
ms.technology: machine-learning
ms.date: 04/15/2018
ms.topic: conceptual
author: HeidiSteen
ms.author: heidist
manager: cgronlun
ms.openlocfilehash: 05689ae356d415f9655b8709c619e40e6d8fa817
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
ms.locfileid: "31202176"
---
# <a name="using-r-code-profiling-functions"></a>С помощью функции профилирования кода R
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

Помимо использования средств и ресурсов SQL Server для отслеживания выполнения скрипта R можно использовать средства обеспечения производительности, входящие в другие пакеты R, чтобы получить дополнительные сведения о внутренних вызовах функций. Здесь приведен перечень некоторых основных ресурсов, чтобы помочь вам приступить к работе. Чтобы ознакомиться с рекомендациями экспертов, мы рекомендуем изучить раздел о [производительности](http://adv-r.had.co.nz/Performance.html) книги Хедли Уикема (Hadley Wickham), посвященной структурам данных R.

## <a name="using-rprof"></a>Использование функции rprof

*rprof* — это функция, входящая в базовый пакет **utils**, который загружается по умолчанию. Одним из преимуществ *rprof* является то, что она выполняет выборку, уменьшая таким образом нагрузку производительности для мониторинга.

Чтобы использовать профилирование R в коде, вызовите эту функцию и укажите ее параметры, включая расположение записываемого файла журнала. Дополнительные сведения см. в справке по *rprof*.

Обычно функция *rprof* осуществляет выписку стека вызовов в файл через указанные интервалы времени. Затем для обработки выходного файла можно использовать функцию *summaryRprof*. 

Вы можете включить и отключить профилирование кода. Чтобы включить профилирование, приостановить его, а затем перезапустить, используйте последовательность вызовов функции *rprof*.

1. Укажите выходной файл профилирования.

    ```R
    varOutputFile <- "C:/TEMP/run001.log")
    Rprof(varOutputFile)
    ```
2. Отключите профилирование:
    ```R
    Rprof(NULL)
    ```
    
3. Перезапустите профилирование:
    ```R
    Rprof(append=TRUE)
    ```


> [!NOTE]
> Чтобы использовать эту функцию, установите Windows Perl на компьютер, где выполняется код. Таким образом, мы советуем выполнить профилирование кода во время его разработки в среде R, а затем развернуть отлаженный код в SQL Server.  


## <a name="r-system-functions"></a>Системные функции R

Язык R содержит множество базовых функций пакета для возврата содержимого системных переменных. 

Например, в качестве части кода R можно использовать `Sys.timezone` для получения сведений о текущем часовом поясе или `Sys.Time` для получения системного времени из R. 

Чтобы получить сведения об отдельных системных функциях R, введите имя функции в качестве аргумента для функции R `help()` в командной строке R.

```R
help("Sys.time")
```

## <a name="debugging-and-profiling-in-r"></a>Отладка и профилирование в R

Установленная по умолчанию документация по Microsoft R Open содержит подробное руководство по разработке расширений языка R, посвященное профилированию и отладке.

Глава доступна также: [https://cran.r-project.org/doc/manuals/r-release/R-exts.html#Debugging](https://cran.r-project.org/doc/manuals/r-release/R-exts.html#Debugging)

### <a name="location-of-r-help-files"></a>Расположение файлов справки R

C:\Program Files\Microsoft SQL Server\MSSQL13.MSSQLSERVER\R_SERVICES\doc\manual



