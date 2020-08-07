---
title: Définition des propriétés | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SMO [SQL Server], properties
- SQL Server Management Objects, properties
- properties [SMO]
ms.assetid: 342569ba-d2f7-44d2-8f3f-ae9c701c7f0f
author: stevestein
ms.author: sstein
ms.openlocfilehash: de381f8e4e9dfe9f6590638742e988f866ccabdc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704008"
---
# <a name="setting-properties"></a><span data-ttu-id="31c23-102">Définition de propriétés</span><span class="sxs-lookup"><span data-stu-id="31c23-102">Setting Properties</span></span>
  <span data-ttu-id="31c23-103">Les propriétés sont des valeurs qui stockent des informations descriptives sur l'objet.</span><span class="sxs-lookup"><span data-stu-id="31c23-103">Properties are values that store descriptive information about the object.</span></span> <span data-ttu-id="31c23-104">Par exemple, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] les options de configuration sont représentées par les <xref:Microsoft.SqlServer.Management.Smo.Server.Configuration%2A> Propriétés de l’objet.</span><span class="sxs-lookup"><span data-stu-id="31c23-104">For example, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] configuration options are represented by the <xref:Microsoft.SqlServer.Management.Smo.Server.Configuration%2A> object's properties.</span></span> <span data-ttu-id="31c23-105">Les propriétés sont accessibles soit directement, soit indirectement par le biais de la collection de propriétés.</span><span class="sxs-lookup"><span data-stu-id="31c23-105">Properties can be accessed either directly or indirectly by using the property collection.</span></span> <span data-ttu-id="31c23-106">L'accès aux propriétés utilise directement la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="31c23-106">Accessing properties directly uses the following syntax:</span></span>  
  
 `objInstance.PropertyName`  
  
 <span data-ttu-id="31c23-107">Une valeur de propriété peut être modifiée ou récupérée selon que la propriété dispose d'un accès en lecture/écriture ou d'un accès en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="31c23-107">A property value can be modified or retrieved depending on whether the property has read/write access or read-only access.</span></span> <span data-ttu-id="31c23-108">Il est également nécessaire de définir certaines propriétés avant qu'un objet ne puisse être créé.</span><span class="sxs-lookup"><span data-stu-id="31c23-108">It is also necessary to set certain properties before an object can be created.</span></span> <span data-ttu-id="31c23-109">Pour plus d'informations, consultez la référence SMO pour l'objet particulier.</span><span class="sxs-lookup"><span data-stu-id="31c23-109">For more information, see the SMO reference for the particular object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31c23-110">Les collections d'objets enfants apparaissent en tant que propriété d'un objet.</span><span class="sxs-lookup"><span data-stu-id="31c23-110">Collections of child objects appear as the property of an object.</span></span> <span data-ttu-id="31c23-111">Par exemple, la collection `Tables` est une propriété d'un objet `Server`.</span><span class="sxs-lookup"><span data-stu-id="31c23-111">For example, the `Tables` collection is a property of a `Server` object.</span></span> <span data-ttu-id="31c23-112">Pour plus d'informations, voir [Using Collections](using-collections.md).</span><span class="sxs-lookup"><span data-stu-id="31c23-112">For more information, see [Using Collections](using-collections.md).</span></span>  
  
 <span data-ttu-id="31c23-113">Les propriétés d'un objet sont membres de la collection Properties.</span><span class="sxs-lookup"><span data-stu-id="31c23-113">The properties of an object are members of the Properties collection.</span></span> <span data-ttu-id="31c23-114">La collection Properties peut être utilisée pour parcourir chaque propriété d'un objet.</span><span class="sxs-lookup"><span data-stu-id="31c23-114">The Properties collection can be used to iterate through every property of an object.</span></span>  
  
 <span data-ttu-id="31c23-115">Parfois, une propriété n'est pas disponible pour les raisons suivantes :</span><span class="sxs-lookup"><span data-stu-id="31c23-115">Sometimes a property is not available for the following reasons:</span></span>  
  
-   <span data-ttu-id="31c23-116">La version du serveur ne prend pas en charge la propriété, notamment si vous essayez d'accéder à une propriété représentant une nouvelle fonctionnalité [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sur une ancienne version de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31c23-116">The server version does not support the property, such as if you try to access a property that represents a new [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] feature on an older version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="31c23-117">Le serveur ne fournit pas de données pour la propriété, notamment si vous essayez d'accéder à une propriété représentant un composant [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] qui n'est pas installé.</span><span class="sxs-lookup"><span data-stu-id="31c23-117">The server does not provide data for the property, such as if you try to access a property that represents a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] component that is not installed.</span></span>  
  
 <span data-ttu-id="31c23-118">Vous pouvez gérer ces circonstances en interceptant les exceptions SMO <xref:Microsoft.SqlServer.Management.Smo.UnknownPropertyException> et <xref:Microsoft.SqlServer.Management.Smo.PropertyCannotBeRetrievedException>.</span><span class="sxs-lookup"><span data-stu-id="31c23-118">You can handle these circumstances by catching the <xref:Microsoft.SqlServer.Management.Smo.UnknownPropertyException> and the <xref:Microsoft.SqlServer.Management.Smo.PropertyCannotBeRetrievedException> SMO exceptions.</span></span>  
  
## <a name="setting-default-initialization-fields"></a><span data-ttu-id="31c23-119">Définition des champs d'initialisation par défaut</span><span class="sxs-lookup"><span data-stu-id="31c23-119">Setting Default Initialization Fields</span></span>  
 <span data-ttu-id="31c23-120">SMO effectue une optimisation lors de la récupération d'objets.</span><span class="sxs-lookup"><span data-stu-id="31c23-120">SMO performs an optimization when retrieving objects.</span></span> <span data-ttu-id="31c23-121">L'optimisation réduit le nombre de propriétés chargées en procédant automatiquement à une mise à l'échelle entre les états suivants :</span><span class="sxs-lookup"><span data-stu-id="31c23-121">The optimization minimizes the number of properties loaded by automatically scaling between the following states:</span></span>  
  
1.  <span data-ttu-id="31c23-122">Partiellement chargé.</span><span class="sxs-lookup"><span data-stu-id="31c23-122">Partially loaded.</span></span> <span data-ttu-id="31c23-123">Lorsqu'un objet est référencé pour la première fois, il dispose d'un nombre minimal de propriétés (telles que Nom et Schéma).</span><span class="sxs-lookup"><span data-stu-id="31c23-123">When an object is first referenced it has a minimum of properties available (such as Name and Schema).</span></span>  
  
2.  <span data-ttu-id="31c23-124">Complètement chargé.</span><span class="sxs-lookup"><span data-stu-id="31c23-124">Fully loaded.</span></span> <span data-ttu-id="31c23-125">Lorsqu'une propriété est référencée, les propriétés restantes à chargement rapide sont initialisées et mises à disposition.</span><span class="sxs-lookup"><span data-stu-id="31c23-125">When any property is referenced, the remaining properties that are quick to load, are initialized and are made available.</span></span>  
  
3.  <span data-ttu-id="31c23-126">Propriétés qui utilisent beaucoup de mémoire.</span><span class="sxs-lookup"><span data-stu-id="31c23-126">Properties that use lots of memory.</span></span> <span data-ttu-id="31c23-127">Les propriétés non disponibles restantes utilisent beaucoup de mémoire et la valeur de la propriété <xref:Microsoft.SqlServer.Management.Smo.Property.Expensive%2A> est True (par exemple <xref:Microsoft.SqlServer.Management.Smo.Database.DataSpaceUsage%2A>).</span><span class="sxs-lookup"><span data-stu-id="31c23-127">The remaining unavailable properties use lots of memory and have an <xref:Microsoft.SqlServer.Management.Smo.Property.Expensive%2A> property value of true (such as <xref:Microsoft.SqlServer.Management.Smo.Database.DataSpaceUsage%2A>).</span></span> <span data-ttu-id="31c23-128">Ces propriétés sont chargées uniquement lorsqu'elles sont spécifiquement référencées.</span><span class="sxs-lookup"><span data-stu-id="31c23-128">These properties are loaded only when specifically referenced.</span></span>  
  
 <span data-ttu-id="31c23-129">Si votre application extrait des propriétés supplémentaires, en plus de celles fournies dans l'état partiellement chargé, elle envoie une requête pour récupérer ces propriétés supplémentaires et passe à l'état complètement chargé.</span><span class="sxs-lookup"><span data-stu-id="31c23-129">If your application does fetch extra properties, besides the ones provided in the partially loaded state, it submits a query to retrieve these extra properties and scales up to the fully loaded state.</span></span> <span data-ttu-id="31c23-130">Cela peut générer un trafic inutile entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="31c23-130">This can cause unnecessary traffic between the client and server.</span></span> <span data-ttu-id="31c23-131">Vous pouvez bénéficier d'une meilleure optimisation en appelant la méthode <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A>.</span><span class="sxs-lookup"><span data-stu-id="31c23-131">More optimization can be achieved by calling the <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> method.</span></span> <span data-ttu-id="31c23-132">La méthode <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> vous permet de spécifier des propriétés qui sont chargées lors de l'initialisation de l'objet.</span><span class="sxs-lookup"><span data-stu-id="31c23-132">The <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> method allows specification of the properties that are loaded when the object is initialized.</span></span>  
  
 <span data-ttu-id="31c23-133">La méthode <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> définit le comportement de chargement des propriétés pour le reste de l'application ou jusqu'à ce qu'elle soit réinitialisée.</span><span class="sxs-lookup"><span data-stu-id="31c23-133">The <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> method sets the property loading behavior for the rest of application or until it is reset.</span></span> <span data-ttu-id="31c23-134">Vous pouvez enregistrer le comportement d'origine en utilisant la méthode <xref:Microsoft.SqlServer.Management.Smo.Server.GetDefaultInitFields%2A> et en la restaurant selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="31c23-134">You can save the original behavior by using the <xref:Microsoft.SqlServer.Management.Smo.Server.GetDefaultInitFields%2A> method and restore it as required.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="31c23-135">Exemples</span><span class="sxs-lookup"><span data-stu-id="31c23-135">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="getting-and-setting-a-property-in-visual-basic"></a><span data-ttu-id="31c23-136">Obtention et définition d'une propriété en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="31c23-136">Getting and Setting a Property in Visual Basic</span></span>  
 <span data-ttu-id="31c23-137">Cet exemple de code montre comment obtenir la propriété <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> de l'objet <xref:Microsoft.SqlServer.Management.Smo.Information> et comment attribuer à la propriété <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> de la propriété <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> le membre `ExecuteSql` du type énuméré <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes>.</span><span class="sxs-lookup"><span data-stu-id="31c23-137">This code example shows how to get the <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Information> object and how to set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> property to the `ExecuteSql` member of the <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes> enumerated type.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBProperties1](SMO How to#SMO_VBProperties1)]  -->  
  
## <a name="getting-and-setting-a-property-in-visual-c"></a><span data-ttu-id="31c23-138">Obtention et définition d'une propriété en Visual C#</span><span class="sxs-lookup"><span data-stu-id="31c23-138">Getting and Setting a Property in Visual C#</span></span>  
 <span data-ttu-id="31c23-139">Cet exemple de code montre comment obtenir la propriété <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> de l'objet <xref:Microsoft.SqlServer.Management.Smo.Information> et comment attribuer à la propriété <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> de la propriété <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> le membre `ExecuteSql` du type énuméré <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes>.</span><span class="sxs-lookup"><span data-stu-id="31c23-139">This code example shows how to get the <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Information> object and how to set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> property to the `ExecuteSql` member of the <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes> enumerated type.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Get a property.   
Console.WriteLine(srv.Information.Version);   
//Set a property.   
srv.ConnectionContext.SqlExecutionModes = SqlExecutionModes.ExecuteSql;   
}  
```  
  
## <a name="setting-various-properties-before-an-object-is-created-in-visual-basic"></a><span data-ttu-id="31c23-140">Définition de différentes propriétés avant la création d'un objet en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="31c23-140">Setting Various Properties Before an Object is Created in Visual Basic</span></span>  
 <span data-ttu-id="31c23-141">Cet exemple de code montre comment définir directement la propriété <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> de l'objet <xref:Microsoft.SqlServer.Management.Smo.Table>, et comment créer et ajouter des colonnes avant de créer l'objet <xref:Microsoft.SqlServer.Management.Smo.Table>.</span><span class="sxs-lookup"><span data-stu-id="31c23-141">This code example shows how to directly set the <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Table> object, and how to create and add columns before you create the <xref:Microsoft.SqlServer.Management.Smo.Table> object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBProperties2](SMO How to#SMO_VBProperties2)]  -->  
  
## <a name="setting-various-properties-before-an-object-is-created-in-visual-c"></a><span data-ttu-id="31c23-142">Définition de différentes propriétés avant la création d'un objet en Visual C#</span><span class="sxs-lookup"><span data-stu-id="31c23-142">Setting Various Properties Before an Object is Created in Visual C#</span></span>  
 <span data-ttu-id="31c23-143">Cet exemple de code montre comment définir directement la propriété <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> de l'objet <xref:Microsoft.SqlServer.Management.Smo.Table>, et comment créer et ajouter des colonnes avant de créer l'objet <xref:Microsoft.SqlServer.Management.Smo.Table>.</span><span class="sxs-lookup"><span data-stu-id="31c23-143">This code example shows how to directly set the <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Table> object, and how to create and add columns before you create the <xref:Microsoft.SqlServer.Management.Smo.Table> object.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Create a new table in the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
Table tb;   
//Specify the parent database, table schema, and the table name in the constructor.   
tb = new Table(db, "Test_Table", "HumanResources");   
//Add columns because the table requires columns before it can be created.   
Column c1;   
//Specify the parent table, the column name, and data type in the constructor.   
c1 = new Column(tb, "ID", DataType.Int);   
tb.Columns.Add(c1);   
c1.Nullable = false;   
c1.Identity = true;   
c1.IdentityIncrement = 1;   
c1.IdentitySeed = 0;   
Column c2;   
c2 = new Column(tb, "Name", DataType.NVarChar(100));   
c2.Nullable = false;   
tb.Columns.Add(c2);   
tb.AnsiNullsStatus = true;   
//Create the table on the instance of SQL Server.   
tb.Create();   
}  
```  
  
## <a name="iterating-through-all-properties-of-an-object-in-visual-basic"></a><span data-ttu-id="31c23-144">Parcours de toutes les propriétés d'un objet en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="31c23-144">Iterating Through All Properties of an Object in Visual Basic</span></span>  
 <span data-ttu-id="31c23-145">Cet exemple de code parcourt la collection `Properties` de l'objet <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> et affiche les propriétés dans l'écran de sortie de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31c23-145">This code example iterates through the `Properties` collection of the <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> object and displays them on the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Output screen.</span></span>  
  
 <span data-ttu-id="31c23-146">Dans l'exemple, l'objet <xref:Microsoft.SqlServer.Management.Smo.Property> a été mis entre crochets car il s'agit également d'un mot clé dans [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31c23-146">In the example, the <xref:Microsoft.SqlServer.Management.Smo.Property> object has been put in square parentheses because it is also a [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] keyword.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBProperties3](SMO How to#SMO_VBProperties3)]  -->  
  
## <a name="iterating-through-all-properties-of-an-object-in-visual-c"></a><span data-ttu-id="31c23-147">Parcours de toutes les propriétés d'un objet en Visual C#</span><span class="sxs-lookup"><span data-stu-id="31c23-147">Iterating Through All Properties of an Object in Visual C#</span></span>  
 <span data-ttu-id="31c23-148">Cet exemple de code parcourt la collection `Properties` de l'objet <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> et affiche les propriétés dans l'écran de sortie de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31c23-148">This code example iterates through the `Properties` collection of the <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> object and displays them on the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Output screen.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Set properties on the uspGetEmployeedManagers stored procedure on the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
StoredProcedure sp;   
sp = db.StoredProcedures("uspGetEmployeeManagers");   
sp.AnsiNullsStatus = false;   
sp.QuotedIdentifierStatus = false;   
//Iterate through the properties of the stored procedure and display.   
  Property p;   
  foreach ( p in sp.Properties) {   
    Console.WriteLine(p.Name + p.Value);   
  }   
}  
```  
  
## <a name="setting-default-initialization-fields-in-visual-basic"></a><span data-ttu-id="31c23-149">Définition des champs d'initialisation par défaut en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="31c23-149">Setting Default Initialization Fields in Visual Basic</span></span>  
 <span data-ttu-id="31c23-150">Cet exemple de code montre comment réduire le nombre de propriétés d'objet initialisées dans un programme SMO.</span><span class="sxs-lookup"><span data-stu-id="31c23-150">This code example shows how to minimize the number of object properties initialized in an SMO program.</span></span> <span data-ttu-id="31c23-151">Vous devez inclure l'instruction `using System.Collections.Specialized` pour utiliser l'objet <xref:System.Collections.Specialized.StringCollection>.</span><span class="sxs-lookup"><span data-stu-id="31c23-151">You have to include the `using System.Collections.Specialized`; statement to use the <xref:System.Collections.Specialized.StringCollection> object.</span></span>  
  
 [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] <span data-ttu-id="31c23-152">peut être utilisé pour comparer le nombre d'instructions envoyées à l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] avec cette optimisation.</span><span class="sxs-lookup"><span data-stu-id="31c23-152">can be used to compare the number statements sent to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with this optimization.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDefaultInitFields1](SMO How to#SMO_VBDefaultInitFields1)]  -->  
  
## <a name="setting-default-initialization-fields-in-visual-c"></a><span data-ttu-id="31c23-153">Définition des champs d'initialisation par défaut en Visual C#</span><span class="sxs-lookup"><span data-stu-id="31c23-153">Setting Default Initialization Fields in Visual C#</span></span>  
 <span data-ttu-id="31c23-154">Cet exemple de code montre comment réduire le nombre de propriétés d'objet initialisées dans un programme SMO.</span><span class="sxs-lookup"><span data-stu-id="31c23-154">This code example shows how to minimize the number of object properties initialized in an SMO program.</span></span> <span data-ttu-id="31c23-155">Vous devez inclure l'instruction `using System.Collections.Specialized` pour utiliser l'objet <xref:System.Collections.Specialized.StringCollection>.</span><span class="sxs-lookup"><span data-stu-id="31c23-155">You have to include the `using System.Collections.Specialized`; statement to use the <xref:System.Collections.Specialized.StringCollection> object.</span></span>  
  
 [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] <span data-ttu-id="31c23-156">peut être utilisé pour comparer le nombre d'instructions envoyées à l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] avec cette optimisation.</span><span class="sxs-lookup"><span data-stu-id="31c23-156">can be used to compare the number statements sent to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with this optimization.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Reference the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
//Assign the Table object type to a System.Type object variable.   
Table tb;   
Type typ;   
tb = new Table();   
typ = tb.GetType;   
//Assign the current default initialization fields for the Table object type to a   
//StringCollection object variable.   
StringCollection sc;   
sc = srv.GetDefaultInitFields(typ);   
//Set the default initialization fields for the Table object type to the CreateDate property.   
srv.SetDefaultInitFields(typ, "CreateDate");   
//Retrieve the Schema, Name, and CreateDate properties for every table in AdventureWorks2012.   
   //Note that the improvement in performance can be viewed in SQL Server Profiler.   
foreach ( tb in db.Tables) {   
   Console.WriteLine(tb.Schema + "." + tb.Name + " " + tb.CreateDate);   
}   
//Set the default initialization fields for the Table object type back to the original settings.   
srv.SetDefaultInitFields(typ, sc);   
}  
```  
  
  
