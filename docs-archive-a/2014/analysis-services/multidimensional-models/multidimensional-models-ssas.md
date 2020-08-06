---
title: Modélisation multidimensionnelle (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 509df042-fdb3-4e2c-a6b8-86943ce1b0fc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7348a932eccb62f2e00c0b154ca9efc8086fcd1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710931"
---
# <a name="multidimensional-modeling-ssas"></a><span data-ttu-id="532ff-102">Modélisation multidimensionnelle (SSAS)</span><span class="sxs-lookup"><span data-stu-id="532ff-102">Multidimensional Modeling (SSAS)</span></span>
  <span data-ttu-id="532ff-103">La solution multidimensionnelle Analysis Services utilise des structures de cube pour analyser les données d'entreprise entre plusieurs dimensions.</span><span class="sxs-lookup"><span data-stu-id="532ff-103">An Analysis Services multidimensional solution uses cube structures for analyzing business data across multiple dimensions.</span></span> <span data-ttu-id="532ff-104">Le mode multidimensionnel est le mode serveur par défaut d'Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="532ff-104">Multidimensional mode is the default server mode of Analysis Services.</span></span> <span data-ttu-id="532ff-105">Il inclut une requête et un moteur de calcul pour les données OLAP, avec les modes de stockage MOLAP, ROLAP et HOLAP pour équilibrer les performances par des conditions de données évolutives.</span><span class="sxs-lookup"><span data-stu-id="532ff-105">It includes a query and calculation engine for OLAP data, with MOLAP, ROLAP, and HOLAP storage modes to balance performance with scalable data requirements.</span></span> <span data-ttu-id="532ff-106">Le moteur OLAP d'Analysis Services est un serveur OLAP leader de l'industrie qui fonctionne parfaitement avec de nombreux outils BI.</span><span class="sxs-lookup"><span data-stu-id="532ff-106">The Analysis Services OLAP engine is an industry leading OLAP server that works well with a broad range of BI tools.</span></span> <span data-ttu-id="532ff-107">La plupart des déploiements Analysis Services sont installés comme des serveurs OLAP classiques.</span><span class="sxs-lookup"><span data-stu-id="532ff-107">Most Analysis Services deployments are installed as classic OLAP servers.</span></span>  
  
## <a name="benefits-of-using-multidimensional-solutions"></a><span data-ttu-id="532ff-108">Avantages de l'utilisation des solutions multidimensionnelles</span><span class="sxs-lookup"><span data-stu-id="532ff-108">Benefits of Using Multidimensional Solutions</span></span>  
 <span data-ttu-id="532ff-109">La raison première de générer un modèle multidimensionnel Analysis Services est d'accélérer les performances des requêtes ad hoc sur des données d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="532ff-109">The primary reason for building an Analysis Services multidimensional model is to achieve fast performance of ad hoc queries against business data.</span></span> <span data-ttu-id="532ff-110">Un modèle multidimensionnel est composé de cubes et de dimensions qui peuvent être annotés et étendus pour prendre en charge des constructions de requêtes complexes.</span><span class="sxs-lookup"><span data-stu-id="532ff-110">A multidimensional model is composed of cubes and dimensions that can be annotated and extended to support complex query constructions.</span></span> <span data-ttu-id="532ff-111">Les développeurs BI créent des cubes pour accélérer les temps de réponse et fournir une seule source de données pour les rapports d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="532ff-111">BI developers create cubes to support fast response times, and to provide a single data source for business reporting.</span></span> <span data-ttu-id="532ff-112">Étant donné l'importance croissante des solutions décisionnelles à tous les niveaux d'une organisation, le fait d'avoir une seule source de données analytiques garantit que les anomalies sont limitées au minimum faute de pouvoir les éliminer entièrement.</span><span class="sxs-lookup"><span data-stu-id="532ff-112">Given the growing importance of business intelligence across all levels of an organization, having a single source of analytical data ensures that discrepancies are kept to a minimum, if not eliminated entirely.</span></span>  
  
 <span data-ttu-id="532ff-113">Un autre avantage procuré par les bases de données multidimensionnelles Analysis Services est l'intégration avec les outils de création de rapports BI couramment utilisés tels qu'Excel, Reporting Services et PerformancePoint, ainsi que des application personnalisées et des solutions tierces.</span><span class="sxs-lookup"><span data-stu-id="532ff-113">Another important benefit to using Analysis Services multidimensional databases is integration with commonly used BI reporting tools such as Excel, Reporting Services, and PerformancePoint, as well as custom applications and third-party solutions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="532ff-114">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="532ff-114">In This Section</span></span>  
 [<span data-ttu-id="532ff-115">Solutions de modèles multidimensionnels &#40;SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="532ff-115">Multidimensional Model Solutions &#40;SSAS&#41;</span></span>](multidimensional-model-solutions-ssas.md)  
  
 [<span data-ttu-id="532ff-116">Bases de données de modèle multidimensionnel &#40;SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="532ff-116">Multidimensional Model Databases &#40;SSAS&#41;</span></span>](multidimensional-model-databases-ssas.md)  
  
 [<span data-ttu-id="532ff-117">Traitement des objets de modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="532ff-117">Multidimensional Model Object Processing</span></span>](processing-a-multidimensional-model-analysis-services.md)  
  
 [<span data-ttu-id="532ff-118">Rôles et autorisations &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="532ff-118">Roles and Permissions &#40;Analysis Services&#41;</span></span>](roles-and-permissions-analysis-services.md)  
  
 [<span data-ttu-id="532ff-119">Power View pour les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="532ff-119">Power View for Multidimensional Models</span></span>](power-view-for-multidimensional-models.md)  
  
 [<span data-ttu-id="532ff-120">Gestion des assemblys de modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="532ff-120">Multidimensional Model Assemblies Management</span></span>](multidimensional-model-assemblies-management.md)  
  
  
