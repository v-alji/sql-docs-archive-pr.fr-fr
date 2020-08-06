---
title: Chronologie de sauvegarde | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.POINTINTIMERESTORE.F1
- sql12.swb.backuptimeline.f1
helpviewer_keywords:
- Backup Timeline
ms.assetid: ae3565f2-ddb2-4469-a992-7531d4f9ebb8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9b075f8c9ec32cfe483c64e34e9f9b4e4b6e80e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614682"
---
# <a name="backup-timeline"></a><span data-ttu-id="1fab9-102">Chronologie de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="1fab9-102">Backup Timeline</span></span>
  <span data-ttu-id="1fab9-103">Utilisez la boîte de dialogue **Chronologie de sauvegarde** pour rechercher et spécifier des sauvegardes afin de restaurer une base de données jusqu’à une date et heure.</span><span class="sxs-lookup"><span data-stu-id="1fab9-103">Use the **Backup Timeline** dialog box to locate and specify backups to restore a database to a point-in-time.</span></span> <span data-ttu-id="1fab9-104">La boîte de dialogue **Chronologie de sauvegarde** est accessible en cliquant sur **Chronologie** dans le volet **Restaurer la base de données (page Général)** .</span><span class="sxs-lookup"><span data-stu-id="1fab9-104">The **Backup Timeline** dialog box is accessed by clicking **Timeline** on the **Restore Database (General Page)** pane.</span></span> <span data-ttu-id="1fab9-105">Cette boîte de dialogue vous permet de consulter une chronologie des opérations de restauration effectuées sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="1fab9-105">This dialog box allows you to view a timeline of the restore operations performed on the database.</span></span>  
  
 <span data-ttu-id="1fab9-106">L'Assistant Récupération de base de données garantit que seules les sauvegardes requises pour la restauration à cette limite dans le temps sont sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="1fab9-106">The Database Recovery Advisor ensures that only backups that are required for restoring to that point in time are selected.</span></span> <span data-ttu-id="1fab9-107">Ces sauvegardes sélectionnées constituent le plan de restauration recommandé pour votre opération de restauration.</span><span class="sxs-lookup"><span data-stu-id="1fab9-107">These selected backups make up the recommended restore plan for your restore operation.</span></span> <span data-ttu-id="1fab9-108">Vous devez utiliser uniquement les sauvegardes sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="1fab9-108">You should use only the selected backups.</span></span> <span data-ttu-id="1fab9-109">Pour plus d’informations sur l’Assistant de récupération de base de données, consultez [Vue d’ensemble de la restauration et de la récupération &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1fab9-109">For information about the Database Recovery Advisor, see [Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span></span>  
  
## <a name="restore-to"></a><span data-ttu-id="1fab9-110">Restaurer sur</span><span class="sxs-lookup"><span data-stu-id="1fab9-110">Restore to</span></span>  
 <span data-ttu-id="1fab9-111">L'option**Dernière sauvegarde effectuée** est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="1fab9-111">**Last backup taken** is selected by default.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="1fab9-112">sélectionne les sauvegardes appropriées pour restaurer la base de données, et restaure la base de données jusqu'au point de la dernière sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="1fab9-112">will select the appropriate backups to restore the database, and will restore the database to the point of the last backup.</span></span> <span data-ttu-id="1fab9-113">Cliquez sur **Date et heure spécifiques** pour définir les date et heure manuellement (sélection d’un point spécifique dans le temps).</span><span class="sxs-lookup"><span data-stu-id="1fab9-113">Click **A specific date and time** to manually set the date and time (selecting a specific point in time).</span></span>  
  
 <span data-ttu-id="1fab9-114">L'option**Date et heure spécifiques** vous permet d'arrêter la restauration à une date et une heure que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="1fab9-114">**Specific date and time** permits you stop the restore at a specific date and time that you select.</span></span> <span data-ttu-id="1fab9-115">La chronologie indique une représentation des opérations de sauvegarde effectuées sur une période 24 heures autour de la date et de l'heure sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="1fab9-115">The timeline shows a representation of the backup operations performed in the 24 hours around the select date and time.</span></span>  
  
 <span data-ttu-id="1fab9-116">**Date**</span><span class="sxs-lookup"><span data-stu-id="1fab9-116">**Date**</span></span>  
 <span data-ttu-id="1fab9-117">Entrez une date ou sélectionnez-en une dans la zone de liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="1fab9-117">Enter or select a date from the drop-down list.</span></span>  
  
 <span data-ttu-id="1fab9-118">**Time**</span><span class="sxs-lookup"><span data-stu-id="1fab9-118">**Time**</span></span>  
 <span data-ttu-id="1fab9-119">Entrez ou sélectionnez une date pour indiquer le moment précis auquel la restauration doit s'arrêter.</span><span class="sxs-lookup"><span data-stu-id="1fab9-119">Enter or select a date to designate the specific point-in-time for the restore to stop.</span></span>  
  
 <span data-ttu-id="1fab9-120">**Barre planning - Intervalle**</span><span class="sxs-lookup"><span data-stu-id="1fab9-120">**Timeline Interval**</span></span>  
 <span data-ttu-id="1fab9-121">Affiche les options pour les types d'intervalle consultables sur la chronologie.</span><span class="sxs-lookup"><span data-stu-id="1fab9-121">Displays the options for the interval types viewable on the timeline.</span></span>  
  
## <a name="timeline-and-legend"></a><span data-ttu-id="1fab9-122">Chronologie et légende</span><span class="sxs-lookup"><span data-stu-id="1fab9-122">Timeline and Legend</span></span>  
 <span data-ttu-id="1fab9-123">Utilisez la barre de défilement sous la chronologie pour déplacer le curseur vers l'avant et vers l'arrière le long de la chronologie.</span><span class="sxs-lookup"><span data-stu-id="1fab9-123">Use the scroll bar beneath the timeline to move the cursor forward and backward along the timeline.</span></span> <span data-ttu-id="1fab9-124">Cliquez sur une sauvegarde pour déplacer la barre de défilement à la fin de cette sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="1fab9-124">Click on a backup to move the scroll bar to the end of that backup.</span></span> <span data-ttu-id="1fab9-125">Pointez la souris sur un marqueur pour afficher une info-bulle qui fournit des informations sur le jeu de sauvegarde sélectionné.</span><span class="sxs-lookup"><span data-stu-id="1fab9-125">Hover the mouse over a marker to display a ScreenTip providing information about the selected backup set.</span></span> <span data-ttu-id="1fab9-126">Les informations de sauvegarde sont indiquées sur la chronologie par les marqueurs suivants.</span><span class="sxs-lookup"><span data-stu-id="1fab9-126">Backup information is shown on the timeline by the following markers.</span></span>  
  
 <span data-ttu-id="1fab9-127">Plus grand triangle</span><span class="sxs-lookup"><span data-stu-id="1fab9-127">Larger triangle</span></span>  
 <span data-ttu-id="1fab9-128">Représente les sauvegardes complètes effectuées sur la base de données, en indiquant le point spécifique à l'heure où chaque sauvegarde complète a été effectuée.</span><span class="sxs-lookup"><span data-stu-id="1fab9-128">Represents the full backups performed on the database, denoting the specific point in time each full backup was performed.</span></span>  
  
 <span data-ttu-id="1fab9-129">Plus petit triangle</span><span class="sxs-lookup"><span data-stu-id="1fab9-129">Smaller triangle</span></span>  
 <span data-ttu-id="1fab9-130">Représente les sauvegardes différentielles effectuées sur la base de données, en indiquant le point spécifique à l'heure où chaque sauvegarde différentielle a été effectuée.</span><span class="sxs-lookup"><span data-stu-id="1fab9-130">Represents the differential backups performed on the database, denoting the specific point in time that each differential backup was performed.</span></span>  
  
 <span data-ttu-id="1fab9-131">Zones hachurées vertes</span><span class="sxs-lookup"><span data-stu-id="1fab9-131">Green shaded areas</span></span>  
 <span data-ttu-id="1fab9-132">Représente la couverture de sauvegarde du journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="1fab9-132">Represents the transaction log backup coverage.</span></span>  
  
 <span data-ttu-id="1fab9-133">Ligne rouge</span><span class="sxs-lookup"><span data-stu-id="1fab9-133">Red line</span></span>  
 <span data-ttu-id="1fab9-134">Peut être positionnée uniquement le long de la chronologie où la restauration est possible.</span><span class="sxs-lookup"><span data-stu-id="1fab9-134">Can only be positioned along the timeline where the restore is possible.</span></span> <span data-ttu-id="1fab9-135">En déplaçant la ligne rouge le long de la chronologie, vous pouvez régler les date et heure affichées dans les zones **Date** et **Heure** .</span><span class="sxs-lookup"><span data-stu-id="1fab9-135">Moving the red line along the timeline adjusts the date and time displayed in the **Date** and **Time** boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fab9-136"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1fab9-136">See Also</span></span>  
 [<span data-ttu-id="1fab9-137">Restaurer la base de données &#40;page Général&#41;</span><span class="sxs-lookup"><span data-stu-id="1fab9-137">Restore Database &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
  
