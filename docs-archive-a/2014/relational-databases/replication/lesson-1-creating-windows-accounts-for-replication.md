---
title: 'Leçon 1 : Création de comptes Windows pour la réplication | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
- replication [SQL Server], administering
ms.assetid: 65c3816b-47f0-448c-a4a4-ebd3e2a58820
author: rothja
ms.author: jroth
ms.openlocfilehash: 29f1008338b3ba728066ed611108477586a4c899
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601316"
---
# <a name="lesson-1-creating-windows-accounts-for-replication"></a><span data-ttu-id="a6c9b-102">Leçon 1 : Création de comptes Windows pour la réplication</span><span class="sxs-lookup"><span data-stu-id="a6c9b-102">Lesson 1: Creating Windows Accounts for Replication</span></span>
  <span data-ttu-id="a6c9b-103">Dans cette leçon, vous allez créer des comptes Windows pour exécuter les agents de réplication.</span><span class="sxs-lookup"><span data-stu-id="a6c9b-103">In this lesson, you will create Windows accounts to run replication agents.</span></span> <span data-ttu-id="a6c9b-104">Vous allez créer un compte Windows distinct sur le serveur local pour les agents suivants :</span><span class="sxs-lookup"><span data-stu-id="a6c9b-104">You will create a separate Windows account on the local server for the following agents:</span></span>  
  
|<span data-ttu-id="a6c9b-105">Agent</span><span class="sxs-lookup"><span data-stu-id="a6c9b-105">Agent</span></span>|<span data-ttu-id="a6c9b-106">Emplacement</span><span class="sxs-lookup"><span data-stu-id="a6c9b-106">Location</span></span>|<span data-ttu-id="a6c9b-107">Nom du compte</span><span class="sxs-lookup"><span data-stu-id="a6c9b-107">Account name</span></span>|  
|-----------|--------------|------------------|  
|<span data-ttu-id="a6c9b-108">Agent d'instantané</span><span class="sxs-lookup"><span data-stu-id="a6c9b-108">Snapshot Agent</span></span>|<span data-ttu-id="a6c9b-109">Publisher</span><span class="sxs-lookup"><span data-stu-id="a6c9b-109">Publisher</span></span>|<span data-ttu-id="a6c9b-110">\<*machine_name*>\ repl_snapshot</span><span class="sxs-lookup"><span data-stu-id="a6c9b-110">\<*machine_name*>\repl_snapshot</span></span>|  
|<span data-ttu-id="a6c9b-111">l'Agent de lecture du journal ;</span><span class="sxs-lookup"><span data-stu-id="a6c9b-111">Log Reader Agent</span></span>|<span data-ttu-id="a6c9b-112">Publisher</span><span class="sxs-lookup"><span data-stu-id="a6c9b-112">Publisher</span></span>|<span data-ttu-id="a6c9b-113">\<*machine_name*>\ repl_logreader</span><span class="sxs-lookup"><span data-stu-id="a6c9b-113">\<*machine_name*>\repl_logreader</span></span>|  
|<span data-ttu-id="a6c9b-114">Agent de distribution</span><span class="sxs-lookup"><span data-stu-id="a6c9b-114">Distribution Agent</span></span>|<span data-ttu-id="a6c9b-115">Serveur de publication et Abonné</span><span class="sxs-lookup"><span data-stu-id="a6c9b-115">Publisher and Subscriber</span></span>|<span data-ttu-id="a6c9b-116">\<*machine_name*>\ repl_distribution</span><span class="sxs-lookup"><span data-stu-id="a6c9b-116">\<*machine_name*>\repl_distribution</span></span>|  
|<span data-ttu-id="a6c9b-117">Agent de fusion</span><span class="sxs-lookup"><span data-stu-id="a6c9b-117">Merge Agent</span></span>|<span data-ttu-id="a6c9b-118">Serveur de publication et Abonné</span><span class="sxs-lookup"><span data-stu-id="a6c9b-118">Publisher and Subscriber</span></span>|<span data-ttu-id="a6c9b-119">\<*machine_name*>\ repl_merge</span><span class="sxs-lookup"><span data-stu-id="a6c9b-119">\<*machine_name*>\repl_merge</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="a6c9b-120">Dans les didacticiels de réplication, le serveur de publication et le serveur de distribution partagent la même instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6c9b-120">In the replication tutorials, the Publisher and Distributor share the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a6c9b-121">Le serveur de publication et l'Abonné peuvent partager la même instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], mais ce n'est pas une obligation.</span><span class="sxs-lookup"><span data-stu-id="a6c9b-121">The Publisher and Subscriber may share the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], but it is not a requirement.</span></span> <span data-ttu-id="a6c9b-122">Si le serveur de publication et l'Abonné partagent la même instance, les étapes de création de comptes pour l'Abonné ne sont pas requises.</span><span class="sxs-lookup"><span data-stu-id="a6c9b-122">If the Publisher and Subscriber share the same instance, the steps that are used to create accounts at the Subscriber are not required.</span></span>  
  
### <a name="to-create-local-windows-accounts-for-replication-agents-at-the-publisher"></a><span data-ttu-id="a6c9b-123">Pour créer des comptes Windows locaux pour les agents de réplication sur le serveur de publication</span><span class="sxs-lookup"><span data-stu-id="a6c9b-123">To create local Windows accounts for replication agents at the Publisher</span></span>  
  
1.  <span data-ttu-id="a6c9b-124">Sur le serveur de publication, ouvrez gestion de l' **ordinateur** à partir des **Outils d’administration** dans le panneau de configuration.</span><span class="sxs-lookup"><span data-stu-id="a6c9b-124">At the Publisher, open **Computer Management** from **Administrative Tools** in Control Panel.</span></span>  
  
2.  <span data-ttu-id="a6c9b-125">Dans **Outils système**, développez **Utilisateurs et groupes locaux**.</span><span class="sxs-lookup"><span data-stu-id="a6c9b-125">In **System Tools**, expand **Local Users and Groups**.</span></span>  
  
3.  <span data-ttu-id="a6c9b-126">Cliquez avec le bouton droit sur **utilisateurs** , puis cliquez sur **nouvel utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="a6c9b-126">Right-click **Users** and then click **New User**.</span></span>  
  
4.  <span data-ttu-id="a6c9b-127">Entrez `repl_snapshot` dans la zone **nom d’utilisateur** , fournissez le mot de passe et d’autres informations pertinentes, puis cliquez sur **créer** pour créer le compte repl_snapshot.</span><span class="sxs-lookup"><span data-stu-id="a6c9b-127">Enter `repl_snapshot` in the **User name** box, provide the password and other relevant information, and then click **Create** to create the repl_snapshot account.</span></span>  
  
5.  <span data-ttu-id="a6c9b-128">Répétez l'étape précédente pour créer les comptes repl_logreader, repl_distribution et repl_merge.</span><span class="sxs-lookup"><span data-stu-id="a6c9b-128">Repeat the previous step to create the repl_logreader, repl_distribution, and repl_merge accounts.</span></span>  
  
6.  <span data-ttu-id="a6c9b-129">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="a6c9b-129">Click **Close**.</span></span>  
  
### <a name="to-create-local-windows-accounts-for-replication-agents-at-the-subscriber"></a><span data-ttu-id="a6c9b-130">Pour créer des comptes Windows locaux pour les agents de réplication sur l'Abonné</span><span class="sxs-lookup"><span data-stu-id="a6c9b-130">To create local Windows accounts for replication agents at the Subscriber</span></span>  
  
1.  <span data-ttu-id="a6c9b-131">Sur l’abonné, ouvrez **gestion** de l’ordinateur à partir des **Outils d’administration** dans le panneau de configuration.</span><span class="sxs-lookup"><span data-stu-id="a6c9b-131">At the Subscriber, open **Computer Management** from **Administrative Tools** in Control Panel.</span></span>  
  
2.  <span data-ttu-id="a6c9b-132">Dans **Outils système**, développez **Utilisateurs et groupes locaux**.</span><span class="sxs-lookup"><span data-stu-id="a6c9b-132">In **System Tools**, expand **Local Users and Groups**.</span></span>  
  
3.  <span data-ttu-id="a6c9b-133">Cliquez avec le bouton droit sur **utilisateurs** , puis cliquez sur **nouvel utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="a6c9b-133">Right-click **Users** and then click **New User**.</span></span>  
  
4.  <span data-ttu-id="a6c9b-134">Entrez `repl_distribution` dans la zone **nom d’utilisateur** , fournissez le mot de passe et d’autres informations pertinentes, puis cliquez sur **créer** pour créer le compte repl_distribution.</span><span class="sxs-lookup"><span data-stu-id="a6c9b-134">Enter `repl_distribution` in the **User name** box, provide the password and other relevant information, and then click **Create** to create the repl_distribution account.</span></span>  
  
5.  <span data-ttu-id="a6c9b-135">Répétez l'étape précédente pour créer le compte repl_merge.</span><span class="sxs-lookup"><span data-stu-id="a6c9b-135">Repeat the previous step to create the repl_merge account.</span></span>  
  
6.  <span data-ttu-id="a6c9b-136">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="a6c9b-136">Click **Close**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a6c9b-137">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="a6c9b-137">Next Steps</span></span>  
 <span data-ttu-id="a6c9b-138">Vous avez créé avec succès les comptes Windows des agents de réplication.</span><span class="sxs-lookup"><span data-stu-id="a6c9b-138">You have successfully created Windows accounts for replication agents.</span></span> <span data-ttu-id="a6c9b-139">Ensuite, vous allez configurer le dossier d'instantanés.</span><span class="sxs-lookup"><span data-stu-id="a6c9b-139">Next, you will configure the snapshot folder.</span></span> <span data-ttu-id="a6c9b-140">Voir [Leçon 2 : Préparation du dossier d’instantanés](lesson-2-preparing-the-snapshot-folder.md).</span><span class="sxs-lookup"><span data-stu-id="a6c9b-140">See [Lesson 2: Preparing the Snapshot Folder](lesson-2-preparing-the-snapshot-folder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6c9b-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a6c9b-141">See Also</span></span>  
 [<span data-ttu-id="a6c9b-142">Présentation des Agents de réplication</span><span class="sxs-lookup"><span data-stu-id="a6c9b-142">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
