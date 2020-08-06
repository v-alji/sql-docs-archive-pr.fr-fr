---
title: 'Didacticiel : Préparation du serveur à la réplication | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: ce30a095-2975-4387-9377-94a461ac78ee
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1f036ff2a111ee6b5f97655b9bebaf34391a436
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614486"
---
# <a name="tutorial-preparing-the-server-for-replication"></a><span data-ttu-id="e51f5-102">Didacticiel : Préparation du serveur à la réplication</span><span class="sxs-lookup"><span data-stu-id="e51f5-102">Tutorial: Preparing the Server for Replication</span></span>
  <span data-ttu-id="e51f5-103">Il importe de prévoir la sécurité avant de configurer la topologie de réplication.</span><span class="sxs-lookup"><span data-stu-id="e51f5-103">It is important to plan for security before you configure your replication topology.</span></span> <span data-ttu-id="e51f5-104">Ce didacticiel vous explique comment sécuriser au mieux une topologie de réplication et configurer la distribution, première étape de la réplication des données.</span><span class="sxs-lookup"><span data-stu-id="e51f5-104">This tutorial shows you how to better secure a replication topology as well as how to configure distribution, which is the first step in replicating data.</span></span> <span data-ttu-id="e51f5-105">Ce didacticiel doit être effectué avant les autres didacticiels.</span><span class="sxs-lookup"><span data-stu-id="e51f5-105">You must complete this tutorial before any of the others.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e51f5-106">Pour répliquer les données de façon sécurisée entre les serveurs, vous devez implémenter l’ensemble des recommandations des [Méthodes préconisées en matière de sécurité de réplication](security/replication-security-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="e51f5-106">To replicate data securely between servers, you should implement all of the recommendations in [Replication Security Best Practices](security/replication-security-best-practices.md).</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="e51f5-107">Contenu du didacticiel</span><span class="sxs-lookup"><span data-stu-id="e51f5-107">What You Will Learn</span></span>  
 <span data-ttu-id="e51f5-108">Dans ce didacticiel, vous allez apprendre à préparer un serveur afin que la réplication puisse s'exécuter de façon sécurisée avec les privilèges minimaux.</span><span class="sxs-lookup"><span data-stu-id="e51f5-108">In this tutorial you will learn how to prepare a server so that replication can run securely with least privileges.</span></span> <span data-ttu-id="e51f5-109">La première leçon explique comment créer les comptes de service Windows utilisés pour exécuter les agents de réplication.</span><span class="sxs-lookup"><span data-stu-id="e51f5-109">The first lesson shows how to create the Windows service accounts used to run replication agents.</span></span> <span data-ttu-id="e51f5-110">La deuxième leçon montre comment configurer le dossier utilisé pour générer et stocker les instantanés de publication.</span><span class="sxs-lookup"><span data-stu-id="e51f5-110">The second lesson shows how to configure the folder used to generate and store publication snapshots.</span></span> <span data-ttu-id="e51f5-111">La troisième leçon vous apprend à configurer la distribution et à définir les autorisations.</span><span class="sxs-lookup"><span data-stu-id="e51f5-111">The third lesson shows how to configure distribution and set permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e51f5-112">Spécifications</span><span class="sxs-lookup"><span data-stu-id="e51f5-112">Requirements</span></span>  
 <span data-ttu-id="e51f5-113">Ce didacticiel est destiné aux utilisateurs qui sont familiers des opérations essentielles de base de données, mais dont l'expérience en matière de réplication est limitée.</span><span class="sxs-lookup"><span data-stu-id="e51f5-113">This tutorial is intended for users familiar with fundamental database operations, but who have limited exposure to replication.</span></span>  
  
 <span data-ttu-id="e51f5-114">Pour utiliser ce didacticiel, les composants suivants doivent être installés sur votre système :</span><span class="sxs-lookup"><span data-stu-id="e51f5-114">To use this tutorial, your system must have the following components installed:</span></span>  
  
-   [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] <span data-ttu-id="e51f5-115">avec la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e51f5-115">with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="e51f5-116">Pour des raisons de sécurité, les exemples de bases de données ne sont pas installés par défaut.</span><span class="sxs-lookup"><span data-stu-id="e51f5-116">To enhance security, the sample databases are not installed by default.</span></span>  
  
 <span data-ttu-id="e51f5-117">**Durée estimée pour effectuer ce didacticiel : 30 minutes.**</span><span class="sxs-lookup"><span data-stu-id="e51f5-117">**Estimated time to complete this tutorial: 30 minutes.**</span></span>  
  
## <a name="lessons-in-this-tutorial"></a><span data-ttu-id="e51f5-118">Leçons du didacticiel</span><span class="sxs-lookup"><span data-stu-id="e51f5-118">Lessons in This Tutorial</span></span>  
  
-   [<span data-ttu-id="e51f5-119">Leçon 1 : Création de comptes Windows pour la réplication</span><span class="sxs-lookup"><span data-stu-id="e51f5-119">Lesson 1: Creating Windows Accounts for Replication</span></span>](lesson-1-creating-windows-accounts-for-replication.md)  
  
-   [<span data-ttu-id="e51f5-120">Leçon 2 : Préparation du dossier d'instantanés</span><span class="sxs-lookup"><span data-stu-id="e51f5-120">Lesson 2: Preparing the Snapshot Folder</span></span>](lesson-2-preparing-the-snapshot-folder.md)  
  
-   [<span data-ttu-id="e51f5-121">Leçon 3 : Configuration de la distribution</span><span class="sxs-lookup"><span data-stu-id="e51f5-121">Lesson 3: Configuring Distribution</span></span>](lesson-3-configuring-distribution.md)  
  
 [<span data-ttu-id="e51f5-122">Démarrer le didacticiel</span><span class="sxs-lookup"><span data-stu-id="e51f5-122">Start the Tutorial</span></span>](lesson-1-creating-windows-accounts-for-replication.md)  
  
## <a name="see-also"></a><span data-ttu-id="e51f5-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e51f5-123">See Also</span></span>  
 <span data-ttu-id="e51f5-124">[Configurer la distribution](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="e51f5-124">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="e51f5-125">Sécurité Réplication SQL Server</span><span class="sxs-lookup"><span data-stu-id="e51f5-125">SQL Server Replication Security</span></span>](security/view-and-modify-replication-security-settings.md)  
  
  
