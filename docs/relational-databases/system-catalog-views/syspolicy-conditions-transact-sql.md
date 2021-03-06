---
title: syspolicy_conditions (Transact-SQL) | Документы Microsoft
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-catalog-views
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- syspolicy_conditions
- syspolicy_conditions_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- syspolicy_conditions view
ms.assetid: af97d26c-4bd5-4b08-be51-8419e3b2832c
caps.latest.revision: 22
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 09d52d9a4c4d5005a51057a40c29524301d3fdd4
ms.sourcegitcommit: f1caaa156db2b16e817e0a3884394e7b30fb642f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33220805"
---
# <a name="syspolicyconditions-transact-sql"></a>syspolicy_conditions (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Отображает одну строку для каждого условия управления на основе политик в данном экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. syspolicy_conditions принадлежит схеме dbo в базе данных msdb. Следующая таблица описывает столбцы в представлении syspolicy_conditions.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|condition_id|**int**|Идентификатор условия. Каждое условие представляет собой коллекцию, состоящую из одного или нескольких выражений условий.|  
|имя|**sysname**|Имя условия.|  
|date_created|**datetime**|Дата и время создания условия.|  
|description|**nvarchar(max)**|Описание условия. Столбец описания является необязательным и может принимать значение NULL.|  
|created_by|**sysname**|Имя пользователя, создавшего условие.|  
|modified_by|**sysname**|Имя пользователя, изменившего это условие последним. Содержит значение NULL, если изменений не было.|  
|date_modified|**datetime**|Дата и время создания условия. Содержит значение NULL, если изменений не было.|  
|is_name_condition|**smallint**|Указывает, является ли условие условием именования.<br /><br /> 0 = выражение условия не содержит переменной @Name.<br /><br /> 1 = выражение условия содержит переменную @Name.|  
|аспект|**nvarchar(max)**|Имя аспекта, на котором основано условие.|  
|Выражение|**nvarchar(max)**|Выражение для состояний аспекта.|  
|obj_name|**sysname**|Имя объекта, присвоенного @Name, если выражение условия содержит переменную.|  
  
## <a name="remarks"></a>Замечания  
 При устранении неполадок управления на основе политик, запрос к представлению syspolicy_conditions, чтобы определить, кто создал или изменил условие последнего.  
  
## <a name="permissions"></a>Разрешения  
 Требуется членство в роли PolicyAdministratorRole базы данных msdb.  
  
## <a name="see-also"></a>См. также  
 [Администрирование серверов с помощью управления на основе политик](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md)   
 [Административные представления на основе политик (Transact-SQL)](../../relational-databases/system-catalog-views/policy-based-management-views-transact-sql.md)  
  
  
