---
title: Работа с типами данных | Документация Майкрософт
ms.custom: ''
ms.date: 08/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: smo
ms.reviewer: ''
ms.suite: sql
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- DataType object
- SQL Server Management Objects, data types
- data types [SMO]
- SMO [SQL Server], data types
ms.assetid: 1e0e736a-c709-4d89-aeb2-b32dcfd641fa
caps.latest.revision: 45
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: =azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: dabf1515804f1a2a333f80a85154bba224d42acb
ms.sourcegitcommit: 4183dc18999ad243c40c907ce736f0b7b7f98235
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "43109534"
---
# <a name="working-with-data-types"></a>Работа с типами данных
[!INCLUDE[appliesto-ss-asdb-asdw-xxx-md](../../../includes/appliesto-ss-asdb-asdw-xxx-md.md)]

  Данные поступают в виде различных типов и размеров, таких как строка определенной длины, число с конкретной точностью или определяемый пользователем тип, представляющий собой другой объект, со своим набором правил. <xref:Microsoft.SqlServer.Management.Smo.DataType> Классифицирует типы данных, чтобы оно могло быть обработано правильно по [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. Объект <xref:Microsoft.SqlServer.Management.Smo.DataType> связан с объектами, принимающими данные. Следующие [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] управляющих объектов (SMO) принимают данные, которые должны быть определены по <xref:Microsoft.SqlServer.Management.Smo.DataType> свойство объекта:  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Column>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunctionParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.StoredProcedureParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunctionParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedAggregateParameter>  
  
 Свойство **DataType** для объектов, принимающих данные, можно задать несколькими способами.  
  
-   Использовать конструктор по умолчанию и указать <xref:Microsoft.SqlServer.Management.Smo.DataType> явным образом свойства объекта  
  
-   Применение перегруженного конструктора и укажите <xref:Microsoft.SqlServer.Management.Smo.DataType> свойств в виде параметров.  
  
-   Укажите <xref:Microsoft.SqlServer.Management.Smo.DataType> , встроенный в конструкторе объекта.  
  
-   Используйте один из статических членов <xref:Microsoft.SqlServer.Management.Smo.DataType> классов, например **Int**. В результате будет возвращен экземпляр объекта <xref:Microsoft.SqlServer.Management.Smo.DataType>.  
  
 Объект <xref:Microsoft.SqlServer.Management.Smo.DataType> имеет несколько свойств, описывающих тип данных. Например, свойство <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> задает тип данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. Постоянные величины, представляющие [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] типы данных, перечислены в <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> перечисления. Это относится к таким типам данных, как **varchar**, **nchar**, **currency**, **integer**, **float**и **datetime**.  
  
 После установления типа данных необходимо задать для данных конкретные свойства. Например, если это тип **nchar** , необходимо задать в свойстве **Length** длину строковых данных. Тоже относится к числовым значениям, для которых необходимо задать точность и масштаб.  
  
 Типы данных <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> и <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> относятся к объектам, содержащим определение типа данных, созданного пользователем. Определяемый пользователем тип данных <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> основан на типах данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] из перечисления <xref:Microsoft.SqlServer.Management.Smo.SqlDataType>. <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> Основан на [!INCLUDE[msCoName](../../../includes/msconame-md.md)] типы данных .NET. Обычно эти данные представляют собой данные конкретного типа, часто используемые повторно в базе данных, поскольку этого требуют бизнес-правила, определяемые организацией. Например, компания, которая проводит сделки с использованием нескольких валют, может использовать тип данных, предусматривающий хранение денежной суммы и кода валюты.  
  
 <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> Перечисление содержит список всех [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-поддерживаемые типы данных.  
  
## <a name="examples"></a>Примеры  
Чтобы использовать какой-либо из представленных примеров кода, нужно выбрать среду, шаблон и язык программирования, с помощью которых будет создаваться приложение. Дополнительные сведения см. в разделе [Visual C создайте&#35; проекта SMO в Visual Studio .NET](../../../relational-databases/server-management-objects-smo/how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).  
  
  
## <a name="constructing-a-datatype-object-with-the-specification-in-the-constructor-in-visual-basic"></a>Создание объекта DataType со спецификацией в конструкторе объекта на языке Visual Basic  
 Данный пример кода показано, как использовать конструктор для создания экземпляров типов данных, основанных на разных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] типов данных.  
  
> [!NOTE]  
>  Типы <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> и типы XML требуют использования имени для идентификации объекта.  
  
```VBNET
'Declare a DataType object variable and define the data type in the constructor.
Dim dt As DataType
'For the decimal data type the following two arguements specify precision, and scale.
dt = New DataType(SqlDataType.Decimal, 10, 2)
``` 
  
## <a name="constructing-a-datatype-object-with-the-specification-in-the-constructor-in-visual-c"></a>Создание объекта DataType со спецификацией в конструкторе объекта на языке Visual C#  
 Данный пример кода показано, как использовать конструктор для создания экземпляров типов данных, основанных на разных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] типов данных.  
  
> [!NOTE]  
>  Типы <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> и типы XML требуют использования имени для идентификации объекта.  
  
```csharp  
{   
//Declare a DataType object variable and define the data type in the constructor.   
DataType dt;   
//For the decimal data type the following two arguements specify precision, and scale.   
dt = new DataType(SqlDataType.Decimal, 10, 2);   
}  
```  
  
## <a name="constructing-a-datatype-object-by-using-the-default-constructor-in-visual-basic"></a>Создание объекта DataType с применением конструктора по умолчанию на языке Visual Basic  
 Данный пример кода показано, как использовать конструктор по умолчанию для создания экземпляров типов данных, основанных на разных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] типов данных. После этого с помощью свойств задается тип данных.  
  
 **Примечание** <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, и типы XML требуют использования имени для идентификации объекта.  
  
```VBNET
'Declare and create a DataType object variable.
Dim dt As DataType
dt = New DataType
'Define the data type by setting the SqlDataType property.
dt.SqlDataType = SqlDataType.VarChar
'The VarChar data type requires a value for the MaximumLength property.
dt.MaximumLength = 100
```
  
## <a name="constructing-a-datatype-object-by-using-the-default-constructor-in-visual-c"></a>Создание объекта DataType с применением конструктора по умолчанию на языке Visual C#  
 Данный пример кода показано, как использовать конструктор по умолчанию для создания экземпляров типов данных, основанных на разных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] типов данных. После этого с помощью свойств задается тип данных.  
  
 **Примечание** <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, и типы XML требуют использования имени для идентификации объекта.  
  
```csharp  
{   
//Declare and create a DataType object variable.   
DataType dt;   
dt = new DataType();   
//Define the data type by setting the SqlDataType property.   
dt.SqlDataType = SqlDataType.VarChar;   
//The VarChar data type requires a value for the MaximumLength property.   
dt.MaximumLength = 100;   
}  
```  
  
  
