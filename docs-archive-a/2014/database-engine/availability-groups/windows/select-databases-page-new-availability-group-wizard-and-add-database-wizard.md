---
title: Page Sélectionner les bases de données (Assistant Nouveau groupe de disponibilité-Assistant Ajout d’une base de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.adddatabasewizard.selectdatabases.f1
- sql12.swb.newagwizard.selectdatabases.f1
ms.assetid: 929c5e15-d087-438d-b1f2-aa97c5f8bff8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c626b8f0953f18a6dd4661124a09b7f542caeb82
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707892"
---
# <a name="select-databases-page-new-availability-group-wizard-add-database-wizard"></a><span data-ttu-id="7223f-102">Page Sélectionner les bases de données (Assistant Nouveau groupe de disponibilité-Assistant Ajout d’une base de données)</span><span class="sxs-lookup"><span data-stu-id="7223f-102">Select Databases Page (New Availability Group Wizard-Add Database Wizard)</span></span>
  <span data-ttu-id="7223f-103"> Cette rubrique d’aide décrit les options de la page **Spécifier les bases de données**.</span><span class="sxs-lookup"><span data-stu-id="7223f-103">This help topic describes the options of the **Specify Databases** page.</span></span> <span data-ttu-id="7223f-104">Cette rubrique s'applique à l' [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] et à l' [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7223f-104">This topic applies to the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] and [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
##  <a name="select-databases-options"></a><a name="PageOptions"></a><span data-ttu-id="7223f-105">Options de sélection de bases de données</span><span class="sxs-lookup"><span data-stu-id="7223f-105">Select Databases Options</span></span>  
 <span data-ttu-id="7223f-106">La grille **Bases de données utilisateur sur cette instance de SQL Server** répertorie chaque base de données utilisateur locale.</span><span class="sxs-lookup"><span data-stu-id="7223f-106">The **User databases on this instance of SQL Server** grid lists every local user database.</span></span> <span data-ttu-id="7223f-107">Les colonnes sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="7223f-107">The columns are as follows:</span></span>  
  
 <span data-ttu-id="7223f-108">**Nom**</span><span class="sxs-lookup"><span data-stu-id="7223f-108">**Name**</span></span>  
 <span data-ttu-id="7223f-109">Affiche le nom d'une base de données utilisateur locale.</span><span class="sxs-lookup"><span data-stu-id="7223f-109">Displays the name of a local user database.</span></span>  
  
 <span data-ttu-id="7223f-110">**Taille**</span><span class="sxs-lookup"><span data-stu-id="7223f-110">**Size**</span></span>  
 <span data-ttu-id="7223f-111">Affiche la taille de la base de données, si cette information est connue de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="7223f-111">Displays the database size, if the size is available to the wizard.</span></span>  
  
 <span data-ttu-id="7223f-112">**État**</span><span class="sxs-lookup"><span data-stu-id="7223f-112">**Status**</span></span>  
 <span data-ttu-id="7223f-113">Affiche un lien hypertexte dont le texte indique si une base de données particulière réunit les conditions préalables requises en vue de l'ajout à un groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="7223f-113">Displays a hyperlink whose text that indicates whether a given database meets the prerequisites for being added to an availability group.</span></span> <span data-ttu-id="7223f-114">Si l'état est «**Répond aux conditions requises**», vous pouvez ajouter la base de données au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="7223f-114">If the status is "**Meets prerequisites**" you can add the database to the availability group.</span></span> <span data-ttu-id="7223f-115">Si une base de données ne réunit pas l'ensemble des conditions préalables requises, le lien hypertexte **État** fournit une brève explication de la raison pour laquelle la base de données n'est pas éligible.</span><span class="sxs-lookup"><span data-stu-id="7223f-115">If a database does not meet all of the prerequisites, the **Status** hyperlink provides a brief explanation of why the database is ineligible.</span></span> <span data-ttu-id="7223f-116">Pour plus d'informations, cliquez sur le lien hypertexte.</span><span class="sxs-lookup"><span data-stu-id="7223f-116">For more information, click the hyperlink.</span></span>  
  
 <span data-ttu-id="7223f-117">Vous pouvez laisser l'Assistant sur la page **Sélectionner une base de données** lorsque vous agissez sur une base de données afin qu'elle remplisse une condition préalable.</span><span class="sxs-lookup"><span data-stu-id="7223f-117">You can leave the wizard on the **Select Database** page while you take action on a database to meet a prerequisite.</span></span> <span data-ttu-id="7223f-118">Lorsque vous revenez à la page **Sélectionner les bases de données** , cliquez sur **Actualiser** pour mettre à jour la grille.</span><span class="sxs-lookup"><span data-stu-id="7223f-118">When you return to the **Select Databases** page, click **Refresh** to update the grid.</span></span>  
  
 <span data-ttu-id="7223f-119">**Actualiser**</span><span class="sxs-lookup"><span data-stu-id="7223f-119">**Refresh**</span></span>  
 <span data-ttu-id="7223f-120">Cliquez pour actualiser la grille.</span><span class="sxs-lookup"><span data-stu-id="7223f-120">Click to refresh the grid.</span></span> <span data-ttu-id="7223f-121">Cette action est utile lorsque vous agissez sur une base de données afin qu'elle remplisse une condition préalable.</span><span class="sxs-lookup"><span data-stu-id="7223f-121">This is useful after you take action on a database to meet a prerequisite.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="7223f-122">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="7223f-122">Related Tasks</span></span>  
  
-   [<span data-ttu-id="7223f-123">Utiliser la boîte de dialogue Nouveau groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="7223f-123">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="7223f-124">Utiliser l’Assistant Ajouter une base de données au groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="7223f-124">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="7223f-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7223f-125">See Also</span></span>  
 <span data-ttu-id="7223f-126">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7223f-126">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="7223f-127">Conditions préalables requises, restrictions et recommandations pour groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7223f-127">Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](prereqs-restrictions-recommendations-always-on-availability.md)  
  
  
