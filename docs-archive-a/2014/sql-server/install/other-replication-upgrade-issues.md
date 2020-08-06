---
title: Autres problèmes de mise à niveau de la réplication | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- system tables [SQL Server], replication
- passwords [SQL Server replication]
- versions [SQL Server replication]
- connections [SQL Server replication]
- scripts [SQL Server replication]
- ActiveX controls [SQL Server replication]
ms.assetid: 8a5e74be-4992-4f17-b20c-c3dce8f49329
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e8ce3f35ead9d3322c636462f682ef391703cfe2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613277"
---
# <a name="other-replication-upgrade-issues"></a><span data-ttu-id="4b929-102">Autres problèmes de mise à niveau de la réplication</span><span class="sxs-lookup"><span data-stu-id="4b929-102">Other Replication Upgrade Issues</span></span>
  <span data-ttu-id="4b929-103">Cette rubrique traite de plusieurs problèmes de mise à niveau qui ne sont pas signalés par le Conseiller de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="4b929-103">This topic covers a number of upgrade issues that are not reported by Upgrade Advisor.</span></span>  
  
## <a name="versions-supported"></a><span data-ttu-id="4b929-104">Versions prises en charge</span><span class="sxs-lookup"><span data-stu-id="4b929-104">Versions Supported</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="4b929-105">prend en charge la mise à niveau des bases de données répliquées à partir des versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b929-105">supports upgrading replicated databases from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4b929-106">Il n'est pas nécessaire d'arrêter l'activité sur les autres nœuds pendant qu'un nœud est mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="4b929-106">You do not have to stop activity at other nodes while a node is being upgraded.</span></span> <span data-ttu-id="4b929-107">Prenez soin de respecter les règles relatives aux versions qui sont prises en charge dans une topologie.</span><span class="sxs-lookup"><span data-stu-id="4b929-107">Ensure that you adhere to the rules regarding which versions are supported in a topology.</span></span>  
  
 <span data-ttu-id="4b929-108">Lorsque vous effectuez une réplication entre ou entre différentes versions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vous êtes généralement limité aux fonctionnalités de la version la plus ancienne qui est utilisée.</span><span class="sxs-lookup"><span data-stu-id="4b929-108">When you replicate between or among different versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you are usually limited to the functionality of the earliest version that is being used.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4b929-109">Le format de stockage sur disque de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] étant le même dans les environnements 64 bits et 32 bits, une topologie de réplication peut combiner des instances de serveur qui s'exécutent dans un environnement 32 bits et des instances de serveur qui s'exécutent dans un environnement 64 bits.</span><span class="sxs-lookup"><span data-stu-id="4b929-109">Because the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on-disk storage format is the same in the 64-bit and 32-bit environments, a replication topology can combine server instances that run in a 32-bit environment and server instances that run in a 64-bit environment.</span></span>  
  
 <span data-ttu-id="4b929-110">Pour tous les types de réplication, la version du serveur de distribution ne doit pas être antérieure à la version du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="4b929-110">For all types of replication, the Distributor version must be no earlier than the Publisher version.</span></span> <span data-ttu-id="4b929-111">(Dans la plupart des cas, les deux versions sont identiques.)</span><span class="sxs-lookup"><span data-stu-id="4b929-111">(Frequently, the Distributor is the same instance as the Publisher.)</span></span>  
  
 <span data-ttu-id="4b929-112">Pour la réplication transactionnelle, la version d'un Abonné à une publication transactionnelle peut être n'importe laquelle des deux versions du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="4b929-112">For transactional replication, a Subscriber to a transactional publication can be any version within two versions of the Publisher version.</span></span>  
  
 <span data-ttu-id="4b929-113">Pour la réplication de fusion, un Abonné à une publication de fusion peut être n'importe quelle version antérieure à la version du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="4b929-113">For merge replication, a Subscriber to a merge publication can be any version no later than the Publisher version.</span></span>  
  
## <a name="merge-replication-batches-changes"></a><span data-ttu-id="4b929-114">Modifications des lots de réplication de fusion</span><span class="sxs-lookup"><span data-stu-id="4b929-114">Merge Replication Batches Changes</span></span>  
 <span data-ttu-id="4b929-115">Les modifications apportées par l'Agent de fusion sont regroupées de manière à améliorer les performances ; par conséquent, une même instruction permet d'insérer, de mettre à jour ou de supprimer plusieurs lignes.</span><span class="sxs-lookup"><span data-stu-id="4b929-115">Changes that are made by the Merge Agent are batched to improve performance; therefore, more than one row can be inserted, updated, or deleted within a single statement.</span></span> <span data-ttu-id="4b929-116">Si, dans les bases de données de publication ou d'abonnement, des tables publiées possèdent des déclencheurs, vérifiez que ceux-ci peuvent gérer les insertions, les mises à jour et les suppressions portant sur plusieurs lignes.</span><span class="sxs-lookup"><span data-stu-id="4b929-116">If any published tables in the publication or subscription databases have triggers, ensure that the triggers can handle multirow inserts, updates, and deletes.</span></span> <span data-ttu-id="4b929-117">Pour plus d'informations, consultez « Observations au sujet des lignes multiples pour les déclencheurs DML » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b929-117">For more information, see "Multirow Considerations for DML Triggers" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="activex-control-changes"></a><span data-ttu-id="4b929-118">Modifications des contrôles ActiveX</span><span class="sxs-lookup"><span data-stu-id="4b929-118">ActiveX Control Changes</span></span>  
 <span data-ttu-id="4b929-119">Les modifications suivantes ont été apportées aux contrôles ActiveX de réplication :</span><span class="sxs-lookup"><span data-stu-id="4b929-119">The following changes have been made for replication ActiveX controls:</span></span>  
  
-   <span data-ttu-id="4b929-120">Tous les contrôles ActiveX sont marqués comme non sûrs pour l'écriture de scripts et l'initialisation.</span><span class="sxs-lookup"><span data-stu-id="4b929-120">All ActiveX controls are marked as unsafe for scripting and initialization.</span></span>  
  
-   <span data-ttu-id="4b929-121">Le contrôle ActiveX d'instantané a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="4b929-121">The Snapshot ActiveX control has been dropped.</span></span> <span data-ttu-id="4b929-122">Vous pouvez créer et gérer des instantanés à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou par programmation en utilisant des procédures stockées de réplication.</span><span class="sxs-lookup"><span data-stu-id="4b929-122">You can create and manage snapshots by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or programmatically by using replication stored procedures.</span></span> <span data-ttu-id="4b929-123">Pour plus d'informations, consultez les rubriques « Procédure : créer et appliquer l'instantané initial ([!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]) » et « Procédure : créer l'instantané initial (programmation Transact-SQL de programmation) » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b929-123">For more information, see the topics "How to: Create and Apply the Initial Snapshot ([!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)])" and "How to: Create the Initial Snapshot (Replication Transact-SQL Programming)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
-   <span data-ttu-id="4b929-124">Le contrôle ActiveX de distribution et le contrôle ActiveX de fusion ont été déconseillés.</span><span class="sxs-lookup"><span data-stu-id="4b929-124">The Distribution ActiveX control and Merge ActiveX control have been deprecated.</span></span> <span data-ttu-id="4b929-125">Une fonctionnalité semblable est fournie pour les applications de code managé à l'aide de Replication Management Objects.</span><span class="sxs-lookup"><span data-stu-id="4b929-125">Similar functionality is provided for managed code applications using Replication Management Objects (RMO).</span></span> <span data-ttu-id="4b929-126">Pour plus d'informations, consultez « Synchronisation des abonnements (Programmation RMO) » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b929-126">For more information, see "Synchronizing Subscriptions (RMO Programming)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b929-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4b929-127">See Also</span></span>  
 [<span data-ttu-id="4b929-128">Problèmes de mise à niveau de la réplication</span><span class="sxs-lookup"><span data-stu-id="4b929-128">Replication Upgrade Issues</span></span>](../../../2014/sql-server/install/replication-upgrade-issues.md)  
  
  
