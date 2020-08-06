---
title: 'Didacticiel : Réplication de données avec des clients mobiles | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: af673514-30c7-403a-9d18-d01e1a095115
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2cdf8be7cb0da11f0aa1022ba656d50c10826ad2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614482"
---
# <a name="tutorial-replicating-data-with-mobile-clients"></a><span data-ttu-id="39ae0-102">Didacticiel : Réplication de données avec des clients mobiles</span><span class="sxs-lookup"><span data-stu-id="39ae0-102">Tutorial: Replicating Data with Mobile Clients</span></span>
  <span data-ttu-id="39ae0-103">La réplication constitue une bonne solution au problème de transfert des données entre un serveur central et des clients mobiles qui ne sont connectés que de façon occasionnelle.</span><span class="sxs-lookup"><span data-stu-id="39ae0-103">Replication is a good solution to the problem of moving data between a central server and mobile clients that are only occasionally connected.</span></span> <span data-ttu-id="39ae0-104">À l'aide des Assistants de réplication, vous pouvez aisément configurer et administrer une topologie de réplication.</span><span class="sxs-lookup"><span data-stu-id="39ae0-104">Using replication's wizards, you can easily configure and administer a replication topology.</span></span> <span data-ttu-id="39ae0-105">Ce didacticiel vous explique comment configurer une topologie de réplication pour des clients mobiles.</span><span class="sxs-lookup"><span data-stu-id="39ae0-105">This tutorial shows you how to configure a replication topology for mobile clients.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="39ae0-106">Contenu du didacticiel</span><span class="sxs-lookup"><span data-stu-id="39ae0-106">What You Will Learn</span></span>  
 <span data-ttu-id="39ae0-107">Dans ce didacticiel, vous allez utiliser la réplication de fusion pour publier des données à partir d'une base de données centrale vers un ou plusieurs utilisateurs mobiles afin que chaque utilisateur obtienne un sous-ensemble des données filtré de façon unique.</span><span class="sxs-lookup"><span data-stu-id="39ae0-107">In this tutorial you will use merge replication to publish data from a central database to one or more mobile users so that each user gets a uniquely filtered subset of the data.</span></span> <span data-ttu-id="39ae0-108">La première leçon montre comment utiliser [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour créer une publication.</span><span class="sxs-lookup"><span data-stu-id="39ae0-108">The first lesson shows how to use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create a publication.</span></span> <span data-ttu-id="39ae0-109">Les leçons suivantes expliquent comment créer et synchroniser un abonnement.</span><span class="sxs-lookup"><span data-stu-id="39ae0-109">Later lessons show how to create and synchronize a subscription.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39ae0-110">Spécifications</span><span class="sxs-lookup"><span data-stu-id="39ae0-110">Requirements</span></span>  
 <span data-ttu-id="39ae0-111">Ce didacticiel est destiné aux utilisateurs qui sont familiers des opérations essentielles de base de données, mais dont l'expérience en matière de réplication est limitée.</span><span class="sxs-lookup"><span data-stu-id="39ae0-111">This tutorial is intended for users familiar with fundamental database operations, but who have limited experience with replication.</span></span> <span data-ttu-id="39ae0-112">Avant de commencer ce didacticiel, vous devez effectuer le [Didacticiel : Préparation du serveur à la réplication](tutorial-preparing-the-server-for-replication.md).</span><span class="sxs-lookup"><span data-stu-id="39ae0-112">Before you start this tutorial, you must complete [Tutorial: Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
 <span data-ttu-id="39ae0-113">Pour utiliser ce didacticiel, les composants suivants doivent être installés sur votre système :</span><span class="sxs-lookup"><span data-stu-id="39ae0-113">To use this tutorial, your system must have the following components installed:</span></span>  
  
-   <span data-ttu-id="39ae0-114">Sur le serveur de publication (source)</span><span class="sxs-lookup"><span data-stu-id="39ae0-114">At the Publisher server (source):</span></span>  
  
    -   <span data-ttu-id="39ae0-115">Toute édition de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]sauf Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) ou [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39ae0-115">Any edition of [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], except for Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) or [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> <span data-ttu-id="39ae0-116">Ces éditions ne peuvent pas constituer un serveur de publication de réplication.</span><span class="sxs-lookup"><span data-stu-id="39ae0-116">These editions cannot be a replication Publisher.</span></span>  
  
    -   <span data-ttu-id="39ae0-117">Exemple de base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39ae0-117">The [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="39ae0-118">Pour des raisons de sécurité, les exemples de bases de données ne sont pas installés par défaut.</span><span class="sxs-lookup"><span data-stu-id="39ae0-118">To enhance security, the sample databases are not installed by default.</span></span>  
  
-   <span data-ttu-id="39ae0-119">Serveur de l'Abonné (destination) :</span><span class="sxs-lookup"><span data-stu-id="39ae0-119">Subscriber server (destination):</span></span>  
  
    -   <span data-ttu-id="39ae0-120">Toute édition de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], sauf [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39ae0-120">Any edition of [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], except for [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> [!INCLUDE[ssEW](../../includes/ssew-md.md)] <span data-ttu-id="39ae0-121">n'est pas pris en charge par la publication créée dans ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="39ae0-121">is not supported by the publication created in this tutorial.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="39ae0-122">La réplication n’est pas installée par défaut dans [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39ae0-122">Replication is not installed by default on [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="39ae0-123">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], vous devez vous connecter au serveur de publication et à l'Abonné à l'aide d'un identifiant de connexion membre du rôle serveur fixe sysadmin.</span><span class="sxs-lookup"><span data-stu-id="39ae0-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you must connect to the Publisher and Subscriber using a login that is a member of the sysadmin fixed server role.</span></span>  
  
 <span data-ttu-id="39ae0-124">**Durée estimée pour effectuer ce didacticiel : 30 minutes.**</span><span class="sxs-lookup"><span data-stu-id="39ae0-124">**Estimated time to complete this tutorial: 30 minutes.**</span></span>  
  
## <a name="lessons-in-this-tutorial"></a><span data-ttu-id="39ae0-125">Leçons du didacticiel</span><span class="sxs-lookup"><span data-stu-id="39ae0-125">Lessons in This Tutorial</span></span>  
  
-   [<span data-ttu-id="39ae0-126">Leçon 1 : Publication de données à l’aide de la réplication de fusion</span><span class="sxs-lookup"><span data-stu-id="39ae0-126">Lesson 1: Publishing Data Using Merge Replication</span></span>](lesson-1-publishing-data-using-merge-replication.md)  
  
-   [<span data-ttu-id="39ae0-127">Leçon 2 : Création d’un abonnement à la publication de fusion</span><span class="sxs-lookup"><span data-stu-id="39ae0-127">Lesson 2: Creating a Subscription to the Merge Publication</span></span>](lesson-2-creating-a-subscription-to-the-merge-publication.md)  
  
 [<span data-ttu-id="39ae0-128">Démarrer le didacticiel</span><span class="sxs-lookup"><span data-stu-id="39ae0-128">Start the Tutorial</span></span>](merge/merge-replication.md)  
  
## <a name="see-also"></a><span data-ttu-id="39ae0-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="39ae0-129">See Also</span></span>  
 [<span data-ttu-id="39ae0-130">Concepts de programmation en matière de réplication</span><span class="sxs-lookup"><span data-stu-id="39ae0-130">Replication Programming Concepts</span></span>](concepts/replication-programming-concepts.md)  
  
  
