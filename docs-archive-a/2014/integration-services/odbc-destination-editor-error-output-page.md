---
title: Éditeur de destination ODBC (page sortie d’erreur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcdest.errorhandling.f1
ms.assetid: 0a743f8d-2a51-4296-9976-8104f5ca22d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 475a2e00d67b221ddf05fdd273317fbab5248cd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703195"
---
# <a name="odbc-destination-editor-error-output-page"></a><span data-ttu-id="d5c6e-102">Éditeur de destination ODBC (page Sortie d'erreur)</span><span class="sxs-lookup"><span data-stu-id="d5c6e-102">ODBC Destination Editor (Error Output Page)</span></span>
  <span data-ttu-id="d5c6e-103">Utilisez la page **Sortie d'erreur** de la boîte de dialogue **Éditeur de destination ODBC** pour sélectionner les options de gestion des erreurs.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-103">Use the **Error Output** page of the **ODBC Destination Editor** dialog box to select error handling options.</span></span>  
  
 <span data-ttu-id="d5c6e-104">Pour en savoir plus sur la destination ODBC, consultez [ODBC Destination](data-flow/odbc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="d5c6e-104">To learn more about the ODBC destination, see [ODBC Destination](data-flow/odbc-destination.md).</span></span>  
  
 <span data-ttu-id="d5c6e-105">**Pour ouvrir l'Éditeur de destination ODBC (page Sortie d'erreur)**</span><span class="sxs-lookup"><span data-stu-id="d5c6e-105">**To open the ODBC Destination Editor Error Output Page**</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="d5c6e-106">Liste des tâches</span><span class="sxs-lookup"><span data-stu-id="d5c6e-106">Task List</span></span>  
  
-   <span data-ttu-id="d5c6e-107">Dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], ouvrez le package [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] qui possède la destination ODBC.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC destination.</span></span>  
  
-   <span data-ttu-id="d5c6e-108">Sous l’onglet **Flux de données** , double-cliquez sur la destination ODBC.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-108">On the **Data Flow** tab, double-click the ODBC destination.</span></span>  
  
-   <span data-ttu-id="d5c6e-109">Dans l' **Éditeur de destination ODBC**, cliquez sur **Sortie d'erreur**.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-109">In the **ODBC Destination Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d5c6e-110">Options</span><span class="sxs-lookup"><span data-stu-id="d5c6e-110">Options</span></span>  
  
### <a name="inputoutput"></a><span data-ttu-id="d5c6e-111">Entrée/sortie</span><span class="sxs-lookup"><span data-stu-id="d5c6e-111">Input/Output</span></span>  
 <span data-ttu-id="d5c6e-112">Affichez le nom de la source de données.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-112">View the name of the data source.</span></span>  
  
### <a name="column"></a><span data-ttu-id="d5c6e-113">Colonne</span><span class="sxs-lookup"><span data-stu-id="d5c6e-113">Column</span></span>  
 <span data-ttu-id="d5c6e-114">Non utilisé.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-114">Not used.</span></span>  
  
### <a name="error"></a><span data-ttu-id="d5c6e-115">Error</span><span class="sxs-lookup"><span data-stu-id="d5c6e-115">Error</span></span>  
 <span data-ttu-id="d5c6e-116">Sélectionnez la façon dont la destination ODBC doit gérer les erreurs dans un flux : ignorer l'échec, rediriger la ligne ou faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-116">Select how the ODBC destination should handle errors in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="truncation"></a><span data-ttu-id="d5c6e-117">Troncation</span><span class="sxs-lookup"><span data-stu-id="d5c6e-117">Truncation</span></span>  
 <span data-ttu-id="d5c6e-118">Sélectionnez la façon dont la destination ODBC doit gérer la troncation dans un flux : ignorer l'échec, rediriger la ligne ou faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-118">Select how the ODBC destination should handle truncation in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="description"></a><span data-ttu-id="d5c6e-119">Description</span><span class="sxs-lookup"><span data-stu-id="d5c6e-119">Description</span></span>  
 <span data-ttu-id="d5c6e-120">Affichez la description d'une erreur.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-120">View a description of the error.</span></span>  
  
### <a name="set-this-value-to-selected-cells"></a><span data-ttu-id="d5c6e-121">Définir cette valeur sur les cellules sélectionnées</span><span class="sxs-lookup"><span data-stu-id="d5c6e-121">Set this value to selected cells</span></span>  
 <span data-ttu-id="d5c6e-122">Sélectionnez la façon dont la destination ODBC gère l'ensemble des cellules sélectionnées lorsqu'une erreur ou une troncation se produit : ignorer l'échec, rediriger la ligne ou faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-122">Select how the ODBC destination handles all selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="apply"></a><span data-ttu-id="d5c6e-123">Appliquer</span><span class="sxs-lookup"><span data-stu-id="d5c6e-123">Apply</span></span>  
 <span data-ttu-id="d5c6e-124">Appliquez les options de gestion des erreurs aux cellules sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-124">Apply the error handling options to the selected cells.</span></span>  
  
## <a name="error-handling-options"></a><span data-ttu-id="d5c6e-125">Options de gestion des erreurs</span><span class="sxs-lookup"><span data-stu-id="d5c6e-125">Error Handling Options</span></span>  
 <span data-ttu-id="d5c6e-126">Vous pouvez utiliser les options suivantes pour configurer la façon dont la destination ODBC gère les erreurs et les troncations.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-126">You use the following options to configure how the ODBC destination handles errors and truncations.</span></span>  
  
### <a name="fail-component"></a><span data-ttu-id="d5c6e-127">Composant défaillant</span><span class="sxs-lookup"><span data-stu-id="d5c6e-127">Fail Component</span></span>  
 <span data-ttu-id="d5c6e-128">La tâche de flux de données échoue lorsqu'une erreur ou une troncation a lieu.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-128">The Data Flow task fails when an error or a truncation occurs.</span></span> <span data-ttu-id="d5c6e-129">Il s'agit du comportement par défaut.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-129">This is the default behavior.</span></span>  
  
### <a name="ignore-failure"></a><span data-ttu-id="d5c6e-130">Ignorer l'échec</span><span class="sxs-lookup"><span data-stu-id="d5c6e-130">Ignore Failure</span></span>  
 <span data-ttu-id="d5c6e-131">L'erreur ou la troncation est ignorée.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-131">The error or the truncation is ignored.</span></span>  
  
### <a name="redirect-flow"></a><span data-ttu-id="d5c6e-132">Rediriger le flux</span><span class="sxs-lookup"><span data-stu-id="d5c6e-132">Redirect Flow</span></span>  
 <span data-ttu-id="d5c6e-133">La ligne qui provoque l'erreur ou la troncation est dirigée vers la sortie d'erreur de la destination ODBC.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-133">The row that is causing the error or the truncation is directed to the error output of the ODBC destination.</span></span> <span data-ttu-id="d5c6e-134">Pour plus d'informations, consultez Destination ODBC.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-134">For more information, see ODBC Destination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5c6e-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d5c6e-135">See Also</span></span>  
 <span data-ttu-id="d5c6e-136">[Éditeur de destination ODBC &#40;page Gestionnaire de connexions&#41;](../../2014/integration-services/odbc-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="d5c6e-136">[ODBC Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/odbc-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="d5c6e-137">Éditeur de destination ODBC &#40;page Mappages&#41;</span><span class="sxs-lookup"><span data-stu-id="d5c6e-137">ODBC Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/odbc-destination-editor-mappings-page.md)  
  
  
