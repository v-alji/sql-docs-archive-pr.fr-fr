---
title: Utilisation des synonymes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- synonyms [SMO]
ms.assetid: db0a9022-9549-43e5-b6b3-deb236f05fb8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5e8416dc3daea3b173fae92e5454a8a65c399e53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614464"
---
# <a name="using-synonyms"></a><span data-ttu-id="9cca6-102">Utilisation de synonymes</span><span class="sxs-lookup"><span data-stu-id="9cca6-102">Using Synonyms</span></span>
  <span data-ttu-id="9cca6-103">Un synonyme est un alias donné à un objet dans l'étendue du schéma.</span><span class="sxs-lookup"><span data-stu-id="9cca6-103">A synonym is an alternative name for a schema-scoped object.</span></span> <span data-ttu-id="9cca6-104">Dans SMO, les synonymes sont représentés par l'objet <xref:Microsoft.SqlServer.Management.Smo.Synonym>.</span><span class="sxs-lookup"><span data-stu-id="9cca6-104">In SMO, synonyms are represented by the <xref:Microsoft.SqlServer.Management.Smo.Synonym> object.</span></span> <span data-ttu-id="9cca6-105">L'objet <xref:Microsoft.SqlServer.Management.Smo.Synonym> est un enfant de l'objet <xref:Microsoft.SqlServer.Management.Smo.Database>.</span><span class="sxs-lookup"><span data-stu-id="9cca6-105">The <xref:Microsoft.SqlServer.Management.Smo.Synonym> object is a child of the <xref:Microsoft.SqlServer.Management.Smo.Database> object.</span></span> <span data-ttu-id="9cca6-106">Cela signifie que les synonymes ne sont valides que dans le contexte de la base de données dans laquelle ils ont été définis.</span><span class="sxs-lookup"><span data-stu-id="9cca6-106">This means that synonyms are valid only within the scope of the database in which they are defined.</span></span> <span data-ttu-id="9cca6-107">Toutefois, le synonyme peut faire référence aux objets d'une autre base de données ou d'une instance distante de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9cca6-107">However, the synonym can refer to objects on another database, or on a remote instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9cca6-108">L'objet auquel est attribué un alias est l'objet de base.</span><span class="sxs-lookup"><span data-stu-id="9cca6-108">The object that is given an alternative name is known as the base object.</span></span> <span data-ttu-id="9cca6-109">La propriété de nom de l'objet <xref:Microsoft.SqlServer.Management.Smo.Synonym> est l'alias attribué à l'objet de base.</span><span class="sxs-lookup"><span data-stu-id="9cca6-109">The name property of the <xref:Microsoft.SqlServer.Management.Smo.Synonym> object is the alternative name given to the base object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cca6-110">Exemple</span><span class="sxs-lookup"><span data-stu-id="9cca6-110">Example</span></span>  
 <span data-ttu-id="9cca6-111">Dans l'exemple de code suivant, vous devez sélectionner l'environnement, le modèle et le langage de programmation à utiliser pour créer votre application.</span><span class="sxs-lookup"><span data-stu-id="9cca6-111">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="9cca6-112">Pour plus d’informations, consultez [créer un projet Visual Basic Smo dans Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) et [créer un projet Visual C&#35; Smo dans Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="9cca6-112">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-synonym-in-visual-basic"></a><span data-ttu-id="9cca6-113">Création d'un synonyme en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9cca6-113">Creating a Synonym in Visual Basic</span></span>  
 <span data-ttu-id="9cca6-114">L'exemple de code montre comment créer un synonyme ou un alias pour un objet compris dans l'étendue du schéma.</span><span class="sxs-lookup"><span data-stu-id="9cca6-114">The code example shows how to create a synonym or an alternate name for a schema scoped object.</span></span> <span data-ttu-id="9cca6-115">Les applications clientes peuvent utiliser une référence unique pour l'objet de base par le biais d'un synonyme, au lieu d'employer une référence en plusieurs parties à l'objet de base.</span><span class="sxs-lookup"><span data-stu-id="9cca6-115">Client applications can use a single reference for the base object via a synonym instead of using a multiple part name to reference the base object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBSynonyms1](SMO How to#SMO_VBSynonyms1)]  -->  
  
## <a name="creating-a-synonym-in-visual-c"></a><span data-ttu-id="9cca6-116">Création d'un synonyme en Visual C#</span><span class="sxs-lookup"><span data-stu-id="9cca6-116">Creating a Synonym in Visual C#</span></span>  
 <span data-ttu-id="9cca6-117">L'exemple de code montre comment créer un synonyme ou un alias pour un objet compris dans l'étendue du schéma.</span><span class="sxs-lookup"><span data-stu-id="9cca6-117">The code example shows how to create a synonym or an alternate name for a schema scoped object.</span></span> <span data-ttu-id="9cca6-118">Les applications clientes peuvent utiliser une référence unique pour l'objet de base par le biais d'un synonyme, au lieu d'employer une référence en plusieurs parties à l'objet de base.</span><span class="sxs-lookup"><span data-stu-id="9cca6-118">Client applications can use a single reference for the base object via a synonym instead of using a multiple part name to reference the base object.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
  
            //Reference the AdventureWorks2012 database.   
            Database db = srv.Databases["AdventureWorks2012"];  
  
            //Define a Synonym object variable by supplying the   
            //parent database, name, and schema arguments in the constructor.   
            //The name is also a synonym of the name of the base object.   
            Synonym syn = new Synonym(db, "Shop", "Sales");  
  
            //Specify the base object, which is the object on which   
            //the synonym is based.   
            syn.BaseDatabase = "AdventureWorks2012";  
            syn.BaseSchema = "Sales";  
            syn.BaseObject = "Store";  
            syn.BaseServer = srv.Name;  
  
            //Create the synonym on the instance of SQL Server.   
            syn.Create();  
        }  
```  
  
## <a name="creating-a-synonym-in-powershell"></a><span data-ttu-id="9cca6-119">Création d'un synonyme dans PowerShell</span><span class="sxs-lookup"><span data-stu-id="9cca6-119">Creating a Synonym in PowerShell</span></span>  
 <span data-ttu-id="9cca6-120">L'exemple de code montre comment créer un synonyme ou un alias pour un objet compris dans l'étendue du schéma.</span><span class="sxs-lookup"><span data-stu-id="9cca6-120">The code example shows how to create a synonym or an alternate name for a schema scoped object.</span></span> <span data-ttu-id="9cca6-121">Les applications clientes peuvent utiliser une référence unique pour l'objet de base par le biais d'un synonyme, au lieu d'employer une référence en plusieurs parties à l'objet de base.</span><span class="sxs-lookup"><span data-stu-id="9cca6-121">Client applications can use a single reference for the base object via a synonym instead of using a multiple part name to reference the base object.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#And the database object corresponding to Adventureworks  
$db = $srv.Databases["AdventureWorks2012"]  
  
$syn = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Synonym -ArgumentList $db, "Shop", "Sales"  
  
#Specify the base object, which is the object on which the synonym is based.  
$syn.BaseDatabase = "AdventureWorks2012"  
$syn.BaseSchema = "Sales"  
$syn.BaseObject = "Store"  
$syn.BaseServer = $srv.Name  
  
#Create the synonym on the instance of SQL Server.  
$syn.Create()  
```  
  
## <a name="see-also"></a><span data-ttu-id="9cca6-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9cca6-122">See Also</span></span>  
 [<span data-ttu-id="9cca6-123">CREATE SYNONYM &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9cca6-123">CREATE SYNONYM &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-synonym-transact-sql)  
