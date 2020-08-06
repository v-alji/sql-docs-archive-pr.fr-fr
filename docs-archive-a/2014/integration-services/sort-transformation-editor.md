---
title: Éditeur de transformation de tri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sorttransformation.f1
helpviewer_keywords:
- Sort Transformation Editor
ms.assetid: 8ae23970-49a9-4d6d-9f15-c7074783347c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9f48c366f4337af29b03877f6bb20b804457a293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709711"
---
# <a name="sort-transformation-editor"></a><span data-ttu-id="c6e8e-102">Éditeur de transformation de tri</span><span class="sxs-lookup"><span data-stu-id="c6e8e-102">Sort Transformation Editor</span></span>
  <span data-ttu-id="c6e8e-103">Utilisez la boîte de dialogue **Éditeur de transformation de tri** pour sélectionner les colonnes à trier, définir l'ordre de tri et indiquer si les doublons sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="c6e8e-103">Use the **Sort Transformation Editor** dialog box to select the columns to sort, set the sort order, and specify whether duplicates are removed.</span></span>  
  
 <span data-ttu-id="c6e8e-104">Pour en savoir plus sur la transformation de tri, consultez [Sort Transformation](data-flow/transformations/sort-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="c6e8e-104">To learn more about the Sort transformation, see [Sort Transformation](data-flow/transformations/sort-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c6e8e-105">Options</span><span class="sxs-lookup"><span data-stu-id="c6e8e-105">Options</span></span>  
 <span data-ttu-id="c6e8e-106">**Colonnes d'entrée disponibles**</span><span class="sxs-lookup"><span data-stu-id="c6e8e-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="c6e8e-107">Définissez les colonnes à trier en utilisant les cases à cocher.</span><span class="sxs-lookup"><span data-stu-id="c6e8e-107">Using the check boxes, specify the columns to sort.</span></span>  
  
 <span data-ttu-id="c6e8e-108">**Nom**</span><span class="sxs-lookup"><span data-stu-id="c6e8e-108">**Name**</span></span>  
 <span data-ttu-id="c6e8e-109">Affiche le nom de chaque colonne d'entrée disponible.</span><span class="sxs-lookup"><span data-stu-id="c6e8e-109">View the name of each available input column.</span></span>  
  
 <span data-ttu-id="c6e8e-110">**Passage**</span><span class="sxs-lookup"><span data-stu-id="c6e8e-110">**Passthrough**</span></span>  
 <span data-ttu-id="c6e8e-111">Indique s'il faut inclure la colonne dans la sortie triée.</span><span class="sxs-lookup"><span data-stu-id="c6e8e-111">Indicate whether to include the column in the sorted output.</span></span>  
  
 <span data-ttu-id="c6e8e-112">**Colonne d'entrée**</span><span class="sxs-lookup"><span data-stu-id="c6e8e-112">**Input Column**</span></span>  
 <span data-ttu-id="c6e8e-113">Sélectionnez dans la liste le nom d'une colonne d'entrée pour chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="c6e8e-113">Select from the list of available input columns for each row.</span></span> <span data-ttu-id="c6e8e-114">Vos sélections se reflètent dans les sélections des cases à cocher de la table **Colonnes d'entrée disponibles** .</span><span class="sxs-lookup"><span data-stu-id="c6e8e-114">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="c6e8e-115">**Alias de sortie**</span><span class="sxs-lookup"><span data-stu-id="c6e8e-115">**Output Alias**</span></span>  
 <span data-ttu-id="c6e8e-116">Permet de saisir un alias pour chaque colonne de sortie.</span><span class="sxs-lookup"><span data-stu-id="c6e8e-116">Type an alias for each output column.</span></span> <span data-ttu-id="c6e8e-117">Par défaut, il s'agit du nom de la colonne d'entrée ; vous pouvez néanmoins choisir un nom unique et descriptif.</span><span class="sxs-lookup"><span data-stu-id="c6e8e-117">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="c6e8e-118">**Type de tri**</span><span class="sxs-lookup"><span data-stu-id="c6e8e-118">**Sort Type**</span></span>  
 <span data-ttu-id="c6e8e-119">Indiquez si vous voulez effectuer un tri croissant ou décroissant.</span><span class="sxs-lookup"><span data-stu-id="c6e8e-119">Indicate whether to sort in ascending or descending order.</span></span>  
  
 <span data-ttu-id="c6e8e-120">**Ordre de tri**</span><span class="sxs-lookup"><span data-stu-id="c6e8e-120">**Sort Order**</span></span>  
 <span data-ttu-id="c6e8e-121">Indiquez l'ordre de tri des colonnes.</span><span class="sxs-lookup"><span data-stu-id="c6e8e-121">Indicate the order in which to sort columns.</span></span> <span data-ttu-id="c6e8e-122">Vous devez le faire manuellement pour chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="c6e8e-122">This must be set manually for each column.</span></span>  
  
 <span data-ttu-id="c6e8e-123">**Indicateurs de comparaison**</span><span class="sxs-lookup"><span data-stu-id="c6e8e-123">**Comparison Flags**</span></span>  
 <span data-ttu-id="c6e8e-124">Pour plus d’informations sur les options de comparaison de chaînes, consultez [Comparaison des données chaînes](data-flow/comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="c6e8e-124">For information about the string comparison options, see [Comparing String Data](data-flow/comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="c6e8e-125">**Supprimer les lignes avec des valeurs de tri en double**</span><span class="sxs-lookup"><span data-stu-id="c6e8e-125">**Remove rows with duplicate sort values**</span></span>  
 <span data-ttu-id="c6e8e-126">Indiquez si la transformation copie les lignes en double dans la sortie de transformation ou crée une seule entrée pour tous les doublons en fonction des options de comparaison de chaînes définies.</span><span class="sxs-lookup"><span data-stu-id="c6e8e-126">Indicate whether the transformation copies duplicate rows to the transformation output, or creates a single entry for all duplicates, based on the specified string comparison options.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6e8e-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c6e8e-127">See Also</span></span>  
 [<span data-ttu-id="c6e8e-128">Guide de référence des erreurs et des messages propres à Integration Services</span><span class="sxs-lookup"><span data-stu-id="c6e8e-128">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
