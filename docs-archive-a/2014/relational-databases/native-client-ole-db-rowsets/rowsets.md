---
title: Ensembles de lignes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- rowsets [OLE DB], about rowsets
- SQL Server Native Client OLE DB provider, rowsets
- OLE DB rowsets
- OLE DB rowsets, about rowsets
- rowsets [OLE DB]
ms.assetid: 5e7b3cbe-3670-4e18-8172-2226e0b6b142
author: rothja
ms.author: jroth
ms.openlocfilehash: 1245d17dc0f3757b3c212146c8c162de6e48a483
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602826"
---
# <a name="rowsets"></a><span data-ttu-id="a0ef8-102">Ensembles de lignes</span><span class="sxs-lookup"><span data-stu-id="a0ef8-102">Rowsets</span></span>
  <span data-ttu-id="a0ef8-103">Un ensemble de lignes est un jeu de lignes contenant des colonnes de données.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-103">A rowset is a set of rows that contain columns of data.</span></span> <span data-ttu-id="a0ef8-104">Les ensembles de lignes sont des objets centraux qui permettent à tous les fournisseurs de données OLE DB d'exposer les données des jeux de résultats sous forme tabulaire.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-104">Rowsets are central objects that enable all OLE DB data providers to expose result set data in tabular form.</span></span>  
  
 <span data-ttu-id="a0ef8-105">Après avoir créé une session en utilisant la méthode **IDBCreateSession::CreateSession**, le consommateur peut utiliser l’interface **IOpenRowset** ou **IDBCreateCommand** dans la session pour créer un ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-105">After a consumer creates a session by using the **IDBCreateSession::CreateSession** method, the consumer can use either the **IOpenRowset** or **IDBCreateCommand** interface on the session to create a rowset.</span></span> <span data-ttu-id="a0ef8-106">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client prend en charge ces deux interfaces.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports both of these interfaces.</span></span> <span data-ttu-id="a0ef8-107">Ces deux méthodes sont décrites ici.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-107">Both of these methods are described here.</span></span>  
  
-   <span data-ttu-id="a0ef8-108">Créer un ensemble de lignes en appelant la méthode **IOpenRowset::OpenRowset**.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-108">Create a rowset by calling the **IOpenRowset::OpenRowset** method.</span></span>  
  
     <span data-ttu-id="a0ef8-109">Cette solution est équivalente à la création d'un ensemble de lignes sur une même table.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-109">This is equivalent to creating a rowset over a single table.</span></span> <span data-ttu-id="a0ef8-110">Cette méthode ouvre et retourne un ensemble de lignes qui inclut toutes les lignes d'une même table de base.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-110">This method opens and returns a rowset that includes all of the rows from a single base table.</span></span> <span data-ttu-id="a0ef8-111">L’un des arguments transmis à **OpenRowset** est un ID qui identifie la table à partir de laquelle créer l’ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-111">One of the arguments to **OpenRowset** is a table ID that identifies the table from which to create the rowset.</span></span>  
  
-   <span data-ttu-id="a0ef8-112">Créer un objet de commande en appelant la méthode **IDBCreateCommand::CreateCommand**.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-112">Create a command object by calling the **IDBCreateCommand::CreateCommand** method.</span></span>  
  
     <span data-ttu-id="a0ef8-113">L'objet de commande exécute les commandes que le fournisseur prend en charge.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-113">The command object executes commands that the provider supports.</span></span> <span data-ttu-id="a0ef8-114">Avec le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, le consommateur peut spécifier une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)], telle qu'une instruction SELECT ou l'appel d'une procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-114">With the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the consumer can specify any [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, such as a SELECT statement or a call to a stored procedure.</span></span> <span data-ttu-id="a0ef8-115">Les étapes de la création d'un ensemble de lignes en utilisant un objet de commande sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a0ef8-115">The steps for creating a rowset by using a command object are:</span></span>  
  
    1.  <span data-ttu-id="a0ef8-116">Le consommateur appelle la méthode **IDBCreateCommand::CreateCommand** dans la session pour obtenir un objet de commande qui demande l’interface **ICommandText** dans l’objet de commande.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-116">The consumer calls the **IDBCreateCommand::CreateCommand** method on the session to get a command object requesting the **ICommandText** interface on the command object.</span></span> <span data-ttu-id="a0ef8-117">Cette interface **ICommandText** définit et récupère le texte de la commande.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-117">This **ICommandText** interface sets and retrieves the actual command text.</span></span> <span data-ttu-id="a0ef8-118">Le consommateur remplit la commande de texte en appelant la méthode **ICommandText::SetCommandText**.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-118">The consumer fills in the text command by calling the **ICommandText::SetCommandText** method.</span></span>  
  
    2.  <span data-ttu-id="a0ef8-119">L’utilisateur appelle la méthode **ICommand::Execute** dans la commande.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-119">The user calls the **ICommand::Execute** method on the command.</span></span> <span data-ttu-id="a0ef8-120">L'objet de l'ensemble de lignes créé lors de l'exécution de la commande contient le jeu de résultats de la commande.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-120">The rowset object built when the command executes contains the result set from the command.</span></span>  
  
 <span data-ttu-id="a0ef8-121">Le consommateur peut utiliser l’interface **ICommandProperties** pour obtenir ou définir les propriétés de l’ensemble de lignes retourné par la commande exécutée par les interfaces **ICommand::Execute**.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-121">The consumer can use the **ICommandProperties** interface to get or set the properties for the rowset returned by the command executed by the **ICommand::Execute** interfaces.</span></span> <span data-ttu-id="a0ef8-122">Les propriétés les plus communément demandées sont les interfaces que l'ensemble de lignes doit prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-122">The most commonly requested properties are the interfaces the rowset must support.</span></span> <span data-ttu-id="a0ef8-123">En plus des interfaces, le consommateur peut demander les propriétés qui modifient le comportement de l'ensemble de lignes ou de l'interface.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-123">In addition to interfaces, the consumer can request properties that modify the behavior of the rowset or interface.</span></span>  
  
 <span data-ttu-id="a0ef8-124">Les consommateurs libèrent les ensembles de lignes avec la méthode **IRowset::Release**.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-124">Consumers release rowsets with the **IRowset::Release** method.</span></span> <span data-ttu-id="a0ef8-125">La libération d'un ensemble de lignes entraîne celle des handles de ligne détenus par le consommateur sur cet ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-125">Releasing a rowset releases any row handles held by the consumer on that rowset.</span></span> <span data-ttu-id="a0ef8-126">La libération d'un ensemble de lignes ne libère pas les accesseurs.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-126">Releasing a rowset does not release the accessors.</span></span> <span data-ttu-id="a0ef8-127">Si vous avez une interface **IAccessor**, il lui reste à être libérée.</span><span class="sxs-lookup"><span data-stu-id="a0ef8-127">If you have an **IAccessor** interface, it still has to be released.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a0ef8-128">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="a0ef8-128">In This Section</span></span>  
  
-   [<span data-ttu-id="a0ef8-129">Création d'un ensemble de lignes avec IOpenRowset</span><span class="sxs-lookup"><span data-stu-id="a0ef8-129">Creating a Rowset with IOpenRowset</span></span>](creating-a-rowset-with-iopenrowset.md)  
  
-   [<span data-ttu-id="a0ef8-130">Création d'ensembles de lignes avec ICommand::Execute</span><span class="sxs-lookup"><span data-stu-id="a0ef8-130">Creating Rowsets with ICommand::Execute</span></span>](creating-rowsets-with-icommand-execute.md)  
  
-   [<span data-ttu-id="a0ef8-131">Propriétés et comportements de l’ensemble de lignes</span><span class="sxs-lookup"><span data-stu-id="a0ef8-131">Rowset Properties and Behaviors</span></span>](rowset-properties-and-behaviors.md)  
  
-   [<span data-ttu-id="a0ef8-132">Ensembles de lignes et curseurs SQL Server</span><span class="sxs-lookup"><span data-stu-id="a0ef8-132">Rowsets and SQL Server Cursors</span></span>](rowsets-and-sql-server-cursors.md)  
  
-   [<span data-ttu-id="a0ef8-133">Extraction de lignes</span><span class="sxs-lookup"><span data-stu-id="a0ef8-133">Fetching Rows</span></span>](fetching-rows.md)  
  
-   [<span data-ttu-id="a0ef8-134">Extraction d'une ligne unique avec IRow</span><span class="sxs-lookup"><span data-stu-id="a0ef8-134">Fetching a Single Row with IRow</span></span>](fetching-a-single-row-with-irow.md)  
  
-   [<span data-ttu-id="a0ef8-135">Signets</span><span class="sxs-lookup"><span data-stu-id="a0ef8-135">Bookmarks</span></span>](bookmarks.md)  
  
-   [<span data-ttu-id="a0ef8-136">Mise à jour des données dans les ensembles de lignes</span><span class="sxs-lookup"><span data-stu-id="a0ef8-136">Updating Data in Rowsets</span></span>](updating-data-in-rowsets.md)  
  
## <a name="see-also"></a><span data-ttu-id="a0ef8-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a0ef8-137">See Also</span></span>  
 [<span data-ttu-id="a0ef8-138">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="a0ef8-138">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
