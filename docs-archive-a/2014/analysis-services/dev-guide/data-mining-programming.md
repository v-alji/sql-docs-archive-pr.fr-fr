---
title: Programmation de l’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- data mining [Analysis Services], developer's guide
ms.assetid: 9fd77b16-0b89-44ce-bcf1-7c04b62499da
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd4bd48b5914d5fda89f94c0a959e670ffec3321
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696291"
---
# <a name="data-mining-programming"></a><span data-ttu-id="93998-102">Programmation de l'exploration de données</span><span class="sxs-lookup"><span data-stu-id="93998-102">Data Mining Programming</span></span>
  <span data-ttu-id="93998-103">Si vous estimez que les outils et composants intégrés dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ne répondent pas à vos besoins, vous pouvez étendre la puissance de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en codant vos propres extensions.</span><span class="sxs-lookup"><span data-stu-id="93998-103">If you find that the built-in tools and viewers in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] do not meet your requirements, you can extend the power of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] by coding your own extensions.</span></span> <span data-ttu-id="93998-104">Dans cette optique, deux options sont à votre disposition :</span><span class="sxs-lookup"><span data-stu-id="93998-104">In this approach, you have two options:</span></span>  
  
-   <span data-ttu-id="93998-105">**XMLA**</span><span class="sxs-lookup"><span data-stu-id="93998-105">**XMLA**</span></span>  
  
     [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="93998-106">[!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)]prend en charge XML for Analysis (XMLA) comme protocole pour la communication avec les applications clientes.</span><span class="sxs-lookup"><span data-stu-id="93998-106">[!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] supports XML for Analysis (XMLA) as a protocol for communication with client applications.</span></span> <span data-ttu-id="93998-107">Des commandes supplémentaires qui étendent la spécification XML for Analysis sont prises en charge par [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93998-107">Additional commands are supported by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that extend the XML for Analysis specification.</span></span>  
  
     <span data-ttu-id="93998-108">Dans la mesure où [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] utilise XMLA pour la définition, la manipulation et le contrôle de données, vous pouvez créer des structures et des modèles d'exploration de données à l'aide des outils visuels fournis par [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], puis étendre les objets d'exploration de données que vous avez créés en utilisant des scripts DMX (Data Mining Extensions) et ASSL (Analysis Services Scripting Language).</span><span class="sxs-lookup"><span data-stu-id="93998-108">Because [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] uses XMLA for data definition, data manipulation, and data control support, you can create mining structures and mining models by using the visual tools provided by [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], and then extend the data mining objects that you have created by using Data Mining Extensions (DMX) and Analysis Services Scripting Language (ASSL) scripts.</span></span>  
  
     <span data-ttu-id="93998-109">Vous pouvez créer et modifier des objets d'exploration de données entièrement dans des scripts XMLA et exécuter par programme des requêtes de prédiction sur les modèles à partir de vos propres applications.</span><span class="sxs-lookup"><span data-stu-id="93998-109">You can create and modify data mining objects entirely in XMLA scripts, and run prediction queries against the models programmatically from your own applications.</span></span>  
  
-   <span data-ttu-id="93998-110">**Objets AMO (Analysis Management Objects)**</span><span class="sxs-lookup"><span data-stu-id="93998-110">**Analysis Management Objects (AMO)**</span></span>  
  
     [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="93998-111">propose également une infrastructure complète permettant aux fournisseurs d'exploration de données tiers d'intégrer les objets d'exploration de données dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93998-111">also provides a complete framework that enables third-party data mining providers to integrate the data mining objects into [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="93998-112">Créez des structures et des modèles d'exploration de données à l'aide d'AMO.</span><span class="sxs-lookup"><span data-stu-id="93998-112">You can create mining structures and mining models by using AMO.</span></span> <span data-ttu-id="93998-113">Consultez les exemples suivants dans CodePlex :</span><span class="sxs-lookup"><span data-stu-id="93998-113">See the following samples in CodePlex:</span></span>  
  
    -   <span data-ttu-id="93998-114">Navigateur d'indicateur de performance clé (AMO)</span><span class="sxs-lookup"><span data-stu-id="93998-114">AMO Browser</span></span>  
  
         <span data-ttu-id="93998-115">Se connecte à l'instance SSAS spécifiée et répertorie tous les objets serveur et leurs propriétés, notamment la structure d'exploration de données et les modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="93998-115">Connects to the SSAS instance you specify and lists all server objects and their properties, including mining structure and mining models.</span></span>  
  
    -   <span data-ttu-id="93998-116">Exemple AMO simple</span><span class="sxs-lookup"><span data-stu-id="93998-116">AMO Simple Sample</span></span>  
  
         <span data-ttu-id="93998-117">L'exemple AS simple couvre l'accès par programme à la plupart des objets principaux et illustre la navigation dans les métadonnées et l'accès aux valeurs des objets.</span><span class="sxs-lookup"><span data-stu-id="93998-117">The AS Simple Sample covers programmatic access to most major objects, and demonstrates metadata browsing, and access to the values in objects.</span></span>  
  
         <span data-ttu-id="93998-118">L'exemple illustre également la création et le traitement d'une structure et d'un modèle d'exploration de données, et la navigation dans un modèle d'exploration de données existant.</span><span class="sxs-lookup"><span data-stu-id="93998-118">The sample also demonstrates how to create and process a data mining structure and model, as well as browse an existing data mining model.</span></span>  
  
-   <span data-ttu-id="93998-119">**DMR**</span><span class="sxs-lookup"><span data-stu-id="93998-119">**DMX**</span></span>  
  
     <span data-ttu-id="93998-120">Vous pouvez utiliser DMX pour encapsuler des instructions de commande, des requêtes de prédiction et des requêtes de métadonnées, et retourner les résultats dans un format tabulaire, si vous avez créé une connexion à un serveur [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93998-120">You can use DMX to encapsulate command statements, prediction queries, and metadata queries and return results in a tabular format, assuming you have created a connection to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="93998-121">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="93998-121">In This Section</span></span>  
 [<span data-ttu-id="93998-122">OLE DB pour l'exploration de données</span><span class="sxs-lookup"><span data-stu-id="93998-122">OLE DB for Data Mining</span></span>](../../../2014/analysis-services/dev-guide/ole-db-for-data-mining.md)  
 <span data-ttu-id="93998-123">Décrit les ajouts possibles à la spécification de manière à prendre en charge l'exploration de données et les données multidimensionnelles : nouveaux ensembles de lignes et nouvelles colonnes pour les schémas, langage DMX (Data Mining Extension) pour la création et la gestion des structures d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="93998-123">Describes additions to the specification to support data mining and multidimensional data: new schema rowsets and columns, Data Mining Extensions (DMX) language for creating and managing mining structures.</span></span>  
  
## <a name="related-reference"></a><span data-ttu-id="93998-124">Référence connexe</span><span class="sxs-lookup"><span data-stu-id="93998-124">Related Reference</span></span>  
 [<span data-ttu-id="93998-125">Développement avec ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="93998-125">Developing with ADOMD.NET</span></span>](https://docs.microsoft.com/bi-reference/adomd/developing-with-adomd-net)  
 <span data-ttu-id="93998-126">Présente les objets de programmation du client et du serveur ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="93998-126">Introduces ADOMD.NET client and server programming objects.</span></span>  
  
 [<span data-ttu-id="93998-127">Développement avec AMO &#40;Analysis Management Objects&#41;</span><span class="sxs-lookup"><span data-stu-id="93998-127">Developing with Analysis Management Objects &#40;AMO&#41;</span></span>](https://docs.microsoft.com/bi-reference/amo/developing-with-analysis-management-objects-amo)  
 <span data-ttu-id="93998-128">Présente la bibliothèque de programmation AMO.</span><span class="sxs-lookup"><span data-stu-id="93998-128">Introduces the AMO programming library.</span></span>  
  
 [<span data-ttu-id="93998-129">Développement avec le langage de script Analysis Services &#40;ASSL&#41;</span><span class="sxs-lookup"><span data-stu-id="93998-129">Developing with Analysis Services Scripting Language &#40;ASSL&#41;</span></span>](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md)  
 <span data-ttu-id="93998-130">Présente XML for Analysis (XMLA) et ses extensions.</span><span class="sxs-lookup"><span data-stu-id="93998-130">Introduces XML for Analysis (XMLA) and its extensions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93998-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="93998-131">See Also</span></span>  
 <span data-ttu-id="93998-132">[Guide du développeur &#40;Analysis Services&#41;](../analysis-services-developer-documentation.md) </span><span class="sxs-lookup"><span data-stu-id="93998-132">[Developer's Guide &#40;Analysis Services&#41;](../analysis-services-developer-documentation.md) </span></span>  
 [<span data-ttu-id="93998-133">Référence DMX &#40;Data Mining Extensions&#41;</span><span class="sxs-lookup"><span data-stu-id="93998-133">Data Mining Extensions &#40;DMX&#41; Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-reference)  
  
  
