---
title: Éditeur de transformation de recherche (page sortie d’erreur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.erroroutput.f1
ms.assetid: 15d53bb0-8be1-46fb-b459-04a397e75fac
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9cd78f40a0072f7f0c5c923cdd51431873402f3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605550"
---
# <a name="lookup-transformation-editor-error-output-page"></a><span data-ttu-id="8d0a5-102">Éditeur de transformation de recherche (page Sortie d'erreur)</span><span class="sxs-lookup"><span data-stu-id="8d0a5-102">Lookup Transformation Editor (Error Output Page)</span></span>
  <span data-ttu-id="8d0a5-103">Utilisez la page **Sortie d'erreur** de la boîte de dialogue **Éditeur de transformation de recherche** pour définir les options de gestion des erreurs.</span><span class="sxs-lookup"><span data-stu-id="8d0a5-103">Use the **Error Output** page of the **Lookup Transformation Editor** dialog box to specify error handling options.</span></span>  
  
 <span data-ttu-id="8d0a5-104">Pour en savoir plus sur la transformation de recherche, consultez [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="8d0a5-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="8d0a5-105">Options</span><span class="sxs-lookup"><span data-stu-id="8d0a5-105">Options</span></span>  
 <span data-ttu-id="8d0a5-106">**Entrée/sortie**</span><span class="sxs-lookup"><span data-stu-id="8d0a5-106">**Input/Output**</span></span>  
 <span data-ttu-id="8d0a5-107">Affichez le nom de l'entrée.</span><span class="sxs-lookup"><span data-stu-id="8d0a5-107">View the name of the input.</span></span>  
  
 <span data-ttu-id="8d0a5-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="8d0a5-108">**Column**</span></span>  
 <span data-ttu-id="8d0a5-109">Non utilisé.</span><span class="sxs-lookup"><span data-stu-id="8d0a5-109">Not used.</span></span>  
  
 <span data-ttu-id="8d0a5-110">**Error**</span><span class="sxs-lookup"><span data-stu-id="8d0a5-110">**Error**</span></span>  
 <span data-ttu-id="8d0a5-111">Spécifiez le type d'erreur devant se produire lors de la gestion des lignes sans entrées correspondantes dans le dataset de référence :</span><span class="sxs-lookup"><span data-stu-id="8d0a5-111">Specify what type of error should occur when handling rows without matching entries in the reference dataset:</span></span>  
  
-   <span data-ttu-id="8d0a5-112">ignorer l'échec et diriger les lignes vers une sortie ;</span><span class="sxs-lookup"><span data-stu-id="8d0a5-112">Ignore the failure and direct the rows to an output.</span></span>  
  
-   <span data-ttu-id="8d0a5-113">rediriger les lignes vers une sortie d'erreur ;</span><span class="sxs-lookup"><span data-stu-id="8d0a5-113">Redirect the rows to an error output.</span></span>  
  
-   <span data-ttu-id="8d0a5-114">faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="8d0a5-114">Fail the component.</span></span>  
  
 <span data-ttu-id="8d0a5-115">Cette option n'est pas disponible lorsque vous sélectionnez **Rediriger les lignes vers la sortie sans correspondance** dans la liste **Spécifier comment gérer les lignes sans entrées correspondantes** .</span><span class="sxs-lookup"><span data-stu-id="8d0a5-115">This option is not available when you select **Redirect rows to no match output** in the **Specify how to handle rows with no matching entries** list.</span></span> <span data-ttu-id="8d0a5-116">Cette liste se trouve dans la page **Général** de la boîte de dialogue **Éditeur de transformation de recherche** .</span><span class="sxs-lookup"><span data-stu-id="8d0a5-116">This list is on the **General** page of the **Lookup Transformation Editor** dialog box.</span></span>  
  
 <span data-ttu-id="8d0a5-117">**Rubriques connexes :** [Gestion des erreurs dans les données](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="8d0a5-117">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="8d0a5-118">**Troncation**</span><span class="sxs-lookup"><span data-stu-id="8d0a5-118">**Truncation**</span></span>  
 <span data-ttu-id="8d0a5-119">Spécifiez ce qui doit se passer lorsqu'une troncation de données a lieu :</span><span class="sxs-lookup"><span data-stu-id="8d0a5-119">Specify what should happen when data truncation occurs:</span></span>  
  
-   <span data-ttu-id="8d0a5-120">ignorer l'erreur ;</span><span class="sxs-lookup"><span data-stu-id="8d0a5-120">Ignore the failure.</span></span>  
  
-   <span data-ttu-id="8d0a5-121">rediriger la ligne ;</span><span class="sxs-lookup"><span data-stu-id="8d0a5-121">Redirect the row.</span></span>  
  
-   <span data-ttu-id="8d0a5-122">faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="8d0a5-122">Fail the component.</span></span>  
  
 <span data-ttu-id="8d0a5-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="8d0a5-123">**Description**</span></span>  
 <span data-ttu-id="8d0a5-124">Affichez la description de l'opération.</span><span class="sxs-lookup"><span data-stu-id="8d0a5-124">View the description of the operation.</span></span>  
  
 <span data-ttu-id="8d0a5-125">**Définir cette valeur sur les cellules sélectionnées**</span><span class="sxs-lookup"><span data-stu-id="8d0a5-125">**Set selected cells to this value**</span></span>  
 <span data-ttu-id="8d0a5-126">Indiquez ce qui doit se produire pour toutes les cellules sélectionnées lorsqu'une erreur ou une troncation a lieu :</span><span class="sxs-lookup"><span data-stu-id="8d0a5-126">Specify what should happen to all the selected cells when an error or truncation occurs:</span></span>  
  
-   <span data-ttu-id="8d0a5-127">ignorer l'erreur ;</span><span class="sxs-lookup"><span data-stu-id="8d0a5-127">Ignore the failure.</span></span>  
  
-   <span data-ttu-id="8d0a5-128">rediriger la ligne ;</span><span class="sxs-lookup"><span data-stu-id="8d0a5-128">Redirect the row.</span></span>  
  
-   <span data-ttu-id="8d0a5-129">faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="8d0a5-129">Fail the component.</span></span>  
  
 <span data-ttu-id="8d0a5-130">**Appliquer**</span><span class="sxs-lookup"><span data-stu-id="8d0a5-130">**Apply**</span></span>  
 <span data-ttu-id="8d0a5-131">Appliquez l'option de gestion des erreurs aux cellules sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="8d0a5-131">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d0a5-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8d0a5-132">See Also</span></span>  
 [<span data-ttu-id="8d0a5-133">Guide de référence des erreurs et des messages propres à Integration Services</span><span class="sxs-lookup"><span data-stu-id="8d0a5-133">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
