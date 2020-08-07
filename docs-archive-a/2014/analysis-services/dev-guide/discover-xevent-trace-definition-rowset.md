---
title: Ensemble de lignes DISCOVER_XEVENT_TRACE_DEFINITION | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: e1ce2d2d-f994-4318-801a-ee0385aecd84
author: minewiskan
ms.author: owend
ms.openlocfilehash: bedd6ec66a188738ac9a522b4802b3b431e82f36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703399"
---
# <a name="discover_xevent_trace_definition-rowset"></a><span data-ttu-id="34a8c-102">DISCOVER_XEVENT_TRACE_DEFINITION, ensemble de lignes</span><span class="sxs-lookup"><span data-stu-id="34a8c-102">DISCOVER_XEVENT_TRACE_DEFINITION Rowset</span></span>
  <span data-ttu-id="34a8c-103">Fournit des informations sur les traces XEvent qui sont actuellement actives sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="34a8c-103">Provides information about XEvent traces that are currently active on the server.</span></span>  
  
 <span data-ttu-id="34a8c-104">**S'applique à :** modèles tabulaires, modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="34a8c-104">**Applies to:** tabular models, multidimensional models</span></span>  
  
## <a name="rowset-columns"></a><span data-ttu-id="34a8c-105">Colonnes de l'ensemble de lignes</span><span class="sxs-lookup"><span data-stu-id="34a8c-105">Rowset Columns</span></span>  
 <span data-ttu-id="34a8c-106">L'ensemble de lignes `DISCOVER_XEVENT_TRACE_DEFINITION` contient les colonnes suivantes.</span><span class="sxs-lookup"><span data-stu-id="34a8c-106">The `DISCOVER_XEVENT_TRACE_DEFINITION` rowset contains the following columns.</span></span>  
  
|<span data-ttu-id="34a8c-107">Nom de la colonne</span><span class="sxs-lookup"><span data-stu-id="34a8c-107">Column name</span></span>|<span data-ttu-id="34a8c-108">Indicateur de type</span><span class="sxs-lookup"><span data-stu-id="34a8c-108">Type indicator</span></span>|<span data-ttu-id="34a8c-109">Longueur</span><span class="sxs-lookup"><span data-stu-id="34a8c-109">Length</span></span>|<span data-ttu-id="34a8c-110">Description</span><span class="sxs-lookup"><span data-stu-id="34a8c-110">Description</span></span>|  
|-----------------|--------------------|------------|-----------------|  
|`Data`|`DBTYPE_WSTR`||<span data-ttu-id="34a8c-111">Définition XML de la trace XEvent.</span><span class="sxs-lookup"><span data-stu-id="34a8c-111">The XML definition of the XEvent trace.</span></span>|  
  
 <span data-ttu-id="34a8c-112">Cet ensemble de lignes de schéma n'est pas trié.</span><span class="sxs-lookup"><span data-stu-id="34a8c-112">This schema rowset is not sorted.</span></span>  
  
## <a name="using-adomdnet-to-return-the-rowset"></a><span data-ttu-id="34a8c-113">Utilisation d'ADOMD.NET pour retourner l'ensemble de lignes</span><span class="sxs-lookup"><span data-stu-id="34a8c-113">Using ADOMD.NET to return the rowset</span></span>  
 <span data-ttu-id="34a8c-114">Lorsque vous utilisez ADOMD.NET et l'ensemble de lignes de schéma pour récupérer des métadonnées, vous pouvez utiliser un GUID ou une chaîne pour référencer un objet d'ensemble de lignes de schéma dans la méthode GetSchemaDataSet.</span><span class="sxs-lookup"><span data-stu-id="34a8c-114">When using ADOMD.NET and the schema rowset to retrieve metadata, you can use either the GUID or string to reference a schema rowset object in the GetSchemaDataSet method.</span></span> <span data-ttu-id="34a8c-115">Pour plus d'informations, consultez [Working with Schema Rowsets in ADOMD.NET](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-client/retrieving-metadata-working-with-schema-rowsets).</span><span class="sxs-lookup"><span data-stu-id="34a8c-115">For more information, see [Working with Schema Rowsets in ADOMD.NET](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-client/retrieving-metadata-working-with-schema-rowsets).</span></span>  
  
 <span data-ttu-id="34a8c-116">Le tableau suivant fournit le GUID et les valeurs de chaîne qui identifient cet ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="34a8c-116">The following table provides the GUID and string values that identify this rowset.</span></span>  
  
|<span data-ttu-id="34a8c-117">Argument</span><span class="sxs-lookup"><span data-stu-id="34a8c-117">Argument</span></span>|<span data-ttu-id="34a8c-118">Valeur</span><span class="sxs-lookup"><span data-stu-id="34a8c-118">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="34a8c-119">GUID</span><span class="sxs-lookup"><span data-stu-id="34a8c-119">GUID</span></span>|<span data-ttu-id="34a8c-120">a07ccd1c-8148-11d0-87bb-00c04fc33942</span><span class="sxs-lookup"><span data-stu-id="34a8c-120">a07ccd1c-8148-11d0-87bb-00c04fc33942</span></span>|  
|<span data-ttu-id="34a8c-121">String</span><span class="sxs-lookup"><span data-stu-id="34a8c-121">String</span></span>|<span data-ttu-id="34a8c-122">DISCOVER_XEVENT_TRACE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="34a8c-122">DISCOVER_XEVENT_TRACE_DEFINITION</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="34a8c-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="34a8c-123">See Also</span></span>  
 <span data-ttu-id="34a8c-124">[Ensembles de lignes de schéma XML for Analysis](https://docs.microsoft.com/bi-reference/schema-rowsets/xml/xml-for-analysis-schema-rowsets) </span><span class="sxs-lookup"><span data-stu-id="34a8c-124">[XML for Analysis Schema Rowsets](https://docs.microsoft.com/bi-reference/schema-rowsets/xml/xml-for-analysis-schema-rowsets) </span></span>  
 <span data-ttu-id="34a8c-125">[Utilisez SQL Server des événements étendus &#40;&#41; XEvents pour surveiller Analysis Services](../instances/monitor-analysis-services-with-sql-server-extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="34a8c-125">[Use SQL Server Extended Events &#40;XEvents&#41; to Monitor Analysis Services](../instances/monitor-analysis-services-with-sql-server-extended-events.md) </span></span>  
 [<span data-ttu-id="34a8c-126">Utiliser des vues de gestion dynamique &#40;DMV&#41; pour surveiller Analysis Services</span><span class="sxs-lookup"><span data-stu-id="34a8c-126">Use Dynamic Management Views &#40;DMVs&#41; to Monitor Analysis Services</span></span>](../instances/use-dynamic-management-views-dmvs-to-monitor-analysis-services.md)  
  
  
