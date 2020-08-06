---
title: Éditeur du gestionnaire de connexions de fichiers plats multiples (page général) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.multifile.general.f1
helpviewer_keywords:
- Multiple Flat Files Connection Manager Editor
ms.assetid: 00129d43-2772-413b-bdf8-ac5de81cf4a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f30a422794723f216d30e05f0750fb1e974e0920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705260"
---
# <a name="multiple-flat-files-connection-manager-editor-general-page"></a><span data-ttu-id="c561b-102">Éditeur du gestionnaire de connexions de fichiers plats multiples (page Général)</span><span class="sxs-lookup"><span data-stu-id="c561b-102">Multiple Flat Files Connection Manager Editor (General Page)</span></span>
  <span data-ttu-id="c561b-103">Utilisez la page **Général** de la boîte de dialogue **Éditeur du gestionnaire de connexions de fichiers plats multiples** pour sélectionner un groupe de fichiers ayant le même format de données et pour spécifier leur format de données.</span><span class="sxs-lookup"><span data-stu-id="c561b-103">Use the **General** page of the **Multiple Flat Files Connection Manager Editor** dialog box to select a group of files that have the same data format, and to specify their data format.</span></span> <span data-ttu-id="c561b-104">Une connexion de fichiers plats multiples permet à un package de se connecter à un groupe de fichiers texte ayant le même format.</span><span class="sxs-lookup"><span data-stu-id="c561b-104">A multiple flat files connection enables a package to connect to a group of text files that have the same format.</span></span>  
  
 <span data-ttu-id="c561b-105">Pour en savoir plus sur le gestionnaire de connexions de fichiers plats multiples, consultez [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c561b-105">To learn more about the Multiple Flat Files connection manager, see [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c561b-106">Options</span><span class="sxs-lookup"><span data-stu-id="c561b-106">Options</span></span>  
 <span data-ttu-id="c561b-107">**Nom du gestionnaire de connexions**</span><span class="sxs-lookup"><span data-stu-id="c561b-107">**Connection manager name**</span></span>  
 <span data-ttu-id="c561b-108">Spécifiez un nom unique pour la connexion de fichiers plats multiples dans le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="c561b-108">Provide a unique name for the Multiple Flat Files connection in the workflow.</span></span> <span data-ttu-id="c561b-109">Le nom fourni sera affiché dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c561b-109">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="c561b-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="c561b-110">**Description**</span></span>  
 <span data-ttu-id="c561b-111">Décrit la connexion.</span><span class="sxs-lookup"><span data-stu-id="c561b-111">Describe the connection.</span></span> <span data-ttu-id="c561b-112">Il est recommandé d'indiquer ici l'usage auquel la connexion est destinée, de sorte que les packages soient correctement documentés et plus faciles à gérer.</span><span class="sxs-lookup"><span data-stu-id="c561b-112">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="c561b-113">**Noms de fichiers**</span><span class="sxs-lookup"><span data-stu-id="c561b-113">**File names**</span></span>  
 <span data-ttu-id="c561b-114">Tapez le chemin d'accès et les noms de fichiers à utiliser dans la connexion de fichiers plats multiples.</span><span class="sxs-lookup"><span data-stu-id="c561b-114">Type the path and file names to use in the Multiple Flat Files connection.</span></span> <span data-ttu-id="c561b-115">Vous pouvez spécifier plusieurs fichiers à la fois en utilisant des caractères génériques (par exemple, C:\\*.txt) ou en utilisant la barre verticale (|) pour séparer plusieurs noms de fichiers.</span><span class="sxs-lookup"><span data-stu-id="c561b-115">You can specify multiple files by using wildcard characters, as in the example "C:\\*.txt", or by using the vertical pipe character (|) to separate multiple file names.</span></span> <span data-ttu-id="c561b-116">Tous les fichiers doivent avoir le même format de données.</span><span class="sxs-lookup"><span data-stu-id="c561b-116">All files must have the same data format.</span></span>  
  
 <span data-ttu-id="c561b-117">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="c561b-117">**Browse**</span></span>  
 <span data-ttu-id="c561b-118">Naviguez jusqu'aux noms de fichiers à utiliser dans la connexion de fichiers plats multiples.</span><span class="sxs-lookup"><span data-stu-id="c561b-118">Browse the file names to use in the Multiple Flat Files connection.</span></span> <span data-ttu-id="c561b-119">Vous pouvez sélectionner plusieurs fichiers.</span><span class="sxs-lookup"><span data-stu-id="c561b-119">You can select multiple files.</span></span> <span data-ttu-id="c561b-120">Tous les fichiers doivent avoir le même format de données.</span><span class="sxs-lookup"><span data-stu-id="c561b-120">All files must have the same data format.</span></span>  
  
 <span data-ttu-id="c561b-121">**Paramètres régionaux**</span><span class="sxs-lookup"><span data-stu-id="c561b-121">**Locale**</span></span>  
 <span data-ttu-id="c561b-122">Indiquez l'emplacement qui fournira les informations de classement et de conversion de la date et de l'heure.</span><span class="sxs-lookup"><span data-stu-id="c561b-122">Specify the location to provide information for ordering and for date and time conversion.</span></span>  
  
 <span data-ttu-id="c561b-123">**Unicode**</span><span class="sxs-lookup"><span data-stu-id="c561b-123">**Unicode**</span></span>  
 <span data-ttu-id="c561b-124">Indique s'il convient d'utiliser Unicode.</span><span class="sxs-lookup"><span data-stu-id="c561b-124">Indicate whether to use Unicode.</span></span> <span data-ttu-id="c561b-125">L'utilisation d'Unicode vous empêche de spécifier une page de codes.</span><span class="sxs-lookup"><span data-stu-id="c561b-125">Using Unicode precludes specifying a code page.</span></span>  
  
 <span data-ttu-id="c561b-126">**Page de codes**</span><span class="sxs-lookup"><span data-stu-id="c561b-126">**Code page**</span></span>  
 <span data-ttu-id="c561b-127">Spécifiez la page de codes pour du texte non-Unicode.</span><span class="sxs-lookup"><span data-stu-id="c561b-127">Specify the code page for non-Unicode text.</span></span>  
  
 <span data-ttu-id="c561b-128">**Format**</span><span class="sxs-lookup"><span data-stu-id="c561b-128">**Format**</span></span>  
 <span data-ttu-id="c561b-129">Permet de préciser la mise en forme à utiliser : délimitée, à largeur fixe ou en drapeau à droite.</span><span class="sxs-lookup"><span data-stu-id="c561b-129">Indicate whether to use delimited, fixed width, or ragged right formatting.</span></span> <span data-ttu-id="c561b-130">Tous les fichiers doivent avoir le même format de données.</span><span class="sxs-lookup"><span data-stu-id="c561b-130">All files must have the same data format.</span></span>  
  
|<span data-ttu-id="c561b-131">Valeur</span><span class="sxs-lookup"><span data-stu-id="c561b-131">Value</span></span>|<span data-ttu-id="c561b-132">Description</span><span class="sxs-lookup"><span data-stu-id="c561b-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c561b-133">Delimited</span><span class="sxs-lookup"><span data-stu-id="c561b-133">Delimited</span></span>|<span data-ttu-id="c561b-134">Les colonnes sont séparées par les séparateurs spécifiés à la page **Colonnes** .</span><span class="sxs-lookup"><span data-stu-id="c561b-134">Columns are separated by delimiters, specified on the **Columns** page.</span></span>|  
|<span data-ttu-id="c561b-135">Largeur fixe</span><span class="sxs-lookup"><span data-stu-id="c561b-135">Fixed width</span></span>|<span data-ttu-id="c561b-136">Les colonnes ont une largeur fixe que vous spécifiez en faisant glisser les lignes des marqueurs dans la page **Colonnes** .</span><span class="sxs-lookup"><span data-stu-id="c561b-136">Columns have a fixed width, specified by dragging marker lines on the **Columns** page.</span></span>|  
|<span data-ttu-id="c561b-137">En drapeau à droite</span><span class="sxs-lookup"><span data-stu-id="c561b-137">Ragged right</span></span>|<span data-ttu-id="c561b-138">Dans les fichiers en drapeau à droite, toutes les colonnes ont une largeur fixe, sauf la dernière, qui est délimitée par le séparateur de lignes défini dans la page **Colonnes** .</span><span class="sxs-lookup"><span data-stu-id="c561b-138">Ragged right files are files in which every column has a fixed width, except for the last column, which is delimited by the row delimiter, specified on the **Columns** page.</span></span>|  
  
 <span data-ttu-id="c561b-139">**Qualificateur de texte**</span><span class="sxs-lookup"><span data-stu-id="c561b-139">**Text qualifier**</span></span>  
 <span data-ttu-id="c561b-140">Spécifiez le qualificateur de texte à utiliser.</span><span class="sxs-lookup"><span data-stu-id="c561b-140">Specify the text qualifier to use.</span></span> <span data-ttu-id="c561b-141">Par exemple, vous pouvez spécifier de mettre le texte entre guillemets.</span><span class="sxs-lookup"><span data-stu-id="c561b-141">For example, you can specify to enclose text with quotation marks.</span></span>  
  
 <span data-ttu-id="c561b-142">**Séparateur de lignes d'en-tête**</span><span class="sxs-lookup"><span data-stu-id="c561b-142">**Header row delimiter**</span></span>  
 <span data-ttu-id="c561b-143">Choisissez dans la liste des séparateurs de lignes d'en-tête ou entrez le texte de séparation.</span><span class="sxs-lookup"><span data-stu-id="c561b-143">Select from the list of delimiters for header rows, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="c561b-144">Valeur</span><span class="sxs-lookup"><span data-stu-id="c561b-144">Value</span></span>|<span data-ttu-id="c561b-145">Description</span><span class="sxs-lookup"><span data-stu-id="c561b-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c561b-146">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="c561b-146">**{CR}{LF}**</span></span>|<span data-ttu-id="c561b-147">La ligne d'en-tête est séparée par une combinaison retour chariot-saut de ligne.</span><span class="sxs-lookup"><span data-stu-id="c561b-147">The header row is delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="c561b-148">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="c561b-148">**{CR}**</span></span>|<span data-ttu-id="c561b-149">La ligne d'en-tête est séparée par des retours chariot.</span><span class="sxs-lookup"><span data-stu-id="c561b-149">The header row is delimited by a carriage return.</span></span>|  
|<span data-ttu-id="c561b-150">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="c561b-150">**{LF}**</span></span>|<span data-ttu-id="c561b-151">La ligne d'en-tête est séparée par des sauts de lignes.</span><span class="sxs-lookup"><span data-stu-id="c561b-151">The header row is delimited by a line feed.</span></span>|  
|<span data-ttu-id="c561b-152">**Point-virgule {;}**</span><span class="sxs-lookup"><span data-stu-id="c561b-152">**Semicolon {;}**</span></span>|<span data-ttu-id="c561b-153">La ligne d'en-tête est séparée par des points-virgules.</span><span class="sxs-lookup"><span data-stu-id="c561b-153">The header row is delimited by a semicolon.</span></span>|  
|<span data-ttu-id="c561b-154">**Deux-points {:}**</span><span class="sxs-lookup"><span data-stu-id="c561b-154">**Colon {:}**</span></span>|<span data-ttu-id="c561b-155">La ligne d'en-tête est séparée par des deux-points.</span><span class="sxs-lookup"><span data-stu-id="c561b-155">The header row is delimited by a colon.</span></span>|  
|<span data-ttu-id="c561b-156">**Virgule {,}**</span><span class="sxs-lookup"><span data-stu-id="c561b-156">**Comma {,}**</span></span>|<span data-ttu-id="c561b-157">La ligne d'en-tête est séparée par des virgules.</span><span class="sxs-lookup"><span data-stu-id="c561b-157">The header row is delimited by a comma.</span></span>|  
|<span data-ttu-id="c561b-158">**Tabulation {t}**</span><span class="sxs-lookup"><span data-stu-id="c561b-158">**Tab {t}**</span></span>|<span data-ttu-id="c561b-159">La ligne d'en-tête est séparée par des tabulations.</span><span class="sxs-lookup"><span data-stu-id="c561b-159">The header row is delimited by a tab.</span></span>|  
|<span data-ttu-id="c561b-160">**Barre verticale {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="c561b-160">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="c561b-161">La ligne d'en-tête est séparée par des barres verticales.</span><span class="sxs-lookup"><span data-stu-id="c561b-161">The header row is delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="c561b-162">**Lignes d'en-tête à ignorer**</span><span class="sxs-lookup"><span data-stu-id="c561b-162">**Header rows to skip**</span></span>  
 <span data-ttu-id="c561b-163">Spécifiez le nombre de lignes d'en-tête à ignorer, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="c561b-163">Specify the number of header rows to skip, if any.</span></span>  
  
 <span data-ttu-id="c561b-164">**Noms de colonnes dans la première ligne de données**</span><span class="sxs-lookup"><span data-stu-id="c561b-164">**Column names in the first data row**</span></span>  
 <span data-ttu-id="c561b-165">Indique si des noms de colonne doivent être attendus ou fournis dans la première ligne de données.</span><span class="sxs-lookup"><span data-stu-id="c561b-165">Indicate whether to expect or provide column names in the first data row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c561b-166">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c561b-166">See Also</span></span>  
 <span data-ttu-id="c561b-167">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="c561b-167">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="c561b-168">[Éditeur du gestionnaire de connexions de fichiers plats multiples &#40;page colonnes&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="c561b-168">[Multiple Flat Files Connection Manager Editor &#40;Columns Page&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-columns-page.md) </span></span>  
 <span data-ttu-id="c561b-169">[Éditeur du gestionnaire de connexions de fichiers plats multiples &#40;page avancé&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="c561b-169">[Multiple Flat Files Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="c561b-170">Éditeur du gestionnaire de connexions de fichiers plats multiples &#40;page Aperçu&#41;</span><span class="sxs-lookup"><span data-stu-id="c561b-170">Multiple Flat Files Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/multiple-flat-files-connection-manager-editor-preview-page.md)  
  
  
