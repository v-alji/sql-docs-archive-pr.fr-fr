---
title: Éditeur de transformation de recherche floue (onglet table de référence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzylookuptransformation.referencetable.f1
helpviewer_keywords:
- Fuzzy Lookup Transformation Editor
ms.assetid: 451f4e7d-1c8e-4784-b540-df0806509bf1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9ce51dd64c9c5807ab23ac645694cfec29a36d52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601580"
---
# <a name="fuzzy-lookup-transformation-editor-reference-table-tab"></a><span data-ttu-id="de3d9-102">Éditeur de transformation de recherche floue (onglet Table de référence)</span><span class="sxs-lookup"><span data-stu-id="de3d9-102">Fuzzy Lookup Transformation Editor (Reference Table Tab)</span></span>
  <span data-ttu-id="de3d9-103">Utilisez l’onglet **Table de référence** de la boîte de dialogue **Éditeur de transformation de recherche floue** pour définir la table source et l’index à utiliser pour la recherche.</span><span class="sxs-lookup"><span data-stu-id="de3d9-103">Use the **Reference Table** tab of the **Fuzzy Lookup Transformation Editor** dialog box to specify the source table and the index to use for the lookup.</span></span> <span data-ttu-id="de3d9-104">La source de données de référence doit être une table d’une base de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="de3d9-104">The reference data source must be a table in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="de3d9-105">La transformation de recherche floue crée une copie de travail de la table de référence.</span><span class="sxs-lookup"><span data-stu-id="de3d9-105">The Fuzzy Lookup transformation creates a working copy of the reference table.</span></span> <span data-ttu-id="de3d9-106">Les index décrits ci-dessous sont créés dans cette table de travail en utilisant une table spéciale et non un index [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] standard.</span><span class="sxs-lookup"><span data-stu-id="de3d9-106">The indexes described below are created on this working table by using a special table, not an ordinary [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] index.</span></span> <span data-ttu-id="de3d9-107">La transformation ne modifie pas les tables sources existantes si vous ne sélectionnez pas **Conserver l’index stocké**.</span><span class="sxs-lookup"><span data-stu-id="de3d9-107">The transformation does not modify the existing source tables unless you select **Maintain stored index**.</span></span> <span data-ttu-id="de3d9-108">Dans ce cas, elle crée un déclencheur dans la table de référence qui met à jour la table de travail et la table d'index de recherche en fonction des modifications apportées à la table de référence.</span><span class="sxs-lookup"><span data-stu-id="de3d9-108">In this case, it creates a trigger on the reference table that updates the working table and the lookup index table based on changes to the reference table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="de3d9-109">Les `Exhaustive` Propriétés et `MaxMemoryUsage` de la transformation de recherche floue ne sont pas disponibles dans l **'éditeur de transformation de recherche floue**, mais elles peuvent être définies à l’aide de l' **éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="de3d9-109">The `Exhaustive` and the `MaxMemoryUsage` properties of the Fuzzy Lookup transformation are not available in the **Fuzzy Lookup Transformation Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="de3d9-110">De plus, une valeur supérieure à 100 pour `MaxOutputMatchesPerInput` ne peut être spécifiée que dans le **éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="de3d9-110">In addition, a value greater than 100 for `MaxOutputMatchesPerInput` can be specified only in the **Advanced Editor**.</span></span> <span data-ttu-id="de3d9-111">Pour plus d’informations sur ces propriétés, consultez la section Transformation de recherche floue dans [Propriétés personnalisées des transformations](data-flow/transformations/transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="de3d9-111">For more information on these properties, see the Fuzzy Lookup Transformation section of [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="de3d9-112">Pour en savoir plus sur la transformation de recherche floue, consultez [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="de3d9-112">To learn more about the Fuzzy Lookup transformation, see [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="de3d9-113">Options</span><span class="sxs-lookup"><span data-stu-id="de3d9-113">Options</span></span>  
 <span data-ttu-id="de3d9-114">**Gestionnaire de connexions OLE DB**</span><span class="sxs-lookup"><span data-stu-id="de3d9-114">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="de3d9-115">Sélectionnez un gestionnaire de connexions OLE DB existant dans la liste ou créez une connexion en cliquant sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="de3d9-115">Select an existing OLE DB connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="de3d9-116">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="de3d9-116">**New**</span></span>  
 <span data-ttu-id="de3d9-117">Crée une connexion en utilisant la boîte de dialogue **Configurer le gestionnaire de connexions OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="de3d9-117">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="de3d9-118">**Créer un nouvel index**</span><span class="sxs-lookup"><span data-stu-id="de3d9-118">**Generate new index**</span></span>  
 <span data-ttu-id="de3d9-119">Indiquez que la transformation doit créer un nouvel index à utiliser pour la recherche.</span><span class="sxs-lookup"><span data-stu-id="de3d9-119">Specify that the transformation should create a new index to use for the lookup.</span></span>  
  
 <span data-ttu-id="de3d9-120">**Nom de la table de référence**</span><span class="sxs-lookup"><span data-stu-id="de3d9-120">**Reference table name**</span></span>  
 <span data-ttu-id="de3d9-121">Sélectionnez la table existante à utiliser comme table de référence (recherche).</span><span class="sxs-lookup"><span data-stu-id="de3d9-121">Select the existing table to use as the reference (lookup) table.</span></span>  
  
 <span data-ttu-id="de3d9-122">**Stocker un nouvel index**</span><span class="sxs-lookup"><span data-stu-id="de3d9-122">**Store new index**</span></span>  
 <span data-ttu-id="de3d9-123">Sélectionnez cette option pour enregistrer le nouvel index de recherche.</span><span class="sxs-lookup"><span data-stu-id="de3d9-123">Select this option if you want to save the new lookup index.</span></span>  
  
 <span data-ttu-id="de3d9-124">**Nom du nouvel index**</span><span class="sxs-lookup"><span data-stu-id="de3d9-124">**New index name**</span></span>  
 <span data-ttu-id="de3d9-125">Si vous avez décidé d'enregistrer le nouvel index de recherche, tapez un nom descriptif.</span><span class="sxs-lookup"><span data-stu-id="de3d9-125">If you have chosen to save the new lookup index, type a descriptive name for the index.</span></span>  
  
 <span data-ttu-id="de3d9-126">**Conserver l’index stocké**</span><span class="sxs-lookup"><span data-stu-id="de3d9-126">**Maintain stored index**</span></span>  
 <span data-ttu-id="de3d9-127">Si vous avez décidé d'enregistrer le nouvel index de recherche, indiquez si vous voulez également que [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] conserve l'index.</span><span class="sxs-lookup"><span data-stu-id="de3d9-127">If you have chosen to save the new lookup index, specify whether you also want [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to maintain the index.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="de3d9-128">Lorsque vous sélectionnez **Conserver l’index stocké** sous l’onglet **Table de référence** de **l’Éditeur de transformation de recherche floue**, la transformation utilise des procédures stockées managées pour maintenir l’index.</span><span class="sxs-lookup"><span data-stu-id="de3d9-128">When you select **Maintain stored index** on the **Reference Table** tab of the **Fuzzy Lookup Transformation Editor**, the transformation uses managed stored procedures to maintain the index.</span></span> <span data-ttu-id="de3d9-129">Ces procédures stockées managées utilisent la fonctionnalité de l’intégration du common language runtime (CLR) dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de3d9-129">These managed stored procedures use the common language runtime (CLR) integration feature in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="de3d9-130">Par défaut, l'intégration CLR dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] est désactivée.</span><span class="sxs-lookup"><span data-stu-id="de3d9-130">By default, CLR integration in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is not enabled.</span></span> <span data-ttu-id="de3d9-131">Pour utiliser la fonctionnalité **Conserver l’index stocké** , vous devez activer l’intégration du CLR.</span><span class="sxs-lookup"><span data-stu-id="de3d9-131">To use the **Maintain stored index** functionality, you must enable CLR integration.</span></span> <span data-ttu-id="de3d9-132">Pour plus d’informations, consultez [Activation de l’intégration du CLR](../relational-databases/clr-integration/clr-integration-enabling.md).</span><span class="sxs-lookup"><span data-stu-id="de3d9-132">For more information, see [Enabling CLR Integration](../relational-databases/clr-integration/clr-integration-enabling.md).</span></span>  
>   
>  <span data-ttu-id="de3d9-133">Dans la mesure où l’option **Conserver l’index stocké** requiert l’intégration du CLR, cette fonctionnalité n’est effective que lorsque vous sélectionnez une table de référence dans une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pour laquelle l’intégration du CLR est activée.</span><span class="sxs-lookup"><span data-stu-id="de3d9-133">Because the **Maintain stored index** option requires CLR integration, this feature works only when you select a reference table on an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] where CLR integration is enabled.</span></span>  
  
 <span data-ttu-id="de3d9-134">**Utiliser l'index existant**</span><span class="sxs-lookup"><span data-stu-id="de3d9-134">**Use existing index**</span></span>  
 <span data-ttu-id="de3d9-135">Indiquez que la transformation doit utiliser un index de recherche existant.</span><span class="sxs-lookup"><span data-stu-id="de3d9-135">Specify that the transformation should use an existing index for the lookup.</span></span>  
  
 <span data-ttu-id="de3d9-136">**Nom d'un index existant**</span><span class="sxs-lookup"><span data-stu-id="de3d9-136">**Name of an existing index**</span></span>  
 <span data-ttu-id="de3d9-137">Dans la liste, sélectionnez un index de recherche existant.</span><span class="sxs-lookup"><span data-stu-id="de3d9-137">Select a previously created lookup index from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de3d9-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="de3d9-138">See Also</span></span>  
 <span data-ttu-id="de3d9-139">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="de3d9-139">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="de3d9-140">[Éditeur de transformation de recherche floue &#40;onglet colonnes&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-columns-tab.md) </span><span class="sxs-lookup"><span data-stu-id="de3d9-140">[Fuzzy Lookup Transformation Editor &#40;Columns Tab&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-columns-tab.md) </span></span>  
 [<span data-ttu-id="de3d9-141">Éditeur de transformation de recherche floue &#40;onglet Avancé&#41;</span><span class="sxs-lookup"><span data-stu-id="de3d9-141">Fuzzy Lookup Transformation Editor &#40;Advanced Tab&#41;</span></span>](../../2014/integration-services/fuzzy-lookup-transformation-editor-advanced-tab.md)  
  
  
