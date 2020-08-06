---
title: Se connecter à un fichier plat (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connflatfile.f1
ms.assetid: a365991e-eded-4cd8-89c0-0daf6d658d15
author: minewiskan
ms.author: owend
ms.openlocfilehash: e6bee3c8f7f4b255e6985e8d783365bc8a47599e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602474"
---
# <a name="connect-to-a-flat-file-ssas"></a><span data-ttu-id="27f11-102">Connexion à un fichier plat (SSAS)</span><span class="sxs-lookup"><span data-stu-id="27f11-102">Connect to a Flat File (SSAS)</span></span>
  <span data-ttu-id="27f11-103">Cette page de **l’Assistant Importation de table** vous permet de vous connecter à un fichier plat (.txt), un fichier séparé par des tabulations (.tab) ou un fichier séparé par des virgules (.csv).</span><span class="sxs-lookup"><span data-stu-id="27f11-103">This page of the **Table Import Wizard** enables you to connect to a flat file (.txt), tab-separated file (.tab), or a comma-separated file (.csv).</span></span> <span data-ttu-id="27f11-104">Pour accéder à l'Assistant [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dans le menu **Modèle** , cliquez sur **Importer à partir de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="27f11-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="27f11-105">Pour vous connecter à un fichier plat, le fournisseur ACE doit être installé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="27f11-105">To connect to a flat file, you must have the ACE provider installed on your computer.</span></span> <span data-ttu-id="27f11-106">Pour plus d’informations, consultez [Sources de données prises en charge &#40;SSAS Tabulaire&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="27f11-106">For more information, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="27f11-107">Les informations d'identification de l'utilisateur actuel sont utilisées lors de la sélection d'un fichier dans cette page.</span><span class="sxs-lookup"><span data-stu-id="27f11-107">The credentials of the current user are used when selecting a file in this page.</span></span> <span data-ttu-id="27f11-108">Toutefois, l'importation ne réussira pas si l'utilisateur spécifié dans la page Informations d'emprunt d'identité n'a pas de privilèges suffisants pour lire le fichier sélectionné.</span><span class="sxs-lookup"><span data-stu-id="27f11-108">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected file.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="27f11-109">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="27f11-109">UI element list</span></span>  
 <span data-ttu-id="27f11-110">**Nom convivial de la connexion**</span><span class="sxs-lookup"><span data-stu-id="27f11-110">**Friendly connection name**</span></span>  
 <span data-ttu-id="27f11-111">Tapez un nom unique pour cette connexion à la source de données.</span><span class="sxs-lookup"><span data-stu-id="27f11-111">Type a unique name for this data source connection.</span></span> <span data-ttu-id="27f11-112">Ce champ est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="27f11-112">This is a required field.</span></span>  
  
 <span data-ttu-id="27f11-113">**Chemin du fichier**</span><span class="sxs-lookup"><span data-stu-id="27f11-113">**File Path**</span></span>  
 <span data-ttu-id="27f11-114">Spécifiez le chemin d'accès complet du fichier.</span><span class="sxs-lookup"><span data-stu-id="27f11-114">Specify a full path for the file.</span></span>  
  
 <span data-ttu-id="27f11-115">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="27f11-115">**Browse**</span></span>  
 <span data-ttu-id="27f11-116">Accédez à un emplacement dans lequel un fichier est disponible.</span><span class="sxs-lookup"><span data-stu-id="27f11-116">Navigate to a location where a file is available.</span></span>  
  
 <span data-ttu-id="27f11-117">**Séparateur de colonnes**</span><span class="sxs-lookup"><span data-stu-id="27f11-117">**Column Separator**</span></span>  
 <span data-ttu-id="27f11-118">Effectuez une sélection dans une liste de séparateurs de colonnes disponibles.</span><span class="sxs-lookup"><span data-stu-id="27f11-118">Select from a list of available column separators.</span></span> <span data-ttu-id="27f11-119">Choisissez un séparateur qu'il est peu probable de rencontrer dans le texte.</span><span class="sxs-lookup"><span data-stu-id="27f11-119">Choose a separator that is not likely to occur in the text.</span></span>  
  
|<span data-ttu-id="27f11-120">Valeur</span><span class="sxs-lookup"><span data-stu-id="27f11-120">Value</span></span>|<span data-ttu-id="27f11-121">Description</span><span class="sxs-lookup"><span data-stu-id="27f11-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="27f11-122">Tabulation (t)</span><span class="sxs-lookup"><span data-stu-id="27f11-122">Tab (t)</span></span>|<span data-ttu-id="27f11-123">Les colonnes sont séparées par une tabulation (t).</span><span class="sxs-lookup"><span data-stu-id="27f11-123">Columns are separated by a tab (t).</span></span>|  
|<span data-ttu-id="27f11-124">Virgule (,)</span><span class="sxs-lookup"><span data-stu-id="27f11-124">Comma (,)</span></span>|<span data-ttu-id="27f11-125">Les colonnes sont séparées par une virgule (,).</span><span class="sxs-lookup"><span data-stu-id="27f11-125">Columns are separated by a comma (,).</span></span>|  
|<span data-ttu-id="27f11-126">Point-virgule (;)</span><span class="sxs-lookup"><span data-stu-id="27f11-126">Semicolon (;)</span></span>|<span data-ttu-id="27f11-127">Les colonnes sont séparées par un point-virgule (;).</span><span class="sxs-lookup"><span data-stu-id="27f11-127">Columns are separated by a semicolon (;).</span></span>|  
|<span data-ttu-id="27f11-128">Espace ( )</span><span class="sxs-lookup"><span data-stu-id="27f11-128">Space ( )</span></span>|<span data-ttu-id="27f11-129">Les colonnes sont séparées par un espace ().</span><span class="sxs-lookup"><span data-stu-id="27f11-129">Columns are separated by a space ( ).</span></span>|  
|<span data-ttu-id="27f11-130">deux-points (:)</span><span class="sxs-lookup"><span data-stu-id="27f11-130">Colon (:)</span></span>|<span data-ttu-id="27f11-131">Les colonnes sont séparées par un deux-points (:).</span><span class="sxs-lookup"><span data-stu-id="27f11-131">Columns are separated by a colon (:).</span></span>|  
|<span data-ttu-id="27f11-132">Barre verticale (&#124;)</span><span class="sxs-lookup"><span data-stu-id="27f11-132">Vertical Bar (&#124;)</span></span>|<span data-ttu-id="27f11-133">Les colonnes sont séparées par une barre verticale (&#124;).</span><span class="sxs-lookup"><span data-stu-id="27f11-133">Columns are separated by a vertical bar (&#124;).</span></span>|  
  
 <span data-ttu-id="27f11-134">**Avancée**</span><span class="sxs-lookup"><span data-stu-id="27f11-134">**Advanced**</span></span>  
 <span data-ttu-id="27f11-135">Spécifiez les options de paramètres régionaux et d'encodage pour le fichier plat.</span><span class="sxs-lookup"><span data-stu-id="27f11-135">Specify the encoding and locale options for the flat file.</span></span>  
  
 <span data-ttu-id="27f11-136">**Utiliser la première ligne comme en-têtes de colonnes**</span><span class="sxs-lookup"><span data-stu-id="27f11-136">**Use first row as column headers**</span></span>  
 <span data-ttu-id="27f11-137">Spécifiez s'il convient d'utiliser la première ligne de données comme en-têtes de colonnes de la table de destination.</span><span class="sxs-lookup"><span data-stu-id="27f11-137">Specify whether to use the first data row as the column headers of the destination table.</span></span>  
  
 <span data-ttu-id="27f11-138">**Aperçu des données**</span><span class="sxs-lookup"><span data-stu-id="27f11-138">**Data preview**</span></span>  
 <span data-ttu-id="27f11-139">Affichez un aperçu des données dans le fichier sélectionné et utilisez les options suivantes pour modifier l'importation de données.</span><span class="sxs-lookup"><span data-stu-id="27f11-139">Preview the data in the selected file, and use the following options to modify the data import.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="27f11-140">Seules les 50 premières lignes du fichier sont affichées dans cet aperçu.</span><span class="sxs-lookup"><span data-stu-id="27f11-140">Only the first 50 rows in the file are displayed in this preview.</span></span>  
  
|<span data-ttu-id="27f11-141">Option</span><span class="sxs-lookup"><span data-stu-id="27f11-141">Option</span></span>|<span data-ttu-id="27f11-142">Description</span><span class="sxs-lookup"><span data-stu-id="27f11-142">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="27f11-143">**Case à cocher dans l'en-tête de colonne**</span><span class="sxs-lookup"><span data-stu-id="27f11-143">**Checkbox in the column header**</span></span>|<span data-ttu-id="27f11-144">Activez la case à cocher pour inclure la colonne lors de l'importation des données.</span><span class="sxs-lookup"><span data-stu-id="27f11-144">Select the checkbox to include the column in the data import.</span></span> <span data-ttu-id="27f11-145">Désactivez la case à cocher pour supprimer la colonne lors de l'importation de données.</span><span class="sxs-lookup"><span data-stu-id="27f11-145">Clear the checkbox to remove the column from the data import.</span></span>|  
|<span data-ttu-id="27f11-146">**Bouton Flèche vers le bas dans l'en-tête de colonne**</span><span class="sxs-lookup"><span data-stu-id="27f11-146">**Down-arrow button in the column header**</span></span>|<span data-ttu-id="27f11-147">Triez et filtrez les données dans la colonne.</span><span class="sxs-lookup"><span data-stu-id="27f11-147">Sort and filter data in the column.</span></span>|  
  
 <span data-ttu-id="27f11-148">**Désactiver les filtres de lignes**</span><span class="sxs-lookup"><span data-stu-id="27f11-148">**Clear Row Filters**</span></span>  
 <span data-ttu-id="27f11-149">Supprimez tous les filtres appliqués aux données dans les colonnes.</span><span class="sxs-lookup"><span data-stu-id="27f11-149">Remove all filters that were applied to the data in the columns.</span></span>  
  
  
