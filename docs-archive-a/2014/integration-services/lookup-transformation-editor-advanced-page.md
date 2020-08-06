---
title: Éditeur de transformation de recherche (page avancé) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.advanced.f1
helpviewer_keywords:
- Lookup Transformation Editor
ms.assetid: f3395c65-0320-47f9-8d83-daaa082d8713
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 23f235ef0506da7ac808d832db6ac36d53cfa604
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605555"
---
# <a name="lookup-transformation-editor-advanced-page"></a><span data-ttu-id="f9e0d-102">Éditeur de transformation de recherche (page Avancé)</span><span class="sxs-lookup"><span data-stu-id="f9e0d-102">Lookup Transformation Editor (Advanced Page)</span></span>
  <span data-ttu-id="f9e0d-103">La page **Avancé** de la boîte de dialogue **Éditeur de transformation de recherche** permet de configurer la mise en cache partielle et de modifier l’instruction SQL pour la transformation de recherche.</span><span class="sxs-lookup"><span data-stu-id="f9e0d-103">Use the **Advanced** page of the **Lookup Transformation Editor** dialog box to configure partial caching and to modify the SQL statement for the Lookup transformation.</span></span>  
  
 <span data-ttu-id="f9e0d-104">Pour en savoir plus sur la transformation de recherche, consultez [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="f9e0d-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="f9e0d-105">Options</span><span class="sxs-lookup"><span data-stu-id="f9e0d-105">Options</span></span>  
 <span data-ttu-id="f9e0d-106">**Taille du cache (32 bits)**</span><span class="sxs-lookup"><span data-stu-id="f9e0d-106">**Cache size (32-bit)**</span></span>  
 <span data-ttu-id="f9e0d-107">Ajustez la taille du cache (en mégaoctets) pour les ordinateurs 32 bits.</span><span class="sxs-lookup"><span data-stu-id="f9e0d-107">Adjust the  cache size (in megabytes) for 32-bit computers.</span></span> <span data-ttu-id="f9e0d-108">La valeur par défaut est 5 mégaoctets.</span><span class="sxs-lookup"><span data-stu-id="f9e0d-108">The default value is 5 megabytes.</span></span>  
  
 <span data-ttu-id="f9e0d-109">**Taille du cache (64 bits)**</span><span class="sxs-lookup"><span data-stu-id="f9e0d-109">**Cache size (64-bit)**</span></span>  
 <span data-ttu-id="f9e0d-110">Ajustez la taille du cache (en mégaoctets) pour les ordinateurs 64 bits.</span><span class="sxs-lookup"><span data-stu-id="f9e0d-110">Adjust the cache size (in megabytes) for 64-bit computers.</span></span> <span data-ttu-id="f9e0d-111">La valeur par défaut est 5 mégaoctets.</span><span class="sxs-lookup"><span data-stu-id="f9e0d-111">The default value is 5 megabytes.</span></span>  
  
 <span data-ttu-id="f9e0d-112">**Activer le cache pour les lignes sans entrées correspondantes**</span><span class="sxs-lookup"><span data-stu-id="f9e0d-112">**Enable cache for rows with no matching entries**</span></span>  
 <span data-ttu-id="f9e0d-113">Mettez en cache les lignes sans entrées correspondantes dans le dataset de référence.</span><span class="sxs-lookup"><span data-stu-id="f9e0d-113">Cache rows with no matching entries in the reference dataset.</span></span>  
  
 <span data-ttu-id="f9e0d-114">**Allocation à partir du cache**</span><span class="sxs-lookup"><span data-stu-id="f9e0d-114">**Allocation from cache**</span></span>  
 <span data-ttu-id="f9e0d-115">Spécifiez le pourcentage de cache à allouer aux lignes sans entrées correspondantes dans le dataset de référence.</span><span class="sxs-lookup"><span data-stu-id="f9e0d-115">Specify the percentage of the cache to allocate for rows with no matching entries in the reference dataset.</span></span>  
  
 <span data-ttu-id="f9e0d-116">**Modifier l'instruction SQL**</span><span class="sxs-lookup"><span data-stu-id="f9e0d-116">**Modify the SQL statement**</span></span>  
 <span data-ttu-id="f9e0d-117">Modifiez l'instruction SQL utilisée pour générer le dataset de référence.</span><span class="sxs-lookup"><span data-stu-id="f9e0d-117">Modify the SQL statement that is used to generate the reference dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f9e0d-118">L’instruction SQL facultative que vous spécifiez dans cette page substitue et remplace le nom de table que vous avez spécifié dans la page **Connexion** de **l’Éditeur de transformation de recherche**.</span><span class="sxs-lookup"><span data-stu-id="f9e0d-118">The optional SQL statement that you specify on this page overrides and replaces the table name that you specified on the **Connection** page of the **Lookup Transformation Editor**.</span></span> <span data-ttu-id="f9e0d-119">Pour plus d’informations, consultez [Éditeur de transformation de recherche &#40;page Connexion&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md).</span><span class="sxs-lookup"><span data-stu-id="f9e0d-119">For more information, see [Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md).</span></span>  
  
 <span data-ttu-id="f9e0d-120">**Définition des paramètres**</span><span class="sxs-lookup"><span data-stu-id="f9e0d-120">**Set Parameters**</span></span>  
 <span data-ttu-id="f9e0d-121">Mappez les colonnes d’entrée aux paramètres en utilisant la boîte de dialogue **Définition des paramètres de la requête** .</span><span class="sxs-lookup"><span data-stu-id="f9e0d-121">Map input columns to parameters by using the **Set Query Parameters** dialog box.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="f9e0d-122">Ressources externes</span><span class="sxs-lookup"><span data-stu-id="f9e0d-122">External Resources</span></span>  
 <span data-ttu-id="f9e0d-123">Entrée de blog, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) sur blogs.msdn.com</span><span class="sxs-lookup"><span data-stu-id="f9e0d-123">Blog entry, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) on blogs.msdn.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9e0d-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f9e0d-124">See Also</span></span>  
 <span data-ttu-id="f9e0d-125">[Éditeur de transformation de recherche &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="f9e0d-125">[Lookup Transformation Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="f9e0d-126">[Éditeur de transformation de recherche &#40;page connexion&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="f9e0d-126">[Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span></span>  
 <span data-ttu-id="f9e0d-127">[Éditeur de transformation de recherche &#40;page colonnes&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="f9e0d-127">[Lookup Transformation Editor &#40;Columns Page&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span></span>  
 <span data-ttu-id="f9e0d-128">[Éditeur de transformation de recherche &#40;page sortie d’erreur&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="f9e0d-128">[Lookup Transformation Editor &#40;Error Output Page&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="f9e0d-129">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="f9e0d-129">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="f9e0d-130">transformation de recherche floue</span><span class="sxs-lookup"><span data-stu-id="f9e0d-130">Fuzzy Lookup Transformation</span></span>](data-flow/transformations/fuzzy-lookup-transformation.md)  
  
  
