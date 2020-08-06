---
title: Éditeur du gestionnaire de connexions de fichiers plats multiples (page colonnes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.multifile.columns.f1
helpviewer_keywords:
- Multiple Flat Files Connection Manager Editor
ms.assetid: ad0cb668-0df2-4d4e-9a20-d20692a0b67a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a7f4936f0722754b414076820eda7dcf2dc8dc5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601545"
---
# <a name="multiple-flat-files-connection-manager-editor-columns-page"></a><span data-ttu-id="7d88e-102">Éditeur du gestionnaire de connexions de fichiers plats multiples (page Colonnes)</span><span class="sxs-lookup"><span data-stu-id="7d88e-102">Multiple Flat Files Connection Manager Editor (Columns Page)</span></span>
  <span data-ttu-id="7d88e-103">Utilisez le nœud **Colonnes** de la boîte de dialogue **Éditeur du gestionnaire de connexions de fichiers plats multiples** pour spécifier les informations de ligne et de colonne et afficher un aperçu du premier fichier sélectionné.</span><span class="sxs-lookup"><span data-stu-id="7d88e-103">Use the **Columns** node of the **Multiple Flat Files Connection Manager Editor** dialog box to specify the row and column information, and to preview the first selected file.</span></span>  
  
 <span data-ttu-id="7d88e-104">Pour en savoir plus sur le gestionnaire de connexions de fichiers plats multiples, consultez [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="7d88e-104">To learn more about the Multiple Flat Files connection manager, see [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="7d88e-105">Options statiques</span><span class="sxs-lookup"><span data-stu-id="7d88e-105">Static Options</span></span>  
 <span data-ttu-id="7d88e-106">**Nom du gestionnaire de connexions**</span><span class="sxs-lookup"><span data-stu-id="7d88e-106">**Connection manager name**</span></span>  
 <span data-ttu-id="7d88e-107">Spécifiez un nom unique pour la connexion de fichiers plats multiples dans le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="7d88e-107">Provide a unique name for the Multiple Flat Files connection in the workflow.</span></span> <span data-ttu-id="7d88e-108">Le nom fourni sera affiché dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7d88e-108">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="7d88e-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="7d88e-109">**Description**</span></span>  
 <span data-ttu-id="7d88e-110">Décrit la connexion.</span><span class="sxs-lookup"><span data-stu-id="7d88e-110">Describe the connection.</span></span> <span data-ttu-id="7d88e-111">Il est recommandé d'indiquer ici l'usage auquel la connexion est destinée, de sorte que les packages soient correctement documentés et plus faciles à gérer.</span><span class="sxs-lookup"><span data-stu-id="7d88e-111">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
## <a name="flat-file-format-dynamic-options"></a><span data-ttu-id="7d88e-112">Options dynamiques de format de fichier plat</span><span class="sxs-lookup"><span data-stu-id="7d88e-112">Flat File Format Dynamic Options</span></span>  
  
### <a name="format--delimited"></a><span data-ttu-id="7d88e-113">Format = Délimité</span><span class="sxs-lookup"><span data-stu-id="7d88e-113">Format = Delimited</span></span>  
 <span data-ttu-id="7d88e-114">**Séparateur de lignes**</span><span class="sxs-lookup"><span data-stu-id="7d88e-114">**Row delimiter**</span></span>  
 <span data-ttu-id="7d88e-115">Effectuez une sélection dans la liste des séparateurs de lignes disponibles ou entrez le texte du séparateur.</span><span class="sxs-lookup"><span data-stu-id="7d88e-115">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="7d88e-116">Valeur</span><span class="sxs-lookup"><span data-stu-id="7d88e-116">Value</span></span>|<span data-ttu-id="7d88e-117">Description</span><span class="sxs-lookup"><span data-stu-id="7d88e-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7d88e-118">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-118">**{CR}{LF}**</span></span>|<span data-ttu-id="7d88e-119">Les lignes sont séparées par une combinaison de retour chariot/saut de ligne.</span><span class="sxs-lookup"><span data-stu-id="7d88e-119">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="7d88e-120">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-120">**{CR}**</span></span>|<span data-ttu-id="7d88e-121">Les lignes sont séparées par un retour chariot.</span><span class="sxs-lookup"><span data-stu-id="7d88e-121">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="7d88e-122">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-122">**{LF}**</span></span>|<span data-ttu-id="7d88e-123">Les lignes sont séparées par un saut de ligne.</span><span class="sxs-lookup"><span data-stu-id="7d88e-123">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="7d88e-124">**Point-virgule {;}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-124">**Semicolon {;}**</span></span>|<span data-ttu-id="7d88e-125">Les lignes sont séparées par un point-virgule.</span><span class="sxs-lookup"><span data-stu-id="7d88e-125">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="7d88e-126">**Deux-points {:}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-126">**Colon {:}**</span></span>|<span data-ttu-id="7d88e-127">Les lignes sont séparées par un deux-points.</span><span class="sxs-lookup"><span data-stu-id="7d88e-127">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="7d88e-128">**Virgule {,}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-128">**Comma {,}**</span></span>|<span data-ttu-id="7d88e-129">Les lignes sont séparées par une virgule.</span><span class="sxs-lookup"><span data-stu-id="7d88e-129">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="7d88e-130">**Tabulation {t}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-130">**Tab {t}**</span></span>|<span data-ttu-id="7d88e-131">Les lignes sont séparées par une tabulation.</span><span class="sxs-lookup"><span data-stu-id="7d88e-131">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="7d88e-132">**Barre verticale {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-132">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="7d88e-133">Les lignes sont séparées par une barre verticale.</span><span class="sxs-lookup"><span data-stu-id="7d88e-133">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="7d88e-134">**Délimiteur de colonne**</span><span class="sxs-lookup"><span data-stu-id="7d88e-134">**Column delimiter**</span></span>  
 <span data-ttu-id="7d88e-135">Effectuez une sélection dans la liste des séparateurs de colonnes disponibles ou entrez le texte du séparateur.</span><span class="sxs-lookup"><span data-stu-id="7d88e-135">Select from the list of available column delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="7d88e-136">Valeur</span><span class="sxs-lookup"><span data-stu-id="7d88e-136">Value</span></span>|<span data-ttu-id="7d88e-137">Description</span><span class="sxs-lookup"><span data-stu-id="7d88e-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7d88e-138">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-138">**{CR}{LF}**</span></span>|<span data-ttu-id="7d88e-139">Les colonnes sont délimitées par une combinaison retour chariot-saut de ligne.</span><span class="sxs-lookup"><span data-stu-id="7d88e-139">Columns are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="7d88e-140">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-140">**{CR}**</span></span>|<span data-ttu-id="7d88e-141">Les colonnes sont séparées par un retour chariot.</span><span class="sxs-lookup"><span data-stu-id="7d88e-141">Columns are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="7d88e-142">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-142">**{LF}**</span></span>|<span data-ttu-id="7d88e-143">Les colonnes sont séparées par un saut de ligne.</span><span class="sxs-lookup"><span data-stu-id="7d88e-143">Columns are delimited by a line feed.</span></span>|  
|<span data-ttu-id="7d88e-144">**Point-virgule {;}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-144">**Semicolon {;}**</span></span>|<span data-ttu-id="7d88e-145">Les colonnes sont séparées par un point-virgule.</span><span class="sxs-lookup"><span data-stu-id="7d88e-145">Columns are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="7d88e-146">**Deux-points {:}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-146">**Colon {:}**</span></span>|<span data-ttu-id="7d88e-147">Les colonnes sont séparées par un deux-points.</span><span class="sxs-lookup"><span data-stu-id="7d88e-147">Columns are delimited by a colon.</span></span>|  
|<span data-ttu-id="7d88e-148">**Virgule {,}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-148">**Comma {,}**</span></span>|<span data-ttu-id="7d88e-149">Les colonnes sont séparées par une virgule.</span><span class="sxs-lookup"><span data-stu-id="7d88e-149">Columns are delimited by a comma.</span></span>|  
|<span data-ttu-id="7d88e-150">**Tabulation {t}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-150">**Tab {t}**</span></span>|<span data-ttu-id="7d88e-151">Les colonnes sont séparées par une tabulation.</span><span class="sxs-lookup"><span data-stu-id="7d88e-151">Columns are delimited by a tab.</span></span>|  
|<span data-ttu-id="7d88e-152">**Barre verticale {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-152">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="7d88e-153">Les colonnes sont séparées par une barre verticale.</span><span class="sxs-lookup"><span data-stu-id="7d88e-153">Columns are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="7d88e-154">**Réinitialiser les colonnes**</span><span class="sxs-lookup"><span data-stu-id="7d88e-154">**Reset Columns**</span></span>  
 <span data-ttu-id="7d88e-155">Cliquez sur **Réinitialiser les colonnes**pour supprimer toutes les colonnes à l’exception de celles d’origine.</span><span class="sxs-lookup"><span data-stu-id="7d88e-155">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--fixed-width"></a><span data-ttu-id="7d88e-156">Format = Largeur fixe</span><span class="sxs-lookup"><span data-stu-id="7d88e-156">Format = Fixed Width</span></span>  
 <span data-ttu-id="7d88e-157">**Police**</span><span class="sxs-lookup"><span data-stu-id="7d88e-157">**Font**</span></span>  
 <span data-ttu-id="7d88e-158">Sélectionnez la police d'affichage de l'aperçu des données.</span><span class="sxs-lookup"><span data-stu-id="7d88e-158">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="7d88e-159">**Colonnes de données sources**</span><span class="sxs-lookup"><span data-stu-id="7d88e-159">**Source data columns**</span></span>  
 <span data-ttu-id="7d88e-160">Ajustez la largeur de la ligne en faisant glisser le marqueur de ligne vertical, et celle des colonnes en cliquant sur la règle en haut de la fenêtre d'aperçu.</span><span class="sxs-lookup"><span data-stu-id="7d88e-160">Adjust the width of the row by sliding the vertical row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="7d88e-161">**Largeur de ligne**</span><span class="sxs-lookup"><span data-stu-id="7d88e-161">**Row width**</span></span>  
 <span data-ttu-id="7d88e-162">Spécifiez la largeur de la ligne avant d'ajouter des séparateurs pour des colonnes distinctes.</span><span class="sxs-lookup"><span data-stu-id="7d88e-162">Specify the length of the row before adding delimiters for individual columns.</span></span> <span data-ttu-id="7d88e-163">Vous pouvez également faire glisser la ligne verticale dans la fenêtre d'aperçu pour marquer la fin de la ligne.</span><span class="sxs-lookup"><span data-stu-id="7d88e-163">Or, drag the vertical line in the preview window to mark the end of the row.</span></span> <span data-ttu-id="7d88e-164">La valeur de la largeur de ligne est automatiquement mise à jour.</span><span class="sxs-lookup"><span data-stu-id="7d88e-164">The row width value is automatically updated.</span></span>  
  
 <span data-ttu-id="7d88e-165">**Réinitialiser les colonnes**</span><span class="sxs-lookup"><span data-stu-id="7d88e-165">**Reset Columns**</span></span>  
 <span data-ttu-id="7d88e-166">Cliquez sur **Réinitialiser les colonnes**pour supprimer toutes les colonnes à l’exception de celles d’origine.</span><span class="sxs-lookup"><span data-stu-id="7d88e-166">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--ragged-right"></a><span data-ttu-id="7d88e-167">Format = En drapeau à droite</span><span class="sxs-lookup"><span data-stu-id="7d88e-167">Format = Ragged Right</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7d88e-168">Les fichiers en drapeau à droite sont ceux dans lesquels chaque colonne possède une largeur fixe, à l'exception de la dernière.</span><span class="sxs-lookup"><span data-stu-id="7d88e-168">Ragged right files are those in which every column has a fixed width, except for the last column.</span></span> <span data-ttu-id="7d88e-169">Un séparateur de lignes s'applique.</span><span class="sxs-lookup"><span data-stu-id="7d88e-169">It is delimited by the row delimiter.</span></span>  
  
 <span data-ttu-id="7d88e-170">**Police**</span><span class="sxs-lookup"><span data-stu-id="7d88e-170">**Font**</span></span>  
 <span data-ttu-id="7d88e-171">Sélectionnez la police d'affichage de l'aperçu des données.</span><span class="sxs-lookup"><span data-stu-id="7d88e-171">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="7d88e-172">**Colonnes de données sources**</span><span class="sxs-lookup"><span data-stu-id="7d88e-172">**Source data columns**</span></span>  
 <span data-ttu-id="7d88e-173">Ajustez la largeur de la ligne en faisant glisser le marqueur de ligne vertical, et celle des colonnes en cliquant sur la règle en haut de la fenêtre d'aperçu.</span><span class="sxs-lookup"><span data-stu-id="7d88e-173">Adjust the width of the row by sliding the vertical row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="7d88e-174">**Séparateur de lignes**</span><span class="sxs-lookup"><span data-stu-id="7d88e-174">**Row delimiter**</span></span>  
 <span data-ttu-id="7d88e-175">Effectuez une sélection dans la liste des séparateurs de lignes disponibles ou entrez le texte du séparateur.</span><span class="sxs-lookup"><span data-stu-id="7d88e-175">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="7d88e-176">Valeur</span><span class="sxs-lookup"><span data-stu-id="7d88e-176">Value</span></span>|<span data-ttu-id="7d88e-177">Description</span><span class="sxs-lookup"><span data-stu-id="7d88e-177">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7d88e-178">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-178">**{CR}{LF}**</span></span>|<span data-ttu-id="7d88e-179">Les lignes sont séparées par une combinaison de retour chariot/saut de ligne.</span><span class="sxs-lookup"><span data-stu-id="7d88e-179">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="7d88e-180">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-180">**{CR}**</span></span>|<span data-ttu-id="7d88e-181">Les lignes sont séparées par un retour chariot.</span><span class="sxs-lookup"><span data-stu-id="7d88e-181">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="7d88e-182">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-182">**{LF}**</span></span>|<span data-ttu-id="7d88e-183">Les lignes sont séparées par un saut de ligne.</span><span class="sxs-lookup"><span data-stu-id="7d88e-183">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="7d88e-184">**Point-virgule {;}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-184">**Semicolon {;}**</span></span>|<span data-ttu-id="7d88e-185">Les lignes sont séparées par un point-virgule.</span><span class="sxs-lookup"><span data-stu-id="7d88e-185">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="7d88e-186">**Deux-points {:}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-186">**Colon {:}**</span></span>|<span data-ttu-id="7d88e-187">Les lignes sont séparées par un deux-points.</span><span class="sxs-lookup"><span data-stu-id="7d88e-187">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="7d88e-188">**Virgule {,}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-188">**Comma {,}**</span></span>|<span data-ttu-id="7d88e-189">Les lignes sont séparées par une virgule.</span><span class="sxs-lookup"><span data-stu-id="7d88e-189">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="7d88e-190">**Tabulation {t}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-190">**Tab {t}**</span></span>|<span data-ttu-id="7d88e-191">Les lignes sont séparées par une tabulation.</span><span class="sxs-lookup"><span data-stu-id="7d88e-191">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="7d88e-192">**Barre verticale {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="7d88e-192">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="7d88e-193">Les lignes sont séparées par une barre verticale.</span><span class="sxs-lookup"><span data-stu-id="7d88e-193">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="7d88e-194">**Réinitialiser les colonnes**</span><span class="sxs-lookup"><span data-stu-id="7d88e-194">**Reset Columns**</span></span>  
 <span data-ttu-id="7d88e-195">Cliquez sur **Réinitialiser les colonnes**pour supprimer toutes les colonnes à l’exception de celles d’origine.</span><span class="sxs-lookup"><span data-stu-id="7d88e-195">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d88e-196">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7d88e-196">See Also</span></span>  
 <span data-ttu-id="7d88e-197">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="7d88e-197">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="7d88e-198">[Éditeur du gestionnaire de connexions de fichiers plats multiples &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="7d88e-198">[Multiple Flat Files Connection Manager Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="7d88e-199">[Éditeur du gestionnaire de connexions de fichiers plats multiples &#40;page avancé&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="7d88e-199">[Multiple Flat Files Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="7d88e-200">Éditeur du gestionnaire de connexions de fichiers plats multiples &#40;page Aperçu&#41;</span><span class="sxs-lookup"><span data-stu-id="7d88e-200">Multiple Flat Files Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/multiple-flat-files-connection-manager-editor-preview-page.md)  
  
  
