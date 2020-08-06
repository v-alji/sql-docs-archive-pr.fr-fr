---
title: Programmation de modèles tabulaires | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 0ceb461e-12c1-44ea-97ac-b99bf308676b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2565ed28a882750ab9b37beadbce698d3a0abb19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710839"
---
# <a name="tabular-model-programming"></a><span data-ttu-id="d4fd7-102">Programmation de modèle tabulaire</span><span class="sxs-lookup"><span data-stu-id="d4fd7-102">Tabular Model Programming</span></span>
  <span data-ttu-id="d4fd7-103">Les modèles tabulaires utilisent des constructions relationnelles pour modéliser les données Analysis Services utilisées par les applications analytiques et de rapports.</span><span class="sxs-lookup"><span data-stu-id="d4fd7-103">Tabular models use relational constructs to model the Analysis Services data used by analytical and reporting applications.</span></span> <span data-ttu-id="d4fd7-104">Ces modèles s'exécutent sur une instance Analysis Service qui est configurée pour le mode tabulaire, en utilisant un moteur d'analyse en mémoire pour le stockage et les analyses de table rapides qui agrègent et calculent des données à mesure qu'elles sont demandées.</span><span class="sxs-lookup"><span data-stu-id="d4fd7-104">These models run on an Analysis Service instance that is configured for tabular mode, using an in-memory analytics engine for storage and fast table scans that aggregate and calculate data as it is requested.</span></span>  
  
 <span data-ttu-id="d4fd7-105">Par programme, les objets que vous utilisez dans AMO, ADOMD.NET, XMLA, ou OLE DB sont fondamentalement les mêmes pour des solutions tabulaires et multidimensionnelles.</span><span class="sxs-lookup"><span data-stu-id="d4fd7-105">Programmatically, the objects you work with in AMO, ADOMD.NET, XMLA, or OLE DB are fundamentally the same for both tabular and multidimensional solutions.</span></span> <span data-ttu-id="d4fd7-106">Si les besoins de votre solution BI personnalisée sont mieux remplis par une base de données de modèles tabulaires, vous pouvez utiliser l'une des bibliothèques Analysis Services et interfaces de programmation clientes pour intégrer votre application à des modèles tabulaires sur une instance Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="d4fd7-106">If the requirements of your custom BI solution are best met by a tabular model database, you can use any of the Analysis Services client libraries and programming interfaces to integrate your application with tabular models on an Analysis Services instance.</span></span> <span data-ttu-id="d4fd7-107">Pour interroger et calculer des données de modèle tabulaire, vous pouvez utiliser MDX ou DAX incorporé dans votre code.</span><span class="sxs-lookup"><span data-stu-id="d4fd7-107">To query and calculate tabular model data, you can use either embedded MDX or DAX in your code.</span></span>  
  
 <span data-ttu-id="d4fd7-108">Cette section fournit plus d'informations sur la façon dont vous pouvez programmer ces entités de modèle tabulaire et leurs propriétés.</span><span class="sxs-lookup"><span data-stu-id="d4fd7-108">This section provides more information about how you can programmatically work with tabular model entities and their properties.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d4fd7-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="d4fd7-109">In This Section</span></span>  
 [<span data-ttu-id="d4fd7-110">Annotations CSDL pour Business Intelligence &#40;CSDLBI&#41;</span><span class="sxs-lookup"><span data-stu-id="d4fd7-110">CSDL Annotations for Business Intelligence &#40;CSDLBI&#41;</span></span>](/analysis-services/csdlbi/csdl-annotations-for-business-intelligence-csdlbi)  
  
 [<span data-ttu-id="d4fd7-111">Présentation du modèle d'objet tabulaire</span><span class="sxs-lookup"><span data-stu-id="d4fd7-111">Understanding the Tabular Object Model</span></span>](representation/understanding-tabular-object-model-at-levels-1050-through-1103.md)  
  
 [<span data-ttu-id="d4fd7-112">Informations techniques de référence sur les annotations pour le décisionnel dans CSDL</span><span class="sxs-lookup"><span data-stu-id="d4fd7-112">Technical Reference for BI Annotations to CSDL</span></span>](/analysis-services/csdlbi/technical-reference-for-bi-annotations-to-csdl)  
  
 [<span data-ttu-id="d4fd7-113">Interface IMDEmbedded</span><span class="sxs-lookup"><span data-stu-id="d4fd7-113">IMDEmbedded Interface</span></span>](imdembeddeddata-interface.md)  
  
## <a name="see-also"></a><span data-ttu-id="d4fd7-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d4fd7-114">See Also</span></span>  
 <span data-ttu-id="d4fd7-115">[Modélisation tabulaire &#40;la&#41;tabulaire SSAS](../tabular-models/tabular-models-ssas.md) </span><span class="sxs-lookup"><span data-stu-id="d4fd7-115">[Tabular Modeling &#40;SSAS Tabular&#41;](../tabular-models/tabular-models-ssas.md) </span></span>  
 [<span data-ttu-id="d4fd7-116">Concepteur de modèles tabulaires &#40;&#41;SSAS tabulaire</span><span class="sxs-lookup"><span data-stu-id="d4fd7-116">Tabular Model Designer &#40;SSAS Tabular&#41;</span></span>](../tabular-model-designer-ssas-tabular.md)  
  
  
