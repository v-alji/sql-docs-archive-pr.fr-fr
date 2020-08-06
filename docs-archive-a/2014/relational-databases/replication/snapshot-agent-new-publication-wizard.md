---
title: Agent d’instantané (Assistant Nouvelle publication) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.configuresnapshotagent.f1
ms.assetid: 0257d4ee-1f7b-49fd-b4ef-65bfc1ef6951
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c45fa3444fb2f81436a40a2bfb80519aea105c47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614498"
---
# <a name="snapshot-agent-new-publication-wizard"></a><span data-ttu-id="d828a-102">Agent d'instantané (Assistant Nouvelle publication)</span><span class="sxs-lookup"><span data-stu-id="d828a-102">Snapshot Agent (New Publication Wizard)</span></span>
  <span data-ttu-id="d828a-103">L'Agent d'instantané crée des fichiers qui contiennent le schéma de publication et les données utilisées pour initialiser de nouveaux abonnements.</span><span class="sxs-lookup"><span data-stu-id="d828a-103">The Snapshot Agent creates files containing the publication schema and data that are used to initialize new subscriptions.</span></span> <span data-ttu-id="d828a-104">Par défaut, il s'exécute immédiatement après la création de la publication dans l'Assistant Nouvelle publication.</span><span class="sxs-lookup"><span data-stu-id="d828a-104">By default, the Snapshot Agent runs immediately after the publication is created in the New Publication Wizard.</span></span> <span data-ttu-id="d828a-105">Par la suite, il s'exécute selon une planification spécifiée.</span><span class="sxs-lookup"><span data-stu-id="d828a-105">Subsequently, the agent runs according to a schedule you specify.</span></span> <span data-ttu-id="d828a-106">La création de nouveaux fichiers d'instantané par l'agent à chaque exécution dépend du type de réplication et des options choisies.</span><span class="sxs-lookup"><span data-stu-id="d828a-106">Whether the agent creates new snapshot files each time it runs depends on the type of replication and options chosen.</span></span> <span data-ttu-id="d828a-107">Pour plus d’informations, consultez [Créer et appliquer un instantané](create-and-apply-the-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="d828a-107">For more information, see [Create and Apply the Snapshot](create-and-apply-the-snapshot.md).</span></span>  
  
 <span data-ttu-id="d828a-108">Pour les publications de fusion utilisant les filtres paramétrés, vous devez créer un instantané pour chaque partition de données après la fin de l'instantané pour la publication.</span><span class="sxs-lookup"><span data-stu-id="d828a-108">For merge publications that use parameterized filters, you must create a snapshot for each partition of data after the publication snapshot has completed.</span></span> <span data-ttu-id="d828a-109">Pour plus d'informations, voir [Snapshots for Merge Publications with Parameterized Filters](snapshots-for-merge-publications-with-parameterized-filters.md).</span><span class="sxs-lookup"><span data-stu-id="d828a-109">For more information, see [Snapshots for Merge Publications with Parameterized Filters](snapshots-for-merge-publications-with-parameterized-filters.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d828a-110">Options</span><span class="sxs-lookup"><span data-stu-id="d828a-110">Options</span></span>  
 <span data-ttu-id="d828a-111">**Créer un instantané immédiatement** (réplication de fusion) ou **Créer un instantané immédiatement et garder cette dernière disponible pour l'initialisation des abonnements** (réplication transactionnelle)</span><span class="sxs-lookup"><span data-stu-id="d828a-111">**Create a snapshot immediately** (merge replication) or **Create a snapshot immediately and keep the snapshot available to initialize subscriptions** (transactional replication)</span></span>  
 <span data-ttu-id="d828a-112">Activez cette case à cocher pour créer un instantané immédiatement après la fin de l'Assistant Nouvelle publication.</span><span class="sxs-lookup"><span data-stu-id="d828a-112">Select this check box to create a snapshot immediately after the New Publication Wizard is completed.</span></span> <span data-ttu-id="d828a-113">Désactivez cette case à cocher si vous comptez modifier les propriétés d'instantané dans la boîte de dialogue **Propriétés de la publication** avant la génération d'un instantané ou si vous lancez l'abonné sans instantané.</span><span class="sxs-lookup"><span data-stu-id="d828a-113">Clear this check box if you plan to change snapshot properties in the **Publication Properties** dialog box before generating a snapshot, or if you will initialize the Subscriber without a snapshot.</span></span> <span data-ttu-id="d828a-114">Pour plus d’informations, consultez [Initialiser un abonnement transactionnel sans instantané](initialize-a-transactional-subscription-without-a-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="d828a-114">For more information, see [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d828a-115">Il se peut que l'Assistant demande une connexion au serveur de distribution pour pouvoir démarrer le travail approprié pour l'Agent de distribution ou l'Agent de fusion.</span><span class="sxs-lookup"><span data-stu-id="d828a-115">The wizard might prompt for a connection to the Distributor in order to start the appropriate job for the Distribution Agent or Merge Agent.</span></span>  
  
 <span data-ttu-id="d828a-116">**Planifier l'exécution de l'Agent d'instantané aux heures suivantes**</span><span class="sxs-lookup"><span data-stu-id="d828a-116">**Schedule the Snapshot Agent to run at the following times**</span></span>  
 <span data-ttu-id="d828a-117">Acceptez la planification par défaut pour l'exécution de l'Agent d'instantané ou cliquez sur **Modifier** pour en spécifier une.</span><span class="sxs-lookup"><span data-stu-id="d828a-117">Accept the default schedule for running the Snapshot Agent, or click **Change** to specify a schedule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d828a-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d828a-118">See Also</span></span>  
 <span data-ttu-id="d828a-119">[Create a Publication](publish/create-a-publication.md) </span><span class="sxs-lookup"><span data-stu-id="d828a-119">[Create a Publication](publish/create-a-publication.md) </span></span>  
 <span data-ttu-id="d828a-120">[Créer et appliquer l’instantané initial](create-and-apply-the-initial-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="d828a-120">[Create and Apply the Initial Snapshot](create-and-apply-the-initial-snapshot.md) </span></span>  
 <span data-ttu-id="d828a-121">[Afficher et modifier les propriétés d’une publication](publish/view-and-modify-publication-properties.md) </span><span class="sxs-lookup"><span data-stu-id="d828a-121">[View and Modify Publication Properties](publish/view-and-modify-publication-properties.md) </span></span>  
 <span data-ttu-id="d828a-122">[Initialiser un abonnement avec un instantané](initialize-a-subscription-with-a-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="d828a-122">[Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) </span></span>  
 <span data-ttu-id="d828a-123">[Publier des données et des objets de base de données](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="d828a-123">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 [<span data-ttu-id="d828a-124">Présentation des Agents de réplication</span><span class="sxs-lookup"><span data-stu-id="d828a-124">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
