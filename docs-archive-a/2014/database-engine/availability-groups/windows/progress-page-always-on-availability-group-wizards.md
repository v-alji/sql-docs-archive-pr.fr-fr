---
title: Page progression (assistants de groupe de disponibilité AlwaysOn) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.addreplicawizard.progress.f1
- sql12.swb.newagwizard.progress.f1
- sql11.swb.failoverwizard.progress.f1
- sql11.swb.adddatabasewizard.progress.f1
- sql11.swb.addreplicawizard.progress.f1
- sql11.swb.newagwizard.progress.f1
- sql12.swb.adddatabasewizard.progress.f1
- sql12.swb.failoverwixard.progress.f1
ms.assetid: bd3b0306-8384-4120-a1c9-03825f0ae26a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7de8df6906d930215d71a0adc562bd7cef961ebb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707904"
---
# <a name="progress-page-alwayson-availability-group-wizards"></a><span data-ttu-id="8a3a9-102">Page Progression (Assistants Groupe de disponibilité AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="8a3a9-102">Progress Page (AlwaysOn Availability Group Wizards)</span></span>
  <span data-ttu-id="8a3a9-103">Utilisez cette boîte de dialogue pour afficher la progression d'un Assistant [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] que vous exécutez dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a3a9-103">Use this dialog box to view the progress of a [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] wizard that you are running in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="8a3a9-104">La barre de progression indique la progression relative des étapes que l'Assistant effectue.</span><span class="sxs-lookup"><span data-stu-id="8a3a9-104">The progress bar indicates the relative progress of the steps that the wizard is performing.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="8a3a9-105">Liste d’éléments UI</span><span class="sxs-lookup"><span data-stu-id="8a3a9-105">UI element list</span></span>  
 <span data-ttu-id="8a3a9-106">**En savoir plus**</span><span class="sxs-lookup"><span data-stu-id="8a3a9-106">**More details**</span></span>  
 <span data-ttu-id="8a3a9-107">Cliquez sur la flèche bas pour afficher une grille de progression qui répertorie toutes les étapes effectuées, dans l'ordre, suivies de l'opération en cours actuelle.</span><span class="sxs-lookup"><span data-stu-id="8a3a9-107">Click the down arrow to display a progress grid that lists any completed steps, in order, followed by the current in-progress operation.</span></span> <span data-ttu-id="8a3a9-108">Cette grille comporte les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="8a3a9-108">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="8a3a9-109">**Nom**</span><span class="sxs-lookup"><span data-stu-id="8a3a9-109">**Name**</span></span>  
 <span data-ttu-id="8a3a9-110">Affiche une expression qui décrit une étape spécifique.</span><span class="sxs-lookup"><span data-stu-id="8a3a9-110">Displays a phrase that describes a specific step.</span></span>  
  
 <span data-ttu-id="8a3a9-111">**État**</span><span class="sxs-lookup"><span data-stu-id="8a3a9-111">**Status**</span></span>  
 <span data-ttu-id="8a3a9-112">Indique le résultat des étapes terminées et le pourcentage d'exécution de l'étape active, comme suit :</span><span class="sxs-lookup"><span data-stu-id="8a3a9-112">Indicates the outcome of completed steps and the percentage of completion of the current step, as follows:</span></span>  
  
|<span data-ttu-id="8a3a9-113">Résultats</span><span class="sxs-lookup"><span data-stu-id="8a3a9-113">Result</span></span>|<span data-ttu-id="8a3a9-114">Description</span><span class="sxs-lookup"><span data-stu-id="8a3a9-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8a3a9-115">**Error**</span><span class="sxs-lookup"><span data-stu-id="8a3a9-115">**Error**</span></span>|<span data-ttu-id="8a3a9-116">Indique que l'opération pour cette étape a rencontré une erreur.</span><span class="sxs-lookup"><span data-stu-id="8a3a9-116">Indicates the operation for this step experienced an error.</span></span> <span data-ttu-id="8a3a9-117">Cliquez sur le lien pour afficher une boîte de dialogue de message qui décrit l'erreur.</span><span class="sxs-lookup"><span data-stu-id="8a3a9-117">Click the link to display a message dialog box that describes the error.</span></span>|  
|<span data-ttu-id="8a3a9-118">**En cours (** *pourcentage-effectué* **)**</span><span class="sxs-lookup"><span data-stu-id="8a3a9-118">**In Progress (** *percentage-completed* **)**</span></span>|<span data-ttu-id="8a3a9-119">Indique que l'opération a maintenant lieu et estime le pourcentage de réalisation de cette étape.</span><span class="sxs-lookup"><span data-stu-id="8a3a9-119">Indicates that the operation is occurring now and estimates the percentage of this step that has completed.</span></span>|  
|<span data-ttu-id="8a3a9-120">**Success**</span><span class="sxs-lookup"><span data-stu-id="8a3a9-120">**Success**</span></span>|<span data-ttu-id="8a3a9-121">Indique que l'opération pour cette étape s'est terminée avec succès.</span><span class="sxs-lookup"><span data-stu-id="8a3a9-121">Indicates the operation for this step completed successfully.</span></span>|  
  
 <span data-ttu-id="8a3a9-122">**Moins de détails**</span><span class="sxs-lookup"><span data-stu-id="8a3a9-122">**Fewer Details**</span></span>  
 <span data-ttu-id="8a3a9-123">Cliquez pour masquer la grille de progression.</span><span class="sxs-lookup"><span data-stu-id="8a3a9-123">Click to hide the progress grid.</span></span>  
  
 <span data-ttu-id="8a3a9-124">**Annuler**</span><span class="sxs-lookup"><span data-stu-id="8a3a9-124">**Cancel**</span></span>  
 <span data-ttu-id="8a3a9-125">Cliquez pour ignorer les opérations restantes, puis quittez l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="8a3a9-125">Click to skip any remaining operations and then exit the wizard.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="8a3a9-126">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="8a3a9-126">Related Tasks</span></span>  
  
-   [<span data-ttu-id="8a3a9-127">Utiliser la boîte de dialogue Nouveau groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="8a3a9-127">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="8a3a9-128">Utiliser l’Assistant Ajouter un réplica au groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="8a3a9-128">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="8a3a9-129">Utiliser l’Assistant Ajouter une base de données au groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="8a3a9-129">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
-   [<span data-ttu-id="8a3a9-130">Utiliser l’Assistant Basculer le groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="8a3a9-130">Use the Fail Over Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-fail-over-availability-group-wizard-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="8a3a9-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8a3a9-131">See Also</span></span>  
 [<span data-ttu-id="8a3a9-132">Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8a3a9-132">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
