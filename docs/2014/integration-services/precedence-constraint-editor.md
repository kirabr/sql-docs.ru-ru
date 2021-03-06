---
title: Редактор управления очередностью | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.precedenceconstraint.f1
helpviewer_keywords:
- Precedence Constraint Editor dialog box
ms.assetid: b10d4330-6e35-4037-b309-ef56efcd60c5
caps.latest.revision: 27
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 573ce289579e0d239585f5f4b0f6292a6145b0ae
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37209354"
---
# <a name="precedence-constraint-editor"></a>Редактор управления очередностью
  Диалоговое окно **Редактор ограничений очередностью** используется для настройки ограничений очередностью.  
  
## <a name="options"></a>Параметры  
 **Вычислительная операция**  
 Определяет вычислительную операцию, которую использует ограничение очередностью. Операциями могут быть: **Ограничение**, **Выражение**, **Выражение и ограничение**и **Выражение или ограничение**.  
  
 **Value**  
 Укажите ограничение по значению: **Успешно**, **Сбой**или **Завершение**.  
  
> [!NOTE]  
>  Строка элементов управления очередностью имеет зеленый цвет для значения **Успех**, синий — для значения **Завершение**и выделяется для значения **Неудача**.  
  
 **Выражение**  
 При использовании действий **Выражение**, **Выражение и ограничение**или **Выражение или ограничение**введите выражение или запустите построитель выражений для создания выражения. Выражение должно иметь логическое значение.  
  
 **Тест**  
 Проверка выражения.  
  
 **Логическое И**  
 Выберите, чтобы указать, что несколько ограничений очередности в одном исполняемом объекте должны учитываться вместе. Все аргументы должны иметь `True`.  
  
> [!NOTE]  
>  Этот тип элементов управления очередностью имеет вид сплошной зеленой или синей линии либо выделяется.  
  
 **Логическое ИЛИ**  
 Выберите, чтобы указать, что несколько ограничений очередности в одном исполняемом объекте должны учитываться вместе. По крайней мере одно ограничение должно иметь значение `True`.  
  
> [!NOTE]  
>  Этот тип элементов управления очередностью имеет вид пунктирной зеленой или синей линии либо выделяется.  
  
## <a name="see-also"></a>См. также  
 [Управление очередностью](control-flow/precedence-constraints.md)   
 [Задачи служб Integration Services](control-flow/integration-services-tasks.md)   
 [Контейнеры служб Integration Services](control-flow/integration-services-containers.md)   
 [Выражения служб Integration Services (SSIS)](expressions/integration-services-ssis-expressions.md)  
  
  
