---
title: Abonnements pouvant être mis à jour | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.updatablesubscriptions.f1
ms.assetid: 8e9a13a0-6b24-47c6-9d83-3cbaf08f673d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 447114152365e098420f46d4b7e880e8f2907864
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697884"
---
# <a name="updatable-subscriptions"></a><span data-ttu-id="b426d-102">Abonnements pouvant être mis à jour</span><span class="sxs-lookup"><span data-stu-id="b426d-102">Updatable Subscriptions</span></span>
  <span data-ttu-id="b426d-103">Avec la réplication transactionnelle, les données répliquées doivent être traitées en lecture seule. Toutefois, vous pouvez modifier les données répliquées au niveau d’un abonné [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en utilisant des abonnements pouvant être mis à jour.</span><span class="sxs-lookup"><span data-stu-id="b426d-103">With transactional replication, replicated data should be treated as read-only; however, you can modify replicated data at a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscriber by using updatable subscriptions.</span></span> <span data-ttu-id="b426d-104">Si vous devez modifier des données sur l'Abonné, vous pouvez choisir l'une des options suivantes selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="b426d-104">If you need to modify data at the Subscriber, choose one of the following options depending on your requirements.</span></span>  
  
|<span data-ttu-id="b426d-105">Type d'abonnement pouvant être mis à jour</span><span class="sxs-lookup"><span data-stu-id="b426d-105">Updatable Subscription Type</span></span>|<span data-ttu-id="b426d-106">Spécifications</span><span class="sxs-lookup"><span data-stu-id="b426d-106">Requirements</span></span>|  
|---------------------------------|------------------|  
|<span data-ttu-id="b426d-107">Mise à jour immédiate</span><span class="sxs-lookup"><span data-stu-id="b426d-107">Immediate Updating</span></span>|<span data-ttu-id="b426d-108">Le serveur de publication et l'Abonné doivent être connectés pour mettre à jour les données sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="b426d-108">Publisher and Subscriber must be connected to update data at the Subscriber.</span></span>|  
|<span data-ttu-id="b426d-109">Mise à jour en attente</span><span class="sxs-lookup"><span data-stu-id="b426d-109">Queued Updating</span></span>|<span data-ttu-id="b426d-110">Le serveur de publication et l'Abonné n'ont pas besoin d'être connectés pour mettre à jour les données sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="b426d-110">Publisher and Subscriber do not have to be connected to update data at the Subscriber.</span></span> <span data-ttu-id="b426d-111">Les mises à jour peuvent être effectuées hors ligne et synchronisées ensuite entre le serveur de publication et l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="b426d-111">Updates can be made while offline, and later synchronized between the Publisher and Subscriber.</span></span>|  
  
## <a name="options"></a><span data-ttu-id="b426d-112">Options</span><span class="sxs-lookup"><span data-stu-id="b426d-112">Options</span></span>  
 <span data-ttu-id="b426d-113">**Répliquer les modifications de l'Abonné**</span><span class="sxs-lookup"><span data-stu-id="b426d-113">**Replicate Subscriber changes**</span></span>  
 <span data-ttu-id="b426d-114">Activez la case à cocher dans la colonne **Répliquer** pour chaque abonné qui doit pouvoir effectuer des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="b426d-114">Select the check box in the **Replicate** column for each Subscriber that should be able to make updates.</span></span> <span data-ttu-id="b426d-115">Pour les abonnés qui peuvent effectuer des mises à jour, sélectionnez l'option appropriée dans la zone de liste déroulante de la colonne **Valider sur le serveur de publication** :</span><span class="sxs-lookup"><span data-stu-id="b426d-115">For those Subscribers that can make updates, select the appropriate option from the drop-down list box in the **Commit at Publisher** column:</span></span>  
  
-   <span data-ttu-id="b426d-116">Sélectionnez **Enregistrer les modifications simultanément** pour un abonnement mis à jour immédiatement.</span><span class="sxs-lookup"><span data-stu-id="b426d-116">Select **Simultaneously commit changes** for an immediate updating subscription.</span></span>  
  
-   <span data-ttu-id="b426d-117">Sélectionnez **Mettre les modifications en file d'attente et valider dès que possible** pour un abonnement mis à jour en file d'attente.</span><span class="sxs-lookup"><span data-stu-id="b426d-117">Select **Queue changes and commit when possible** for a queued updating subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b426d-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b426d-118">See Also</span></span>  
 <span data-ttu-id="b426d-119">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="b426d-119">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="b426d-120">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="b426d-120">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="b426d-121">[S’abonner aux Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="b426d-121">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 [<span data-ttu-id="b426d-122">Updatable Subscriptions for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="b426d-122">Updatable Subscriptions for Transactional Replication</span></span>](transactional/updatable-subscriptions-for-transactional-replication.md)  
  
  
