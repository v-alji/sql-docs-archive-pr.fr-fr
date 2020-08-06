---
title: Référence d’expression (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: bb16e4ab-b13f-48f2-8cfe-1851656875ef
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7854aa2cc256d63fe93ddb049486e782bfaa0e11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603855"
---
# <a name="expression-reference-report-builder-and-ssrs"></a><span data-ttu-id="9e6fd-102">Référence d'expression (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="9e6fd-102">Expression Reference (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9e6fd-103">Les expressions de rapport prennent en charge diverses références aux fonctions et collections intégrées.</span><span class="sxs-lookup"><span data-stu-id="9e6fd-103">Report expressions support a variety of references to built-in functions and built-in collections.</span></span> <span data-ttu-id="9e6fd-104">La syntaxe des expressions doit être conforme à [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] avant qu'un rapport ne puisse être publié ou traité.</span><span class="sxs-lookup"><span data-stu-id="9e6fd-104">Expressions must have valid [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] syntax before a report can be published or processed.</span></span>  
  
 <span data-ttu-id="9e6fd-105">Pour développer des expressions complexes ou des expressions qui utilisent du code personnalisé ou des assemblys personnalisés, il est recommandé de recourir au Concepteur de rapports dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e6fd-105">To develop complex expressions or expressions that use custom code or custom assemblies, we recommend that you use Report Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="9e6fd-106">Pour plus d’informations, consultez [Code personnalisé et références d’assembly dans les expressions du Concepteur de rapports &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9e6fd-106">For more information, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="9e6fd-107">Utilisez les rubriques de cette section pour écrire les expressions simples incluses dans un rapport.</span><span class="sxs-lookup"><span data-stu-id="9e6fd-107">Use the topics in this section to help write simple expressions in a report.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9e6fd-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="9e6fd-108">In This Section</span></span>  
 [<span data-ttu-id="9e6fd-109">Types de données dans les expressions &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9e6fd-109">Data Types in Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="9e6fd-110">Constantes dans les expressions &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9e6fd-110">Constants in Expressions &#40;Report Builder and SSRS&#41;</span></span>](constants-in-expressions-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="9e6fd-111">Opérateurs dans les expressions &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9e6fd-111">Operators in Expressions &#40;Report Builder and SSRS&#41;</span></span>](operators-in-expressions-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="9e6fd-112">Collections intégrées dans les expressions &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9e6fd-112">Built-in Collections in Expressions &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-in-expressions-report-builder.md)  
  
 [<span data-ttu-id="9e6fd-113">Références à des champs Globals et Users prédéfinis &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9e6fd-113">Built-in Globals and Users References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-built-in-globals-and-users-references-report-builder.md)  
  
 [<span data-ttu-id="9e6fd-114">Références à la collection Parameters &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9e6fd-114">Parameters Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-parameters-collection-references-report-builder.md)  
  
 [<span data-ttu-id="9e6fd-115">Références à une collection de champs de dataset &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9e6fd-115">Dataset Fields Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-dataset-fields-collection-references-report-builder.md)  
  
 [<span data-ttu-id="9e6fd-116">Références à des collections DataSources et DataSets &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9e6fd-116">DataSources and DataSets Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-datasources-and-datasets-references-report-builder.md)  
  
 [<span data-ttu-id="9e6fd-117">Références à des collections de variables de rapport et de groupe &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9e6fd-117">Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-report-and-group-variables-references-report-builder.md)  
  
 [<span data-ttu-id="9e6fd-118">Références à la collection ReportItems &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9e6fd-118">ReportItems Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-reportitems-collection-references-report-builder.md)  
  
## <a name="see-also"></a><span data-ttu-id="9e6fd-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9e6fd-119">See Also</span></span>  
 [<span data-ttu-id="9e6fd-120">Expressions &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9e6fd-120">Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)  
  
  
