---
title: Moniteur d’activité des travaux | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.ACTIVITYMON.F1
- sql12.ag.jobactivitymonitor.alljobs.f1
ms.assetid: 11f2182c-5f71-46f8-8d2b-74f0fc48f2d6
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6f89d5448f0885c85229c2808ee6f85bf6fa071
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699221"
---
# <a name="job-activity-monitor"></a><span data-ttu-id="949eb-102">Moniteur d'activité des travaux</span><span class="sxs-lookup"><span data-stu-id="949eb-102">Job Activity Monitor</span></span>
  <span data-ttu-id="949eb-103">Utilisez cette page pour afficher l'activité actuelle des travaux de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="949eb-103">Use this page to view the current activity of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span> <span data-ttu-id="949eb-104">Cliquez sur **Filtre** pour restreindre le nombre de travaux affichés.</span><span class="sxs-lookup"><span data-stu-id="949eb-104">Click **Filter** to limit the jobs displayed.</span></span> <span data-ttu-id="949eb-105">La grille **Activité du travail de l’Agent** est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="949eb-105">The **Agent Job Activity** grid is read-only.</span></span> <span data-ttu-id="949eb-106">Cliquez sur les en-têtes de colonne pour trier la grille.</span><span class="sxs-lookup"><span data-stu-id="949eb-106">Click on the column headers to sort the grid.</span></span> <span data-ttu-id="949eb-107">Pour modifier un travail, double-cliquez dessus pour ouvrir la boîte de dialogue **Propriétés du travail** .</span><span class="sxs-lookup"><span data-stu-id="949eb-107">To modify a job, double-click the job to open the **Job Properties** dialog box.</span></span> <span data-ttu-id="949eb-108">En cliquant avec le bouton droit sur un travail affiché dans la grille, vous pouvez démarrer l'exécution de toutes les étapes du travail, démarrer le travail à partir d'une étape spécifique, désactiver ou activer le travail, actualiser le travail, supprimer le travail, afficher l'historique du travail ou afficher les propriétés du travail.</span><span class="sxs-lookup"><span data-stu-id="949eb-108">Right-click a job in the grid to start it running all job steps, start at a particular job step, disable or enable the job, refresh the job, delete the job, view the history of the job, or view the properties of the job.</span></span> <span data-ttu-id="949eb-109">Cliquez sur **Actualiser** pour afficher les informations actuelles dans la grille.</span><span class="sxs-lookup"><span data-stu-id="949eb-109">Click **Refresh** to update the grid with current information.</span></span>  
  
## <a name="options"></a><span data-ttu-id="949eb-110">Options</span><span class="sxs-lookup"><span data-stu-id="949eb-110">Options</span></span>  
 <span data-ttu-id="949eb-111">**Nom**</span><span class="sxs-lookup"><span data-stu-id="949eb-111">**Name**</span></span>  
 <span data-ttu-id="949eb-112">Nom du travail.</span><span class="sxs-lookup"><span data-stu-id="949eb-112">Name of the job.</span></span>  
  
 <span data-ttu-id="949eb-113">**Activé**</span><span class="sxs-lookup"><span data-stu-id="949eb-113">**Enabled**</span></span>  
 <span data-ttu-id="949eb-114">Indique si le travail est activé (**oui**) ou désactivé (**non**).</span><span class="sxs-lookup"><span data-stu-id="949eb-114">Whether the job is enabled (**yes**) or not enabled (**no**).</span></span>  
  
 <span data-ttu-id="949eb-115">**État** <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="949eb-115">**Status** <sup>1</sup></span></span>  
 <span data-ttu-id="949eb-116">État actuel du travail.</span><span class="sxs-lookup"><span data-stu-id="949eb-116">Current status of the job.</span></span>  
  
 <span data-ttu-id="949eb-117">**Résultats de la dernière exécution**</span><span class="sxs-lookup"><span data-stu-id="949eb-117">**Last Run Outcome**</span></span>  
 <span data-ttu-id="949eb-118">État du travail lors de sa dernière exécution.</span><span class="sxs-lookup"><span data-stu-id="949eb-118">Job status when last run.</span></span>  
  
 <span data-ttu-id="949eb-119">**Dernière exécution**</span><span class="sxs-lookup"><span data-stu-id="949eb-119">**Last Run**</span></span>  
 <span data-ttu-id="949eb-120">Date et heure de la dernière exécution du travail via la date et l'heure locales du serveur.</span><span class="sxs-lookup"><span data-stu-id="949eb-120">Date and time job was last run using the local date and time of the server.</span></span>  
  
 <span data-ttu-id="949eb-121">**Prochaine exécution** <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="949eb-121">**Next Run** <sup>1</sup></span></span>  
 <span data-ttu-id="949eb-122">Date et heure de la prochaine planification du travail via la date et l'heure locales du serveur.</span><span class="sxs-lookup"><span data-stu-id="949eb-122">Date and time the job is next scheduled to run using the local date and time of the server.</span></span>  
  
 <span data-ttu-id="949eb-123">**Catégorie**</span><span class="sxs-lookup"><span data-stu-id="949eb-123">**Category**</span></span>  
 <span data-ttu-id="949eb-124">La catégorie de travaux attribuée au travail.</span><span class="sxs-lookup"><span data-stu-id="949eb-124">The job category assigned to the job.</span></span>  
  
 <span data-ttu-id="949eb-125">**Lancer**</span><span class="sxs-lookup"><span data-stu-id="949eb-125">**Runnable**</span></span>  
 <span data-ttu-id="949eb-126">**Oui** si le travail peut être exécuté ; **Non** si le travail ne peut pas être exécuté.</span><span class="sxs-lookup"><span data-stu-id="949eb-126">**Yes** if the job can be run; **No** if the job cannot be run.</span></span> <span data-ttu-id="949eb-127">Un travail ne peut pas être exécuté s'il ne comporte aucune étape ou s'il n'est associé à aucun serveur cible.</span><span class="sxs-lookup"><span data-stu-id="949eb-127">A job is not runnable if it has no steps or if it has no target server.</span></span>  
  
 <span data-ttu-id="949eb-128">**Planifié**</span><span class="sxs-lookup"><span data-stu-id="949eb-128">**Scheduled**</span></span>  
 <span data-ttu-id="949eb-129">**Oui** s’il existe une planification du travail pour ce travail ; **Non** s’il n’y a pas de planification pour ce travail.</span><span class="sxs-lookup"><span data-stu-id="949eb-129">**Yes** if the job is assigned to a job schedule; **No** if the job has no schedule.</span></span>  
  
 <span data-ttu-id="949eb-130"><sup>1</sup> Seuls les membres du [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rôle serveur fixe sysadmin et du groupe administrateurs du serveur peuvent voir les valeurs dans cette colonne.</span><span class="sxs-lookup"><span data-stu-id="949eb-130"><sup>1</sup>Only members of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sysadmin fixed server role and the server administrators group can see values in this column.</span></span> <span data-ttu-id="949eb-131">Les membres du rôle SQLAgentOperatorRole ne peuvent pas consulter les valeurs de cette colonne.</span><span class="sxs-lookup"><span data-stu-id="949eb-131">Members of the SQLAgentOperatorRole role cannot see values in this column.</span></span>  
  
#### <a name="to-open-the-job-activity-monitor"></a><span data-ttu-id="949eb-132">Pour ouvrir le Moniteur d'activité du travail</span><span class="sxs-lookup"><span data-stu-id="949eb-132">To open the Job Activity Monitor</span></span>  
  
-   <span data-ttu-id="949eb-133">Dans **l’Explorateur d’objets**, développez votre serveur, puis **Agent SQL Server**, cliquez avec le bouton droit sur **Moniteur d’activité des travaux**, puis cliquez sur **Afficher l’activité du travail**.</span><span class="sxs-lookup"><span data-stu-id="949eb-133">In **Object Explorer**, expand your server, expand **SQL Server Agent**, right-click **Job Activity Monitor**, and then click **View Job Activity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="949eb-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="949eb-134">See Also</span></span>  
 [<span data-ttu-id="949eb-135">Surveiller l'activité des travaux</span><span class="sxs-lookup"><span data-stu-id="949eb-135">Monitor Job Activity</span></span>](monitor-job-activity.md)  
  
  
