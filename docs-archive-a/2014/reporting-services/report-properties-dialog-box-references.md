---
title: Boîte de dialogue Propriétés du rapport, références | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10530"
- sql12.rtp.rptdesigner.reportproperties.references.f1
ms.assetid: 4639d368-9918-4bb1-9953-7a724ca78dea
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4b28ea0865d37bdc56054d6b23dc8c82d9279b08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702396"
---
# <a name="report-properties-dialog-box-references"></a><span data-ttu-id="c9475-102">Boîte de dialogue Propriétés du rapport, Références</span><span class="sxs-lookup"><span data-stu-id="c9475-102">Report Properties Dialog Box, References</span></span>
  <span data-ttu-id="c9475-103">Sélectionnez **Références** dans la boîte de dialogue **Propriétés du rapport** pour ajouter ou supprimer des références aux assemblys personnalisés ou externes et aux instances de classes personnalisées qui sont utilisées par des expressions dans la définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="c9475-103">Select **References** on the **Report Properties** dialog box to add or remove references to custom or other external assemblies and custom class instances that are used by expressions in the report definition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c9475-104">Options</span><span class="sxs-lookup"><span data-stu-id="c9475-104">Options</span></span>  
 <span data-ttu-id="c9475-105">**Ajouter ou supprimer des assemblys**</span><span class="sxs-lookup"><span data-stu-id="c9475-105">**Add or remove assemblies**</span></span>  
 <span data-ttu-id="c9475-106">Répertorie les assemblys référencés par le rapport.</span><span class="sxs-lookup"><span data-stu-id="c9475-106">Lists the assemblies that the report references.</span></span> <span data-ttu-id="c9475-107">L'assembly doit être disponible sur l'ordinateur où est installé l'outil que vous utilisez pour concevoir le rapport, ainsi que sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="c9475-107">The assembly must be available on the computer on which the tool you are using to design the report is installed and on the report server.</span></span> <span data-ttu-id="c9475-108">Le nom de la référence doit correspondre exactement au contenu des **\<CodeModule>** balises dans le fichier Report Definition Language (. rdl).</span><span class="sxs-lookup"><span data-stu-id="c9475-108">The name of the reference must match the contents of **\<CodeModule>** tags in the Report Definition Language (.rdl) file exactly.</span></span>  
  
 <span data-ttu-id="c9475-109">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="c9475-109">**Add**</span></span>  
 <span data-ttu-id="c9475-110">Cliquez pour ajouter un assembly.</span><span class="sxs-lookup"><span data-stu-id="c9475-110">Click to add an assembly.</span></span> <span data-ttu-id="c9475-111">Cliquez sur le bouton de sélection (...) pour ouvrir la boîte de dialogue **ouvrir** et sélectionner les assemblys nécessaires pour effectuer le traitement du rapport et l’évaluation de l’expression.</span><span class="sxs-lookup"><span data-stu-id="c9475-111">Click the ellipsis (...) button to open the **Open** dialog box and select the assemblies necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="c9475-112">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="c9475-112">**Delete**</span></span>  
 <span data-ttu-id="c9475-113">Pour supprimer une référence d’assembly de la liste, sélectionnez le nom de l’assembly, puis cliquez sur le bouton **Supprimer** .</span><span class="sxs-lookup"><span data-stu-id="c9475-113">To remove an assembly reference from the list, select the assembly name and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="c9475-114">**Ajouter ou supprimer des classes**</span><span class="sxs-lookup"><span data-stu-id="c9475-114">**Add or remove classes**</span></span>  
 <span data-ttu-id="c9475-115">Répertorie les instances de classes utilisées par le rapport.</span><span class="sxs-lookup"><span data-stu-id="c9475-115">Lists the class instances that are used by the report.</span></span> <span data-ttu-id="c9475-116">Cette liste de classes est utilisée uniquement par des membres d'instances, et non par des membres statiques.</span><span class="sxs-lookup"><span data-stu-id="c9475-116">The class list is used only by instance-based members, not static members.</span></span>  
  
 <span data-ttu-id="c9475-117">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="c9475-117">**Add**</span></span>  
 <span data-ttu-id="c9475-118">Cliquez pour ajouter une référence de classe.</span><span class="sxs-lookup"><span data-stu-id="c9475-118">Click to add a class reference.</span></span> <span data-ttu-id="c9475-119">Cliquez sur le bouton de sélection (...) pour ouvrir la boîte de dialogue **ouvrir** et sélectionner les classes nécessaires pour effectuer le traitement du rapport et l’évaluation de l’expression.</span><span class="sxs-lookup"><span data-stu-id="c9475-119">Click the ellipsis (...) button to open the **Open** dialog box and select the classes necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="c9475-120">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="c9475-120">**Delete**</span></span>  
 <span data-ttu-id="c9475-121">Pour supprimer l’instance de classe, sélectionnez-la et cliquez sur le bouton **Supprimer** .</span><span class="sxs-lookup"><span data-stu-id="c9475-121">To delete the class instance, select it and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="c9475-122">**Haut**</span><span class="sxs-lookup"><span data-stu-id="c9475-122">**Up**</span></span>  
 <span data-ttu-id="c9475-123">Pour les classes qui ont des dépendances, vous pouvez faire monter cette référence dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c9475-123">For classes that have dependencies, you can move this reference higher in the list.</span></span>  
  
 <span data-ttu-id="c9475-124">**Descendre**</span><span class="sxs-lookup"><span data-stu-id="c9475-124">**Down**</span></span>  
 <span data-ttu-id="c9475-125">Pour les classes qui ont des dépendances, vous pouvez faire descendre cette référence dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c9475-125">For classes that have dependencies, you can move this reference lower in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9475-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c9475-126">See Also</span></span>  
 <span data-ttu-id="c9475-127">[Code personnalisé et références d’assembly dans les expressions du Concepteur de rapports &#40;SSRS&#41;](report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c9475-127">[Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md) </span></span>  
 <span data-ttu-id="c9475-128">[Les collections de variables de rapport et de groupe référencent &#40;Générateur de rapports et SSRS&#41;](report-design/built-in-collections-report-and-group-variables-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="c9475-128">[Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;](report-design/built-in-collections-report-and-group-variables-references-report-builder.md) </span></span>  
 [<span data-ttu-id="c9475-129">Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c9475-129">Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](report-design/expression-examples-report-builder-and-ssrs.md)  
  
  
