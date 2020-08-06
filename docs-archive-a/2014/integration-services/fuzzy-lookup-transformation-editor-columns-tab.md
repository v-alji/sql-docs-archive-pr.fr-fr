---
title: Éditeur de transformation de recherche floue (onglet colonnes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzylookuptransformation.columns.f1
helpviewer_keywords:
- Fuzzy Lookup Transformation Editor
ms.assetid: aaf45327-79e9-4760-9b4d-546ace91b5b4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f9294022b52536940916a381d7b811437eaa5814
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696987"
---
# <a name="fuzzy-lookup-transformation-editor-columns-tab"></a><span data-ttu-id="09dbd-102">Éditeur de transformation de recherche floue (onglet Colonnes)</span><span class="sxs-lookup"><span data-stu-id="09dbd-102">Fuzzy Lookup Transformation Editor (Columns Tab)</span></span>
  <span data-ttu-id="09dbd-103">L'onglet **Colonnes** de la boîte de dialogue **Éditeur de transformation de recherche floue** vous permet de définir les propriétés des colonnes d'entrée et de sortie.</span><span class="sxs-lookup"><span data-stu-id="09dbd-103">Use the **Columns** tab of the **Fuzzy Lookup Transformation Editor** dialog box to set properties for input and output columns.</span></span>  
  
 <span data-ttu-id="09dbd-104">Pour en savoir plus sur la transformation de recherche floue, consultez [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="09dbd-104">To learn more about the Fuzzy Lookup transformation, see [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="09dbd-105">Options</span><span class="sxs-lookup"><span data-stu-id="09dbd-105">Options</span></span>  
 <span data-ttu-id="09dbd-106">**Colonnes d'entrée disponibles**</span><span class="sxs-lookup"><span data-stu-id="09dbd-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="09dbd-107">Faites glisser les colonnes d'entrée sur les colonnes de recherche afin de les y connecter.</span><span class="sxs-lookup"><span data-stu-id="09dbd-107">Drag input columns to connect them to available lookup columns.</span></span> <span data-ttu-id="09dbd-108">Ces colonnes doivent avoir le même type de données pris en charge.</span><span class="sxs-lookup"><span data-stu-id="09dbd-108">These columns must have matching, supported data types.</span></span> <span data-ttu-id="09dbd-109">Sélectionnez une ligne de mappage et cliquez avec le bouton droit pour modifier les mappages dans la boîte de dialogue [Créer des relations](data-flow/transformations/create-relationships.md) .</span><span class="sxs-lookup"><span data-stu-id="09dbd-109">Select a mapping line and right-click to edit the mappings in the [Create Relationships](data-flow/transformations/create-relationships.md) dialog box.</span></span>  
  
 <span data-ttu-id="09dbd-110">**Nom**</span><span class="sxs-lookup"><span data-stu-id="09dbd-110">**Name**</span></span>  
 <span data-ttu-id="09dbd-111">Permet d'afficher les noms des colonnes d'entrée disponibles.</span><span class="sxs-lookup"><span data-stu-id="09dbd-111">View the names of the available input columns.</span></span>  
  
 <span data-ttu-id="09dbd-112">**Transfert direct**</span><span class="sxs-lookup"><span data-stu-id="09dbd-112">**Pass Through**</span></span>  
 <span data-ttu-id="09dbd-113">Permet d'indiquer s'il convient d'inclure les colonnes d'entrée dans la sortie de la transformation.</span><span class="sxs-lookup"><span data-stu-id="09dbd-113">Specify whether to include the input columns in the output of the transformation.</span></span>  
  
 <span data-ttu-id="09dbd-114">**Colonnes de recherche disponibles**</span><span class="sxs-lookup"><span data-stu-id="09dbd-114">**Available Lookup Columns**</span></span>  
 <span data-ttu-id="09dbd-115">Ces cases à cocher vous permettent de choisir les colonnes sur lesquelles les opérations de recherche floue doivent porter.</span><span class="sxs-lookup"><span data-stu-id="09dbd-115">Use the check boxes to select columns on which to perform fuzzy lookup operations.</span></span>  
  
 <span data-ttu-id="09dbd-116">**colonne de recherche**</span><span class="sxs-lookup"><span data-stu-id="09dbd-116">**Lookup Column**</span></span>  
 <span data-ttu-id="09dbd-117">Permet de choisir les colonnes de recherche floue dans la liste des colonnes disponibles de la table de référence.</span><span class="sxs-lookup"><span data-stu-id="09dbd-117">Select lookup columns from the list of available reference table columns.</span></span> <span data-ttu-id="09dbd-118">Vos sélections se reflètent dans les sélections des cases à cocher tirées de la table **Colonnes de recherche disponibles** .</span><span class="sxs-lookup"><span data-stu-id="09dbd-118">Your selections are reflected in the check box selections in the **Available Lookup Columns** table.</span></span> <span data-ttu-id="09dbd-119">En sélectionnant une colonne dans la table **Colonnes de recherche disponibles** , vous créez ainsi une colonne de sortie contenant la valeur de la colonne issue de la table de référence de chaque ligne retournée y correspondant.</span><span class="sxs-lookup"><span data-stu-id="09dbd-119">Selecting a column in the **Available Lookup Columns** table creates an output column that contains the reference table column value for each matching row returned.</span></span>  
  
 <span data-ttu-id="09dbd-120">**Alias de sortie**</span><span class="sxs-lookup"><span data-stu-id="09dbd-120">**Output Alias**</span></span>  
 <span data-ttu-id="09dbd-121">Permet de saisir un alias pour la sortie de chaque colonne de recherche.</span><span class="sxs-lookup"><span data-stu-id="09dbd-121">Type an alias for the output for each lookup column.</span></span> <span data-ttu-id="09dbd-122">La valeur par défaut correspond au nom de la colonne de recherche suivi d'une valeur d'index numérique. Vous pouvez cependant choisir tout autre nom descriptif s'il reste unique.</span><span class="sxs-lookup"><span data-stu-id="09dbd-122">The default is the name of the lookup column with a numeric index value appended; however, you can choose any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09dbd-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="09dbd-123">See Also</span></span>  
 <span data-ttu-id="09dbd-124">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="09dbd-124">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="09dbd-125">[Éditeur de transformation de recherche floue &#40;onglet de la table de référence&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-reference-table-tab.md) </span><span class="sxs-lookup"><span data-stu-id="09dbd-125">[Fuzzy Lookup Transformation Editor &#40;Reference Table Tab&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-reference-table-tab.md) </span></span>  
 [<span data-ttu-id="09dbd-126">Éditeur de transformation de recherche floue &#40;onglet Avancé&#41;</span><span class="sxs-lookup"><span data-stu-id="09dbd-126">Fuzzy Lookup Transformation Editor &#40;Advanced Tab&#41;</span></span>](../../2014/integration-services/fuzzy-lookup-transformation-editor-advanced-tab.md)  
  
  
