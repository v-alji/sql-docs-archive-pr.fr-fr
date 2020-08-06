---
title: Initialiser les abonnements | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.initializesubscriptions.f1
ms.assetid: 7b170e4e-470d-4828-a9ed-7435b0b03514
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f8c9388138ddec275dc1abd2b75e0b0c7fc99de4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601320"
---
# <a name="initialize-subscriptions"></a><span data-ttu-id="f2736-102">Initialiser les abonnements</span><span class="sxs-lookup"><span data-stu-id="f2736-102">Initialize Subscriptions</span></span>
  <span data-ttu-id="f2736-103">Les abonnés doivent être initialisés pour pouvoir recevoir des données répliquées.</span><span class="sxs-lookup"><span data-stu-id="f2736-103">Subscribers must be initialized before they can begin receiving replicated data.</span></span> <span data-ttu-id="f2736-104">Un jeu de données initial n'est pas nécessaire, mais l'abonné doit avoir au minimum le schéma de chaque objet répliqué ainsi que les tables de métadonnées et les procédures nécessaires à la réplication.</span><span class="sxs-lookup"><span data-stu-id="f2736-104">An initial dataset is not required, but the Subscriber must at least have the schema for each replicated object and any metadata tables and procedures required by replication.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f2736-105">Options</span><span class="sxs-lookup"><span data-stu-id="f2736-105">Options</span></span>  
 <span data-ttu-id="f2736-106">**Propriétés de l'abonnement**</span><span class="sxs-lookup"><span data-stu-id="f2736-106">**Subscription properties**</span></span>  
 <span data-ttu-id="f2736-107">Activez la case à cocher dans la colonne **Initialiser** de chaque abonné nécessitant un jeu de données initial.</span><span class="sxs-lookup"><span data-stu-id="f2736-107">Select the check box in the **Initialize** column for each Subscriber that requires an initial data set.</span></span> <span data-ttu-id="f2736-108">Si vous désactivez la case à cocher, seules les métadonnées et les procédures de réplication sont initialisées.</span><span class="sxs-lookup"><span data-stu-id="f2736-108">If the check box is cleared, only the replication metadata and procedures will be initialized.</span></span> <span data-ttu-id="f2736-109">Pour plus d’informations sur l’initialisation d’un abonnement sans instantané, consultez [Initialiser un abonnement transactionnel sans instantané](initialize-a-transactional-subscription-without-a-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="f2736-109">For more information about initializing a subscription without a snapshot, see [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span></span>  
  
 <span data-ttu-id="f2736-110">Sélectionnez **Immédiatement** dans la zone de liste déroulante dans la colonne **À quel moment** pour que l'Agent de fusion ou l'Agent de distribution transfère les fichiers d'instantané vers l'abonné à la fin de l'exécution de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="f2736-110">Select **Immediately** from the drop-down list box in the **Initialize When** column to have the Merge Agent or Distribution Agent transfer snapshot files to the Subscriber after this wizard is completed.</span></span> <span data-ttu-id="f2736-111">Sélectionnez **Lors de la première synchronisation** pour que l'Agent transfère les fichiers lors de la prochaine exécution planifiée de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="f2736-111">Select **At first synchronization** to have the agent transfer the files the next time it is scheduled to run.</span></span> <span data-ttu-id="f2736-112">L’option **Immédiatement** n’est pas disponible pour les abonnements par extraction à [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2736-112">The **Immediately** option is not available for pull subscriptions to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="f2736-113">L'Agent de fusion et l'Agent de distribution ne fonctionnent pas sur les instances de [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]; l'abonnement doit donc être initialisé via une autre méthode.</span><span class="sxs-lookup"><span data-stu-id="f2736-113">The Merge Agent and Distribution Agent do not run on instances of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]; therefore the subscription must be initialized through another method.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f2736-114">Il se peut que l'Assistant demande une connexion au serveur de distribution pour pouvoir démarrer le travail approprié pour l'Agent de distribution ou l'Agent de fusion.</span><span class="sxs-lookup"><span data-stu-id="f2736-114">The wizard might prompt for a connection to the Distributor in order to start the appropriate job for the Distribution Agent or Merge Agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2736-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f2736-115">See Also</span></span>  
 <span data-ttu-id="f2736-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="f2736-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="f2736-117">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="f2736-117">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="f2736-118">[Initialiser un abonnement](initialize-a-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="f2736-118">[Initialize a Subscription](initialize-a-subscription.md) </span></span>  
 [<span data-ttu-id="f2736-119">S'abonner à des publications</span><span class="sxs-lookup"><span data-stu-id="f2736-119">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
