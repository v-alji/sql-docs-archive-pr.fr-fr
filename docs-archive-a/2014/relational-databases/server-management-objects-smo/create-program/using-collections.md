---
title: Utilisation des collections | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQL Server Management Objects, collections
- SMO [SQL Server], collections
- collections [SMO]
ms.assetid: 209eb175-2514-4de1-bc32-b2e6a469d945
author: stevestein
ms.author: sstein
ms.openlocfilehash: 288f2110952a85d2aab610c0f1da40d433882400
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602005"
---
# <a name="using-collections"></a><span data-ttu-id="080be-102">Utilisation de collections</span><span class="sxs-lookup"><span data-stu-id="080be-102">Using Collections</span></span>
  <span data-ttu-id="080be-103">Une collection est une liste d'objets construits à partir de la même classe d'objets et qui partagent le même objet parent.</span><span class="sxs-lookup"><span data-stu-id="080be-103">A collection is a list of objects that have been constructed from the same object class and that share the same parent object.</span></span> <span data-ttu-id="080be-104">L'objet de collection contient toujours le nom du type d'objet avec le suffixe Collection.</span><span class="sxs-lookup"><span data-stu-id="080be-104">The collection object always contains the name of the object type with the Collection suffix.</span></span> <span data-ttu-id="080be-105">Par exemple, pour accéder aux colonnes dans une table spécifiée, utilisez le type d'objet <xref:Microsoft.SqlServer.Management.Smo.ColumnCollection>.</span><span class="sxs-lookup"><span data-stu-id="080be-105">For example, to access the columns in a specified table, use the <xref:Microsoft.SqlServer.Management.Smo.ColumnCollection> object type.</span></span> <span data-ttu-id="080be-106">Il contient tous les objets <xref:Microsoft.SqlServer.Management.Smo.Column> qui appartiennent au même objet <xref:Microsoft.SqlServer.Management.Smo.Table>.</span><span class="sxs-lookup"><span data-stu-id="080be-106">It contains all the <xref:Microsoft.SqlServer.Management.Smo.Column> objects that belong to the same <xref:Microsoft.SqlServer.Management.Smo.Table> object.</span></span>  
  
 <span data-ttu-id="080be-107">L' [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `For...Each` instruction ou l' [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] `foreach` instruction peut être utilisée pour itérer au sein de chaque membre de la collection.</span><span class="sxs-lookup"><span data-stu-id="080be-107">The [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `For...Each` statement or the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] `foreach` statement can be used to iterate through each member of the collection.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="080be-108">Exemples</span><span class="sxs-lookup"><span data-stu-id="080be-108">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="referencing-an-object-by-using-a-collection-in-visual-basic"></a><span data-ttu-id="080be-109">Référence d'un objet à l'aide d'une collection en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="080be-109">Referencing an Object by Using a Collection in Visual Basic</span></span>  
 <span data-ttu-id="080be-110">Cet exemple de code indique comment définir une propriété de colonne à l'aide des propriétés <xref:Microsoft.SqlServer.Management.Smo.TableViewTableTypeBase.Columns%2A>, <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A> et <xref:Microsoft.SqlServer.Management.Smo.Server.Databases%2A>.</span><span class="sxs-lookup"><span data-stu-id="080be-110">This code example shows how to set a column property by using the <xref:Microsoft.SqlServer.Management.Smo.TableViewTableTypeBase.Columns%2A>, <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A>, and <xref:Microsoft.SqlServer.Management.Smo.Server.Databases%2A> properties.</span></span> <span data-ttu-id="080be-111">Ces propriétés représentent des collections, qui peuvent être utilisées pour identifier un objet particulier lorsqu'elles sont utilisées avec un paramètre qui spécifie le nom de l'objet.</span><span class="sxs-lookup"><span data-stu-id="080be-111">These properties represent collections, which can be used to identify a particular object when they are used with a parameter that specifies the name of the object.</span></span> <span data-ttu-id="080be-112">Le nom et le schéma sont requis pour la propriété d'objet de collection <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A>.</span><span class="sxs-lookup"><span data-stu-id="080be-112">The name and the schema are required for the <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A> collection object property.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBCollections1](SMO How to#SMO_VBCollections1)]  -->  
  
## <a name="referencing-an-object-by-using-a-collection-in-visual-c"></a><span data-ttu-id="080be-113">Référence d'un objet à l'aide d'une collection en Visual C#</span><span class="sxs-lookup"><span data-stu-id="080be-113">Referencing an Object by Using a Collection in Visual C#</span></span>  
 <span data-ttu-id="080be-114">Cet exemple de code indique comment définir une propriété de colonne à l'aide des propriétés <xref:Microsoft.SqlServer.Management.Smo.TableViewTableTypeBase.Columns%2A>, <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A> et <xref:Microsoft.SqlServer.Management.Smo.Server.Databases%2A>.</span><span class="sxs-lookup"><span data-stu-id="080be-114">This code example shows how to set a column property by using the <xref:Microsoft.SqlServer.Management.Smo.TableViewTableTypeBase.Columns%2A>, <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A>, and <xref:Microsoft.SqlServer.Management.Smo.Server.Databases%2A> properties.</span></span> <span data-ttu-id="080be-115">Ces propriétés représentent des collections, qui peuvent être utilisées pour identifier un objet particulier lorsqu'elles sont utilisées avec un paramètre qui spécifie le nom de l'objet.</span><span class="sxs-lookup"><span data-stu-id="080be-115">These properties represent collections, which can be used to identify a particular object when they are used with a parameter that specifies the name of the object.</span></span> <span data-ttu-id="080be-116">Le nom et le schéma sont requis pour la propriété d'objet de collection <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A>.</span><span class="sxs-lookup"><span data-stu-id="080be-116">The name and the schema are required for the <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A> collection object property.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Modify a property using the Databases, Tables, and Columns collections to reference a column.   
srv.Databases("AdventureWorks2012").Tables("Person", "Person").Columns("LastName").Nullable = true;   
//Call the Alter method to make the change on the instance of SQL Server.   
srv.Databases("AdventureWorks2012").Tables("Person", "Person").Columns("LastName").Alter();   
}  
```  
  
## <a name="iterating-through-the-members-of-a-collection-in-visual-basic"></a><span data-ttu-id="080be-117">Parcours des membres d'une collection en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="080be-117">Iterating Through the Members of a Collection in Visual Basic</span></span>  
 <span data-ttu-id="080be-118">Cet exemple de code parcourt la propriété de collection <xref:Microsoft.AnalysisServices.Server.Databases%2A> et affiche toutes les connexions de base de données à l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="080be-118">This code example iterates through the <xref:Microsoft.AnalysisServices.Server.Databases%2A> collection property and displays all database connections to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBCollections2](SMO How to#SMO_VBCollections2)]  -->  
  
## <a name="iterating-through-the-members-of-a-collection-in-visual-c"></a><span data-ttu-id="080be-119">Parcours des membres d'une collection en Visual C#</span><span class="sxs-lookup"><span data-stu-id="080be-119">Iterating Through the Members of a Collection in Visual C#</span></span>  
 <span data-ttu-id="080be-120">Cet exemple de code parcourt la propriété de collection <xref:Microsoft.AnalysisServices.Server.Databases%2A> et affiche toutes les connexions de base de données à l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="080be-120">This code example iterates through the <xref:Microsoft.AnalysisServices.Server.Databases%2A> collection property and displays all database connections to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```  
//Connect to the local, default instance of SQL Server.   
{   
Server srv = default(Server);   
srv = new Server();   
int count = 0;   
int total = 0;   
//Iterate through the databases and call the GetActiveDBConnectionCount method.   
Database db = default(Database);   
foreach ( db in srv.Databases) {   
  count = srv.GetActiveDBConnectionCount(db.Name);   
  total = total + count;   
  //Display the number of connections for each database.   
  Console.WriteLine(count + " connections on " + db.Name);   
}   
//Display the total number of connections on the instance of SQL Server.   
Console.WriteLine("Total connections =" + total);   
}   
```  
  
  
