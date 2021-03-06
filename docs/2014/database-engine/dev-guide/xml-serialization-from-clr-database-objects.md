---
title: Сериализация XML из объектов базы данных CLR | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- serialization
- XML serialization [CLR integration]
- common language runtime [SQL Server], XML serialization
- XmlSerializer class
ms.assetid: ac84339b-9384-4710-bebc-01607864a344
caps.latest.revision: 19
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 8b59c013a9a21aaa50465acd5a565eda5c1e0653
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37279830"
---
# <a name="xml-serialization-from-clr-database-objects"></a>Сериализация XML из объектов базы данных CLR
  XML-сериализация используется в двух случаях:  
  
-   при вызове веб-служб из объектов среды CLR;  
  
-   для преобразования определяемого пользователем типа данных в XML.  
  
 Выполнение XML-сериализации с помощью вызова класса `XmlSerializer` обычно создает дополнительную сборку сериализации, перегружаемую в проект, содержащий исходную сборку.  Однако в целях безопасности в CLR эта перегрузка отключена. Таким образом для вызова веб-службы или преобразования определяемого пользователем ТИПА в XML внутри [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], следует создать сборку вручную с помощью инструмента **Sgen.exe** поставляемого вместе с .NET Framework, которое создает необходимые сборки сериализации. При вызове класса `XmlSerializer` следует создать сборку сериализации вручную, проделав следующие шаги:  
  
1.  Запустите **Sgen.exe** средство, которое входит в состав пакета SDK для .NET Framework для создания сборки, содержащей сериализаторы XML для исходной сборки.  
  
2.  Зарегистрируйте созданную сборку в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью инструкции `CREATE ASSEMBLY`.  
  
 Сведения об ошибках, появляющиеся при выполнении XML-сериализации см. в следующей статье технической поддержки Майкрософт: [«Не удается загрузить динамически созданную сборку сериализации»](http://support.microsoft.com/kb/913668).  
  
 Сведения о типах данных, не поддерживаемых классом XMLSerializer, см. в разделе о поддержке привязки к схеме XML на платформе .NET Framework в документации по платформе .NET Framework.  
  
## <a name="see-also"></a>См. также  
 [Доступ к данным из объектов базы данных CLR](../../relational-databases/clr-integration/data-access/data-access-from-clr-database-objects.md)   
 [CREATE ASSEMBLY (Transact-SQL)](/sql/t-sql/statements/create-assembly-transact-sql)  
  
  
