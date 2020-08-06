---
title: Éditeur de destination SAP BW (page Mappages) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: dfa1f1d6-6b64-4331-bdc5-eaa8b7aa41a1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7c4c2803be3e2649f7425a2974dae8ac0a80fae7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695900"
---
# <a name="sap-bw-destination-editor-mappings-page"></a><span data-ttu-id="21187-102">Éditeur de destination SAP BW (page Mappages)</span><span class="sxs-lookup"><span data-stu-id="21187-102">SAP BW Destination Editor (Mappings Page)</span></span>
  <span data-ttu-id="21187-103">La page **Mappages** de **l’Éditeur de destination SAP BW** vous permet de mapper les colonnes d’entrée aux colonnes de destination.</span><span class="sxs-lookup"><span data-stu-id="21187-103">Use the **Mappings** page of the **SAP BW Destination Editor** to map input columns to destination columns.</span></span>  
  
 <span data-ttu-id="21187-104">Pour en savoir plus sur la destination SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 pour SAP BW, consultez [Destination SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="21187-104">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="21187-105">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="21187-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="21187-106">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="21187-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="21187-107">**Pour ouvrir la page Mappages**</span><span class="sxs-lookup"><span data-stu-id="21187-107">**To open the Mappings page**</span></span>  
  
1.  <span data-ttu-id="21187-108">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui contient la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="21187-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="21187-109">Sous l’onglet **Flux de données** , double-cliquez sur la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="21187-109">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="21187-110">Dans **l’Éditeur de destination SAP BW**, cliquez sur **Mappages** pour ouvrir la page **Mappages** de l’éditeur.</span><span class="sxs-lookup"><span data-stu-id="21187-110">In the **SAP BW Destination Editor**, click **Mappings** to open the **Mappings** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="21187-111">Options</span><span class="sxs-lookup"><span data-stu-id="21187-111">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="21187-112">Si vous ne connaissez pas toutes les valeurs requises pour configurer la destination, adressez-vous à votre administrateur SAP.</span><span class="sxs-lookup"><span data-stu-id="21187-112">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="21187-113">La page **Mappages** de **l’Éditeur de destination SAP BW** contient deux sections :</span><span class="sxs-lookup"><span data-stu-id="21187-113">The **Mappings** page of the **SAP BW Destination Editor consists** of two sections:</span></span>  
  
-   <span data-ttu-id="21187-114">La section supérieure montre les colonnes d'entrée et de destination disponibles et vous permet de créer des mappages entre ces deux types de colonnes.</span><span class="sxs-lookup"><span data-stu-id="21187-114">The upper section shows the available input and destination columns and lets you create mappings between these two types of columns.</span></span>  
  
-   <span data-ttu-id="21187-115">La section inférieure est un tableau qui indique quelles colonnes d'entrée ont été mappées à quelles colonnes de sortie.</span><span class="sxs-lookup"><span data-stu-id="21187-115">The lower section is a table that lists which input columns have been mapped to which output columns.</span></span>  
  
### <a name="upper-section-options"></a><span data-ttu-id="21187-116">Options de la section supérieure</span><span class="sxs-lookup"><span data-stu-id="21187-116">Upper Section Options</span></span>  
 <span data-ttu-id="21187-117">La section supérieure comporte les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="21187-117">The upper section has the following options:</span></span>  
  
 <span data-ttu-id="21187-118">**Colonnes d'entrée disponibles**</span><span class="sxs-lookup"><span data-stu-id="21187-118">**Available Input Columns**</span></span>  
 <span data-ttu-id="21187-119">Affichez la liste des colonnes d'entrée disponibles.</span><span class="sxs-lookup"><span data-stu-id="21187-119">View the list of available input columns.</span></span>  
  
 <span data-ttu-id="21187-120">Pour mapper une colonne d’entrée à une colonne de destination, faites glisser une colonne de la liste **Colonnes d’entrée disponibles** et déposez-la sur une colonne de la liste **Colonnes de destination disponibles** .</span><span class="sxs-lookup"><span data-stu-id="21187-120">To map an input column to a destination column, drag a column from the **Available Input Columns** list and drop that column onto a column in the **Available Destination Columns** list.</span></span>  
  
 <span data-ttu-id="21187-121">**Colonnes de destination disponibles**</span><span class="sxs-lookup"><span data-stu-id="21187-121">**Available Destination Columns**</span></span>  
 <span data-ttu-id="21187-122">Affichez la liste des colonnes de destination disponibles.</span><span class="sxs-lookup"><span data-stu-id="21187-122">View the list of available destination columns.</span></span>  
  
 <span data-ttu-id="21187-123">Pour mapper une colonne d’entrée à une colonne de destination, faites glisser une colonne de la liste **Colonnes d’entrée disponibles** et déposez-la sur une colonne de la liste **Colonnes de destination disponibles** .</span><span class="sxs-lookup"><span data-stu-id="21187-123">To map an input column to destination column, drag a column from the **Available Input Columns** list and drop that column onto a column in the **Available Destination Columns** list.</span></span>  
  
 <span data-ttu-id="21187-124">La section supérieure comporte également un menu contextuel que vous pouvez ouvrir en cliquant avec le bouton droit sur l'arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="21187-124">The upper section also has a context menu that you can open by right-clicking on the background.</span></span> <span data-ttu-id="21187-125">Ce menu contextuel contient les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="21187-125">This context menu contains the following options:</span></span>  
  
-   <span data-ttu-id="21187-126">**Sélectionner tous les mappages**</span><span class="sxs-lookup"><span data-stu-id="21187-126">**Select All Mappings**</span></span>  
  
-   <span data-ttu-id="21187-127">**Supprimer les mappages sélectionnés**</span><span class="sxs-lookup"><span data-stu-id="21187-127">**Delete Selected Mappings**</span></span>  
  
-   <span data-ttu-id="21187-128">**Mapper les éléments par noms correspondants**</span><span class="sxs-lookup"><span data-stu-id="21187-128">**Map Items by Matching Names**</span></span>  
  
### <a name="lower-section-columns"></a><span data-ttu-id="21187-129">Colonnes de la section inférieure</span><span class="sxs-lookup"><span data-stu-id="21187-129">Lower Section Columns</span></span>  
 <span data-ttu-id="21187-130">La section inférieure est un tableau des mappages. Elle comporte les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="21187-130">The lower section is a table of the mappings, and has the following columns:</span></span>  
  
 <span data-ttu-id="21187-131">**Colonne d'entrée**</span><span class="sxs-lookup"><span data-stu-id="21187-131">**Input Column**</span></span>  
 <span data-ttu-id="21187-132">Affichez les colonnes d'entrée que vous avez sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="21187-132">View the input columns that you have selected.</span></span>  
  
 <span data-ttu-id="21187-133">Pour mapper une colonne d'entrée différente à la même colonne de destination, sélectionnez une colonne d'entrée différente dans la liste.</span><span class="sxs-lookup"><span data-stu-id="21187-133">To map a different input column to the same destination column, select a different input column in the list.</span></span> <span data-ttu-id="21187-134">Pour supprimer un mappage, sélectionnez **\<ignore>** afin d’exclure la colonne d’entrée de la sortie.</span><span class="sxs-lookup"><span data-stu-id="21187-134">To remove a mapping, select **\<ignore>** to exclude the input column from the output.</span></span>  
  
 <span data-ttu-id="21187-135">**Colonne de destination**</span><span class="sxs-lookup"><span data-stu-id="21187-135">**Destination Column**</span></span>  
 <span data-ttu-id="21187-136">Affichez chaque colonne de destination disponible, qu'elle soit mappée ou non.</span><span class="sxs-lookup"><span data-stu-id="21187-136">View each available destination column, regardless of whether that column is mapped or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21187-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="21187-137">See Also</span></span>  
 <span data-ttu-id="21187-138">[Éditeur de destination SAP BW &#40;page Gestionnaire de connexions&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="21187-138">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="21187-139">[Éditeur de destination SAP BW &#40;page Sortie d’erreur&#41;](sap-bw-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="21187-139">[SAP BW Destination Editor &#40;Error Output Page&#41;](sap-bw-destination-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="21187-140">[Éditeur de destination SAP BW &#40;page Avancé&#41;](sap-bw-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="21187-140">[SAP BW Destination Editor &#40;Advanced Page&#41;](sap-bw-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="21187-141">Aide (F1) sur Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="21187-141">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
