---
title: sys.fn_translate_permissions (Transact-SQL) | Документы Microsoft
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-functions
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sys.fn_translate_permissions
- sys.fn_translate_permissions_TSQL
- fn_translate_permissions
- fn_translate_permissions_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- permissions bitmask [SQL Server]
- sys.fn_translate_permissions function
- fn_translate_permissions function
ms.assetid: ac97121f-2bd0-4f71-8e45-42c8584edbc5
caps.latest.revision: 18
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 56fe5c1054bdf41af5708981e6377ae7175e4210
ms.sourcegitcommit: f1caaa156db2b16e817e0a3884394e7b30fb642f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33233072"
---
# <a name="sysfntranslatepermissions-transact-sql"></a>sys.fn_translate_permissions (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Преобразует битовую маску разрешений, возвращаемую трассировкой SQL, в таблицу имен разрешений.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sys.fn_translate_permissions ( level , perms )  
```  
  
## <a name="arguments"></a>Аргументы  
 *level*  
 Вид защищаемого объекта, к которому применяется разрешение. *уровень* — **nvarchar(60)**.  
  
 *perms*  
 Битовая маска, возвращаемая в столбце разрешений. *perms* — **varbinary(16)**.  
  
## <a name="returns"></a>Возвращает  
 **table**  
  
## <a name="remarks"></a>Замечания  
 Значение, возвращаемое в **разрешений** столбца трассировки SQL, является целочисленным представлением битовой маски, используемый [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для вычисления эффективных разрешений. Каждый из 25 вида защищаемых объектов имеет собственный набор разрешений с соответствующими числовыми значениями. **sys.fn_translate_permissions** преобразует эту битовую маску в таблицу имен разрешений.  
  
## <a name="permissions"></a>Разрешения  
 Необходимо быть членом роли **public** .  
  
## <a name="example"></a>Пример  
 В следующем запросе используется `sys.fn_builtin_permissions` для отображения разрешения, относящиеся к сертификатам и затем использует `sys.fn_translate_permissions` для возврата результатов битовую маску разрешений.  
  
```  
SELECT * FROM sys.fn_builtin_permissions('CERTIFICATE');  
SELECT '0001' AS Input, * FROM sys.fn_translate_permissions('CERTIFICATE', 0001);  
SELECT '0010' AS Input, * FROM sys.fn_translate_permissions('CERTIFICATE', 0010);  
SELECT '0011' AS Input, * FROM sys.fn_translate_permissions('CERTIFICATE', 0011);  
```  
  
## <a name="see-also"></a>См. также  
 [Разрешения (компонент Database Engine)](../../relational-databases/security/permissions-database-engine.md)   
 [sys.server_permissions (Transact-SQL)](../../relational-databases/system-catalog-views/sys-server-permissions-transact-sql.md)   
 [sys.database_permissions (Transact-SQL)](../../relational-databases/system-catalog-views/sys-database-permissions-transact-sql.md)  
  
  
