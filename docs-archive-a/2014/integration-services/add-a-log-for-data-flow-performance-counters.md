---
title: Ajouter un journal pour les compteurs de performances de workflow de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- performance counters [Integration Services]
- counters [Integration Services]
- logs [Integration Services], data flow counters
ms.assetid: b500d166-33ba-4b82-a92d-b0a333924e8d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 489bde1b0e5769f05d1063eb0af2376b659574de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705360"
---
# <a name="add-a-log-for-data-flow-performance-counters"></a><span data-ttu-id="1eeda-102">Ajouter un journal pour les compteurs de performances de flux de données</span><span class="sxs-lookup"><span data-stu-id="1eeda-102">Add a Log for Data Flow Performance Counters</span></span>
  <span data-ttu-id="1eeda-103">Cette procédure décrit comment ajouter un journal pour les compteurs de performances fournis par le moteur de flux de données.</span><span class="sxs-lookup"><span data-stu-id="1eeda-103">This procedure describes how to add a log for the performance counters that the data flow engine provides.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1eeda-104">Si vous installez [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sur un ordinateur qui exécute [!INCLUDE[winxpsvr](../includes/winxpsvr-md.md)], puis que vous mettez à niveau cet ordinateur vers [!INCLUDE[firstref_longhorn](../includes/firstref-longhorn-md.md)], le processus de mise à niveau supprime les compteurs de performances de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="1eeda-104">If you install [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] on a computer that is running [!INCLUDE[winxpsvr](../includes/winxpsvr-md.md)], and then upgrade that computer to [!INCLUDE[firstref_longhorn](../includes/firstref-longhorn-md.md)], the upgrade process removes the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] performance counters from the computer.</span></span> <span data-ttu-id="1eeda-105">Pour restaurer les compteurs de performances de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sur l’ordinateur, exécutez l’installation de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en mode réparation.</span><span class="sxs-lookup"><span data-stu-id="1eeda-105">To restore the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] performance counters on the computer, run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Setup in repair mode.</span></span>  
  
### <a name="to-add-logging-of-performance-counters"></a><span data-ttu-id="1eeda-106">Pour ajouter un journal des compteurs de performances</span><span class="sxs-lookup"><span data-stu-id="1eeda-106">To add logging of performance counters</span></span>  
  
1.  <span data-ttu-id="1eeda-107">Dans le **Panneau de configuration**, si vous utilisez l’affichage classique, cliquez sur **Outils d’administration**.</span><span class="sxs-lookup"><span data-stu-id="1eeda-107">In **Control Panel**, if you are using Classic view, click **Administrative Tools**.</span></span> <span data-ttu-id="1eeda-108">Si vous utilisez l’affichage des catégories, cliquez sur **Performances et maintenance** , puis sur **Outils d’administration**.</span><span class="sxs-lookup"><span data-stu-id="1eeda-108">If you are using Category view, click **Performance and Maintenance** and then click **Administrative Tools**.</span></span>  
  
2.  <span data-ttu-id="1eeda-109">Cliquez sur **Performances**.</span><span class="sxs-lookup"><span data-stu-id="1eeda-109">Click **Performance**.</span></span>  
  
3.  <span data-ttu-id="1eeda-110">Dans la boîte de dialogue **Performances** , développez **Journaux et alertes de performances**, cliquez avec le bouton droit sur **Journaux de compteurs**, puis cliquez sur **Nouveaux paramètres de journal**.</span><span class="sxs-lookup"><span data-stu-id="1eeda-110">In the **Performance** dialog box, expand **Performance Logs and Alerts**, right-click **Counter Logs**, and then click **New Log Settings**.</span></span> <span data-ttu-id="1eeda-111">Tapez le nom du journal.</span><span class="sxs-lookup"><span data-stu-id="1eeda-111">Type the name of the log.</span></span> <span data-ttu-id="1eeda-112">Par exemple, tapez **MonJournal**.</span><span class="sxs-lookup"><span data-stu-id="1eeda-112">For example, type **MyLog**.</span></span>  
  
4.  <span data-ttu-id="1eeda-113">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1eeda-113">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="1eeda-114">Dans la boîte de dialogue **MonJournal** , cliquez sur **Ajouter des compteurs**.</span><span class="sxs-lookup"><span data-stu-id="1eeda-114">In the **MyLog** dialog box, click **Add Counters**.</span></span>  
  
6.  <span data-ttu-id="1eeda-115">Cliquez sur **Utiliser les compteurs locaux de l’ordinateur** pour journaliser les compteurs de performances sur l’ordinateur local ou cliquez sur **Choisir les compteurs sur :** et sélectionnez un ordinateur dans la liste pour journaliser les compteurs de performances sur l’ordinateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="1eeda-115">Click **Use local computer counters** to log performance counters on the local computer, or click **Select counters from computer** and then select a computer from the list to log performance counters on the specified computer.</span></span>  
  
7.  <span data-ttu-id="1eeda-116">Dans la boîte de dialogue **Ajouter des compteurs** , sélectionnez **SQL Server : pipeline SSIS** dans la liste **Objet de performance** .</span><span class="sxs-lookup"><span data-stu-id="1eeda-116">In the **Add Counters** dialog box, select **SQL Server:SSIS Pipeline** in the **Performance object** list.</span></span>  
  
8.  <span data-ttu-id="1eeda-117">Pour sélectionner les compteurs de performances, effectuez l'une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="1eeda-117">To select performance counters, do one of the following:</span></span>  
  
    -   <span data-ttu-id="1eeda-118">Sélectionnez **Tous les compteurs** pour journaliser tous les compteurs de performances.</span><span class="sxs-lookup"><span data-stu-id="1eeda-118">Select **All Counters** to log all performance counters.</span></span>  
  
    -   <span data-ttu-id="1eeda-119">Sélectionnez **Sélectionner les compteurs dans la liste** et sélectionnez les compteurs de performances à utiliser.</span><span class="sxs-lookup"><span data-stu-id="1eeda-119">Select **Select counters in list** and select the performance counters to use.</span></span>  
  
9. <span data-ttu-id="1eeda-120">Cliquez sur **Add**.</span><span class="sxs-lookup"><span data-stu-id="1eeda-120">Click **Add**.</span></span>  
  
10. <span data-ttu-id="1eeda-121">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="1eeda-121">Click **Close**.</span></span>  
  
11. <span data-ttu-id="1eeda-122">Dans la boîte de dialogue **MonJournal** , vérifiez la liste des compteurs de performances journalisés dans la liste **Compteurs** .</span><span class="sxs-lookup"><span data-stu-id="1eeda-122">In the **MyLog** dialog box, review the list of logging performance counters in the **Counters** list.</span></span>  
  
12. <span data-ttu-id="1eeda-123">Pour ajouter des compteurs supplémentaires, répétez les étapes 5 à 10.</span><span class="sxs-lookup"><span data-stu-id="1eeda-123">To add additional counters, repeat steps 5 through 10.</span></span>  
  
13. <span data-ttu-id="1eeda-124">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1eeda-124">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1eeda-125">Vous devez démarrer le service Journaux et alertes de performance à l'aide d'un compte local ou d'un compte de domaine membre du groupe Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="1eeda-125">You must start the Performance Logs and Alerts service using a local account or a domain account that is a member of the Administrators group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eeda-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1eeda-126">See Also</span></span>  
 <span data-ttu-id="1eeda-127">[Compteurs de performances](performance/performance-counters.md) </span><span class="sxs-lookup"><span data-stu-id="1eeda-127">[Performance Counters](performance/performance-counters.md) </span></span>  
 [<span data-ttu-id="1eeda-128">Afficher les entrées de journal dans la fenêtre Journaux d’événements</span><span class="sxs-lookup"><span data-stu-id="1eeda-128">View Log Entries in the Log Events Window</span></span>](../../2014/integration-services/view-log-entries-in-the-log-events-window.md)  
  
  
