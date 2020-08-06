---
title: 'Tâche 2 : chargement des données des fournisseurs dans MDS à l’aide de Complément MDS pour Excel | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 598deb57-e0cc-4e0a-aeb1-94432c094c67
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 16c5fa9db81649b30c12fae4d2e57afa8bf094e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600400"
---
# <a name="task-2-uploading-supplier-data-to-mds-using-mds-add-in-for-excel"></a><span data-ttu-id="e2d82-102">Tâche 2 : Téléchargement des données des fournisseurs vers MDS à l’aide du complément MDS pour Excel</span><span class="sxs-lookup"><span data-stu-id="e2d82-102">Task 2: Uploading Supplier Data to MDS using MDS Add-in for Excel</span></span>
  <span data-ttu-id="e2d82-103">Au cours de cette tâche, vous allez publier les données du fournisseur et du nettoyage dans **MDS** à l’aide de la **complément MDS pour Excel**.</span><span class="sxs-lookup"><span data-stu-id="e2d82-103">In this task, you publish the cleansed and supplier data to **MDS** using the **MDS Add-in for Excel**.</span></span> <span data-ttu-id="e2d82-104">Vous créez une entité nommée **fournisseur** dans le modèle **fournisseurs** que vous avez créé dans la leçon précédente.</span><span class="sxs-lookup"><span data-stu-id="e2d82-104">You create an entity named **Supplier** in the **Suppliers** model you created in the previous lesson.</span></span> <span data-ttu-id="e2d82-105">L'entité aura un attribut pour chaque colonne dans le fichier Excel.</span><span class="sxs-lookup"><span data-stu-id="e2d82-105">The entity will have an attribute for each column in the Excel file.</span></span> <span data-ttu-id="e2d82-106">Les attributs de code et de nom de l’entité fournisseur correspondent aux colonnes **SupplierID** et **nom du fournisseur** dans Excel.</span><span class="sxs-lookup"><span data-stu-id="e2d82-106">The Code and Name attributes of the Supplier entity correspond to the **SupplierID** and **Supplier Name** columns in Excel.</span></span>  
  
1.  <span data-ttu-id="e2d82-107">Ouvrir **les Suppliers.xlsnettoyées et mises en correspondance** dans **Excel**.</span><span class="sxs-lookup"><span data-stu-id="e2d82-107">Open **Cleansed and Matched Suppliers.xls** in **Excel**.</span></span>  
  
2.  <span data-ttu-id="e2d82-108">Appuyez sur **Ctrl + A** pour sélectionner des données entières.</span><span class="sxs-lookup"><span data-stu-id="e2d82-108">Press **CTRL+A** to select entire data.</span></span> <span data-ttu-id="e2d82-109">Il est **important** de sélectionner l’ensemble des données dans la feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="e2d82-109">It is **important** that you select the entire data in the spreadsheet.</span></span>  
  
3.  <span data-ttu-id="e2d82-110">Dans la barre de menus, cliquez sur **données** de référence.</span><span class="sxs-lookup"><span data-stu-id="e2d82-110">Click **Master Data** on the menu bar.</span></span>  
  
4.  <span data-ttu-id="e2d82-111">Cliquez sur le bouton **créer une entité** dans le ruban.</span><span class="sxs-lookup"><span data-stu-id="e2d82-111">Click **Create Entity** button on the ribbon.</span></span>  
  
     <span data-ttu-id="e2d82-112">![Excel - Onglet des données de référence - Bouton Créer entité](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-01.jpg "Excel - Onglet des données de référence - Bouton Créer entité")</span><span class="sxs-lookup"><span data-stu-id="e2d82-112">![Excel - Master Data Tab - Create Entity Button](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-01.jpg "Excel - Master Data Tab - Create Entity Button")</span></span>  
  
5.  <span data-ttu-id="e2d82-113">Dans la boîte de dialogue **gérer les connexions** , si vous ne voyez pas la connexion au **serveur MDS local** sous **connexions existantes**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e2d82-113">In **Manage Connections** dialog box, if you do not see the connection to **local MDS server** under **Existing connections**, do the following:</span></span>  
  
    1.  <span data-ttu-id="e2d82-114">Sélectionnez **créer une nouvelle connexion**, puis cliquez sur le bouton **nouveau** .</span><span class="sxs-lookup"><span data-stu-id="e2d82-114">Select **Create a new connection**, and click **New** button.</span></span>  
  
    2.  <span data-ttu-id="e2d82-115">Dans la boîte de dialogue **Ajouter une nouvelle connexion** , tapez **serveur MDS local** pour **Description** et **http : \/ /localhost/MDS** pour **adresse du serveur MDS**, puis cliquez sur **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e2d82-115">In the **Add New Connection** dialog box, type **Local MDS Server** for **Description** and **http:\//localhost/MDS** for **MDS server address**, and click **OK** to close the dialog box.</span></span>  
  
6.  <span data-ttu-id="e2d82-116">Dans la boîte de dialogue **gérer les connexions** , sélectionnez **serveur MDS local** ( `http://localhost/MDS` ), puis cliquez sur **tester** pour tester la connexion.</span><span class="sxs-lookup"><span data-stu-id="e2d82-116">In **Manage Connections** dialog box, select **Local MDS Server** (`http://localhost/MDS`), click **Test** to test the connection.</span></span> <span data-ttu-id="e2d82-117">Cliquez sur **OK** dans le message de confirmation.</span><span class="sxs-lookup"><span data-stu-id="e2d82-117">Click **OK** on the message box.</span></span>  
  
7.  <span data-ttu-id="e2d82-118">Cliquez sur **se connecter** pour vous connecter au serveur MDS.</span><span class="sxs-lookup"><span data-stu-id="e2d82-118">Click **Connect** to connect to the MDS server.</span></span>  
  
8.  <span data-ttu-id="e2d82-119">Dans la boîte de dialogue **créer une entité** , sélectionnez **fournisseurs** pour le **modèle**.</span><span class="sxs-lookup"><span data-stu-id="e2d82-119">In the **Create Entity** dialog box, select **Suppliers** for the **Model**.</span></span>  
  
9. <span data-ttu-id="e2d82-120">Assurez-vous que **Version_1** est sélectionné pour **version**.</span><span class="sxs-lookup"><span data-stu-id="e2d82-120">Ensure that **VERSION_1** is selected for **Version**.</span></span>  
  
10. <span data-ttu-id="e2d82-121">Entrez le **fournisseur** du **nouveau nom**de l’entité.</span><span class="sxs-lookup"><span data-stu-id="e2d82-121">Enter **Supplier** for **New entity name**.</span></span>  
  
11. <span data-ttu-id="e2d82-122">Sélectionnez **SupplierID** pour **la colonne qui contient un champ d’identificateur unique** (vous pouvez également générer automatiquement un code).</span><span class="sxs-lookup"><span data-stu-id="e2d82-122">Select **SupplierID** for **the column that contains a unique identifier** field (you can also generate a code automatically).</span></span> <span data-ttu-id="e2d82-123">Vous mappez essentiellement la colonne **RéfFournisseur** dans **Excel** à l’attribut **code** de l’entité **Supplier** .</span><span class="sxs-lookup"><span data-stu-id="e2d82-123">You are essentially mapping the **SupplierID** column in **Excel** to the **Code** attribute of **Supplier** entity.</span></span>  
  
12. <span data-ttu-id="e2d82-124">Sélectionnez le **nom du fournisseur** pour **la colonne qui contient le champ noms** .</span><span class="sxs-lookup"><span data-stu-id="e2d82-124">Select **Supplier Name** for **the column that contains names** field.</span></span> <span data-ttu-id="e2d82-125">Vous mappez essentiellement la colonne **nom du fournisseur** dans **Excel** à l’attribut **nom** de l’entité **fournisseur** .</span><span class="sxs-lookup"><span data-stu-id="e2d82-125">You are essentially mapping the **Supplier Name** column in **Excel** to the **Name** attribute of the **Supplier** entity.</span></span> <span data-ttu-id="e2d82-126">Les attributs de **code** et de **nom** sont des attributs obligatoires pour une entité dans MDS.</span><span class="sxs-lookup"><span data-stu-id="e2d82-126">The **Code** and **Name** attributes are mandatory attributes for an entity in MDS.</span></span>  
  
     <span data-ttu-id="e2d82-127">![Boîte de dialogue Créer entité](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-02.jpg "Boîte de dialogue Créer entité")</span><span class="sxs-lookup"><span data-stu-id="e2d82-127">![Create Entity Dialog Box](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-02.jpg "Create Entity Dialog Box")</span></span>  
  
13. <span data-ttu-id="e2d82-128">Cliquez sur **OK** pour créer l’entité sur MDS, publier les données de référence dans l’entité et fermer la boîte de dialogue **créer une entité** .</span><span class="sxs-lookup"><span data-stu-id="e2d82-128">Click **OK** to create the entity on MDS, publish the master data to the entity, and close **Create Entity** dialog box.</span></span>  
  
14. <span data-ttu-id="e2d82-129">Vous devez maintenant voir une nouvelle feuille intitulée **Supplier**, qui est le nom de l’entité, ajouté à votre feuille de calcul Excel et en haut de la feuille de calcul, vous devez voir que la feuille de calcul est connectée au serveur MDS.</span><span class="sxs-lookup"><span data-stu-id="e2d82-129">Now, you should see a new sheet titled **Supplier**, which is the name of the entity, added to your Excel spreadsheet and at the top of the worksheet you should see that the worksheet is connected to the MDS server.</span></span> <span data-ttu-id="e2d82-130">Notez que la feuille de calcul d’origine (intitulée **Feuil1**) existe toujours.</span><span class="sxs-lookup"><span data-stu-id="e2d82-130">Notice that the original worksheet (titled **Sheet1**) still exists.</span></span>  
  
     <span data-ttu-id="e2d82-131">![Excel - Onglets Fournisseurs et Feuille1](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-03.jpg "Excel - Onglets Fournisseurs et Feuille1")</span><span class="sxs-lookup"><span data-stu-id="e2d82-131">![Excel - Supplier and Sheet1 Tabs](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-03.jpg "Excel - Supplier and Sheet1 Tabs")</span></span>  
  
     <span data-ttu-id="e2d82-132">![Excel - Affichage des détails de la connexion MDS](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-04.jpg "Excel - Affichage des détails de la connexion MDS")</span><span class="sxs-lookup"><span data-stu-id="e2d82-132">![Excel - Showing MDS Connection Details](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-04.jpg "Excel - Showing MDS Connection Details")</span></span>  
  
15. <span data-ttu-id="e2d82-133">Laissez **Excel** ouvert.</span><span class="sxs-lookup"><span data-stu-id="e2d82-133">Keep **Excel** open.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="e2d82-134">Tâche suivante</span><span class="sxs-lookup"><span data-stu-id="e2d82-134">Next Task</span></span>  
 [<span data-ttu-id="e2d82-135">Tâche 3 : Vérification des données dans Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="e2d82-135">Task 3: Verifying the Data in Master Data Manager</span></span>](../../2014/tutorials/task-3-verifying-the-data-in-master-data-manager.md)  
  
  
