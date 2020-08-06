---
title: Éditeur de source CDC (page colonnes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsource.columns.f1
ms.assetid: bcf3030e-98d8-4445-967c-33c3f8ecb4fc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aa30defb5e6873ea05e8e41c733477cf50d0dc4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613583"
---
# <a name="cdc-source-editor-columns-page"></a><span data-ttu-id="3b440-102">Éditeur de source CDC (page Colonnes)</span><span class="sxs-lookup"><span data-stu-id="3b440-102">CDC Source Editor (Columns Page)</span></span>
  <span data-ttu-id="3b440-103">Utilisez la page **Colonnes** de la boîte de dialogue **Éditeur de source CDC** pour mapper une colonne de sortie à chaque colonne externe (source).</span><span class="sxs-lookup"><span data-stu-id="3b440-103">Use the **Columns** page of the **CDC Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="3b440-104">Pour en savoir plus sur la source CDC, consultez [CDC Source](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="3b440-104">To learn more about the CDC source, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="3b440-105">Liste des tâches</span><span class="sxs-lookup"><span data-stu-id="3b440-105">Task List</span></span>  
 <span data-ttu-id="3b440-106">**Pour ouvrir l'Éditeur de source CDC (page Colonnes)**</span><span class="sxs-lookup"><span data-stu-id="3b440-106">**To open the CDC Source Editor Columns Page**</span></span>  
  
1.  <span data-ttu-id="3b440-107">Dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], ouvrez le package [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] qui possède la source CDC.</span><span class="sxs-lookup"><span data-stu-id="3b440-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the CDC source.</span></span>  
  
2.  <span data-ttu-id="3b440-108">Sous l’onglet **Flux de données** , double-cliquez sur la source CDC.</span><span class="sxs-lookup"><span data-stu-id="3b440-108">On the **Data Flow** tab, double-click the CDC source.</span></span>  
  
3.  <span data-ttu-id="3b440-109">Dans l' **Éditeur de source CDC**, cliquez sur **Colonnes**.</span><span class="sxs-lookup"><span data-stu-id="3b440-109">In the **CDC Source Editor**, click **Columns**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3b440-110">Options</span><span class="sxs-lookup"><span data-stu-id="3b440-110">Options</span></span>  
 <span data-ttu-id="3b440-111">**Colonnes externes disponibles**</span><span class="sxs-lookup"><span data-stu-id="3b440-111">**Available External Columns**</span></span>  
 <span data-ttu-id="3b440-112">Liste des colonnes externes disponibles dans la source de données.</span><span class="sxs-lookup"><span data-stu-id="3b440-112">A list of available external columns in the data source.</span></span> <span data-ttu-id="3b440-113">Vous ne pouvez pas ajouter ou supprimer des colonnes à l'aide de cette table.</span><span class="sxs-lookup"><span data-stu-id="3b440-113">You cannot use this table to add or delete columns.</span></span> <span data-ttu-id="3b440-114">Sélectionnez les colonnes à utiliser dans la source.</span><span class="sxs-lookup"><span data-stu-id="3b440-114">Select the columns to use in the source.</span></span> <span data-ttu-id="3b440-115">Les colonnes sélectionnées sont ajoutées à la liste **Colonne externe** dans l'ordre de leur sélection.</span><span class="sxs-lookup"><span data-stu-id="3b440-115">The selected columns are added to the **External Column** list in the order they are selected.</span></span>  
  
 <span data-ttu-id="3b440-116">**Colonne externe**</span><span class="sxs-lookup"><span data-stu-id="3b440-116">**External Column**</span></span>  
 <span data-ttu-id="3b440-117">Vue des colonnes externes (sources) selon l'ordre dans lequel vous les visualisez lorsque vous configurez des composants qui consomment des données à partir de la source CDC.</span><span class="sxs-lookup"><span data-stu-id="3b440-117">A view of the external (source) columns in the order that you see them when configuring components that consume data from the CDC source.</span></span> <span data-ttu-id="3b440-118">Vous pouvez modifier cet ordre en supprimant d'abord les colonnes sélectionnées dans la liste **Colonnes externes disponibles** , puis en choisissant des colonnes externes dans la liste selon un ordre différent.</span><span class="sxs-lookup"><span data-stu-id="3b440-118">To change this order, first clear the selected columns in the **Available External Columns** list, and then select external columns from the list in a different order.</span></span> <span data-ttu-id="3b440-119">Les colonnes sélectionnées sont ajoutées à la liste **Colonne externe** dans l'ordre de leur sélection.</span><span class="sxs-lookup"><span data-stu-id="3b440-119">The selected columns are added to the **External Column** list in the order you select them.</span></span>  
  
 <span data-ttu-id="3b440-120">**Colonne de sortie**</span><span class="sxs-lookup"><span data-stu-id="3b440-120">**Output Column**</span></span>  
 <span data-ttu-id="3b440-121">Spécifiez un nom unique pour chaque colonne de sortie.</span><span class="sxs-lookup"><span data-stu-id="3b440-121">Enter a unique name for each output column.</span></span> <span data-ttu-id="3b440-122">Le nom par défaut est celui de la colonne externe (source) sélectionnée ; toutefois, vous pouvez choisir n'importe quel nom unique et descriptif.</span><span class="sxs-lookup"><span data-stu-id="3b440-122">The default is the name of the selected external (source) column, however you can choose any unique, descriptive name.</span></span> <span data-ttu-id="3b440-123">Le nom entré est affiché dans le concepteur SSIS.</span><span class="sxs-lookup"><span data-stu-id="3b440-123">The name entered is displayed in the SSIS Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b440-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3b440-124">See Also</span></span>  
 <span data-ttu-id="3b440-125">[Éditeur de source CDC &#40;page Gestionnaire de connexions&#41;](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="3b440-125">[CDC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="3b440-126">Éditeur de source CDC &#40;page Sortie d’erreur&#41;</span><span class="sxs-lookup"><span data-stu-id="3b440-126">CDC Source Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/cdc-source-editor-error-output-page.md)  
  
  
