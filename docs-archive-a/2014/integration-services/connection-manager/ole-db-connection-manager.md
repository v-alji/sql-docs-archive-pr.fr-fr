---
title: Gestionnaire de connexions OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- OLE DB connection manager
- data sources [Integration Services], connections
- connection managers [Integration Services], OLE DB
- connections [Integration Services], OLE DB
ms.assetid: 91e3622e-4b1a-439a-80c7-a00b90d66979
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5431de956a1039c2978688982792f190b0abc544
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611220"
---
# <a name="ole-db-connection-manager"></a><span data-ttu-id="7d4bd-102">Gestionnaire de connexions OLE DB</span><span class="sxs-lookup"><span data-stu-id="7d4bd-102">OLE DB Connection Manager</span></span>
  <span data-ttu-id="7d4bd-103">Un gestionnaire de connexions OLE DB permet à un package de se connecter à une source de données à l'aide d'un fournisseur OLE DB.</span><span class="sxs-lookup"><span data-stu-id="7d4bd-103">An OLE DB connection manager enables a package to connect to a data source by using an OLE DB provider.</span></span> <span data-ttu-id="7d4bd-104">Par exemple, un gestionnaire de connexions OLE DB qui se connecte à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut utiliser le fournisseur [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d4bd-104">For example, an OLE DB connection manager that connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d4bd-105">Le fournisseur OLEDB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 11.0 ne prend pas en charge les mots clés de la nouvelle chaîne de connexion (MultiSubnetFailover=True) pour le clustering de basculement de sous-réseaux multiples.</span><span class="sxs-lookup"><span data-stu-id="7d4bd-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 11.0 OLEDB provider does not support the new connection string key words (MultiSubnetFailover=True) for Multi-Subnet Failover Clustering.</span></span> <span data-ttu-id="7d4bd-106">Pour plus d’informations, consultez les [notes de publication de SQL Server](https://go.microsoft.com/fwlink/?LinkId=247824) et le billet de blog [AlwaysOn multi-Subnet Failover and SSIS](https://www.mattmasson.com/2012/03/alwayson-multi-subnet-failover-and-ssis/), sur www.mattmasson.com.</span><span class="sxs-lookup"><span data-stu-id="7d4bd-106">For more information, see the [SQL Server Release  Notes](https://go.microsoft.com/fwlink/?LinkId=247824) and the blog post, [AlwaysOn Multi-Subnet Failover and SSIS](https://www.mattmasson.com/2012/03/alwayson-multi-subnet-failover-and-ssis/), on www.mattmasson.com.</span></span>  
  
 <span data-ttu-id="7d4bd-107">Plusieurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] tâches et composants de processus de données utilisent un gestionnaire de connexions OLE DB.</span><span class="sxs-lookup"><span data-stu-id="7d4bd-107">Several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] tasks and data flow components use an OLE DB connection manager.</span></span> <span data-ttu-id="7d4bd-108">Ainsi, la source et la destination OLE DB utilisent ce gestionnaire de connexions pour extraire et charger des données, tandis que la tâche d’exécution SQL utilise ce gestionnaire pour se connecter à une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] afin d’exécuter des requêtes.</span><span class="sxs-lookup"><span data-stu-id="7d4bd-108">For example, the OLE DB source and OLE DB destination use this connection manager to extract and load data, and the Execute SQL task can use this connection manager to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database to run queries.</span></span>  
  
 <span data-ttu-id="7d4bd-109">Le gestionnaire de connexions OLE DB est également utilisé pour accéder à des sources de données OLE DB dans des tâches personnalisées écrites dans du code non géré utilisant un langage comme C++.</span><span class="sxs-lookup"><span data-stu-id="7d4bd-109">The OLE DB connection manager is also used to access OLE DB data sources in custom tasks written in unmanaged code that uses a language such as C++.</span></span>  
  
 <span data-ttu-id="7d4bd-110">Lorsque vous ajoutez un gestionnaire de connexions OLE DB à un package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crée un gestionnaire de connexions qui sera converti en connexion OLE DB au moment de l'exécution, définit les propriétés du gestionnaire de connexions et ajoute le gestionnaire de connexions à la collection `Connections` du package.</span><span class="sxs-lookup"><span data-stu-id="7d4bd-110">When you add an OLE DB connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an OLE DB connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="7d4bd-111">La propriété `ConnectionManagerType` du gestionnaire de connexions a pour valeur `OLEDB`.</span><span class="sxs-lookup"><span data-stu-id="7d4bd-111">The `ConnectionManagerType` property of the connection manager is set to `OLEDB`.</span></span>  
  
 <span data-ttu-id="7d4bd-112">Le gestionnaire de connexions OLE DB peut être configuré de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="7d4bd-112">The OLE DB connection manager can be configured in the following ways:</span></span>  
  
-   <span data-ttu-id="7d4bd-113">Indiquez une chaîne de connexion spécifique configurée pour répondre aux besoins du fournisseur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="7d4bd-113">Provide a specific connection string configured to meet the requirements of the selected provider.</span></span>  
  
-   <span data-ttu-id="7d4bd-114">Selon le fournisseur, incluez le nom de la source de données à laquelle se connecter.</span><span class="sxs-lookup"><span data-stu-id="7d4bd-114">Depending on the provider, include the name of the data source to connect to.</span></span>  
  
-   <span data-ttu-id="7d4bd-115">Fournissez les informations d'identification de sécurité nécessaires selon le fournisseur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="7d4bd-115">Provide security credentials as appropriate for the selected provider.</span></span>  
  
-   <span data-ttu-id="7d4bd-116">Indiquez si la connexion créée à partir du gestionnaire de connexions est conservée au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="7d4bd-116">Indicate whether the connection that is created from the connection manager is retained at run time.</span></span>  
  
## <a name="logging"></a><span data-ttu-id="7d4bd-117">Journalisation</span><span class="sxs-lookup"><span data-stu-id="7d4bd-117">Logging</span></span>  
 <span data-ttu-id="7d4bd-118">Vous pouvez consigner les appels que le gestionnaire de connexions OLE DB effectue vers des fournisseurs de données externes.</span><span class="sxs-lookup"><span data-stu-id="7d4bd-118">You can log the calls that the OLE DB connection manager makes to external data providers.</span></span> <span data-ttu-id="7d4bd-119">Cette fonctionnalité de journalisation permet de résoudre des problèmes liés aux connexions que le gestionnaire de connexions OLE DB établit avec des sources de données externes.</span><span class="sxs-lookup"><span data-stu-id="7d4bd-119">You can use this logging capability to troubleshoot the connections that the OLE DB connection manager makes to external data sources.</span></span> <span data-ttu-id="7d4bd-120">Pour consigner les appels que le gestionnaire de connexions OLE DB effectue auprès des fournisseurs de données externes, activez la journalisation des packages et sélectionnez l’événement **diagnostic** au niveau du package.</span><span class="sxs-lookup"><span data-stu-id="7d4bd-120">To log the calls that the OLE DB connection manager makes to external data providers, enable package logging and select the **Diagnostic** event at the package level.</span></span> <span data-ttu-id="7d4bd-121">Pour plus d’informations, consultez [Outils de dépannage pour l’exécution des packages](../troubleshooting/troubleshooting-tools-for-package-execution.md).</span><span class="sxs-lookup"><span data-stu-id="7d4bd-121">For more information, see [Troubleshooting Tools for Package Execution](../troubleshooting/troubleshooting-tools-for-package-execution.md).</span></span>  
  
## <a name="configuration-of-the-oledb-connection-manager"></a><span data-ttu-id="7d4bd-122">Configuration du gestionnaire de connexions OLEDB</span><span class="sxs-lookup"><span data-stu-id="7d4bd-122">Configuration of the OLEDB Connection Manager</span></span>  
 <span data-ttu-id="7d4bd-123">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="7d4bd-123">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span> <span data-ttu-id="7d4bd-124">Pour plus d’informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , consultez [Configurer le gestionnaire de connexions OLE DB](../configure-ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="7d4bd-124">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Configure OLE DB Connection Manager](../configure-ole-db-connection-manager.md).</span></span> <span data-ttu-id="7d4bd-125">Pour plus d’informations sur la configuration d’un gestionnaire de connexions par programmation, consultez la documentation de la classe **T:Microsoft.SqlServer.Dts.Runtime.ConnectionManager** dans le Guide du développeur.</span><span class="sxs-lookup"><span data-stu-id="7d4bd-125">For information about configuring a connection manager programmatically, see the documentation for **T:Microsoft.SqlServer.Dts.Runtime.ConnectionManager** class in the Developer Guide.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="7d4bd-126">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="7d4bd-126">Related Content</span></span>  
  
-   <span data-ttu-id="7d4bd-127">Article wiki, [SSIS avec connecteurs Oracle](https://go.microsoft.com/fwlink/?LinkId=220670) sur social.technet.Microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="7d4bd-127">Wiki article, [SSIS with Oracle Connectors](https://go.microsoft.com/fwlink/?LinkId=220670) on social.technet.microsoft.com.</span></span>  
  
-   <span data-ttu-id="7d4bd-128">Article technique, [Connection Strings for OLE DB Providers](https://go.microsoft.com/fwlink/?LinkId=220744)(Chaînes de connexion pour les fournisseurs OLE DB), sur carlprothman.net.</span><span class="sxs-lookup"><span data-stu-id="7d4bd-128">Technical article, [Connection Strings for OLE DB Providers](https://go.microsoft.com/fwlink/?LinkId=220744), on carlprothman.net.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d4bd-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7d4bd-129">See Also</span></span>  
 <span data-ttu-id="7d4bd-130">[Source OLE DB](../data-flow/ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="7d4bd-130">[OLE DB Source](../data-flow/ole-db-source.md) </span></span>  
 <span data-ttu-id="7d4bd-131">[Destination OLE DB](../data-flow/ole-db-destination.md) </span><span class="sxs-lookup"><span data-stu-id="7d4bd-131">[OLE DB Destination](../data-flow/ole-db-destination.md) </span></span>  
 <span data-ttu-id="7d4bd-132">[Tâche d’exécution SQL](../control-flow/execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="7d4bd-132">[Execute SQL Task](../control-flow/execute-sql-task.md) </span></span>  
 [<span data-ttu-id="7d4bd-133">Connexions Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="7d4bd-133">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
