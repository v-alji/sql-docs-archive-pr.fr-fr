---
title: Ajouter une jauge à un rapport (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 45da4fef-2b02-40e1-977c-f8f80d87155e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7125080d95e9c7b882df8d715cce5c6cf8aa6344
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706247"
---
# <a name="add-a-gauge-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="c43a7-102">Ajouter une jauge à un rapport (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="c43a7-102">Add a Gauge to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c43a7-103">Lorsque vous souhaitez synthétiser des données dans un format visuel, vous pouvez utiliser une région de données de type jauge.</span><span class="sxs-lookup"><span data-stu-id="c43a7-103">When you want to summarize data in a visual format, you can use a Gauge data region.</span></span> <span data-ttu-id="c43a7-104">Après avoir ajouté une région de données de jauge à l'aire de conception, vous pouvez faire glisser les champs de dataset du rapport vers un volet des données sur la jauge.</span><span class="sxs-lookup"><span data-stu-id="c43a7-104">After you add a Gauge data region to the design surface, you can drag report dataset fields to a data pane on the gauge.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-gauge-to-your-report"></a><span data-ttu-id="c43a7-105">Pour ajouter une jauge à votre rapport</span><span class="sxs-lookup"><span data-stu-id="c43a7-105">To add a gauge to your report</span></span>  
  
1.  <span data-ttu-id="c43a7-106">Créez un rapport ou ouvrez-en un qui existe déjà.</span><span class="sxs-lookup"><span data-stu-id="c43a7-106">Create a report or open an existing report.</span></span>  
  
2.  <span data-ttu-id="c43a7-107">Sous l'onglet Insérer, double-cliquez sur Jauge.</span><span class="sxs-lookup"><span data-stu-id="c43a7-107">On the Insert tab, double-click Gauge.</span></span> <span data-ttu-id="c43a7-108">La boîte de dialogue **Sélectionner le type de jauge** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="c43a7-108">The **Select Gauge Type** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="c43a7-109">Sélectionnez le type de jauge que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="c43a7-109">Select the type of gauge you want to add.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="c43a7-110">Contrairement aux graphiques, il n'existe que deux types de jauge : linéaire et radial.</span><span class="sxs-lookup"><span data-stu-id="c43a7-110">Unlike Chart, Gauge has only two types: linear and radial.</span></span> <span data-ttu-id="c43a7-111">Les jauges disponibles dans la boîte de dialogue **Sélectionner le type de jauge** sont des modèles correspondant à ces deux types de jauges.</span><span class="sxs-lookup"><span data-stu-id="c43a7-111">The available gauges in the **Select a Gauge Type** dialog box are templates for these two types of gauges.</span></span> <span data-ttu-id="c43a7-112">C'est ce qui explique que vous ne pouvez pas modifier le type de jauge une fois que vous avez ajouté une jauge à votre rapport.</span><span class="sxs-lookup"><span data-stu-id="c43a7-112">For this reason, you cannot change the gauge type after you add the gauge to your report.</span></span> <span data-ttu-id="c43a7-113">Vous devez supprimer et rajouter une jauge pour en modifier le type.</span><span class="sxs-lookup"><span data-stu-id="c43a7-113">You must delete and re-add a gauge to change its type.</span></span>  
  
     <span data-ttu-id="c43a7-114">Si le rapport ne possède pas de source de données ni de dataset, la boîte de dialogue **Propriétés de la source de données** s'ouvre et vous aide à en créer.</span><span class="sxs-lookup"><span data-stu-id="c43a7-114">If the report has no data source and dataset the **Data Source Properties** dialog box opens and takes you through the steps to create both.</span></span> <span data-ttu-id="c43a7-115">Pour plus d’informations, consultez [Ajouter et vérifier une connexion de données ou une source de données &#40;générateur de rapports et des&#41;SSRS ](../report-data/add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c43a7-115">For more information see, [Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;](../report-data/add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span></span>  
  
     <span data-ttu-id="c43a7-116">Si le rapport est associé à une source de données mais à aucun dataset, la boîte de dialogue **Propriétés du dataset** s'ouvre et vous aide à en créer un.</span><span class="sxs-lookup"><span data-stu-id="c43a7-116">If the report has a data source, but no dataset the **Dataset Properties** dialog box opens and takes you through the steps to create one.</span></span> <span data-ttu-id="c43a7-117">Pour plus d’informations, consultez [Créer un dataset partagé ou incorporé &#40;Générateur de rapports et SSRS&#41;](../report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c43a7-117">For more information, see [Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;](../report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md).</span></span>  
  
4.  <span data-ttu-id="c43a7-118">Cliquez sur la jauge pour afficher le volet des données.</span><span class="sxs-lookup"><span data-stu-id="c43a7-118">Click the gauge to display the data pane.</span></span> <span data-ttu-id="c43a7-119">Par défaut, une jauge dispose d'un pointeur qui correspond à une valeur.</span><span class="sxs-lookup"><span data-stu-id="c43a7-119">By default, a gauge has one pointer corresponding to one value.</span></span> <span data-ttu-id="c43a7-120">Vous pouvez ajouter des pointeurs supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="c43a7-120">You can add additional pointers.</span></span>  
  
5.  <span data-ttu-id="c43a7-121">Ajoutez un champ du dataset à la zone de dépôt de champ de données.</span><span class="sxs-lookup"><span data-stu-id="c43a7-121">Add one field from the dataset to the data field drop-zone.</span></span> <span data-ttu-id="c43a7-122">Vous pouvez ajouter un champ uniquement.</span><span class="sxs-lookup"><span data-stu-id="c43a7-122">You can add only one field.</span></span> <span data-ttu-id="c43a7-123">Si vous souhaitez afficher plusieurs champs, vous devez ajouter des pointeurs supplémentaires, un pour chaque champ.</span><span class="sxs-lookup"><span data-stu-id="c43a7-123">If you want to display multiple fields, you must add additional pointers, one for each field.</span></span>  
  
     <span data-ttu-id="c43a7-124">Cliquez avec le bouton droit sur l’échelle de la jauge et sélectionnez **Propriétés de l’échelle**.</span><span class="sxs-lookup"><span data-stu-id="c43a7-124">Right-click the gauge scale, and select **Scale Properties**.</span></span> <span data-ttu-id="c43a7-125">Tapez la valeur **Minimum** et **Maximum** de l'échelle.</span><span class="sxs-lookup"><span data-stu-id="c43a7-125">Type a value for the **Minimum** and **Maximum** of the scale.</span></span> <span data-ttu-id="c43a7-126">Pour plus d’informations, consultez [Définir un minimum ou un maximum sur une jauge &#40;Générateur de rapports et SSRS&#41;](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c43a7-126">For more information, see [Set a Minimum or Maximum on a Gauge &#40;Report Builder and SSRS&#41;](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c43a7-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c43a7-127">See Also</span></span>  
 <span data-ttu-id="c43a7-128">[Régions de données imbriquées &#40;Générateur de rapports et SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c43a7-128">[Nested Data Regions &#40;Report Builder and SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c43a7-129">Jauges &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c43a7-129">Gauges &#40;Report Builder and SSRS&#41;</span></span>](gauges-report-builder-and-ssrs.md)  
  
  
