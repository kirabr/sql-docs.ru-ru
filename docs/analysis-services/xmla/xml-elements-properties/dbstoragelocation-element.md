---
title: Элемент DbStorageLocation | Документы Microsoft
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 42b0b7e4ded0aa9d31587e5a4fa296968559e78b
ms.sourcegitcommit: 808d23a654ef03ea16db1aa23edab496b73e5072
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34579116"
---
# <a name="dbstoragelocation-element"></a>Элемент DbStorageLocation
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]
  Указывает папку, в которой службы [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] создают все файлы данных базы данных и метаданных, а также управляют ими.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
  
<Database>  
...  
   <ddl100_100:DbStorageLocation>...</ddl100_100:DbStorageLocation>  
...  
</Database>  
```  
  
## <a name="element-characteristics"></a>Характеристики элемента  
  
|Характеристика|Описание|  
|--------------------|-----------------|  
|Тип данных и длина|String|  
|Значение по умолчанию|""|  
|Количество элементов|0—1: Необязательный элемент, который может появляться только один раз.|  
  
## <a name="element-relationships"></a>Связи элемента  
  
|Связь|Элемент|  
|------------------|-------------|  
|Родительские элементы|[База данных](../../../analysis-services/xmla/xml-elements-properties/database-element-xmla.md)|  
|Дочерние элементы|None|  
  
## <a name="remarks"></a>Примечания  
 В свойстве базы данных **DbStorageLocation** должен быть задан путь к существующей папке в формате UNC или пустая строка. Пустая строка является папкой данных сервера, используемой по умолчанию. Если папка не существует, при выполнении команд **Create**, **Attach**или **Alter** возникнет ошибка.  
  
 Кроме того, нельзя настроить свойство базы данных **DbStorageLocation** таким образом, чтобы оно указывало на папку данных сервера или на одну из вложенных в нее папок. Если местоположение указывает на папку данных сервера или на одну из вложенных в нее папок, при выполнении команд **Create**, **Attach**или **Alter** возникнет ошибка.  
  
## <a name="see-also"></a>См. также
 <xref:Microsoft.AnalysisServices.Database.DbStorageLocation%2A>   
 [Подключение и отключение баз данных служб Analysis Services](../../../analysis-services/multidimensional-models/attach-and-detach-analysis-services-databases.md)  
  
  
