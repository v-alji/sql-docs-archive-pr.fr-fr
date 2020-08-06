---
title: Boîte de dialogue Modifier les propriétés de la table (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.edittablepropdb.f1
ms.assetid: 8d913e83-7246-44cc-8fc7-31729023c0d8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6664d244f5f653610b37bd628abdb2263e015c0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613194"
---
# <a name="edit-table-properties-dialog-box-ssas"></a><span data-ttu-id="cab73-102">Modifier les propriétés de la table, boîte de dialogue (SSAS)</span><span class="sxs-lookup"><span data-stu-id="cab73-102">Edit Table Properties Dialog Box (SSAS)</span></span>
  <span data-ttu-id="cab73-103">La boîte de dialogue **Modifier les propriétés de la table** vous permet d'afficher et de modifier les propriétés des tables importées dans le générateur de modèles à l'aide de l'Assistant Importation de table.</span><span class="sxs-lookup"><span data-stu-id="cab73-103">The **Edit Table Properties** dialog box enables you to view and modify the properties of tables that are imported into the model designer by using the Table Import Wizard.</span></span> <span data-ttu-id="cab73-104">Pour accéder à cette boîte de dialogue, dans le générateur de modèles, sélectionnez une table, puis cliquez sur le menu **Table** , puis sur **Propriétés de la table**.</span><span class="sxs-lookup"><span data-stu-id="cab73-104">To access this dialog box, in the model designer, select a table, then click the **Table** menu, and then click **Table Properties**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="cab73-105">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="cab73-105">UI element list</span></span>  
 <span data-ttu-id="cab73-106">Les options proposées dans cette boîte de dialogue diffèrent selon que vous avez initialement importé les données en sélectionnant des tables dans une liste ou en utilisant une requête SQL.</span><span class="sxs-lookup"><span data-stu-id="cab73-106">The options for this dialog box are different depending on whether you originally imported data by selecting tables from a list or by using a SQL query.</span></span>  
  
## <a name="table-preview-mode"></a><span data-ttu-id="cab73-107">Mode Aperçu de la table</span><span class="sxs-lookup"><span data-stu-id="cab73-107">Table Preview Mode</span></span>  
 <span data-ttu-id="cab73-108">**Nom de la table**</span><span class="sxs-lookup"><span data-stu-id="cab73-108">**Table name**</span></span>  
 <span data-ttu-id="cab73-109">Affiche le nom de la table de données dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="cab73-109">Displays the name of the data table in the model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cab73-110">Vous ne pouvez pas en modifier le nom à cet endroit.</span><span class="sxs-lookup"><span data-stu-id="cab73-110">You cannot edit the name here.</span></span> <span data-ttu-id="cab73-111">Toutefois, vous pouvez modifier le nom de la table en cliquant avec le bouton droit sur l'onglet de table en bas du générateur de modèles.</span><span class="sxs-lookup"><span data-stu-id="cab73-111">However, you can change the name of the table by right-clicking the table tab at the bottom of the model designer.</span></span>  
  
 <span data-ttu-id="cab73-112">**Nom de connexion**</span><span class="sxs-lookup"><span data-stu-id="cab73-112">**Connection name**</span></span>  
 <span data-ttu-id="cab73-113">Affiche le nom de la connexion qui est actuellement en cours d'utilisation.</span><span class="sxs-lookup"><span data-stu-id="cab73-113">Displays the name of the connection that is currently in use.</span></span>  
  
 <span data-ttu-id="cab73-114">**Nom de la source**</span><span class="sxs-lookup"><span data-stu-id="cab73-114">**Source name**</span></span>  
 <span data-ttu-id="cab73-115">Affichez ou modifiez la table à partir de laquelle les données sont obtenues.</span><span class="sxs-lookup"><span data-stu-id="cab73-115">Display or change the table from which the data is obtained.</span></span>  
  
 <span data-ttu-id="cab73-116">Si vous modifiez la source en une table qui comporte des colonnes différentes de la table actuelle, un message s'affiche pour vous avertir que les colonnes sont différentes.</span><span class="sxs-lookup"><span data-stu-id="cab73-116">If you change the source to a table that has different columns than the current table, a message is displayed warning that the columns are different.</span></span> <span data-ttu-id="cab73-117">Vous devez ensuite sélectionner les colonnes que vous souhaitez placer dans la table actuelle et cliquer sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="cab73-117">You must then select the columns that you want to put in the current table and click **Save**.</span></span> <span data-ttu-id="cab73-118">Vous pouvez remplacer la table entière en activant la case à cocher située à la gauche de la table.</span><span class="sxs-lookup"><span data-stu-id="cab73-118">You can replace the entire table by selecting the check box at the left of the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cab73-119">Lorsque vous modifiez la source de données d'une table, vous remplacez essentiellement le contenu de la table actuelle par le contenu de la nouvelle table source.</span><span class="sxs-lookup"><span data-stu-id="cab73-119">When you change the data source of a table, you essentially replace the contents of the current table with the contents of the new source table.</span></span>  
  
 <span data-ttu-id="cab73-120">**Origine des noms de colonnes**</span><span class="sxs-lookup"><span data-stu-id="cab73-120">**Column names from**</span></span>  
 |||  
|-|-|  
|<span data-ttu-id="cab73-121">**Source**</span><span class="sxs-lookup"><span data-stu-id="cab73-121">**Source**</span></span>|<span data-ttu-id="cab73-122">Sélectionnez cette option pour remplacer les noms de colonnes actuels par les noms de colonnes de la table source sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cab73-122">Select this option to replace the current column names with the column names from the selected source table.</span></span>|  
|<span data-ttu-id="cab73-123">**Modèle**</span><span class="sxs-lookup"><span data-stu-id="cab73-123">**Model**</span></span>|<span data-ttu-id="cab73-124">Sélectionnez cette option pour utiliser les noms de colonne actuels tels qu'ils existent dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="cab73-124">Select this option to use the current column names as they exist in the model.</span></span>|  
  
 <span data-ttu-id="cab73-125">**Actualiser l'aperçu**</span><span class="sxs-lookup"><span data-stu-id="cab73-125">**Refresh preview**</span></span>  
 <span data-ttu-id="cab73-126">Cliquez pour examiner les colonnes de données dans la table source actuellement sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cab73-126">Click to view the columns of data in the currently selected source table.</span></span>  
  
 <span data-ttu-id="cab73-127">**Basculer vers**</span><span class="sxs-lookup"><span data-stu-id="cab73-127">**Switch to**</span></span>  
 |||  
|-|-|  
|<span data-ttu-id="cab73-128">**Aperçu de la table**</span><span class="sxs-lookup"><span data-stu-id="cab73-128">**Table preview**</span></span>|<span data-ttu-id="cab73-129">Sélectionnez cette option pour afficher un aperçu de la table sélectionnée et un nombre limité de lignes de données.</span><span class="sxs-lookup"><span data-stu-id="cab73-129">Select this option to preview the selected table and a limited number of rows of data.</span></span>|  
|<span data-ttu-id="cab73-130">**Éditeur de requête**</span><span class="sxs-lookup"><span data-stu-id="cab73-130">**Query editor**</span></span>|<span data-ttu-id="cab73-131">Sélectionnez cette option pour examiner la requête sur la source de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cab73-131">Select this option to view the query against the selected data source.</span></span> <span data-ttu-id="cab73-132">Cette option n'est pas disponible pour toutes les sources de données.</span><span class="sxs-lookup"><span data-stu-id="cab73-132">This option is not available for all data sources.</span></span>|  
  
 <span data-ttu-id="cab73-133">**Case à cocher dans l'en-tête de colonne**</span><span class="sxs-lookup"><span data-stu-id="cab73-133">**Checkbox in the column header**</span></span>  
 <span data-ttu-id="cab73-134">Activez la case à cocher pour inclure la colonne lors de l'importation des données.</span><span class="sxs-lookup"><span data-stu-id="cab73-134">Select the checkbox to include the column in the data import.</span></span> <span data-ttu-id="cab73-135">Désactivez la case à cocher pour supprimer la colonne lors de l'importation de données.</span><span class="sxs-lookup"><span data-stu-id="cab73-135">Clear the checkbox to remove the column from the data import.</span></span>  
  
 <span data-ttu-id="cab73-136">**Bouton Flèche vers le bas dans l'en-tête de colonne**</span><span class="sxs-lookup"><span data-stu-id="cab73-136">**Down-arrow button in the column header**</span></span>  
 <span data-ttu-id="cab73-137">Filtrez les données dans la colonne.</span><span class="sxs-lookup"><span data-stu-id="cab73-137">Filter data in the column.</span></span>  
  
 <span data-ttu-id="cab73-138">**Effacer les filtres de lignes**</span><span class="sxs-lookup"><span data-stu-id="cab73-138">**Clear row filters**</span></span>  
 <span data-ttu-id="cab73-139">Cliquez pour supprimer tous les filtres qui ont été appliqués.</span><span class="sxs-lookup"><span data-stu-id="cab73-139">Click to remove any filters that have been applied.</span></span>  
  
 <span data-ttu-id="cab73-140">**OK**</span><span class="sxs-lookup"><span data-stu-id="cab73-140">**OK**</span></span>  
 <span data-ttu-id="cab73-141">Cliquez pour appliquer toutes les modifications que vous avez apportées, notamment le remplacement des colonnes.</span><span class="sxs-lookup"><span data-stu-id="cab73-141">Click to apply all changes that you made, including replacing columns.</span></span>  
  
## <a name="query-design-mode"></a><span data-ttu-id="cab73-142">Mode Conception de requête</span><span class="sxs-lookup"><span data-stu-id="cab73-142">Query Design Mode</span></span>  
 <span data-ttu-id="cab73-143">**Nom de la table**</span><span class="sxs-lookup"><span data-stu-id="cab73-143">**Table name**</span></span>  
 <span data-ttu-id="cab73-144">Affiche le nom de la table de données dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="cab73-144">Displays the name of the data table in the model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cab73-145">Vous ne pouvez pas modifier le nom ici ; toutefois, vous pouvez modifier le nom de la table en cliquant avec le bouton droit sur l'onglet de table en bas du concepteur.</span><span class="sxs-lookup"><span data-stu-id="cab73-145">You cannot edit the name here; however, you can change the name of the table by right-clicking the table tab at the bottom of the designer.</span></span>  
  
 <span data-ttu-id="cab73-146">**Nom de connexion**</span><span class="sxs-lookup"><span data-stu-id="cab73-146">**Connection name**</span></span>  
 <span data-ttu-id="cab73-147">Affiche le nom de la connexion qui est actuellement en cours d'utilisation.</span><span class="sxs-lookup"><span data-stu-id="cab73-147">Displays the name of the connection that is currently in use.</span></span>  
  
 <span data-ttu-id="cab73-148">**Basculer vers**</span><span class="sxs-lookup"><span data-stu-id="cab73-148">**Switch to**</span></span>  
 |||  
|-|-|  
|<span data-ttu-id="cab73-149">**Aperçu de la table**</span><span class="sxs-lookup"><span data-stu-id="cab73-149">**Table preview**</span></span>|<span data-ttu-id="cab73-150">Sélectionnez cette option pour afficher un aperçu de la table sélectionnée et quelques lignes de données.</span><span class="sxs-lookup"><span data-stu-id="cab73-150">Select this option to preview the selected table and a few rows of data.</span></span>|  
|<span data-ttu-id="cab73-151">**Éditeur de requête**</span><span class="sxs-lookup"><span data-stu-id="cab73-151">**Query editor**</span></span>|<span data-ttu-id="cab73-152">Sélectionnez cette option pour examiner la requête qui sera émise sur la source de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cab73-152">Select this option to view the query that will be issued against the selected data source.</span></span>|  
  
 <span data-ttu-id="cab73-153">**Instruction SQL**</span><span class="sxs-lookup"><span data-stu-id="cab73-153">**Sql statement**</span></span>  
 <span data-ttu-id="cab73-154">Affiche l'instruction SQL émise sur la source de données actuelle afin de récupérer des lignes.</span><span class="sxs-lookup"><span data-stu-id="cab73-154">Displays the SQL statement that is issued against the current data source to retrieve rows.</span></span> <span data-ttu-id="cab73-155">Par défaut, toutes les lignes sont récupérées, mais vous pouvez récupérer un sous-ensemble de lignes, soit en concevant un filtre, soit en modifiant manuellement l'instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="cab73-155">By default, all rows are retrieved, but you can retrieve a subset of rows, either by designing a filter, or by manually editing the SQL statement.</span></span>  
  
 <span data-ttu-id="cab73-156">**Procéder à la validation**</span><span class="sxs-lookup"><span data-stu-id="cab73-156">**Validate**</span></span>  
 <span data-ttu-id="cab73-157">Cliquez pour vérifier que l'instruction est syntaxiquement correcte pour le fournisseur et la source de données sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="cab73-157">Click to verify that the statement is syntactically correct for the selected data source and provider.</span></span>  
  
 <span data-ttu-id="cab73-158">**Concevez**</span><span class="sxs-lookup"><span data-stu-id="cab73-158">**Design**</span></span>  
 <span data-ttu-id="cab73-159">Cliquez pour ouvrir un concepteur de requêtes visuel et générer une instruction de requête.</span><span class="sxs-lookup"><span data-stu-id="cab73-159">Click to open a visual query designer and build a query statement.</span></span> <span data-ttu-id="cab73-160">Pour plus d'informations sur l'utilisation du concepteur, appuyez sur F1 dans le concepteur.</span><span class="sxs-lookup"><span data-stu-id="cab73-160">For information about how to use the designer, press F1 from the designer.</span></span>  
  
 <span data-ttu-id="cab73-161">**OK**</span><span class="sxs-lookup"><span data-stu-id="cab73-161">**OK**</span></span>  
 <span data-ttu-id="cab73-162">Cliquez pour appliquer toutes les modifications que vous avez apportées, notamment le remplacement des colonnes.</span><span class="sxs-lookup"><span data-stu-id="cab73-162">Click to apply all changes that you made, including replacing columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cab73-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cab73-163">See Also</span></span>  
 [<span data-ttu-id="cab73-164">Tables et colonnes &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="cab73-164">Tables and Columns &#40;SSAS Tabular&#41;</span></span>](tabular-models/tables-and-columns-ssas-tabular.md)  
  
  
