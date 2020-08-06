---
title: Éditeur du gestionnaire de connexions de fichiers plats (page colonnes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ffileconnection.columns.f1
helpviewer_keywords:
- Flat File Connection Manager Editor
ms.assetid: 40ce7537-abd0-4973-97fd-6ccb90fddfa0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f6ce579f73922d2eaa2c48e98a98f52cd5836f5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601603"
---
# <a name="flat-file-connection-manager-editor-columns-page"></a><span data-ttu-id="0901b-102">Éditeur du gestionnaire de connexions de fichiers plats (page Colonnes)</span><span class="sxs-lookup"><span data-stu-id="0901b-102">Flat File Connection Manager Editor (Columns Page)</span></span>
  <span data-ttu-id="0901b-103">La page **Colonnes** de la boîte de dialogue **Éditeur du gestionnaire de connexions de fichiers plats** vous permet de spécifier les informations de ligne et de colonne, ainsi que d'afficher un aperçu du fichier.</span><span class="sxs-lookup"><span data-stu-id="0901b-103">Use the **Columns** page of the **Flat File Connection Manager Editor** dialog box to specify the row and column information, and to preview the file.</span></span>  
  
 <span data-ttu-id="0901b-104">Pour en savoir plus sur le gestionnaire de connexions de fichiers plats, consultez [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="0901b-104">To learn more about the Flat File connection manager, see [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="0901b-105">Options statiques</span><span class="sxs-lookup"><span data-stu-id="0901b-105">Static Options</span></span>  
 <span data-ttu-id="0901b-106">**Nom du gestionnaire de connexions**</span><span class="sxs-lookup"><span data-stu-id="0901b-106">**Connection manager name**</span></span>  
 <span data-ttu-id="0901b-107">Fournit un nom unique pour la connexion de fichiers plats du flux de travail.</span><span class="sxs-lookup"><span data-stu-id="0901b-107">Provide a unique name for the Flat File connection in the workflow.</span></span> <span data-ttu-id="0901b-108">Le nom fourni sera affiché dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0901b-108">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="0901b-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="0901b-109">**Description**</span></span>  
 <span data-ttu-id="0901b-110">Décrit la connexion.</span><span class="sxs-lookup"><span data-stu-id="0901b-110">Describe the connection.</span></span> <span data-ttu-id="0901b-111">Il est recommandé d'indiquer ici l'usage auquel la connexion est destinée, de sorte que les packages soient correctement documentés et plus faciles à gérer.</span><span class="sxs-lookup"><span data-stu-id="0901b-111">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
## <a name="flat-file-format-dynamic-options"></a><span data-ttu-id="0901b-112">Options dynamiques de format de fichier plat</span><span class="sxs-lookup"><span data-stu-id="0901b-112">Flat File Format Dynamic Options</span></span>  
  
### <a name="format--delimited"></a><span data-ttu-id="0901b-113">Format = Délimité</span><span class="sxs-lookup"><span data-stu-id="0901b-113">Format = Delimited</span></span>  
 <span data-ttu-id="0901b-114">**Séparateur de lignes**</span><span class="sxs-lookup"><span data-stu-id="0901b-114">**Row delimiter**</span></span>  
 <span data-ttu-id="0901b-115">Effectuez une sélection dans la liste des séparateurs de lignes disponibles ou entrez le texte du séparateur.</span><span class="sxs-lookup"><span data-stu-id="0901b-115">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="0901b-116">Valeur</span><span class="sxs-lookup"><span data-stu-id="0901b-116">Value</span></span>|<span data-ttu-id="0901b-117">Description</span><span class="sxs-lookup"><span data-stu-id="0901b-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0901b-118">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="0901b-118">**{CR}{LF}**</span></span>|<span data-ttu-id="0901b-119">Les lignes sont séparées par une combinaison de retour chariot/saut de ligne.</span><span class="sxs-lookup"><span data-stu-id="0901b-119">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="0901b-120">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="0901b-120">**{CR}**</span></span>|<span data-ttu-id="0901b-121">Les lignes sont séparées par un retour chariot.</span><span class="sxs-lookup"><span data-stu-id="0901b-121">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="0901b-122">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="0901b-122">**{LF}**</span></span>|<span data-ttu-id="0901b-123">Les lignes sont séparées par un saut de ligne.</span><span class="sxs-lookup"><span data-stu-id="0901b-123">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="0901b-124">**Point-virgule {;}**</span><span class="sxs-lookup"><span data-stu-id="0901b-124">**Semicolon {;}**</span></span>|<span data-ttu-id="0901b-125">Les lignes sont séparées par un point-virgule.</span><span class="sxs-lookup"><span data-stu-id="0901b-125">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="0901b-126">**Deux-points {:}**</span><span class="sxs-lookup"><span data-stu-id="0901b-126">**Colon {:}**</span></span>|<span data-ttu-id="0901b-127">Les lignes sont séparées par un deux-points.</span><span class="sxs-lookup"><span data-stu-id="0901b-127">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="0901b-128">**Virgule {,}**</span><span class="sxs-lookup"><span data-stu-id="0901b-128">**Comma {,}**</span></span>|<span data-ttu-id="0901b-129">Les lignes sont séparées par une virgule.</span><span class="sxs-lookup"><span data-stu-id="0901b-129">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="0901b-130">**Tabulation {t}**</span><span class="sxs-lookup"><span data-stu-id="0901b-130">**Tab {t}**</span></span>|<span data-ttu-id="0901b-131">Les lignes sont séparées par une tabulation.</span><span class="sxs-lookup"><span data-stu-id="0901b-131">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="0901b-132">**Barre verticale {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="0901b-132">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="0901b-133">Les lignes sont séparées par une barre verticale.</span><span class="sxs-lookup"><span data-stu-id="0901b-133">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="0901b-134">**Délimiteur de colonne**</span><span class="sxs-lookup"><span data-stu-id="0901b-134">**Column delimiter**</span></span>  
 <span data-ttu-id="0901b-135">Effectuez une sélection dans la liste des séparateurs de colonnes disponibles ou entrez le texte du séparateur.</span><span class="sxs-lookup"><span data-stu-id="0901b-135">Select from the list of available column delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="0901b-136">Valeur</span><span class="sxs-lookup"><span data-stu-id="0901b-136">Value</span></span>|<span data-ttu-id="0901b-137">Description</span><span class="sxs-lookup"><span data-stu-id="0901b-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0901b-138">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="0901b-138">**{CR}{LF}**</span></span>|<span data-ttu-id="0901b-139">Les colonnes sont délimitées par une combinaison retour chariot-saut de ligne.</span><span class="sxs-lookup"><span data-stu-id="0901b-139">Columns are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="0901b-140">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="0901b-140">**{CR}**</span></span>|<span data-ttu-id="0901b-141">Les colonnes sont séparées par un retour chariot.</span><span class="sxs-lookup"><span data-stu-id="0901b-141">Columns are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="0901b-142">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="0901b-142">**{LF}**</span></span>|<span data-ttu-id="0901b-143">Les colonnes sont séparées par un saut de ligne.</span><span class="sxs-lookup"><span data-stu-id="0901b-143">Columns are delimited by a line feed.</span></span>|  
|<span data-ttu-id="0901b-144">**Point-virgule {;}**</span><span class="sxs-lookup"><span data-stu-id="0901b-144">**Semicolon {;}**</span></span>|<span data-ttu-id="0901b-145">Les colonnes sont séparées par un point-virgule.</span><span class="sxs-lookup"><span data-stu-id="0901b-145">Columns are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="0901b-146">**Deux-points {:}**</span><span class="sxs-lookup"><span data-stu-id="0901b-146">**Colon {:}**</span></span>|<span data-ttu-id="0901b-147">Les colonnes sont séparées par un deux-points.</span><span class="sxs-lookup"><span data-stu-id="0901b-147">Columns are delimited by a colon.</span></span>|  
|<span data-ttu-id="0901b-148">**Virgule {,}**</span><span class="sxs-lookup"><span data-stu-id="0901b-148">**Comma {,}**</span></span>|<span data-ttu-id="0901b-149">Les colonnes sont séparées par une virgule.</span><span class="sxs-lookup"><span data-stu-id="0901b-149">Columns are delimited by a comma.</span></span>|  
|<span data-ttu-id="0901b-150">**Tabulation {t}**</span><span class="sxs-lookup"><span data-stu-id="0901b-150">**Tab {t}**</span></span>|<span data-ttu-id="0901b-151">Les colonnes sont séparées par une tabulation.</span><span class="sxs-lookup"><span data-stu-id="0901b-151">Columns are delimited by a tab.</span></span>|  
|<span data-ttu-id="0901b-152">**Barre verticale {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="0901b-152">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="0901b-153">Les colonnes sont séparées par une barre verticale.</span><span class="sxs-lookup"><span data-stu-id="0901b-153">Columns are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="0901b-154">**Actualiser**</span><span class="sxs-lookup"><span data-stu-id="0901b-154">**Refresh**</span></span>  
 <span data-ttu-id="0901b-155">Affichez les résultats des modifications des séparateurs en cliquant sur **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="0901b-155">View the effect of changing the delimiters to skip by clicking **Refresh**.</span></span> <span data-ttu-id="0901b-156">Il ne devient visible qu'après avoir changé d'autres options de connexion.</span><span class="sxs-lookup"><span data-stu-id="0901b-156">This button only becomes visible after you have changed other connection options.</span></span>  
  
 <span data-ttu-id="0901b-157">**Aperçu des lignes**</span><span class="sxs-lookup"><span data-stu-id="0901b-157">**Preview rows**</span></span>  
 <span data-ttu-id="0901b-158">Affichez les données d'exemple dans le fichier plat, divisées en colonnes et en lignes à l'aide des options sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="0901b-158">View sample data in the flat file, divided into columns and rows by using the options selected.</span></span>  
  
 <span data-ttu-id="0901b-159">**Réinitialiser les colonnes**</span><span class="sxs-lookup"><span data-stu-id="0901b-159">**Reset Columns**</span></span>  
 <span data-ttu-id="0901b-160">Cliquez sur **Réinitialiser les colonnes**pour supprimer toutes les colonnes à l’exception de celles d’origine.</span><span class="sxs-lookup"><span data-stu-id="0901b-160">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--fixed-width"></a><span data-ttu-id="0901b-161">Format = Largeur fixe</span><span class="sxs-lookup"><span data-stu-id="0901b-161">Format = Fixed Width</span></span>  
 <span data-ttu-id="0901b-162">**Police**</span><span class="sxs-lookup"><span data-stu-id="0901b-162">**Font**</span></span>  
 <span data-ttu-id="0901b-163">Sélectionnez la police d'affichage de l'aperçu des données.</span><span class="sxs-lookup"><span data-stu-id="0901b-163">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="0901b-164">**Colonnes de données sources**</span><span class="sxs-lookup"><span data-stu-id="0901b-164">**Source data columns**</span></span>  
 <span data-ttu-id="0901b-165">Ajustez la largeur de la ligne en faisant glisser le marqueur de ligne rouge vertical, et celle des colonnes en cliquant sur la règle en haut de la fenêtre d'aperçu.</span><span class="sxs-lookup"><span data-stu-id="0901b-165">Adjust the width of the row by sliding the vertical red row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="0901b-166">**Largeur de ligne**</span><span class="sxs-lookup"><span data-stu-id="0901b-166">**Row width**</span></span>  
 <span data-ttu-id="0901b-167">Spécifiez la largeur de la ligne avant d'ajouter des séparateurs pour des colonnes distinctes.</span><span class="sxs-lookup"><span data-stu-id="0901b-167">Specify the length of the row before adding delimiters for individual columns.</span></span> <span data-ttu-id="0901b-168">Vous pouvez également faire glisser la ligne rouge verticale dans la fenêtre d'aperçu pour marquer la fin de la ligne.</span><span class="sxs-lookup"><span data-stu-id="0901b-168">Or, drag the vertical red line in the preview window to mark the end of the row.</span></span> <span data-ttu-id="0901b-169">La valeur de la largeur de ligne est automatiquement mise à jour.</span><span class="sxs-lookup"><span data-stu-id="0901b-169">The row width value is automatically updated.</span></span>  
  
 <span data-ttu-id="0901b-170">**Réinitialiser les colonnes**</span><span class="sxs-lookup"><span data-stu-id="0901b-170">**Reset Columns**</span></span>  
 <span data-ttu-id="0901b-171">Cliquez sur **Réinitialiser les colonnes**pour supprimer toutes les colonnes à l’exception de celles d’origine.</span><span class="sxs-lookup"><span data-stu-id="0901b-171">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--ragged-right"></a><span data-ttu-id="0901b-172">Format = En drapeau à droite</span><span class="sxs-lookup"><span data-stu-id="0901b-172">Format = Ragged Right</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0901b-173">Les fichiers en drapeau à droite sont des fichiers dans lesquels chaque colonne a une largeur fixe, à l'exception de la dernière colonne.</span><span class="sxs-lookup"><span data-stu-id="0901b-173">Ragged right files are files in which every column has a fixed width, except for the last column.</span></span> <span data-ttu-id="0901b-174">Un séparateur de lignes s'applique.</span><span class="sxs-lookup"><span data-stu-id="0901b-174">It is delimited by the row delimiter.</span></span>  
  
 <span data-ttu-id="0901b-175">**Police**</span><span class="sxs-lookup"><span data-stu-id="0901b-175">**Font**</span></span>  
 <span data-ttu-id="0901b-176">Sélectionnez la police d'affichage de l'aperçu des données.</span><span class="sxs-lookup"><span data-stu-id="0901b-176">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="0901b-177">**Colonnes de données sources**</span><span class="sxs-lookup"><span data-stu-id="0901b-177">**Source data columns**</span></span>  
 <span data-ttu-id="0901b-178">Ajustez la largeur de la ligne en faisant glisser le marqueur de ligne rouge vertical, et celle des colonnes en cliquant sur la règle en haut de la fenêtre d'aperçu.</span><span class="sxs-lookup"><span data-stu-id="0901b-178">Adjust the width of the row by sliding the vertical red row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="0901b-179">**Séparateur de lignes**</span><span class="sxs-lookup"><span data-stu-id="0901b-179">**Row delimiter**</span></span>  
 <span data-ttu-id="0901b-180">Effectuez une sélection dans la liste des séparateurs de lignes disponibles ou entrez le texte du séparateur.</span><span class="sxs-lookup"><span data-stu-id="0901b-180">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="0901b-181">Valeur</span><span class="sxs-lookup"><span data-stu-id="0901b-181">Value</span></span>|<span data-ttu-id="0901b-182">Description</span><span class="sxs-lookup"><span data-stu-id="0901b-182">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0901b-183">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="0901b-183">**{CR}{LF}**</span></span>|<span data-ttu-id="0901b-184">Les lignes sont séparées par une combinaison de retour chariot/saut de ligne.</span><span class="sxs-lookup"><span data-stu-id="0901b-184">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="0901b-185">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="0901b-185">**{CR}**</span></span>|<span data-ttu-id="0901b-186">Les lignes sont séparées par un retour chariot.</span><span class="sxs-lookup"><span data-stu-id="0901b-186">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="0901b-187">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="0901b-187">**{LF}**</span></span>|<span data-ttu-id="0901b-188">Les lignes sont séparées par un saut de ligne.</span><span class="sxs-lookup"><span data-stu-id="0901b-188">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="0901b-189">**Point-virgule {;}**</span><span class="sxs-lookup"><span data-stu-id="0901b-189">**Semicolon {;}**</span></span>|<span data-ttu-id="0901b-190">Les lignes sont séparées par un point-virgule.</span><span class="sxs-lookup"><span data-stu-id="0901b-190">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="0901b-191">**Deux-points {:}**</span><span class="sxs-lookup"><span data-stu-id="0901b-191">**Colon {:}**</span></span>|<span data-ttu-id="0901b-192">Les lignes sont séparées par un deux-points.</span><span class="sxs-lookup"><span data-stu-id="0901b-192">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="0901b-193">**Virgule {,}**</span><span class="sxs-lookup"><span data-stu-id="0901b-193">**Comma {,}**</span></span>|<span data-ttu-id="0901b-194">Les lignes sont séparées par une virgule.</span><span class="sxs-lookup"><span data-stu-id="0901b-194">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="0901b-195">**Tabulation {t}**</span><span class="sxs-lookup"><span data-stu-id="0901b-195">**Tab {t}**</span></span>|<span data-ttu-id="0901b-196">Les lignes sont séparées par une tabulation.</span><span class="sxs-lookup"><span data-stu-id="0901b-196">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="0901b-197">**Barre verticale {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="0901b-197">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="0901b-198">Les lignes sont séparées par une barre verticale.</span><span class="sxs-lookup"><span data-stu-id="0901b-198">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="0901b-199">**Réinitialiser les colonnes**</span><span class="sxs-lookup"><span data-stu-id="0901b-199">**Reset Columns**</span></span>  
 <span data-ttu-id="0901b-200">Cliquez sur **Réinitialiser les colonnes**pour supprimer toutes les colonnes à l’exception de celles d’origine.</span><span class="sxs-lookup"><span data-stu-id="0901b-200">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0901b-201">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0901b-201">See Also</span></span>  
 <span data-ttu-id="0901b-202">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="0901b-202">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="0901b-203">[Éditeur du gestionnaire de connexions de fichiers plats &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="0901b-203">[Flat File Connection Manager Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="0901b-204">[Éditeur du gestionnaire de connexions de fichiers plats &#40;page avancé&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="0901b-204">[Flat File Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="0901b-205">Éditeur du gestionnaire de connexions de fichiers plats &#40;page Aperçu&#41;</span><span class="sxs-lookup"><span data-stu-id="0901b-205">Flat File Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/flat-file-connection-manager-editor-preview-page.md)  
  
  
