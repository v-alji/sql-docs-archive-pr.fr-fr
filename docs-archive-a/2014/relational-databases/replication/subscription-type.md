---
title: Type d’abonnement | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.subscriptiontype.f1
ms.assetid: 9a50f588-ee45-4a87-826f-372ff0798587
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 614ff910b13706485ee9466c884243ff1c9027ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699449"
---
# <a name="subscription-type"></a><span data-ttu-id="11f8c-102">Type d'abonnement</span><span class="sxs-lookup"><span data-stu-id="11f8c-102">Subscription Type</span></span>
  <span data-ttu-id="11f8c-103">La réplication de fusion propose deux types d’abonnements : l’abonnement serveur et l’abonnement client (connus dans les versions précédentes de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sous les noms respectifs d’abonnement global et d’abonnement local).</span><span class="sxs-lookup"><span data-stu-id="11f8c-103">Merge replication offers two subscription types: server and client (referred to in previous versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as global and local, respectively).</span></span> <span data-ttu-id="11f8c-104">Les abonnés disposant d'un abonnement serveur peuvent :</span><span class="sxs-lookup"><span data-stu-id="11f8c-104">Subscribers with a server subscription can:</span></span>  
  
-   <span data-ttu-id="11f8c-105">republier des données à d'autres Abonnés ;</span><span class="sxs-lookup"><span data-stu-id="11f8c-105">Republish data to other Subscribers.</span></span>  
  
-   <span data-ttu-id="11f8c-106">agir en l'état d'autre partenaire de synchronisation ;</span><span class="sxs-lookup"><span data-stu-id="11f8c-106">Serve as alternate synchronization partners.</span></span>  
  
-   <span data-ttu-id="11f8c-107">résoudre des conflits d'après une liste de priorités que vous établissez.</span><span class="sxs-lookup"><span data-stu-id="11f8c-107">Resolve conflicts according to a priority you set.</span></span>  
  
 <span data-ttu-id="11f8c-108">La plupart des Abonnés n'ont pas besoin de cette fonctionnalité et peuvent passer par un abonnement client.</span><span class="sxs-lookup"><span data-stu-id="11f8c-108">Most Subscribers do not require this functionality and can use a client subscription.</span></span> <span data-ttu-id="11f8c-109">Les abonnements client permettent en effet la détection et la résolution de conflits, mais dans ce cas de figure les Abonnés ne se voient pas affecter de priorité : le premier Abonné soumettant une modification à un serveur de publication bénéficie de la préférence de validité des données sur tout conflit pouvant se produire relatif à cette modification.</span><span class="sxs-lookup"><span data-stu-id="11f8c-109">Client subscriptions still allow conflict detection and resolution, but Subscribers are not assigned a priority: the first Subscriber to submit a change to the Publisher wins any conflicts that might arise from that change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="11f8c-110">Vous ne pouvez pas modifier le type d'un abonnement après sa création.</span><span class="sxs-lookup"><span data-stu-id="11f8c-110">Subscription type cannot be changed after a subscription is created.</span></span>  
  
## <a name="options"></a><span data-ttu-id="11f8c-111">Options</span><span class="sxs-lookup"><span data-stu-id="11f8c-111">Options</span></span>  
 <span data-ttu-id="11f8c-112">**Propriétés de l'abonnement**</span><span class="sxs-lookup"><span data-stu-id="11f8c-112">**Subscription properties**</span></span>  
 <span data-ttu-id="11f8c-113">Permet de sélectionner pour chaque Abonné la valeur **Client** ou **Serveur** dans la zone de liste déroulante de la colonne **Type d'abonnement** .</span><span class="sxs-lookup"><span data-stu-id="11f8c-113">For each Subscriber, select **Client** or **Server** from the drop-down list box in the **Subscription Type** column.</span></span> <span data-ttu-id="11f8c-114">Dans le cas d'Abonnés bénéficiant d'un abonnement serveur, vous devez saisir un nombre compris entre 0 et 99,99 dans la colonne **Priorité pour la résolution des conflits** : plus ce nombre est grand, plus la priorité de l'Abonné est forte.</span><span class="sxs-lookup"><span data-stu-id="11f8c-114">For Subscribers with server subscriptions, enter a number between 0 and 99.99 in the **Priority for Conflict Resolution** column (the higher the number, the higher the priority for the Subscriber).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11f8c-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="11f8c-115">See Also</span></span>  
 <span data-ttu-id="11f8c-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="11f8c-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="11f8c-117">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="11f8c-117">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 [<span data-ttu-id="11f8c-118">S'abonner à des publications</span><span class="sxs-lookup"><span data-stu-id="11f8c-118">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
