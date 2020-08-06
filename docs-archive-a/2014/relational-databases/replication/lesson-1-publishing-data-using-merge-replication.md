---
title: 'Leçon 1 : Publication de données à l’aide de la réplication de fusion | Microsoft Docs'
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: c3c6e0b6-54cd-4b7d-8efb-2cefe14fcd7f
author: rothja
ms.author: jroth
ms.openlocfilehash: ba1d8829d84c02d1436013af80de4bf0979049e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705055"
---
# <a name="lesson-1-publishing-data-using-merge-replication"></a><span data-ttu-id="fc30b-102">Leçon 1 : publication de données à l'aide de la réplication de fusion</span><span class="sxs-lookup"><span data-stu-id="fc30b-102">Lesson 1: Publishing Data Using Merge Replication</span></span>
  <span data-ttu-id="fc30b-103">Dans cette leçon, vous créez une publication de fusion à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour publier un sous-ensemble des tables **Employee**, **SalesOrderHeader**et **SalesOrderDetail** de l’exemple de base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fc30b-103">In this lesson, you will create a merge publication using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to publish a subset of the **Employee**, **SalesOrderHeader**, and **SalesOrderDetail** tables in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="fc30b-104">Ces tables sont filtrées avec des filtres de lignes paramétrables pour que chaque abonnement contienne une partition unique des données.</span><span class="sxs-lookup"><span data-stu-id="fc30b-104">These tables are filtered with parameterized row filters so that each subscription contains a unique partition of the data.</span></span> <span data-ttu-id="fc30b-105">Vous ajoutez également la connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilisée par l’Agent de fusion à la liste d’accès à la publication.</span><span class="sxs-lookup"><span data-stu-id="fc30b-105">You will also add the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used by the Merge Agent to the publication access list (PAL).</span></span> <span data-ttu-id="fc30b-106">Pour suivre ce didacticiel, vous devez avoir terminé le didacticiel précédent, [Préparation du serveur pour la réplication](tutorial-preparing-the-server-for-replication.md).</span><span class="sxs-lookup"><span data-stu-id="fc30b-106">This tutorial requires that you have completed the previous tutorial, [Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
### <a name="to-create-a-publication-and-define-articles"></a><span data-ttu-id="fc30b-107">Pour créer une publication et définir des articles</span><span class="sxs-lookup"><span data-stu-id="fc30b-107">To create a publication and define articles</span></span>  
  
1.  <span data-ttu-id="fc30b-108">Connectez-vous au serveur de publication dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="fc30b-108">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="fc30b-109">Développez le dossier **Réplication** , cliquez avec le bouton droit sur le dossier **Publications locales**, puis cliquez sur **Nouvelle publication**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-109">Expand the **Replication** folder, right-click **Local Publications**, and click **New Publication**.</span></span>  
  
     <span data-ttu-id="fc30b-110">L'Assistant Configuration de la publication démarre.</span><span class="sxs-lookup"><span data-stu-id="fc30b-110">The Publication Configuration Wizard launches.</span></span>  
  
3.  <span data-ttu-id="fc30b-111">Dans la page Base de données de publication, sélectionnez [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-111">On the Publication Database page, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="fc30b-112">Dans la page Type de publication, sélectionnez **Publication de fusion**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-112">On the Publication Type page, select **Merge publication**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="fc30b-113">Dans la page Types d’Abonnés, vérifiez que seul [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ou version ultérieure est sélectionné, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-113">On the Subscriber Types page, ensure that only [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later is selected, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="fc30b-114">Dans la page Articles, développez le nœud **Tables** , sélectionnez **SalesOrderHeader** et **SalesOrderDetail**, puis développez **Employee**, sélectionnez **EmployeeID** ou **LoginID**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-114">On the Articles page, expand the **Tables** node, select **SalesOrderHeader** and **SalesOrderDetail**, then expand **Employee**, select **EmployeeID** or **LoginID**, and then click **Next**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="fc30b-115">Les colonnes supplémentaires requises sont sélectionnées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="fc30b-115">Additional required columns are automatically selected.</span></span> <span data-ttu-id="fc30b-116">Choisissez une des colonnes sélectionnées automatiquement et affichez la remarque sous la liste **Objets à publier** pour savoir pourquoi cette colonne est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="fc30b-116">Select any of  the automatically selected columns and view the note below the **Objects to publish** list for an explanation why the column is required.</span></span>  
  
7.  <span data-ttu-id="fc30b-117">Dans la page Filtrer les lignes de la table, cliquez sur **Ajouter** , puis sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-117">On the Filter Table Rows page, click **Add** and then click **Add Filter**.</span></span>  
  
8.  <span data-ttu-id="fc30b-118">Dans la boîte de dialogue **Ajouter un filtre** , sélectionnez **Employee (HumanResources)** dans **Sélectionnez la table à filtrer**, cliquez sur la colonne **LoginID** , cliquez sur la flèche droite pour ajouter la colonne à la clause WHERE de la requête de filtre et modifiez la clause WHERE comme suit :</span><span class="sxs-lookup"><span data-stu-id="fc30b-118">In the **Add Filter** dialog box, select **Employee (HumanResources)** in **Select the table to filter**, click the **LoginID** column, click the right arrow to add the column to the WHERE clause of the filter query, and modify the WHERE clause as follows:</span></span>  
  
    ```  
    WHERE [LoginID] = HOST_NAME()  
    ```  
  
9. <span data-ttu-id="fc30b-119">Cliquez sur **Une ligne de cette table ira à un seul abonnement**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-119">Click **A row from this table will go to only one subscription**, and click **OK**.</span></span>  
  
10. <span data-ttu-id="fc30b-120">Dans la page **Filtrer les lignes de la table** , cliquez sur **Employee (Human Resources)**, cliquez sur **Ajouter** , puis sur **Ajouter une jointure pour étendre le filtre sélectionné**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-120">On the **Filter Table Rows** page, click **Employee (Human Resources)**, click **Add,** and then click **Add Join to Extend the Selected Filter**.</span></span>  
  
11. <span data-ttu-id="fc30b-121">Dans la boîte de dialogue **Ajouter une jointure** , sélectionnez **Sales.SalesOrderHeader** sous **Table jointe**, cliquez sur **Créer manuellement l’instruction de jointure**et complétez l’instruction de jointure comme suit :</span><span class="sxs-lookup"><span data-stu-id="fc30b-121">In the **Add Join** dialog box, select **Sales.SalesOrderHeader** under **Joined table**, click **Write the join statement manually**, and complete the join statement as follows:</span></span>  
  
    ```  
    ON Employee.EmployeeID = SalesOrderHeader.SalesPersonID  
    ```  
  
12. <span data-ttu-id="fc30b-122">Dans **Spécifiez les options de jointure**, sélectionnez **Clé unique**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-122">In **Specify join options**, select **Unique key**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="fc30b-123">Dans la page Filtrer les lignes de la table, cliquez sur **SalesOrderHeader**, cliquez sur **Ajouter**, puis sur **Ajouter une jointure pour étendre le filtre sélectionné**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-123">On the Filter Table Rows page, click **SalesOrderHeader**, click **Add**, and then click **Add Join to Extend the Selected Filter**.</span></span>  
  
14. <span data-ttu-id="fc30b-124">Dans la boîte de dialogue **Ajouter une jointure** , sélectionnez **Sales.SalesOrderDetail** sous **Table jointe**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-124">In the **Add Join** dialog box, select **Sales.SalesOrderDetail** under **Joined table**.</span></span>  
  
15. <span data-ttu-id="fc30b-125">Cliquez sur **Créer manuellement l’instruction de jointure**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-125">Click **Write the join statement manually**.</span></span>  
  
16. <span data-ttu-id="fc30b-126">Dans **Colonnes de table filtrée**, sélectionnez **BusinessEntityID**, puis cliquez sur le bouton Flèche pour copier le nom de colonne dans l’instruction de jointure.</span><span class="sxs-lookup"><span data-stu-id="fc30b-126">In **Filtered table columns**, select **BusinessEntityID**, then click the arrow button to copy the column name to the loin statement.</span></span>  
  
17. <span data-ttu-id="fc30b-127">Dans la zone **Instruction de jointure** , complétez l’instruction de jointure comme suit :</span><span class="sxs-lookup"><span data-stu-id="fc30b-127">In the **Join statement** box, complete the join statement as follows:</span></span>  
  
    ```  
    ON Employee.BusinessEntityID = SalesOrderHeader.SalesPersonID  
    ```  
  
18. <span data-ttu-id="fc30b-128">Dans **Spécifiez les options de jointure**, sélectionnez **Clé unique**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-128">In **Specify join options**, select **Unique key**, and then click **OK**.</span></span>  
  
19. <span data-ttu-id="fc30b-129">Dans la page **Filtrer les lignes de la table** , cliquez sur **SalesOrderHeader (Sales)**, sur **Ajouter**, puis sur **Ajouter une jointure pour étendre le filtre sélectionné**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-129">On the **Filter Table Rows** page, click **SalesOrderHeader (Sales)**, click **Add**, and then click **Add Join to Extend the Selected Filter**.</span></span>  
  
20. <span data-ttu-id="fc30b-130">Dans la boîte de dialogue **Ajouter une jointure** , sélectionnez **Sales.SalesOrderDetail** sous **Table jointe**, cliquez sur **OK**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-130">In the **Add Join** dialog box, select **Sales.SalesOrderDetail** under **Joined table**, click **OK**, and then click **Next**.</span></span>  
  
21. <span data-ttu-id="fc30b-131">Sélectionnez **Créer un instantané immédiatement**, décochez **Planifier l’exécution de l’Agent d’instantané aux heures suivantes**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-131">Select **Create a snapshot immediately**, clear **Schedule the snapshot agent to run at the following times**, and click **Next**.</span></span>  
  
22. <span data-ttu-id="fc30b-132">Dans la page sécurité de l’agent, cliquez sur **paramètres de sécurité**, tapez \<_Machine_Name> _**\ repl_snapshot** dans la zone **compte de processus** , fournissez le mot de passe de ce compte, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-132">On the Agent Security page, click **Security Settings**, type \<_Machine_Name>_**\repl_snapshot** in the **Process account** box, supply the password for this account, and then click **OK**.</span></span> <span data-ttu-id="fc30b-133">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-133">Click **Finish**.</span></span>  
  
23. <span data-ttu-id="fc30b-134">Dans la page Terminer l’Assistant, entrez **AdvWorksSalesOrdersMerge** dans la zone **Nom de la publication** , puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-134">On the Complete the Wizard page, enter **AdvWorksSalesOrdersMerge** in the **Publication name** box and click **Finish**.</span></span>  
  
24. <span data-ttu-id="fc30b-135">Une fois la publication créée, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-135">After the publication is created, click **Close**.</span></span>  
  
### <a name="to-view-the-status-of-snapshot-generation"></a><span data-ttu-id="fc30b-136">Pour afficher l'état d'une génération d'instantané</span><span class="sxs-lookup"><span data-stu-id="fc30b-136">To view the status of snapshot generation</span></span>  
  
1.  <span data-ttu-id="fc30b-137">Connectez-vous au serveur de publication dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], développez le nœud du serveur, puis le dossier **Réplication** .</span><span class="sxs-lookup"><span data-stu-id="fc30b-137">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="fc30b-138">Dans le dossier Publications locales, cliquez avec le bouton droit sur **AdvWorksSalesOrdersMerge**, puis cliquez sur **Afficher l’état de l’Agent d’instantané**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-138">In the Local Publications folder, right-click **AdvWorksSalesOrdersMerge**, and then click **View Snapshot Agent Status**.</span></span>  
  
3.  <span data-ttu-id="fc30b-139">L'état en cours du travail de l'Agent d'instantané pour la publication s'affiche.</span><span class="sxs-lookup"><span data-stu-id="fc30b-139">The current status of the Snapshot Agent job for the publication is displayed.</span></span> <span data-ttu-id="fc30b-140">Vérifiez que le travail d'instantané a bien réussi avant de passer à la leçon suivante.</span><span class="sxs-lookup"><span data-stu-id="fc30b-140">Ensure that the snapshot job has succeeded before you continue to the next lesson.</span></span>  
  
### <a name="to-add-the-merge-agent-login-to-the-pal"></a><span data-ttu-id="fc30b-141">Pour ajouter la connexion de l'Agent de fusion à la liste d'accès à la publication</span><span class="sxs-lookup"><span data-stu-id="fc30b-141">To add the Merge Agent login to the PAL</span></span>  
  
1.  <span data-ttu-id="fc30b-142">Connectez-vous au serveur de publication dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], développez le nœud du serveur, puis le dossier **Réplication** .</span><span class="sxs-lookup"><span data-stu-id="fc30b-142">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="fc30b-143">Dans le dossier Publications locales, cliquez avec le bouton droit sur **AdvWorksSalesOrdersMerge**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-143">In the Local Publications folder, right-click **AdvWorksSalesOrdersMerge**, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="fc30b-144">La boîte de dialogue **Propriétés de la publication** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="fc30b-144">The **Publication Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="fc30b-145">Sélectionnez la page **Liste d’accès à la publication** , puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-145">Select the **Publication Access List** page, and click **Add**.</span></span>  
  
4.  <span data-ttu-id="fc30b-146">Dans la boîte de dialogue Ajouter un accès à une publication, sélectionnez _<nom_ordinateur>_**\repl_merge** et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-146">In the Add Publication Access dialog box, select _<Machine_Name>_**\repl_merge** and click **OK**.</span></span> <span data-ttu-id="fc30b-147">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fc30b-147">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fc30b-148">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="fc30b-148">Next Steps</span></span>  
 <span data-ttu-id="fc30b-149">Vous avez créé avec succès la publication de fusion.</span><span class="sxs-lookup"><span data-stu-id="fc30b-149">You have successfully created the merge publication.</span></span> <span data-ttu-id="fc30b-150">Ensuite, vous allez créer l'abonnement à cette publication.</span><span class="sxs-lookup"><span data-stu-id="fc30b-150">Next, you will subscribe to this publication.</span></span> <span data-ttu-id="fc30b-151">Consultez [Leçon 2 : Création d’un abonnement à la publication de fusion](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span><span class="sxs-lookup"><span data-stu-id="fc30b-151">See [Lesson 2: Creating a Subscription to the Merge Publication](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc30b-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fc30b-152">See Also</span></span>  
 <span data-ttu-id="fc30b-153">[Filtrer des données publiées](publish/filter-published-data.md) </span><span class="sxs-lookup"><span data-stu-id="fc30b-153">[Filter Published Data](publish/filter-published-data.md) </span></span>  
 <span data-ttu-id="fc30b-154">[Filtres de lignes paramétrés](merge/parameterized-filters-parameterized-row-filters.md) </span><span class="sxs-lookup"><span data-stu-id="fc30b-154">[Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md) </span></span>  
 [<span data-ttu-id="fc30b-155">Définir un article</span><span class="sxs-lookup"><span data-stu-id="fc30b-155">Define an Article</span></span>](publish/define-an-article.md)  
  
  
