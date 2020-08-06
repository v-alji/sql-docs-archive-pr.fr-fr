---
title: Programmation du serveur ADOMD.NET | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- programming [ADOMD.NET]
- ADOMD.NET, programming
ms.assetid: 7f7ff5be-3826-43a5-b94d-ddeec5ddb2eb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 522478af0b19f1745d80f167e40345d4751136b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694799"
---
# <a name="adomdnet-server-programming"></a><span data-ttu-id="3b708-102">Programmation du serveur ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="3b708-102">ADOMD.NET Server Programming</span></span>
  <span data-ttu-id="3b708-103">Les composants serveur d'ADOMD.NET résident dans l'espace de noms `Microsoft.AnalysisServices.AdomdServer` (dans msmgdsrv.dll).</span><span class="sxs-lookup"><span data-stu-id="3b708-103">The ADOMD.NET server components of ADOMD.NET reside within the `Microsoft.AnalysisServices.AdomdServer` namespace (in msmgdsrv.dll).</span></span> <span data-ttu-id="3b708-104">Vous utilisez ces composants serveur pour créer des fonctions MDX (Multidimensional Expressions) personnalisées et des procédures stockées qui sont exécutées sur une instance de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3b708-104">You use these server components to create custom Multidimensional Expressions (MDX) functions and stored procedures that are run on an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="3b708-105">Les objets serveur permettent d'interroger les cubes et les modèles d'exploration de données et d'évaluer des expressions dans un contexte donné.</span><span class="sxs-lookup"><span data-stu-id="3b708-105">The server objects provide the capabilities for querying cubes and mining models, and for evaluating expressions in a given context.</span></span> <span data-ttu-id="3b708-106">La création de fonctions personnalisées et de procédures stockées offrent les avantages d'une exécution rapide, d'un déploiement centralisé et d'une facilité de maintenance améliorée.</span><span class="sxs-lookup"><span data-stu-id="3b708-106">The benefits for creating custom functions and stored procedures include fast execution, centralized deployment, and improved maintainability.</span></span>  
  
 <span data-ttu-id="3b708-107">Les rubriques mentionnées dans le tableau suivant vous aideront à développer des applications serveur ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="3b708-107">The topics in the following table will help you develop ADOMD.NET server applications.</span></span>  
  
|<span data-ttu-id="3b708-108">Rubrique</span><span class="sxs-lookup"><span data-stu-id="3b708-108">Topic</span></span>|<span data-ttu-id="3b708-109">Description</span><span class="sxs-lookup"><span data-stu-id="3b708-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="3b708-110">Fonctionnalités serveur ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="3b708-110">ADOMD.NET Server Functionality</span></span>](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-server/adomd-net-server-functionality)|<span data-ttu-id="3b708-111">Décrit les différentes utilisations d'objets serveur ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="3b708-111">Describes the uses for ADOMD.NET server objects.</span></span>|  
|[<span data-ttu-id="3b708-112">Architecture des objets serveur ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="3b708-112">ADOMD.NET Server Object Architecture</span></span>](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-server/adomd-net-server-object-architecture)|<span data-ttu-id="3b708-113">Décrit l'architecture objet des objets serveur ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="3b708-113">Describes the object architecture for ADOMD.NET server objects.</span></span>|  
|[<span data-ttu-id="3b708-114">Fonctions définies par l'utilisateur et procédures stockées</span><span class="sxs-lookup"><span data-stu-id="3b708-114">User Defined Functions and Stored Procedures</span></span>](https://docs.microsoft.com/analysis-services/adomd/multidimensional-models-adomd-net-server/user-defined-functions-and-stored-procedures)|<span data-ttu-id="3b708-115">Présente le processus de création d'une fonction définie par l'utilisateur ou d'une procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="3b708-115">Walks you through the process of creating a user defined function or stored Procedure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3b708-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3b708-116">See Also</span></span>  
 <span data-ttu-id="3b708-117">[Programmation du client ADOMD.NET](https://docs.microsoft.com/analysis-services/adomd/multidimensional-models-adomd-net-client/adomd-net-client-programming) </span><span class="sxs-lookup"><span data-stu-id="3b708-117">[ADOMD.NET Client Programming](https://docs.microsoft.com/analysis-services/adomd/multidimensional-models-adomd-net-client/adomd-net-client-programming) </span></span>  
 [<span data-ttu-id="3b708-118">Développement avec ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="3b708-118">Developing with ADOMD.NET</span></span>](https://docs.microsoft.com/bi-reference/adomd/developing-with-adomd-net)  
  
  
