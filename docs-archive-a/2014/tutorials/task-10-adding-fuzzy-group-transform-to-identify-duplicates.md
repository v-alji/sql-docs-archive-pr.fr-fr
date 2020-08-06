---
title: 'Tâche 10 : ajout d’une transformation de groupe approximatif pour identifier les doublons | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 90b2b323-babd-464a-8914-9dc5e66aca74
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 086625197850fdfd6381e9c0a4a7deac8ce3ae45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699000"
---
# <a name="task-10-adding-fuzzy-group-transform-to-identify-duplicates"></a><span data-ttu-id="f6c08-102">Tâche 10 : Ajout d’une transformation de regroupement probable pour identifier des doublons</span><span class="sxs-lookup"><span data-stu-id="f6c08-102">Task 10: Adding Fuzzy Group Transform to Identify Duplicates</span></span>
  <span data-ttu-id="f6c08-103">Dans cette tâche, vous allez ajouter une transformation de regroupement probable au flux de données.</span><span class="sxs-lookup"><span data-stu-id="f6c08-103">In this task, you add a Fuzzy Group Transform to the data flow.</span></span> <span data-ttu-id="f6c08-104">La transformation de regroupement probable aide à identifier les doublons dans les données sources.</span><span class="sxs-lookup"><span data-stu-id="f6c08-104">The Fuzzy Group transformation can help identify duplicates in the source data.</span></span> <span data-ttu-id="f6c08-105">Pour plus d’informations, consultez [transformation de regroupement approximatif](../integration-services/data-flow/transformations/fuzzy-grouping-transformation.md) .</span><span class="sxs-lookup"><span data-stu-id="f6c08-105">See [Fuzzy Grouping Transformation](../integration-services/data-flow/transformations/fuzzy-grouping-transformation.md) for more details.</span></span>  
  
1.  <span data-ttu-id="f6c08-106">Glissez-déplacez la transformation de **groupe approximatif** dans d' **autres transformations** de la **boîte à outils SSIS** vers l’onglet de **Workflow** sous **combiner les enregistrements corrects et corrigés**.</span><span class="sxs-lookup"><span data-stu-id="f6c08-106">Drag-drop **Fuzzy Group** transform in **Other Transforms** on the **SSIS Toolbox** to the **Data Flow** tab under **Combine Correct and Corrected Records**.</span></span>  
  
2.  <span data-ttu-id="f6c08-107">Cliquez avec le bouton droit sur transformation de **groupe approximatif** dans l’onglet **Flow Data** , puis cliquez sur **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="f6c08-107">Right-click **Fuzzy Group** Transform in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="f6c08-108">Tapez **regrouper les fournisseurs avec des ID correspondants** et appuyez sur **entrée**.</span><span class="sxs-lookup"><span data-stu-id="f6c08-108">Type **Group Suppliers with matching IDs** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="f6c08-109">Connexion **combiner des enregistrements corrects et corrigés** pour **regrouper les fournisseurs avec des ID correspondants** à l’aide du connecteur bleu.</span><span class="sxs-lookup"><span data-stu-id="f6c08-109">Connect **Combine Correct and Corrected Records** to **Group Suppliers with matching IDs** using the blue connector.</span></span>  
  
     <span data-ttu-id="f6c08-110">![Connexion aux fournisseurs du groupe avec ID correspondants](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-01.jpg "Connexion aux fournisseurs du groupe avec ID correspondants")</span><span class="sxs-lookup"><span data-stu-id="f6c08-110">![Connection to Group Suppliers with Matching IDs](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-01.jpg "Connection to Group Suppliers with Matching IDs")</span></span>  
  
4.  <span data-ttu-id="f6c08-111">Double-cliquez sur **regrouper les fournisseurs avec des ID correspondants**.</span><span class="sxs-lookup"><span data-stu-id="f6c08-111">Double-click **Group Suppliers with matching IDs**.</span></span>  
  
5.  <span data-ttu-id="f6c08-112">Dans l **'éditeur de transformation de groupe approximatif**, cliquez sur **nouveau** en regard de **OLE DB liste déroulante gestionnaire de connexions** pour lancer la boîte de dialogue **configurer le gestionnaire de connexions OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="f6c08-112">In the **Fuzzy Group Transformation Editor**, click **New** next to **OLE DB Connection Manager drop-down list** to launch **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
6.  <span data-ttu-id="f6c08-113">Dans la boîte de dialogue, cliquez sur **nouveau** pour lancer la boîte de dialogue **Gestionnaire de connexions** .</span><span class="sxs-lookup"><span data-stu-id="f6c08-113">In the dialog box, click **New** to launch **Connection Manager** dialog box.</span></span>  
  
7.  <span data-ttu-id="f6c08-114">Tapez **(local)** ou **point** (.) pour le nom du serveur.</span><span class="sxs-lookup"><span data-stu-id="f6c08-114">Type **(local)** or **period** (.) for the Server name.</span></span>  
  
8.  <span data-ttu-id="f6c08-115">Sélectionnez **MDS** pour **le champ sélectionner ou entrer un nom de base de données** .</span><span class="sxs-lookup"><span data-stu-id="f6c08-115">Select **MDS** for **Select or enter a database name** field.</span></span> <span data-ttu-id="f6c08-116">Vous allez utiliser la base de données MDS comme stockage temporaire pour la **transformation de groupe approximatif**.</span><span class="sxs-lookup"><span data-stu-id="f6c08-116">You will use the MDS database as the temporary storage for the **Fuzzy Group Transform**.</span></span> <span data-ttu-id="f6c08-117">La transformation de **regroupement approximatif** nécessite une connexion à une instance de SQL Server pour créer les tables temporaires SQL Server dont l’algorithme de transformation a besoin pour effectuer son travail.</span><span class="sxs-lookup"><span data-stu-id="f6c08-117">The **Fuzzy Grouping** transformation requires a connection to an instance of SQL Server to create the temporary SQL Server tables that the transformation algorithm requires to do its work.</span></span> <span data-ttu-id="f6c08-118">Vous pouvez créer une base de données ou utiliser une base de données existante à cet effet.</span><span class="sxs-lookup"><span data-stu-id="f6c08-118">You can create a database or use another existing database for this purpose.</span></span>  
  
9. <span data-ttu-id="f6c08-119">Cliquez sur **tester la connexion** pour tester la connexion, puis cliquez sur **OK** dans la boîte de message.</span><span class="sxs-lookup"><span data-stu-id="f6c08-119">Click **Test Connection** to test the connection and click **OK** on the message box.</span></span>  
  
10. <span data-ttu-id="f6c08-120">Dans la boîte de dialogue **Gestionnaire de connexions** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6c08-120">In the **Connection Manager** dialog box, click **OK**.</span></span>  
  
11. <span data-ttu-id="f6c08-121">Sélectionnez **(local). MDS** (ou **localhost. MDS**) dans la **liste des connexions de données** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6c08-121">Select **(local).MDS** (or **localhost.MDS**) from the **list of Data Connections** and click **OK**.</span></span>  
  
12. <span data-ttu-id="f6c08-122">Dans l **'éditeur de transformation de regroupement probable**, vérifiez que **(local). MDS** ou **localhost. MDS** est sélectionné pour le **Gestionnaire de connexions OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="f6c08-122">In the **Fuzzy Grouping Transformation Editor**, confirm that **(local).MDS** or **localhost.MDS** is selected for the **OLE DB Connection Manager**.</span></span>  
  
13. <span data-ttu-id="f6c08-123">Basculez vers l’onglet **colonnes** .</span><span class="sxs-lookup"><span data-stu-id="f6c08-123">Switch to the **Columns** tab.</span></span>  
  
14. <span data-ttu-id="f6c08-124">Sélectionnez (case à cocher) **SupplierID_Output** dans la liste des **colonnes d’entrée disponibles**.</span><span class="sxs-lookup"><span data-stu-id="f6c08-124">Select (check box) **SupplierID_Output** from the list of **Available Input Columns**.</span></span> <span data-ttu-id="f6c08-125">Pour configurer la transformation, sélectionnez les colonnes d'entrée à utiliser lors de l'identification des doublons.</span><span class="sxs-lookup"><span data-stu-id="f6c08-125">To configure the transformation, select the input columns to use when identifying duplicates.</span></span> <span data-ttu-id="f6c08-126">Pour faire simple, utilisez uniquement SupplierID dans cette étape.</span><span class="sxs-lookup"><span data-stu-id="f6c08-126">To keep it simple, you only use the SupplierID in this step.</span></span>  
  
     <span data-ttu-id="f6c08-127">![Éditeur de transformation de regroupement probable](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-02.jpg "Éditeur de transformation de regroupement probable")</span><span class="sxs-lookup"><span data-stu-id="f6c08-127">![Fuzzy Grouping Transformation Editor](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-02.jpg "Fuzzy Grouping Transformation Editor")</span></span>  
  
15. <span data-ttu-id="f6c08-128">Cliquez sur **OK** pour fermer l **'éditeur de transformation de groupe approximatif**.</span><span class="sxs-lookup"><span data-stu-id="f6c08-128">Click **OK** to close the **Fuzzy Group Transformation Editor**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="f6c08-129">étape suivante</span><span class="sxs-lookup"><span data-stu-id="f6c08-129">Next Step</span></span>  
 [<span data-ttu-id="f6c08-130">Tâche 11 : Ajout d’une transformation de fractionnement conditionnel pour filtrer les doublons</span><span class="sxs-lookup"><span data-stu-id="f6c08-130">Task 11: Adding Conditional Split Transform to Filter Duplicates</span></span>](../../2014/tutorials/task-11-adding-conditional-split-transform-to-filter-duplicates.md)  
  
  
