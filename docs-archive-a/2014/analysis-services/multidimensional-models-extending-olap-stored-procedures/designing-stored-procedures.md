---
title: Conception de procédures stockées | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- stored procedures [Analysis Services], designing
- dependent assemblies [Analysis Services]
- assemblies [Analysis Services]
ms.assetid: af4e7bd5-041b-4a40-9942-0ef6a3af46c6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 42b33873d6bdf28f7f702bcf186d681f57d6024d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700428"
---
# <a name="designing-stored-procedures"></a><span data-ttu-id="37fd5-102">Conception des procédures stockées</span><span class="sxs-lookup"><span data-stu-id="37fd5-102">Designing Stored Procedures</span></span>
  <span data-ttu-id="37fd5-103">Le modèle objet administratif AMO (Analysis Management Objects) et le modèle objet orienté client ([!INCLUDE[msCoName](../../includes/msconame-md.md)] ADO (ActiveX® Data Objects) MD (Multidimensional)) sont disponibles dans les procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="37fd5-103">Both the administrative object model Analysis Management Objects (AMO) and the client oriented object model [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX® Data Objects (Multidimensional) (ADO MD) are available in stored procedures.</span></span>  
  
 <span data-ttu-id="37fd5-104">Les procédures stockées doivent être dans la portée (le serveur ou la base de données) afin d'être visibles au niveau MDX (Multidimensional Expressions) pour être appelées.</span><span class="sxs-lookup"><span data-stu-id="37fd5-104">Stored procedures must be in scope (either the server or the database) to be visible at the Multidimensional Expressions (MDX) level to be called.</span></span> <span data-ttu-id="37fd5-105">Toutefois, lorsqu'une procédure stockée est appelée, sa portée ne se limite pas aux actions effectuées sous son parent.</span><span class="sxs-lookup"><span data-stu-id="37fd5-105">However, once a stored procedure is invoked, its scope is not limited to actions under its parent.</span></span> <span data-ttu-id="37fd5-106">Une procédure stockée peut effectuer des modifications n'importe où sur le serveur ; elle est juste astreinte à respecter les limites de sécurité du processus utilisateur qui l'appelle ou les limites de la transaction dans laquelle elle fonctionne.</span><span class="sxs-lookup"><span data-stu-id="37fd5-106">A stored procedure may make changes or modifications anywhere on the server, subject only to the security limitations of the user process that invokes it or to the limitations of the transaction in which it is operating.</span></span>  
  
 <span data-ttu-id="37fd5-107">Les procédures de portée du serveur sont disponibles dans tous les contextes du serveur.</span><span class="sxs-lookup"><span data-stu-id="37fd5-107">Server scope procedures are available in all contexts on the server.</span></span> <span data-ttu-id="37fd5-108">Les procédures stockées de portée de base de données sont uniquement visibles dans le contexte de la base de données dans laquelle elles sont définies.</span><span class="sxs-lookup"><span data-stu-id="37fd5-108">Database scope stored procedures are visible only in the database context of the database in which they are defined.</span></span>  
  
 <span data-ttu-id="37fd5-109">Comme pour toute fonction MDX, une procédure stockée doit être résolue pour qu'une session MDX puisse continuer ; les procédures stockées bloquent les sessions MDX pendant leur exécution.</span><span class="sxs-lookup"><span data-stu-id="37fd5-109">As with any MDX function, stored procedure must be resolved before an MDX session can continue; stored procedures lock MDX sessions while executing.</span></span> <span data-ttu-id="37fd5-110">Sauf si une raison spécifique justifie l'arrêt d'une session MDX dans l'attente d'une intervention de l'utilisateur, il est fortement recommandé d'éviter toute interaction de ce type (telle qu'une boîte de dialogue par exemple).</span><span class="sxs-lookup"><span data-stu-id="37fd5-110">Unless a specific reason exists to halt an MDX session pending user interaction, then user interactions (such as dialog boxes) are discouraged.</span></span>  
  
## <a name="dependent-assemblies"></a><span data-ttu-id="37fd5-111">Assemblys dépendants</span><span class="sxs-lookup"><span data-stu-id="37fd5-111">Dependent Assemblies</span></span>  
 <span data-ttu-id="37fd5-112">Tous les assemblys dépendants doivent être chargés dans une instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que le Common Language Runtime (CLR) doit trouver.</span><span class="sxs-lookup"><span data-stu-id="37fd5-112">All dependent assemblies must be loaded into an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to be found by the common language runtime (CLR).</span></span> [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="37fd5-113">stocke les assemblys dépendants dans le même dossier que l'assembly principal, afin que le CLR résolve automatiquement toutes les références de fonction à des fonctions de ces assemblys.</span><span class="sxs-lookup"><span data-stu-id="37fd5-113">stores the dependent assemblies in the same folder as the main assembly, so the CLR automatically resolves all function references to functions in those assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37fd5-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="37fd5-114">See Also</span></span>  
 <span data-ttu-id="37fd5-115">[Gestion des assemblys de modèles multidimensionnels](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="37fd5-115">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="37fd5-116">Définition de procédures stockées</span><span class="sxs-lookup"><span data-stu-id="37fd5-116">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
