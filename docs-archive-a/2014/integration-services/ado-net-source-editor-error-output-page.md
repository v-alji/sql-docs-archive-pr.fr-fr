---
title: Éditeur de source ADO NET (page sortie d’erreur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetsource.erroroutput.f1
ms.assetid: 4dd9d129-a95c-4d3a-bbbf-e84a39089950
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9ee480caa8764d70b52b25a416f200f353d30c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707747"
---
# <a name="ado-net-source-editor-error-output-page"></a><span data-ttu-id="11409-102">Éditeur de source ADO NET (page Sortie d'erreur)</span><span class="sxs-lookup"><span data-stu-id="11409-102">ADO NET Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="11409-103">Utilisez la page **Sortie d'erreur** de la boîte de dialogue **Éditeur de source ADO NET** pour sélectionner les options de gestion des erreurs et pour définir les propriétés des colonnes de sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="11409-103">Use the **Error Output** page of the **ADO NET Source Editor** dialog box to select error handling options and to set properties on error output columns.</span></span>  
  
 <span data-ttu-id="11409-104">Pour en savoir plus sur la source ADO NET, consultez [ADO NET Source](data-flow/ado-net-source.md).</span><span class="sxs-lookup"><span data-stu-id="11409-104">To learn more about the ADO NET source, see [ADO NET Source](data-flow/ado-net-source.md).</span></span>  
  
 <span data-ttu-id="11409-105">**Pour ouvrir la page Sortie d'erreur**</span><span class="sxs-lookup"><span data-stu-id="11409-105">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="11409-106">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] qui possède la source ADO NET.</span><span class="sxs-lookup"><span data-stu-id="11409-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET source.</span></span>  
  
2.  <span data-ttu-id="11409-107">Sous l’onglet **Flux de données** , double-cliquez sur la source ADO NET.</span><span class="sxs-lookup"><span data-stu-id="11409-107">On the **Data Flow** tab, double-click the ADO NET source.</span></span>  
  
3.  <span data-ttu-id="11409-108">Dans l' **Éditeur de source ADO NET**, cliquez sur **Sortie d'erreur**.</span><span class="sxs-lookup"><span data-stu-id="11409-108">In the **ADO NET Source Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="11409-109">Options</span><span class="sxs-lookup"><span data-stu-id="11409-109">Options</span></span>  
 <span data-ttu-id="11409-110">**Entrée/sortie**</span><span class="sxs-lookup"><span data-stu-id="11409-110">**Input/Output**</span></span>  
 <span data-ttu-id="11409-111">Affichez le nom de la source de données.</span><span class="sxs-lookup"><span data-stu-id="11409-111">View the name of the data source.</span></span>  
  
 <span data-ttu-id="11409-112">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="11409-112">**Column**</span></span>  
 <span data-ttu-id="11409-113">Affichez les colonnes externes (sources) que vous avez sélectionnées dans la page **Gestionnaire de connexions** de la boîte de dialogue **Éditeur de source ADO NET** .</span><span class="sxs-lookup"><span data-stu-id="11409-113">View the external (source) columns that you selected on the **Connection Manager** page of the **ADO NET Source Editor** dialog box.</span></span>  
  
 <span data-ttu-id="11409-114">**Error**</span><span class="sxs-lookup"><span data-stu-id="11409-114">**Error**</span></span>  
 <span data-ttu-id="11409-115">Indiquez ce qui doit se produire lorsqu'une erreur se produit : ignorer l'échec, rediriger la ligne ou faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="11409-115">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="11409-116">**Rubriques connexes :** [Gestion des erreurs dans les données](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="11409-116">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="11409-117">**Troncation**</span><span class="sxs-lookup"><span data-stu-id="11409-117">**Truncation**</span></span>  
 <span data-ttu-id="11409-118">Indiquez ce qui doit se produire lorsqu'une troncation se produit : ignorer l'échec, rediriger la ligne ou faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="11409-118">Specify what should happen when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="11409-119">**Description**</span><span class="sxs-lookup"><span data-stu-id="11409-119">**Description**</span></span>  
 <span data-ttu-id="11409-120">Affiche la description de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="11409-120">View the description of the error.</span></span>  
  
 <span data-ttu-id="11409-121">**Définir cette valeur sur les cellules sélectionnées**</span><span class="sxs-lookup"><span data-stu-id="11409-121">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="11409-122">Indiquez ce qui doit se produire pour l'ensemble des cellules sélectionnées lorsqu'une erreur ou une troncation se produit : ignorer l'échec, rediriger la ligne ou faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="11409-122">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="11409-123">**Appliquer**</span><span class="sxs-lookup"><span data-stu-id="11409-123">**Apply**</span></span>  
 <span data-ttu-id="11409-124">Appliquez l'option de gestion des erreurs aux cellules sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="11409-124">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11409-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="11409-125">See Also</span></span>  
 <span data-ttu-id="11409-126">[Éditeur de source ADO NET &#40;page Gestionnaire de connexions&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="11409-126">[ADO NET Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="11409-127">[Éditeur de source ADO NET &#40;page colonnes&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="11409-127">[ADO NET Source Editor &#40;Columns Page&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="11409-128">Gestionnaire de connexions ADO.NET</span><span class="sxs-lookup"><span data-stu-id="11409-128">ADO.NET Connection Manager</span></span>](connection-manager/ado-net-connection-manager.md)  
  
  
