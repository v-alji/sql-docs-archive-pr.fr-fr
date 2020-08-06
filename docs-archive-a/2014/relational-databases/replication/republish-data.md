---
title: Republier des données | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- republishing data
- publishing [SQL Server replication], Subscribers
- Subscribers [SQL Server replication], republishing data
ms.assetid: a1485cf4-b1c4-49e9-ab06-8ccfaad998f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f1e4213266121b3bf55bf2857e15f71f1e94e301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600766"
---
# <a name="republish-data"></a><span data-ttu-id="3c9ba-102">Republier des données</span><span class="sxs-lookup"><span data-stu-id="3c9ba-102">Republish Data</span></span>
  <span data-ttu-id="3c9ba-103">Dans un modèle de republication, le serveur de publication envoie les données à un Abonné qui les retransmet ensuite à un nombre quelconque d'Abonnés.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-103">In a republishing model, the Publisher sends data to a Subscriber, which then republishes the data to any number of other Subscribers.</span></span> <span data-ttu-id="3c9ba-104">Cette méthode est utile lorsqu'un serveur de publication doit envoyer les données à des Abonnés via une liaison de communication lente ou coûteuse.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-104">This is useful when a Publisher must send data to Subscribers over a slow or expensive communications link.</span></span> <span data-ttu-id="3c9ba-105">S'il existe beaucoup d'Abonnés à l'extrémité distante de cette liaison, l'utilisation d'un serveur de republication permet de déplacer la totalité de la charge de distribution de ce côté de la liaison.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-105">If there are a number of Subscribers on the far side of that link, using a republisher shifts the bulk of the distribution load to that side of the link.</span></span>  
  
 <span data-ttu-id="3c9ba-106">Pour republier les données, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="3c9ba-106">Republishing data involves the following steps:</span></span>  
  
1.  <span data-ttu-id="3c9ba-107">Créez une publication sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-107">Create a publication at the Publisher.</span></span>  
  
2.  <span data-ttu-id="3c9ba-108">Créez un abonnement à une publication pour l'Abonné chargé de la republication.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-108">Create a subscription to the publication for the republishing Subscriber.</span></span>  
  
3.  <span data-ttu-id="3c9ba-109">Initialisez l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-109">Initialize the subscription.</span></span> <span data-ttu-id="3c9ba-110">L'abonnement doit être initialisé avant de créer la publication sur l'Abonné chargé de la republication sans quoi la réplication échoue.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-110">The subscription must be initialized before the publication is created at the republishing Subscriber, or replication will fail.</span></span>  
  
4.  <span data-ttu-id="3c9ba-111">Créez une publication dans la base de données d'abonnement sur l'Abonné chargé de la republication.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-111">Create a publication in the subscription database at the republishing Subscriber.</span></span>  
  
5.  <span data-ttu-id="3c9ba-112">Créez des abonnements à la publication sur l'Abonné chargé de la republication pour les autres Abonnés.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-112">Create subscriptions to the publication at the republishing Subscriber for the other Subscribers.</span></span>  
  
6.  <span data-ttu-id="3c9ba-113">Initialisez les abonnements.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-113">Initialize the subscriptions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3c9ba-114">Si vous utilisez la réplication de fusion dans une topologie de republication, tous les Abonnés chargés de la republication doivent utiliser des abonnements serveur.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-114">If you use merge replication in a republishing topology, all republishing Subscribers must use server subscriptions.</span></span> <span data-ttu-id="3c9ba-115">Pour plus d’informations sur les types d’abonnements, consultez [S’abonner à des publications](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="3c9ba-115">For more information about subscription types, see [Subscribe to Publications](subscribe-to-publications.md).</span></span>  
  
 <span data-ttu-id="3c9ba-116">Dans l'illustration suivante, le serveur de publication et celui de republication sont aussi leurs propres distributeurs locaux.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-116">In the following illustration, both the Publisher and the republisher are acting as their own local Distributors.</span></span> <span data-ttu-id="3c9ba-117">Si chacun d'eux a été configuré pour utiliser un serveur de distribution distant, chaque serveur de distribution doit se trouver du même côté de la liaison de communication lente ou coûteuse que son serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-117">If each were set up to use a remote Distributor, each Distributor would need to be on the same side of the slow or expensive communications link as its Publisher.</span></span> <span data-ttu-id="3c9ba-118">Les serveurs de publication doivent être connectés à des serveurs de distribution distants par l'intermédiaire de liaisons de communications fiables à haut débit.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-118">Publishers must be connected to remote Distributors by reliable, high-speed communications links.</span></span>  
  
 <span data-ttu-id="3c9ba-119">![Republication de données](media/repl-06a.gif "Republication de données")</span><span class="sxs-lookup"><span data-stu-id="3c9ba-119">![Republishing data](media/repl-06a.gif "Republishing data")</span></span>  
  
 <span data-ttu-id="3c9ba-120">Tous les serveurs peuvent être à la fois serveur de publication et Abonné.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-120">Any server can act as both a Publisher and Subscriber.</span></span> <span data-ttu-id="3c9ba-121">Le diagramme suivant illustre l'exemple d'une publication d'une table située à Londres et qui doit être distribuée dans quatre villes aux États-Unis : Chicago, New York, San Diego et Seattle.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-121">For example, consider the following diagram in which a publication of a table exists in London and must be distributed to four different cities in the United States: Chicago, New York, San Diego, and Seattle.</span></span> <span data-ttu-id="3c9ba-122">Le serveur situé à New York a été sélectionné pour s'abonner à la table publiée sur le serveur londonien, car le site new-yorkais réunit les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="3c9ba-122">The server in New York is chosen to subscribe to the published table originating in London, because the New York site meets these conditions:</span></span>  
  
-   <span data-ttu-id="3c9ba-123">La liaison réseau de retour vers Londres est relativement fiable.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-123">The network link back to London is relatively reliable.</span></span>  
  
-   <span data-ttu-id="3c9ba-124">Les coûts de communication de Londres à New York sont acceptables.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-124">The London-to-New York communication costs are acceptable.</span></span>  
  
-   <span data-ttu-id="3c9ba-125">Les lignes de communication réseau à partir de New York vers tous les autres sites d'Abonnés aux États-Unis sont de bonne qualité.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-125">There are good network communications lines from New York to all other Subscriber sites in the United States.</span></span>  
  
     <span data-ttu-id="3c9ba-126">![Republication de données vers des emplacements dispersés](media/repl-06.gif "Republication de données vers des emplacements dispersés")</span><span class="sxs-lookup"><span data-stu-id="3c9ba-126">![Republishing data to dispersed locations](media/repl-06.gif "Republishing data to dispersed locations")</span></span>  
  
 <span data-ttu-id="3c9ba-127">La réplication prend en charge les scénarios de republication répertoriés dans le tableau ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-127">Replication supports the republishing scenarios shown in the following table.</span></span>  
  
|<span data-ttu-id="3c9ba-128">Serveur de publication</span><span class="sxs-lookup"><span data-stu-id="3c9ba-128">Publisher</span></span>|<span data-ttu-id="3c9ba-129">Abonné de publication</span><span class="sxs-lookup"><span data-stu-id="3c9ba-129">Publishing Subscriber</span></span>|<span data-ttu-id="3c9ba-130">Abonné</span><span class="sxs-lookup"><span data-stu-id="3c9ba-130">Subscriber</span></span>|  
|---------------|---------------------------|----------------|  
|<span data-ttu-id="3c9ba-131">Publication transactionnelle</span><span class="sxs-lookup"><span data-stu-id="3c9ba-131">Transactional publication</span></span>|<span data-ttu-id="3c9ba-132">Abonnement transactionnel/publication transactionnelle</span><span class="sxs-lookup"><span data-stu-id="3c9ba-132">Transactional subscription/transactional publication</span></span>|<span data-ttu-id="3c9ba-133">Abonnement transactionnel</span><span class="sxs-lookup"><span data-stu-id="3c9ba-133">Transactional subscription</span></span>|  
|<span data-ttu-id="3c9ba-134">Publication transactionnelle</span><span class="sxs-lookup"><span data-stu-id="3c9ba-134">Transactional publication</span></span>|<span data-ttu-id="3c9ba-135">Abonnement transactionnel/publication de fusion<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="3c9ba-135">Transactional subscription/merge publication<sup>1</sup></span></span>|<span data-ttu-id="3c9ba-136">Abonnement de fusion</span><span class="sxs-lookup"><span data-stu-id="3c9ba-136">Merge subscription</span></span>|  
|<span data-ttu-id="3c9ba-137">Publication de fusion</span><span class="sxs-lookup"><span data-stu-id="3c9ba-137">Merge publication</span></span>|<span data-ttu-id="3c9ba-138">Abonnement de fusion/publication de fusion</span><span class="sxs-lookup"><span data-stu-id="3c9ba-138">Merge subscription/merge publication</span></span>|<span data-ttu-id="3c9ba-139">Abonnement de fusion</span><span class="sxs-lookup"><span data-stu-id="3c9ba-139">Merge subscription</span></span>|  
|<span data-ttu-id="3c9ba-140">Publication de fusion</span><span class="sxs-lookup"><span data-stu-id="3c9ba-140">Merge publication</span></span>|<span data-ttu-id="3c9ba-141">Abonnement de fusion/publication transactionnelle</span><span class="sxs-lookup"><span data-stu-id="3c9ba-141">Merge subscription/transactional publication</span></span>|<span data-ttu-id="3c9ba-142">Abonnement transactionnel</span><span class="sxs-lookup"><span data-stu-id="3c9ba-142">Transactional subscription</span></span>|  
  
 <span data-ttu-id="3c9ba-143"><sup>1</sup> Vous devez définir la `@published_in_tran_pub` propriété sur la publication de fusion.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-143"><sup>1</sup>You should set the `@published_in_tran_pub` property on the merge publication.</span></span> <span data-ttu-id="3c9ba-144">Par défaut, la réplication transactionnelle suppose que les tables sur l'Abonné soient traitées en tant qu'éléments accessibles en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-144">By default, transactional replication expects tables at the Subscriber to be treated as read-only.</span></span> <span data-ttu-id="3c9ba-145">Si la réplication de fusion apporte des modifications aux données d'une table dans un abonnement transactionnel, une non-convergence de données peut se produire.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-145">If merge replication makes data changes to a table in a transactional subscription, non-convergence of data can occur.</span></span> <span data-ttu-id="3c9ba-146">Pour éviter ce risque, il est recommandé de spécifier toute table de ce type en tant qu'objet en téléchargement seul dans la publication de fusion.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-146">To avoid this risk, we recommend that any such table be specified as download-only in the merge publication.</span></span> <span data-ttu-id="3c9ba-147">Cela empêche un Abonné de fusion de télécharger les modifications apportées aux données de la table.</span><span class="sxs-lookup"><span data-stu-id="3c9ba-147">This prevents a merge Subscriber from uploading data changes to the table.</span></span> <span data-ttu-id="3c9ba-148">Pour plus d’informations, consultez [Optimiser les performances de la réplication de fusion avec les articles en téléchargement seul](merge/optimize-merge-replication-performance-with-download-only-articles.md).</span><span class="sxs-lookup"><span data-stu-id="3c9ba-148">For more information, see [Optimize Merge Replication Performance with Download-Only Articles](merge/optimize-merge-replication-performance-with-download-only-articles.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c9ba-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3c9ba-149">See Also</span></span>  
 <span data-ttu-id="3c9ba-150">[Configurer la distribution](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="3c9ba-150">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="3c9ba-151">[Publier des données et des objets de base de données](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="3c9ba-151">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 <span data-ttu-id="3c9ba-152">[S’abonner aux Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="3c9ba-152">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 <span data-ttu-id="3c9ba-153">[Initialiser un abonnement](initialize-a-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="3c9ba-153">[Initialize a Subscription](initialize-a-subscription.md) </span></span>  
 [<span data-ttu-id="3c9ba-154">Synchroniser les données</span><span class="sxs-lookup"><span data-stu-id="3c9ba-154">Synchronize Data</span></span>](synchronize-data.md)  
  
  
