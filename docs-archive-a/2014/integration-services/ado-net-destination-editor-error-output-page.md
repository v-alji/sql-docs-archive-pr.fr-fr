---
title: Éditeur de destination ADO NET (page sortie d’erreur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetdest.erroroutput.f1
ms.assetid: 1a56c3cf-fb6a-416d-a62c-bb19fe441ae5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9cfd69d3adec2aa617f5e9d3add35a1a6923804
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605685"
---
# <a name="ado-net-destination-editor-error-output-page"></a><span data-ttu-id="d37cc-102">Éditeur de destination ADO NET (page Sortie d'erreur)</span><span class="sxs-lookup"><span data-stu-id="d37cc-102">ADO NET Destination Editor (Error Output Page)</span></span>
  <span data-ttu-id="d37cc-103">Utilisez la page **Sortie d'erreur** de la boîte de dialogue **Éditeur de destination ADO NET** pour spécifier les options de gestion des erreurs.</span><span class="sxs-lookup"><span data-stu-id="d37cc-103">Use the **Error Output** page of the **ADO NET Destination Editor** dialog box to specify error handling options.</span></span>  
  
 <span data-ttu-id="d37cc-104">Pour en savoir plus sur la destination ADO NET, consultez [ADO NET Destination](data-flow/ado-net-destination.md).</span><span class="sxs-lookup"><span data-stu-id="d37cc-104">To learn more about the ADO NET destination, see [ADO NET Destination](data-flow/ado-net-destination.md).</span></span>  
  
 <span data-ttu-id="d37cc-105">**Pour ouvrir la page Sortie d'erreur**</span><span class="sxs-lookup"><span data-stu-id="d37cc-105">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="d37cc-106">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] qui possède la destination ADO NET.</span><span class="sxs-lookup"><span data-stu-id="d37cc-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET destination.</span></span>  
  
2.  <span data-ttu-id="d37cc-107">Sous l’onglet **Flux de données** , double-cliquez sur la destination ADO NET.</span><span class="sxs-lookup"><span data-stu-id="d37cc-107">On the **Data Flow** tab, double-click the ADO NET destination.</span></span>  
  
3.  <span data-ttu-id="d37cc-108">Dans **l’Éditeur de destination ADO NET**, cliquez sur **Sortie d’erreur**.</span><span class="sxs-lookup"><span data-stu-id="d37cc-108">In the **ADO NET Destination Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d37cc-109">Options</span><span class="sxs-lookup"><span data-stu-id="d37cc-109">Options</span></span>  
 <span data-ttu-id="d37cc-110">**Entrée ou Sortie**</span><span class="sxs-lookup"><span data-stu-id="d37cc-110">**Input or Output**</span></span>  
 <span data-ttu-id="d37cc-111">Affichez le nom de l'entrée.</span><span class="sxs-lookup"><span data-stu-id="d37cc-111">View the name of the input.</span></span>  
  
 <span data-ttu-id="d37cc-112">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d37cc-112">**Column**</span></span>  
 <span data-ttu-id="d37cc-113">Non utilisé.</span><span class="sxs-lookup"><span data-stu-id="d37cc-113">Not used.</span></span>  
  
 <span data-ttu-id="d37cc-114">**Error**</span><span class="sxs-lookup"><span data-stu-id="d37cc-114">**Error**</span></span>  
 <span data-ttu-id="d37cc-115">Indiquez ce qui doit se produire lorsqu'une erreur se produit : ignorer l'échec, rediriger la ligne ou faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="d37cc-115">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="d37cc-116">**Rubriques connexes :** [Gestion des erreurs dans les données](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="d37cc-116">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="d37cc-117">**Troncation**</span><span class="sxs-lookup"><span data-stu-id="d37cc-117">**Truncation**</span></span>  
 <span data-ttu-id="d37cc-118">Non utilisé.</span><span class="sxs-lookup"><span data-stu-id="d37cc-118">Not used.</span></span>  
  
 <span data-ttu-id="d37cc-119">**Description**</span><span class="sxs-lookup"><span data-stu-id="d37cc-119">**Description**</span></span>  
 <span data-ttu-id="d37cc-120">Affichez la description de l'opération.</span><span class="sxs-lookup"><span data-stu-id="d37cc-120">View the description of the operation.</span></span>  
  
 <span data-ttu-id="d37cc-121">**Définir cette valeur sur les cellules sélectionnées**</span><span class="sxs-lookup"><span data-stu-id="d37cc-121">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="d37cc-122">Indiquez ce qui doit se produire pour l'ensemble des cellules sélectionnées lorsqu'une erreur ou une troncation se produit : ignorer l'échec, rediriger la ligne ou faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="d37cc-122">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="d37cc-123">**Appliquer**</span><span class="sxs-lookup"><span data-stu-id="d37cc-123">**Apply**</span></span>  
 <span data-ttu-id="d37cc-124">Appliquez l'option de gestion des erreurs aux cellules sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="d37cc-124">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d37cc-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d37cc-125">See Also</span></span>  
 <span data-ttu-id="d37cc-126">[Éditeur de destination ADO NET &#40;page Gestionnaire de connexions&#41;](../../2014/integration-services/ado-net-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="d37cc-126">[ADO NET Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ado-net-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="d37cc-127">Éditeur de destination ADO NET &#40;page Mappages&#41;</span><span class="sxs-lookup"><span data-stu-id="d37cc-127">ADO NET Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/ado-net-destination-editor-mappings-page.md)  
  
  
