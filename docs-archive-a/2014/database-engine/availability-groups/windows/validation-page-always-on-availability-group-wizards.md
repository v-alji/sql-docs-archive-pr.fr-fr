---
title: Page validation (assistants de groupe de disponibilité AlwaysOn) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.newagwizard.validation.f1
- sql12.swb.addreplicawizard.validation.f1
- sql12.swb.adddatabasewizard.validation.f1
helpviewer_keywords:
- ', listeners'
ms.assetid: c8971556-240c-491a-bc86-9cc72f71a3dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f2010074a357932f8af7358a05ee6ed16f5c0881
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601112"
---
# <a name="validation-page-alwayson-availability-group-wizards"></a><span data-ttu-id="a56f1-102">Page Validation (Assistants Groupe de disponibilité AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="a56f1-102">Validation Page (AlwaysOn Availability Group Wizards)</span></span>
  <span data-ttu-id="a56f1-103">Cette rubrique d’aide décrit les options de la page **Validation** .</span><span class="sxs-lookup"><span data-stu-id="a56f1-103">This help topic describes the options of the **Validation** page.</span></span> <span data-ttu-id="a56f1-104">Cette rubrique s'applique à l' [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)], à l' [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)]et à l' [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a56f1-104">This topic applies to the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)], [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)], and [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="a56f1-105">Utilisez cette page pour confirmer que votre environnement prend en charge tous les choix de configuration que vous avez apportés dans les pages précédentes de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="a56f1-105">Use this page to validate that your environment supports all the configuration choices you made on previous pages of the wizard.</span></span>  
  
##  <a name="validation-page-options"></a><a name="PageOptions"></a><span data-ttu-id="a56f1-106">Options de la page validation</span><span class="sxs-lookup"><span data-stu-id="a56f1-106">Validation Page Options</span></span>  
 <span data-ttu-id="a56f1-107">**Résultats de la validation du groupe de disponibilité.**</span><span class="sxs-lookup"><span data-stu-id="a56f1-107">**Results of availability group validation.**</span></span>  
 <span data-ttu-id="a56f1-108">Cette grille affiche les résultats de chaque étape de validation finalisée.</span><span class="sxs-lookup"><span data-stu-id="a56f1-108">This grid displays the results of each completed validation step.</span></span> <span data-ttu-id="a56f1-109">Les colonnes de la grille sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a56f1-109">The grid columns are as follows:</span></span>  
  
 <span data-ttu-id="a56f1-110">**Nom**</span><span class="sxs-lookup"><span data-stu-id="a56f1-110">**Name**</span></span>  
 <span data-ttu-id="a56f1-111">Affiche une expression qui décrit une étape spécifique.</span><span class="sxs-lookup"><span data-stu-id="a56f1-111">Displays a phrase that describes a specific step.</span></span>  
  
 <span data-ttu-id="a56f1-112">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="a56f1-112">**Result**</span></span>  
 <span data-ttu-id="a56f1-113">Affiche l'un des textes de lien hypertexte suivants.</span><span class="sxs-lookup"><span data-stu-id="a56f1-113">Displays one of the following hyperlink texts.</span></span> <span data-ttu-id="a56f1-114">Pour plus d'informations sur le résultat d'une étape de validation donnée, cliquez sur le lien hypertexte.</span><span class="sxs-lookup"><span data-stu-id="a56f1-114">For more information about the result of given validation step, click the hyperlink.</span></span>  
  
|<span data-ttu-id="a56f1-115">Résultats</span><span class="sxs-lookup"><span data-stu-id="a56f1-115">Result</span></span>|<span data-ttu-id="a56f1-116">Description</span><span class="sxs-lookup"><span data-stu-id="a56f1-116">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a56f1-117">**Error**</span><span class="sxs-lookup"><span data-stu-id="a56f1-117">**Error**</span></span>|<span data-ttu-id="a56f1-118">Indique que l'étape de validation a échoué.</span><span class="sxs-lookup"><span data-stu-id="a56f1-118">Indicates that the validation step failed.</span></span> <span data-ttu-id="a56f1-119">Cliquez sur le lien pour afficher le message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="a56f1-119">Click the link to view the error message.</span></span>|  
|<span data-ttu-id="a56f1-120">**Ignoré**</span><span class="sxs-lookup"><span data-stu-id="a56f1-120">**Skipped**</span></span>|<span data-ttu-id="a56f1-121">Indique que l'étape de validation a été ignorée parce qu'elle n'était pas requise par vos sélections.</span><span class="sxs-lookup"><span data-stu-id="a56f1-121">Indicates that the validation step was skipped because it is not required by your selections.</span></span> <span data-ttu-id="a56f1-122">Cliquez sur le lien pour afficher la raison pour laquelle une étape a été ignorée.</span><span class="sxs-lookup"><span data-stu-id="a56f1-122">Click the link to view the reason that a step was skipped.</span></span>|  
|<span data-ttu-id="a56f1-123">**Success**</span><span class="sxs-lookup"><span data-stu-id="a56f1-123">**Success**</span></span>|<span data-ttu-id="a56f1-124">Indique que l'étape de validation s'est terminée avec succès</span><span class="sxs-lookup"><span data-stu-id="a56f1-124">Indicates that the validation step completed successfully</span></span>|  
|<span data-ttu-id="a56f1-125">**Avertissement**</span><span class="sxs-lookup"><span data-stu-id="a56f1-125">**Warning**</span></span>|<span data-ttu-id="a56f1-126">Indique un problème potentiel avec la configuration du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="a56f1-126">Indicates a potential issue with the availability group configuration.</span></span>  <span data-ttu-id="a56f1-127">Cliquez sur le lien pour afficher le message d'avertissement.</span><span class="sxs-lookup"><span data-stu-id="a56f1-127">Click the link to view the warning message.</span></span>|  
  
 <span data-ttu-id="a56f1-128">**Réexécuter la validation**</span><span class="sxs-lookup"><span data-stu-id="a56f1-128">**Re-run Validation**</span></span>  
 <span data-ttu-id="a56f1-129">Cliquez pour répéter les étapes de validation si vous apportez une modification à l'extérieur de l'Assistant en réponse à une erreur de validation.</span><span class="sxs-lookup"><span data-stu-id="a56f1-129">Click to repeat the validation steps if you make a change outside of the wizard in response to a validation error.</span></span>  
  

  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="a56f1-130">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="a56f1-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="a56f1-131">Utiliser la boîte de dialogue Nouveau groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a56f1-131">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="a56f1-132">Utiliser l’Assistant Ajouter un réplica au groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a56f1-132">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="a56f1-133">Utiliser l’Assistant Ajouter une base de données au groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a56f1-133">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
 
  
## <a name="see-also"></a><span data-ttu-id="a56f1-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a56f1-134">See Also</span></span>  
 [<span data-ttu-id="a56f1-135">Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a56f1-135">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
