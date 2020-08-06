---
title: Serveur Integration Services (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], managing
- managing packages [Integration Services]
ms.assetid: 6d667bba-7c25-492a-8f4d-70ebaca28f40
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a0da83cdac269499dfbde7a6387a4af4690c83ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611239"
---
# <a name="integration-services-ssis-server"></a><span data-ttu-id="238de-102">Serveur Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="238de-102">Integration Services (SSIS) Server</span></span>
  <span data-ttu-id="238de-103">Après avoir conçu et testé des packages dans [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], vous pouvez déployer les projets qui contiennent les packages sur le serveur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="238de-103">After you design and test packages in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], you can deploy the projects that contain the packages to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="238de-104">Le serveur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] est une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] qui héberge la base de données `SSISDB`.</span><span class="sxs-lookup"><span data-stu-id="238de-104">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server is an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the `SSISDB` database.</span></span> <span data-ttu-id="238de-105">La base de données stocke les objets suivants : packages, projets, paramètres, autorisations, propriétés du serveur et historique opérationnel.</span><span class="sxs-lookup"><span data-stu-id="238de-105">The database stores the following objects: packages, projects, parameters, permissions, server properties, and operational history.</span></span>  
  
 <span data-ttu-id="238de-106">La base de données `SSISDB` expose les informations d'objet dans des vues publiques que vous pouvez interroger.</span><span class="sxs-lookup"><span data-stu-id="238de-106">The `SSISDB` database exposes the object information in public views that you can query.</span></span> <span data-ttu-id="238de-107">La base de données fournit également des procédures stockées que vous pouvez appeler pour gérer les objets.</span><span class="sxs-lookup"><span data-stu-id="238de-107">The database also provides stored procedures that you can call to manage the objects.</span></span>  
  
 <span data-ttu-id="238de-108">Avant de pouvoir déployer des projets sur le serveur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], vous devez créer le catalogue `SSISDB`.</span><span class="sxs-lookup"><span data-stu-id="238de-108">Before you can deploy the projects to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server, you need to create the `SSISDB` catalog.</span></span>  
  
 <span data-ttu-id="238de-109">Vous trouverez une vue d’ensemble des fonctionnalités du catalogue SSISDB sur la page [Catalogue SSIS](ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="238de-109">For an overview of the SSISDB catalog functionality, see [SSIS Catalog](ssis-catalog.md).</span></span>  
  
## <a name="high-availability"></a><span data-ttu-id="238de-110">Haute disponibilité</span><span class="sxs-lookup"><span data-stu-id="238de-110">High Availability</span></span>  
 <span data-ttu-id="238de-111">Tout comme les autres bases de données utilisateur, la base de données `SSISDB` ne prend pas en charge la mise en miroir et la réplication de bases de données.</span><span class="sxs-lookup"><span data-stu-id="238de-111">Like other user databases, the `SSISDB` database does support database mirroring and replication.</span></span> <span data-ttu-id="238de-112">Pour plus d’informations sur la mise en miroir et la réplication, consultez la page [Mise en miroir de bases de données &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="238de-112">For more information about mirroring and replication, see [Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md).</span></span>  
  
 <span data-ttu-id="238de-113">Vous pouvez également fournir une haute disponibilité de SSISDB et de son contenu en utilisant SSIS et les groupes de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="238de-113">You can also provide high-availability of SSISDB and its contents by making use of SSIS and AlwaysOn Availability Groups.</span></span> <span data-ttu-id="238de-114">Pour plus d'informations, consultez cette entrée de blog de Matt Masson, [SSIS with AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873)(en anglais), sur le site Web blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="238de-114">For more information, see this blog post by Matt Masson, [SSIS with AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873), at blogs.msdn.com.</span></span>  
  
##  <a name="integration-services-server-in-sql-server-management-studio"></a><a name="ssms"></a><span data-ttu-id="238de-115">Integration Services Server dans SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="238de-115">Integration Services Server in SQL Server Management Studio</span></span>  
 <span data-ttu-id="238de-116">Lorsque vous vous connectez à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] qui héberge la base de données `SSISDB`, vous affichez les objets suivants dans l'Explorateur d'objets :</span><span class="sxs-lookup"><span data-stu-id="238de-116">When you connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the `SSISDB` database, you see the following objects in Object Explorer:</span></span>  
  
-   <span data-ttu-id="238de-117">**Base de données SSISDB**</span><span class="sxs-lookup"><span data-stu-id="238de-117">**SSISDB Database**</span></span>  
  
     <span data-ttu-id="238de-118">La `SSISDB` base de données apparaît sous le nœud **bases de données** dans l’Explorateur d’objets.</span><span class="sxs-lookup"><span data-stu-id="238de-118">The `SSISDB` database appears under the **Databases** node in Object Explore.</span></span> <span data-ttu-id="238de-119">Vous pouvez interroger les vues et appeler les procédures stockées qui gèrent le serveur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] et les objets stockés sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="238de-119">You can query the views and call the stored procedures that manage the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server and the objects that are stored on the server.</span></span>  
  
-   <span data-ttu-id="238de-120">**Catalogues Integration Services**</span><span class="sxs-lookup"><span data-stu-id="238de-120">**Integration Services Catalogs**</span></span>  
  
     <span data-ttu-id="238de-121">Sous le nœud **Catalogues Integration Services** se trouvent des dossiers pour des environnements et des projets [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="238de-121">Under the **Integration Services Catalogs** node there are folders for [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] projects and environments.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="238de-122">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="238de-122">Related Tasks</span></span>  
  
-   [<span data-ttu-id="238de-123">Créer le catalogue SSIS</span><span class="sxs-lookup"><span data-stu-id="238de-123">Create the SSIS Catalog</span></span>](../create-the-ssis-catalog.md)  
  
-   [<span data-ttu-id="238de-124">Afficher la liste des packages sur le serveur Integration Services</span><span class="sxs-lookup"><span data-stu-id="238de-124">View the List of Packages on the Integration Services Server</span></span>](view-the-list-of-packages-on-the-integration-services-server.md)  
  
-   [<span data-ttu-id="238de-125">Déployer des projets sur le serveur Integration Services</span><span class="sxs-lookup"><span data-stu-id="238de-125">Deploy Projects to Integration Services Server</span></span>](../deploy-projects-to-integration-services-server.md)  
  
-   [<span data-ttu-id="238de-126">Exécuter un package sur le serveur SSIS à l’aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="238de-126">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>](../run-a-package-on-the-ssis-server-using-sql-server-management-studio.md)  
  
## <a name="related-content"></a><span data-ttu-id="238de-127">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="238de-127">Related Content</span></span>  
 <span data-ttu-id="238de-128">Entrée de blog, [SSIS with AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873)(en anglais), sur le site Web blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="238de-128">Blog entry, [SSIS with AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873), at blogs.msdn.com.</span></span>  
  
  
