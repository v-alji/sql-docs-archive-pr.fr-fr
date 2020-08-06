---
title: Spécifier les critères de requête (Assistant Optimisation de l’utilisation) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.usagebasedoptimizationwizard.specifyquerycriteria.f1
ms.assetid: 3193adc2-af9f-4234-a4cc-dea0c280a724
author: minewiskan
ms.author: owend
ms.openlocfilehash: f3b93034a089ff3121155e35de4cec96846824a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603068"
---
# <a name="specify-query-criteria-usage-based-optimization-wizard"></a><span data-ttu-id="13734-102">Spécifier les critères de requêtes (Assistant Optimisation de l'utilisation)</span><span class="sxs-lookup"><span data-stu-id="13734-102">Specify Query Criteria (Usage-Based Optimization Wizard)</span></span>
  <span data-ttu-id="13734-103">Utilisez la page **Spécifier les critères de requêtes** pour choisir unes ou plusieurs options de filtre afin d'identifier des requêtes à optimiser.</span><span class="sxs-lookup"><span data-stu-id="13734-103">Use the **Specify Query Criteria** page to choose one or more filter options in order to identify queries to optimize.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="13734-104">Cette page est désactivée si [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] n'est pas connecté au journal des requêtes.</span><span class="sxs-lookup"><span data-stu-id="13734-104">This page is disabled if [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cannot connect to the query log.</span></span>  
  
## <a name="options"></a><span data-ttu-id="13734-105">Options</span><span class="sxs-lookup"><span data-stu-id="13734-105">Options</span></span>  
 <span data-ttu-id="13734-106">**Statistiques du journal des requêtes**</span><span class="sxs-lookup"><span data-stu-id="13734-106">**Query log statistics**</span></span>  
 <span data-ttu-id="13734-107">Affiche des informations sur les requêtes stockées dans le journal pour les partitions sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="13734-107">Displays information about the queries stored in the query log for the selected partitions.</span></span> <span data-ttu-id="13734-108">Les éléments suivants s'affichent :</span><span class="sxs-lookup"><span data-stu-id="13734-108">The following items are displayed:</span></span>  
  
|<span data-ttu-id="13734-109">Terme</span><span class="sxs-lookup"><span data-stu-id="13734-109">Term</span></span>|<span data-ttu-id="13734-110">Définition</span><span class="sxs-lookup"><span data-stu-id="13734-110">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="13734-111">**Nombre total de requêtes**</span><span class="sxs-lookup"><span data-stu-id="13734-111">**Total queries**</span></span>|<span data-ttu-id="13734-112">Affiche le nombre total de requêtes stockées dans le journal pour les partitions sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="13734-112">Displays the total number of queries stored in the query log for the selected partitions.</span></span>|  
|<span data-ttu-id="13734-113">**Requêtes distinctes**</span><span class="sxs-lookup"><span data-stu-id="13734-113">**Distinct queries**</span></span>|<span data-ttu-id="13734-114">Affiche le nombre de requêtes distinctes stockées dans le journal pour les partitions sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="13734-114">Displays the number of distinct queries stored in the query log for the selected partitions.</span></span>|  
|<span data-ttu-id="13734-115">**Utilisateurs distincts**</span><span class="sxs-lookup"><span data-stu-id="13734-115">**Distinct users**</span></span>|<span data-ttu-id="13734-116">Affiche le nombre total d'utilisateurs distincts associés aux requêtes stockées dans le journal pour les partitions sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="13734-116">Displays the total number of distinct users associated with queries stored in the query log for the selected partitions.</span></span>|  
|<span data-ttu-id="13734-117">**Temps de réponse moyen**</span><span class="sxs-lookup"><span data-stu-id="13734-117">**Average response time**</span></span>|<span data-ttu-id="13734-118">Affiche le temps de réponse moyen pour les requêtes stockées dans le journal pour les partitions sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="13734-118">Displays the average response time for queries stored in the query log for the selected partitions.</span></span>|  
  
 <span data-ttu-id="13734-119">**Date de début**</span><span class="sxs-lookup"><span data-stu-id="13734-119">**Beginning date**</span></span>  
 <span data-ttu-id="13734-120">Filtre les requêtes du journal en fonction de la date et de l'heure de début.</span><span class="sxs-lookup"><span data-stu-id="13734-120">Filters queries in the query log based on a starting date and time.</span></span> <span data-ttu-id="13734-121">Choisissez ou tapez une date dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="13734-121">Choose or type a date in the dropdown list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="13734-122"> Si vous ne sélectionnez pas **Date de fin** , toutes les requêtes du journal portant une date et une heure égales ou ultérieures à celles spécifiées seront prises en compte.</span><span class="sxs-lookup"><span data-stu-id="13734-122">If **Ending date** is not selected, all queries in the query log on or after the date and time specified for this option are considered.</span></span>  
  
 <span data-ttu-id="13734-123">**Date de fin**</span><span class="sxs-lookup"><span data-stu-id="13734-123">**Ending date**</span></span>  
 <span data-ttu-id="13734-124">Filtre les requêtes du journal en fonction de la date et de l'heure de fin.</span><span class="sxs-lookup"><span data-stu-id="13734-124">Filters queries in the query log based on an ending date and time.</span></span> <span data-ttu-id="13734-125">Choisissez ou tapez une date dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="13734-125">Choose or type a date in the dropdown list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="13734-126"> Si vous ne sélectionnez pas **Date de début** , toutes les requêtes du journal portant une date et une heure égales ou antérieures à celles spécifiées seront prises en compte.</span><span class="sxs-lookup"><span data-stu-id="13734-126">If **Beginning date** is not selected, all queries in the query log on or before the date and time specified for this option are considered.</span></span>  
  
 <span data-ttu-id="13734-127">**Utilisateurs**</span><span class="sxs-lookup"><span data-stu-id="13734-127">**Users**</span></span>  
 <span data-ttu-id="13734-128">Filtre les requêtes du journal en fonction d'un jeu d'utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="13734-128">Filters queries in the query log based on a specified set of users.</span></span> <span data-ttu-id="13734-129">Cliquez sur le bouton (**...**) pour afficher la boîte de dialogue **Sélection de l’utilisateur** et choisir des utilisateurs sur la base desquels les requêtes doivent être filtrées.</span><span class="sxs-lookup"><span data-stu-id="13734-129">Click the ellipsis (**...**) button to display the **User Selection** dialog box and choose users on which to filter queries.</span></span> <span data-ttu-id="13734-130">Pour plus d’informations sur la boîte de dialogue **Sélection de l’utilisateur**, consultez [Boîte de dialogue Sélection de l’utilisateur &#40;Analysis Services – Données multidimensionnelles&#41;](user-selection-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="13734-130">For more information about the **User Selection** dialog box, see [User Selection Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](user-selection-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="13734-131">**Requêtes les plus fréquentes**</span><span class="sxs-lookup"><span data-stu-id="13734-131">**Most frequent queries**</span></span>  
 <span data-ttu-id="13734-132">Filtre les requêtes du journal en fonction du pourcentage supérieur de requêtes distinctes exécutées le plus fréquemment pour les partitions sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="13734-132">Filters queries in the query log based on the topmost percentage of the distinct queries most often run for the selected partitions.</span></span> <span data-ttu-id="13734-133">Choisissez ou tapez un pourcentage dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="13734-133">Choose or type a percent value in the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13734-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="13734-134">See Also</span></span>  
 <span data-ttu-id="13734-135">[Aide (F1) de l’Assistant Optimisation de l’utilisation](usage-based-optimization-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="13734-135">[Usage-Based Optimization Wizard F1 Help](usage-based-optimization-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="13734-136">Analysis Services assistants &#40;&#41;de données multidimensionnelles</span><span class="sxs-lookup"><span data-stu-id="13734-136">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
