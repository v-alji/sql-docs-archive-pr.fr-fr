---
title: 'Tâche 14 : ajout d’une tâche d’exécution SQL à un workflow de contrôle pour exécuter la procédure stockée pour MDS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 9a5d1b52-d505-4e6f-8a89-569329c094e2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: da8e80b25706c40e749fc364baeb578681e76b42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698928"
---
# <a name="task-14-adding-execute-sql-task-to-control-flow-to-run-the-stored-procedure-for-mds"></a><span data-ttu-id="da8e8-102">Tâche 14 : Ajout d’une tâche d’exécution SQL au flux de contrôle pour exécuter la procédure stockée pour MDS</span><span class="sxs-lookup"><span data-stu-id="da8e8-102">Task 14: Adding Execute SQL Task to Control Flow to Run the Stored Procedure for MDS</span></span>
  <span data-ttu-id="da8e8-103">Après le chargement des données dans les tables intermédiaires de MDS, vous allez exécuter une procédure stockée associée à ces tables pour charger les données des tables intermédiaires vers les tables appropriées dans la base de données MDS.</span><span class="sxs-lookup"><span data-stu-id="da8e8-103">After loading data into the staging tables of MDS, you run a stored procedure associated with that table to load the data from staging into the appropriate tables in the MDS database.</span></span> <span data-ttu-id="da8e8-104">Cette procédure stockée nécessite deux paramètres : LogFlag et VersionName.</span><span class="sxs-lookup"><span data-stu-id="da8e8-104">This stored procedure has two required parameters that you need to pass: LogFlag and VersionName.</span></span> <span data-ttu-id="da8e8-105">LogFlag spécifie si les transactions sont journalisées pendant le processus intermédiaire et VersionName représente la version du modèle.</span><span class="sxs-lookup"><span data-stu-id="da8e8-105">LogFlag specifies whether transactions are logged during the staging process and VersionName represents the version of the model.</span></span> <span data-ttu-id="da8e8-106">Pour plus d’informations, consultez la rubrique [procédure stockée intermédiaire](https://msdn.microsoft.com/library/hh231028.aspx) .</span><span class="sxs-lookup"><span data-stu-id="da8e8-106">See [Staged Stored Procedure](https://msdn.microsoft.com/library/hh231028.aspx) topic for more details.</span></span>

 <span data-ttu-id="da8e8-107">Dans cette tâche, vous allez ajouter la tâche d'exécution SQL au flux de contrôle pour appeler la procédure stockée et charger les données intermédiaires dans les tables MDS appropriées.</span><span class="sxs-lookup"><span data-stu-id="da8e8-107">In this task, you add the Execute SQL Task to the control flow to invoke the stored procedure to load the staged data into appropriate MDS tables.</span></span>

1.  <span data-ttu-id="da8e8-108">Maintenant, basculez vers l’onglet **Flow Control** .</span><span class="sxs-lookup"><span data-stu-id="da8e8-108">Now, switch to the **Control Flow** tab.</span></span>

2.  <span data-ttu-id="da8e8-109">Glissez-déplacez la **tâche d’exécution SQL** de la **boîte à outils SSIS** vers l’onglet **Flow Control** .</span><span class="sxs-lookup"><span data-stu-id="da8e8-109">Drag-drop **Execute SQL Task** from the **SSIS Toolbox** to the **Control Flow** tab.</span></span>

3.  <span data-ttu-id="da8e8-110">Cliquez avec le bouton droit sur **tâche d’exécution SQL** dans l’onglet **contrôle** de la gestion, puis cliquez sur **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="da8e8-110">Right-click **Execute SQL Task** in the **Control Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="da8e8-111">Tapez **déclencher la procédure stockée pour charger des données dans MDS** et appuyez sur **entrée**.</span><span class="sxs-lookup"><span data-stu-id="da8e8-111">Type **Trigger Stored Procedure to Load Data into MDS** and press **ENTER**.</span></span>

4.  <span data-ttu-id="da8e8-112">Connectez **recevoir, nettoyer, faire correspondre et organiser les données des fournisseurs** pour **déclencher la procédure stockée et charger les données** à l’aide du connecteur vert.</span><span class="sxs-lookup"><span data-stu-id="da8e8-112">Connect **Receive, Cleanse, Match, and Curate Supplier Data** to **Trigger Stored Procedure to Load Data** using the green connector.</span></span>

     <span data-ttu-id="da8e8-113">![Connecter à la tâche d'exécution SQL](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-01.jpg "Connecter à la tâche d'exécution SQL")</span><span class="sxs-lookup"><span data-stu-id="da8e8-113">![Connect to Execute SQL Task](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-01.jpg "Connect to Execute SQL Task")</span></span>

5.  <span data-ttu-id="da8e8-114">À l’aide de la fenêtre **variables** , ajoutez deux nouvelles variables avec les paramètres suivants.</span><span class="sxs-lookup"><span data-stu-id="da8e8-114">Using the **Variables** window, add two new variables with the following settings.</span></span> <span data-ttu-id="da8e8-115">Si vous ne voyez pas la fenêtre **variables** , cliquez sur **SSIS** dans la barre de menus, puis cliquez sur **variables**.</span><span class="sxs-lookup"><span data-stu-id="da8e8-115">If you do not see the **Variables** window, click **SSIS** on the menu bar and click **Variables**.</span></span>

    |<span data-ttu-id="da8e8-116">Nom</span><span class="sxs-lookup"><span data-stu-id="da8e8-116">Name</span></span>|<span data-ttu-id="da8e8-117">Type de données</span><span class="sxs-lookup"><span data-stu-id="da8e8-117">Data Type</span></span>|<span data-ttu-id="da8e8-118">Valeur</span><span class="sxs-lookup"><span data-stu-id="da8e8-118">Value</span></span>|
    |----------|---------------|-----------|
    |<span data-ttu-id="da8e8-119">LogFlag</span><span class="sxs-lookup"><span data-stu-id="da8e8-119">LogFlag</span></span>|<span data-ttu-id="da8e8-120">Int32</span><span class="sxs-lookup"><span data-stu-id="da8e8-120">Int32</span></span>|<span data-ttu-id="da8e8-121">1</span><span class="sxs-lookup"><span data-stu-id="da8e8-121">1</span></span>|
    |<span data-ttu-id="da8e8-122">VersionName</span><span class="sxs-lookup"><span data-stu-id="da8e8-122">VersionName</span></span>|<span data-ttu-id="da8e8-123">String</span><span class="sxs-lookup"><span data-stu-id="da8e8-123">String</span></span>|<span data-ttu-id="da8e8-124">VERSION_1</span><span class="sxs-lookup"><span data-stu-id="da8e8-124">VERSION_1</span></span>|

     <span data-ttu-id="da8e8-125">![Fenêtre Variables SSIS.](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-02.jpg "Fenêtre Variables SSIS.")</span><span class="sxs-lookup"><span data-stu-id="da8e8-125">![SSIS Variables Window](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-02.jpg "SSIS Variables Window")</span></span>

6.  <span data-ttu-id="da8e8-126">Double-cliquez sur **déclencher une procédure stockée pour charger des données dans MDS**.</span><span class="sxs-lookup"><span data-stu-id="da8e8-126">Double-click **Trigger Stored Procedure to Load Data into MDS**.</span></span>

7.  <span data-ttu-id="da8e8-127">Dans la boîte de dialogue **éditeur de tâche d’exécution de SQL** , sélectionnez **(local). MDS** (ou **localhost. MDS**) pour la **connexion**.</span><span class="sxs-lookup"><span data-stu-id="da8e8-127">In the **Execute SQL Task Editor** dialog box, select **(local).MDS** (or **localhost.MDS**) for **Connection**.</span></span>

8.  <span data-ttu-id="da8e8-128">Tapez **exec [STG]. [ udp_Supplier_Leaf] ?, ?, ?**</span><span class="sxs-lookup"><span data-stu-id="da8e8-128">Type **EXEC [stg].[udp_Supplier_Leaf] ?, ?, ?**</span></span> <span data-ttu-id="da8e8-129">pour l' **instruction SQL**.</span><span class="sxs-lookup"><span data-stu-id="da8e8-129">for **SQL Statement**.</span></span> <span data-ttu-id="da8e8-130">Vérifiez le nom à l'aide de SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="da8e8-130">You can verify the name by using SQL Server Management Studio.</span></span>

     <span data-ttu-id="da8e8-131">![Boîte de dialogue Éditeur de tâche d'exécution SQL - Paramètres généraux](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-03.jpg "Boîte de dialogue Éditeur de tâche d'exécution SQL - Paramètres généraux")</span><span class="sxs-lookup"><span data-stu-id="da8e8-131">![Execute SQL Editor Dialog Box - General Settings](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-03.jpg "Execute SQL Editor Dialog Box - General Settings")</span></span>

9. <span data-ttu-id="da8e8-132">Cliquez sur **mappage des paramètres** dans le menu de gauche.</span><span class="sxs-lookup"><span data-stu-id="da8e8-132">Click **Parameter Mapping** from the menu on left.</span></span>

10. <span data-ttu-id="da8e8-133">Dans la page **mappage de paramètre** , cliquez sur **Ajouter** pour ajouter un mappage.</span><span class="sxs-lookup"><span data-stu-id="da8e8-133">In the **Parameter Mapping** page, click **Add** to add a mapping.</span></span> <span data-ttu-id="da8e8-134">Agrandissez la fenêtre et redimensionnez les colonnes afin de voir correctement les valeurs dans les listes déroulantes.</span><span class="sxs-lookup"><span data-stu-id="da8e8-134">Maximize the window and resize columns so that you can see values in drop-down lists properly.</span></span>

11. <span data-ttu-id="da8e8-135">Sélectionnez **User :: VersionName** dans la liste déroulante correspondant au **nom**de la variable.</span><span class="sxs-lookup"><span data-stu-id="da8e8-135">Select **User::VersionName** from the drop-down list for the **Variable Name**.</span></span>

12. <span data-ttu-id="da8e8-136">Sélectionnez **nvarchar** pour **type de données**.</span><span class="sxs-lookup"><span data-stu-id="da8e8-136">Select **NVARCHAR** for **Data Type**.</span></span>

13. <span data-ttu-id="da8e8-137">Tapez **0** (zéro) comme **nom de paramètre**.</span><span class="sxs-lookup"><span data-stu-id="da8e8-137">Type **0** (zero) for **Parameter Name**.</span></span>

14. <span data-ttu-id="da8e8-138">Répétez les quatre étapes précédentes pour ajouter deux variables supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="da8e8-138">Repeat the previous four steps to add two more variables.</span></span>

    |<span data-ttu-id="da8e8-139">Nom de la variable</span><span class="sxs-lookup"><span data-stu-id="da8e8-139">Variable Name</span></span>|<span data-ttu-id="da8e8-140">Type de données (important)</span><span class="sxs-lookup"><span data-stu-id="da8e8-140">Data Type (important)</span></span>|<span data-ttu-id="da8e8-141">Nom du paramètre</span><span class="sxs-lookup"><span data-stu-id="da8e8-141">Parameter Name</span></span>|
    |-------------------|-----------------------------|--------------------|
    |<span data-ttu-id="da8e8-142">User::LogFlag</span><span class="sxs-lookup"><span data-stu-id="da8e8-142">User::LogFlag</span></span>|<span data-ttu-id="da8e8-143">LONG</span><span class="sxs-lookup"><span data-stu-id="da8e8-143">LONG</span></span>|<span data-ttu-id="da8e8-144">1</span><span class="sxs-lookup"><span data-stu-id="da8e8-144">1</span></span>|
    |<span data-ttu-id="da8e8-145">User::BatchTag</span><span class="sxs-lookup"><span data-stu-id="da8e8-145">User::BatchTag</span></span>|<span data-ttu-id="da8e8-146">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="da8e8-146">NVARCHAR</span></span>|<span data-ttu-id="da8e8-147">2</span><span class="sxs-lookup"><span data-stu-id="da8e8-147">2</span></span>|

     <span data-ttu-id="da8e8-148">![Éditeur de tâche d'exécution de SQL - Mappage de paramètre](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-04.jpg "Éditeur de tâche d'exécution de SQL - Mappage de paramètre")</span><span class="sxs-lookup"><span data-stu-id="da8e8-148">![Execute SQL Task Editor - Parameter Mapping](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-04.jpg "Execute SQL Task Editor - Parameter Mapping")</span></span>

15. <span data-ttu-id="da8e8-149">Cliquez sur **OK** pour fermer la boîte de dialogue **éditeur SQL d’exécution** .</span><span class="sxs-lookup"><span data-stu-id="da8e8-149">Click **OK** to close the **Execute SQL Editor** dialog box.</span></span>

## <a name="next-step"></a><span data-ttu-id="da8e8-150">étape suivante</span><span class="sxs-lookup"><span data-stu-id="da8e8-150">Next Step</span></span>
 [<span data-ttu-id="da8e8-151">Tâche 15 : Génération et exécution du projet SSIS</span><span class="sxs-lookup"><span data-stu-id="da8e8-151">Task 15: Building and Running the SSIS Project</span></span>](../../2014/tutorials/task-15-building-and-running-the-ssis-project.md)


