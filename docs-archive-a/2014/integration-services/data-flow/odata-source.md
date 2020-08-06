---
title: Source OData | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.ODATASOURCE.F1
ms.assetid: cc9003c9-638e-432b-867e-e949d50cec90
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 98b14ef034597f6098f70386ca41c1b90be86500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708499"
---
# <a name="odata-source"></a><span data-ttu-id="2a8be-102">Source OData</span><span class="sxs-lookup"><span data-stu-id="2a8be-102">OData Source</span></span>
  <span data-ttu-id="2a8be-103">Utilisez le composant source OData dans un package SSIS pour consommer les données provenant de services OData (Open Data Protocol).</span><span class="sxs-lookup"><span data-stu-id="2a8be-103">You use the OData Source component in an SSIS package to consume data from Open Data Protocol (OData) services.</span></span> <span data-ttu-id="2a8be-104">Le composant prend en charge les protocoles OData v2 et v3, ainsi que formats de données et ATOM de JSON.</span><span class="sxs-lookup"><span data-stu-id="2a8be-104">The component supports the OData v2 and v3 protocols, as well as the ATOM and JSON data formats.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2a8be-105">La source OData peut être utilisée pour lire des listes SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2a8be-105">The OData Source can be used to read from SharePoint lists.</span></span> <span data-ttu-id="2a8be-106">Pour afficher toutes les listes sur votre serveur SharePoint, utilisez l’URL suivante : http:// \<server> /_vti_bin/listdata.svc.</span><span class="sxs-lookup"><span data-stu-id="2a8be-106">To see all lists on your SharePoint server, use the following URL: http://\<server>/_vti_bin/ListData.svc.</span></span> <span data-ttu-id="2a8be-107">Pour plus d'informations sur les conventions d'URL SharePoint, consultez [Interface REST de SharePoint Foundation](https://msdn.microsoft.com/library/ff521587.aspx).</span><span class="sxs-lookup"><span data-stu-id="2a8be-107">For more information about SharePoint URL conventions, see [SharePoint Foundation REST Interface](https://msdn.microsoft.com/library/ff521587.aspx).</span></span>  
  
## <a name="odata-format"></a><span data-ttu-id="2a8be-108">Format OData</span><span class="sxs-lookup"><span data-stu-id="2a8be-108">OData Format</span></span>  
 <span data-ttu-id="2a8be-109">La plupart des services ODatas retournent les résultats dans plusieurs formats.</span><span class="sxs-lookup"><span data-stu-id="2a8be-109">Most OData services return results in multiple formats.</span></span> <span data-ttu-id="2a8be-110">Vous pouvez spécifier le format du jeu de résultats à l'aide de l'option de requête $format.</span><span class="sxs-lookup"><span data-stu-id="2a8be-110">You can specify the format of the result set by using the $format query option.</span></span> <span data-ttu-id="2a8be-111">Les formats comme JSON et JSON Light sont plus efficaces qu'ATOM/XML, et peuvent offrir de meilleures performances en cas de transfert d'un grand volume de données.</span><span class="sxs-lookup"><span data-stu-id="2a8be-111">Formats such as JSON and JSON Light are more efficient than ATOM/XML, and may give you better performance when transferring large amounts of data.</span></span> <span data-ttu-id="2a8be-112">Le tableau suivant fournit les résultats des tests.</span><span class="sxs-lookup"><span data-stu-id="2a8be-112">The following table provides results from sample tests.</span></span> <span data-ttu-id="2a8be-113">Comme vous pouvez le voir, un gain de performances de 30-53 % a été enregistré en passant d'ATOM à JSON, et un gain de performances de 67 % a été constaté en passant d'ATOM au nouveau format JSON Light (disponible dans WCF Data Services 5.1).</span><span class="sxs-lookup"><span data-stu-id="2a8be-113">As you can see, there was a 30-53% performance gain when switching from ATOM to JSON and 67% performance gain when switching from ATOM to the new JSON light format (available in WCF Data Services 5.1).</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="2a8be-114">Lignes</span><span class="sxs-lookup"><span data-stu-id="2a8be-114">Rows</span></span>|<span data-ttu-id="2a8be-115">ATOM</span><span class="sxs-lookup"><span data-stu-id="2a8be-115">ATOM</span></span>|<span data-ttu-id="2a8be-116">JSON</span><span class="sxs-lookup"><span data-stu-id="2a8be-116">JSON</span></span>|<span data-ttu-id="2a8be-117">JSON (Light)</span><span class="sxs-lookup"><span data-stu-id="2a8be-117">JSON (Light)</span></span>|  
|<span data-ttu-id="2a8be-118">10000</span><span class="sxs-lookup"><span data-stu-id="2a8be-118">10000</span></span>|<span data-ttu-id="2a8be-119">113 secondes</span><span class="sxs-lookup"><span data-stu-id="2a8be-119">113 seconds</span></span>|<span data-ttu-id="2a8be-120">74 secondes</span><span class="sxs-lookup"><span data-stu-id="2a8be-120">74 seconds</span></span>|<span data-ttu-id="2a8be-121">68 secondes</span><span class="sxs-lookup"><span data-stu-id="2a8be-121">68 seconds</span></span>|  
|<span data-ttu-id="2a8be-122">1000000</span><span class="sxs-lookup"><span data-stu-id="2a8be-122">1000000</span></span>|<span data-ttu-id="2a8be-123">1110 secondes</span><span class="sxs-lookup"><span data-stu-id="2a8be-123">1110 seconds</span></span>|<span data-ttu-id="2a8be-124">853 secondes</span><span class="sxs-lookup"><span data-stu-id="2a8be-124">853 seconds</span></span>|<span data-ttu-id="2a8be-125">665 secondes</span><span class="sxs-lookup"><span data-stu-id="2a8be-125">665 seconds</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="2a8be-126">La source OData SSIS utilise ODataLib 5.5.0 pour analyser les flux OData et peut lire tous les formats pris en charge par cette bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="2a8be-126">The SSIS OData Source uses ODataLib 5.5.0 to parse OData feeds and it can read all formats supported by this library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2a8be-127">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="2a8be-127">In This Section</span></span>  
  
-   [<span data-ttu-id="2a8be-128">Installer et désinstaller le composant source OData</span><span class="sxs-lookup"><span data-stu-id="2a8be-128">Install and Uninstall OData Source Component</span></span>](../install-and-uninstall-odata-source-component.md)  
  
-   [<span data-ttu-id="2a8be-129">Didacticiel : utilisation de la source OData &#91;&#93;SSIS</span><span class="sxs-lookup"><span data-stu-id="2a8be-129">Tutorial: Using the OData Source &#91;SSIS&#93;</span></span>](tutorial-using-the-odata-source.md)  
  
-   [<span data-ttu-id="2a8be-130">Modifier la requête de la source OData à l’exécution</span><span class="sxs-lookup"><span data-stu-id="2a8be-130">Modify OData Source Query at Runtime</span></span>](modify-odata-source-query-at-runtime.md)  
  
-   [<span data-ttu-id="2a8be-131">Éditeur de la source OData &#40;page Connexion&#41;</span><span class="sxs-lookup"><span data-stu-id="2a8be-131">OData Source Editor &#40;Connection Page&#41;</span></span>](../odata-source-editor-connection-page.md)  
  
-   [<span data-ttu-id="2a8be-132">Éditeur de source OData &#40;page Colonnes&#41;</span><span class="sxs-lookup"><span data-stu-id="2a8be-132">OData Source Editor &#40;Columns Page&#41;</span></span>](../odata-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="2a8be-133">Éditeur de la source OData &#40;page Sortie d’erreur&#41;</span><span class="sxs-lookup"><span data-stu-id="2a8be-133">OData Source Editor &#40;Error Output Page&#41;</span></span>](../odata-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="2a8be-134">Propriétés de la source OData</span><span class="sxs-lookup"><span data-stu-id="2a8be-134">OData Source Properties</span></span>](odata-source-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="2a8be-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2a8be-135">See Also</span></span>  
 [<span data-ttu-id="2a8be-136">Gestionnaire de connexions OData</span><span class="sxs-lookup"><span data-stu-id="2a8be-136">OData Connection Manager</span></span>](../connection-manager/odata-connection-manager.md)  
  
  
