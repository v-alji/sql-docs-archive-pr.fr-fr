---
title: Éditeur de source CDC (page sortie d’erreur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsource.errorhandling.f1
ms.assetid: 8a4c2cb8-fd2f-4c45-824f-b93473a8981e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b39532304fddfa90fabe8cafe2a6caf5b1fb5c8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613582"
---
# <a name="cdc-source-editor-error-output-page"></a><span data-ttu-id="02859-102">Éditeur de source CDC (page Sortie d'erreur)</span><span class="sxs-lookup"><span data-stu-id="02859-102">CDC Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="02859-103">Utilisez la page **Sortie d'erreur** de la boîte de dialogue **Éditeur de source CDC** pour sélectionner les options de gestion des erreurs.</span><span class="sxs-lookup"><span data-stu-id="02859-103">Use the **Error Output** page of the **CDC Source Editor** dialog box to select error handling options.</span></span>  
  
 <span data-ttu-id="02859-104">Pour en savoir plus sur la source CDC, consultez [CDC Source](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="02859-104">To learn more about the CDC source, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="02859-105">Liste des tâches</span><span class="sxs-lookup"><span data-stu-id="02859-105">Task List</span></span>  
 <span data-ttu-id="02859-106">**Pour ouvrir l'Éditeur de source CDC (page Sortie d'erreur)**</span><span class="sxs-lookup"><span data-stu-id="02859-106">**To open the CDC Source Editor Error Output Page**</span></span>  
  
1.  <span data-ttu-id="02859-107">Dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], ouvrez le package [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] qui possède la source CDC.</span><span class="sxs-lookup"><span data-stu-id="02859-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the CDC source.</span></span>  
  
2.  <span data-ttu-id="02859-108">Sous l’onglet **Flux de données** , double-cliquez sur la source CDC.</span><span class="sxs-lookup"><span data-stu-id="02859-108">On the **Data Flow** tab, double-click the CDC source.</span></span>  
  
3.  <span data-ttu-id="02859-109">Dans l' **Éditeur de source CDC**, cliquez sur **Sortie d'erreur**.</span><span class="sxs-lookup"><span data-stu-id="02859-109">In the **CDC Source Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="02859-110">Options</span><span class="sxs-lookup"><span data-stu-id="02859-110">Options</span></span>  
 <span data-ttu-id="02859-111">**Entrée/sortie**</span><span class="sxs-lookup"><span data-stu-id="02859-111">**Input/Output**</span></span>  
 <span data-ttu-id="02859-112">Affichez le nom de la source de données.</span><span class="sxs-lookup"><span data-stu-id="02859-112">View the name of the data source.</span></span>  
  
 <span data-ttu-id="02859-113">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="02859-113">**Column**</span></span>  
 <span data-ttu-id="02859-114">Affichez les colonnes externes (sources) que vous avez sélectionnées dans la page **Gestionnaire de connexions** de la boîte de dialogue **Éditeur de source CDC** .</span><span class="sxs-lookup"><span data-stu-id="02859-114">View the external (source) columns that you selected on the **Connection Manager** page of the **CDC Source Editor** dialog box.</span></span>  
  
 <span data-ttu-id="02859-115">**Error**</span><span class="sxs-lookup"><span data-stu-id="02859-115">**Error**</span></span>  
 <span data-ttu-id="02859-116">Sélectionnez la façon dont la source CDC doit gérer les erreurs dans un flux : ignorer l'échec, rediriger la ligne ou faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="02859-116">Select how the CDC source should handle errors in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="02859-117">**Troncation**</span><span class="sxs-lookup"><span data-stu-id="02859-117">**Truncation**</span></span>  
 <span data-ttu-id="02859-118">Sélectionnez la façon dont la source CDC doit gérer la troncation dans un flux : ignorer l'échec, rediriger la ligne ou faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="02859-118">Select how the CDC source should handle truncation in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="02859-119">**Description**</span><span class="sxs-lookup"><span data-stu-id="02859-119">**Description**</span></span>  
 <span data-ttu-id="02859-120">Non utilisé.</span><span class="sxs-lookup"><span data-stu-id="02859-120">Not used.</span></span>  
  
 <span data-ttu-id="02859-121">**Définir cette valeur sur les cellules sélectionnées**</span><span class="sxs-lookup"><span data-stu-id="02859-121">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="02859-122">Sélectionnez la façon dont la source CDC gère l'ensemble des cellules sélectionnées lorsqu'une erreur ou une troncation se produit : ignorer l'échec, rediriger la ligne ou faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="02859-122">Select how the CDC source handles all selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="02859-123">**Appliquer**</span><span class="sxs-lookup"><span data-stu-id="02859-123">**Apply**</span></span>  
 <span data-ttu-id="02859-124">Appliquez les options de gestion des erreurs aux cellules sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="02859-124">Apply the error handling options to the selected cells.</span></span>  
  
## <a name="error-handling-options"></a><span data-ttu-id="02859-125">Options de gestion des erreurs</span><span class="sxs-lookup"><span data-stu-id="02859-125">Error Handling Options</span></span>  
 <span data-ttu-id="02859-126">Vous pouvez utiliser les options suivantes pour configurer la façon dont la source CDC gère les erreurs et les troncations.</span><span class="sxs-lookup"><span data-stu-id="02859-126">You use the following options to configure how the CDC source handles errors and truncations.</span></span>  
  
 <span data-ttu-id="02859-127">**Composant défaillant**</span><span class="sxs-lookup"><span data-stu-id="02859-127">**Fail Component**</span></span>  
 <span data-ttu-id="02859-128">La tâche de flux de données échoue lorsqu'une erreur ou une troncation a lieu.</span><span class="sxs-lookup"><span data-stu-id="02859-128">The Data Flow task fails when an error or a truncation occurs.</span></span> <span data-ttu-id="02859-129">Il s'agit du comportement par défaut.</span><span class="sxs-lookup"><span data-stu-id="02859-129">This is the default behavior.</span></span>  
  
 <span data-ttu-id="02859-130">**Ignorer l'échec**</span><span class="sxs-lookup"><span data-stu-id="02859-130">**Ignore Failure**</span></span>  
 <span data-ttu-id="02859-131">L'erreur ou la troncation est ignorée et la ligne de données est dirigée vers la sortie de la source CDC.</span><span class="sxs-lookup"><span data-stu-id="02859-131">The error or the truncation is ignored and the data row is directed to the CDC source output.</span></span>  
  
 <span data-ttu-id="02859-132">**Rediriger le flux**</span><span class="sxs-lookup"><span data-stu-id="02859-132">**Redirect Flow**</span></span>  
 <span data-ttu-id="02859-133">La ligne de données qui présente l'erreur ou la troncation est dirigée vers la sortie d'erreur de la source CDC.</span><span class="sxs-lookup"><span data-stu-id="02859-133">The error or the truncation data row is directed to the error output of the CDC source.</span></span> <span data-ttu-id="02859-134">Dans ce cas, la gestion des erreurs de la source CDC est utilisée.</span><span class="sxs-lookup"><span data-stu-id="02859-134">In this case the CDC source error handling is used.</span></span> <span data-ttu-id="02859-135">Pour plus d'informations, consultez [CDC Source](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="02859-135">For more information, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02859-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="02859-136">See Also</span></span>  
 <span data-ttu-id="02859-137">[Éditeur de source CDC &#40;page Gestionnaire de connexions&#41;](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="02859-137">[CDC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="02859-138">Éditeur de source CDC &#40;page Colonnes&#41;</span><span class="sxs-lookup"><span data-stu-id="02859-138">CDC Source Editor &#40;Columns Page&#41;</span></span>](../../2014/integration-services/cdc-source-editor-columns-page.md)  
  
  
