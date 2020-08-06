---
title: 'Tâche 12 : ajout d’une transformation de colonne dérivée pour ajouter des colonnes requises par MDS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 98ccb271-04da-4126-9729-67e9a479aaef
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a4a70dd4d288e425beb2821f6b2aaf440b1d1930
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703512"
---
# <a name="task-12-adding-derived-column-transform-to-add-columns-required-by-mds"></a><span data-ttu-id="849f9-102">Tâche 12 : Ajout d’une transformation de colonne dérivée pour ajouter les colonnes requises par MDS</span><span class="sxs-lookup"><span data-stu-id="849f9-102">Task 12: Adding Derived Column Transform to Add Columns Required by MDS</span></span>
  <span data-ttu-id="849f9-103">Dans cette tâche, vous allez ajouter une transformation de colonne dérivée au flux de données.</span><span class="sxs-lookup"><span data-stu-id="849f9-103">In this task, you add the Derive Column Transform to the data flow.</span></span> <span data-ttu-id="849f9-104">Vous ajoutez deux colonnes dérivées, **ImportType** et **BatchTag**, aux enregistrements passés à cette transformation.</span><span class="sxs-lookup"><span data-stu-id="849f9-104">You add two derived columns, **ImportType** and **BatchTag**, to the records passed to this transform.</span></span> <span data-ttu-id="849f9-105">Vous devez ajouter ces colonnes avant de télécharger les données dans des tables intermédiaires dans MDS.</span><span class="sxs-lookup"><span data-stu-id="849f9-105">You should add these columns before uploading the data to staging tables in MDS.</span></span> <span data-ttu-id="849f9-106">Ces deux colonnes sont requises pour les tables intermédiaires dans MDS.</span><span class="sxs-lookup"><span data-stu-id="849f9-106">These two are required columns for the staging tables in MDS.</span></span> <span data-ttu-id="849f9-107">Pour plus d’informations, consultez [tables de mise en lots des membres feuille](../master-data-services/leaf-member-staging-table-master-data-services.md) .</span><span class="sxs-lookup"><span data-stu-id="849f9-107">See [Leaf Member Staging Tables](../master-data-services/leaf-member-staging-table-master-data-services.md) for more details.</span></span>  
  
1.  <span data-ttu-id="849f9-108">Glissez-déplacez la **transformation de colonne dérivée** de la section **commun** dans la **boîte à outils SSIS** vers l’onglet de **Workflow** .</span><span class="sxs-lookup"><span data-stu-id="849f9-108">Drag-drop **Derived Column transform** from **Common** section in the **SSIS Toolbox** to the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="849f9-109">Cliquez avec le bouton droit sur transformation de **colonne dérivée** sous l’onglet **Flow Data** , puis cliquez sur **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="849f9-109">Right-click **Derived Column** Transform in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="849f9-110">Tapez **Add Columns required by MDS** et appuyez sur **entrée**.</span><span class="sxs-lookup"><span data-stu-id="849f9-110">Type **Add Columns Required by MDS** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="849f9-111">Connectez les **doublons de filtre** pour **Ajouter les colonnes requises par MDS** à l’aide du connecteur Blue.</span><span class="sxs-lookup"><span data-stu-id="849f9-111">Connect **Filter Duplicates** to **Add Columns Required by MDS** using the blue connector.</span></span> <span data-ttu-id="849f9-112">La boîte de dialogue **sélection de sortie d’entrée** doit s’afficher.</span><span class="sxs-lookup"><span data-stu-id="849f9-112">You should see the **Input Output Selection** dialog box.</span></span>  
  
4.  <span data-ttu-id="849f9-113">Dans la boîte de dialogue **sélection de sortie d’entrée** , sélectionnez **enregistrements uniques**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="849f9-113">In the **Input Output Selection** dialog box, select **Unique Records**, and click **OK**.</span></span>  
  
     <span data-ttu-id="849f9-114">![Boîte de dialogue Sélection entrée et sortie](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-01.jpg "Boîte de dialogue Sélection entrée et sortie")</span><span class="sxs-lookup"><span data-stu-id="849f9-114">![Input Output Selection Dialog Box](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-01.jpg "Input Output Selection Dialog Box")</span></span>  
  
5.  <span data-ttu-id="849f9-115">Cliquez sur **SSIS** dans la barre de menus et cliquez sur **variables**.</span><span class="sxs-lookup"><span data-stu-id="849f9-115">Click **SSIS** on the menu bar and click **Variables**.</span></span>  
  
6.  <span data-ttu-id="849f9-116">Dans la fenêtre **variables** , cliquez sur le bouton **Ajouter une variable** de la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="849f9-116">In the **Variables** window, click **Add Variable** button on the toolbar.</span></span>  
  
     <span data-ttu-id="849f9-117">![Fenêtre Variables SSIS.](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-02.jpg "Fenêtre Variables SSIS.")</span><span class="sxs-lookup"><span data-stu-id="849f9-117">![SSIS Variables Window](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-02.jpg "SSIS Variables Window")</span></span>  
  
7.  <span data-ttu-id="849f9-118">Tapez **ImportType** pour le **nom** et **2** pour la **valeur**.</span><span class="sxs-lookup"><span data-stu-id="849f9-118">Type **ImportType** for the **Name** and **2** for the **value**.</span></span> <span data-ttu-id="849f9-119">Vous spécifiez la valeur 2 étant donné que vous souhaitez ajouter de nouveaux membres à une entité dans MDS.</span><span class="sxs-lookup"><span data-stu-id="849f9-119">You specify the value as 2 because you want to add new members to an entity in MDS.</span></span> <span data-ttu-id="849f9-120">Pour plus d’informations sur ce paramètre, consultez [table de mise en lots des membres feuille](../master-data-services/leaf-member-staging-table-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="849f9-120">For details about this parameter, see [Leaf Member Staging Table](../master-data-services/leaf-member-staging-table-master-data-services.md).</span></span>  
  
8.  <span data-ttu-id="849f9-121">Cliquez à nouveau sur le bouton **Ajouter une variable** de la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="849f9-121">Click **Add Variable** toolbar button again.</span></span>  
  
9. <span data-ttu-id="849f9-122">Tapez **BatchTag** pour le **nom**, sélectionnez **chaîne** comme **type de données**et **EIMBatch** pour la **valeur**.</span><span class="sxs-lookup"><span data-stu-id="849f9-122">Type **BatchTag** for the **Name**, select **String** for the **Data type**, and **EIMBatch** for the **Value**.</span></span> <span data-ttu-id="849f9-123">**BatchTag** est simplement un nom unique pour le lot que vous allez soumettre à MDS.</span><span class="sxs-lookup"><span data-stu-id="849f9-123">**BatchTag** is just a unique name for the batch you will be submitting to MDS.</span></span>  
  
10. <span data-ttu-id="849f9-124">Sous l’onglet **Data Flow** , double-cliquez sur **Add Columns required by MDS**.</span><span class="sxs-lookup"><span data-stu-id="849f9-124">In the **Data Flow** tab, double-click **Add Columns Required by MDS**.</span></span>  
  
11. <span data-ttu-id="849f9-125">Dans la boîte de dialogue **éditeur de transformation de colonne dérivée** , dans la **zone de liste dans le volet inférieur**, tapez **ImportType** pour le nom de la **colonne dérivée**.</span><span class="sxs-lookup"><span data-stu-id="849f9-125">In the **Derived Column Transformation Editor** dialog box, in the **list box in the bottom pane**, type **ImportType** for the **Derived Column Name**.</span></span>  
  
12. <span data-ttu-id="849f9-126">Développez **variables et paramètres** dans le volet supérieur gauche, glissez-déposez **User :: ImportType** dans la colonne **expression** .</span><span class="sxs-lookup"><span data-stu-id="849f9-126">Expand **Variables and Parameters** in the top-left pane, drag-drop **User::ImportType** to the **Expression** column.</span></span>  
  
     <span data-ttu-id="849f9-127">![Éditeur de transformation de colonne dérivée](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-03.jpg "Éditeur de transformation de colonne dérivée")</span><span class="sxs-lookup"><span data-stu-id="849f9-127">![Derived Column Transformation Editor](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-03.jpg "Derived Column Transformation Editor")</span></span>  
  
13. <span data-ttu-id="849f9-128">Tapez **BatchTag** dans la ligne suivante pour le **nom de la colonne dérivée**.</span><span class="sxs-lookup"><span data-stu-id="849f9-128">Type **BatchTag** in the next row for the **Derived Column Name**.</span></span>  
  
14. <span data-ttu-id="849f9-129">Faites glisser **User :: BatchTag** à partir de **variables et de paramètres** vers la colonne **expression** .</span><span class="sxs-lookup"><span data-stu-id="849f9-129">Drag-drop **User::BatchTag** from **Variables and Parameters** to the **Expression** column.</span></span>  
  
15. <span data-ttu-id="849f9-130">Cliquez sur **OK** pour fermer la boîte de dialogue **transformation de colonne dérivée** .</span><span class="sxs-lookup"><span data-stu-id="849f9-130">Click **OK** to close the **Derived Column Transformation** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="849f9-131">étape suivante</span><span class="sxs-lookup"><span data-stu-id="849f9-131">Next Step</span></span>  
 [<span data-ttu-id="849f9-132">Tâche 13 : Ajout d’une destination OLE DB pour écrire des données dans une table intermédiaire MDS</span><span class="sxs-lookup"><span data-stu-id="849f9-132">Task 13: Adding OLE DB Destination to Write Data to MDS Staging Table</span></span>](../../2014/tutorials/task-13-adding-ole-db-destination-to-write-data-to-mds-staging-table.md)  
  
  
