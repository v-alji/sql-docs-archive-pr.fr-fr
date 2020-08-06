---
title: 'Tâche 1 (condition préalable) : suppression des données des fournisseurs dans MDS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6f0a4287-7fd4-4f18-b7e4-a5191a9d4a3c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e78dc5ff04f95d42cf440e3f80b1b349e0315a69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612653"
---
# <a name="task-1-prerequisite-removing-supplier-data-in-mds"></a><span data-ttu-id="83e4c-102">Tâche 1 (prérequis) : Suppression de données de fournisseur dans MDS</span><span class="sxs-lookup"><span data-stu-id="83e4c-102">Task 1 (Prerequisite): Removing Supplier Data in MDS</span></span>
  <span data-ttu-id="83e4c-103">Dans cette tâche, vous allez supprimer les données des fournisseurs stockées dans MDS.</span><span class="sxs-lookup"><span data-stu-id="83e4c-103">In this task, you remove the supplier data stored in MDS.</span></span> <span data-ttu-id="83e4c-104">Vous avez chargé les données manuellement à l’aide du **complément MDS pour Excel** dans la leçon précédente.</span><span class="sxs-lookup"><span data-stu-id="83e4c-104">You uploaded the data manually using **MDS Excel Add-in** in the previous lesson.</span></span> <span data-ttu-id="83e4c-105">Le package SSIS que vous créez dans cette leçon charge automatiquement les données dans MDS pour vous.</span><span class="sxs-lookup"><span data-stu-id="83e4c-105">The SSIS package you create in this lesson will automatically upload the data to MDS for you.</span></span> <span data-ttu-id="83e4c-106">Par conséquent, avant de tester le package SSIS, vous devez supprimer les données des fournisseurs dans MDS, ainsi que la hiérarchie dérivée, les entités Fournisseur et État, et créer l'entité Fournisseur sans données.</span><span class="sxs-lookup"><span data-stu-id="83e4c-106">Therefore, before testing the SSIS package, you need to remove the supplier data from MDS, remove the derived hierarchy, remove supplier and state entities, and create the supplier entity with no data.</span></span>  
  
1.  <span data-ttu-id="83e4c-107">Lancez le **Data Manager maître** en accédant à `http://localhost/MDS` ou au site Web et à l’application que vous avez spécifiés lors de la configuration de MDS.</span><span class="sxs-lookup"><span data-stu-id="83e4c-107">Launch **Master Data Manager** by navigating to `http://localhost/MDS` or the website and application you specified when configuring MDS.</span></span> <span data-ttu-id="83e4c-108">Si vous avez conservé le **Data Manager maître** ouvert, cliquez sur **SQL Server Master Data Services 2012** en haut pour basculer vers la **page d’hébergement**.</span><span class="sxs-lookup"><span data-stu-id="83e4c-108">If you kept the **Master Data Manager** open, click **SQL Server 2012 Master Data Services** at the top to switch to the **home page**.</span></span>  
  
2.  <span data-ttu-id="83e4c-109">Cliquez sur **administration de système** dans la section **tâches administratives** .</span><span class="sxs-lookup"><span data-stu-id="83e4c-109">Click **System Administration** in the **Administrative Tasks** section.</span></span>  
  
3.  <span data-ttu-id="83e4c-110">Pointez la souris sur **gérer** dans le menu et cliquez sur **hiérarchies dérivées**.</span><span class="sxs-lookup"><span data-stu-id="83e4c-110">Hover the mouse over **Manage** on the menu and click **Derived Hierarchies**.</span></span> <span data-ttu-id="83e4c-111">Vous devez supprimer la hiérarchie dérivée **SuppliersInState** avant de supprimer les entités dans le modèle **Suppliers** .</span><span class="sxs-lookup"><span data-stu-id="83e4c-111">You need to delete the derived hierarchy **SuppliersInState** before deleting the entities in the **Suppliers** model.</span></span>  
  
4.  <span data-ttu-id="83e4c-112">Sélectionnez **SuppliersInState** dans la liste **hiérarchie dérivée** , puis cliquez sur le bouton **X (supprimer)** dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="83e4c-112">Select **SuppliersInState** from the **Derived Hierarchy** list and click **X (Delete)** button on the toolbar.</span></span>  
  
5.  <span data-ttu-id="83e4c-113">Cliquez sur **OK** pour confirmer la suppression.</span><span class="sxs-lookup"><span data-stu-id="83e4c-113">Click **OK** to confirm deletion.</span></span>  
  
6.  <span data-ttu-id="83e4c-114">Pointez la souris sur **gérer** dans le menu et cliquez sur **entités**.</span><span class="sxs-lookup"><span data-stu-id="83e4c-114">Hover the mouse over **Manage** on the menu and click **Entities**.</span></span>  
  
7.  <span data-ttu-id="83e4c-115">Cliquez sur **fournisseur** , puis sur le bouton **Supprimer (X)** de la barre d’outils pour supprimer l’entité.</span><span class="sxs-lookup"><span data-stu-id="83e4c-115">Click **Supplier** and click **Delete (X)** button on toolbar to delete the entity.</span></span> <span data-ttu-id="83e4c-116">Cliquez sur **OK** dans les boîtes de message.</span><span class="sxs-lookup"><span data-stu-id="83e4c-116">Click **OK** on message boxes.</span></span>  
  
8.  <span data-ttu-id="83e4c-117">Répétez l’étape précédente pour supprimer l’entité **État** .</span><span class="sxs-lookup"><span data-stu-id="83e4c-117">Repeat the previous step to delete **State** entity.</span></span>  
  
9. <span data-ttu-id="83e4c-118">Ne fermez pas le **Data Manager maître**.</span><span class="sxs-lookup"><span data-stu-id="83e4c-118">Don't close **Master Data Manager**.</span></span>  
  
10. <span data-ttu-id="83e4c-119">Basculez vers la fenêtre Excel pour laquelle le fichier **Suppliers.xlsnettoyé et mis en correspondance** est ouvert.</span><span class="sxs-lookup"><span data-stu-id="83e4c-119">Switch to the Excel window that has **Cleansed and Matched Suppliers.xls** file open.</span></span> <span data-ttu-id="83e4c-120">Basculez vers l’onglet **Feuil1** en bas.</span><span class="sxs-lookup"><span data-stu-id="83e4c-120">Switch to the **Sheet1** tab at the bottom.</span></span>  
  
11. <span data-ttu-id="83e4c-121">Sélectionnez uniquement la **première ligne avec des en-têtes**.</span><span class="sxs-lookup"><span data-stu-id="83e4c-121">Select only the **first row with headers**.</span></span> <span data-ttu-id="83e4c-122">Ne sélectionnez aucune autre ligne.</span><span class="sxs-lookup"><span data-stu-id="83e4c-122">Don't select any other row.</span></span> <span data-ttu-id="83e4c-123">Vous souhaitez créer les entités en fonction des colonnes Excel, mais vous ne souhaitez pas télécharger de données.</span><span class="sxs-lookup"><span data-stu-id="83e4c-123">You want to create the entities based on the Excel columns but don't want to upload any data.</span></span> <span data-ttu-id="83e4c-124">Par conséquent, sélectionnez uniquement la première ligne avec les en-têtes.</span><span class="sxs-lookup"><span data-stu-id="83e4c-124">Therefore you select only the first row with the headers.</span></span>  
  
12. <span data-ttu-id="83e4c-125">Dans la barre de menus, cliquez sur **données** de référence.</span><span class="sxs-lookup"><span data-stu-id="83e4c-125">Click **Master Data** on the menu bar.</span></span>  
  
13. <span data-ttu-id="83e4c-126">Cliquez sur **créer une entité** dans le ruban.</span><span class="sxs-lookup"><span data-stu-id="83e4c-126">Click **Create Entity** from the ribbon.</span></span>  
  
14. <span data-ttu-id="83e4c-127">Dans la boîte de dialogue **gérer les connexions** , si vous ne voyez pas la connexion au **serveur MDS local** sous **connexions existantes**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="83e4c-127">In **Manage Connections** dialog box, if you do not see the connection to **local MDS server** under **Existing connections**, do the following:</span></span>  
  
    1.  <span data-ttu-id="83e4c-128">Sélectionnez **créer une nouvelle connexion**, puis cliquez sur le bouton **nouveau** .</span><span class="sxs-lookup"><span data-stu-id="83e4c-128">Select **Create a new connection**, and click **New** button.</span></span>  
  
    2.  <span data-ttu-id="83e4c-129">Dans la boîte de dialogue Ajouter une nouvelle connexion, tapez **serveur MDS local** pour **Description** et **http : \/ /localhost/MDS** pour **adresse du serveur MDS**, puis cliquez sur **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="83e4c-129">In the Add New Connection dialog box, type **Local MDS Server** for **Description** and **http:\//localhost/MDS** for **MDS server address**, and click **OK** to close the dialog box.</span></span>  
  
15. <span data-ttu-id="83e4c-130">Dans la boîte de dialogue **gérer les connexions** , sélectionnez **serveur MDS local** ( `http://localhost/MDS` ), puis cliquez sur **tester** pour tester la connexion.</span><span class="sxs-lookup"><span data-stu-id="83e4c-130">In **Manage Connections** dialog box, select **Local MDS Server** (`http://localhost/MDS`), click **Test** to test the connection.</span></span> <span data-ttu-id="83e4c-131">Cliquez sur **OK** dans le message de confirmation.</span><span class="sxs-lookup"><span data-stu-id="83e4c-131">Click **OK** on the message box.</span></span>  
  
16. <span data-ttu-id="83e4c-132">Cliquez sur **connexion** pour établir une connexion au serveur MDS.</span><span class="sxs-lookup"><span data-stu-id="83e4c-132">Click **Connect** to make a connection to the MDS server.</span></span>  
  
17. <span data-ttu-id="83e4c-133">Dans la boîte de dialogue **créer une entité** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="83e4c-133">In the **Create Entity** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="83e4c-134">Confirmez que la **plage** est définie sur **$1 : $1**.</span><span class="sxs-lookup"><span data-stu-id="83e4c-134">Confirm that **Range** is set to **$1:$1**.</span></span>  
  
    2.  <span data-ttu-id="83e4c-135">Sélectionnez **Suppliers** pour **Model**.</span><span class="sxs-lookup"><span data-stu-id="83e4c-135">Select **Suppliers** for **Model**.</span></span>  
  
    3.  <span data-ttu-id="83e4c-136">Sélectionnez **Version_1** pour **version**.</span><span class="sxs-lookup"><span data-stu-id="83e4c-136">Select **VERSION_1** for **Version**.</span></span>  
  
    4.  <span data-ttu-id="83e4c-137">Tapez **Supplier** pour **nouveau nom d’entité**.</span><span class="sxs-lookup"><span data-stu-id="83e4c-137">Type **Supplier** for **New entity name**.</span></span>  
  
    5.  <span data-ttu-id="83e4c-138">Sélectionnez **RéfFournisseur** comme **code**.</span><span class="sxs-lookup"><span data-stu-id="83e4c-138">Select **SupplierID** for **Code**.</span></span>  
  
    6.  <span data-ttu-id="83e4c-139">Sélectionnez **nom du fournisseur** pour **nom**.</span><span class="sxs-lookup"><span data-stu-id="83e4c-139">Select **Supplier Name** for **Name**.</span></span>  
  
    7.  <span data-ttu-id="83e4c-140">Cliquez sur **OK** pour créer l’entité et fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="83e4c-140">Click **OK** to create the entity and close the dialog box.</span></span>  
  
18. <span data-ttu-id="83e4c-141">Fermez **Excel** et **n’enregistrez pas** le fichier.</span><span class="sxs-lookup"><span data-stu-id="83e4c-141">Close **Excel** and **do not save** the file.</span></span>  
  
19. <span data-ttu-id="83e4c-142">Dans **Data Manager maître**, actualisez le navigateur Internet et confirmez que l’entité **fournisseur** est affichée dans la liste.</span><span class="sxs-lookup"><span data-stu-id="83e4c-142">In **Master Data Manager**, refresh the internet browser and confirm that **Supplier** entity is displayed in the list.</span></span>  
  
20. <span data-ttu-id="83e4c-143">Basculez vers la **page d’hébergement** en cliquant sur **SQL Server 2012 Master Data Services** en haut.</span><span class="sxs-lookup"><span data-stu-id="83e4c-143">Switch to the **home page** by clicking **SQL Server 2012 Master Data Services** at the top.</span></span>  
  
21. <span data-ttu-id="83e4c-144">Vérifiez que l’option **Supplier** Model est sélectionnée pour **model** et que **Version_1** est sélectionné pour **version**.</span><span class="sxs-lookup"><span data-stu-id="83e4c-144">Confirm that **Suppliers** model is selected for **Model** and **VERSION_1** is selected for **Version**.</span></span>  
  
22. <span data-ttu-id="83e4c-145">Cliquez sur **Explorateur**.</span><span class="sxs-lookup"><span data-stu-id="83e4c-145">Click **Explorer**.</span></span> <span data-ttu-id="83e4c-146">Notez que l’entité **Supplier** avec tous les attributs est créée sans **valeur**.</span><span class="sxs-lookup"><span data-stu-id="83e4c-146">Notice that the **Supplier** entity with all the attributes is created with **no values**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="83e4c-147">étape suivante</span><span class="sxs-lookup"><span data-stu-id="83e4c-147">Next Step</span></span>  
 [<span data-ttu-id="83e4c-148">Tâche 2 &#40;&#41; facultative : création d’une vue d’abonnement MDS à l’aide du Data Manager maître</span><span class="sxs-lookup"><span data-stu-id="83e4c-148">Task 2 &#40;Optional&#41;: Creating a MDS Subscription View using Master Data Manager</span></span>](../../2014/tutorials/task-2-optional-creating-a-mds-subscription-view-using-master-data-manager.md)  
  
  
