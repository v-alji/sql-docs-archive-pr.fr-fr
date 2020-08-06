---
title: 'Leçon 1 : Publication de données à l’aide de la réplication transactionnelle | Microsoft Docs'
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 9c55aa3c-4664-41fc-943f-e817c31aad5e
author: rothja
ms.author: jroth
ms.openlocfilehash: ce20f4ed8863ede34c8709d2b77bf032e7d14a97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696712"
---
# <a name="lesson-1-publishing-data-using-transactional-replication"></a><span data-ttu-id="a8e7c-102">Leçon 1 : publication de données à l'aide de la réplication transactionnelle</span><span class="sxs-lookup"><span data-stu-id="a8e7c-102">Lesson 1: Publishing Data Using Transactional Replication</span></span>
  <span data-ttu-id="a8e7c-103"> Dans cette leçon, vous créez une publication transactionnelle en utilisant [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour publier un sous-ensemble filtré de la table **Product** de l’exemple de base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8e7c-103">In this lesson, you will create a transactional publication using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to publish a filtered subset of the **Product** table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="a8e7c-104">Vous allez aussi ajouter à la liste d'accès à la publication le compte de connexion SQL Server utilisée par l'Agent de distribution.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-104">You will also add the SQL Server login used by the Distribution Agent to the publication access list (PAL).</span></span> <span data-ttu-id="a8e7c-105">Avant de commencer ce didacticiel, vous devez avoir terminé le didacticiel précédent, [Préparation du serveur à la réplication](tutorial-preparing-the-server-for-replication.md).</span><span class="sxs-lookup"><span data-stu-id="a8e7c-105">Before starting this tutorial, you should have completed the previous tutorial, [Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
### <a name="to-create-a-publication-and-define-articles"></a><span data-ttu-id="a8e7c-106">Pour créer une publication et définir des articles</span><span class="sxs-lookup"><span data-stu-id="a8e7c-106">To create a publication and define articles</span></span>  
  
1.  <span data-ttu-id="a8e7c-107">Connectez-vous au serveur de publication dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-107">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="a8e7c-108">Développez le dossier **Réplication** , cliquez avec le bouton droit sur le dossier **Publications locales** , puis cliquez sur **Nouvelle publication**.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-108">Expand the **Replication** folder, right-click the **Local Publications** folder, and click **New Publication**.</span></span>  
  
     <span data-ttu-id="a8e7c-109">L'Assistant Configuration de la publication démarre.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-109">The Publication Configuration Wizard launches.</span></span>  
  
3.  <span data-ttu-id="a8e7c-110">Dans la page Base de données de publication, sélectionnez [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-110">On the Publication Database page, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="a8e7c-111">Dans la page Type de publication, sélectionnez **Publication transactionnelle**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-111">On the Publication Type page, select **Transactional publication**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="a8e7c-112">Dans la page Articles, développez le nœud **Tables** , cochez la case **Product** , puis développez **Product** et décochez les cases **ListPrice** et **StandardCost** .</span><span class="sxs-lookup"><span data-stu-id="a8e7c-112">On the Articles page, expand the **Tables** node, select the **Product** check box, then expand **Product** and clear the **ListPrice** and **StandardCost** check boxes.</span></span> <span data-ttu-id="a8e7c-113">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-113">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="a8e7c-114">Dans la page Filtrer les lignes de la table, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-114">On the Filter Table Rows page, click **Add**.</span></span>  
  
7.  <span data-ttu-id="a8e7c-115">Dans la boîte de dialogue **Ajouter un filtre** , cliquez sur la colonne **SafetyStockLevel** , cliquez sur la flèche droite pour ajouter la colonne à la clause WHERE de la requête de filtre et modifiez la clause WHERE comme suit :</span><span class="sxs-lookup"><span data-stu-id="a8e7c-115">In the **Add Filter** dialog box, click the **SafetyStockLevel** column, click the right arrow to add the column to the Filter statement WHERE clause of the filter query, and modify the WHERE clause as follows:</span></span>  
  
    ```  
    WHERE [SafetyStockLevel] < 500  
    ```  
  
8.  <span data-ttu-id="a8e7c-116">Cliquez sur **OK**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-116">Click **OK**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="a8e7c-117">Cochez la case **Créer un instantané immédiatement et garder ce dernier disponible pour l’initialisation des abonnements** et cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-117">Select the **Create a snapshot immediately and keep the snapshot available to initialize subscriptions** check box, and click **Next**.</span></span>  
  
10. <span data-ttu-id="a8e7c-118">Dans la page Sécurité de l’agent, décochez la case **Utiliser les paramètres de sécurité de l’Agent d’instantané** .</span><span class="sxs-lookup"><span data-stu-id="a8e7c-118">On the Agent Security page, clear **Use the security settings from the Snapshot Agent** check box.</span></span>  
  
11. <span data-ttu-id="a8e7c-119">Cliquez sur **paramètres de sécurité** pour la agent d’instantané, entrez \<_Machine_Name> _**\ repl_snapshot** dans la zone **compte de processus** , fournissez le mot de passe de ce compte, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-119">Click **Security Settings** for the Snapshot Agent, enter \<_Machine_Name>_**\repl_snapshot** in the **Process account** box, supply the password for this account, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="a8e7c-120">Répétez l’étape précédente pour définir repl_logreader comme compte de processus de l’Agent de lecture du journal, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-120">Repeat the previous step to set repl_logreader as the process account for the Log Reader Agent, and then click **Finish**.</span></span>  
  
13. <span data-ttu-id="a8e7c-121">Dans la page Terminer l’Assistant, entrez **AdvWorksProductTrans** dans la zone **Nom de la publication** , puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-121">On the Complete the Wizard page, type **AdvWorksProductTrans** in the **Publication name** box, and click **Finish**.</span></span>  
  
14. <span data-ttu-id="a8e7c-122">Une fois la publication créée, cliquez sur **Fermer** pour terminer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-122">After the publication is created, click **Close** to complete the wizard.</span></span>  
  
### <a name="to-view-the-status-of-snapshot-generation"></a><span data-ttu-id="a8e7c-123">Pour afficher l'état d'une génération d'instantané</span><span class="sxs-lookup"><span data-stu-id="a8e7c-123">To view the status of snapshot generation</span></span>  
  
1.  <span data-ttu-id="a8e7c-124">Connectez-vous au serveur de publication dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], développez le nœud du serveur, puis le dossier **Réplication** .</span><span class="sxs-lookup"><span data-stu-id="a8e7c-124">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="a8e7c-125">Dans le dossier **Publications locales** , cliquez avec le bouton droit sur **AdvWorksProductTrans**, puis cliquez sur **Afficher l’état de l’Agent d’instantané**.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-125">In the **Local Publications** folder, right-click **AdvWorksProductTrans**, and then click **View Snapshot Agent Status**.</span></span>  
  
3.  <span data-ttu-id="a8e7c-126">L'état en cours du travail de l'Agent d'instantané pour la publication s'affiche.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-126">The current status of the Snapshot Agent job for the publication is displayed.</span></span> <span data-ttu-id="a8e7c-127">Vérifiez que le travail d'instantané a bien réussi avant de passer à la leçon suivante.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-127">Verify that the snapshot job has succeeded before you continue to the next lesson.</span></span>  
  
### <a name="to-add-the-distribution-agent-login-to-the-pal"></a><span data-ttu-id="a8e7c-128">Pour ajouter la connexion de l'Agent de distribution à la liste d'accès à la publication</span><span class="sxs-lookup"><span data-stu-id="a8e7c-128">To add the Distribution Agent login to the PAL</span></span>  
  
1.  <span data-ttu-id="a8e7c-129">Connectez-vous au serveur de publication dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], développez le nœud du serveur, puis le dossier **Réplication** .</span><span class="sxs-lookup"><span data-stu-id="a8e7c-129">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="a8e7c-130">Dans le dossier **Publications locales** , cliquez avec le bouton droit sur **AdvWorksProductTrans**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-130">In the **Local Publications** folder, right-click **AdvWorksProductTrans**, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="a8e7c-131">La boîte de dialogue **Propriétés de la publication** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-131">The **Publication Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="a8e7c-132">Sélectionnez la page **Liste d’accès à la publication** , puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-132">Select the **Publication Access List** page, and click **Add**.</span></span>  
  
4.  <span data-ttu-id="a8e7c-133">\Dans la boîte de dialogue **Ajouter un accès à une publication**, sélectionnez _nom_ordinateur>_**\repl_distribution** et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-133">\In the **Add Publication Access** dialog box, select _<Machine_Name>_**\repl_distribution** and click **OK**.</span></span> <span data-ttu-id="a8e7c-134">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-134">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a8e7c-135">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="a8e7c-135">Next Steps</span></span>  
 <span data-ttu-id="a8e7c-136">Vous avez créé avec succès la publication transactionnelle.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-136">You have successfully created the transactional publication.</span></span> <span data-ttu-id="a8e7c-137">Ensuite, vous allez créer l'abonnement à cette publication.</span><span class="sxs-lookup"><span data-stu-id="a8e7c-137">Next, you will subscribe to this publication.</span></span> <span data-ttu-id="a8e7c-138">Consultez [Leçon 2 : Création d’un abonnement à la publication transactionnelle](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span><span class="sxs-lookup"><span data-stu-id="a8e7c-138">See [Lesson 2: Creating a Subscription to the Transactional Publication](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8e7c-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a8e7c-139">See Also</span></span>  
 <span data-ttu-id="a8e7c-140">[Filtrer des données publiées](publish/filter-published-data.md) </span><span class="sxs-lookup"><span data-stu-id="a8e7c-140">[Filter Published Data](publish/filter-published-data.md) </span></span>  
 <span data-ttu-id="a8e7c-141">[Define an Article](publish/define-an-article.md) </span><span class="sxs-lookup"><span data-stu-id="a8e7c-141">[Define an Article](publish/define-an-article.md) </span></span>  
 [<span data-ttu-id="a8e7c-142">Créer et appliquer un instantané</span><span class="sxs-lookup"><span data-stu-id="a8e7c-142">Create and Apply the Snapshot</span></span>](create-and-apply-the-snapshot.md)  
  
  
