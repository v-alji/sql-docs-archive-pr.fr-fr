---
title: Valider tous les abonnements | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.validate.allsubscriptions.f1
helpviewer_keywords:
- Validate All Subscriptions dialog box
ms.assetid: 32e31469-36e4-42d9-a57a-12388bfd229d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 27a7a4f5e5c3c303d5a1cbe257c0a0e9b531e824
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612219"
---
# <a name="validate-all-subscriptions"></a><span data-ttu-id="39754-102">Valider tous les abonnements</span><span class="sxs-lookup"><span data-stu-id="39754-102">Validate All Subscriptions</span></span>
  <span data-ttu-id="39754-103">La boîte de dialogue **Valider tous les abonnements** permet d'indiquer que tous les abonnements à une publication de fusion doivent être validés lors de la prochaine exécution de l'Agent de fusion de chaque abonnement.</span><span class="sxs-lookup"><span data-stu-id="39754-103">Use the **Validate All Subscriptions** dialog box to specify that all subscriptions to a merge publication should be validated the next time the Merge Agent for each subscription runs.</span></span> <span data-ttu-id="39754-104">Le résultat de la validation figure dans le Moniteur de réplication.</span><span class="sxs-lookup"><span data-stu-id="39754-104">The results of validation are displayed in Replication Monitor.</span></span> <span data-ttu-id="39754-105">Pour plus d'informations, voir [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="39754-105">For more information, see [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span></span>  
  
 <span data-ttu-id="39754-106">Vous pouvez également valider un seul abonnement en cliquant avec le bouton droit de la souris sur un abonnement dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , puis en choisissant **Valider l'abonnement**.</span><span class="sxs-lookup"><span data-stu-id="39754-106">It is also possible to validate a single subscription by right-clicking a subscription in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and clicking **Validate Subscription**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="39754-107">Options</span><span class="sxs-lookup"><span data-stu-id="39754-107">Options</span></span>  
 <span data-ttu-id="39754-108">**Vérifier uniquement le nombre de lignes**</span><span class="sxs-lookup"><span data-stu-id="39754-108">**Verify the row counts only**</span></span>  
 <span data-ttu-id="39754-109">Sélectionnez cette option pour indiquer si la table au niveau de l'Abonné a le même nombre de lignes que la table sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="39754-109">Select to validate whether the table at the Subscriber has the same number of rows as the table at the Publisher.</span></span> <span data-ttu-id="39754-110">Cette méthode ne valide pas le contenu des correspondances de lignes.</span><span class="sxs-lookup"><span data-stu-id="39754-110">This method does not validate that the content of the rows matches.</span></span> <span data-ttu-id="39754-111">La validation du nombre de lignes fournit une approche allégée de la validation qui vous permet de savoir qu'il existe des problèmes au niveau des données.</span><span class="sxs-lookup"><span data-stu-id="39754-111">Row count validation provides a lightweight approach to validation that can make you aware of issues with your data.</span></span>  
  
 <span data-ttu-id="39754-112">**Vérifier le nombre de lignes et comparer les totaux de contrôle pour vérifier les données de ligne**</span><span class="sxs-lookup"><span data-stu-id="39754-112">**Verify the row counts and compare checksums to verify the row data**</span></span>  
 <span data-ttu-id="39754-113">Outre le comptage des lignes sur le serveur de publication et sur l'Abonné, une somme de contrôle de toutes les données est calculée à l'aide de l'algorithme de somme de contrôle binaire.</span><span class="sxs-lookup"><span data-stu-id="39754-113">In addition to taking a count of rows at the Publisher and Subscriber, a checksum of all the data is calculated using the binary checksum algorithm.</span></span> <span data-ttu-id="39754-114">Si le nombre de lignes est erroné, la somme de contrôle n'est pas effectuée.</span><span class="sxs-lookup"><span data-stu-id="39754-114">If the row count fails, the checksum is not performed.</span></span> <span data-ttu-id="39754-115">Cette option n'est pas valide pour [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39754-115">This option is not valid for [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39754-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="39754-116">See Also</span></span>  
 [<span data-ttu-id="39754-117">Valider des données répliquées</span><span class="sxs-lookup"><span data-stu-id="39754-117">Validate Replicated Data</span></span>](validate-data-at-the-subscriber.md)  
  
  
