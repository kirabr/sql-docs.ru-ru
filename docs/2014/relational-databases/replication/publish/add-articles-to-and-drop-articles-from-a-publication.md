---
title: Добавление и удаление статей в публикации (среда SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- articles [SQL Server replication], dropping
- deleting articles
- dropping articles
- adding articles
- articles [SQL Server replication], adding
ms.assetid: d5a3e536-62d2-4473-a178-877ba52f7d7f
caps.latest.revision: 33
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: da55583a9d883d14a7baffea7ecf72a0128e196e
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37260380"
---
# <a name="add-articles-to-and-drop-articles-from-a-publication-sql-server-management-studio"></a>Добавление и удаление статей в публикации (среда SQL Server Management Studio)
  Вначале статьи в публикацию добавляются при ее создании в мастере создания публикации. Дополнительные сведения об использовании мастера см. в статье [Создание публикации](create-a-publication.md).  
  
 После создания публикации вы можете добавлять и удалять статьи на странице **Статьи** диалогового окна **Свойства публикации — \<публикация>**. Дополнительные сведения о доступе к этому диалоговому окну см. в разделе [Просмотр и изменение свойств публикации](view-and-modify-publication-properties.md). Сведения о добавлении и удалении статей см. в статье [Добавление и удаление статей в существующих публикациях](add-articles-to-and-drop-articles-from-existing-publications.md).  
  
### <a name="to-add-an-article-after-a-publication-is-created"></a>Добавление статьи после создания публикации  
  
1.  На странице **Статьи** диалогового окна **Свойства публикации — \<публикация>** снимите флажок **Показывать в списке только отмеченные объекты**. Это позволит увидеть неопубликованные объекты в базе данных публикаций.  
  
2.  Установите флажок рядом с каждой статьей, которую нужно добавить.  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-delete-an-article"></a>Удаление статьи  
  
1.  На странице **Статьи** диалогового окна **Свойства публикации — \<название публикации>** снимите флажки напротив всех статей, которые нужно удалить.  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Определение статьи](define-an-article.md)   
 [Публикация данных и объектов базы данных](publish-data-and-database-objects.md)  
  
  
