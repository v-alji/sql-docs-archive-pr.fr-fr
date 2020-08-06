---
title: Paramètres de filtre (Explorateur d’objets et Explorateur de l’utilitaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.filtersettings.f1
- sql12.swb.common.filtersettings.f1
ms.assetid: 4aab04bc-e1ab-4d4b-ab74-b287fc805bc2
author: stevestein
ms.author: sstein
ms.openlocfilehash: c31fbcbef9cbab86a7bd3ab7b2fae21e626aaa59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599751"
---
# <a name="filter-settings-object-explorer-and-utility-explorer"></a><span data-ttu-id="203ab-102">Paramètres de filtre (Explorateur d'objets et Explorateur de l'utilitaire)</span><span class="sxs-lookup"><span data-stu-id="203ab-102">Filter Settings (Object Explorer and Utility Explorer)</span></span>
  <span data-ttu-id="203ab-103">Cette boîte de dialogue vous permet de spécifier un filtre.</span><span class="sxs-lookup"><span data-stu-id="203ab-103">Use this dialog box to specify a filter.</span></span> <span data-ttu-id="203ab-104">Un filtre vous permet de configurer l'Explorateur d'objets et l'Explorateur de l'utilitaire pour qu'ils affichent uniquement les éléments qui correspondent à des critères spécifiques.</span><span class="sxs-lookup"><span data-stu-id="203ab-104">A filter allows you to configure Object Explorer and Utility Explorer to display only items that meet specific criteria.</span></span> <span data-ttu-id="203ab-105">Par exemple, vous pouvez utiliser un filtre pour afficher uniquement les travaux dont le nom contient le mot « Maintenance ».</span><span class="sxs-lookup"><span data-stu-id="203ab-105">For example, you can use a filter to show only jobs with names that contain the word "Maintenance."</span></span> <span data-ttu-id="203ab-106">L’en-tête de la boîte de dialogue **Paramètres du filtre** contient le nom du serveur et peut contenir le nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="203ab-106">The header for the **Filter Settings** dialog box contains the name of the server, and it may contain the name of the database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="203ab-107">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="203ab-107">UI element list</span></span>  
 <span data-ttu-id="203ab-108">**Propriété**</span><span class="sxs-lookup"><span data-stu-id="203ab-108">**Property**</span></span>  
 <span data-ttu-id="203ab-109">Indique la propriété sur laquelle filtrer.</span><span class="sxs-lookup"><span data-stu-id="203ab-109">Displays the property to filter on.</span></span>  
  
 <span data-ttu-id="203ab-110">**Opérateur**</span><span class="sxs-lookup"><span data-stu-id="203ab-110">**Operator**</span></span>  
 <span data-ttu-id="203ab-111">Permet de sélectionner la manière dont le filtre applique la valeur à la propriété.</span><span class="sxs-lookup"><span data-stu-id="203ab-111">Select the way that the filter applies the value to the property.</span></span> <span data-ttu-id="203ab-112">Les options suivantes sont possibles :</span><span class="sxs-lookup"><span data-stu-id="203ab-112">There are the following options:</span></span>  
  
-   <span data-ttu-id="203ab-113">**Égal à**</span><span class="sxs-lookup"><span data-stu-id="203ab-113">**Equals**</span></span>  
  
     <span data-ttu-id="203ab-114">Le filtre affiche les éléments pour lesquels la propriété et la valeur correspondent exactement.</span><span class="sxs-lookup"><span data-stu-id="203ab-114">The filter shows items where the property and the value are an exact match.</span></span>  
  
-   <span data-ttu-id="203ab-115">**Contains**</span><span class="sxs-lookup"><span data-stu-id="203ab-115">**Contains**</span></span>  
  
     <span data-ttu-id="203ab-116">Le filtre affiche les éléments pour lesquels la propriété contient la valeur.</span><span class="sxs-lookup"><span data-stu-id="203ab-116">The filter shows items where the property contains the value.</span></span> <span data-ttu-id="203ab-117">La propriété peut contenir du texte supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="203ab-117">The property may contain other text.</span></span>  
  
-   <span data-ttu-id="203ab-118">**Ne contient pas**</span><span class="sxs-lookup"><span data-stu-id="203ab-118">**Does not contain**</span></span>  
  
     <span data-ttu-id="203ab-119">Le filtre affiche les éléments pour lesquels la propriété ne contient pas la valeur.</span><span class="sxs-lookup"><span data-stu-id="203ab-119">The filter shows items that where the property does not contain the value.</span></span>  
  
-   <span data-ttu-id="203ab-120">**Inférieur à**</span><span class="sxs-lookup"><span data-stu-id="203ab-120">**Less than**</span></span>  
  
     <span data-ttu-id="203ab-121">Disponible pour les dates, ce filtre affiche les éléments dont la date est antérieure à la valeur fournie.</span><span class="sxs-lookup"><span data-stu-id="203ab-121">Available for dates, this filter shows items whose date is before the value provided.</span></span>  
  
-   <span data-ttu-id="203ab-122">**Inférieur ou égal à**</span><span class="sxs-lookup"><span data-stu-id="203ab-122">**Less than or equal**</span></span>  
  
     <span data-ttu-id="203ab-123">Disponible pour les dates, ce filtre affiche les éléments dont la date est antérieure à la valeur fournie ou contient cette valeur.</span><span class="sxs-lookup"><span data-stu-id="203ab-123">Available for dates, this filter shows items whose date contains or is before the value provided.</span></span>  
  
-   <span data-ttu-id="203ab-124">**Supérieur à**</span><span class="sxs-lookup"><span data-stu-id="203ab-124">**Greater than**</span></span>  
  
     <span data-ttu-id="203ab-125">Disponible pour les dates, ce filtre affiche les éléments dont la date est postérieure à la valeur fournie.</span><span class="sxs-lookup"><span data-stu-id="203ab-125">Available for dates, this filter shows items whose date is after the value provided.</span></span>  
  
-   <span data-ttu-id="203ab-126">**Supérieur ou égal à**</span><span class="sxs-lookup"><span data-stu-id="203ab-126">**Greater than or equal**</span></span>  
  
     <span data-ttu-id="203ab-127">Disponible pour les dates, ce filtre affiche les éléments dont la date est postérieure à la valeur fournie ou contient cette valeur.</span><span class="sxs-lookup"><span data-stu-id="203ab-127">Available for dates, this filter shows items whose date contains or is after the value provided.</span></span>  
  
-   <span data-ttu-id="203ab-128">**Entre**</span><span class="sxs-lookup"><span data-stu-id="203ab-128">**Between**</span></span>  
  
     <span data-ttu-id="203ab-129">Disponible pour les dates, ce filtre affiche les éléments dont la date est comprise entre deux dates fournies.</span><span class="sxs-lookup"><span data-stu-id="203ab-129">Available for dates, this filter shows items whose date is between two dates provided.</span></span> <span data-ttu-id="203ab-130">Sélectionnez **Entre** et appuyez sur Tab pour ajouter une autre ligne afin d’entrer la seconde date.</span><span class="sxs-lookup"><span data-stu-id="203ab-130">Select **Between** and press TAB to add another row allowing entry of the second date.</span></span>  
  
-   <span data-ttu-id="203ab-131">**Non compris entre**</span><span class="sxs-lookup"><span data-stu-id="203ab-131">**Not between**</span></span>  
  
     <span data-ttu-id="203ab-132">Disponible pour les dates, ce filtre affiche les éléments dont la date est antérieure ou postérieure aux deux dates fournies.</span><span class="sxs-lookup"><span data-stu-id="203ab-132">Available for dates, this filter shows items whose date is before or after two dates provided.</span></span> <span data-ttu-id="203ab-133">Sélectionnez **Non compris entre** et quittez la colonne **Opérateur** à l’aide des tabulations pour ajouter une ligne afin d’entrer la seconde date.</span><span class="sxs-lookup"><span data-stu-id="203ab-133">Select **Not Between** and tab out of the **Operator** column to add another row allowing entry of the second date.</span></span>  
  
 <span data-ttu-id="203ab-134">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="203ab-134">**Value**</span></span>  
 <span data-ttu-id="203ab-135">Tapez la valeur à comparer à la propriété.</span><span class="sxs-lookup"><span data-stu-id="203ab-135">Type the value to compare to the property.</span></span> <span data-ttu-id="203ab-136">Pour une date, cliquez sur la flèche vers le bas pour afficher un calendrier vous permettant de sélectionner la date.</span><span class="sxs-lookup"><span data-stu-id="203ab-136">For dates, click the down arrow to show a calendar for selecting the date.</span></span>  
  
 <span data-ttu-id="203ab-137">**Effacer le filtre**</span><span class="sxs-lookup"><span data-stu-id="203ab-137">**Clear Filter**</span></span>  
 <span data-ttu-id="203ab-138">Supprime tous les paramètres actuels du filtre.</span><span class="sxs-lookup"><span data-stu-id="203ab-138">Removes all current filter settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="203ab-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="203ab-139">See Also</span></span>  
 <span data-ttu-id="203ab-140">[Utiliser SQL Server Management Studio](../sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="203ab-140">[Use SQL Server Management Studio](../sql-server-management-studio-ssms.md) </span></span>  
 [<span data-ttu-id="203ab-141">Fonctionnalités et tâches de l’utilitaire SQL Server</span><span class="sxs-lookup"><span data-stu-id="203ab-141">SQL Server Utility Features and Tasks</span></span>](../../relational-databases/manage/sql-server-utility-features-and-tasks.md)  
  
  
