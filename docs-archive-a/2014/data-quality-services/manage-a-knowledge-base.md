---
title: Gérer une base de connaissances | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 27f306f4-d67c-47f5-b35c-4260cc5d36e3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cc5fdd87ddb3ea687db10a29d7001564fd8ff107
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613641"
---
# <a name="manage-a-knowledge-base"></a><span data-ttu-id="1ae69-102">Gérer une base de connaissances</span><span class="sxs-lookup"><span data-stu-id="1ae69-102">Manage a Knowledge Base</span></span>
  <span data-ttu-id="1ae69-103">Cette rubrique décrit comment remplir les fonctions de gestion sur une base de connaissances dans [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="1ae69-103">This topic describes how to perform management functions on a knowledge base in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="1ae69-104">Vous pouvez supprimer une base de connaissances, la déverrouiller, ignorer vos modifications, la renommer et afficher ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="1ae69-104">You can delete a knowledge base, unlock it, discard your work on it, rename it, and display its properties.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1ae69-105">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="1ae69-105">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="1ae69-106">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="1ae69-106">Prerequisites</span></span>  
 <span data-ttu-id="1ae69-107">Pour gérer une base de connaissances, la base de connaissances doit avoir été déjà créée, et publiée (si une autre personne l'a créée) ou fermée (si vous l'avez créée).</span><span class="sxs-lookup"><span data-stu-id="1ae69-107">To manage a knowledge base, the knowledge base must have already been created, and either published (if another person created it) or have been closed (if you created it).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1ae69-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="1ae69-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1ae69-109">Autorisations</span><span class="sxs-lookup"><span data-stu-id="1ae69-109">Permissions</span></span>  
 <span data-ttu-id="1ae69-110">Vous devez disposer du rôle dqs_kb_editor ou dqs_administrator sur la base de données DQS_MAIN pour ouvrir une base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="1ae69-110">You must have the dqs_kb_editor role or the dqs_administrator on the DQS_MAIN database to open a knowledge base.</span></span>  
  
##  <a name="manage-a-knowledge-base"></a><a name="Manage"></a><span data-ttu-id="1ae69-111">Gérer une base de connaissances</span><span class="sxs-lookup"><span data-stu-id="1ae69-111">Manage a Knowledge Base</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="1ae69-112">[Exécutez l’Application Data Quality client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="1ae69-112">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="1ae69-113">Dans l'écran d'accueil de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , cliquez sur **Ouvrir une base de connaissances**.</span><span class="sxs-lookup"><span data-stu-id="1ae69-113">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open knowledge base**.</span></span>  
  
3.  <span data-ttu-id="1ae69-114">Cliquez avec le bouton droit sur une base de connaissances dans la table des bases de connaissances.</span><span class="sxs-lookup"><span data-stu-id="1ae69-114">Right-click a knowledge base in the knowledge base table.</span></span>  
  
4.  <span data-ttu-id="1ae69-115">Dans le menu contextuel, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="1ae69-115">In the context menu, you can do the following:</span></span>  
  
    1.  <span data-ttu-id="1ae69-116">**Ouvrir**: cliquez pour ouvrir la base de connaissances dans l'activité sélectionnée dans le volet **Sélectionner une activité** .</span><span class="sxs-lookup"><span data-stu-id="1ae69-116">**Open**: Click to open the knowledge base in the activity selected in the **Select Activity** pane.</span></span>  
  
    2.  <span data-ttu-id="1ae69-117">**Déverrouiller**: vous pouvez déverrouiller la base de connaissances si vous êtes l'utilisateur qui travaillait sur la base de connaissances lors de l'une des étapes de la gestion des domaines, de la découverte des connaissances et de l'activité de la stratégie de correspondance, et l'avait fermée.</span><span class="sxs-lookup"><span data-stu-id="1ae69-117">**Unlock**: You can unlock the knowledge base if you are the user who was working on the knowledge base in one of the steps of domain management, knowledge discovery, and the matching policy activity, and closed it.</span></span> <span data-ttu-id="1ae69-118">Si vous déchargez la base de connaissances, une autre personne peut l'ouvrir et travailler dessus.</span><span class="sxs-lookup"><span data-stu-id="1ae69-118">If you unload the knowledge base, another person will be able to open it and work on it.</span></span> <span data-ttu-id="1ae69-119">Cette commande n'est pas disponible si la base de connaissances n'est pas dans un état d'une activité.</span><span class="sxs-lookup"><span data-stu-id="1ae69-119">This command is not available if the knowledge base is not in a state of an activity.</span></span> <span data-ttu-id="1ae69-120">Pour plus d'informations, consultez [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="1ae69-120">For more information, see [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span></span>  
  
    3.  <span data-ttu-id="1ae69-121">**Ignorer le travail**: cliquez sur cette option lorsque la base de connaissances est dans un état de travail, comme illustré avec une entrée dans le champ État de la table.</span><span class="sxs-lookup"><span data-stu-id="1ae69-121">**Discard work**: Click when the knowledge base is in a state of being worked on, as shown with an entry in the State field in the table.</span></span> <span data-ttu-id="1ae69-122">Cette commande n'est pas disponible si la base de connaissances n'est pas dans un état d'une activité ou si la base de connaissances est verrouillée.</span><span class="sxs-lookup"><span data-stu-id="1ae69-122">This command is not available if the knowledge base is not in a state of an activity, and it is not available if the knowledge base is locked.</span></span> <span data-ttu-id="1ae69-123">Pour plus d'informations, consultez [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="1ae69-123">For more information, see [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span></span>  
  
    4.  <span data-ttu-id="1ae69-124">**Renommer**: cliquez sur cette option pour que le champ Base de connaissances de la table puisse être modifié pour la base de connaissances sur laquelle vous avez cliqué avec le bouton droit.</span><span class="sxs-lookup"><span data-stu-id="1ae69-124">**Rename**: Click to make the Knowledge Base field of the table editable for the knowledge base that you right-clicked on.</span></span> <span data-ttu-id="1ae69-125">Modifiez le nom, puis cliquez sur cette base de connaissances et sur une autre dans le champ pour accepter le changement de nom.</span><span class="sxs-lookup"><span data-stu-id="1ae69-125">Change the name, and then click on that knowledge base and another one in the field to accept the name change.</span></span>  
  
    5.  <span data-ttu-id="1ae69-126">**Supprimer**: cliquez sur cette option pour supprimer la base de connaissances de la base de données DQS_MAIN sur [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ae69-126">**Delete**: Click to remove the knowledge base from the DQS_MAIN database on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
    6.  <span data-ttu-id="1ae69-127">**Propriétés**: cliquez sur cette option pour afficher les propriétés de la base de données en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="1ae69-127">**Properties**: Click to display properties for the database in a read-only display.</span></span>  
  
        1.  <span data-ttu-id="1ae69-128">**Base de connaissances source**: base de connaissances sur laquelle cette base de données était fondée.</span><span class="sxs-lookup"><span data-stu-id="1ae69-128">**Source Knowledge Base**: the knowledge base that this database was based on.</span></span> <span data-ttu-id="1ae69-129">Ce paramètre est facultatif.</span><span class="sxs-lookup"><span data-stu-id="1ae69-129">This is optional.</span></span>  
  
        2.  <span data-ttu-id="1ae69-130">**État**: indique si la base de connaissances est **En cours** et si elle est dans une activité spécifique de gestion des connaissances, comme déterminé lors de la dernière fermeture.</span><span class="sxs-lookup"><span data-stu-id="1ae69-130">**State**: Indicates if the knowledge base is **In Work** and if it is in a specific knowledge management activity, as determined when it was last closed.</span></span> <span data-ttu-id="1ae69-131">L'état peut être **En cours**, à savoir que la base de connaissances est ouverte dans une session de gestion des connaissances, mais pas dans une activité spécifique, ou **En cours** plus une activité de gestion des connaissances, dans laquelle la base de connaissances est ouverte dans une session de gestion des connaissances, et dans une activité spécifique.</span><span class="sxs-lookup"><span data-stu-id="1ae69-131">The state can be **In Work**, in which the knowledge base is opened in a knowledge management session, but not in a specific activity, or **In Work** plus a knowledge management activity, in which the knowledge base is opened in a knowledge management session, and in a specific activity.</span></span>  
  
        3.  <span data-ttu-id="1ae69-132">**Est verrouillé**: **True** si la base de connaissances a été verrouillée, **FALSE** dans le cas contraire</span><span class="sxs-lookup"><span data-stu-id="1ae69-132">**Is Locked**: **True** if the knowledge base was locked, **False** if not</span></span>  
  
        4.  <span data-ttu-id="1ae69-133">**Contenu non publié**: True si la base de connaissances contient un contenu qui n'a pas été enregistré par publication, False dans le cas contraire</span><span class="sxs-lookup"><span data-stu-id="1ae69-133">**Contains unpublished content**: True if the knowledge base contains content that has not been saved by publishing, False if not</span></span>  
  
        5.  <span data-ttu-id="1ae69-134">**Verrouillé par**: nom de l'utilisateur qui a fermé la base de connaissances et l'a verrouillée</span><span class="sxs-lookup"><span data-stu-id="1ae69-134">**Locked By**: the name of the user who closed the knowledge base, locking it</span></span>  
  
        6.  <span data-ttu-id="1ae69-135">**Verrouillé le**: date du verrouillage</span><span class="sxs-lookup"><span data-stu-id="1ae69-135">**Locked Date**: date when locked</span></span>  
  
        7.  <span data-ttu-id="1ae69-136">**Créé par**: nom de l'utilisateur qui a créé la base de connaissances, avec le réseau auquel il appartient</span><span class="sxs-lookup"><span data-stu-id="1ae69-136">**Created By**: the name of the user who created the knowledge base, with the network that he or she belongs to</span></span>  
  
        8.  <span data-ttu-id="1ae69-137">**Date de création**: date lors de la création</span><span class="sxs-lookup"><span data-stu-id="1ae69-137">**Created Date**: date when created</span></span>  
  
##  <a name="follow-up-after-managing-a-knowledge-base"></a><a name="FollowUp"></a> <span data-ttu-id="1ae69-138">Suivi : après la gestion d'une base de connaissances</span><span class="sxs-lookup"><span data-stu-id="1ae69-138">Follow Up: After Managing a Knowledge Base</span></span>  
 <span data-ttu-id="1ae69-139">Après que vous avez géré une base de connaissances, l'étape suivante varie selon l'action effectuée sur la base de connaissances :</span><span class="sxs-lookup"><span data-stu-id="1ae69-139">After you manage a knowledge base, your next step depends upon the action you took on the knowledge base:</span></span>  
  
-   <span data-ttu-id="1ae69-140">Si vous avez ouvert la base de connaissances, vous continuerez dans l'activité que vous avez sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1ae69-140">If you opened the knowledge base, you will continue in the activity that you selected.</span></span>  
  
-   <span data-ttu-id="1ae69-141">Si vous l'avez déverrouillée, elle est disponible pour qu'une autre personne l'ouvre et travaille dessus, dans l'état indiqué.</span><span class="sxs-lookup"><span data-stu-id="1ae69-141">If you unlocked it, it will be available for another person to open and work on, in the state indicated.</span></span>  
  
-   <span data-ttu-id="1ae69-142">Si vous aviez ignoré le travail sur la base de connaissances, celle-ci sera disponible dans son dernier état publié.</span><span class="sxs-lookup"><span data-stu-id="1ae69-142">If you discarded the work on it, the knowledge base will be available in its last published state.</span></span>  
  
-   <span data-ttu-id="1ae69-143">Si vous l'avez renommée, vous devez ouvrir la base de connaissances renommée pour travailler dessus.</span><span class="sxs-lookup"><span data-stu-id="1ae69-143">If you renamed it, you will have to open the renamed knowledge base to work on it.</span></span>  
  
-   <span data-ttu-id="1ae69-144">Si vous la supprimez, vous devrez sélectionner une autre base de connaissances sur laquelle travailler ou en créez une nouvelle.</span><span class="sxs-lookup"><span data-stu-id="1ae69-144">If you delete it, you will have to select another knowledge base to work on, or create a new one.</span></span>  
  
  
