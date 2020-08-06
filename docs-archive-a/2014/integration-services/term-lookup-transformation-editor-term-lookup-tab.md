---
title: Éditeur de transformation de recherche de terme (onglet recherche de terme) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.termlookup.termlookup.f1
helpviewer_keywords:
- Term Lookup Transformation Editor
ms.assetid: 245d3466-d51f-4073-978a-694a8d9dfaec
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9bb8c0bd0477d9883640cc3e4d3cb25c2a3a8b27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614163"
---
# <a name="term-lookup-transformation-editor-term-lookup-tab"></a><span data-ttu-id="85e84-102">Éditeur de transformation de recherche de terme (onglet Recherche de terme)</span><span class="sxs-lookup"><span data-stu-id="85e84-102">Term Lookup Transformation Editor (Term Lookup Tab)</span></span>
  <span data-ttu-id="85e84-103">L'onglet **Recherche de terme** de la boîte de dialogue **Éditeur de transformation de recherche de terme** permet de mapper une colonne d'entrée à une colonne de recherche dans une table de référence et de fournir un alias pour chaque colonne de sortie.</span><span class="sxs-lookup"><span data-stu-id="85e84-103">Use the **Term Lookup** tab of the **Term Lookup Transformation Editor** dialog box to map an input column to a lookup column in a reference table and to provide an alias for each output column.</span></span>  
  
 <span data-ttu-id="85e84-104">Pour en savoir plus sur la transformation de recherche de terme, consultez [Term Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="85e84-104">To learn more about the Term Lookup transformation, see [Term Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="85e84-105">Options</span><span class="sxs-lookup"><span data-stu-id="85e84-105">Options</span></span>  
 <span data-ttu-id="85e84-106">**Colonnes d'entrée disponibles**</span><span class="sxs-lookup"><span data-stu-id="85e84-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="85e84-107">À l'aide des cases à cocher, sélectionnez les colonnes d'entrées à transmettre telles quelles à la sortie.</span><span class="sxs-lookup"><span data-stu-id="85e84-107">Using the check boxes, select input columns to pass through to the output unchanged.</span></span> <span data-ttu-id="85e84-108">Faites glisser une colonne d'entrée vers la liste **Colonnes de référence disponibles** pour la mapper sur une colonne de recherche dans la table de référence.</span><span class="sxs-lookup"><span data-stu-id="85e84-108">Drag an input column to the **Available Reference Columns** list to map it to a lookup column in the reference table.</span></span> <span data-ttu-id="85e84-109">Les types de données prises en charge par les colonnes d'entrée et de recherche doivent correspondre et avoir pour valeur  DT_NTEXT ou DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="85e84-109">The input and lookup columns must have matching, supported data types, either DT_NTEXT or DT_WSTR.</span></span> <span data-ttu-id="85e84-110">Sélectionnez une ligne de mappage et cliquez avec le bouton droit pour modifier les mappages dans la boîte de dialogue [Créer des relations](data-flow/transformations/create-relationships.md) .</span><span class="sxs-lookup"><span data-stu-id="85e84-110">Select a mapping line and right-click to edit the mappings in the [Create Relationships](data-flow/transformations/create-relationships.md) dialog box.</span></span>  
  
 <span data-ttu-id="85e84-111">**Colonnes de référence disponibles**</span><span class="sxs-lookup"><span data-stu-id="85e84-111">**Available Reference Columns**</span></span>  
 <span data-ttu-id="85e84-112">Affiche les colonnes disponibles dans la table de référence.</span><span class="sxs-lookup"><span data-stu-id="85e84-112">View the available columns in the reference table.</span></span> <span data-ttu-id="85e84-113">Choisissez la colonne qui contient la liste de termes correspondants.</span><span class="sxs-lookup"><span data-stu-id="85e84-113">Choose the column that contains the list of terms to match.</span></span>  
  
 <span data-ttu-id="85e84-114">**Colonne SQL directe**</span><span class="sxs-lookup"><span data-stu-id="85e84-114">**Pass-Through Column**</span></span>  
 <span data-ttu-id="85e84-115">Permet de sélectionner des colonnes dans la liste des colonnes d'entrée disponibles.</span><span class="sxs-lookup"><span data-stu-id="85e84-115">Select from the list of available input columns.</span></span> <span data-ttu-id="85e84-116">Vos sélections se reflètent dans les sélections des cases à cocher de la table **Colonnes d'entrée disponibles** .</span><span class="sxs-lookup"><span data-stu-id="85e84-116">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="85e84-117">**Alias de colonne de sortie**</span><span class="sxs-lookup"><span data-stu-id="85e84-117">**Output Column Alias**</span></span>  
 <span data-ttu-id="85e84-118">Permet de saisir un alias pour chaque colonne de sortie.</span><span class="sxs-lookup"><span data-stu-id="85e84-118">Type an alias for each output column.</span></span> <span data-ttu-id="85e84-119">La valeur par défaut correspond au nom de la colonne. Cependant, vous pouvez choisir un nom unique descriptif.</span><span class="sxs-lookup"><span data-stu-id="85e84-119">The default is the name of the column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="85e84-120">**Configurer la sortie d’erreur**</span><span class="sxs-lookup"><span data-stu-id="85e84-120">**Configure Error Output**</span></span>  
 <span data-ttu-id="85e84-121">Utilisez la boîte de dialogue [Configurer l’affichage des erreurs](../../2014/integration-services/configure-error-output.md) pour spécifier les options de gestion des erreurs dans les lignes qui provoquent des erreurs.</span><span class="sxs-lookup"><span data-stu-id="85e84-121">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling options for rows that cause errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85e84-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="85e84-122">See Also</span></span>  
 <span data-ttu-id="85e84-123">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="85e84-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="85e84-124">[Éditeur de transformation de recherche de terme &#40;onglet de la table de référence&#41;](../../2014/integration-services/term-lookup-transformation-editor-reference-table-tab.md) </span><span class="sxs-lookup"><span data-stu-id="85e84-124">[Term Lookup Transformation Editor &#40;Reference Table Tab&#41;](../../2014/integration-services/term-lookup-transformation-editor-reference-table-tab.md) </span></span>  
 <span data-ttu-id="85e84-125">[Éditeur de transformation de recherche de terme &#40;onglet Avancé&#41;](../../2014/integration-services/term-lookup-transformation-editor-advanced-tab.md) </span><span class="sxs-lookup"><span data-stu-id="85e84-125">[Term Lookup Transformation Editor &#40;Advanced Tab&#41;](../../2014/integration-services/term-lookup-transformation-editor-advanced-tab.md) </span></span>  
 [<span data-ttu-id="85e84-126">Transformation d'extraction de terme</span><span class="sxs-lookup"><span data-stu-id="85e84-126">Term Extraction Transformation</span></span>](data-flow/transformations/term-extraction-transformation.md)  
  
  
