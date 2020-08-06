---
title: Extension d’OLAP par le biais de personnalisations | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Analysis Services, extensibility
ms.assetid: 348e49fc-4390-43c1-9b6c-61b386ff4373
author: minewiskan
ms.author: owend
ms.openlocfilehash: 93669980e989b1cb11673f45c111de3609bbe920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708755"
---
# <a name="extending-olap-through-personalizations"></a><span data-ttu-id="d732e-102">Extension d'OLAP par des personnalisations</span><span class="sxs-lookup"><span data-stu-id="d732e-102">Extending OLAP through personalizations</span></span>
  <span data-ttu-id="d732e-103">Microsoft [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] fournit de nombreuses fonctions intrinsèques à utiliser avec les langages MDX (Multidimensional Expressions) et DMX (Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="d732e-103">Microsoft  [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] supplies many intrinsic functions for use with the Multidimensional Expressions (MDX) and Data Mining Extensions (DMX) languages.</span></span> <span data-ttu-id="d732e-104">Ces fonctions sont conçues pour accomplir toutes les opérations possibles, depuis les calculs statistiques standard jusqu'au parcours des membres d'une hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="d732e-104">These functions are designed to accomplish everything from standard statistical calculations to traversing members in a hierarchy.</span></span> <span data-ttu-id="d732e-105">Cependant, comme avec tout autre produit complexe et puissant, il est toujours nécessaire d'étendre les fonctionnalités de ce type d'outil.</span><span class="sxs-lookup"><span data-stu-id="d732e-105">However, as with any other complex and robust product, there is always the need to extend the functionality of such a product further.</span></span>  
  
 <span data-ttu-id="d732e-106">Par conséquent, Analysis Services vous permet d'ajouter des assemblys et des extensions personnalisées à une instance du service, afin de répondre aux besoins de votre entreprise chaque fois que les fonctionnalités standard sont insuffisantes.</span><span class="sxs-lookup"><span data-stu-id="d732e-106">Therefore, Analysis Services provides you with the ability to add assemblies and personalized extensions to an instance of the service, in order to complete your business needs whenever the standard functionality is not enough.</span></span>  
  
## <a name="assemblies"></a><span data-ttu-id="d732e-107">Assemblys</span><span class="sxs-lookup"><span data-stu-id="d732e-107">Assemblies</span></span>  
 <span data-ttu-id="d732e-108">Les assemblys vous permettent d'étendre les fonctions d'entreprise de MDX et de DMX.</span><span class="sxs-lookup"><span data-stu-id="d732e-108">Assemblies enable you to extend the business functionality of MDX and DMX.</span></span> <span data-ttu-id="d732e-109">Vous générez les fonctionnalités souhaitées dans une bibliothèque, telle qu'une bibliothèque de liens dynamiques (DLL), puis vous ajoutez cette bibliothèque en tant qu'assembly à une instance d'Analysis Services ou à une base de données Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="d732e-109">You build the functionality that you want into a library, such as a dynamic link library (DLL), then add the library as an assembly to an instance of Analysis Services or to an Analysis Services database.</span></span> <span data-ttu-id="d732e-110">Les méthodes publiques de la bibliothèque sont alors exposées en tant que fonctions définies par l'utilisateur aux expressions, procédures, calculs, actions et applications clientes MDX et DMX.</span><span class="sxs-lookup"><span data-stu-id="d732e-110">The public methods in the library are then exposed as user-defined functions to MDX and DMX expressions, procedures, calculations, actions, and client applications.</span></span>  
  
## <a name="personalized-extensions"></a><span data-ttu-id="d732e-111">Extensions personnalisées</span><span class="sxs-lookup"><span data-stu-id="d732e-111">Personalized Extensions</span></span>  
 <span data-ttu-id="d732e-112">Les extensions de personnalisation SQL Server Analysis Services sont la base de l'idée d'implémentation d'une architecture de plug-in.</span><span class="sxs-lookup"><span data-stu-id="d732e-112">SQL Server Analysis Services personalization extensions are the foundation of the idea of implementing a plug-in architecture.</span></span> <span data-ttu-id="d732e-113">Analysis Services extensions de personnalisation sont une modification simple et élégante de l’architecture d’assembly managée existante et sont exposées dans le modèle d’objet Analysis Services [Microsoft. AnalysisServices. AdomdServer](/previous-versions/sql/sql-server-2014/ms131779(v=sql.120)) , la syntaxe MDX (Multidimensional Expressions) et les ensembles de lignes de schéma.</span><span class="sxs-lookup"><span data-stu-id="d732e-113">Analysis Services personalization extensions are a simple and elegant modification to the existing managed assembly architecture and are exposed throughout the Analysis Services [Microsoft.AnalysisServices.AdomdServer](/previous-versions/sql/sql-server-2014/ms131779(v=sql.120)) object model, Multidimensional Expressions (MDX) syntax, and schema rowsets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d732e-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d732e-114">See Also</span></span>  
 <span data-ttu-id="d732e-115">[Gestion des assemblys de modèles multidimensionnels](../multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="d732e-115">[Multidimensional Model Assemblies Management](../multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="d732e-116">Extensions de personnalisation Analysis Services</span><span class="sxs-lookup"><span data-stu-id="d732e-116">Analysis Services Personalization Extensions</span></span>](analysis-services-personalization-extensions.md)  
  
  
