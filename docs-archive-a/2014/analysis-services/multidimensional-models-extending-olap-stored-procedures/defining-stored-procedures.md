---
title: Définition des procédures stockées | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- stored procedures [Analysis Services]
- OLAP [Analysis Services], stored procedures
- external routines [Analysis Services]
- stored procedures [Analysis Services], about stored procedures
ms.assetid: f9c57d91-f60f-4f0e-8f7f-d87f4ba97b7c
author: minewiskan
ms.author: owend
ms.openlocfilehash: cc1f028f822d2289ee79702feb2494487040977c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700427"
---
# <a name="defining-stored-procedures"></a><span data-ttu-id="c212d-102">Définition de procédures stockées</span><span class="sxs-lookup"><span data-stu-id="c212d-102">Defining Stored Procedures</span></span>
  <span data-ttu-id="c212d-103">Vous pouvez utiliser des procédures stockées pour appeler des routines externes à partir de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c212d-103">You can use stored procedures to call external routines from [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="c212d-104">Vous pouvez écrire les routines externes appelées par une procédure stockée dans n'importe quel langage CLR (Common Language Runtime), comme C, C++, C#, Visual Basic ou Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="c212d-104">You can write an external routines called by a stored procedure in any common language runtime (CLR) language, such as C, C++, C#, Visual Basic, or Visual Basic .NET.</span></span> <span data-ttu-id="c212d-105">Une procédure stockée peut être créée une fois et être ensuite appelée à partir de nombreux contextes, par exemple par d'autres procédures stockées, par des mesures calculées ou par des applications clientes.</span><span class="sxs-lookup"><span data-stu-id="c212d-105">A stored procedure can be created once and called from many contexts, such as other stored procedures, calculated measures, or client applications.</span></span> <span data-ttu-id="c212d-106">Les procédures stockées simplifient le développement et l'implémentation des bases de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en permettant de développer une fois du code commun et de le stoker dans un emplacement unique.</span><span class="sxs-lookup"><span data-stu-id="c212d-106">Stored procedures simplify [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database development and implementation by allowing common code to be developed once and stored in a single location.</span></span> <span data-ttu-id="c212d-107">Les procédures stockées peuvent être utilisées pour ajouter à vos applications des fonctionnalités métier qui ne sont pas fournies par les fonctionnalités natives de MDX.</span><span class="sxs-lookup"><span data-stu-id="c212d-107">Stored procedures can be used to add business functionality to your applications that is not provided by the native functionality of MDX.</span></span>  
  
 <span data-ttu-id="c212d-108">Cette section contient les informations nécessaires pour comprendre, concevoir et mettre en œuvre des procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="c212d-108">This section provides the information necessary to understand, design, and implement stored procedures.</span></span>  
  
|<span data-ttu-id="c212d-109">Rubrique</span><span class="sxs-lookup"><span data-stu-id="c212d-109">Topic</span></span>|<span data-ttu-id="c212d-110">Description</span><span class="sxs-lookup"><span data-stu-id="c212d-110">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="c212d-111">Conception des procédures stockées</span><span class="sxs-lookup"><span data-stu-id="c212d-111">Designing Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/designing-stored-procedures.md)|<span data-ttu-id="c212d-112">Explique comment concevoir des assemblys pour [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c212d-112">Describes how to design assemblies for use with [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="c212d-113">Création de procédures stockées</span><span class="sxs-lookup"><span data-stu-id="c212d-113">Creating Stored Procedures</span></span>](creating-stored-procedures.md)|<span data-ttu-id="c212d-114">Explique comment créer des assemblys pour [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c212d-114">Describes how to create assemblies for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="c212d-115">Appel des procédures stockées</span><span class="sxs-lookup"><span data-stu-id="c212d-115">Calling Stored Procedures</span></span>](calling-stored-procedures.md)|<span data-ttu-id="c212d-116">Fournit des informations sur l'utilisation des assemblys dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c212d-116">Provides information on how to use assemblies in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="c212d-117">Accès au contexte de requête dans les procédures stockées</span><span class="sxs-lookup"><span data-stu-id="c212d-117">Accessing Query Context in Stored Procedures</span></span>](accessing-query-context-in-stored-procedures.md)|<span data-ttu-id="c212d-118">Explique comment accéder aux informations d'étendue et de contexte avec des assemblys.</span><span class="sxs-lookup"><span data-stu-id="c212d-118">Describes how to access scope and context information with assemblies.</span></span>|  
|[<span data-ttu-id="c212d-119">Définition de la sécurité pour les procédures stockées</span><span class="sxs-lookup"><span data-stu-id="c212d-119">Setting Security for Stored Procedures</span></span>](setting-security-for-stored-procedures.md)|<span data-ttu-id="c212d-120">Explique comment configurer la sécurité des assemblys dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c212d-120">Describes how to configure security for assemblies in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="c212d-121">Débogage des procédures stockées</span><span class="sxs-lookup"><span data-stu-id="c212d-121">Debugging Stored Procedures</span></span>](debugging-stored-procedures.md)|<span data-ttu-id="c212d-122">Explique comment déboguer les assemblys dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c212d-122">Describes how to debug assemblies in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c212d-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c212d-123">See Also</span></span>  
 [<span data-ttu-id="c212d-124">Gestion des assemblys de modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="c212d-124">Multidimensional Model Assemblies Management</span></span>](../multidimensional-models/multidimensional-model-assemblies-management.md)  
  
  
