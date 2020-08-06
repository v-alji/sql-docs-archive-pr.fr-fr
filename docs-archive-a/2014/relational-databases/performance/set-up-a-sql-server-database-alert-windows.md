---
title: Configurer une alerte de base de données SQL Server (Windows) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server], creating
ms.assetid: 65d2c5c1-921f-4eff-9ef7-149170ab61e8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 090eeda2c134857df18d083ce06d460214aa4dfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614559"
---
# <a name="set-up-a-sql-server-database-alert-windows"></a><span data-ttu-id="7d2c5-102">Configurer une alerte de base de données SQL Server (Windows)</span><span class="sxs-lookup"><span data-stu-id="7d2c5-102">Set Up a SQL Server Database Alert (Windows)</span></span>
  <span data-ttu-id="7d2c5-103">À l'aide du Moniteur système, vous pouvez créer une alerte qui se déclenche quand le seuil d'un compteur du Moniteur système est franchi.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-103">Using System Monitor, you can create an alert to be raised when a threshold value for a System Monitor counter has been reached.</span></span> <span data-ttu-id="7d2c5-104">En réponse à l'alerte, le Moniteur système peut lancer une application, telle qu'une application personnalisée écrite pour prendre en charge la condition d'alerte.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-104">In response to the alert, System Monitor can launch an application, such as a custom application written to handle the alert condition.</span></span> <span data-ttu-id="7d2c5-105">Par exemple, vous pouvez créer une alerte déclenchée quand le nombre de blocages dépasse une valeur spécifique.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-105">For example, you can create an alert that is raised when the number of deadlocks exceeds a specific value.</span></span>  
  
 <span data-ttu-id="7d2c5-106">Vous pouvez également définir des alertes à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] et de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7d2c5-106">Alerts also can be defined using Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="7d2c5-107">Pour plus d’informations, consultez [Alertes](../../ssms/agent/alerts.md).</span><span class="sxs-lookup"><span data-stu-id="7d2c5-107">For more information, see [Alerts](../../ssms/agent/alerts.md).</span></span>  
  
### <a name="to-set-up-a-sql-server-database-alert"></a><span data-ttu-id="7d2c5-108">Pour installer une alerte de base de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="7d2c5-108">To set up a SQL Server database alert</span></span>  
  
1.  <span data-ttu-id="7d2c5-109">Dans l’arborescence de navigation de la fenêtre Performances, développez **Journaux et alertes de performance**.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-109">On the navigation tree of the Performance window, expand **Performance Logs and Alerts**.</span></span>  
  
2.  <span data-ttu-id="7d2c5-110">Cliquez avec le bouton droit sur **Alertes**, puis cliquez sur **Nouveaux paramètres d’alerte**.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-110">Right-click **Alerts**, and then click **New Alert Settings**.</span></span>  
  
3.  <span data-ttu-id="7d2c5-111">Dans la boîte de dialogue **Nouveaux paramètres d’alerte** , entrez un nom pour la nouvelle alerte, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-111">In the **New Alert Settings** dialog box, type a name for the new alert, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="7d2c5-112">Sous l’onglet **Général** de la boîte de dialogue de la nouvelle alerte, ajoutez un **commentaire**, puis cliquez sur **Ajouter** pour ajouter un compteur à l’alerte.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-112">On the **General** tab of the dialog box for the new alert, add a **Comment**, and click **Add** to add a counter to the alert.</span></span>  
  
     <span data-ttu-id="7d2c5-113">Chaque alerte doit avoir au moins un compteur.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-113">All alerts must have at least one counter.</span></span>  
  
5.  <span data-ttu-id="7d2c5-114">Dans la boîte de dialogue Ajouter des compteurs, sélectionnez un objet SQL Server dans la liste **Objet de performance** , puis sélectionnez un compteur dans la zone **Sélectionner les compteurs dans la liste**.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-114">In the Add Counters dialog box, select a SQL Server object from the **Performance Object** list, and then select a counter from the **Select counters from list**.</span></span>  
  
6.  <span data-ttu-id="7d2c5-115">Pour ajouter le compteur à l’alerte, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-115">To add the counter to the alert, click **Add**.</span></span> <span data-ttu-id="7d2c5-116">Vous pouvez continuer à ajouter des compteurs, ou bien cliquer sur **Fermer** pour revenir à la boîte de dialogue de la nouvelle alerte.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-116">You can continue to add counters, or you can click **Close** to return to the dialog box for the new alert.</span></span>  
  
7.  <span data-ttu-id="7d2c5-117">Dans la boîte de dialogue de la nouvelle alerte, cliquez sur **Supérieur à** ou sur **Inférieur à**dans la liste **Avertir si la valeur est** , puis entrez une valeur de seuil dans la zone **Limite**.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-117">In the new alert dialog box, click either **Over** or **Under**in the **Alert when the value is** list, and then enter a threshold value in **Limit**.</span></span>  
  
     <span data-ttu-id="7d2c5-118">L’alerte est générée lorsque la valeur du compteur est supérieure ou inférieure à la valeur du seuil (selon que vous avez sélectionné **Supérieur à** ou **Inférieur à**).</span><span class="sxs-lookup"><span data-stu-id="7d2c5-118">The alert is generated when the value for the counter is more than or less than the threshold value (depending on whether you clicked **Over** or **Under**).</span></span>  
  
8.  <span data-ttu-id="7d2c5-119">Dans les zones **Période d’échantillonnage des données** , définissez la fréquence d’échantillonnage.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-119">In the **Sample data every** boxes, set the sampling frequency.</span></span>  
  
9. <span data-ttu-id="7d2c5-120">Sous l’onglet **Action** , définissez les actions qui doivent se produire lorsque l’alerte est déclenchée.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-120">On the **Action** tab, set actions to occur every time the alert is triggered.</span></span>  
  
10. <span data-ttu-id="7d2c5-121">Sous l’onglet **Planification** , définissez la planification de début et de fin de l’analyse d’alerte.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-121">On the **Schedule** tab, set the start and stop schedule for the alert scan.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d2c5-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7d2c5-122">See Also</span></span>  
 [<span data-ttu-id="7d2c5-123">Créer une alerte de base de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="7d2c5-123">Create a SQL Server Database Alert</span></span>](../performance-monitor/create-a-sql-server-database-alert.md)  
  
  
