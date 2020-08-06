---
title: Utiliser des données XML dans les applications | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- parameters [XML in SQL Server]
- XML [SQL Server], ADO
- columns [XML in SQL Server], ADO.NET
- ADO [XML in SQL Server]
- columns [XML in SQL Server], SQL Server Native Client
- xml data type [SQL Server], ADO
- SQLNCLI, XML
- xml data type [SQL Server], SQL Server Native Client
- SQL Server Native Client, XML
- ADO.NET [XML in SQL Server]
- XML [SQL Server], ADO.NET
- columns [XML in SQL Server], ADO
- xml data type [SQL Server], ADO.NET
- XML [SQL Server], SQL Server Native Client
ms.assetid: 5dabf7e0-c6df-451d-a070-4661f84607fd
author: rothja
ms.author: jroth
ms.openlocfilehash: 79dd4f4d2ff3cd61bc33c632f499bfb8e8817f0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695448"
---
# <a name="use-xml-data-in-applications"></a><span data-ttu-id="cbd89-102">Utiliser des données XML dans les applications</span><span class="sxs-lookup"><span data-stu-id="cbd89-102">Use XML Data in Applications</span></span>
  <span data-ttu-id="cbd89-103">Cette rubrique décrit les options dont vous disposez pour utiliser le type de données `xml` dans votre application.</span><span class="sxs-lookup"><span data-stu-id="cbd89-103">This topic describes the options that are available to you for working with the `xml` data type in your application.</span></span> <span data-ttu-id="cbd89-104">Cette rubrique inclut des informations sur les thèmes suivants :</span><span class="sxs-lookup"><span data-stu-id="cbd89-104">The topic includes information about the following:</span></span>  
  
-   <span data-ttu-id="cbd89-105">Gestion de XML à partir d'une colonne de type `xml` à l'aide d'ADO et de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client</span><span class="sxs-lookup"><span data-stu-id="cbd89-105">Handling XML from an `xml` type column by using ADO and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client</span></span>  
  
-   <span data-ttu-id="cbd89-106">Gestion de XML à partir d'une colonne de type `xml` à l'aide d'ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cbd89-106">Handling XML from an `xml` type column by using ADO.NET</span></span>  
  
-   <span data-ttu-id="cbd89-107">Gestion du type `xml` dans les paramètres à l'aide d'ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cbd89-107">Handling `xml` type in parameters by using ADO.NET</span></span>  
  
## <a name="handling-xml-from-an-xml-type-column-by-using-ado-and-sql-server-native-client"></a><span data-ttu-id="cbd89-108">Gestion de XML à partir d'une colonne de type XML à l'aide d'ADO et de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="cbd89-108">Handling XML from an xml Type Column by Using ADO and SQL Server Native Client</span></span>  
 <span data-ttu-id="cbd89-109">Pour utiliser des composants MDAC pour accéder aux types et aux fonctionnalités introduits dans [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], vous devez définir la propriété d’initialisation DataTypeCompatibility dans la chaîne de connexion ADO.</span><span class="sxs-lookup"><span data-stu-id="cbd89-109">To use MDAC components to access the types and features that were introduced in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], you must set the DataTypeCompatibility initialization property in the ADO connection string.</span></span>  
  
 <span data-ttu-id="cbd89-110">Par exemple, l'exemple VBScript (Visual Basic Scripting Edition) suivant affiche les résultats de l'interrogation d'une colonne de type de données `xml`, `Demographics`, dans la table `Sales.Store` de l'exemple de base de données `AdventureWorks2012`.</span><span class="sxs-lookup"><span data-stu-id="cbd89-110">For example, the following Visual Basic Scripting Edition (VBScript) sample shows the results of querying an `xml` data type column, `Demographics`, in the `Sales.Store` table of the `AdventureWorks2012` sample database.</span></span> <span data-ttu-id="cbd89-111">La requête recherche plus particulièrement la valeur de l'instance de cette colonne pour la ligne dans laquelle `CustomerID` est égal à `3`.</span><span class="sxs-lookup"><span data-stu-id="cbd89-111">Specifically, the query looks for the instance value of this column for the row where the `CustomerID` is equal to `3`.</span></span>  
  
```  
Const DS = "MyServer"  
Const DB = "AdventureWorks2012"  
  
Set objConn = CreateObject("ADODB.Connection")  
Set objRs = CreateObject("ADODB.Recordset")  
  
CommandText = "SELECT Demographics" & _  
              " FROM Sales.Store" & _  
              " INNER JOIN Sales.Customer" & _  
              " ON Sales.Store.BusinessEntityID = sales.customer.StoreID" & _  
              " WHERE Sales.Customer.CustomerID = 3" & _  
              " OR Sales.Customer.CustomerID = 4"  
  
ConnectionString = "Provider=SQLNCLI11" & _  
                   ";Data Source=" & DS & _  
                   ";Initial Catalog=" & DB & _  
                   ";Integrated Security=SSPI;" & _  
                   "DataTypeCompatibility=80"  
  
'Connect to the data source.  
objConn.Open ConnectionString  
  
'Execute command through the connection and display  
Set objRs = objConn.Execute(CommandText)  
  
Dim rowcount  
rowcount = 0  
Do While Not objRs.EOF  
   rowcount = rowcount + 1  
   MsgBox "Row " & rowcount & _  
           vbCrLf & vbCrLf & objRs(0)  
   objRs.MoveNext  
Loop  
  
'Clean up.  
objRs.Close  
objConn.Close  
Set objRs = Nothing  
Set objConn = Nothing  
```  
  
 <span data-ttu-id="cbd89-112">Cet exemple montre comment définir la propriété de compatibilité du type de données.</span><span class="sxs-lookup"><span data-stu-id="cbd89-112">This example shows how to set the data type compatibility property.</span></span> <span data-ttu-id="cbd89-113">Par défaut, elle a la valeur 0 lorsque vous utilisez [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="cbd89-113">By default, this is set to 0 when you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="cbd89-114">Si vous avez affecté la valeur 80 à cette propriété, le fournisseur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client fait apparaître les colonnes de type `xml` et définies par l'utilisateur comme des types de données [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbd89-114">If you set the value to 80, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client provider will make `xml` and user-defined type columns appear as [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] data types.</span></span> <span data-ttu-id="cbd89-115">Il s'agit respectivement de BTYPE_WSTR et de DBTYPE_BYTES.</span><span class="sxs-lookup"><span data-stu-id="cbd89-115">This would be DBTYPE_WSTR and DBTYPE_BYTES, respectively.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cbd89-116">Native Client doit également être installé sur l'ordinateur client et la chaîne de connexion doit le désigner comme fournisseur de données avec «`Provider=SQLNCLI11;...`».</span><span class="sxs-lookup"><span data-stu-id="cbd89-116">Native Client must also be installed on the client computer and the connection string must specify it for use as the data provider with "`Provider=SQLNCLI11;...`".</span></span>  
  
#### <a name="to-test-this-example"></a><span data-ttu-id="cbd89-117">Pour tester cet exemple</span><span class="sxs-lookup"><span data-stu-id="cbd89-117">To test this example</span></span>  
  
1.  <span data-ttu-id="cbd89-118">Vérifiez que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client est installé et que MDAC version 2.6.0 ou ultérieure est disponible sur l'ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="cbd89-118">Verify that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client is installed and that MDAC 2.6.0or later is available on the client computer.</span></span>  
  
     <span data-ttu-id="cbd89-119">Pour plus d’informations, consultez [Programmation de SQL Server Native Client](../native-client/sql-server-native-client-programming.md).</span><span class="sxs-lookup"><span data-stu-id="cbd89-119">For more information, see [SQL Server Native Client Programming](../native-client/sql-server-native-client-programming.md).</span></span>  
  
2.  <span data-ttu-id="cbd89-120">Vérifiez que l'exemple de base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est installé.</span><span class="sxs-lookup"><span data-stu-id="cbd89-120">Verify that the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span>  
  
     <span data-ttu-id="cbd89-121">Cet exemple requiert l'exemple de base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cbd89-121">This example requires the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
3.  <span data-ttu-id="cbd89-122">Copiez le code préalablement présenté dans cette rubrique et collez-le dans votre éditeur de texte ou de code.</span><span class="sxs-lookup"><span data-stu-id="cbd89-122">Copy the code shown previously in this topic and paste the code into your text or code editor.</span></span> <span data-ttu-id="cbd89-123">Enregistrez le fichier sous HandlingXmlDataType.vbs.</span><span class="sxs-lookup"><span data-stu-id="cbd89-123">Save the file as HandlingXmlDataType.vbs.</span></span>  
  
4.  <span data-ttu-id="cbd89-124">Modifiez le script comme le requiert votre installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et enregistrez vos modifications.</span><span class="sxs-lookup"><span data-stu-id="cbd89-124">Modify the script as required for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation and save your changes.</span></span>  
  
     <span data-ttu-id="cbd89-125">Par exemple, à l'endroit où `MyServer` est spécifié, vous devez le remplacer par `(local)` ou par le nom réel du serveur sur lequel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est installé.</span><span class="sxs-lookup"><span data-stu-id="cbd89-125">For example, where `MyServer` is specified, you should replace it with either `(local)` or the actual name of the server on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span>  
  
5.  <span data-ttu-id="cbd89-126">Exécutez HandlingXmlDataType.vbs et exécutez le script.</span><span class="sxs-lookup"><span data-stu-id="cbd89-126">Run HandlingXmlDataType.vbs and execute the script.</span></span>  
  
 <span data-ttu-id="cbd89-127">Les résultats doivent être semblables à l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="cbd89-127">The results should be similar to the following sample output:</span></span>  
  
```  
Row 1  
  
<StoreSurvey xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey">  
  <AnnualSales>1500000</AnnualSales>  
  <AnnualRevenue>150000</AnnualRevenue>  
  <BankName>Primary International</BankName>  
  <BusinessType>OS</BusinessType>  
  <YearOpened>1974</YearOpened>  
  <Specialty>Road</Specialty>  
  <SquareFeet>38000</SquareFeet>  
  <Brands>3</Brands>  
  <Internet>DSL</Internet>  
  <NumberEmployees>40</NumberEmployees>  
</StoreSurvey>  
  
Row 2  
  
<StoreSurvey xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey">  
  <AnnualSales>300000</AnnualSales>  
  <AnnualRevenue>30000</AnnualRevenue>  
  <BankName>United Security</BankName>  
  <BusinessType>BM</BusinessType>  
  <YearOpened>1976</YearOpened>  
  <Specialty>Road</Specialty>  
  <SquareFeet>6000</SquareFeet>  
  <Brands>2</Brands>  
  <Internet>DSL</Internet>  
  <NumberEmployees>5</NumberEmployees>  
</StoreSurvey>  
```  
  
## <a name="handling-xml-from-an-xml-type-column-by-using-adonet"></a><span data-ttu-id="cbd89-128">Gestion de XML à partir d'une colonne de type XML à l'aide d'ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cbd89-128">Handling XML from an xml Type Column by Using ADO.NET</span></span>  
 <span data-ttu-id="cbd89-129">Pour gérer du code XML à partir d’une `xml` colonne de type de données à l’aide de ADO.net et du, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] vous pouvez utiliser le comportement standard de la `SqlCommand` classe.</span><span class="sxs-lookup"><span data-stu-id="cbd89-129">To handle XML from an `xml` data type column by using ADO.NET and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] you can use the standard behavior of the `SqlCommand` class.</span></span> <span data-ttu-id="cbd89-130">Par exemple, une colonne de type de données `xml` et ses valeurs peuvent être récupérées comme toute colonne SQL à l'aide de `SqlDataReader`.Toutefois, si vous souhaitez utiliser le contenu d'une colonne de type de données `xml` sous la forme XML, vous devez d'abord assigner un type `XmlReader` au contenu.</span><span class="sxs-lookup"><span data-stu-id="cbd89-130">For example, an `xml` data type column and its values can be retrieved in the same way any SQL column is retrieved by using a `SqlDataReader`.However, if you want to work with the contents of an `xml` data type column as XML, you will first have to assign the contents to an `XmlReader` type.</span></span>  
  
 <span data-ttu-id="cbd89-131">Pour plus d’informations et d’exemples de code, consultez la rubrique relative aux valeurs de colonne XML dans un lecteur de données dans la documentation du SDK [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbd89-131">For more information and example code, see "XML Column Values in a Data Reader" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] SDK documentation.</span></span>  
  
## <a name="handling-an-xml-type-column-in-parameters-by-using-adonet"></a><span data-ttu-id="cbd89-132">Gestion d'une colonne de type XML dans les paramètres à l'aide d'ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cbd89-132">Handling an xml Type Column in Parameters by Using ADO.NET</span></span>  
 <span data-ttu-id="cbd89-133">Pour gérer un type de données XML passé en tant que paramètre dans ADO.NET et le [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], vous pouvez fournir la valeur sous la forme d'une instance du type de données `SqlXml`.</span><span class="sxs-lookup"><span data-stu-id="cbd89-133">To handle an xml data type passed as a parameter in ADO.NET and the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can supply the value as an instance of the `SqlXml` data type.</span></span> <span data-ttu-id="cbd89-134">Aucune gestion spéciale n'est requise, car les colonnes de type de données `xml` de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peuvent accepter les valeurs de paramètre de la même façon que d'autres colonnes et types de données, tels que `string` ou `integer`.</span><span class="sxs-lookup"><span data-stu-id="cbd89-134">No special handling is involved, because `xml` data type columns in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can accept parameter values in the same way as other columns and data types, such as `string` or `integer`.</span></span>  
  
 <span data-ttu-id="cbd89-135">Pour plus d’informations et d’exemples de code, consultez la rubrique relative aux valeurs XML en tant que paramètres de commande dans la documentation du SDK [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbd89-135">For more information and example code, see "XML Values as Command Parameters" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] SDK documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbd89-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cbd89-136">See Also</span></span>  
 [<span data-ttu-id="cbd89-137">Données XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cbd89-137">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
