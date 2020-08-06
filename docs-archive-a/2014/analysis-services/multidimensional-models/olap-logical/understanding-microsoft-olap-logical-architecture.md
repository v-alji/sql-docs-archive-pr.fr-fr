---
title: Architecture logique (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Analysis Services, architecture
- logical architecture [Analysis Services Multidimensional Data]
ms.assetid: 1b9cae0a-8990-4194-af5f-a1ea5f2aff06
author: minewiskan
ms.author: owend
ms.openlocfilehash: d93361fb14bc6544ffa7376439c2da0c8e06c3fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612554"
---
# <a name="logical-architecture-analysis-services---multidimensional-data"></a><span data-ttu-id="22a39-102">Architecture logique (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="22a39-102">Logical Architecture (Analysis Services - Multidimensional Data)</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="22a39-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] utilise des composants serveur et client pour fournir des fonctionnalités de traitement analytique en ligne (OLAP) et d’exploration de données pour les applications décisionnelles :</span><span class="sxs-lookup"><span data-stu-id="22a39-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] uses both server and client components to supply online analytical processing (OLAP) and data mining functionality for business intelligence applications:</span></span>  
  
-   <span data-ttu-id="22a39-104">Le composant serveur d'[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] est implémenté comme un service Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="22a39-104">The server component of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] is implemented as a Microsoft Windows service.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="22a39-105">[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]prend en charge plusieurs instances sur le même ordinateur, chaque instance de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] étant implémentée en tant qu’instance distincte du service Windows.</span><span class="sxs-lookup"><span data-stu-id="22a39-105">[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] supports multiple instances on the same computer, with each instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] implemented as a separate instance of the Windows service.</span></span>  
  
-   <span data-ttu-id="22a39-106">Les clients communiquent avec [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] à l’aide de la norme publique XMLA (XML for Analysis), un protocole SOAP qui permet d’émettre des commandes et de recevoir des réponses, exposée en tant que service web.</span><span class="sxs-lookup"><span data-stu-id="22a39-106">Clients communicate with [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] using the public standard XML for Analysis (XMLA), a SOAP-based protocol for issuing commands and receiving responses, exposed as a Web service.</span></span> <span data-ttu-id="22a39-107">Des modèles objet clients sont aussi fournis via XMLA, et sont accessibles soit à l'aide d'un fournisseur managé, notamment ADOMD.NET ou un fournisseur OLE DB natif.</span><span class="sxs-lookup"><span data-stu-id="22a39-107">Client object models are also provided over XMLA, and can be accessed either by using a managed provider, such as ADOMD.NET, or a native OLE DB provider.</span></span>  
  
-   <span data-ttu-id="22a39-108">Les commandes de requête peuvent être émises à l'aide des langages suivants : SQL, MDX (Multidimensional Expressions), un langage de requête standard orienté analyse ou DMX (Data Mining Extensions), un langage de requête standard orienté exploration de données.</span><span class="sxs-lookup"><span data-stu-id="22a39-108">Query commands can be issued using the following languages: SQL; Multidimensional Expressions (MDX), an industry standard query language for analysis; or Data Mining Extensions (DMX), an industry standard query language oriented toward data mining.</span></span> <span data-ttu-id="22a39-109">Vous pouvez aussi utiliser ASSL (Analysis Services Scripting Language) pour gérer les objets de la base de données [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="22a39-109">Analysis Services Scripting Language (ASSL) can also be used to manage [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] database objects.</span></span>  
  
 [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="22a39-110">prend également en charge un moteur de cube local qui permet aux applications exécutées sur des clients déconnectés de parcourir les données multidimensionnelles stockées localement.</span><span class="sxs-lookup"><span data-stu-id="22a39-110">also supports a local cube engine that enables applications on disconnected clients to browse locally stored multidimensional data.</span></span> <span data-ttu-id="22a39-111">Pour plus d’informations, consultez [Configuration requise de l’architecture client pour le développement de Analysis Services](../olap-physical/client-architecture-requirements-for-analysis-services-development.md)</span><span class="sxs-lookup"><span data-stu-id="22a39-111">For more information, see [Client Architecture Requirements for Analysis Services Development](../olap-physical/client-architecture-requirements-for-analysis-services-development.md)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="22a39-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="22a39-112">In This Section</span></span>  
 <span data-ttu-id="22a39-113">**Vue d'ensemble de l'architecture logique**</span><span class="sxs-lookup"><span data-stu-id="22a39-113">**Logical Architecture Overview**</span></span>  
 [<span data-ttu-id="22a39-114">Vue d’ensemble de l’architecture logique &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="22a39-114">Logical Architecture Overview &#40;Analysis Services - Multidimensional Data&#41;</span></span>](logical-architecture-overview-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="22a39-115">**Objets serveur**</span><span class="sxs-lookup"><span data-stu-id="22a39-115">**Server Objects**</span></span>  
 [<span data-ttu-id="22a39-116">Objets serveur &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="22a39-116">Server Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](server-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="22a39-117">**Objets de base de données**</span><span class="sxs-lookup"><span data-stu-id="22a39-117">**Database Objects**</span></span>  
 [<span data-ttu-id="22a39-118">Objets de bases de données &#40;Analysis Services – Données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="22a39-118">Database Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](database-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="22a39-119">**Objets Dimension**</span><span class="sxs-lookup"><span data-stu-id="22a39-119">**Dimension Objects**</span></span>  
 [<span data-ttu-id="22a39-120">Objets de dimension &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="22a39-120">Dimension Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-dimension-objects/dimension-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="22a39-121">**Objets de cube**</span><span class="sxs-lookup"><span data-stu-id="22a39-121">**Cube Objects**</span></span>  
 [<span data-ttu-id="22a39-122">Objets de cube &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="22a39-122">Cube Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="22a39-123">**Sécurité de l'accès utilisateur**</span><span class="sxs-lookup"><span data-stu-id="22a39-123">**User Access Security**</span></span>  
 [<span data-ttu-id="22a39-124">Architecture de sécurité de l'accès utilisateur</span><span class="sxs-lookup"><span data-stu-id="22a39-124">User Access Security Architecture</span></span>](understanding-microsoft-olap-logical-architecture.md)  
  
## <a name="see-also"></a><span data-ttu-id="22a39-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="22a39-125">See Also</span></span>  
 <span data-ttu-id="22a39-126">[Compréhension de l’architecture Microsoft OLAP](../olap-physical/understanding-microsoft-olap-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="22a39-126">[Understanding Microsoft OLAP Architecture](../olap-physical/understanding-microsoft-olap-architecture.md) </span></span>  
 [<span data-ttu-id="22a39-127">Architecture physique &#40;Analysis Services - Données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="22a39-127">Physical Architecture &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../olap-physical/understanding-microsoft-olap-physical-architecture.md)  
  
  
