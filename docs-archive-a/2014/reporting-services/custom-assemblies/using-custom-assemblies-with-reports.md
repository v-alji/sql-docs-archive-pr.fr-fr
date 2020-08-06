---
title: Utilisation d’assemblages personnalisés avec des rapports | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom assemblies [Reporting Services]
- assemblies [Reporting Services], custom
- custom assemblies [Reporting Services], about custom assemblies
ms.assetid: 53d141d0-2185-466a-84dc-7b90d284da3d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f77b9da44ebb57617bd45e43d1e1e847e9074662
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697580"
---
# <a name="using-custom-assemblies-with-reports"></a><span data-ttu-id="c3b7f-102">Utilisation d'assemblys personnalisés avec des rapports</span><span class="sxs-lookup"><span data-stu-id="c3b7f-102">Using Custom Assemblies with Reports</span></span>
  <span data-ttu-id="c3b7f-103">Dans [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], vous pouvez écrire du code personnalisé pour les valeurs, les styles et la mise en forme des éléments de rapport.</span><span class="sxs-lookup"><span data-stu-id="c3b7f-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can write custom code for report item values, styles, and formatting.</span></span> <span data-ttu-id="c3b7f-104">Par exemple, vous pouvez utiliser du code personnalisé pour mettre en forme les devises en fonction de paramètres régionaux, marquer certaines valeurs avec une mise en forme spéciale ou appliquer d'autres règles d'entreprise en pratique dans votre société.</span><span class="sxs-lookup"><span data-stu-id="c3b7f-104">For example, you can use custom code to format currencies based on locale, flag certain values with special formatting, or apply other business rules that are in practice for your company.</span></span> <span data-ttu-id="c3b7f-105">Une façon d’inclure ce code dans vos rapports consiste à créer un assembly de code personnalisé à l’aide du [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] que vous pouvez référencer à partir de vos fichiers de définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="c3b7f-105">One way to include this code in your reports is to create a custom code assembly using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] that you can reference from within your report definition files.</span></span> <span data-ttu-id="c3b7f-106">Le serveur appelle les fonctions de votre assembly personnalisé lors de l'exécution d'un rapport.</span><span class="sxs-lookup"><span data-stu-id="c3b7f-106">The server calls the functions in your custom assemblies when a report is run.</span></span> <span data-ttu-id="c3b7f-107">Les assemblys personnalisés peuvent être utilisés pour extraire des fonctions spéciales que vous envisagez d'utiliser dans vos rapports.</span><span class="sxs-lookup"><span data-stu-id="c3b7f-107">Custom assemblies can be used to retrieve specialized functions that you plan to use in your reports.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c3b7f-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="c3b7f-108">In This Section</span></span>  
 [<span data-ttu-id="c3b7f-109">Référencement d'assemblys dans un Fichier RDL</span><span class="sxs-lookup"><span data-stu-id="c3b7f-109">Referencing Assemblies in an RDL File</span></span>](referencing-assemblies-in-an-rdl-file.md)  
 <span data-ttu-id="c3b7f-110">Décrit comment référencer vos assemblys personnalisés dans un fichier RDL (Report Definition Language File).</span><span class="sxs-lookup"><span data-stu-id="c3b7f-110">Describes how to reference your custom assemblies in a report definition language file.</span></span>  
  
 [<span data-ttu-id="c3b7f-111">Déploiement d'un assembly personnalisé</span><span class="sxs-lookup"><span data-stu-id="c3b7f-111">Deploying a Custom Assembly</span></span>](deploying-a-custom-assembly.md)  
 <span data-ttu-id="c3b7f-112">Décrit comment déployer un assembly personnalisé sur le Concepteur de rapports et le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="c3b7f-112">Describes how to deploy a custom assembly to Report Designer and the report server.</span></span>  
  
 [<span data-ttu-id="c3b7f-113">Utilisation d'assemblys personnalisés avec noms forts</span><span class="sxs-lookup"><span data-stu-id="c3b7f-113">Using Strong-Named Custom Assemblies</span></span>](using-strong-named-custom-assemblies.md)  
 <span data-ttu-id="c3b7f-114">Décrit comment utiliser des assemblys personnalisés avec des noms forts.</span><span class="sxs-lookup"><span data-stu-id="c3b7f-114">Describes how to use custom assemblies with strong names.</span></span>  
  
 [<span data-ttu-id="c3b7f-115">Déclaration d'autorisations dans les assemblys personnalisés</span><span class="sxs-lookup"><span data-stu-id="c3b7f-115">Asserting Permissions in Custom Assemblies</span></span>](asserting-permissions-in-custom-assemblies.md)  
 <span data-ttu-id="c3b7f-116">Décrit comment déployer des assemblys personnalisés avec des autorisations limitées et spécifiques, et comment déclarer ces autorisations dans le code.</span><span class="sxs-lookup"><span data-stu-id="c3b7f-116">Describes how to deploy custom assemblies with limited and specific permissions and how to assert those permissions in code.</span></span>  
  
 [<span data-ttu-id="c3b7f-117">Accès aux assemblys personnalisés par le biais d'expressions</span><span class="sxs-lookup"><span data-stu-id="c3b7f-117">Accessing Custom Assemblies Through Expressions</span></span>](accessing-custom-assemblies-through-expressions.md)  
 <span data-ttu-id="c3b7f-118">Décrit comment appeler des méthodes d'assembly personnalisé sous la forme d'expressions de rapport dans vos définitions de rapport.</span><span class="sxs-lookup"><span data-stu-id="c3b7f-118">Describes how to call custom assembly methods as report expressions in your report definitions.</span></span>  
  
 [<span data-ttu-id="c3b7f-119">Initialisation d'objets Assembly personnalisés</span><span class="sxs-lookup"><span data-stu-id="c3b7f-119">Initializing Custom Assembly Objects</span></span>](initializing-custom-assembly-objects.md)  
 <span data-ttu-id="c3b7f-120">Décrit comment initialiser les valeurs des objets d'assembly personnalisé appelés à partir d'un rapport.</span><span class="sxs-lookup"><span data-stu-id="c3b7f-120">Describes how to initialize values for custom assembly objects called from a report.</span></span>  
  
 [<span data-ttu-id="c3b7f-121">Procédure : Déboguer des assemblages personnalisés</span><span class="sxs-lookup"><span data-stu-id="c3b7f-121">How to: Debug Custom Assemblies</span></span>](how-to-debug-custom-assemblies.md)  
 <span data-ttu-id="c3b7f-122">Décrit comment déboguer le code de votre assembly personnalisé.</span><span class="sxs-lookup"><span data-stu-id="c3b7f-122">Describes how to debug your custom assembly code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3b7f-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c3b7f-123">See Also</span></span>  
 [<span data-ttu-id="c3b7f-124">RDL (Report Definition Language) &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c3b7f-124">Report Definition Language &#40;SSRS&#41;</span></span>](../reports/report-definition-language-ssrs.md)  
  
  
