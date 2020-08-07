---
title: Éditeur de source ODBC (page colonnes) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.columns.f1
ms.assetid: 565984eb-8318-4be7-bebc-262209cf5065
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7a11ab6a86978366d07fbe63362f1702310b5d89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703191"
---
# <a name="odbc-source-editor-columns-page"></a><span data-ttu-id="8eaff-102">Éditeur de source ODBC (page Colonnes)</span><span class="sxs-lookup"><span data-stu-id="8eaff-102">ODBC Source Editor (Columns Page)</span></span>
  <span data-ttu-id="8eaff-103">Utilisez la page **Colonnes** de la boîte de dialogue **Éditeur de source ODBC** pour mapper une colonne de sortie à chaque colonne externe (source).</span><span class="sxs-lookup"><span data-stu-id="8eaff-103">Use the **Columns** page of the **ODBC Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="8eaff-104">Pour en savoir plus sur la source ODBC, consultez [ODBC Source](data-flow/odbc-source.md).</span><span class="sxs-lookup"><span data-stu-id="8eaff-104">To learn more about the ODBC source, see [ODBC Source](data-flow/odbc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="8eaff-105">Liste des tâches</span><span class="sxs-lookup"><span data-stu-id="8eaff-105">Task List</span></span>  
 <span data-ttu-id="8eaff-106">**Pour ouvrir l'Éditeur de source ODBC (page Colonnes)**</span><span class="sxs-lookup"><span data-stu-id="8eaff-106">**To open the ODBC Source Editor Columns Page**</span></span>  
  
1.  <span data-ttu-id="8eaff-107">Dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], ouvrez le package [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] qui possède la source ODBC.</span><span class="sxs-lookup"><span data-stu-id="8eaff-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC source.</span></span>  
  
2.  <span data-ttu-id="8eaff-108">Sous l’onglet **Flux de données** , double-cliquez sur la source ODBC.</span><span class="sxs-lookup"><span data-stu-id="8eaff-108">On the **Data Flow** tab, double-click the ODBC source.</span></span>  
  
3.  <span data-ttu-id="8eaff-109">Dans l' **Éditeur de source ODBC**, cliquez sur **Colonnes**.</span><span class="sxs-lookup"><span data-stu-id="8eaff-109">In the **ODBC Source Editor**, click **Columns**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8eaff-110">Options</span><span class="sxs-lookup"><span data-stu-id="8eaff-110">Options</span></span>  
  
### <a name="available-external-columns"></a><span data-ttu-id="8eaff-111">Colonnes externes disponibles</span><span class="sxs-lookup"><span data-stu-id="8eaff-111">Available External Columns</span></span>  
 <span data-ttu-id="8eaff-112">Liste des colonnes externes disponibles dans la source de données.</span><span class="sxs-lookup"><span data-stu-id="8eaff-112">A list of available external columns in the data source.</span></span> <span data-ttu-id="8eaff-113">Vous ne pouvez pas ajouter ou supprimer des colonnes à l'aide de cette table.</span><span class="sxs-lookup"><span data-stu-id="8eaff-113">You cannot use this table to add or delete columns.</span></span> <span data-ttu-id="8eaff-114">Sélectionnez les colonnes à utiliser dans la source.</span><span class="sxs-lookup"><span data-stu-id="8eaff-114">Select the columns to use from the source.</span></span> <span data-ttu-id="8eaff-115">Les colonnes sélectionnées sont ajoutées à la liste **Colonne externe** dans l'ordre de leur sélection.</span><span class="sxs-lookup"><span data-stu-id="8eaff-115">The selected columns are added to the **External Column** list in the order they are selected.</span></span>  
  
 <span data-ttu-id="8eaff-116">Activez la case à cocher **Sélectionner tout** pour sélectionner toutes les colonnes.</span><span class="sxs-lookup"><span data-stu-id="8eaff-116">Select the **Select All** check box to select all of the columns.</span></span>  
  
### <a name="external-column"></a><span data-ttu-id="8eaff-117">Colonne externe</span><span class="sxs-lookup"><span data-stu-id="8eaff-117">External Column</span></span>  
 <span data-ttu-id="8eaff-118">Vue des colonnes externes (sources) selon l'ordre dans lequel vous les visualisez lorsque vous configurez des composants qui consomment des données à partir de la source ODBC.</span><span class="sxs-lookup"><span data-stu-id="8eaff-118">A view of the external (source) columns in the order that you see them when configuring components that consume data from the ODBC source.</span></span>  
  
### <a name="output-column"></a><span data-ttu-id="8eaff-119">Colonne de sortie</span><span class="sxs-lookup"><span data-stu-id="8eaff-119">Output Column</span></span>  
 <span data-ttu-id="8eaff-120">Spécifiez un nom unique pour chaque colonne de sortie.</span><span class="sxs-lookup"><span data-stu-id="8eaff-120">Enter a unique name for each output column.</span></span> <span data-ttu-id="8eaff-121">Le nom par défaut est celui de la colonne externe (source) sélectionnée ; vous pouvez néanmoins choisir n'importe quel nom unique et significatif.</span><span class="sxs-lookup"><span data-stu-id="8eaff-121">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="8eaff-122">Le nom entré est affiché dans le concepteur SSIS.</span><span class="sxs-lookup"><span data-stu-id="8eaff-122">The name entered is displayed in the SSIS Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eaff-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8eaff-123">See Also</span></span>  
 <span data-ttu-id="8eaff-124">[Éditeur de source ODBC &#40;page Gestionnaire de connexions&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="8eaff-124">[ODBC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="8eaff-125">Éditeur de source ODBC &#40;page Sortie d’erreur&#41;</span><span class="sxs-lookup"><span data-stu-id="8eaff-125">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/odbc-source-editor-error-output-page.md)  
  
  
