---
title: Index XML, boîte de dialogue (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.xmlindexes
ms.assetid: eef38310-4498-4ccc-bb77-5bbd1c7cc477
author: stevestein
ms.author: sstein
ms.openlocfilehash: f1fb23a801a9129611c032fa1d659caf624088aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611442"
---
# <a name="xml-indexes-dialog-box-visual-database-tools"></a><span data-ttu-id="8dfb5-102">Boîte de dialogue Index XML (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="8dfb5-102">XML Indexes Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="8dfb5-103">Utilisez la boîte de dialogue **Index XML** pour créer des index pour les colonnes du type de données XML qui ne peuvent pas être indexées à l’aide de la boîte de dialogue **Index/Clés** .</span><span class="sxs-lookup"><span data-stu-id="8dfb5-103">Use the **XML Indexes** dialog box to create indexes for columns of the data type XML, which cannot be indexed using the **Index/Keys** dialog box.</span></span> <span data-ttu-id="8dfb5-104">Chaque colonne XML peut posséder plusieurs index XML, mais le premier index créé (principal) est utilisé comme base pour les autres (secondaires).</span><span class="sxs-lookup"><span data-stu-id="8dfb5-104">Each XML column can have more than one XML Index, but the first one created (primary) will be the basis of the others (secondary).</span></span> <span data-ttu-id="8dfb5-105">Si vous supprimez l'index XML principal, les index secondaires sont également supprimés.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-105">If you delete the primary XML index, the secondary indexes will also be deleted.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8dfb5-106">Options</span><span class="sxs-lookup"><span data-stu-id="8dfb5-106">Options</span></span>  
 <span data-ttu-id="8dfb5-107">**Index XML sélectionné**</span><span class="sxs-lookup"><span data-stu-id="8dfb5-107">**Selected XML Index**</span></span>  
 <span data-ttu-id="8dfb5-108">Répertorie les index XML existants.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-108">Lists existing XML indexes.</span></span> <span data-ttu-id="8dfb5-109">Sélectionnez cette option pour afficher ses propriétés dans la partie droite de la grille.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-109">Select to show its properties in the grid to the right.</span></span> <span data-ttu-id="8dfb5-110">Si la liste est vide, aucune propriété n'est définie pour la table.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-110">If the list is empty, none have been defined for the table.</span></span>  
  
 <span data-ttu-id="8dfb5-111">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="8dfb5-111">**Add**</span></span>  
 <span data-ttu-id="8dfb5-112">Crée un nouvel index XML.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-112">Create a new XML index.</span></span>  
  
 <span data-ttu-id="8dfb5-113">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="8dfb5-113">**Delete**</span></span>  
 <span data-ttu-id="8dfb5-114">Supprime l’index XML sélectionné dans la liste **Index XML sélectionné** .</span><span class="sxs-lookup"><span data-stu-id="8dfb5-114">Delete XML index selected in the **Selected XML Index** list.</span></span> <span data-ttu-id="8dfb5-115">Lorsque vous supprimez l'index XML principal, vous êtes averti que cette opération supprimera également tout index secondaire, et que vous pouvez soit continuer, soit annuler l'action.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-115">If you delete the primary XML index, you will be notified that this will delete all secondary ones as well, and you can either continue or cancel the action.</span></span>  
  
 <span data-ttu-id="8dfb5-116">**Catégorie Général**</span><span class="sxs-lookup"><span data-stu-id="8dfb5-116">**General Category**</span></span>  
 <span data-ttu-id="8dfb5-117">Développée, elle affiche les champs des propriétés **Colonnes**, **Est primaire**et **Type**.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-117">When expanded, shows the property fields for **Columns**, **Is Primary**, and **Type**.</span></span>  
  
 <span data-ttu-id="8dfb5-118">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="8dfb5-118">**Columns**</span></span>  
 <span data-ttu-id="8dfb5-119">Indique que cet index est trié en ordre croissant.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-119">Shows that this index is sorted in ascending order.</span></span>  
  
 <span data-ttu-id="8dfb5-120">**Est primaire**</span><span class="sxs-lookup"><span data-stu-id="8dfb5-120">**Is Primary**</span></span>  
 <span data-ttu-id="8dfb5-121">Indique s'il s'agit de l'index principal.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-121">Indicates whether this is the primary index.</span></span> <span data-ttu-id="8dfb5-122">Le premier index XML créé sur la colonne est utilisé comme base pour les autres.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-122">The first XML index created on the column will be the basis of the others.</span></span>  
  
 <span data-ttu-id="8dfb5-123">**Nom de la référence primaire**</span><span class="sxs-lookup"><span data-stu-id="8dfb5-123">**Primary reference name**</span></span>  
 <span data-ttu-id="8dfb5-124">Affiche le nom de l'index principal s'il s'agit d'un index secondaire.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-124">Shows the name of the primary index if this is a secondary index.</span></span> <span data-ttu-id="8dfb5-125">Disponible uniquement s'il s'agit d'un index secondaire.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-125">Only available if this is a secondary index.</span></span>  
  
 <span data-ttu-id="8dfb5-126">**Type secondaire**</span><span class="sxs-lookup"><span data-stu-id="8dfb5-126">**Secondary type**</span></span>  
 <span data-ttu-id="8dfb5-127">Affiche le type de l'index secondaire.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-127">Shows the type of secondary index.</span></span> <span data-ttu-id="8dfb5-128">Disponible uniquement s'il s'agit d'un index secondaire.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-128">Only available if this is a secondary index.</span></span>  
  
 <span data-ttu-id="8dfb5-129">**Type**</span><span class="sxs-lookup"><span data-stu-id="8dfb5-129">**Type**</span></span>  
 <span data-ttu-id="8dfb5-130">Indique qu'il s'agit d'un index XML.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-130">Shows that this is an XML index.</span></span>  
  
 <span data-ttu-id="8dfb5-131">**Catégorie Identité**</span><span class="sxs-lookup"><span data-stu-id="8dfb5-131">**Identity Category**</span></span>  
 <span data-ttu-id="8dfb5-132">Développée, elle affiche les champs de propriétés de **Nom** et **Description** .</span><span class="sxs-lookup"><span data-stu-id="8dfb5-132">When expanded, shows the **Name** and **Description** property fields.</span></span>  
  
 <span data-ttu-id="8dfb5-133">**Nom**</span><span class="sxs-lookup"><span data-stu-id="8dfb5-133">**Name**</span></span>  
 <span data-ttu-id="8dfb5-134">Indique le nom de l'index XML.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-134">Shows the name of the XML index.</span></span> <span data-ttu-id="8dfb5-135">Lorsqu'un nouvel index ou une nouvelle clé sont créés, ils obtiennent un nom par défaut basé sur la table affichée dans la fenêtre active du Concepteur de tables.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-135">When a new one is created, it is given a default name based on the table in the active window in Table Designer.</span></span> <span data-ttu-id="8dfb5-136">Vous pouvez modifier le nom à tout moment.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-136">You can change the name at any time.</span></span>  
  
 <span data-ttu-id="8dfb5-137">**Description**</span><span class="sxs-lookup"><span data-stu-id="8dfb5-137">**Description**</span></span>  
 <span data-ttu-id="8dfb5-138">Décrivez l’index.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-138">Describe the index.</span></span> <span data-ttu-id="8dfb5-139">Pour écrire une description plus détaillée, cliquez sur **Description**, puis sur le bouton de sélection ( **...** ) qui s’affiche à droite du champ de propriété.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-139">To write a more detailed description, click **Description** and then click the ellipsis button (**...**) that appears to the right of the property field.</span></span> <span data-ttu-id="8dfb5-140">Vous obtiendrez une zone d'écriture plus large.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-140">This provides a larger area in which to write text.</span></span>  
  
 <span data-ttu-id="8dfb5-141">**Catégorie Concepteur de tables**</span><span class="sxs-lookup"><span data-stu-id="8dfb5-141">**Table Designer Category**</span></span>  
 <span data-ttu-id="8dfb5-142">Développée, elle affiche des informations sur les propriétés de cet index XML.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-142">When expanded, shows information about the properties of this XML index.</span></span>  
  
 <span data-ttu-id="8dfb5-143">**Spécification du remplissage**</span><span class="sxs-lookup"><span data-stu-id="8dfb5-143">**Fill Specification**</span></span>  
 <span data-ttu-id="8dfb5-144">Développée, elle affiche des informations sur les options **Taux de remplissage** et **Index Pad**.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-144">When expanded, shows information for **Fill Factor** and **Pad Index**.</span></span>  
  
 <span data-ttu-id="8dfb5-145">**Taux de remplissage**</span><span class="sxs-lookup"><span data-stu-id="8dfb5-145">**Fill Factor**</span></span>  
 <span data-ttu-id="8dfb5-146">Spécifie le pourcentage de la page d'index que le système peut remplir.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-146">Specify what percentage of the index page the system can fill.</span></span> <span data-ttu-id="8dfb5-147">Lorsqu'une page est pleine, le système doit la fractionner au cas où de nouvelles données seraient ajoutées, ce qui affaiblit les performances.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-147">Once a page is full, the system must split the page if new data is added, which impairs performance.</span></span>  
  
-   <span data-ttu-id="8dfb5-148">La valeur 100 signifie que les pages seront remplies et occuperont un espace de stockage minimal, mais c'est la solution la moins efficace.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-148">A value of 100 means the pages will be full; this requires the least amount of storage space but is the least efficient.</span></span> <span data-ttu-id="8dfb5-149">Ce paramètre ne doit être utilisé que lorsqu'aucune modification ne sera apportée aux données, par exemple dans un tableau en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-149">This setting should be used only when there will be no changes to the data, for example, on a read-only table.</span></span>  
  
-   <span data-ttu-id="8dfb5-150">Une valeur inférieure laisse davantage d'espace vide sur les ensembles de données, ce qui réduit le besoin de les fractionner à mesure que la taille des index augmente.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-150">A lower value leaves more empty space on the data pages, which reduces the need to split data pages as indexes grow.</span></span> <span data-ttu-id="8dfb5-151">Néanmoins, l'espace de stockage requis est plus important.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-151">However, it requires more storage space.</span></span> <span data-ttu-id="8dfb5-152">Ce paramètre est plus approprié si vous avez l'intention de modifier les données contenues dans la table.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-152">This setting is more appropriate when there will be changes to the data in the table.</span></span>  
  
 <span data-ttu-id="8dfb5-153">**Index Pad**</span><span class="sxs-lookup"><span data-stu-id="8dfb5-153">**Pad Index**</span></span>  
 <span data-ttu-id="8dfb5-154">Donne aux pages de cet index le même pourcentage d’espace libre (de remplissage) que celui spécifié dans **Taux de remplissage**.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-154">Provide pages in this index the same percentage of empty space (padding) that is specified in **Fill Factor**.</span></span>  
  
 <span data-ttu-id="8dfb5-155">**Est désactivé**</span><span class="sxs-lookup"><span data-stu-id="8dfb5-155">**Is Disabled**</span></span>  
 <span data-ttu-id="8dfb5-156">Spécifie si cet index est désactivé.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-156">Specify whether this index is disabled.</span></span> <span data-ttu-id="8dfb5-157">Les index désactivés ne prennent pas en charge les recherches, et ne sont pas mis à jour lorsque de nouveaux éléments sont ajoutés à la table.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-157">Disabled indexes do not support searches, nor do they get updated when new items are added to the table.</span></span> <span data-ttu-id="8dfb5-158">Vous pouvez améliorer les performances pour les insertions et les mises à jour en bloc en désactivant un index.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-158">You can improve performance for bulk inserts and updates by disabling an index.</span></span>  
  
 <span data-ttu-id="8dfb5-159">**Verrouillage de page autorisé**</span><span class="sxs-lookup"><span data-stu-id="8dfb5-159">**Page Locks Allowed**</span></span>  
 <span data-ttu-id="8dfb5-160">Spécifier si le verrouillage au niveau des pages est autorisé dans cet index.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-160">Specify whether page-level locking is allowed on this index.</span></span> <span data-ttu-id="8dfb5-161">L'autorisation ou non du verrouillage au niveau de la page affecte les performances de la base de données.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-161">Allowing or disallowing page-level locking affects database performance.</span></span>  
  
 <span data-ttu-id="8dfb5-162">**Recalculer les statistiques**</span><span class="sxs-lookup"><span data-stu-id="8dfb5-162">**Re-compute Statistics**</span></span>  
 <span data-ttu-id="8dfb5-163">Calcul de nouvelles statistiques au moment de la création de l'index.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-163">Compute new statistics when the index is created.</span></span> <span data-ttu-id="8dfb5-164">Le calcul de ces nouvelles statistiques ralentit la génération des index, mais améliore généralement les performances des requêtes.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-164">Re-computing statistics slows the building of indexes but usually improves query performance.</span></span>  
  
 <span data-ttu-id="8dfb5-165">**Verrouillage de ligne autorisé**</span><span class="sxs-lookup"><span data-stu-id="8dfb5-165">**Row Locks Allowed**</span></span>  
 <span data-ttu-id="8dfb5-166">Spécifier si le verrouillage au niveau des lignes est autorisé dans cet index.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-166">Specify whether row-level locking is allowed on this index.</span></span> <span data-ttu-id="8dfb5-167">L'autorisation ou non du verrouillage au niveau de la ligne affecte les performances de la base de données.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-167">Allowing or disallowing row-level locking affects database performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dfb5-168">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8dfb5-168">See Also</span></span>  
 [<span data-ttu-id="8dfb5-169">Créer des index XML</span><span class="sxs-lookup"><span data-stu-id="8dfb5-169">Create XML Indexes</span></span>](../../relational-databases/xml/create-xml-indexes.md)  
  
  
