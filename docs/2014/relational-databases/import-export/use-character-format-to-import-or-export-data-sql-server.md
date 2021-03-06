---
title: Использование символьного формата для импорта или экспорта данных (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: data-movement
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- data formats [SQL Server], character
- character formats [SQL Server]
ms.assetid: d925e66a-1a73-43cd-bc06-1cbdf8174a4d
caps.latest.revision: 36
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: a4249f87cf7a8361056caf6c49b3775848d7dfe5
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37250194"
---
# <a name="use-character-format-to-import-or-export-data-sql-server"></a>Использование символьного формата для импорта и экспорта данных (SQL Server)
  Символьный формат рекомендуется применять при выполнении массового экспорта данных в текстовый файл, который предназначен для использования в других программах, а также при выполнении массового импорта данных из текстового файла, созданного другими программами.  
  
> [!NOTE]  
>  При массовом переносе данных между экземплярами [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , если файл данных содержит символьные данные в Юникоде, но не содержит расширенные символы и символы в двухбайтовой кодировке (DBCS), используйте символы в формате Юникод. Дополнительные сведения см. в разделе [Использование символьного формата Юникод для импорта и экспорта данных (SQL Server)](use-unicode-character-format-to-import-or-export-data-sql-server.md).  
  
 В символьном формате все столбцы представлены в формате символьных данных. Хранение данных в символьном формате удобно в том случае, когда данные используются в других программах (например электронных таблицах) или когда на экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] необходимо перенести данные из базы данных другого поставщика (например Oracle).  
  
## <a name="considerations-for-using-character-format"></a>Замечания по использованию символьного формата  
 При использовании символьного формата имейте в виду следующее.  
  
-   По умолчанию программа **bcp** разделяет символьные поля данных символом табуляции, а записи — символом перевода строки. Сведения о том, как указать другой признак конца поля, см. в статье [Определение признаков конца поля и строки (SQL Server)](specify-field-and-row-terminators-sql-server.md).  
  
-   По умолчанию перед выполнением массового импорта или экспорта символьных данных выполняются следующие преобразования.  
  
    |Направление массовой операции|Преобразование|  
    |---------------------------------|----------------|  
    |Экспорт|Преобразует данные в символьное представление. Если это явно запрошено, данные в символьных столбцах преобразуются в требуемую кодовую страницу. Если кодовая страница не указана, символьные данные преобразуются в кодовую страницу изготовителя оборудования (OEM) клиентского компьютера.|  
    |Импорт|Если необходимо, преобразует символьные данные в собственное представление, а также преобразует данные из кодовой страницы клиента в кодовую страницу целевого столбца.|  
  
-   Чтобы предотвратить потерю дополнительных символов при преобразовании, применяйте символьный формат Юникода либо укажите кодовую страницу.  
  
-   Значения типа `sql_variant` сохраняются в файле в символьном формате без метаданных. Каждое значение данных преобразуется в `char` формат, в соответствии с правилами неявного преобразования данных. В столбец типа `sql_variant` данные импортируются как тип `char`. При импорте в столбец с типом данных, отличных от `sql_variant`, данные преобразуются из `char` с помощью неявного преобразования. Дополнительные сведения о преобразовании данных см. в статье [Преобразование типов данных (ядро СУБД)](/sql/t-sql/data-types/data-type-conversion-database-engine).  
  
-   **Bcp** экспортов программа `money` значений с четырьмя знаками после десятичной запятой и без символов-разделителей запятые-разделители, таких как данных символьного формата. Например: для столбца типа `money`, содержащего значение 1 234 567,123456, будет выполнен массовый экспорт в файл данных в виде символьной строки «1234567,1235».  
  
## <a name="command-options-for-character-format"></a>Параметры команд для символьного формата  
 Для импорта символьных данных в таблицу используются команды **bcp**, BULK INSERT и INSERT... ВЫБЕРИТЕ \* FROM OPENROWSET(BULK...). Для команды **bcp** или инструкции BULK INSERT формат данных можно указать в командной строке. Для инструкции INSERT ... SELECT * FROM OPENROWSET(BULK...) нужно указать формат данных в файле форматирования.  
  
 Символьный формат поддерживается следующими параметрами командной строки.  
  
|Command|Параметр|Описание|  
|-------------|------------|-----------------|  
|**bcp**|**-c**|Вызывает **bcp** использовать символьные данные.<sup> 1</sup>|  
|BULK INSERT|DATAFILETYPE **='char'**|Использует символьный формат при массовом импорте данных.|  
  
 <sup>1</sup> Чтобы загрузить символьные (**- c**) данные в формате, совместимом с более ранними версиями [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] клиентов необходимо использовать **-V** переключения. Дополнительные сведения см. в разделе [Импорт данных в собственном и символьном формате из предыдущих версий SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md).  
  
 Дополнительные сведения см. в статьях [Программа bcp](../../tools/bcp-utility.md), [BULK INSERT (Transact-SQL)](/sql/t-sql/statements/bulk-insert-transact-sql) и [OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql).  
  
> [!NOTE]  
>  Также в файле форматирования можно указать форматирование для каждого поля. Дополнительные сведения см. в статье [Файлы форматирования для импорта или экспорта данных (SQL Server)](format-files-for-importing-or-exporting-data-sql-server.md).  
  
## <a name="examples"></a>Примеры  
 В следующих примерах показано, как массово экспортировать символьные данные с помощью **bcp** и массово импортировать эти же данные с помощью BULK INSERT.  
  
### <a name="sample-table"></a>Образец таблицы  
 Для выполнения примеров необходима таблица **myTestCharData** в образце базы данных **AdventureWorks** в схеме **dbo**. Перед выполнением примеров следует создать эту таблицу. Для этого в редакторе запросов SQL среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] выполните:  
  
```  
USE AdventureWorks;  
GO  
CREATE TABLE myTestCharData (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50)  
   );   
```  
  
 Чтобы заполнить эту таблицу и просмотреть результирующее содержимое, выполните следующие инструкции:  
  
```  
INSERT INTO myTestCharData(Col1,Col2,Col3)  
   VALUES(1,'DataField2','DataField3');  
INSERT INTO myTestCharData(Col1,Col2,Col3)  
   VALUES(2,'DataField2','DataField3');  
GO  
SELECT Col1,Col2,Col3 FROM myTestCharData  
  
```  
  
### <a name="using-bcp-to-bulk-export-character-data"></a>Использование программы bcp для массового экспорта символьных данных  
 Чтобы экспортировать данные из таблицы в файл данных, используйте команду **bcp** с параметром **out** и следующими квалификаторами:  
  
|Квалификаторы|Описание|  
|----------------|-----------------|  
|**-c**|Указывает символьный формат данных.|  
|**-t** `,`|Задает запятую (`,`) в качестве признака конца поля.<br /><br /> Примечание. По умолчанию признаком конца поля является символ табуляции (\t). Дополнительные сведения см. в разделе [Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).|  
|**-T**|Указывает, что программа **bcp** устанавливает доверительное соединение с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с использованием встроенной безопасности. Если параметр **-T** не указан, для входа необходимо указать **-U** и **-P**.|  
  
 Следующий пример выполняет массовый экспорт данных из таблицы `myTestCharData` в новый файл данных `myTestCharData-c.Dat` в символьном формате. В качестве признака конца поля используется запятая (,). В командной строке [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows введите:  
  
```  
bcp AdventureWorks..myTestCharData out C:\myTestCharData-c.Dat -c -t, -T  
  
```  
  
### <a name="using-bulk-insert-to-bulk-import-character-data"></a>Применение инструкции BULK INSERT для массового импорта символьных данных  
 В следующем примере с помощью инструкции BULK INSERT выполняется импорт данных из файла данных `myTestCharData-c.Dat` в таблицу `myTestCharData`. В редакторе запросов среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] выполните:  
  
```  
USE AdventureWorks;  
GO  
BULK INSERT myTestCharData   
   FROM 'C:\myTestCharData-c.Dat'   
   WITH (  
      DATAFILETYPE='char',  
      FIELDTERMINATOR=','  
   );   
GO  
SELECT Col1,Col2,Col3 FROM myTestCharData;  
GO  
  
```  
  
##  <a name="RelatedTasks"></a> Связанные задачи  
 **Использование форматов данных для массового импорта или экспорта**  
  
-   [Импорт данных в собственном и символьном формате из предыдущих версий SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [Использование собственного формата для импорта и экспорта данных (SQL Server)](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [Использование символьного формата Юникод для импорта и экспорта данных (SQL Server)](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [Использование собственного формата Юникод для импорта и экспорта данных (SQL Server)](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
## <a name="see-also"></a>См. также  
 [bcp Utility](../../tools/bcp-utility.md)   
 [BULK INSERT (Transact-SQL)](/sql/t-sql/statements/bulk-insert-transact-sql)   
 [OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql)   
 [Типы данных (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql)   
 [Импорт данных в собственном и символьном формате из предыдущих версий SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
  
