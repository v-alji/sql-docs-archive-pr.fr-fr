---
title: Architecture d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 105f52e1-ad3b-4cd0-b67b-06dbb451c304
author: minewiskan
ms.author: owend
ms.openlocfilehash: a372972fd7fa39f7bcfd2e10abbc4fbf8f8c10aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613225"
---
# <a name="data-mining-architecture"></a><span data-ttu-id="3e2d1-102">Architecture d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="3e2d1-102">Data Mining Architecture</span></span>
  <span data-ttu-id="3e2d1-103">Cette section décrit l'architecture des solutions d'exploration de données qui sont hébergées dans une instance d' [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e2d1-103">This section describes the architecture of data mining solutions that are hosted in an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="3e2d1-104">Les rubriques de cette section décrivent l'architecture logique et physique d'une instance d' [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] qui prend en charge l'exploration de données, et fournissent également des informations sur les clients, les fournisseurs et les protocoles qui peuvent être utilisés pour communiquer avec des serveurs d'exploration de données, et pour utiliser des objets d'exploration de données localement ou à distance.</span><span class="sxs-lookup"><span data-stu-id="3e2d1-104">The topics in this section describe the logical and physical architecture of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance that supports data mining, and also provide information about the clients, providers, and protocols that can be used to communicate with data mining servers, and to work with data mining objects either locally or remotely.</span></span>  
  
 <span data-ttu-id="3e2d1-105">En général, l'exploration de données SQL Server fonctionne en tant que service fourni dans le cadre d'une instance d' [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] exécutée en mode multidimensionnel ; par conséquent, nous vous recommandons de consulter également les sections de la documentation en ligne suivantes qui décrivent le fonctionnement, la maintenance et la configuration des solutions multidimensionnelles d' [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3e2d1-105">In general, SQL Server Data Mining operates as a service that is provided as part of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance running in multidimensional mode; therefore, we recommend that you also review the following sections of Books Online that describe the operation, maintenance, and configuration of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] multidimensional solutions.</span></span>  
  
 [<span data-ttu-id="3e2d1-106">Traitement des objets de modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="3e2d1-106">Multidimensional Model Object Processing</span></span>](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md)  
  
 [<span data-ttu-id="3e2d1-107">Se connecter à Analysis Services</span><span class="sxs-lookup"><span data-stu-id="3e2d1-107">Connect to Analysis Services</span></span>](../instances/connect-to-analysis-services.md)  
  
 [<span data-ttu-id="3e2d1-108">Emplacement de stockage de la base de données</span><span class="sxs-lookup"><span data-stu-id="3e2d1-108">Database Storage Location</span></span>](../multidimensional-models/database-storage-location.md)  
  
 [<span data-ttu-id="3e2d1-109">Basculer une base de données Analysis Services entre les modes ReadOnly et ReadWrite</span><span class="sxs-lookup"><span data-stu-id="3e2d1-109">Switch an Analysis Services database between ReadOnly and ReadWrite modes</span></span>](../multidimensional-models/switch-an-analysis-services-database-between-readonly-and-readwrite-modes.md)  
  
 <span data-ttu-id="3e2d1-110">Pour plus d'informations sur la façon dont vous pouvez implémenter l'exploration de données dans votre solution décisionnelle, consultez la section relative aux guides de solutions de MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="3e2d1-110">For more information about how you can implement data mining in your business intelligence solution, see the Solution Guides section of the MSDN Library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3e2d1-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="3e2d1-111">In This Section</span></span>  
 [<span data-ttu-id="3e2d1-112">Architecture logique &#40;Analysis Services - Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3e2d1-112">Logical Architecture &#40;Analysis Services - Data Mining&#41;</span></span>](logical-architecture-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="3e2d1-113">Architecture physique &#40;Analysis Services - Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3e2d1-113">Physical Architecture &#40;Analysis Services - Data Mining&#41;</span></span>](physical-architecture-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="3e2d1-114">Services d'exploration de données et sources de données</span><span class="sxs-lookup"><span data-stu-id="3e2d1-114">Data Mining Services and Data Sources</span></span>](data-mining-services-and-data-sources.md)  
  
 [<span data-ttu-id="3e2d1-115">Gestion des solutions et des objets d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="3e2d1-115">Management of Data Mining Solutions and Objects</span></span>](management-of-data-mining-solutions-and-objects.md)  
  
 [<span data-ttu-id="3e2d1-116">Vue d’ensemble de la sécurité &#40;exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3e2d1-116">Security Overview &#40;Data Mining&#41;</span></span>](security-overview-data-mining.md)  
  
## <a name="see-also"></a><span data-ttu-id="3e2d1-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3e2d1-117">See Also</span></span>  
 <span data-ttu-id="3e2d1-118">[Programmation de modèles multidimensionnels](../multidimensional-models/multidimensional-model-programming.md) </span><span class="sxs-lookup"><span data-stu-id="3e2d1-118">[Multidimensional Model Programming](../multidimensional-models/multidimensional-model-programming.md) </span></span>  
 [<span data-ttu-id="3e2d1-119">Programmation de l’exploration de données</span><span class="sxs-lookup"><span data-stu-id="3e2d1-119">Data Mining Programming</span></span>](../dev-guide/data-mining-programming.md)  
  
  
