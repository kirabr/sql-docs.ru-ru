---
title: Параметры миграции данных (MySQLToSQL) | Документация Майкрософт
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.technology: ssma
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 9c396df4-5676-4f32-9c57-70d4f15f9b7a
caps.latest.revision: 9
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: a5590adadc1436d616d73b275ad90359b6e64d88
ms.sourcegitcommit: c7a98ef59b3bc46245b8c3f5643fad85a082debe
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2018
ms.locfileid: "38984606"
---
# <a name="data-migration-settings-mysqltosql"></a>Параметры миграции данных (MySQLToSQL)
  
## <a name="data-migration-settings"></a>Параметры миграции данных  
**Параметры миграции данных** позволяет пользователю создавать пользовательские запросы для переноса данных.  
  
-   Эта вкладка доступна, когда **расширенных параметров переноса данных** присваивается **Показать** , отображается, если параметр имеет значение **скрыть** в параметрах проекта. Дополнительные сведения о параметрах проекта миграции см. в разделе [параметры проекта (миграция)](http://msdn.microsoft.com/2a3cba9e-cd54-4a8b-b858-8fc4cf2580d9) .  
  
-   Синтаксический анализ инструкций Custom SQL будут реализованы в **параметры миграции данных** вкладке узел таблицы.  
  
-   Ниже приведены два флажка, доступных в **параметры миграции данных** находящие отклик у.:  
  
    1.  Усечение таблицы SQL Server  
  
    2.  Используйте настраиваемые выберите  
  
1.  **Усечение таблицы SQL Server:**  
     Этот параметр позволяет пользователю четкое представление о перенесенных данных в целевую базу данных.  
  
    -   По умолчанию проверяется этому текстовому полю.  
  
    -   Если это текстовое поле не установлен, данные, которые переносятся будут добавляться на существующие данные в целевую базу данных.  
  
2.  **Используйте настраиваемые выберите:**  
     Этот параметр позволяет пользователю изменить **выберите** присутствует инструкция (**выберите** инструкция позволяет пользователям для выбора данных, которое должно отображаться в целевой базе данных).  
  
    1.  По умолчанию это текстовое поле не установлен.  
  
    2.  Если установлен этот textbox, то она позволяет пользователям изменять **выберите** присутствует инструкция.  
  
Существуют две кнопки присутствует находящие отклик у.:  
  
-   **Применить:** щелкните **применить** для применения параметров, которые были изменены.  
  
-   **Отмена:** щелкните **отменить** восстановления присутствует параметров, прежде чем были внесены изменения.  
  
## <a name="see-also"></a>См. также  
[Перенос данных MySQL в SQL Server/SQL Azure](http://msdn.microsoft.com/a6a7f4d6-68aa-4a38-93bf-53eba0d7dc82)  
  
