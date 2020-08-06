---
title: Éditeur du gestionnaire de connexions de fichiers plats (page général) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ffileconnection.general.f1
helpviewer_keywords:
- Flat File Connection Manager Editor
ms.assetid: 77296024-5c1a-4f6a-9665-0b50d45d744c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 478c7bcf56e300b47af93862bf66409a3c94b5f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601605"
---
# <a name="flat-file-connection-manager-editor-general-page"></a><span data-ttu-id="b6626-102">Éditeur du gestionnaire de connexions de fichiers plats (page Général)</span><span class="sxs-lookup"><span data-stu-id="b6626-102">Flat File Connection Manager Editor (General Page)</span></span>
  <span data-ttu-id="b6626-103">La page **Général** de la boîte de dialogue **Éditeur du gestionnaire de connexions de fichiers plats** vous permet de sélectionner un format de fichier et de données.</span><span class="sxs-lookup"><span data-stu-id="b6626-103">Use the **General** page of the **Flat File Connection Manager Editor** dialog box to select a file and data format.</span></span> <span data-ttu-id="b6626-104">Une connexion de fichier plat permet à un package de se connecter à un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="b6626-104">A flat file connection enables a package to connect to a text file.</span></span>  
  
 <span data-ttu-id="b6626-105">Pour en savoir plus sur le gestionnaire de connexions de fichiers plats, consultez [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="b6626-105">To learn more about the Flat File connection manager, see [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b6626-106">Options</span><span class="sxs-lookup"><span data-stu-id="b6626-106">Options</span></span>  
 <span data-ttu-id="b6626-107">**Nom du gestionnaire de connexions**</span><span class="sxs-lookup"><span data-stu-id="b6626-107">**Connection manager name**</span></span>  
 <span data-ttu-id="b6626-108">Permet de fournir un nom unique pour la connexion de fichier plat dans le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="b6626-108">Provide a unique name for the flat file connection in the workflow.</span></span> <span data-ttu-id="b6626-109">Le nom fourni sera affiché dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6626-109">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="b6626-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="b6626-110">**Description**</span></span>  
 <span data-ttu-id="b6626-111">Décrit la connexion.</span><span class="sxs-lookup"><span data-stu-id="b6626-111">Describe the connection.</span></span> <span data-ttu-id="b6626-112">Il est recommandé d'indiquer ici l'usage auquel la connexion est destinée, de sorte que les packages soient correctement documentés et plus faciles à gérer.</span><span class="sxs-lookup"><span data-stu-id="b6626-112">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="b6626-113">**Nom de fichier**</span><span class="sxs-lookup"><span data-stu-id="b6626-113">**File name**</span></span>  
 <span data-ttu-id="b6626-114">Tapez le chemin d'accès et le nom de fichier à utiliser dans la connexion de fichier plat.</span><span class="sxs-lookup"><span data-stu-id="b6626-114">Type the path and file name to use in the flat file connection.</span></span>  
  
 <span data-ttu-id="b6626-115">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="b6626-115">**Browse**</span></span>  
 <span data-ttu-id="b6626-116">Recherchez le nom de fichier à utiliser dans la connexion de fichier plat.</span><span class="sxs-lookup"><span data-stu-id="b6626-116">Locate the file name to use in the flat file connection.</span></span>  
  
 <span data-ttu-id="b6626-117">**Paramètres régionaux**</span><span class="sxs-lookup"><span data-stu-id="b6626-117">**Locale**</span></span>  
 <span data-ttu-id="b6626-118">Spécifiez les paramètres régionaux pour fournir les informations spécifiques à la langue relatives à l'ordre et aux formats de date et d'heure.</span><span class="sxs-lookup"><span data-stu-id="b6626-118">Specify the locale to provide language-specific information for ordering and for date and time formats.</span></span>  
  
 <span data-ttu-id="b6626-119">**Unicode**</span><span class="sxs-lookup"><span data-stu-id="b6626-119">**Unicode**</span></span>  
 <span data-ttu-id="b6626-120">Indique s'il convient d'utiliser Unicode.</span><span class="sxs-lookup"><span data-stu-id="b6626-120">Indicate whether to use Unicode.</span></span> <span data-ttu-id="b6626-121">Si vous utilisez Unicode, vous ne pouvez pas spécifier de page de codes.</span><span class="sxs-lookup"><span data-stu-id="b6626-121">If you use Unicode, you cannot specify a code page.</span></span>  
  
 <span data-ttu-id="b6626-122">**Page de codes**</span><span class="sxs-lookup"><span data-stu-id="b6626-122">**Code page**</span></span>  
 <span data-ttu-id="b6626-123">Spécifiez la page de codes pour du texte non-Unicode.</span><span class="sxs-lookup"><span data-stu-id="b6626-123">Specify the code page for non-Unicode text.</span></span>  
  
 <span data-ttu-id="b6626-124">**Format**</span><span class="sxs-lookup"><span data-stu-id="b6626-124">**Format**</span></span>  
 <span data-ttu-id="b6626-125">Indique si le fichier utilise une mise en forme délimitée, à largeur fixe ou en drapeau à droite.</span><span class="sxs-lookup"><span data-stu-id="b6626-125">Indicate whether the file uses delimited, fixed width, or ragged right formatting.</span></span>  
  
|<span data-ttu-id="b6626-126">Valeur</span><span class="sxs-lookup"><span data-stu-id="b6626-126">Value</span></span>|<span data-ttu-id="b6626-127">Description</span><span class="sxs-lookup"><span data-stu-id="b6626-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b6626-128">Delimited</span><span class="sxs-lookup"><span data-stu-id="b6626-128">Delimited</span></span>|<span data-ttu-id="b6626-129">Les colonnes sont séparées par les séparateurs spécifiés à la page **Colonnes** .</span><span class="sxs-lookup"><span data-stu-id="b6626-129">Columns are separated by delimiters, specified on the **Columns** page.</span></span>|  
|<span data-ttu-id="b6626-130">Largeur fixe</span><span class="sxs-lookup"><span data-stu-id="b6626-130">Fixed width</span></span>|<span data-ttu-id="b6626-131">Les colonnes ont une largeur fixe.</span><span class="sxs-lookup"><span data-stu-id="b6626-131">Columns have a fixed width.</span></span>|  
|<span data-ttu-id="b6626-132">En drapeau à droite</span><span class="sxs-lookup"><span data-stu-id="b6626-132">Ragged right</span></span>|<span data-ttu-id="b6626-133">Les fichiers en drapeau à droite sont des fichiers dans lesquels chaque colonne a une largeur fixe, à l'exception de la dernière colonne.</span><span class="sxs-lookup"><span data-stu-id="b6626-133">Ragged right files are files in which every column has a fixed width, except for the last column.</span></span> <span data-ttu-id="b6626-134">Un séparateur de lignes s'applique.</span><span class="sxs-lookup"><span data-stu-id="b6626-134">It is delimited by the row delimiter.</span></span>|  
  
 <span data-ttu-id="b6626-135">**Qualificateur de texte**</span><span class="sxs-lookup"><span data-stu-id="b6626-135">**Text qualifier**</span></span>  
 <span data-ttu-id="b6626-136">Spécifiez le qualificateur de texte à utiliser.</span><span class="sxs-lookup"><span data-stu-id="b6626-136">Specify the text qualifier to use.</span></span> <span data-ttu-id="b6626-137">Par exemple, vous pouvez spécifier que les champs de texte soient placés entre guillemets.</span><span class="sxs-lookup"><span data-stu-id="b6626-137">For example, you can specify that text fields are enclosed in quotation marks.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b6626-138">Après avoir sélectionné un identificateur de texte, vous ne pouvez pas sélectionner de nouveau l’option **Aucun** .</span><span class="sxs-lookup"><span data-stu-id="b6626-138">After you select a text qualifier, you cannot re-select the **None** option.</span></span> <span data-ttu-id="b6626-139">Tapez **Aucun** pour désélectionner l’identificateur de texte.</span><span class="sxs-lookup"><span data-stu-id="b6626-139">Type **None** to de-select the text qualifier.</span></span>  
  
 <span data-ttu-id="b6626-140">**Séparateur de lignes d'en-tête**</span><span class="sxs-lookup"><span data-stu-id="b6626-140">**Header row delimiter**</span></span>  
 <span data-ttu-id="b6626-141">Choisissez dans la liste des séparateurs de lignes d'en-tête ou entrez le texte de séparation.</span><span class="sxs-lookup"><span data-stu-id="b6626-141">Select from the list of delimiters for header rows, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="b6626-142">Valeur</span><span class="sxs-lookup"><span data-stu-id="b6626-142">Value</span></span>|<span data-ttu-id="b6626-143">Description</span><span class="sxs-lookup"><span data-stu-id="b6626-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b6626-144">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="b6626-144">**{CR}{LF}**</span></span>|<span data-ttu-id="b6626-145">La ligne d'en-tête est séparée par une combinaison retour chariot-saut de ligne.</span><span class="sxs-lookup"><span data-stu-id="b6626-145">The header row is delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="b6626-146">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="b6626-146">**{CR}**</span></span>|<span data-ttu-id="b6626-147">La ligne d'en-tête est séparée par des retours chariot.</span><span class="sxs-lookup"><span data-stu-id="b6626-147">The header row is delimited by a carriage return.</span></span>|  
|<span data-ttu-id="b6626-148">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="b6626-148">**{LF}**</span></span>|<span data-ttu-id="b6626-149">La ligne d'en-tête est séparée par des sauts de lignes.</span><span class="sxs-lookup"><span data-stu-id="b6626-149">The header row is delimited by a line feed.</span></span>|  
|<span data-ttu-id="b6626-150">**Point-virgule {;}**</span><span class="sxs-lookup"><span data-stu-id="b6626-150">**Semicolon {;}**</span></span>|<span data-ttu-id="b6626-151">La ligne d'en-tête est séparée par des points-virgules.</span><span class="sxs-lookup"><span data-stu-id="b6626-151">The header row is delimited by a semicolon.</span></span>|  
|<span data-ttu-id="b6626-152">**Deux-points {:}**</span><span class="sxs-lookup"><span data-stu-id="b6626-152">**Colon {:}**</span></span>|<span data-ttu-id="b6626-153">La ligne d'en-tête est séparée par des deux-points.</span><span class="sxs-lookup"><span data-stu-id="b6626-153">The header row is delimited by a colon.</span></span>|  
|<span data-ttu-id="b6626-154">**Virgule {,}**</span><span class="sxs-lookup"><span data-stu-id="b6626-154">**Comma {,}**</span></span>|<span data-ttu-id="b6626-155">La ligne d'en-tête est séparée par des virgules.</span><span class="sxs-lookup"><span data-stu-id="b6626-155">The header row is delimited by a comma.</span></span>|  
|<span data-ttu-id="b6626-156">**Tabulation {t}**</span><span class="sxs-lookup"><span data-stu-id="b6626-156">**Tab {t}**</span></span>|<span data-ttu-id="b6626-157">La ligne d'en-tête est séparée par des tabulations.</span><span class="sxs-lookup"><span data-stu-id="b6626-157">The header row is delimited by a tab.</span></span>|  
|<span data-ttu-id="b6626-158">**Barre verticale {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="b6626-158">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="b6626-159">La ligne d'en-tête est séparée par des barres verticales.</span><span class="sxs-lookup"><span data-stu-id="b6626-159">The header row is delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="b6626-160">**Lignes d'en-tête à ignorer**</span><span class="sxs-lookup"><span data-stu-id="b6626-160">**Header rows to skip**</span></span>  
 <span data-ttu-id="b6626-161">Spécifiez le nombre de lignes d'en-tête ou de lignes de données initiales à ignorer, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="b6626-161">Specify the number of header rows or initial data rows to skip, if any.</span></span>  
  
 <span data-ttu-id="b6626-162">**Noms de colonnes dans la première ligne de données**</span><span class="sxs-lookup"><span data-stu-id="b6626-162">**Column names in the first data row**</span></span>  
 <span data-ttu-id="b6626-163">Indique si des noms de colonne doivent être attendus ou fournis dans la première ligne de données.</span><span class="sxs-lookup"><span data-stu-id="b6626-163">Indicate whether to expect or provide column names in the first data row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6626-164">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b6626-164">See Also</span></span>  
 <span data-ttu-id="b6626-165">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="b6626-165">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="b6626-166">[Éditeur du gestionnaire de connexions de fichiers plats &#40;page colonnes&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="b6626-166">[Flat File Connection Manager Editor &#40;Columns Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md) </span></span>  
 <span data-ttu-id="b6626-167">[Éditeur du gestionnaire de connexions de fichiers plats &#40;page avancé&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="b6626-167">[Flat File Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="b6626-168">Éditeur du gestionnaire de connexions de fichiers plats &#40;page Aperçu&#41;</span><span class="sxs-lookup"><span data-stu-id="b6626-168">Flat File Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/flat-file-connection-manager-editor-preview-page.md)  
  
  
