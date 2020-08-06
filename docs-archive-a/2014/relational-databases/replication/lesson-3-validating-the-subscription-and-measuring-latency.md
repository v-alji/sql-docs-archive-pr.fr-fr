---
title: 'Leçon 3 : Validation de l’abonnement et mesure de la latence | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 147f7b93-1804-4e0b-9e17-57a51d035b2a
author: rothja
ms.author: jroth
ms.openlocfilehash: e4893c054d25d131eb2f88f32291606b0b789af7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707372"
---
# <a name="lesson-3-validating-the-subscription-and-measuring-latency"></a><span data-ttu-id="9a6a8-102">Leçon 3 : Validation de l'abonnement et mesure de la latence</span><span class="sxs-lookup"><span data-stu-id="9a6a8-102">Lesson 3: Validating the Subscription and Measuring Latency</span></span>
  <span data-ttu-id="9a6a8-103">Dans cette leçon, vous allez utiliser des jetons de suivi pour vérifier que les modifications sont en cours de réplication vers l'Abonné et pour déterminer la latence, à savoir le temps qu'il faut pour qu'une modification apportée sur le serveur de publication apparaisse sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="9a6a8-103">In this lesson, you will use tracer tokens to verify that changes are being replicated to the Subscriber and to determine latency, the time it takes for a change made at the Publisher to appear to the Subscriber.</span></span> <span data-ttu-id="9a6a8-104">Cette leçon suppose que vous avez terminé la leçon précédente, [Leçon 2 : Création d’un abonnement à la publication transactionnelle](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span><span class="sxs-lookup"><span data-stu-id="9a6a8-104">This lesson requires that you have completed the previous lesson, [Lesson 2: Creating a Subscription to the Transactional Publication](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span></span>  
  
### <a name="to-insert-a-tracer-token-and-view-information-on-the-token"></a><span data-ttu-id="9a6a8-105">Pour insérer un jeton de suivi et afficher des informations sur le jeton</span><span class="sxs-lookup"><span data-stu-id="9a6a8-105">To insert a tracer token and view information on the token</span></span>  
  
1.  <span data-ttu-id="9a6a8-106">Connectez-vous au serveur de publication dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], développez le nœud du serveur, cliquez avec le bouton droit sur le dossier **Réplication** , puis cliquez sur **Lancer le moniteur de réplication**.</span><span class="sxs-lookup"><span data-stu-id="9a6a8-106">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, right-click the **Replication** folder, and then click **Launch Replication Monitor**.</span></span>  
  
     <span data-ttu-id="9a6a8-107">Le moniteur de réplication démarre.</span><span class="sxs-lookup"><span data-stu-id="9a6a8-107">Replication Monitor launches.</span></span>  
  
2.  <span data-ttu-id="9a6a8-108">Développez un groupe de serveurs de publication dans le volet gauche, développez une instance du serveur de publication, puis cliquez sur la publication **AdvWorksProductTrans** .</span><span class="sxs-lookup"><span data-stu-id="9a6a8-108">Expand a Publisher group in the left pane, expand the Publisher instance, and then click the **AdvWorksProductTrans** publication.</span></span>  
  
3.  <span data-ttu-id="9a6a8-109">Cliquez sur l'onglet **Jetons de suivi** .</span><span class="sxs-lookup"><span data-stu-id="9a6a8-109">Click the **Tracer Tokens** tab.</span></span>  
  
4.  <span data-ttu-id="9a6a8-110">Cliquez sur **Insérer un suivi**.</span><span class="sxs-lookup"><span data-stu-id="9a6a8-110">Click **Insert Tracer**.</span></span>  
  
5.  <span data-ttu-id="9a6a8-111">Affichez le temps écoulé pour le jeton de suivi dans les colonnes suivantes : **Du serveur de publication vers le serveur de distribution**, **Du serveur de distribution vers l'Abonné**et **Latence totale**.</span><span class="sxs-lookup"><span data-stu-id="9a6a8-111">View elapsed time for the tracer token in the following columns: **Publisher to Distributor**, **Distributor to Subscriber**, **Total Latency**.</span></span> <span data-ttu-id="9a6a8-112">La valeur **en attente** indique que le jeton n’a pas atteint un point donné.</span><span class="sxs-lookup"><span data-stu-id="9a6a8-112">A value of **Pending** indicates that the token has not reached a given point.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9a6a8-113">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="9a6a8-113">Next Steps</span></span>  
 <span data-ttu-id="9a6a8-114">Dans cette leçon, vous avez utilisé avec succès les jetons de suivi pour valider que les modifications de données sont bien en cours de réplication du serveur de publication vers l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="9a6a8-114">In this lesson, you successfully used tracer tokens to validate that data changes are being replicated from the Publisher to the Subscriber.</span></span> <span data-ttu-id="9a6a8-115">Vous pouvez aussi insérer, modifier ou supprimer des données dans la table **Product** du serveur de publication et interroger la table **Product** de l'Abonné pour afficher les modifications après qu'elles ont été répliquées.</span><span class="sxs-lookup"><span data-stu-id="9a6a8-115">You can also insert, update, or delete data in the **Product** table at the Publisher and query the **Product** table at the Subscriber to view these changes after they are replicated.</span></span>  
  
 <span data-ttu-id="9a6a8-116">Ainsi s'achève le didacticiel sur la réplication de données entre serveurs connectés en permanence.</span><span class="sxs-lookup"><span data-stu-id="9a6a8-116">This completes the Replicating Data Between Continuously Connected Servers tutorial.</span></span> <span data-ttu-id="9a6a8-117">Pour obtenir un didacticiel similaire utilisant la réplication de fusion, consultez [Tutorial: Replicating Data with Mobile Clients](tutorial-replicating-data-with-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="9a6a8-117">For a similar tutorial that uses merge replication, see [Tutorial: Replicating Data with Mobile Clients](tutorial-replicating-data-with-mobile-clients.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a6a8-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9a6a8-118">See Also</span></span>  
 [<span data-ttu-id="9a6a8-119">Mesurer la latence et valider les connexions pour la réplication transactionnelle</span><span class="sxs-lookup"><span data-stu-id="9a6a8-119">Measure Latency and Validate Connections for Transactional Replication</span></span>](monitor/measure-latency-and-validate-connections-for-transactional-replication.md)  
  
  
