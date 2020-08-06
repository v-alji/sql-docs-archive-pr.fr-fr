---
title: Boîte de dialogue Propriétés du rapport, références (Générateur de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10082"
ms.assetid: 3414c857-8ea6-4fc4-a6d5-b4883c039efa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2c28e9053a1c13f8d0e0b7b44f3b1a037976c318
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702403"
---
# <a name="report-properties-dialog-box-references-report-builder"></a><span data-ttu-id="a8779-102">Boîte de dialogue Propriétés du rapport, Références (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="a8779-102">Report Properties Dialog Box, References (Report Builder)</span></span>
  <span data-ttu-id="a8779-103">Sélectionnez **Références** dans la boîte de dialogue **Propriétés du rapport** pour ajouter ou supprimer des références aux assemblys personnalisés ou externes et aux instances de classes personnalisées qui sont utilisées par des expressions dans la définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="a8779-103">Select **References** on the **Report Properties** dialog box to add or remove references to custom or other external assemblies and custom class instances that are used by expressions in the report definition.</span></span> <span data-ttu-id="a8779-104">Les assemblys personnalisés ne sont pas pris en charge en mode local dans le Générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="a8779-104">Custom assemblies are not supported in local mode in Report Builder.</span></span> <span data-ttu-id="a8779-105">Pour créer des rapports qui utilisent des assemblys personnalisés, utilisez Concepteur de rapports dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a8779-105">To author reports that use custom assemblies, use Report Designer in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="a8779-106">Options</span><span class="sxs-lookup"><span data-stu-id="a8779-106">Options</span></span>  
 <span data-ttu-id="a8779-107">**Ajouter ou supprimer des assemblys**</span><span class="sxs-lookup"><span data-stu-id="a8779-107">**Add or remove assemblies**</span></span>  
 <span data-ttu-id="a8779-108">Répertorie les assemblys référencés par le rapport.</span><span class="sxs-lookup"><span data-stu-id="a8779-108">Lists the assemblies that the report references.</span></span> <span data-ttu-id="a8779-109">L'assembly doit être disponible sur l'ordinateur où est installé l'outil que vous utilisez pour concevoir le rapport, ainsi que sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="a8779-109">The assembly must be available on the computer on which the tool you are using to design the report is installed and on the report server.</span></span> <span data-ttu-id="a8779-110">Le nom de la référence doit correspondre exactement au contenu des **\<CodeModule>** balises dans le fichier Report Definition Language (. rdl).</span><span class="sxs-lookup"><span data-stu-id="a8779-110">The name of the reference must match the contents of **\<CodeModule>** tags in the Report Definition Language (.rdl) file exactly.</span></span>  
  
 <span data-ttu-id="a8779-111">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="a8779-111">**Add**</span></span>  
 <span data-ttu-id="a8779-112">Cliquez pour ajouter un assembly.</span><span class="sxs-lookup"><span data-stu-id="a8779-112">Click to add an assembly.</span></span> <span data-ttu-id="a8779-113">Cliquez sur le bouton de sélection (...) pour ouvrir la boîte de dialogue **ouvrir** et sélectionner les assemblys nécessaires pour effectuer le traitement du rapport et l’évaluation de l’expression.</span><span class="sxs-lookup"><span data-stu-id="a8779-113">Click the ellipsis (...) button to open the **Open** dialog box and select the assemblies necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="a8779-114">**Remove**</span><span class="sxs-lookup"><span data-stu-id="a8779-114">**Remove**</span></span>  
 <span data-ttu-id="a8779-115">Pour supprimer une référence d’assembly de la liste, sélectionnez le nom de l’assembly, puis cliquez sur le bouton **Supprimer** .</span><span class="sxs-lookup"><span data-stu-id="a8779-115">To remove an assembly reference from the list, select the assembly name and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="a8779-116">**Ajouter ou supprimer des classes**</span><span class="sxs-lookup"><span data-stu-id="a8779-116">**Add or remove classes**</span></span>  
 <span data-ttu-id="a8779-117">Répertorie les instances de classes utilisées par le rapport.</span><span class="sxs-lookup"><span data-stu-id="a8779-117">Lists the class instances that are used by the report.</span></span> <span data-ttu-id="a8779-118">Cette liste de classes est utilisée uniquement par des membres d'instances, et non par des membres statiques.</span><span class="sxs-lookup"><span data-stu-id="a8779-118">The class list is used only by instance-based members, not static members.</span></span>  
  
 <span data-ttu-id="a8779-119">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="a8779-119">**Add**</span></span>  
 <span data-ttu-id="a8779-120">Cliquez pour ajouter une référence de classe.</span><span class="sxs-lookup"><span data-stu-id="a8779-120">Click to add a class reference.</span></span> <span data-ttu-id="a8779-121">Cliquez sur le bouton de sélection (...) pour ouvrir la boîte de dialogue **ouvrir** et sélectionner les classes nécessaires pour effectuer le traitement du rapport et l’évaluation de l’expression.</span><span class="sxs-lookup"><span data-stu-id="a8779-121">Click the ellipsis (...) button to open the **Open** dialog box and select the classes necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="a8779-122">**Remove**</span><span class="sxs-lookup"><span data-stu-id="a8779-122">**Remove**</span></span>  
 <span data-ttu-id="a8779-123">Pour supprimer l’instance de classe, sélectionnez-la et cliquez sur le bouton **Supprimer** .</span><span class="sxs-lookup"><span data-stu-id="a8779-123">To delete the class instance, select it and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="a8779-124">**Haut**</span><span class="sxs-lookup"><span data-stu-id="a8779-124">**Up**</span></span>  
 <span data-ttu-id="a8779-125">Pour les classes qui ont des dépendances, vous pouvez faire monter cette référence dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a8779-125">For classes that have dependencies, you can move this reference higher in the list.</span></span>  
  
 <span data-ttu-id="a8779-126">**Descendre**</span><span class="sxs-lookup"><span data-stu-id="a8779-126">**Down**</span></span>  
 <span data-ttu-id="a8779-127">Pour les classes qui ont des dépendances, vous pouvez faire descendre cette référence dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a8779-127">For classes that have dependencies, you can move this reference lower in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8779-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a8779-128">See Also</span></span>  
 <span data-ttu-id="a8779-129">[Aide Générateur de rapports pour les boîtes de dialogue, les volets et les assistants](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="a8779-129">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 [<span data-ttu-id="a8779-130">Expressions &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a8779-130">Expressions &#40;Report Builder and SSRS&#41;</span></span>](report-design/expressions-report-builder-and-ssrs.md)  
  
  
