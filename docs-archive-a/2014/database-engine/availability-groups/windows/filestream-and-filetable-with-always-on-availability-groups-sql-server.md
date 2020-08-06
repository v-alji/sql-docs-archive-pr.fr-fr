---
title: FILESTREAM et filetable avec groupes de disponibilité AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], Availability Groups
- FILESTREAM [SQL Server], Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: fdceda9a-a9db-4d1d-8745-345992164a98
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e7de7b4d66890bb5f1fe49799844f666de81f4db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604726"
---
# <a name="filestream-and-filetable-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="c77a4-102">FILESTREAM et FileTable avec groupes de disponibilité AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c77a4-102">FILESTREAM and FileTable with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="c77a4-103">Cette rubrique contient des informations sur l'utilisation des fonctionnalités FILESTREAM et FileTable avec [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c77a4-103">This topic contains information about the using the FILESTREAM and FileTable features with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="c77a4-104">L'intégralité des fonctionnalités FILESTREAM est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="c77a4-104">All FILESTREAM functionality is supported.</span></span> <span data-ttu-id="c77a4-105">Après un basculement, les données FILESTREAM sont accessibles à la fois sur les réplicas secondaires avec accès en lecture et sur le nouveau réplica principal.</span><span class="sxs-lookup"><span data-stu-id="c77a4-105">After a failover, FILESTREAM data is accessible on both readable secondary replicas and on the new primary.</span></span>  
  
 <span data-ttu-id="c77a4-106">La fonctionnalité FileTable n'est prise en charge que partiellement.</span><span class="sxs-lookup"><span data-stu-id="c77a4-106">FileTable functionality is partially supported.</span></span> <span data-ttu-id="c77a4-107">Après un basculement, les données FileTable sont accessibles sur le réplica principal, mais pas sur les réplicas secondaires avec accès en lecture.</span><span class="sxs-lookup"><span data-stu-id="c77a4-107">After a failover, FileTable data is accessible on the primary replica, but FileTable data is not accessible on readable secondary replicas.</span></span>  
  
 <span data-ttu-id="c77a4-108">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="c77a4-108">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="c77a4-109">Composants requis</span><span class="sxs-lookup"><span data-stu-id="c77a4-109">Prerequisites</span></span>](#Prerequisites)  
  
-   [<span data-ttu-id="c77a4-110">Utilisation de noms de réseau virtuel (VNN) pour l'accès à FILESTREAM et FileTable</span><span class="sxs-lookup"><span data-stu-id="c77a4-110">Using Virtual Network Names (VNNs) for FILESTREAM and FileTable Access</span></span>](#vnn)  
  
-   [<span data-ttu-id="c77a4-111">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="c77a4-111">Related Tasks</span></span>](#RelatedTasks)  
  
-   [<span data-ttu-id="c77a4-112">Contenu connexe</span><span class="sxs-lookup"><span data-stu-id="c77a4-112">Related Content</span></span>](#RelatedContent)  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="c77a4-113">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="c77a4-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="c77a4-114">Avant d'ajouter une base de données qui utilise FILESTREAM, avec ou sans FileTable, à un groupe de disponibilité, vérifiez que FILESTREAM est activé sur chaque instance de serveur qui héberge un réplica de disponibilité pour le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="c77a4-114">Before adding a database that uses FILESTREAM, with or without FileTable, to an availability group, ensure that FILESTREAM is enabled on every server instance that hosts an availability replica for the availability group.</span></span> <span data-ttu-id="c77a4-115">Pour plus d’informations, consultez [Enable and Configure FILESTREAM](../../../relational-databases/blob/enable-and-configure-filestream.md).</span><span class="sxs-lookup"><span data-stu-id="c77a4-115">For more information, see [Enable and Configure FILESTREAM](../../../relational-databases/blob/enable-and-configure-filestream.md).</span></span>  
  
##  <a name="using-virtual-network-names-vnns-for-filestream-and-filetable-access"></a><a name="vnn"></a><span data-ttu-id="c77a4-116">Utilisation de noms de réseau virtuel (VNN) pour l’accès FILESTREAM et filetable</span><span class="sxs-lookup"><span data-stu-id="c77a4-116">Using Virtual Network Names (VNNs) for FILESTREAM and FileTable Access</span></span>  
 <span data-ttu-id="c77a4-117">Lorsque vous activez FILESTREAM sur une instance du [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], un partage d'instance est créé pour permettre d'accéder aux données FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="c77a4-117">When you enable FILESTREAM on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], an instance-level share is created to provide access to the FILESTREAM data.</span></span> <span data-ttu-id="c77a4-118">Vous accédez à ce partage en utilisant le nom d'ordinateur au format suivant :</span><span class="sxs-lookup"><span data-stu-id="c77a4-118">You access this share by using the computer name in the following format:</span></span>  
  
 `\\<computer_name>\<filestream_share_name>`  
  
 <span data-ttu-id="c77a4-119">Toutefois, dans un groupe de disponibilité AlwaysOn, le nom de l'ordinateur est virtualisé à l'aide d'un nom de réseau virtuel, ou VNN.</span><span class="sxs-lookup"><span data-stu-id="c77a4-119">In an AlwaysOn availability group, however, the name of the computer is virtualized by using a Virtual Network Name, or VNN.</span></span> <span data-ttu-id="c77a4-120">Lorsque l'ordinateur est le réplica primaire dans un groupe de disponibilité, et les bases de données du groupe de disponibilité contiennent des données FILESTREAM, un partage d'étendue VNN est également créé pour permettre d'accéder aux données FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="c77a4-120">When the computer is the primary replica in an availability group, and databases in the availability group contain FILESTREAM data, then a VNN-scoped share is also created to provide access to the FILESTREAM data.</span></span> <span data-ttu-id="c77a4-121">Cela n'affecte pas l'accès Transact-SQL aux données FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="c77a4-121">This does not affect Transact-SQL access to FILESTREAM data.</span></span> <span data-ttu-id="c77a4-122">Toutefois, les applications qui utilisent les API du système de fichiers doivent utiliser le partage d'étendue VNN, dont le chemin d'accès a le format suivant :</span><span class="sxs-lookup"><span data-stu-id="c77a4-122">However applications that use file system APIs have to use the VNN-scoped share, which has a path in the following format:</span></span>  
  
 `\\<VNN>\<filestream_share_name>`  
  
 <span data-ttu-id="c77a4-123">Ce partage d'étendue VNN est créé lorsque l'un des événements suivants se produit.</span><span class="sxs-lookup"><span data-stu-id="c77a4-123">This VNN-scoped share is created when one of the following events occurs.</span></span>  
  
-   <span data-ttu-id="c77a4-124">Vous ajoutez une base de données qui contient des données FILESTREAM à un groupe de disponibilité AlwaysOn sur le réplica primaire.</span><span class="sxs-lookup"><span data-stu-id="c77a4-124">You add a database that contains FILESTREAM data to an AlwaysOn availability group on the primary replica.</span></span> <span data-ttu-id="c77a4-125">Dans ce cas, le partage `\\<computer_name>\<filestream_share_name>` existe déjà.</span><span class="sxs-lookup"><span data-stu-id="c77a4-125">In this case, the share `\\<computer_name>\<filestream_share_name>` already exists.</span></span> <span data-ttu-id="c77a4-126">Le partage `\\<VNN>\<filestream_share_name>` est créé.</span><span class="sxs-lookup"><span data-stu-id="c77a4-126">The share `\\<VNN>\<filestream_share_name>` is created.</span></span>  
  
-   <span data-ttu-id="c77a4-127">Vous activez FILESTREAM pour l'accès en continu des E/S de fichier sur un réplica primaire qui possède des groupes de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="c77a4-127">You enable FILESTREAM for file i/o streaming access on a primary replica that has availability groups.</span></span> <span data-ttu-id="c77a4-128">Les partages suivants sont créés :</span><span class="sxs-lookup"><span data-stu-id="c77a4-128">The following shares are created:</span></span>  
  
    1.  `\\<computer_name>\<filestream_share_name>`  
  
    2.  <span data-ttu-id="c77a4-129">`\\<VNN1>\<filestream_share_name>` pour le groupe de disponibilité 1.</span><span class="sxs-lookup"><span data-stu-id="c77a4-129">`\\<VNN1>\<filestream_share_name>` for availability group 1.</span></span>  
  
    3.  <span data-ttu-id="c77a4-130">`\\<VNN2>\<filestream_share_name>` pour le groupe de disponibilité 2.</span><span class="sxs-lookup"><span data-stu-id="c77a4-130">`\\<VNN2>\<filestream_share_name>` for availability group 2.</span></span>  
  
 <span data-ttu-id="c77a4-131">Ces partages d'étendue VNN sont également propagées à tous les réplicas secondaires.</span><span class="sxs-lookup"><span data-stu-id="c77a4-131">These VNN-scoped shares are also propagated to all secondary replicas.</span></span>  
  
 <span data-ttu-id="c77a4-132">Lorsque la base de données qui contient des données FILESTREAM ou FileTable appartient à un groupe de disponibilité AlwaysOn :</span><span class="sxs-lookup"><span data-stu-id="c77a4-132">When the database that contains FILESTREAM or FileTable data belongs to an AlwaysOn availability group:</span></span>  
  
-   <span data-ttu-id="c77a4-133">Les fonctions FILESTREAM et FileTable acceptent ou retournent des noms de réseau virtuel (VNN) à la place de noms d'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c77a4-133">The FILESTREAM and FileTable functions accept or return virtual network names (VNNs) instead of computer names.</span></span> <span data-ttu-id="c77a4-134">Pour plus d’informations sur ces fonctions, consultez [Fonctions FileStream et FileTable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filestream-and-filetable-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c77a4-134">For more information about these functions, see [Filestream and FileTable Functions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filestream-and-filetable-functions-transact-sql).</span></span>  
  
-   <span data-ttu-id="c77a4-135">Tous les accès à FILESTREAM ou aux données FileTable via les API du système de fichiers doivent utiliser des VNN à la place des noms d'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c77a4-135">All access to FILESTREAM or FileTable data through the file system APIs should use VNNs instead of computer names.</span></span>  
  
 <span data-ttu-id="c77a4-136">Si votre application tente d'accéder au partage en utilisant le nom d'ordinateur au format `\\<computer_name>\<filestream_share_name>` lorsque la base de données fait partie d'un groupe de disponibilité, une erreur est générée.</span><span class="sxs-lookup"><span data-stu-id="c77a4-136">If your application tries to access the share by using the computer name in the format `\\<computer_name>\<filestream_share_name>` when the database is part of an availability group, then an error is raised.</span></span>  
  
 <span data-ttu-id="c77a4-137">Si votre application tente d'accéder au partage à l'aide d'un chemin d'accès d'étendue VNN lorsque la base de données ne fait pas partie d'un groupe de disponibilité, la demande peut réussir.</span><span class="sxs-lookup"><span data-stu-id="c77a4-137">If your application tries to access the share by using a VNN-scoped path when the database is not part of an availability group, then the request may succeed.</span></span> <span data-ttu-id="c77a4-138">Dans ce cas, le nom du réseau virtuel est résolu avec le nom de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c77a4-138">In this case, the virtual network name is resolved to the computer name.</span></span> <span data-ttu-id="c77a4-139">Toutefois, cette utilisation est fortement déconseillée, étant donné que le chemin d'accès d'étendue VNN cesse de fonctionner si le groupe de disponibilité est supprimé.</span><span class="sxs-lookup"><span data-stu-id="c77a4-139">However this usage is strongly discouraged, since the VNN-scoped path will stop working if the availability group is dropped.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="c77a4-140">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="c77a4-140">Related Tasks</span></span>  
  
-   [<span data-ttu-id="c77a4-141">Activer et configurer FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="c77a4-141">Enable and Configure FILESTREAM</span></span>](../../../relational-databases/blob/enable-and-configure-filestream.md)  
  
-   [<span data-ttu-id="c77a4-142">Activer les conditions préalables pour les FileTables</span><span class="sxs-lookup"><span data-stu-id="c77a4-142">Enable the Prerequisites for FileTable</span></span>](../../../relational-databases/blob/enable-the-prerequisites-for-filetable.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="c77a4-143">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="c77a4-143">Related Content</span></span>  
 <span data-ttu-id="c77a4-144">Aucun.</span><span class="sxs-lookup"><span data-stu-id="c77a4-144">None.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c77a4-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c77a4-145">See Also</span></span>  
 [<span data-ttu-id="c77a4-146">Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c77a4-146">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
