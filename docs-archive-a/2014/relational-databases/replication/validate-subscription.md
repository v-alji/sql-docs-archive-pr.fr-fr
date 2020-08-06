---
title: Valider l’abonnement | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.validate.validateandresynch.f1
helpviewer_keywords:
- Validate Subscription dialog box
ms.assetid: 74bdf5e1-b886-4284-b5fb-332bf79ae083
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 010b5b2e9778ccf37133b0a84796373c012290f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603368"
---
# <a name="validate-subscription"></a><span data-ttu-id="2ce51-102">Valider l'abonnement</span><span class="sxs-lookup"><span data-stu-id="2ce51-102">Validate Subscription</span></span>
  <span data-ttu-id="2ce51-103">Utilisez la boîte de dialogue **Valider l'abonnement** pour indiquer qu'un abonnement à une publication de fusion doit être validée lors de la prochaine exécution de l'Agent de fusion de l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="2ce51-103">Use the **Validate Subscription** dialog box to specify that a subscription to a merge publication should be validated the next time the Merge Agent for the subscription runs.</span></span> <span data-ttu-id="2ce51-104">Le résultat de la validation figure dans le Moniteur de réplication.</span><span class="sxs-lookup"><span data-stu-id="2ce51-104">The results of validation are displayed in Replication Monitor.</span></span> <span data-ttu-id="2ce51-105">Pour plus d'informations, voir [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="2ce51-105">For more information, see [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span></span>  
  
 <span data-ttu-id="2ce51-106">Vous pouvez également valider tous les abonnements à une publication de fusion en cliquant avec le bouton droit de la souris sur une publication dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] et en cliquant sur **Valider tous les abonnements**.</span><span class="sxs-lookup"><span data-stu-id="2ce51-106">It is also possible to validate all subscriptions to a merge publication by right-clicking a publication in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and clicking **Validate All Subscriptions**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2ce51-107">Options</span><span class="sxs-lookup"><span data-stu-id="2ce51-107">Options</span></span>  
 <span data-ttu-id="2ce51-108">**Date de la dernière tentative de validation**</span><span class="sxs-lookup"><span data-stu-id="2ce51-108">**Date of the last attempted validation**</span></span>  
 <span data-ttu-id="2ce51-109">Date de la dernière session de l'Agent de fusion qui incluait la validation d'abonnement, que la validation ait abouti ou non.</span><span class="sxs-lookup"><span data-stu-id="2ce51-109">The date of the last Merge Agent session that included subscription validation, whether or not that validation was successful.</span></span>  
  
 <span data-ttu-id="2ce51-110">**Date de la dernière validation réussie**</span><span class="sxs-lookup"><span data-stu-id="2ce51-110">**Date of the last successful validation**</span></span>  
 <span data-ttu-id="2ce51-111">Date de la dernière session de l'Agent de fusion qui incluait une validation d'abonnement réussie.</span><span class="sxs-lookup"><span data-stu-id="2ce51-111">The date of the last Merge Agent session that included a successful subscription validation.</span></span>  
  
 <span data-ttu-id="2ce51-112">**Valider cet abonnement**</span><span class="sxs-lookup"><span data-stu-id="2ce51-112">**Validate this subscription**</span></span>  
 <span data-ttu-id="2ce51-113">Sélectionnez cette option pour valider l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="2ce51-113">Select to validate the subscription.</span></span>  
  
 <span data-ttu-id="2ce51-114">**Options**</span><span class="sxs-lookup"><span data-stu-id="2ce51-114">**Options**</span></span>  
 <span data-ttu-id="2ce51-115">Cliquez pour accéder à la boîte de dialogue **Options de validation d'abonnement** qui permet d'indiquer si vous voulez utiliser la validation du nombre de lignes ou la validation de somme de contrôle.</span><span class="sxs-lookup"><span data-stu-id="2ce51-115">Click to access the **Subscription Validation Options** dialog box, which allows you to specify whether to use row count validation or binary checksum validation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ce51-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2ce51-116">See Also</span></span>  
 [<span data-ttu-id="2ce51-117">Valider des données répliquées</span><span class="sxs-lookup"><span data-stu-id="2ce51-117">Validate Replicated Data</span></span>](validate-data-at-the-subscriber.md)  
  
  
