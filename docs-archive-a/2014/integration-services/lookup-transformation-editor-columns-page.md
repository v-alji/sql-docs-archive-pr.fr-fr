---
title: Éditeur de transformation de recherche (page colonnes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.columns.f1
helpviewer_keywords:
- Lookup Transformation Editor
ms.assetid: 690ffef5-fd59-4e95-a27d-4fcf0d6b1c0b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b768076d8acbcaef8cbff21783a7697020e027eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605554"
---
# <a name="lookup-transformation-editor-columns-page"></a><span data-ttu-id="5103a-102">Éditeur de transformation de recherche (page Colonnes)</span><span class="sxs-lookup"><span data-stu-id="5103a-102">Lookup Transformation Editor (Columns Page)</span></span>
  <span data-ttu-id="5103a-103">Utilisez la page **Colonnes** de la boîte de dialogue **Éditeur de transformation de recherche** pour définir la jointure entre la table source et la table de référence, ainsi que pour sélectionner les colonnes de recherche dans la table de référence.</span><span class="sxs-lookup"><span data-stu-id="5103a-103">Use the **Columns** page of the **Lookup Transformation Editor** dialog box to specify the join between the source table and the reference table, and to select lookup columns from the reference table.</span></span>  
  
 <span data-ttu-id="5103a-104">Pour en savoir plus sur la transformation de recherche, consultez [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="5103a-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5103a-105">Options</span><span class="sxs-lookup"><span data-stu-id="5103a-105">Options</span></span>  
 <span data-ttu-id="5103a-106">**Colonnes d'entrée disponibles**</span><span class="sxs-lookup"><span data-stu-id="5103a-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="5103a-107">Affichez la liste des colonnes d'entrée disponibles.</span><span class="sxs-lookup"><span data-stu-id="5103a-107">View the list of available input columns.</span></span> <span data-ttu-id="5103a-108">Les colonnes d'entrée représentent les colonnes dans le flux de données d'une source connectée.</span><span class="sxs-lookup"><span data-stu-id="5103a-108">The input columns are the columns in the data flow from a connected source.</span></span> <span data-ttu-id="5103a-109">Les colonnes d'entrée et la colonne de recherche doivent avoir des types de données identiques.</span><span class="sxs-lookup"><span data-stu-id="5103a-109">The input columns and lookup column must have matching data types.</span></span>  
  
 <span data-ttu-id="5103a-110">Au moyen d'une opération glisser-déplacer, mappez les colonnes d'entrée disponibles aux colonnes de recherche.</span><span class="sxs-lookup"><span data-stu-id="5103a-110">Use a drag-and-drop operation to map available input columns to lookup columns.</span></span>  
  
 <span data-ttu-id="5103a-111">Vous pouvez également mapper les colonnes d'entrée aux colonnes de recherche à l'aide du clavier. Pour ce faire, mettez en surbrillance une colonne dans la table **Colonnes d'entrée disponibles** , appuyez sur la touche de l'application, puis cliquez sur **Modifier les mappages**.</span><span class="sxs-lookup"><span data-stu-id="5103a-111">You can also map input columns to lookup columns using the keyboard, by highlighting a column in the **Available Input Columns** table, pressing the Application key, and then clicking **Edit Mappings**.</span></span>  
  
 <span data-ttu-id="5103a-112">**Colonnes de recherche disponibles**</span><span class="sxs-lookup"><span data-stu-id="5103a-112">**Available Lookup Columns**</span></span>  
 <span data-ttu-id="5103a-113">Affichez la liste des colonnes de recherche.</span><span class="sxs-lookup"><span data-stu-id="5103a-113">View the list of lookup columns.</span></span> <span data-ttu-id="5103a-114">Les colonnes de recherche représentent les colonnes de la table de référence dans lesquelles vous souhaitez rechercher des valeurs qui correspondent aux colonnes d'entrée.</span><span class="sxs-lookup"><span data-stu-id="5103a-114">The lookup columns are columns in the reference table in which you want to look up values that match the input columns.</span></span>  
  
 <span data-ttu-id="5103a-115">Au moyen d'une opération glisser-déplacer, mappez les colonnes de recherche disponibles aux colonnes d'entrée.</span><span class="sxs-lookup"><span data-stu-id="5103a-115">Use a drag-and-drop operation to map available lookup columns to input columns.</span></span>  
  
 <span data-ttu-id="5103a-116">Utilisez les cases à cocher pour sélectionner les colonnes de recherche de la table de référence sur lesquelles effectuer les opérations de recherche.</span><span class="sxs-lookup"><span data-stu-id="5103a-116">Use the check boxes to select lookup columns in the reference table on which to perform lookup operations.</span></span>  
  
 <span data-ttu-id="5103a-117">Vous pouvez également mapper les colonnes de recherche aux colonnes d'entrée à l'aide du clavier. Pour ce faire, mettez en surbrillance une colonne dans la table **Colonnes de recherche disponibles** , appuyez sur la touche de l'application, puis cliquez sur **Modifier les mappages**.</span><span class="sxs-lookup"><span data-stu-id="5103a-117">You can also map lookup columns to input columns using the keyboard, by highlighting a column in the **Available Lookup Columns** table, pressing the Application key, and then clicking **Edit Mappings**.</span></span>  
  
 <span data-ttu-id="5103a-118">**colonne de recherche**</span><span class="sxs-lookup"><span data-stu-id="5103a-118">**Lookup Column**</span></span>  
 <span data-ttu-id="5103a-119">Affichez les colonnes de recherche sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="5103a-119">View the selected lookup columns.</span></span> <span data-ttu-id="5103a-120">Les sélections se reflètent dans les sélections des cases à cocher de la table **Colonnes de recherche disponibles** .</span><span class="sxs-lookup"><span data-stu-id="5103a-120">The selections are reflected in the check box selections in the **Available Lookup Columns** table.</span></span>  
  
 <span data-ttu-id="5103a-121">**Opération de recherche**</span><span class="sxs-lookup"><span data-stu-id="5103a-121">**Lookup Operation**</span></span>  
 <span data-ttu-id="5103a-122">Dans la liste, sélectionnez une opération de recherche à exécuter sur la colonne de recherche.</span><span class="sxs-lookup"><span data-stu-id="5103a-122">Select a lookup operation from the list to perform on the lookup column.</span></span>  
  
 <span data-ttu-id="5103a-123">**Alias de sortie**</span><span class="sxs-lookup"><span data-stu-id="5103a-123">**Output Alias**</span></span>  
 <span data-ttu-id="5103a-124">Permet de saisir un alias pour la sortie de chaque colonne de recherche.</span><span class="sxs-lookup"><span data-stu-id="5103a-124">Type an alias for the output for each lookup column.</span></span> <span data-ttu-id="5103a-125">La valeur par défaut est le nom de la colonne de recherche. Toutefois, vous pouvez sélectionner n'importe quel nom descriptif unique.</span><span class="sxs-lookup"><span data-stu-id="5103a-125">The default is the name of the lookup column; however, you can select any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5103a-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5103a-126">See Also</span></span>  
 <span data-ttu-id="5103a-127">[Éditeur de transformation de recherche &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="5103a-127">[Lookup Transformation Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="5103a-128">[Éditeur de transformation de recherche &#40;page connexion&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="5103a-128">[Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span></span>  
 <span data-ttu-id="5103a-129">[Éditeur de transformation de recherche &#40;&#41;de page avancé](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="5103a-129">[Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span></span>  
 <span data-ttu-id="5103a-130">[Éditeur de transformation de recherche &#40;page sortie d’erreur&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="5103a-130">[Lookup Transformation Editor &#40;Error Output Page&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="5103a-131">transformation de recherche floue</span><span class="sxs-lookup"><span data-stu-id="5103a-131">Fuzzy Lookup Transformation</span></span>](data-flow/transformations/fuzzy-lookup-transformation.md)  
  
  
