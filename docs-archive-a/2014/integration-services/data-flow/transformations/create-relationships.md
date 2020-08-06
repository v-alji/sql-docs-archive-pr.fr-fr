---
title: Créer des relations | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.createrelationships.f1
ms.assetid: 6ebd305f-ffd2-4a1d-b24c-e28c151b94f5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a1095e193587ae7d416311031e5297a035ca37e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602910"
---
# <a name="create-relationships"></a><span data-ttu-id="4e420-102">Créer des relations</span><span class="sxs-lookup"><span data-stu-id="4e420-102">Create Relationships</span></span>
  <span data-ttu-id="4e420-103">Utilisez la boîte de dialogue **Créer des relations** pour modifier les mappages entre les colonnes source et les colonnes de la table de recherche configurée dans l'Éditeur de transformation de recherche floue, l'Éditeur de transformation de recherche ou l'Éditeur de transformation de recherche de terme.</span><span class="sxs-lookup"><span data-stu-id="4e420-103">Use the **Create Relationships** dialog box to edit mappings between the source columns and the lookup table columns that you configured in the Fuzzy Lookup Transformation Editor, the Lookup Transformation Editor, and the Term Lookup Transformation Editor.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4e420-104">La boîte de dialogue **Créer des relations** affiche uniquement les listes **Colonnes d’entrée** et **Colonne de recherche** quand elle est appelée à partir de l’Éditeur de transformation de recherche de terme.</span><span class="sxs-lookup"><span data-stu-id="4e420-104">The **Create Relationships** dialog box displays only the **Input Column** and **Lookup Column** lists when invoked from the Term Lookup Transformation Editor.</span></span>  
  
 <span data-ttu-id="4e420-105">Pour en savoir plus sur les transformations qui utilisent la boîte de dialogue **Créer des relations** , consultez [Fuzzy Lookup Transformation](lookup-transformation.md), [Lookup Transformation](lookup-transformation.md)et [Term Lookup Transformation](term-lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="4e420-105">To learn more about the transformations that use the **Create Relationships** dialog box, see [Fuzzy Lookup Transformation](lookup-transformation.md), [Lookup Transformation](lookup-transformation.md), and [Term Lookup Transformation](term-lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4e420-106">Options</span><span class="sxs-lookup"><span data-stu-id="4e420-106">Options</span></span>  
 <span data-ttu-id="4e420-107">**Colonne d'entrée**</span><span class="sxs-lookup"><span data-stu-id="4e420-107">**Input Column**</span></span>  
 <span data-ttu-id="4e420-108">Permet de sélectionner des colonnes dans la liste des colonnes d'entrée disponibles.</span><span class="sxs-lookup"><span data-stu-id="4e420-108">Select from the list of available input columns.</span></span>  
  
 <span data-ttu-id="4e420-109">**colonne de recherche**</span><span class="sxs-lookup"><span data-stu-id="4e420-109">**Lookup Column**</span></span>  
 <span data-ttu-id="4e420-110">Sélectionnez dans la liste des colonnes de recherche disponibles.</span><span class="sxs-lookup"><span data-stu-id="4e420-110">Select from the list of available lookup columns.</span></span>  
  
 <span data-ttu-id="4e420-111">**Type de mappage**</span><span class="sxs-lookup"><span data-stu-id="4e420-111">**Mapping Type**</span></span>  
 <span data-ttu-id="4e420-112">Sélectionnez la correspondance floue ou exacte.</span><span class="sxs-lookup"><span data-stu-id="4e420-112">Select fuzzy or exact matching.</span></span>  
  
 <span data-ttu-id="4e420-113">Lorsque vous utilisez la correspondance floue, les lignes sont considérées correspondre à des doublons si elles sont suffisamment similaires dans toutes les colonnes ayant un type de correspondance floue.</span><span class="sxs-lookup"><span data-stu-id="4e420-113">When you use fuzzy matching, rows are considered duplicates if they are sufficiently similar across all columns that have a fuzzy match type.</span></span> <span data-ttu-id="4e420-114">Pour optimiser les résultats de la correspondance floue, vous pouvez indiquer que des colonnes doivent utiliser la correspondance exacte au lieu de la correspondance floue.</span><span class="sxs-lookup"><span data-stu-id="4e420-114">To obtain better results from fuzzy matching, you can specify that some columns should use exact matching instead of fuzzy matching.</span></span> <span data-ttu-id="4e420-115">Si, par exemple, vous savez qu'une colonne ne contient pas d'erreur ou d'incohérence, vous pouvez définir la correspondance exacte sur la colonne pour que seules les lignes qui contiennent des valeurs identiques dans la colonne soient considérées comme des doublons possibles.</span><span class="sxs-lookup"><span data-stu-id="4e420-115">For example, if you know that a certain column contains no errors or inconsistencies, you can specify exact matching on that column, so that only rows which contain identical values in this column are considered as possible duplicates.</span></span> <span data-ttu-id="4e420-116">Ceci améliore la précision de la correspondance floue dans les autres colonnes.</span><span class="sxs-lookup"><span data-stu-id="4e420-116">This increases the accuracy of fuzzy matching on other columns.</span></span>  
  
 <span data-ttu-id="4e420-117">**Indicateurs de comparaison**</span><span class="sxs-lookup"><span data-stu-id="4e420-117">**Comparison Flags**</span></span>  
 <span data-ttu-id="4e420-118">Pour plus d’informations sur les options de comparaison de chaînes, consultez [Comparaison des données chaînes](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="4e420-118">For information about the string comparison options, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="4e420-119">**Similarité minimale**</span><span class="sxs-lookup"><span data-stu-id="4e420-119">**Minimum Similarity**</span></span>  
 <span data-ttu-id="4e420-120">Définissez le seuil de similarité au niveau colonne en utilisant le curseur.</span><span class="sxs-lookup"><span data-stu-id="4e420-120">Set the similarity threshold at the column level by using the slider.</span></span> <span data-ttu-id="4e420-121">Plus la valeur est proche de 1, plus la valeur de recherche doit ressembler à la valeur source pour qu'elle corresponde à une correspondance.</span><span class="sxs-lookup"><span data-stu-id="4e420-121">The closer the value is to 1, the more the lookup value must resemble the source value to qualify as a match.</span></span> <span data-ttu-id="4e420-122">L'augmentation du seuil peut accélérer les recherches du fait que moins de candidats doivent être évalués.</span><span class="sxs-lookup"><span data-stu-id="4e420-122">Increasing the threshold can improve the speed of matching because fewer candidate records have to be considered.</span></span>  
  
 <span data-ttu-id="4e420-123">**Alias de sortie de similarité**</span><span class="sxs-lookup"><span data-stu-id="4e420-123">**Similarity Output Alias**</span></span>  
 <span data-ttu-id="4e420-124">Définissez le nom d'une nouvelle colonne de sortie qui contient les scores de similarité de la colonne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4e420-124">Specify the name for a new output column that contains the similarity scores for the selected column.</span></span> <span data-ttu-id="4e420-125">Si vous ne définissez pas cette valeur, la colonne de sortie n'est pas créée.</span><span class="sxs-lookup"><span data-stu-id="4e420-125">If you leave this value empty, the output column is not created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e420-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4e420-126">See Also</span></span>  
 <span data-ttu-id="4e420-127">[Guide de référence des erreurs et des messages propres à Integration Services](../../integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="4e420-127">[Integration Services Error and Message Reference](../../integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="4e420-128">[Éditeur de transformation de recherche floue &#40;onglet Colonnes&#41;](../../fuzzy-lookup-transformation-editor-columns-tab.md) </span><span class="sxs-lookup"><span data-stu-id="4e420-128">[Fuzzy Lookup Transformation Editor &#40;Columns Tab&#41;](../../fuzzy-lookup-transformation-editor-columns-tab.md) </span></span>  
 <span data-ttu-id="4e420-129">[Éditeur de transformation de recherche &#40;page Colonnes&#41;](../../lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="4e420-129">[Lookup Transformation Editor &#40;Columns Page&#41;](../../lookup-transformation-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="4e420-130">Éditeur de transformation de recherche de terme &#40;onglet Recherche de terme&#41;</span><span class="sxs-lookup"><span data-stu-id="4e420-130">Term Lookup Transformation Editor &#40;Term Lookup Tab&#41;</span></span>](../../term-lookup-transformation-editor-term-lookup-tab.md)  
  
  
