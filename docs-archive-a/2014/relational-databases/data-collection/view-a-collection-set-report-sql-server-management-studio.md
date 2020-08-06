---
title: Afficher un rapport de jeu d’éléments de collecte (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.reporthistory.calendar.f1
helpviewer_keywords:
- collection sets [SQL Server], viewing reports
- reports [SQL Server], viewing collection set
ms.assetid: c3b1e791-9aa1-4bba-9622-4954568e1820
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cb8755c67e6c03bb318fdb86d703f6d647d5a3eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612966"
---
# <a name="view-a-collection-set-report-sql-server-management-studio"></a><span data-ttu-id="8a52a-102">Afficher un rapport de jeu d'éléments de collecte (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="8a52a-102">View a Collection Set Report (SQL Server Management Studio)</span></span>
  <span data-ttu-id="8a52a-103">Après avoir configuré l'entrepôt de données de gestion, vous pouvez afficher un rapport sur un jeu d'éléments de collecte dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a52a-103">After you have configured the management data warehouse, you can view a collection set report in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="8a52a-104">Des rapports sont fournis pour les jeux d'éléments de collecte de données système installés pendant l'installation.</span><span class="sxs-lookup"><span data-stu-id="8a52a-104">Reports are provided for the System Data collection sets that are installed during Setup.</span></span> <span data-ttu-id="8a52a-105">Les rapports proposés sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="8a52a-105">The reports include the following:</span></span>  
  
-   <span data-ttu-id="8a52a-106">Résumé sur l'utilisation du disque</span><span class="sxs-lookup"><span data-stu-id="8a52a-106">Disk Usage Summary</span></span>  
  
-   <span data-ttu-id="8a52a-107">Historique des statistiques sur les requêtes</span><span class="sxs-lookup"><span data-stu-id="8a52a-107">Query Statistics History</span></span>  
  
-   <span data-ttu-id="8a52a-108">Historique de l'activité du serveur</span><span class="sxs-lookup"><span data-stu-id="8a52a-108">Server Activity History</span></span>  
  
 <span data-ttu-id="8a52a-109">Cette procédure affiche le rapport pour le jeu d’éléments de collecte **Utilisation du disque** .</span><span class="sxs-lookup"><span data-stu-id="8a52a-109">This procedure displays the report for the **Disk Usage** collection set.</span></span> <span data-ttu-id="8a52a-110">Vous pouvez suivre la même procédure générale pour afficher les rapports des autres jeux d'éléments de collecte de données système.</span><span class="sxs-lookup"><span data-stu-id="8a52a-110">You can follow the same general procedure to view the reports for the other System Data collection sets.</span></span>  
  
### <a name="to-view-a-collection-set-report"></a><span data-ttu-id="8a52a-111">Pour afficher un rapport de jeu d'éléments de collecte</span><span class="sxs-lookup"><span data-stu-id="8a52a-111">To view a collection set report</span></span>  
  
1.  <span data-ttu-id="8a52a-112">Les tables d'un rapport sont créées lorsque les données collectées sont téléchargées pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="8a52a-112">The tables for a report are created the first time that the collected data is uploaded.</span></span> <span data-ttu-id="8a52a-113">Si vous essayez de consulter un rapport avant ce premier téléchargement, une erreur se produit et aucun rapport n'est affiché.</span><span class="sxs-lookup"><span data-stu-id="8a52a-113">If you try to view a report before this first upload, an error occurs and no report is displayed.</span></span> <span data-ttu-id="8a52a-114">Pour charger des données pour le jeu d’éléments de collecte Utilisation du disque, dans l’Explorateur d’objets, développez le dossier **Gestion** , **Collecte de données**, puis **Jeux d’éléments de collecte de données système**, cliquez avec le bouton droit sur le jeu d’éléments de collecte **Utilisation du disque** et cliquez enfin sur **Collecter et télécharger maintenant**.</span><span class="sxs-lookup"><span data-stu-id="8a52a-114">To upload data for the Disk Usage collection set, in Object Explorer, expand the **Management** folder, expand **Data Collection**, expand **System Data Collection Sets**, right-click the **Disk Usage** collection set, and then click **Collect and Upload Now**.</span></span>  
  
2.  <span data-ttu-id="8a52a-115">Pour afficher le rapport, dans l’Explorateur d’objets, développez le dossier **Gestion** , cliquez avec le bouton droit sur **Collecte de données**, pointez sur **Rapports**, sur **Entrepôt de données de gestion**, puis cliquez sur **Résumé sur l’utilisation du disque**.</span><span class="sxs-lookup"><span data-stu-id="8a52a-115">To view the report, in Object Explorer, expand the **Management** folder, right-click **Data Collection**, point to **Reports**, point to **Management Data Warehouse**, and then click **Disk Usage Summary**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8a52a-116">Certains rapports peuvent afficher un bouton Calendrier sous la chronologie de collecte de données.</span><span class="sxs-lookup"><span data-stu-id="8a52a-116">Some reports might display a calendar button under the data collection timeline.</span></span> <span data-ttu-id="8a52a-117">Cliquez sur ce bouton pour accéder au **Calendrier des rapports de collecte de données**.</span><span class="sxs-lookup"><span data-stu-id="8a52a-117">Click this button to access the **Data Collection Report Calendar**.</span></span>  
  
#### <a name="data-collection-report-calendar"></a><span data-ttu-id="8a52a-118">Calendrier des rapports de collecte de données</span><span class="sxs-lookup"><span data-stu-id="8a52a-118">Data Collection Report Calendar</span></span>  
 <span data-ttu-id="8a52a-119">Utilisez cette boîte de dialogue pour spécifier la date de début, l'heure de début et la durée des données pour lesquelles vous voulez créer un rapport.</span><span class="sxs-lookup"><span data-stu-id="8a52a-119">Use this dialog box to specify the start date, start time, and duration of the data that you want to report on.</span></span> <span data-ttu-id="8a52a-120">Par exemple, vous pouvez générer un rapport sur l'activité d'utilisation du disque d'un serveur pour une période spécifique de 12 heures mercredi dernier.</span><span class="sxs-lookup"><span data-stu-id="8a52a-120">For example, you may want to report on the disk usage activity of a server for a specific 12-hour period last Wednesday.</span></span>  
  
 <span data-ttu-id="8a52a-121">**Date de début**</span><span class="sxs-lookup"><span data-stu-id="8a52a-121">**Start date**</span></span>  
 <span data-ttu-id="8a52a-122">Entrez une date de début pour les données du rapport ou sélectionnez-la dans le calendrier.</span><span class="sxs-lookup"><span data-stu-id="8a52a-122">Enter a beginning date for the report data, or select one from the calendar.</span></span>  
  
 <span data-ttu-id="8a52a-123">**Heure de début**</span><span class="sxs-lookup"><span data-stu-id="8a52a-123">**Start time**</span></span>  
 <span data-ttu-id="8a52a-124">Entrez une heure de début pour les données du rapport ou spécifiez-la en cliquant sur les flèches.</span><span class="sxs-lookup"><span data-stu-id="8a52a-124">Enter a beginning time for the report data or specify one by clicking the arrows.</span></span>  
  
 <span data-ttu-id="8a52a-125">**Durée**</span><span class="sxs-lookup"><span data-stu-id="8a52a-125">**Duration**</span></span>  
 <span data-ttu-id="8a52a-126">Spécifiez la plage de temps à inclure dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="8a52a-126">Specify the time range to include in the report.</span></span> <span data-ttu-id="8a52a-127">La valeur par défaut est 240 minutes.</span><span class="sxs-lookup"><span data-stu-id="8a52a-127">The default value is 240 minutes.</span></span> <span data-ttu-id="8a52a-128">Les valeurs possibles pour la sélection sont 15 minutes, 60 minutes, 240 minutes (4 heures), 720 minutes (12 heures) et 1440 minutes (24 heures).</span><span class="sxs-lookup"><span data-stu-id="8a52a-128">The possible values to select from are 15 minutes, 60 minutes, 240 minutes (4 hours), 720 minutes (12 hours), and 1440 minutes (24 hours).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a52a-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8a52a-129">See Also</span></span>  
 <span data-ttu-id="8a52a-130">[Collecte de données](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="8a52a-130">[Data Collection](data-collection.md) </span></span>  
 <span data-ttu-id="8a52a-131">[Rapports personnalisés dans Management Studio](../../ssms/object/custom-reports-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="8a52a-131">[Custom Reports in Management Studio](../../ssms/object/custom-reports-in-management-studio.md) </span></span>  
 [<span data-ttu-id="8a52a-132">Configurer l’entrepôt de données de gestion &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="8a52a-132">Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;</span></span>](configure-the-management-data-warehouse-sql-server-management-studio.md)  
  
  
