---
title: Mapper des colonnes à des domaines composites | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: d9422412-8a3d-45ae-af7f-072c902a09ba
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6a665b2096579c9da35a1b69be46c4ba6103610f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613048"
---
# <a name="map-columns-to-composite-domains"></a><span data-ttu-id="ffe9f-102">Mapper des colonnes à des domaines composites</span><span class="sxs-lookup"><span data-stu-id="ffe9f-102">Map Columns to Composite Domains</span></span>
  <span data-ttu-id="ffe9f-103">Un domaine composite comprend deux ou plusieurs domaines uniques.</span><span class="sxs-lookup"><span data-stu-id="ffe9f-103">A composite domain consists of two or more single domains.</span></span> <span data-ttu-id="ffe9f-104">Vous pouvez mapper plusieurs colonnes au domaine ou vous pouvez mapper une seule colonne de valeurs délimitées au domaine.</span><span class="sxs-lookup"><span data-stu-id="ffe9f-104">You can map multiple columns to the domain, or you can map a single column with delimited values to the domain.</span></span>  
  
 <span data-ttu-id="ffe9f-105">Lorsque vous avez plusieurs colonnes, vous devez mapper une colonne à chaque domaine unique du domaine composite pour appliquer les règles du domaine composite au nettoyage des données.</span><span class="sxs-lookup"><span data-stu-id="ffe9f-105">When you have multiple columns, you must map a column to each single domain in the composite domain to apply the composite domain rules to data cleansing.</span></span> <span data-ttu-id="ffe9f-106">Sélectionnez les domaines uniques contenus dans le domaine composite dans Data Quality Client.</span><span class="sxs-lookup"><span data-stu-id="ffe9f-106">You select the single domains contained in the composite domain, in the Data Quality Client.</span></span> <span data-ttu-id="ffe9f-107">Pour plus d’informations, consultez [Créer un domaine composite](../../../data-quality-services/create-a-composite-domain.md).</span><span class="sxs-lookup"><span data-stu-id="ffe9f-107">For more information, see [Create a Composite Domain](../../../data-quality-services/create-a-composite-domain.md).</span></span>  
  
 <span data-ttu-id="ffe9f-108">Lorsque vous avez une seule colonne de valeurs délimitées, vous devez mapper la colonne unique au domaine composite.</span><span class="sxs-lookup"><span data-stu-id="ffe9f-108">When you have a single column with delimited values, you must map the single column to the composite domain.</span></span> <span data-ttu-id="ffe9f-109">Les valeurs doivent apparaître dans le même ordre que celui dans lequel les domaines uniques apparaissent dans le domaine composite.</span><span class="sxs-lookup"><span data-stu-id="ffe9f-109">The values must appear in the same order as the single domains appear in the composite domain.</span></span> <span data-ttu-id="ffe9f-110">Le délimiteur de la source de données doit correspondre à celui utilisé pour analyser les valeurs du domaine composite.</span><span class="sxs-lookup"><span data-stu-id="ffe9f-110">The delimiter in the data source must match the delimiter that is used to parse the composite domain values.</span></span> <span data-ttu-id="ffe9f-111">Sélectionnez le délimiteur du domaine composite et définissez d'autres propriétés dans Data Quality Client.</span><span class="sxs-lookup"><span data-stu-id="ffe9f-111">You select the delimiter for the composite domain, as well as set other properties, in the Data Quality Client.</span></span> <span data-ttu-id="ffe9f-112">Pour plus d’informations, consultez [Créer un domaine composite](../../../data-quality-services/create-a-composite-domain.md).</span><span class="sxs-lookup"><span data-stu-id="ffe9f-112">For more information, see [Create a Composite Domain](../../../data-quality-services/create-a-composite-domain.md).</span></span>  
  
### <a name="to-map-multiple-columns-to-a-composite-domain"></a><span data-ttu-id="ffe9f-113">Pour mapper plusieurs colonnes à un domaine composite</span><span class="sxs-lookup"><span data-stu-id="ffe9f-113">To map multiple columns to a composite domain</span></span>  
  
1.  <span data-ttu-id="ffe9f-114">Cliquez avec le bouton droit sur la transformation de nettoyage DQS, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="ffe9f-114">Right-click the DQS Cleansing transformation, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="ffe9f-115">Sous l’onglet **Gestionnaire de connexions** , vérifiez que le domaine composite apparaît dans la liste des domaines disponibles.</span><span class="sxs-lookup"><span data-stu-id="ffe9f-115">On the **Connection Manager** tab, confirm that the composite domain appears in the list of available domains.</span></span>  
  
3.  <span data-ttu-id="ffe9f-116">Sous l’onglet **Mappage** , sélectionnez les colonnes dans la zone **Colonnes d’entrée disponibles** .</span><span class="sxs-lookup"><span data-stu-id="ffe9f-116">On the **Mapping** tab, select the columns in the **Available Input Columns** area.</span></span>  
  
4.  <span data-ttu-id="ffe9f-117">Pour chaque colonne figurant dans le champ **Colonne d’entrée** , sélectionnez un domaine unique dans le champ **Domaine** .</span><span class="sxs-lookup"><span data-stu-id="ffe9f-117">For each column listed in the **Input Column** field, select a single domain in the **Domain** field.</span></span> <span data-ttu-id="ffe9f-118">Sélectionnez uniquement des domaines uniques figurant dans le domaine composite.</span><span class="sxs-lookup"><span data-stu-id="ffe9f-118">Select only single domains that are in the composite domain.</span></span>  
  
5.  <span data-ttu-id="ffe9f-119">Si nécessaire, modifiez les noms qui s’affichent dans les champs **Alias source**, **Alias de sortie**et **Alias d’état** .</span><span class="sxs-lookup"><span data-stu-id="ffe9f-119">As needed, modify the names that appear in the **Source Alias**, **Output Alias**, and **Status Alias** fields.</span></span>  
  
6.  <span data-ttu-id="ffe9f-120">Si nécessaire, définissez des propriétés sous l’onglet **Avancé** . Pour plus d’informations sur les propriétés, consultez [Éditeur de transformation de nettoyage DQS (boîte de dialogue)](../../dqs-cleansing-transformation-editor-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="ffe9f-120">As needed, set properties on the **Advanced** tab. For more information about the properties, see [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span></span>  
  
### <a name="to-map-a-column-with-delimited-values-to-a-composite-domain"></a><span data-ttu-id="ffe9f-121">Pour mapper une colonne de valeurs délimitées à un domaine composite</span><span class="sxs-lookup"><span data-stu-id="ffe9f-121">To map a column with delimited values to a composite domain</span></span>  
  
1.  <span data-ttu-id="ffe9f-122">Cliquez avec le bouton droit sur la transformation de nettoyage DQS, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="ffe9f-122">Right-click the DQS Cleansing transformation, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="ffe9f-123">Sous l’onglet **Gestionnaire de connexions** , vérifiez que le domaine composite apparaît dans la liste des domaines disponibles.</span><span class="sxs-lookup"><span data-stu-id="ffe9f-123">On the **Connection Manager** tab, confirm that the composite domain appears in the list of available domains.</span></span>  
  
3.  <span data-ttu-id="ffe9f-124">Sous l’onglet **Mappage** , sélectionnez la colonne dans la zone **Colonnes d’entrée disponibles** .</span><span class="sxs-lookup"><span data-stu-id="ffe9f-124">On the **Mapping** tab, select the column in the **Available Input Columns** area.</span></span>  
  
4.  <span data-ttu-id="ffe9f-125">Pour la colonne figurant dans le champ **Colonne d’entrée** , sélectionnez le domaine composite dans le champ **Domaine** .</span><span class="sxs-lookup"><span data-stu-id="ffe9f-125">For the column listed in the **Input Column** field, select the composite domain in the **Domain** field.</span></span>  
  
5.  <span data-ttu-id="ffe9f-126">Si nécessaire, modifiez les noms qui s’affichent dans les champs **Alias source**, **Alias de sortie**et **Alias d’état** .</span><span class="sxs-lookup"><span data-stu-id="ffe9f-126">As needed, modify the names that appear in the **Source Alias**, **Output Alias**, and **Status Alias** fields.</span></span>  
  
6.  <span data-ttu-id="ffe9f-127">Si nécessaire, définissez des propriétés sous l’onglet **Avancé** . Pour plus d’informations sur les propriétés, consultez [Éditeur de transformation de nettoyage DQS (boîte de dialogue)](../../dqs-cleansing-transformation-editor-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="ffe9f-127">As needed, set properties on the **Advanced** tab. For more information about the properties, see [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffe9f-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ffe9f-128">See Also</span></span>  
 [<span data-ttu-id="ffe9f-129">Transformation de nettoyage DQS</span><span class="sxs-lookup"><span data-stu-id="ffe9f-129">DQS Cleansing Transformation</span></span>](dqs-cleansing-transformation.md)  
  
  
