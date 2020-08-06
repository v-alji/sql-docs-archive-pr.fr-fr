---
title: 'Didacticiel : Réplication de données entre serveurs connectés en permanence | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- tutorials [SQL Server replication]
- replication [SQL Server], tutorials
- wizards [SQL Server replication]
ms.assetid: 7b18a04a-2c3d-4efe-a0bc-c3f92be72fd0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 415cac62112c1c1d2aa6c42ec189c2614ec03923
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614484"
---
# <a name="tutorial-replicating-data-between-continuously-connected-servers"></a><span data-ttu-id="b55b7-102">Didacticiel : Réplication de données entre serveurs connectés en permanence</span><span class="sxs-lookup"><span data-stu-id="b55b7-102">Tutorial: Replicating Data Between Continuously Connected Servers</span></span>
  <span data-ttu-id="b55b7-103">La réplication constitue une bonne solution au problème de transfert de données entre serveurs connectés en permanence.</span><span class="sxs-lookup"><span data-stu-id="b55b7-103">Replication is a good solution to the problem of moving data between continuously connected servers.</span></span> <span data-ttu-id="b55b7-104">À l'aide des Assistants de réplication, vous pouvez aisément configurer et administrer une topologie de réplication.</span><span class="sxs-lookup"><span data-stu-id="b55b7-104">Using replication's wizards, you can easily configure and administer a replication topology.</span></span> <span data-ttu-id="b55b7-105">Ce didacticiel vous explique comment configurer une topologie de réplication dans le cas de serveurs connectés en permanence.</span><span class="sxs-lookup"><span data-stu-id="b55b7-105">This tutorial shows you how to configure a replication topology for continuously connected servers.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="b55b7-106">Contenu du didacticiel</span><span class="sxs-lookup"><span data-stu-id="b55b7-106">What You Will Learn</span></span>  
 <span data-ttu-id="b55b7-107">Ce didacticiel vous explique comment publier des données d'une base de données sur une autre à l'aide de la réplication transactionnelle.</span><span class="sxs-lookup"><span data-stu-id="b55b7-107">This tutorial will show you how to publish data from one database to another using transactional replication.</span></span> <span data-ttu-id="b55b7-108">La première leçon montre comment utiliser [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour créer une publication.</span><span class="sxs-lookup"><span data-stu-id="b55b7-108">The first lesson shows how to use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create a publication.</span></span> <span data-ttu-id="b55b7-109">Les leçons suivantes expliquent comment créer et valider un abonnement et comment mesurer la latence.</span><span class="sxs-lookup"><span data-stu-id="b55b7-109">Later lessons show how to create and validate a subscription and how to measure latency.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b55b7-110">Spécifications</span><span class="sxs-lookup"><span data-stu-id="b55b7-110">Requirements</span></span>  
 <span data-ttu-id="b55b7-111">Ce didacticiel est destiné aux utilisateurs qui sont familiers des opérations élémentaires de base de données, mais dont l'expérience en matière de réplication est limitée.</span><span class="sxs-lookup"><span data-stu-id="b55b7-111">This tutorial is intended for users who are familiar with basic database operations, but who have limited experience with replication.</span></span> <span data-ttu-id="b55b7-112">Pour suivre ce didacticiel, vous devez avoir terminé le didacticiel précédent, [Préparation du serveur pour la réplication](tutorial-preparing-the-server-for-replication.md).</span><span class="sxs-lookup"><span data-stu-id="b55b7-112">This tutorial requires that you have completed the previous tutorial, [Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
 <span data-ttu-id="b55b7-113">Pour utiliser ce didacticiel, les composants suivants doivent être installés sur votre système :</span><span class="sxs-lookup"><span data-stu-id="b55b7-113">To use this tutorial, your system must have the following components:</span></span>  
  
-   <span data-ttu-id="b55b7-114">Sur le serveur de publication (source)</span><span class="sxs-lookup"><span data-stu-id="b55b7-114">At the Publisher server (source):</span></span>  
  
    -   <span data-ttu-id="b55b7-115">Toute édition de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]sauf Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) ou [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b55b7-115">Any edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], except Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) or [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> <span data-ttu-id="b55b7-116">Ces éditions ne peuvent pas constituer des serveurs de publication de réplication.</span><span class="sxs-lookup"><span data-stu-id="b55b7-116">These editions cannot be replication Publishers.</span></span>  
  
    -   [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] <span data-ttu-id="b55b7-117">: exemple de base de données.</span><span class="sxs-lookup"><span data-stu-id="b55b7-117">sample database.</span></span> <span data-ttu-id="b55b7-118">Pour des raisons de sécurité, les exemples de bases de données ne sont pas installés par défaut.</span><span class="sxs-lookup"><span data-stu-id="b55b7-118">To enhance security, the sample databases are not installed by default.</span></span>  
  
-   <span data-ttu-id="b55b7-119">Serveur de l'Abonné (destination) :</span><span class="sxs-lookup"><span data-stu-id="b55b7-119">Subscriber server (destination):</span></span>  
  
    -   <span data-ttu-id="b55b7-120">Toute édition de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], sauf [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b55b7-120">Any edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], except [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> [!INCLUDE[ssEW](../../includes/ssew-md.md)] <span data-ttu-id="b55b7-121">ne peut pas être un abonné dans une réplication transactionnelle.</span><span class="sxs-lookup"><span data-stu-id="b55b7-121">cannot be a Subscriber in transactional replication.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b55b7-122">La réplication n'est pas installée par défaut dans [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b55b7-122">Replication is not installed on [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b55b7-123">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , vous devez vous connecter au serveur de publication et à l’abonné à l’aide d’une connexion qui est membre du rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="b55b7-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you must connect to the Publisher and Subscriber using a login that is a member of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="b55b7-124">**Durée estimée pour effectuer ce didacticiel : 30 minutes.**</span><span class="sxs-lookup"><span data-stu-id="b55b7-124">**Estimated time to complete this tutorial: 30 minutes.**</span></span>  
  
## <a name="lessons-in-this-tutorial"></a><span data-ttu-id="b55b7-125">Leçons du didacticiel</span><span class="sxs-lookup"><span data-stu-id="b55b7-125">Lessons in This Tutorial</span></span>  
  
-   [<span data-ttu-id="b55b7-126">Leçon 1 : Publication de données à l’aide de la réplication transactionnelle</span><span class="sxs-lookup"><span data-stu-id="b55b7-126">Lesson 1: Publishing Data Using Transactional Replication</span></span>](lesson-1-publishing-data-using-transactional-replication.md)  
  
-   [<span data-ttu-id="b55b7-127">Leçon 2 : Création d'un abonnement à la publication transactionnelle</span><span class="sxs-lookup"><span data-stu-id="b55b7-127">Lesson 2: Creating a Subscription to the Transactional Publication</span></span>](lesson-2-creating-a-subscription-to-the-transactional-publication.md)  
  
-   [<span data-ttu-id="b55b7-128">Leçon 3 : Validation de l’abonnement et mesure de la latence</span><span class="sxs-lookup"><span data-stu-id="b55b7-128">Lesson 3: Validating the Subscription and Measuring Latency</span></span>](lesson-3-validating-the-subscription-and-measuring-latency.md)  
  
 [<span data-ttu-id="b55b7-129">Démarrer le didacticiel</span><span class="sxs-lookup"><span data-stu-id="b55b7-129">Start the Tutorial</span></span>](transactional/transactional-replication.md)  
  
## <a name="see-also"></a><span data-ttu-id="b55b7-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b55b7-130">See Also</span></span>  
 [<span data-ttu-id="b55b7-131">Concepts de programmation en matière de réplication</span><span class="sxs-lookup"><span data-stu-id="b55b7-131">Replication Programming Concepts</span></span>](concepts/replication-programming-concepts.md)  
  
  
