---
title: Utilisation des types de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- DataType object
- SQL Server Management Objects, data types
- data types [SMO]
- SMO [SQL Server], data types
ms.assetid: 1e0e736a-c709-4d89-aeb2-b32dcfd641fa
author: stevestein
ms.author: sstein
ms.openlocfilehash: cbffc1c59eb12fa0f448a7fcb26157d5e18dba3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602006"
---
# <a name="working-with-data-types"></a><span data-ttu-id="6313e-102">Utilisation des types de données</span><span class="sxs-lookup"><span data-stu-id="6313e-102">Working with Data Types</span></span>
  <span data-ttu-id="6313e-103">Il existe des données de nombreux types et tailles différents, telles qu'une chaîne qui a une longueur définie, un nombre qui a une précision spécifique ou un type de données défini par l'utilisateur qui est un autre objet ayant son propre ensemble de règles.</span><span class="sxs-lookup"><span data-stu-id="6313e-103">Data comes in many types and sizes, such as a string that has a defined length, a number that has specific accuracy, or a user-defined data type that is another object that has its own set of rules.</span></span> <span data-ttu-id="6313e-104">L' <xref:Microsoft.SqlServer.Management.Smo.DataType> objet classe le type de données afin qu’il puisse être géré correctement par [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6313e-104">The <xref:Microsoft.SqlServer.Management.Smo.DataType> object classifies the type of data so that it can be handled correctly by [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6313e-105">L'objet <xref:Microsoft.SqlServer.Management.Smo.DataType> est associé aux objets qui acceptent des données.</span><span class="sxs-lookup"><span data-stu-id="6313e-105">The <xref:Microsoft.SqlServer.Management.Smo.DataType> object is associated with objects that accept data.</span></span> <span data-ttu-id="6313e-106">Les objets [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) suivants acceptent des données qui doivent être définies par une propriété d'objet <xref:Microsoft.SqlServer.Management.Smo.DataType> :</span><span class="sxs-lookup"><span data-stu-id="6313e-106">The following [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) objects accept data that must be defined by a <xref:Microsoft.SqlServer.Management.Smo.DataType> object property:</span></span>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Column>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunctionParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.StoredProcedureParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunctionParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedAggregateParameter>  
  
 <span data-ttu-id="6313e-107">La propriété `DataType` pour les objets qui acceptent des données peut être définie de plusieurs façons.</span><span class="sxs-lookup"><span data-stu-id="6313e-107">The `DataType` property for objects that accept data can be set in several ways.</span></span>  
  
-   <span data-ttu-id="6313e-108">Utilisez le constructeur par défaut et spécifiez des propriétés d'objet <xref:Microsoft.SqlServer.Management.Smo.DataType> explicitement.</span><span class="sxs-lookup"><span data-stu-id="6313e-108">Use the default constructor and specify <xref:Microsoft.SqlServer.Management.Smo.DataType> object properties explicitly</span></span>  
  
-   <span data-ttu-id="6313e-109">Utilisez un constructeur surchargé et spécifiez les propriétés <xref:Microsoft.SqlServer.Management.Smo.DataType> comme paramètres.</span><span class="sxs-lookup"><span data-stu-id="6313e-109">Use an overloaded constructor and specify the <xref:Microsoft.SqlServer.Management.Smo.DataType> properties as parameters.</span></span>  
  
-   <span data-ttu-id="6313e-110">Spécifiez le type <xref:Microsoft.SqlServer.Management.Smo.DataType> inline dans le constructeur d'objet.</span><span class="sxs-lookup"><span data-stu-id="6313e-110">Specify the <xref:Microsoft.SqlServer.Management.Smo.DataType> inline in the object constructor.</span></span>  
  
-   <span data-ttu-id="6313e-111">Utilisez l'un des membres statiques de la classe <xref:Microsoft.SqlServer.Management.Smo.DataType>, par exemple `Int`.</span><span class="sxs-lookup"><span data-stu-id="6313e-111">Use one of the static members of the <xref:Microsoft.SqlServer.Management.Smo.DataType> class, for example `Int`.</span></span> <span data-ttu-id="6313e-112">Cela retourne en fait une instance d'un objet <xref:Microsoft.SqlServer.Management.Smo.DataType>.</span><span class="sxs-lookup"><span data-stu-id="6313e-112">This will in fact return an instance of a <xref:Microsoft.SqlServer.Management.Smo.DataType> object.</span></span>  
  
 <span data-ttu-id="6313e-113">L'objet <xref:Microsoft.SqlServer.Management.Smo.DataType> a plusieurs propriétés qui définissent le type de données.</span><span class="sxs-lookup"><span data-stu-id="6313e-113">The <xref:Microsoft.SqlServer.Management.Smo.DataType> object has several properties that define the type of data.</span></span> <span data-ttu-id="6313e-114">Par exemple, la propriété <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> spécifie le type de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6313e-114">For example, the <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> property specifies the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type.</span></span> <span data-ttu-id="6313e-115">Les valeurs constantes qui représentent des types de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sont répertoriées dans l'énumération <xref:Microsoft.SqlServer.Management.Smo.SqlDataType>.</span><span class="sxs-lookup"><span data-stu-id="6313e-115">The constant values that represent [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types are listed in the <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> enumeration.</span></span> <span data-ttu-id="6313e-116">Cela fait référence à des types de données tels que `varchar`, `nchar`, `currency`, `integer`, `float` et `datetime`.</span><span class="sxs-lookup"><span data-stu-id="6313e-116">This refers to data types such as `varchar`, `nchar`, `currency`, `integer`, `float`, and `datetime`.</span></span>  
  
 <span data-ttu-id="6313e-117">Lorsque le type de données est établi, des propriétés spécifiques doivent être définies pour les données.</span><span class="sxs-lookup"><span data-stu-id="6313e-117">When the data type is established, specific properties must be set for the data.</span></span> <span data-ttu-id="6313e-118">Par exemple, s'il s'agit d'un type `nchar`, la longueur des données de chaîne doit être définie dans la propriété `Length`.</span><span class="sxs-lookup"><span data-stu-id="6313e-118">For example, if it is an `nchar` type, the length of the string data must be set in the `Length` property.</span></span> <span data-ttu-id="6313e-119">La même règle s'applique aux valeurs numériques, pour lesquelles il vous faudrait spécifier la précision et l'échelle.</span><span class="sxs-lookup"><span data-stu-id="6313e-119">The same applies for numeric values, where you would have to specify precision and scale.</span></span>  
  
 <span data-ttu-id="6313e-120">Les types de données <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> et <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> font référence à des objets qui contiennent la définition du type de données défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6313e-120"><xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> and <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> data types refer to objects that contain the definition of the type of data defined by the user.</span></span> <span data-ttu-id="6313e-121">Le type <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> est basé sur les types de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de l'énumération <xref:Microsoft.SqlServer.Management.Smo.SqlDataType>.</span><span class="sxs-lookup"><span data-stu-id="6313e-121">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> is based on [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types from the <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> enumeration.</span></span> <span data-ttu-id="6313e-122">Le <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> est basé sur les [!INCLUDE[msCoName](../../../includes/msconame-md.md)] types de données .net.</span><span class="sxs-lookup"><span data-stu-id="6313e-122">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> is based on [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET data types.</span></span> <span data-ttu-id="6313e-123">En général, ces types représentent des données d'un type spécifique qui est fréquemment réutilisé par la base de données à cause de règles d'entreprise définies par l'organisation.</span><span class="sxs-lookup"><span data-stu-id="6313e-123">Typically, these would represent data of a specific type that is frequently reused by the database because of business rules defined by the organization.</span></span> <span data-ttu-id="6313e-124">Par exemple, un type de données qui stocke une somme d'argent et un dénominateur de devise serait utile dans une société qui négocie dans plusieurs devises.</span><span class="sxs-lookup"><span data-stu-id="6313e-124">For example, a data type that stores an amount of money and a currency denominator would be helpful in a company that deals in multiple currencies.</span></span>  
  
 <span data-ttu-id="6313e-125">L'énumération <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> contient une liste de tous les types de données pris en charge par [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6313e-125">The <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> enumeration contains a list of all the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-supported data types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="6313e-126">Exemples</span><span class="sxs-lookup"><span data-stu-id="6313e-126">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="constructing-a-datatype-object-with-the-specification-in-the-constructor-in-visual-basic"></a><span data-ttu-id="6313e-127">Construction d'un objet DataType avec la spécification dans le constructeur en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6313e-127">Constructing a DataType Object with the Specification in the Constructor in Visual Basic</span></span>  
 <span data-ttu-id="6313e-128">Cet exemple de code montre comment utiliser le constructeur pour créer des instances de types de données basées sur différents types de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6313e-128">This code example shows how to use the constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6313e-129">Les types <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> et XML requièrent tous une valeur de nom afin d'identifier l'objet.</span><span class="sxs-lookup"><span data-stu-id="6313e-129">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDataTypes1](SMO How to#SMO_VBDataTypes1)]  -->  
  
## <a name="constructing-a-datatype-object-with-the-specification-in-the-constructor-in-visual-c"></a><span data-ttu-id="6313e-130">Construction d'un objet DataType avec la spécification dans le constructeur en Visual C#</span><span class="sxs-lookup"><span data-stu-id="6313e-130">Constructing a DataType Object with the Specification in the Constructor in Visual C#</span></span>  
 <span data-ttu-id="6313e-131">Cet exemple de code montre comment utiliser le constructeur pour créer des instances de types de données basées sur différents types de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6313e-131">This code example shows how to use the constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6313e-132">Les types <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> et XML requièrent tous une valeur de nom afin d'identifier l'objet.</span><span class="sxs-lookup"><span data-stu-id="6313e-132">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
```  
{   
//Declare a DataType object variable and define the data type in the constructor.   
DataType dt;   
//For the decimal data type the following two arguments specify precision, and scale.   
dt = new DataType(SqlDataType.Decimal, 10, 2);   
}  
```  
  
## <a name="constructing-a-datatype-object-by-using-the-default-constructor-in-visual-basic"></a><span data-ttu-id="6313e-133">Construction d'un objet DataType à l'aide du constructeur par défaut en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6313e-133">Constructing a DataType Object by Using the Default Constructor in Visual Basic</span></span>  
 <span data-ttu-id="6313e-134">Cet exemple de code montre comment utiliser le constructeur par défaut pour créer des instances de types de données basées sur différents types de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6313e-134">This code example shows how to use the default constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="6313e-135">Les propriétés sont ensuite utilisées pour spécifier le type de données.</span><span class="sxs-lookup"><span data-stu-id="6313e-135">The properties are then used to specify the data type.</span></span>  
  
 <span data-ttu-id="6313e-136">**Remarque** Les <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> types, et XML requièrent tous une valeur de nom pour identifier l’objet.</span><span class="sxs-lookup"><span data-stu-id="6313e-136">**Note** The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDataTypes2](SMO How to#SMO_VBDataTypes2)]  -->  
  
## <a name="constructing-a-datatype-object-by-using-the-default-constructor-in-visual-c"></a><span data-ttu-id="6313e-137">Construction d'un objet DataType à l'aide du constructeur par défaut en Visual C#</span><span class="sxs-lookup"><span data-stu-id="6313e-137">Constructing a DataType Object by Using the Default Constructor in Visual C#</span></span>  
 <span data-ttu-id="6313e-138">Cet exemple de code montre comment utiliser le constructeur par défaut pour créer des instances de types de données basées sur différents types de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6313e-138">This code example shows how to use the default constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="6313e-139">Les propriétés sont ensuite utilisées pour spécifier le type de données.</span><span class="sxs-lookup"><span data-stu-id="6313e-139">The properties are then used to specify the data type.</span></span>  
  
 <span data-ttu-id="6313e-140">**Remarque** Les <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> types, et XML requièrent tous une valeur de nom pour identifier l’objet.</span><span class="sxs-lookup"><span data-stu-id="6313e-140">**Note** The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
```  
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
  
  
