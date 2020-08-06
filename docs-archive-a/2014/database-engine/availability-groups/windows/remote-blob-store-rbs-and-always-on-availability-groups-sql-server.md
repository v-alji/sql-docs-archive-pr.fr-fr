---
title: Magasin d’objets BLOB distants (RBS) et groupes de disponibilité AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 01a70258-d4fd-40bc-bc44-c490b5d6c420
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f12a11162d286731b2b510a9051183e6c3025b2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603057"
---
# <a name="remote-blob-store-rbs-and-alwayson-availability-groups-sql-server"></a><span data-ttu-id="842a1-102">Magasin d'objets blob distants et groupes de disponibilité AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="842a1-102">Remote Blob Store (RBS) and AlwaysOn Availability Groups (SQL Server)</span></span>
  [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]<span data-ttu-id="842a1-103">peut fournir une solution de haute disponibilité et de récupération d’urgence pour les [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] objets BLOB du magasin d’objets [BLOB distants (RBS](../../../relational-databases/blob/remote-blob-store-rbs-sql-server.md) ).</span><span class="sxs-lookup"><span data-stu-id="842a1-103">can provide a high-availability and disaster recovery solution for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)][Remote Blob Store (RBS)](../../../relational-databases/blob/remote-blob-store-rbs-sql-server.md) BLOB objects (blobs).</span></span> [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] <span data-ttu-id="842a1-104">protège les métadonnées et schémas du magasin d’objets blob distants stockés dans une base de données de disponibilité en les répliquant sur des réplicas secondaires.</span><span class="sxs-lookup"><span data-stu-id="842a1-104">protects any RBS metadata and schemas stored in an availability database by replicating them to the secondary replicas.</span></span> <span data-ttu-id="842a1-105">Il s'agit de la base de données de contenu SharePoint.</span><span class="sxs-lookup"><span data-stu-id="842a1-105">This is the SharePoint Content Database.</span></span> <span data-ttu-id="842a1-106">De manière générale, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] stocke ces métadonnées RBS indépendamment de l'objet blob.</span><span class="sxs-lookup"><span data-stu-id="842a1-106">Generally speaking, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] stores this RBS metadata independently from the blob.</span></span>  
  
 <span data-ttu-id="842a1-107">La protection des données BLOB de RBD dépend de l'emplacement du magasin d'objets BLOB, comme suit :</span><span class="sxs-lookup"><span data-stu-id="842a1-107">The protection for RBD BLOB data depends on the BLOB Store Location, as follows:</span></span>  
  
|<span data-ttu-id="842a1-108">Emplacement du magasin d'objets BLOB</span><span class="sxs-lookup"><span data-stu-id="842a1-108">BLOB Store Location</span></span>|<span data-ttu-id="842a1-109">Les groupes de disponibilité peuvent-ils protéger ces données BLOB ?</span><span class="sxs-lookup"><span data-stu-id="842a1-109">Can Availability Groups Protect This BLOB Data?</span></span>|  
|-------------------------|-----------------------------------------------------|  
|<span data-ttu-id="842a1-110">La même base de données qui contient les métadonnées du magasin d'objets blob distants (stockées à l'aide d'un fournisseur FILESTREAM distant de RBS)</span><span class="sxs-lookup"><span data-stu-id="842a1-110">The same database that contains the RBS metadata  (stored using a RBS remote FILESTREAM provider)</span></span>|<span data-ttu-id="842a1-111">Oui</span><span class="sxs-lookup"><span data-stu-id="842a1-111">Yes</span></span>|  
|<span data-ttu-id="842a1-112">Une autre base de données dans la même instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (enregistrée à l'aide d'un fournisseur FILESTREAM distant de RBS)</span><span class="sxs-lookup"><span data-stu-id="842a1-112">Another database in the same instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (stored using a RBS remote FILESTREAM provider)</span></span>|<span data-ttu-id="842a1-113">Oui</span><span class="sxs-lookup"><span data-stu-id="842a1-113">Yes</span></span><br /><br /> <span data-ttu-id="842a1-114">Nous vous recommandons de placer cette base de données dans le même groupe de disponibilité que la base de données qui contient les métadonnées du magasin d'objets blob distants.</span><span class="sxs-lookup"><span data-stu-id="842a1-114">We recommend that you put this database in the same availability group as the database that contains the RBS metadata.</span></span>|  
|<span data-ttu-id="842a1-115">Une autre base de données dans une autre instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (enregistrée à l'aide d'un fournisseur FILESTREAM distant de RBS)</span><span class="sxs-lookup"><span data-stu-id="842a1-115">Another database in a different instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (stored using a RBS remote FILESTREAM provider)</span></span>|<span data-ttu-id="842a1-116">Oui</span><span class="sxs-lookup"><span data-stu-id="842a1-116">Yes</span></span><br /><br /> <span data-ttu-id="842a1-117">Cette base de données doit être dans un groupe de disponibilité distinct.</span><span class="sxs-lookup"><span data-stu-id="842a1-117">This database must be in a separate availability group.</span></span>|  
|<span data-ttu-id="842a1-118">Un magasin d'objets BLOB tiers</span><span class="sxs-lookup"><span data-stu-id="842a1-118">A third-party BLOB store</span></span>|<span data-ttu-id="842a1-119">Non</span><span class="sxs-lookup"><span data-stu-id="842a1-119">No</span></span><br /><br /> <span data-ttu-id="842a1-120">Pour protéger ces données BLOB, utilisez les mécanismes de haute disponibilité du fournisseur de magasin d'objets blob.</span><span class="sxs-lookup"><span data-stu-id="842a1-120">To protect this BLOB data, use the high-availability mechanisms of the BLOB store provider.</span></span>|  
  
##  <a name="limitations"></a><a name="Limitations"></a> <span data-ttu-id="842a1-121">Limitations</span><span class="sxs-lookup"><span data-stu-id="842a1-121">Limitations</span></span>  
  
-   <span data-ttu-id="842a1-122">Les chargés de maintenance RBS doivent être ciblés sur le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="842a1-122">RBS maintainers need to be targeted on the primary replica.</span></span>  
  
##  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="842a1-123">Recommandations</span><span class="sxs-lookup"><span data-stu-id="842a1-123">Recommendations</span></span>  
  
-   <span data-ttu-id="842a1-124">Utilisez un écouteur de groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="842a1-124">Use an availability group listener.</span></span> <span data-ttu-id="842a1-125">Pour plus d’informations, consultez [Écouteurs de groupe de disponibilité, connectivité client et basculement d’application &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span><span class="sxs-lookup"><span data-stu-id="842a1-125">For more information, see [Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span></span>  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="842a1-126">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="842a1-126">Related Content</span></span>  
  
-   <span data-ttu-id="842a1-127">[Maintenance du magasin d’objets BLOB distants](https://msdn.microsoft.com/library/gg316773\(SQL.105\).aspx) (dans la documentation en ligne de [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="842a1-127">[Maintaining Remote BLOB Store](https://msdn.microsoft.com/library/gg316773\(SQL.105\).aspx) (in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] Books Online)</span></span>  
  
-   <span data-ttu-id="842a1-128">[Running RBS Maintainer (Exécution du chargé de maintenance RBS)](https://blogs.msdn.com/b/sqlrbs/archive/2010/03/19/running-rbs-maintainer.aspx) (blog)</span><span class="sxs-lookup"><span data-stu-id="842a1-128">[Running RBS Maintainer](https://blogs.msdn.com/b/sqlrbs/archive/2010/03/19/running-rbs-maintainer.aspx) (blog)</span></span>  
  
-   <span data-ttu-id="842a1-129">[Configure Remote BLOB Storage (RBS) with the FILESTREAM provider (SharePoint 2010) (Configurer le stockage d’objets blob distants avec le fournisseur FILESTREAM)](https://blogs.msdn.com/b/mvpawardprogram/archive/2012/04/02/configure-remote-blob-storage-rbs-with-the-filestream-provider-sharepoint-2010.aspx) (blog)</span><span class="sxs-lookup"><span data-stu-id="842a1-129">[Configure Remote BLOB Storage (RBS) with the FILESTREAM provider (SharePoint 2010)](https://blogs.msdn.com/b/mvpawardprogram/archive/2012/04/02/configure-remote-blob-storage-rbs-with-the-filestream-provider-sharepoint-2010.aspx) (blog)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="842a1-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="842a1-130">See Also</span></span>  
 <span data-ttu-id="842a1-131">[Connectivité client AlwaysOn &#40;SQL Server&#41;](always-on-client-connectivity-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="842a1-131">[AlwaysOn Client Connectivity &#40;SQL Server&#41;](always-on-client-connectivity-sql-server.md) </span></span>  
 [<span data-ttu-id="842a1-132">Magasin d’objets blob distants &#40;RBS&#41; &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="842a1-132">Remote Blob Store &#40;RBS&#41; &#40;SQL Server&#41;</span></span>](../../../relational-databases/blob/remote-blob-store-rbs-sql-server.md)  
  
  
