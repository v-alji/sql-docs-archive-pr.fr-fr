---
title: Éditeur de transformation de recherche (page général) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.general.f1
ms.assetid: 4bd15e48-0feb-4f95-be91-5df58105dbfb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aa178118f7e090b6a3c15c7ab9347f322461f07b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696983"
---
# <a name="lookup-transformation-editor-general-page"></a><span data-ttu-id="4e009-102">Éditeur de transformation de recherche (page Général)</span><span class="sxs-lookup"><span data-stu-id="4e009-102">Lookup Transformation Editor (General Page)</span></span>
  <span data-ttu-id="4e009-103">Utilisez la page **Général** de la boîte de dialogue Éditeur de transformation de recherche pour sélectionner le mode de cache ainsi que le type de connexion et pour spécifier comment gérer les lignes sans entrées correspondantes.</span><span class="sxs-lookup"><span data-stu-id="4e009-103">Use the **General** page of the Lookup Transformation Editor dialog box to select the cache mode, select the connection type, and specify how to handle rows with no matching entries.</span></span>  
  
 <span data-ttu-id="4e009-104">Pour en savoir plus sur la transformation de recherche, consultez [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="4e009-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4e009-105">Options</span><span class="sxs-lookup"><span data-stu-id="4e009-105">Options</span></span>  
 <span data-ttu-id="4e009-106">**Cache complet**</span><span class="sxs-lookup"><span data-stu-id="4e009-106">**Full cache**</span></span>  
 <span data-ttu-id="4e009-107">Générez et chargez le dataset de référence dans le cache avant l'exécution de la transformation de recherche.</span><span class="sxs-lookup"><span data-stu-id="4e009-107">Generate and load the reference dataset into cache before the Lookup transformation is executed.</span></span>  
  
 <span data-ttu-id="4e009-108">**Cache partiel**</span><span class="sxs-lookup"><span data-stu-id="4e009-108">**Partial cache**</span></span>  
 <span data-ttu-id="4e009-109">Générez le dataset de référence pendant l'exécution de la transformation de recherche.</span><span class="sxs-lookup"><span data-stu-id="4e009-109">Generate the reference dataset during the execution of the Lookup transformation.</span></span> <span data-ttu-id="4e009-110">Chargez dans le cache les lignes avec des entrées correspondantes dans le dataset de référence et celles sans entrées correspondantes dans le dataset.</span><span class="sxs-lookup"><span data-stu-id="4e009-110">Load the rows with matching entries in the reference dataset and the rows with no matching entries in the dataset into cache.</span></span>  
  
 <span data-ttu-id="4e009-111">**Aucun cache**</span><span class="sxs-lookup"><span data-stu-id="4e009-111">**No cache**</span></span>  
 <span data-ttu-id="4e009-112">Générez le dataset de référence pendant l'exécution de la transformation de recherche.</span><span class="sxs-lookup"><span data-stu-id="4e009-112">Generate the reference dataset during the execution of the Lookup transformation.</span></span> <span data-ttu-id="4e009-113">Aucune donnée n'est chargée dans le cache.</span><span class="sxs-lookup"><span data-stu-id="4e009-113">No data is loaded into cache.</span></span>  
  
 <span data-ttu-id="4e009-114">**Gestionnaire de connexions du cache**</span><span class="sxs-lookup"><span data-stu-id="4e009-114">**Cache connection manager**</span></span>  
 <span data-ttu-id="4e009-115">Configurez la transformation de recherche pour utiliser un gestionnaire de connexions du cache.</span><span class="sxs-lookup"><span data-stu-id="4e009-115">Configure the Lookup transformation to use a Cache connection manager.</span></span> <span data-ttu-id="4e009-116">Cette option n'est disponible que si l'option Cache complet est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4e009-116">This option is available only if the Full cache option is selected.</span></span>  
  
 <span data-ttu-id="4e009-117">**Gestionnaire de connexions OLE DB**</span><span class="sxs-lookup"><span data-stu-id="4e009-117">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="4e009-118">Configurez la transformation de recherche pour utiliser un gestionnaire de connexions OLE DB.</span><span class="sxs-lookup"><span data-stu-id="4e009-118">Configure the Lookup transformation to use an OLE DB connection manager.</span></span>  
  
 <span data-ttu-id="4e009-119">**Spécifier comment gérer les lignes sans entrées correspondantes**</span><span class="sxs-lookup"><span data-stu-id="4e009-119">**Specify how to handle rows with no matching entries**</span></span>  
 <span data-ttu-id="4e009-120">Sélectionnez une option pour gérer les lignes qui ne correspondent pas au moins à une entrée dans le dataset de référence.</span><span class="sxs-lookup"><span data-stu-id="4e009-120">Select an option for handling rows that do not match at least one entry in the reference dataset.</span></span>  
  
 <span data-ttu-id="4e009-121">Lorsque vous sélectionnez **Rediriger les lignes vers la sortie sans correspondance**, les lignes sont redirigées vers une sortie sans correspondance et ne sont pas gérées comme des erreurs.</span><span class="sxs-lookup"><span data-stu-id="4e009-121">When you select **Redirect rows to no match output**, the rows are redirected to a no match output and are not handled as errors.</span></span> <span data-ttu-id="4e009-122">L'option **Erreur** figurant dans la page **Sortie d'erreur** de la boîte de dialogue **Éditeur de transformation de recherche** n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="4e009-122">The **Error** option on the **Error Output** page of the **Lookup Transformation Editor** dialog box is not available.</span></span>  
  
 <span data-ttu-id="4e009-123">Lorsque vous sélectionnez une autre option dans la zone de liste **Spécifier comment gérer les lignes sans entrées correspondantes** , les lignes sont gérées comme des erreurs.</span><span class="sxs-lookup"><span data-stu-id="4e009-123">When you select any other option in the **Specify how to handle rows with no matching entries** list box, the rows are handled as errors.</span></span> <span data-ttu-id="4e009-124">L'option **Erreur** de la page **Sortie d'erreur** est disponible.</span><span class="sxs-lookup"><span data-stu-id="4e009-124">The **Error** option on the **Error Output** page is available.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="4e009-125">Ressources externes</span><span class="sxs-lookup"><span data-stu-id="4e009-125">External Resources</span></span>  
 <span data-ttu-id="4e009-126">Entrée de blog, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) sur blogs.msdn.com</span><span class="sxs-lookup"><span data-stu-id="4e009-126">Blog entry, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) on blogs.msdn.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e009-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4e009-127">See Also</span></span>  
 <span data-ttu-id="4e009-128">[Gestionnaire de connexions du cache](connection-manager/cache-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="4e009-128">[Cache Connection Manager](connection-manager/cache-connection-manager.md) </span></span>  
 <span data-ttu-id="4e009-129">[Éditeur de transformation de recherche &#40;page connexion&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="4e009-129">[Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span></span>  
 <span data-ttu-id="4e009-130">[Éditeur de transformation de recherche &#40;page colonnes&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="4e009-130">[Lookup Transformation Editor &#40;Columns Page&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span></span>  
 <span data-ttu-id="4e009-131">[Éditeur de transformation de recherche &#40;&#41;de page avancé](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="4e009-131">[Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="4e009-132">Éditeur de transformation de recherche &#40;page Sortie d’erreur&#41;</span><span class="sxs-lookup"><span data-stu-id="4e009-132">Lookup Transformation Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/lookup-transformation-editor-error-output-page.md)  
  
  
