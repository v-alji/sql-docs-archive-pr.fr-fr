---
title: Utilisation d’ADO avec SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client, ADO
- data access [SQL Server Native Client], ADO
- ADO [SQL Server Native Client]
- SQLNCLI, ADO
ms.assetid: 118a7cac-4c0d-44fd-b63e-3d542932d239
author: rothja
ms.author: jroth
ms.openlocfilehash: ccd14432aa3541572467a4c651c1f48b1ac957f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706384"
---
# <a name="using-ado-with-sql-server-native-client"></a><span data-ttu-id="c00e5-102">Utilisation d'ADO avec SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="c00e5-102">Using ADO with SQL Server Native Client</span></span>
  <span data-ttu-id="c00e5-103">Pour tirer parti des nouvelles fonctionnalités introduites dans, [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] telles que mars (Multiple Active Result Sets), les notifications de requêtes, les types définis par l’utilisateur (UDT) ou le nouveau type de données **XML** , les applications existantes qui utilisent ActiveX Data Objects (ADO) doivent utiliser le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client comme fournisseur d’accès aux données.</span><span class="sxs-lookup"><span data-stu-id="c00e5-103">In order to take advantage of new features introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] such as multiple active result sets (MARS), query notifications, user-defined types (UDTs), or the new **xml** data type, existing applications that use ActiveX Data Objects (ADO) should use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider as their data access provider.</span></span>  
  
 <span data-ttu-id="c00e5-104">Si vous n'avez pas besoin d'utiliser ces nouvelles fonctionnalités introduites dans [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], il n'est pas nécessaire d'utiliser le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ; vous pouvez continuer à utiliser votre fournisseur d'accès aux données actuel, qui est en général SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="c00e5-104">If you do not need to use any of the new features introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], there is no need to use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider; you can continue using your current data access provider, which is typically SQLOLEDB.</span></span> <span data-ttu-id="c00e5-105">Si vous améliorez une application existante et que vous devez utiliser les nouvelles fonctionnalités introduites dans [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], vous devez utiliser le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="c00e5-105">If you are enhancing an existing application and you need to use the new features introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], you should use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c00e5-106">Si vous développez une nouvelle application, il est recommandé d'envisager l'utilisation d'ADO.NET et du fournisseur de données .NET Framework pour [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] au lieu de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client afin d'accéder à toutes les nouvelles fonctionnalités des versions récentes de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c00e5-106">If you are developing a new application, it is recommended that you consider using ADO.NET and the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instead of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client to access all the new features of recent versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c00e5-107">Pour plus d'informations sur le fournisseur de données .NET Framework pour [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], consultez la documentation du kit de développement logiciel SDK .NET Framework pour ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="c00e5-107">For more information about the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], see the .NET Framework SDK documentation for ADO.NET.</span></span>  
  
 <span data-ttu-id="c00e5-108">Pour permettre à ADO d'utiliser les nouvelles fonctionnalités des récentes versions de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], certaines améliorations ont été apportées au fournisseur OLE DB [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client afin d'étendre les fonctionnalités principales d'OLE DB.</span><span class="sxs-lookup"><span data-stu-id="c00e5-108">To enable ADO to use new features of recent versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], some enhancements have been made to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider which extends the core features of OLE DB.</span></span> <span data-ttu-id="c00e5-109">Ces améliorations permettent aux applications ADO d’utiliser les fonctionnalités [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] les plus récentes et de consommer deux types de données introduits dans [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] : **xml** et **udt**.</span><span class="sxs-lookup"><span data-stu-id="c00e5-109">These enhancements allow ADO applications to use newer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] features and to consume two data types introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]: **xml** and **udt**.</span></span> <span data-ttu-id="c00e5-110">Ces améliorations exploitent également des optimisations apportées aux types de données **varchar**, **nvarchar** et **varbinary**.</span><span class="sxs-lookup"><span data-stu-id="c00e5-110">These enhancements also exploit enhancements to the **varchar**, **nvarchar**, and **varbinary** data types.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="c00e5-111">Native Client ajoute la propriété d’initialisation SSPROP_INIT_DATATYPECOMPATIBILITY au jeu de propriétés DBPROPSET_SQLSERVERDBINIT pour une utilisation par les applications ADO afin que les nouveaux types de données soient exposés de manière compatible avec ADO.</span><span class="sxs-lookup"><span data-stu-id="c00e5-111">Native Client adds the SSPROP_INIT_DATATYPECOMPATIBILITY initialization property to the DBPROPSET_SQLSERVERDBINIT property set for use by ADO applications so that the new data types are exposed in a way compatible with ADO.</span></span> <span data-ttu-id="c00e5-112">En outre, le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client définit également un nouveau mot clé de chaîne `DataTypeCompatibility` de connexion nommé qui est défini dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="c00e5-112">In addition, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider also defines a new connection string keyword named `DataTypeCompatibility` that is set in the connection string.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c00e5-113">Les applications ADO existantes peuvent accéder et mettre à jour des valeurs de champ binaire et texte XML, UDT et de grande valeur à l'aide du fournisseur SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="c00e5-113">Existing ADO applications can access and update XML, UDT, and large value text and binary field values using the SQLOLEDB provider.</span></span> <span data-ttu-id="c00e5-114">Les nouveaux types de données plus grands **varchar(max)** , **nvarchar(max)** et **varbinary(max)** sont retournés respectivement en tant que types ADO **adLongVarChar**, **adLongVarWChar** et **adLongVarBinary**.</span><span class="sxs-lookup"><span data-stu-id="c00e5-114">The new larger **varchar(max)**, **nvarchar(max)**, and **varbinary(max)** data types are returned as the ADO types **adLongVarChar**, **adLongVarWChar** and **adLongVarBinary** respectively.</span></span> <span data-ttu-id="c00e5-115">Les colonnes XML sont retournées comme **adLongVarChar** et les colonnes UDT sont retournées comme **adVarBinary**.</span><span class="sxs-lookup"><span data-stu-id="c00e5-115">XML columns are returned as **adLongVarChar**, and UDT columns are returned as **adVarBinary**.</span></span> <span data-ttu-id="c00e5-116">Toutefois, si vous utilisez le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) au lieu de SQLOLEDB, vous devez vous assurer d'affecter la valeur « 80 » au mot clé `DataTypeCompatibility` afin que les nouveaux types de données mappent correctement aux types de données ADO.</span><span class="sxs-lookup"><span data-stu-id="c00e5-116">However, if you use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider (SQLNCLI11) instead of SQLOLEDB, you need to make sure to set the `DataTypeCompatibility` keyword to "80" so that the new data types will map correctly to the ADO data types.</span></span>  
  
## <a name="enabling-sql-server-native-client-from-ado"></a><span data-ttu-id="c00e5-117">Activation de SQL Server Native Client à partir d'ADO</span><span class="sxs-lookup"><span data-stu-id="c00e5-117">Enabling SQL Server Native Client from ADO</span></span>  
 <span data-ttu-id="c00e5-118">Pour activer l’utilisation de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, les applications ADO doivent implémenter les mots clés suivants dans leurs chaînes de connexion :</span><span class="sxs-lookup"><span data-stu-id="c00e5-118">To enable the usage of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, ADO applications will need to implement the following keywords in their connection strings:</span></span>  
  
-   `Provider=SQLNCLI11`  
  
-   `DataTypeCompatibility=80`  
  
 <span data-ttu-id="c00e5-119">Pour plus d’informations sur les mots clés de chaîne de connexions ADO pris en charge dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, consultez [utilisation de mots clés de chaîne de connexion avec SQL Server Native Client](using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="c00e5-119">For more information about the ADO connections string keywords supported in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, see [Using Connection String Keywords with SQL Server Native Client](using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="c00e5-120">L’exemple suivant illustre l’établissement d’une chaîne de connexion ADO entièrement activée pour fonctionner avec [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, y compris l’activation de la fonctionnalité mars :</span><span class="sxs-lookup"><span data-stu-id="c00e5-120">The following is an example of establishing an ADO connection string that is fully enabled to work with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, including the enabling of the MARS feature:</span></span>  
  
```  
Dim con As New ADODB.Connection  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _  
         & "DataTypeCompatibility=80;" _  
         & "MARS Connection=True;"  
con.Open  
```  
  
## <a name="examples"></a><span data-ttu-id="c00e5-121">Exemples</span><span class="sxs-lookup"><span data-stu-id="c00e5-121">Examples</span></span>  
 <span data-ttu-id="c00e5-122">Les sections suivantes fournissent des exemples de la façon dont vous pouvez utiliser ADO avec le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client.</span><span class="sxs-lookup"><span data-stu-id="c00e5-122">The following sections provide examples of how you can use ADO with the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span>  
  
### <a name="retrieving-xml-column-data"></a><span data-ttu-id="c00e5-123">Extraction de données de colonnes XML</span><span class="sxs-lookup"><span data-stu-id="c00e5-123">Retrieving XML Column Data</span></span>  
 <span data-ttu-id="c00e5-124">Dans cet exemple, un recordset est utilisé pour récupérer et afficher les données d’une colonne XML dans l’exemple de base de données **AdventureWorks** [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c00e5-124">In this example, a recordset is used to retrieve and display the data from an XML column in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] **AdventureWorks** sample database.</span></span>  
  
```  
Dim con As New ADODB.Connection  
Dim rst As New ADODB.Recordset  
Dim sXMLResult As String  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _   
         & "DataTypeCompatibility=80;"  
  
con.Open  
  
' Get the xml data as a recordset.  
Set rst.ActiveConnection = con  
rst.Source = "SELECT AdditionalContactInfo FROM Person.Contact " _  
   & "WHERE AdditionalContactInfo IS NOT NULL"  
rst.Open  
  
' Display the data in the recordset.  
While (Not rst.EOF)  
   sXMLResult = rst.Fields("AdditionalContactInfo").Value  
   Debug.Print (sXMLResult)  
   rst.MoveNext  
End While  
  
con.Close  
Set con = Nothing  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c00e5-125">Le filtrage de jeu d'enregistrements n'est pas pris en charge avec les colonnes XML.</span><span class="sxs-lookup"><span data-stu-id="c00e5-125">Recordset filtering is not supported with XML columns.</span></span> <span data-ttu-id="c00e5-126">S'il est utilisé, une erreur est retournée.</span><span class="sxs-lookup"><span data-stu-id="c00e5-126">If used, an error will be returned.</span></span>  
  
### <a name="retrieving-udt-column-data"></a><span data-ttu-id="c00e5-127">Extraction de données de colonnes UDT</span><span class="sxs-lookup"><span data-stu-id="c00e5-127">Retrieving UDT Column Data</span></span>  
 <span data-ttu-id="c00e5-128">Dans cet exemple, un objet **Command** est utilisé pour exécuter une requête SQL qui retourne un type défini par l’utilisateur (UDT), les données UDT sont mises à jour, puis les nouvelles données sont réinsérées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="c00e5-128">In this example, a **Command** object is used to execute a SQL query that returns a UDT, the UDT data is updated, and then the new data is inserted back into the database.</span></span> <span data-ttu-id="c00e5-129">Cet exemple suppose que le type défini par l’utilisateur **Point** a déjà été inscrit dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="c00e5-129">This example assumes that the **Point** UDT has already been registered in the database.</span></span>  
  
```  
Dim con As New ADODB.Connection  
Dim cmd As New ADODB.Command  
Dim rst As New ADODB.Recordset  
Dim strOldUDT As String  
Dim strNewUDT As String  
Dim aryTempUDT() As String  
Dim strTempID As String  
Dim i As Integer  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _  
         & "DataTypeCompatibility=80;"  
  
con.Open  
  
' Get the UDT value.  
Set cmd.ActiveConnection = con  
cmd.CommandText = "SELECT ID, Pnt FROM dbo.Points.ToString()"  
Set rst = cmd.Execute  
strTempID = rst.Fields(0).Value  
strOldUDT = rst.Fields(1).Value  
  
' Do something with the UDT by adding i to each point.  
arytempUDT = Split(strOldUDT, ",")  
i = 3  
strNewUDT = LTrim(Str(Int(aryTempUDT(0)) + i)) + "," + _  
   LTrim(Str(Int(aryTempUDT(1)) + i))  
  
' Insert the new value back into the database.  
cmd.CommandText = "UPDATE dbo.Points SET Pnt = '" + strNewUDT + _  
   "' WHERE ID = '" + strTempID + "'"  
cmd.Execute  
  
con.Close  
Set con = Nothing  
```  
  
### <a name="enabling-and-using-mars"></a><span data-ttu-id="c00e5-130">Activation et utilisation de MARS</span><span class="sxs-lookup"><span data-stu-id="c00e5-130">Enabling and Using MARS</span></span>  
 <span data-ttu-id="c00e5-131">Dans cet exemple, la chaîne de connexion est construite pour activer MARS par le biais du [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client, puis deux objets Recordset sont créés pour s’exécuter à l’aide de la même connexion.</span><span class="sxs-lookup"><span data-stu-id="c00e5-131">In this example, the connection string is constructed to enable MARS through the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, and then two recordset objects are created to execute using the same connection.</span></span>  
  
```  
Dim con As New ADODB.Connection  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _  
         & "DataTypeCompatibility=80;" _  
         & "MARS Connection=True;"  
con.Open  
  
Dim recordset1 As New ADODB.Recordset  
Dim recordset2 As New ADODB.Recordset  
  
Dim recordsaffected As Integer  
Set recordset1 =  con.Execute("SELECT * FROM Table1", recordsaffected, adCmdText)  
Set recordset2 =  con.Execute("SELECT * FROM Table2", recordsaffected, adCmdText)  
  
con.Close  
Set con = Nothing  
```  
  
 <span data-ttu-id="c00e5-132">Dans les versions antérieures du fournisseur OLE DB, ce code provoquait la création d'une connexion implicite lors de la deuxième exécution car un seul jeu de résultats actif par connexion pouvait être ouvert.</span><span class="sxs-lookup"><span data-stu-id="c00e5-132">In prior versions of the OLE DB provider, this code would cause an implicit connection to be created on the second execution because only one active set of results could be opened per a single connection.</span></span> <span data-ttu-id="c00e5-133">La connexion implicite n'étant pas mise dans le pool de connexions OLE DB, cela provoquait une charge supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="c00e5-133">Because the implicit connection was not pooled in the OLE DB connection pool this would cause additional overhead.</span></span> <span data-ttu-id="c00e5-134">Avec la fonctionnalité MARS exposée par le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client, vous recevez plusieurs résultats actifs sur une seule connexion.</span><span class="sxs-lookup"><span data-stu-id="c00e5-134">With the MARS feature exposed by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, you get multiple active results on the one connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c00e5-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c00e5-135">See Also</span></span>  
 [<span data-ttu-id="c00e5-136">Génération d’applications avec SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="c00e5-136">Building Applications with SQL Server Native Client</span></span>](building-applications-with-sql-server-native-client.md)  
  
  
