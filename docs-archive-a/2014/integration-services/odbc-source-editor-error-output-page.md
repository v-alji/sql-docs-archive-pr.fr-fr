---
title: Éditeur de source ODBC (page sortie d’erreur) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.errorhandling.f1
ms.assetid: b2f6866c-db07-4cb3-9f38-889f8d2b03e6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a8e169875a26efbe0a7f1ac3d06856b393266eb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703183"
---
# <a name="odbc-source-editor-error-output-page"></a><span data-ttu-id="86516-102">Éditeur de source ODBC (page Sortie d'erreur)</span><span class="sxs-lookup"><span data-stu-id="86516-102">ODBC Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="86516-103">Utilisez la page **Sortie d'erreur** de la boîte de dialogue **Éditeur de source ODBC** pour sélectionner les options de gestion des erreurs.</span><span class="sxs-lookup"><span data-stu-id="86516-103">Use the **Error Output** page of the **ODBC Source Editor** dialog box to select error handling options.</span></span>  
  
 <span data-ttu-id="86516-104">Pour en savoir plus sur la source ODBC, consultez [CDC Source](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="86516-104">To learn more about the ODBC source, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="86516-105">Liste des tâches</span><span class="sxs-lookup"><span data-stu-id="86516-105">Task List</span></span>  
 <span data-ttu-id="86516-106">**Pour ouvrir l'Éditeur de source ODBC (page Sortie d'erreur)**</span><span class="sxs-lookup"><span data-stu-id="86516-106">**To open the ODBC Source Editor Error Output Page**</span></span>  
  
-   <span data-ttu-id="86516-107">Dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], ouvrez le package [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] qui possède la source ODBC.</span><span class="sxs-lookup"><span data-stu-id="86516-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC source.</span></span>  
  
-   <span data-ttu-id="86516-108">Sous l’onglet **Flux de données** , double-cliquez sur la source ODBC.</span><span class="sxs-lookup"><span data-stu-id="86516-108">On the **Data Flow** tab, double-click the ODBC source.</span></span>  
  
-   <span data-ttu-id="86516-109">Dans l' **Éditeur de source ODBC**, cliquez sur **Sortie d'erreur**.</span><span class="sxs-lookup"><span data-stu-id="86516-109">In the **ODBC Source Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="86516-110">Options</span><span class="sxs-lookup"><span data-stu-id="86516-110">Options</span></span>  
  
### <a name="inputoutput"></a><span data-ttu-id="86516-111">Entrée/sortie</span><span class="sxs-lookup"><span data-stu-id="86516-111">Input/Output</span></span>  
 <span data-ttu-id="86516-112">Affichez le nom de la source de données.</span><span class="sxs-lookup"><span data-stu-id="86516-112">View the name of the data source.</span></span>  
  
### <a name="column"></a><span data-ttu-id="86516-113">Colonne</span><span class="sxs-lookup"><span data-stu-id="86516-113">Column</span></span>  
 <span data-ttu-id="86516-114">Non utilisé.</span><span class="sxs-lookup"><span data-stu-id="86516-114">Not used.</span></span>  
  
### <a name="error"></a><span data-ttu-id="86516-115">Error</span><span class="sxs-lookup"><span data-stu-id="86516-115">Error</span></span>  
 <span data-ttu-id="86516-116">Sélectionnez la façon dont la source ODBC doit gérer les erreurs dans un flux : ignorer l'échec, rediriger la ligne ou faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="86516-116">Select how the ODBC source should handle errors in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="truncation"></a><span data-ttu-id="86516-117">Troncation</span><span class="sxs-lookup"><span data-stu-id="86516-117">Truncation</span></span>  
 <span data-ttu-id="86516-118">Sélectionnez la façon dont la source ODBC doit gérer la troncation dans un flux : ignorer l'échec, rediriger la ligne ou faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="86516-118">Select how the ODBC source should handle truncation in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="description"></a><span data-ttu-id="86516-119">Description</span><span class="sxs-lookup"><span data-stu-id="86516-119">Description</span></span>  
 <span data-ttu-id="86516-120">Non utilisé.</span><span class="sxs-lookup"><span data-stu-id="86516-120">Not used.</span></span>  
  
### <a name="set-this-value-to-selected-cells"></a><span data-ttu-id="86516-121">Définir cette valeur sur les cellules sélectionnées</span><span class="sxs-lookup"><span data-stu-id="86516-121">Set this value to selected cells</span></span>  
 <span data-ttu-id="86516-122">Sélectionnez la façon dont la source ODBC gère l'ensemble des cellules sélectionnées lorsqu'une erreur ou une troncation se produit : ignorer l'échec, rediriger la ligne ou faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="86516-122">Select how the ODBC source handles all selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="apply"></a><span data-ttu-id="86516-123">Appliquer</span><span class="sxs-lookup"><span data-stu-id="86516-123">Apply</span></span>  
 <span data-ttu-id="86516-124">Appliquez les options de gestion des erreurs aux cellules sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="86516-124">Apply the error handling options to the selected cells.</span></span>  
  
## <a name="error-handling-options"></a><span data-ttu-id="86516-125">Options de gestion des erreurs</span><span class="sxs-lookup"><span data-stu-id="86516-125">Error Handling Options</span></span>  
 <span data-ttu-id="86516-126">Vous pouvez utiliser les options suivantes pour configurer la façon dont la source ODBC gère les erreurs et les troncations.</span><span class="sxs-lookup"><span data-stu-id="86516-126">You use the following options to configure how the ODBC source handles errors and truncations.</span></span>  
  
### <a name="fail-component"></a><span data-ttu-id="86516-127">Composant défaillant</span><span class="sxs-lookup"><span data-stu-id="86516-127">Fail Component</span></span>  
 <span data-ttu-id="86516-128">La tâche de flux de données échoue lorsqu'une erreur ou une troncation a lieu.</span><span class="sxs-lookup"><span data-stu-id="86516-128">The Data Flow task fails when an error or a truncation occurs.</span></span> <span data-ttu-id="86516-129">Il s'agit du comportement par défaut.</span><span class="sxs-lookup"><span data-stu-id="86516-129">This is the default behavior.</span></span>  
  
### <a name="ignore-failure"></a><span data-ttu-id="86516-130">Ignorer l'échec</span><span class="sxs-lookup"><span data-stu-id="86516-130">Ignore Failure</span></span>  
 <span data-ttu-id="86516-131">L'erreur ou la troncation est ignorée.</span><span class="sxs-lookup"><span data-stu-id="86516-131">The error or the truncation is ignored.</span></span>  
  
### <a name="redirect-flow"></a><span data-ttu-id="86516-132">Rediriger le flux</span><span class="sxs-lookup"><span data-stu-id="86516-132">Redirect Flow</span></span>  
 <span data-ttu-id="86516-133">La ligne qui provoque l'erreur ou la troncation est dirigée vers la sortie d'erreur de la source ODBC.</span><span class="sxs-lookup"><span data-stu-id="86516-133">The row that is causing the error or the truncation is directed to the error output of the ODBC source.</span></span> <span data-ttu-id="86516-134">Pour plus d'informations, consultez [ODBC Source](data-flow/odbc-source.md).</span><span class="sxs-lookup"><span data-stu-id="86516-134">For more information, see [ODBC Source](data-flow/odbc-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86516-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="86516-135">See Also</span></span>  
 <span data-ttu-id="86516-136">[Éditeur de source ODBC &#40;page Gestionnaire de connexions&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="86516-136">[ODBC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="86516-137">Éditeur de source ODBC &#40;page Colonnes&#41;</span><span class="sxs-lookup"><span data-stu-id="86516-137">ODBC Source Editor &#40;Columns Page&#41;</span></span>](../../2014/integration-services/odbc-source-editor-columns-page.md)  
  
  
