---
title: Aide sur l’Assistant Gestion de partition via la touche F1 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.managepartition.getstart.f1
- sql12.swb.managepartition.selectoutput.f1
- sql12.swb.managepartition.partitionaction.f1
- sql12.swb.managepartition.switchout.f1
- sql12.swb.managepartition.summary.f1
- sql12.swb.managepartition.createjob.f1
- sql12.swb.managepartition.stagingtable.f1
- sql12.swb.managepartition.progress.f1
- sql12.swb.managepartition.switchin.f1
- sql12.swb.managepartition.selectswitchtables.f1
helpviewer_keywords:
- wizards [SQL Server Management Studio] See Manage Partition Wizard
ms.assetid: e2478d26-dea4-428d-98c5-aad2d2a30da8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 09b3e774168e9a48a0a387c3474b29f96081d875
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696784"
---
# <a name="manage-partition-wizard-f1-help"></a><span data-ttu-id="e41aa-102">Aide sur l'Assistant Gestion de partition via la touche F1</span><span class="sxs-lookup"><span data-stu-id="e41aa-102">Manage Partition Wizard F1 Help</span></span>
  <span data-ttu-id="e41aa-103">Utilisez l’ **Assistant Gestion de partition** pour gérer et modifier des tables partitionnées existantes via le basculement de partition ou l’implémentation d’un scénario de fenêtre glissante.</span><span class="sxs-lookup"><span data-stu-id="e41aa-103">Use the **Manage Partition Wizard** to manage and modify existing partitioned tables through partition switching or the implementation of a sliding window scenario.</span></span> <span data-ttu-id="e41aa-104">Cet Assistant peut faciliter la gestion de vos partitions et simplifier la migration régulière de données vers et à partir de vos tables.</span><span class="sxs-lookup"><span data-stu-id="e41aa-104">This wizard can ease the management of your partitions and simplify the regular migration of data in and out of your tables.</span></span>  
  
### <a name="to-start-the-manage-partition-wizard"></a><span data-ttu-id="e41aa-105">Pour démarrer l'Assistant Gestion de partition</span><span class="sxs-lookup"><span data-stu-id="e41aa-105">To start the Manage Partition Wizard</span></span>  
  
-   <span data-ttu-id="e41aa-106">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], sélectionnez la base de données, cliquez avec le bouton droit sur la table sur laquelle vous souhaitez créer des partitions, pointez sur **Stockage**, puis cliquez sur **Gérer la partition**.</span><span class="sxs-lookup"><span data-stu-id="e41aa-106">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the database, right-click the table on which you want to create partitions, point to **Storage**, and then click **Manage Partition**.</span></span>  
  
     <span data-ttu-id="e41aa-107">`Note`Si **gérer la partition** n’est pas disponible, vous avez peut-être sélectionné une table qui ne contient pas de partitions.</span><span class="sxs-lookup"><span data-stu-id="e41aa-107">`Note` If **Manage Partition** is unavailable, you may have selected a table that does not contain partitions.</span></span> <span data-ttu-id="e41aa-108">Cliquez sur **Créer la partition** dans le sous-menu **Stockage** et utilisez l’ **Assistant Création de partition** pour créer des partitions dans votre table.</span><span class="sxs-lookup"><span data-stu-id="e41aa-108">Click **Create Partition** on the **Storage** submenu and use the **Create Partition Wizard** to create partitions in your table.</span></span>  
  
 <span data-ttu-id="e41aa-109">Pour obtenir des informations générales sur les partitions et les index, consultez [Tables et index partitionnés](partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="e41aa-109">For general information about partitions and indexes, see [Partitioned Tables and Indexes](partitioned-tables-and-indexes.md).</span></span>  
  
 <span data-ttu-id="e41aa-110">Cette section fournit les informations requises pour gérer, modifier et implémenter des partitions à l’aide de l’ **Assistant Gestion de partition**.</span><span class="sxs-lookup"><span data-stu-id="e41aa-110">This section provides the information that is required to manage, modify, and implement partitions using the **Manage Partition Wizard**.</span></span>  
  
##  <a name="in-this-section"></a><a name="Top"></a> <span data-ttu-id="e41aa-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="e41aa-111">In This Section</span></span>  
 <span data-ttu-id="e41aa-112">Les sections ci-dessous fournissent de l’aide sur les pages de l’ **Assistant Gestion de partition**.</span><span class="sxs-lookup"><span data-stu-id="e41aa-112">The following sections provide help on the pages of the **Manage Partition Wizard**.</span></span>  
  
 [<span data-ttu-id="e41aa-113">Assistant Gestion de partition (page Sélectionnez une action de partition)</span><span class="sxs-lookup"><span data-stu-id="e41aa-113">Manage Partition Wizard (Select Partition Action Page)</span></span>](#SelectPartitionAction)  
  
 [<span data-ttu-id="e41aa-114">Assistant Gestion de partition (page Insérer)</span><span class="sxs-lookup"><span data-stu-id="e41aa-114">Manage Partition Wizard (Switch In Page)</span></span>](#SwitchIn)  
  
 [<span data-ttu-id="e41aa-115">Assistant Gestion de partition (page Extraire)</span><span class="sxs-lookup"><span data-stu-id="e41aa-115">Manage Partition Wizard (Switch Out Page)</span></span>](#SwitchOut)  
  
 [<span data-ttu-id="e41aa-116">Assistant Gestion de partition (page Sélectionner les options de table intermédiaire)</span><span class="sxs-lookup"><span data-stu-id="e41aa-116">Manage Partition Wizard (Select Staging Table Options Page)</span></span>](#StagingTableOptions)  
  
 [<span data-ttu-id="e41aa-117">Assistant Gestion de partition (page Sélectionner une option de sortie)</span><span class="sxs-lookup"><span data-stu-id="e41aa-117">Manage Partition Wizard (Select Output Option Page)</span></span>](#OutputOption)  
  
 [<span data-ttu-id="e41aa-118">Assistant Gestion de partition (page Nouvelle planification du travail)</span><span class="sxs-lookup"><span data-stu-id="e41aa-118">Manage Partition Wizard (New Job Schedule Page)</span></span>](#NewJob)  
  
 [<span data-ttu-id="e41aa-119">Assistant Gestion de partition (page Résumé)</span><span class="sxs-lookup"><span data-stu-id="e41aa-119">Manage Partition Wizard (Summary Page)</span></span>](#Summary)  
  
 [<span data-ttu-id="e41aa-120">Assistant Gestion de partition (page Progression)</span><span class="sxs-lookup"><span data-stu-id="e41aa-120">Manage Partition Wizard (Progress Page)</span></span>](#Progress)  
  
##  <a name="select-partition-action-page"></a><a name="SelectPartitionAction"></a> <span data-ttu-id="e41aa-121">Page Sélectionnez une action de partition</span><span class="sxs-lookup"><span data-stu-id="e41aa-121">Select Partition Action Page</span></span>  
 <span data-ttu-id="e41aa-122">Utilisez la page **Sélectionnez une action de partition** pour choisir l’action à effectuer sur votre partition.</span><span class="sxs-lookup"><span data-stu-id="e41aa-122">Use the **Select Partition Action** page to choose the action you want to perform on your partition.</span></span>  
  
### <a name="create-a-staging-table"></a><span data-ttu-id="e41aa-123">Créer une table intermédiaire</span><span class="sxs-lookup"><span data-stu-id="e41aa-123">Create a Staging Table</span></span>  
 <span data-ttu-id="e41aa-124">Le basculement de partition est une tâche de partitionnement courante si vous disposez d'une table partitionnée vers ou à partir de laquelle vous faites régulièrement migrer des données ; il peut par exemple s'agir d'une table partitionnée qui stocke des données du trimestre actuel, que vous devez alimenter en nouvelles données et dont vous devez archiver les anciennes données à la fin de chaque trimestre.</span><span class="sxs-lookup"><span data-stu-id="e41aa-124">Partition switching is a common partitioning task if you have a partitioned table that you migrate data into and out of on a regular basis; for example, you have a partitioned table that stores current quarterly data, and you must move in new data and archive older data at the end of each quarter.</span></span>  
  
 <span data-ttu-id="e41aa-125">L'Assistant conçoit la table intermédiaire avec les mêmes colonne de partitionnement, structure de tables et de colonnes, et index, et stocke la nouvelle table dans le groupe de fichiers où se trouve votre partition source.</span><span class="sxs-lookup"><span data-stu-id="e41aa-125">The wizard designs the staging table with the same partitioning column, table and column structure, and indexes, and stores the new table in the filegroup where your source partition is located.</span></span>  
  
 <span data-ttu-id="e41aa-126">Pour créer une table intermédiaire pour insérer ou extraire des données de partition, sélectionnez **Créer une table intermédiaire pour le basculement de partition**.</span><span class="sxs-lookup"><span data-stu-id="e41aa-126">To create a staging table to switch in or switch out partition data, select **Create a staging table for partition switching**.</span></span>  
  
### <a name="sliding-window-scenario"></a><span data-ttu-id="e41aa-127">Scénario de fenêtre glissante</span><span class="sxs-lookup"><span data-stu-id="e41aa-127">Sliding Window Scenario</span></span>  
 <span data-ttu-id="e41aa-128">Pour gérer vos partitions dans un scénario de fenêtre défilante, sélectionnez **Gérer les données partitionnées dans un scénario de fenêtre glissante**.</span><span class="sxs-lookup"><span data-stu-id="e41aa-128">To manage your partitions in a sliding-window scenario, select **Manage partitioned data in a sliding window scenario**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="e41aa-129">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="e41aa-129">UI element list</span></span>  
 <span data-ttu-id="e41aa-130">**Créer une table intermédiaire pour le basculement de partition**</span><span class="sxs-lookup"><span data-stu-id="e41aa-130">**Create a staging table for partition switching**</span></span>  
 <span data-ttu-id="e41aa-131">Crée une table intermédiaire pour les données que vous insérez ou extrayez dans la table partitionnée existante.</span><span class="sxs-lookup"><span data-stu-id="e41aa-131">Creates a staging table for the data you are switching in or switching out of the existing partitioned table.</span></span>  
  
 <span data-ttu-id="e41aa-132">**Extraire une partition**</span><span class="sxs-lookup"><span data-stu-id="e41aa-132">**Switch out partition**</span></span>  
 <span data-ttu-id="e41aa-133">Fournit des options lors de la suppression d'une partition de la table.</span><span class="sxs-lookup"><span data-stu-id="e41aa-133">Provides options when removing a partition from the table.</span></span>  
  
 <span data-ttu-id="e41aa-134">**Insérer une partition**</span><span class="sxs-lookup"><span data-stu-id="e41aa-134">**Switch in partition**</span></span>  
 <span data-ttu-id="e41aa-135">Fournit des options lors de l'ajout d'une partition à la table.</span><span class="sxs-lookup"><span data-stu-id="e41aa-135">Provides options when adding a partition to the table.</span></span>  
  
 <span data-ttu-id="e41aa-136">**Gérer les données partitionnées dans un scénario de fenêtre glissante**</span><span class="sxs-lookup"><span data-stu-id="e41aa-136">**Manage partitioned data in a sliding window scenario**</span></span>  
 <span data-ttu-id="e41aa-137">Ajoute à la table existante une partition vide qui peut être utilisée pour l'insertion de données.</span><span class="sxs-lookup"><span data-stu-id="e41aa-137">Appends an empty partition to the existing table that can be used for switching in data.</span></span> <span data-ttu-id="e41aa-138">L'Assistant prend actuellement en charge l'insertion dans la dernière partition et l'extraction de la première partition.</span><span class="sxs-lookup"><span data-stu-id="e41aa-138">The wizard currently supports switching into the last partition and switching out the first partition.</span></span>  
  
 <span data-ttu-id="e41aa-139">![Icône de flèche utilisée avec le lien Retour en haut](../../2014-toc/media/uparrow16x16.gif "Icône de flèche utilisée avec le lien Retour en haut") [Dans cette section](#Top)</span><span class="sxs-lookup"><span data-stu-id="e41aa-139">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-partition-switching-in-options-page"></a><a name="SwitchIn"></a> <span data-ttu-id="e41aa-140">Page Sélectionner les options d'insertion de partition</span><span class="sxs-lookup"><span data-stu-id="e41aa-140">Select Partition Switching-In Options Page</span></span>  
 <span data-ttu-id="e41aa-141">Utilisez la page **Sélectionner les options d’insertion de partition** pour sélectionner la table de mise en lots que vous insérez dans la table partitionnée.</span><span class="sxs-lookup"><span data-stu-id="e41aa-141">Use the **Select Partition Switching-In options** page to select the staging table you are switching into the partitioned table.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="e41aa-142">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="e41aa-142">UI element list</span></span>  
 <span data-ttu-id="e41aa-143">**Afficher toutes les partitions**</span><span class="sxs-lookup"><span data-stu-id="e41aa-143">**Show All Partitions**</span></span>  
 <span data-ttu-id="e41aa-144">Sélectionnez cette option pour afficher toutes les partitions, notamment les partitions figurant actuellement dans la table partitionnée.</span><span class="sxs-lookup"><span data-stu-id="e41aa-144">Select to show all partitions, including the partitions currently in the partitioned table.</span></span>  
  
 <span data-ttu-id="e41aa-145">**Grille de partition**</span><span class="sxs-lookup"><span data-stu-id="e41aa-145">**Partition grid**</span></span>  
 <span data-ttu-id="e41aa-146">Affiche le nom des partitions, ainsi que les informations **Limite gauche**, **Limite droite**, **Groupe de fichiers**et **Nombre de lignes** des partitions que vous avez sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="e41aa-146">Displays the partition name, **Left boundary**, **Right boundary**, **Filegroup**, and **Row count** of the partitions you selected.</span></span>  
  
 <span data-ttu-id="e41aa-147">**Table d'insertion**</span><span class="sxs-lookup"><span data-stu-id="e41aa-147">**Switch in table**</span></span>  
 <span data-ttu-id="e41aa-148">Sélectionnez la table intermédiaire qui contient la partition que vous souhaitez ajouter à votre table partitionnée.</span><span class="sxs-lookup"><span data-stu-id="e41aa-148">Select the staging table that contains the partition that you want to add to your partitioned table.</span></span> <span data-ttu-id="e41aa-149">Vous devez créer cette table de mise en lots avec l’ **Assistant Gestion de partition**avant d’insérer des partitions.</span><span class="sxs-lookup"><span data-stu-id="e41aa-149">You must create this staging table before you switch-in partitions with the **Manage PartitionsWizard**.</span></span>  
  
 <span data-ttu-id="e41aa-150">![Icône de flèche utilisée avec le lien Retour en haut](../../2014-toc/media/uparrow16x16.gif "Icône de flèche utilisée avec le lien Retour en haut") [Dans cette section](#Top)</span><span class="sxs-lookup"><span data-stu-id="e41aa-150">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-partition-switching-out-options-page"></a><a name="SwitchOut"></a> <span data-ttu-id="e41aa-151">Page Sélectionner les options d'extraction de partition</span><span class="sxs-lookup"><span data-stu-id="e41aa-151">Select Partition Switching-Out Options Page</span></span>  
 <span data-ttu-id="e41aa-152">Utilisez la page **Sélectionner les options d’extraction de partition** pour sélectionner la partition et la table de mise en lots destinées à maintenir les données partitionnées que vous extrayez de la table partitionnée.</span><span class="sxs-lookup"><span data-stu-id="e41aa-152">Use the **Select Partition Switching-Out options** page to select the partition and the staging table to hold the partitioned data that you are switching out of the partitioned table.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="e41aa-153">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="e41aa-153">UI element list</span></span>  
 <span data-ttu-id="e41aa-154">**Grille de partition**</span><span class="sxs-lookup"><span data-stu-id="e41aa-154">**Partition grid**</span></span>  
 <span data-ttu-id="e41aa-155">Affiche le nom des partitions, ainsi que les informations **Limite gauche**, **Limite droite**, **Groupe de fichiers**et **Nombre de lignes** des partitions que vous avez sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="e41aa-155">Displays the partition name, **Left boundary**, **Right boundary**, **Filegroup**, and **Row count** of the partitions you selected.</span></span>  
  
 <span data-ttu-id="e41aa-156">**Table d'extraction**</span><span class="sxs-lookup"><span data-stu-id="e41aa-156">**Switch out table**</span></span>  
 <span data-ttu-id="e41aa-157">Choisissez une nouvelle table ou une table existante vers laquelle extraire vos données.</span><span class="sxs-lookup"><span data-stu-id="e41aa-157">Choose a new table or an existing table to switch-out your data to.</span></span>  
  
 <span data-ttu-id="e41aa-158">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="e41aa-158">**New**</span></span>  
 <span data-ttu-id="e41aa-159">Entrez un nouveau nom pour la table intermédiaire à utiliser pour la partition à extraire de la table source actuelle.</span><span class="sxs-lookup"><span data-stu-id="e41aa-159">Enter a new name for the staging table you want to use for the partition to switch out of the current source table.</span></span>  
  
 <span data-ttu-id="e41aa-160">**Existant**</span><span class="sxs-lookup"><span data-stu-id="e41aa-160">**Existing**</span></span>  
 <span data-ttu-id="e41aa-161">Sélectionnez la table intermédiaire à utiliser pour la partition à extraire de la table source actuelle.</span><span class="sxs-lookup"><span data-stu-id="e41aa-161">Select an existing staging table you want to use for the partition you want to switch out of the current source table.</span></span> <span data-ttu-id="e41aa-162">Si la table existante contient des données, ces données seront remplacées par celles que vous extrayez.</span><span class="sxs-lookup"><span data-stu-id="e41aa-162">If the existing table contains data, this data will be overwritten with the data you are switching out.</span></span>  
  
 <span data-ttu-id="e41aa-163">![Icône de flèche utilisée avec le lien Retour en haut](../../2014-toc/media/uparrow16x16.gif "Icône de flèche utilisée avec le lien Retour en haut") [Dans cette section](#Top)</span><span class="sxs-lookup"><span data-stu-id="e41aa-163">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-the-staging-table-options-page"></a><a name="StagingTableOptions"></a> <span data-ttu-id="e41aa-164">Page Sélectionner les options de table de mise en lots</span><span class="sxs-lookup"><span data-stu-id="e41aa-164">Select the Staging Table Options Page</span></span>  
 <span data-ttu-id="e41aa-165">Utilisez la page **Sélectionner les options de table de mise en lots** pour créer la table de mise en lots à utiliser pour basculer vos données partitionnées.</span><span class="sxs-lookup"><span data-stu-id="e41aa-165">Use the **Select the Staging Table Options** page to create the staging table you want to use for switching your partitioned data.</span></span>  
  
 <span data-ttu-id="e41aa-166">Les tables intermédiaires doivent résider dans le même groupe de fichiers que la partition sélectionnée où se trouve la table source.</span><span class="sxs-lookup"><span data-stu-id="e41aa-166">Staging tables must reside in the same filegroup of the selected partition where the source table is located.</span></span> <span data-ttu-id="e41aa-167">La table intermédiaire doit refléter la conception des tables source et de destination.</span><span class="sxs-lookup"><span data-stu-id="e41aa-167">The staging table must mirror the design of both the source table and the destination table.</span></span>  
  
 <span data-ttu-id="e41aa-168">Vous pouvez également créer les mêmes index dans la table intermédiaire que dans la partition source.</span><span class="sxs-lookup"><span data-stu-id="e41aa-168">You can also create the same indexes in the staging table that exist in the source partition.</span></span> <span data-ttu-id="e41aa-169">La table intermédiaire contient automatiquement une contrainte basée sur les éléments de la partition source.</span><span class="sxs-lookup"><span data-stu-id="e41aa-169">The staging table automatically contains a constraint based on the elements of the source partition.</span></span> <span data-ttu-id="e41aa-170">Cette contrainte est généralement générée à partir de la valeur limite de la partition source.</span><span class="sxs-lookup"><span data-stu-id="e41aa-170">This constraint is typically generated from the boundary value of the source partition.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="e41aa-171">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="e41aa-171">UI element list</span></span>  
 <span data-ttu-id="e41aa-172">**Nom de la table intermédiaire**</span><span class="sxs-lookup"><span data-stu-id="e41aa-172">**Staging table name**</span></span>  
 <span data-ttu-id="e41aa-173">Créez un nom pour la table intermédiaire ou acceptez le nom par défaut affiché dans la zone d'édition.</span><span class="sxs-lookup"><span data-stu-id="e41aa-173">Create a name for the staging table or accept the default name displayed in the edit box.</span></span>  
  
 <span data-ttu-id="e41aa-174">**Basculer la partition**</span><span class="sxs-lookup"><span data-stu-id="e41aa-174">**Switch partition**</span></span>  
 <span data-ttu-id="e41aa-175">Sélectionnez la partition source que vous souhaitez extraire de la table actuelle.</span><span class="sxs-lookup"><span data-stu-id="e41aa-175">Select the source partition that you want to switch out of the current table.</span></span>  
  
 <span data-ttu-id="e41aa-176">**Nouvelle valeur limite**</span><span class="sxs-lookup"><span data-stu-id="e41aa-176">**New boundary value**</span></span>  
 <span data-ttu-id="e41aa-177">Sélectionnez ou entrez la valeur limite voulue pour la partition dans la table intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="e41aa-177">Select or enter the boundary value you want for the partition in the staging table.</span></span>  
  
 <span data-ttu-id="e41aa-178">**Groupe de fichiers**</span><span class="sxs-lookup"><span data-stu-id="e41aa-178">**Filegroup**</span></span>  
 <span data-ttu-id="e41aa-179">Sélectionnez un groupe de fichiers pour la nouvelle table.</span><span class="sxs-lookup"><span data-stu-id="e41aa-179">Select a filegroup for the new table.</span></span>  
  
 <span data-ttu-id="e41aa-180">![Icône de flèche utilisée avec le lien Retour en haut](../../2014-toc/media/uparrow16x16.gif "Icône de flèche utilisée avec le lien Retour en haut") [Dans cette section](#Top)</span><span class="sxs-lookup"><span data-stu-id="e41aa-180">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-output-option-page"></a><a name="OutputOption"></a> <span data-ttu-id="e41aa-181">Page Sélectionner une option de sortie</span><span class="sxs-lookup"><span data-stu-id="e41aa-181">Select Output Option Page</span></span>  
 <span data-ttu-id="e41aa-182">Utilisez la page **Sélectionner une option de sortie** pour spécifier de quelle manière vous souhaitez apporter les modifications à vos partitions.</span><span class="sxs-lookup"><span data-stu-id="e41aa-182">Use the **Select Output Option** page to specify how you want to complete the modifications to your partitions.</span></span>  
  
### <a name="create-script"></a><span data-ttu-id="e41aa-183">Créer un script</span><span class="sxs-lookup"><span data-stu-id="e41aa-183">Create Script</span></span>  
 <span data-ttu-id="e41aa-184">Une fois qu'il a terminé, l'Assistant crée un script dans l'éditeur de requête afin de modifier des partitions dans la table.</span><span class="sxs-lookup"><span data-stu-id="e41aa-184">When the wizard finishes, it creates a script in Query Editor to modify partitions in the table.</span></span> <span data-ttu-id="e41aa-185">Sélectionnez **Créer un script** si vous souhaitez revoir le script, puis l’exécuter manuellement.</span><span class="sxs-lookup"><span data-stu-id="e41aa-185">Select **Create Script** if you want to review the script, and then execute the script manually.</span></span>  
  
 <span data-ttu-id="e41aa-186">**Générer un script sur fichier**</span><span class="sxs-lookup"><span data-stu-id="e41aa-186">**Script to file**</span></span>  
 <span data-ttu-id="e41aa-187">Génère le script sur un fichier .sql.</span><span class="sxs-lookup"><span data-stu-id="e41aa-187">Generate the script to a .sql file.</span></span> <span data-ttu-id="e41aa-188">Spécifiez **Unicode** ou **Texte ANSI**.</span><span class="sxs-lookup"><span data-stu-id="e41aa-188">Specify either **Unicode** or **ANSI text**.</span></span> <span data-ttu-id="e41aa-189">Pour indiquer le nom et l’emplacement du fichier, cliquez sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="e41aa-189">To specify a name and location for the file, click **Browse**.</span></span>  
  
 <span data-ttu-id="e41aa-190">**Générer un script sur le Presse-papiers**</span><span class="sxs-lookup"><span data-stu-id="e41aa-190">**Script to Clipboard**</span></span>  
 <span data-ttu-id="e41aa-191">Enregistrez le script dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="e41aa-191">Save the script to the Clipboard.</span></span>  
  
 <span data-ttu-id="e41aa-192">**Générer un script dans une nouvelle fenêtre de requête**</span><span class="sxs-lookup"><span data-stu-id="e41aa-192">**Script to New Query Window**</span></span>  
 <span data-ttu-id="e41aa-193">Générez le script dans une fenêtre de l'éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="e41aa-193">Generate the script to a Query Editor window.</span></span> <span data-ttu-id="e41aa-194">Si aucune fenêtre d'éditeur n'est ouverte, une nouvelle fenêtre s'ouvre comme cible du script.</span><span class="sxs-lookup"><span data-stu-id="e41aa-194">If no editor window is open, a new editor window opens as the target for the script.</span></span>  
  
### <a name="run-immediately"></a><span data-ttu-id="e41aa-195">Exécuter immédiatement</span><span class="sxs-lookup"><span data-stu-id="e41aa-195">Run Immediately</span></span>  
 <span data-ttu-id="e41aa-196">**Run immediately**</span><span class="sxs-lookup"><span data-stu-id="e41aa-196">**Run immediately**</span></span>  
 <span data-ttu-id="e41aa-197">Indique à l’Assistant de terminer les modifications de partitions lorsque vous cliquez sur **Suivant** ou **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="e41aa-197">Have the wizard finish modifications to the partitions when you click **Next** or **Finish**.</span></span>  
  
### <a name="schedule"></a><span data-ttu-id="e41aa-198">Planifier</span><span class="sxs-lookup"><span data-stu-id="e41aa-198">Schedule</span></span>  
 <span data-ttu-id="e41aa-199">Sélectionnez cette option pour modifier les partitions de table à des date et heure planifiées.</span><span class="sxs-lookup"><span data-stu-id="e41aa-199">Select to modify the table partitions at a scheduled date and time.</span></span>  
  
 <span data-ttu-id="e41aa-200">**Modifier la planification**</span><span class="sxs-lookup"><span data-stu-id="e41aa-200">**Change schedule**</span></span>  
 <span data-ttu-id="e41aa-201">Ouvre la boîte de dialogue **Nouvelle planification du travail** , dans laquelle vous pouvez sélectionner, modifier ou consulter les propriétés du travail planifié.</span><span class="sxs-lookup"><span data-stu-id="e41aa-201">Opens the **New Job Schedule** dialog box, where you can select, change, or view the properties of the scheduled job.</span></span>  
  
 <span data-ttu-id="e41aa-202">![Icône de flèche utilisée avec le lien Retour en haut](../../2014-toc/media/uparrow16x16.gif "Icône de flèche utilisée avec le lien Retour en haut") [Dans cette section](#Top)</span><span class="sxs-lookup"><span data-stu-id="e41aa-202">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="new-job-schedule-page"></a><a name="NewJob"></a> <span data-ttu-id="e41aa-203">Page Nouvelle planification du travail</span><span class="sxs-lookup"><span data-stu-id="e41aa-203">New Job Schedule Page</span></span>  
 <span data-ttu-id="e41aa-204">Utilisez la page **Nouvelle planification du travail** pour afficher et modifier les propriétés de la planification.</span><span class="sxs-lookup"><span data-stu-id="e41aa-204">Use the **New Job Schedule** page to view and change the properties of the schedule.</span></span>  
  
### <a name="options"></a><span data-ttu-id="e41aa-205">Options</span><span class="sxs-lookup"><span data-stu-id="e41aa-205">Options</span></span>  
 <span data-ttu-id="e41aa-206">Sélectionnez le type de planification qui vous intéresse pour le travail de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e41aa-206">Select the type of schedule you want for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>  
  
 <span data-ttu-id="e41aa-207">**Nom**</span><span class="sxs-lookup"><span data-stu-id="e41aa-207">**Name**</span></span>  
 <span data-ttu-id="e41aa-208">Tapez un nouveau nom pour la planification.</span><span class="sxs-lookup"><span data-stu-id="e41aa-208">Type a new name for the schedule.</span></span>  
  
 <span data-ttu-id="e41aa-209">**Travaux planifiés**</span><span class="sxs-lookup"><span data-stu-id="e41aa-209">**Jobs in schedule**</span></span>  
 <span data-ttu-id="e41aa-210">Indique les travaux existants qui utilisent la planification.</span><span class="sxs-lookup"><span data-stu-id="e41aa-210">View the existing jobs that use the schedule.</span></span>  
  
 <span data-ttu-id="e41aa-211">**Type de planification**</span><span class="sxs-lookup"><span data-stu-id="e41aa-211">**Schedule type**</span></span>  
 <span data-ttu-id="e41aa-212">Permet de sélectionner le type de planification.</span><span class="sxs-lookup"><span data-stu-id="e41aa-212">Select the type of schedule.</span></span>  
  
 <span data-ttu-id="e41aa-213">**Activé**</span><span class="sxs-lookup"><span data-stu-id="e41aa-213">**Enabled**</span></span>  
 <span data-ttu-id="e41aa-214">Permet d'activer ou de désactiver la planification.</span><span class="sxs-lookup"><span data-stu-id="e41aa-214">Enable or disable the schedule.</span></span>  
  
### <a name="recurring-schedule-types-options"></a><span data-ttu-id="e41aa-215">Options des types de planification périodique</span><span class="sxs-lookup"><span data-stu-id="e41aa-215">Recurring Schedule Types Options</span></span>  
 <span data-ttu-id="e41aa-216">Permet de sélectionner la fréquence du travail planifié.</span><span class="sxs-lookup"><span data-stu-id="e41aa-216">Select the frequency of the scheduled job.</span></span>  
  
 <span data-ttu-id="e41aa-217">**Périodicité**</span><span class="sxs-lookup"><span data-stu-id="e41aa-217">**Occurs**</span></span>  
 <span data-ttu-id="e41aa-218">Permet de sélectionner l'intervalle après lequel la planification se répète.</span><span class="sxs-lookup"><span data-stu-id="e41aa-218">Select the interval at which the schedule recurs.</span></span>  
  
 <span data-ttu-id="e41aa-219">**Répéter à chaque**</span><span class="sxs-lookup"><span data-stu-id="e41aa-219">**Recurs every**</span></span>  
 <span data-ttu-id="e41aa-220">Permet de sélectionner le nombre de jours ou de semaines entre deux occurrences de la planification.</span><span class="sxs-lookup"><span data-stu-id="e41aa-220">Select the number of days or weeks between recurrences of the schedule.</span></span> <span data-ttu-id="e41aa-221">Cette option n'est pas disponible pour les planifications mensuelles.</span><span class="sxs-lookup"><span data-stu-id="e41aa-221">This option is not available for monthly schedules.</span></span>  
  
 <span data-ttu-id="e41aa-222">**Lundi**</span><span class="sxs-lookup"><span data-stu-id="e41aa-222">**Monday**</span></span>  
 <span data-ttu-id="e41aa-223">Exécute le travail le lundi.</span><span class="sxs-lookup"><span data-stu-id="e41aa-223">Set the job to occur on a Monday.</span></span> <span data-ttu-id="e41aa-224">Disponible uniquement pour les planifications hebdomadaires.</span><span class="sxs-lookup"><span data-stu-id="e41aa-224">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="e41aa-225">**Mardi**</span><span class="sxs-lookup"><span data-stu-id="e41aa-225">**Tuesday**</span></span>  
 <span data-ttu-id="e41aa-226">Exécute le travail le mardi.</span><span class="sxs-lookup"><span data-stu-id="e41aa-226">Set the job to occur on a Tuesday.</span></span> <span data-ttu-id="e41aa-227">Disponible uniquement pour les planifications hebdomadaires.</span><span class="sxs-lookup"><span data-stu-id="e41aa-227">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="e41aa-228">**Mercredi**</span><span class="sxs-lookup"><span data-stu-id="e41aa-228">**Wednesday**</span></span>  
 <span data-ttu-id="e41aa-229">Exécute le travail le mercredi.</span><span class="sxs-lookup"><span data-stu-id="e41aa-229">Set the job to occur on a Wednesday.</span></span> <span data-ttu-id="e41aa-230">Disponible uniquement pour les planifications hebdomadaires.</span><span class="sxs-lookup"><span data-stu-id="e41aa-230">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="e41aa-231">**Jeudi**</span><span class="sxs-lookup"><span data-stu-id="e41aa-231">**Thursday**</span></span>  
 <span data-ttu-id="e41aa-232">Exécute le travail le jeudi.</span><span class="sxs-lookup"><span data-stu-id="e41aa-232">Set the job to occur on a Thursday.</span></span> <span data-ttu-id="e41aa-233">Disponible uniquement pour les planifications hebdomadaires.</span><span class="sxs-lookup"><span data-stu-id="e41aa-233">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="e41aa-234">**Vendredi**</span><span class="sxs-lookup"><span data-stu-id="e41aa-234">**Friday**</span></span>  
 <span data-ttu-id="e41aa-235">Exécute le travail le vendredi.</span><span class="sxs-lookup"><span data-stu-id="e41aa-235">Set the job to occur on a Friday.</span></span> <span data-ttu-id="e41aa-236">Disponible uniquement pour les planifications hebdomadaires.</span><span class="sxs-lookup"><span data-stu-id="e41aa-236">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="e41aa-237">**Samedi**</span><span class="sxs-lookup"><span data-stu-id="e41aa-237">**Saturday**</span></span>  
 <span data-ttu-id="e41aa-238">Exécute le travail le samedi.</span><span class="sxs-lookup"><span data-stu-id="e41aa-238">Set the job to occur on a Saturday.</span></span> <span data-ttu-id="e41aa-239">Disponible uniquement pour les planifications hebdomadaires.</span><span class="sxs-lookup"><span data-stu-id="e41aa-239">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="e41aa-240">**Dimanche**</span><span class="sxs-lookup"><span data-stu-id="e41aa-240">**Sunday**</span></span>  
 <span data-ttu-id="e41aa-241">Exécute le travail le dimanche.</span><span class="sxs-lookup"><span data-stu-id="e41aa-241">Set the job to occur on a Sunday.</span></span> <span data-ttu-id="e41aa-242">Disponible uniquement pour les planifications hebdomadaires.</span><span class="sxs-lookup"><span data-stu-id="e41aa-242">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="e41aa-243">**Jour**</span><span class="sxs-lookup"><span data-stu-id="e41aa-243">**Day**</span></span>  
 <span data-ttu-id="e41aa-244">Sélectionnez le jour du mois pour la planification.</span><span class="sxs-lookup"><span data-stu-id="e41aa-244">Select the day of the month the schedule occurs.</span></span> <span data-ttu-id="e41aa-245">Disponible uniquement pour les planifications mensuelles.</span><span class="sxs-lookup"><span data-stu-id="e41aa-245">Only available for monthly schedules.</span></span>  
  
 <span data-ttu-id="e41aa-246">**de chaque**</span><span class="sxs-lookup"><span data-stu-id="e41aa-246">**of every**</span></span>  
 <span data-ttu-id="e41aa-247">Sélectionnez le nombre de mois entre deux occurrences de la planification.</span><span class="sxs-lookup"><span data-stu-id="e41aa-247">Select the number of months between occurrences of the schedule.</span></span> <span data-ttu-id="e41aa-248">Disponible uniquement pour les planifications mensuelles.</span><span class="sxs-lookup"><span data-stu-id="e41aa-248">Only available for monthly schedules.</span></span>  
  
 <span data-ttu-id="e41aa-249">**Le**</span><span class="sxs-lookup"><span data-stu-id="e41aa-249">**The**</span></span>  
 <span data-ttu-id="e41aa-250">Spécifiez une planification pour un jour de la semaine spécifique, dans une semaine spécifique dans le mois.</span><span class="sxs-lookup"><span data-stu-id="e41aa-250">Specify a schedule for a specific day of the week on a specific week within the month.</span></span> <span data-ttu-id="e41aa-251">Disponible uniquement pour les planifications mensuelles.</span><span class="sxs-lookup"><span data-stu-id="e41aa-251">Only available for monthly schedules.</span></span>  
  
 <span data-ttu-id="e41aa-252">**Une fois à**</span><span class="sxs-lookup"><span data-stu-id="e41aa-252">**Occurs once at**</span></span>  
 <span data-ttu-id="e41aa-253">Définit l'heure à laquelle le travail est exécuté chaque jour.</span><span class="sxs-lookup"><span data-stu-id="e41aa-253">Set the time for a job to occur daily.</span></span>  
  
 <span data-ttu-id="e41aa-254">**Toutes les**</span><span class="sxs-lookup"><span data-stu-id="e41aa-254">**Occurs every**</span></span>  
 <span data-ttu-id="e41aa-255">Définit le nombre d'heures ou de minutes entre chaque exécution du travail.</span><span class="sxs-lookup"><span data-stu-id="e41aa-255">Set the number of hours or minutes between occurrences.</span></span>  
  
 <span data-ttu-id="e41aa-256">**Date de début**</span><span class="sxs-lookup"><span data-stu-id="e41aa-256">**Start date**</span></span>  
 <span data-ttu-id="e41aa-257">Définit la date à laquelle la planification est effective.</span><span class="sxs-lookup"><span data-stu-id="e41aa-257">Set the date when this schedule will become effective.</span></span>  
  
 <span data-ttu-id="e41aa-258">**Date de fin**</span><span class="sxs-lookup"><span data-stu-id="e41aa-258">**End date**</span></span>  
 <span data-ttu-id="e41aa-259">Définit la date à laquelle la planification cessera d'être appliquée.</span><span class="sxs-lookup"><span data-stu-id="e41aa-259">Set the date when the schedule will no longer be effective.</span></span>  
  
 <span data-ttu-id="e41aa-260">**Aucune date de fin**</span><span class="sxs-lookup"><span data-stu-id="e41aa-260">**No end date**</span></span>  
 <span data-ttu-id="e41aa-261">Spécifie que la planification doit être appliquée indéfiniment.</span><span class="sxs-lookup"><span data-stu-id="e41aa-261">Specify that the schedule will remain effective indefinitely.</span></span>  
  
### <a name="one-time-schedule-types-options"></a><span data-ttu-id="e41aa-262">Options des types de planification unique</span><span class="sxs-lookup"><span data-stu-id="e41aa-262">One Time Schedule Types Options</span></span>  
 <span data-ttu-id="e41aa-263">Si vous planifiez un travail pour une exécution unique, vous devez sélectionner des date et heure situées dans le futur.</span><span class="sxs-lookup"><span data-stu-id="e41aa-263">If you schedule a job to run once, you must select a date and time in the future.</span></span>  
  
 <span data-ttu-id="e41aa-264">**Date**</span><span class="sxs-lookup"><span data-stu-id="e41aa-264">**Date**</span></span>  
 <span data-ttu-id="e41aa-265">Sélectionnez la date d'exécution du travail.</span><span class="sxs-lookup"><span data-stu-id="e41aa-265">Select the date for the job to run.</span></span>  
  
 <span data-ttu-id="e41aa-266">**Time**</span><span class="sxs-lookup"><span data-stu-id="e41aa-266">**Time**</span></span>  
 <span data-ttu-id="e41aa-267">Sélectionnez l'heure d'exécution du travail.</span><span class="sxs-lookup"><span data-stu-id="e41aa-267">Select the time for the job to run.</span></span>  
  
 <span data-ttu-id="e41aa-268">![Icône de flèche utilisée avec le lien Retour en haut](../../2014-toc/media/uparrow16x16.gif "Icône de flèche utilisée avec le lien Retour en haut") [Dans cette section](#Top)</span><span class="sxs-lookup"><span data-stu-id="e41aa-268">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="e41aa-269">Page Résumé</span><span class="sxs-lookup"><span data-stu-id="e41aa-269">Summary Page</span></span>  
 <span data-ttu-id="e41aa-270">Utilisez la page **Résumé** pour examiner les options que vous avez sélectionnées sur les pages précédentes.</span><span class="sxs-lookup"><span data-stu-id="e41aa-270">Use the **Summary** page to review the options that you have selected on the previous pages.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="e41aa-271">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="e41aa-271">UI element list</span></span>  
 <span data-ttu-id="e41aa-272">**Vérifier vos sélections**</span><span class="sxs-lookup"><span data-stu-id="e41aa-272">**Review your selections**</span></span>  
 <span data-ttu-id="e41aa-273">Affiche les choix que vous avez effectués pour chaque page de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="e41aa-273">Displays the selections you have made for each page of the wizard.</span></span> <span data-ttu-id="e41aa-274">Cliquez sur un nœud pour développer et afficher les options que vous avez sélectionnées précédemment.</span><span class="sxs-lookup"><span data-stu-id="e41aa-274">Click a node to expand and view your previously selected options.</span></span>  
  
 <span data-ttu-id="e41aa-275">![Icône de flèche utilisée avec le lien Retour en haut](../../2014-toc/media/uparrow16x16.gif "Icône de flèche utilisée avec le lien Retour en haut") [Dans cette section](#Top)</span><span class="sxs-lookup"><span data-stu-id="e41aa-275">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="progress-page"></a><a name="Progress"></a> <span data-ttu-id="e41aa-276">Page Progression</span><span class="sxs-lookup"><span data-stu-id="e41aa-276">Progress Page</span></span>  
 <span data-ttu-id="e41aa-277">Utilisez la page **Progression** pour surveiller les informations d’état sur les actions de l’ **Assistant Gestion de partition**.</span><span class="sxs-lookup"><span data-stu-id="e41aa-277">Use the **Progress** page to monitor status information about the actions of the **Manage Partition Wizard**.</span></span> <span data-ttu-id="e41aa-278">Selon les options sélectionnées dans l’Assistant, la page **Progression** peut contenir une ou plusieurs actions.</span><span class="sxs-lookup"><span data-stu-id="e41aa-278">Depending on the options that you selected in the wizard, the **Progress** page might contain one or more actions.</span></span> <span data-ttu-id="e41aa-279">La zone supérieure affiche l'état global de l'Assistant et le nombre des messages d'état, d'erreur et d'avertissement qu'il a reçus.</span><span class="sxs-lookup"><span data-stu-id="e41aa-279">The top box displays the overall status of the wizard and the number of status, error, and warning messages that the wizard has received.</span></span>  
  
### <a name="options"></a><span data-ttu-id="e41aa-280">Options</span><span class="sxs-lookup"><span data-stu-id="e41aa-280">Options</span></span>  
 <span data-ttu-id="e41aa-281">**Détails**</span><span class="sxs-lookup"><span data-stu-id="e41aa-281">**Details**</span></span>  
 <span data-ttu-id="e41aa-282">Indique l'action, l'état et tous les messages retournés suite à l'action entreprise par l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="e41aa-282">Provides the action, status, and any messages that are returned from action taken by the wizard.</span></span>  
  
 <span data-ttu-id="e41aa-283">**Action**</span><span class="sxs-lookup"><span data-stu-id="e41aa-283">**Action**</span></span>  
 <span data-ttu-id="e41aa-284">Indique le type et le nom de chaque action.</span><span class="sxs-lookup"><span data-stu-id="e41aa-284">Specifies the type and name of each action.</span></span>  
  
 <span data-ttu-id="e41aa-285">**État**</span><span class="sxs-lookup"><span data-stu-id="e41aa-285">**Status**</span></span>  
 <span data-ttu-id="e41aa-286">Indique si l’action de l’Assistant dans son ensemble a retourné la valeur **Réussite** ou **Échec**.</span><span class="sxs-lookup"><span data-stu-id="e41aa-286">Indicates whether the wizard action as a whole returned the value of **Success** or **Failure**.</span></span>  
  
 <span data-ttu-id="e41aa-287">**Message**</span><span class="sxs-lookup"><span data-stu-id="e41aa-287">**Message**</span></span>  
 <span data-ttu-id="e41aa-288">Indique les messages d'erreur ou d'avertissement retournés par le processus.</span><span class="sxs-lookup"><span data-stu-id="e41aa-288">Provides any error or warning messages that are returned from the process.</span></span>  
  
 <span data-ttu-id="e41aa-289">**Stop**</span><span class="sxs-lookup"><span data-stu-id="e41aa-289">**Stop**</span></span>  
 <span data-ttu-id="e41aa-290">Arrête l'action de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="e41aa-290">Stop the action of the wizard.</span></span>  
  
 <span data-ttu-id="e41aa-291">**Report**</span><span class="sxs-lookup"><span data-stu-id="e41aa-291">**Report**</span></span>  
 <span data-ttu-id="e41aa-292">Crée un rapport qui contient les résultats de l’ **Assistant Gestion de partition**.</span><span class="sxs-lookup"><span data-stu-id="e41aa-292">Create a report that contains the results of the **Manage Partition Wizard**.</span></span> <span data-ttu-id="e41aa-293">Les options sont :</span><span class="sxs-lookup"><span data-stu-id="e41aa-293">The options are:</span></span>  
  
-   <span data-ttu-id="e41aa-294">**Afficher le rapport**</span><span class="sxs-lookup"><span data-stu-id="e41aa-294">**View Report**</span></span>  
  
-   <span data-ttu-id="e41aa-295">**Enregistrer le rapport dans un fichier**</span><span class="sxs-lookup"><span data-stu-id="e41aa-295">**Save Report to File**</span></span>  
  
-   <span data-ttu-id="e41aa-296">**Copier le rapport dans le Presse-papiers**</span><span class="sxs-lookup"><span data-stu-id="e41aa-296">**Copy Report to Clipboard**</span></span>  
  
-   <span data-ttu-id="e41aa-297">**Envoyer le rapport sous forme de courrier électronique**</span><span class="sxs-lookup"><span data-stu-id="e41aa-297">**Send Report as Email**</span></span>  
  
 <span data-ttu-id="e41aa-298">**Afficher le rapport**</span><span class="sxs-lookup"><span data-stu-id="e41aa-298">**View Report**</span></span>  
 <span data-ttu-id="e41aa-299">Ouvre la boîte de dialogue **Afficher le rapport** .</span><span class="sxs-lookup"><span data-stu-id="e41aa-299">Open the **View Report** dialog box.</span></span> <span data-ttu-id="e41aa-300">Cette boîte de dialogue contient un rapport au format texte sur la progression de l’ **Assistant Gestion de partition**.</span><span class="sxs-lookup"><span data-stu-id="e41aa-300">This dialog box contains a text report of the progress of the **Manage Partition Wizard**.</span></span>  
  
 <span data-ttu-id="e41aa-301">**Close**</span><span class="sxs-lookup"><span data-stu-id="e41aa-301">**Close**</span></span>  
 <span data-ttu-id="e41aa-302">Ferme l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="e41aa-302">Close the wizard.</span></span>  
  
 <span data-ttu-id="e41aa-303">![Icône de flèche utilisée avec le lien Retour en haut](../../2014-toc/media/uparrow16x16.gif "Icône de flèche utilisée avec le lien Retour en haut") [Dans cette section](#Top)</span><span class="sxs-lookup"><span data-stu-id="e41aa-303">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e41aa-304">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e41aa-304">See Also</span></span>  
 [<span data-ttu-id="e41aa-305">Tables et index partitionnés</span><span class="sxs-lookup"><span data-stu-id="e41aa-305">Partitioned Tables and Indexes</span></span>](partitioned-tables-and-indexes.md)  
  
  
