---
title: Afficher l’état d’une base de données mise en miroir (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- states [SQL Server], database mirroring
- database mirroring [SQL Server], states
ms.assetid: 544f4194-253e-4c57-96ca-31c16301434f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fc691e8b746a816ab88448e3399aebad6d8844e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604124"
---
# <a name="view-the-state-of-a-mirrored-database-sql-server-management-studio"></a><span data-ttu-id="3ab64-102">Afficher l'état d'une base de données mise en miroir (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="3ab64-102">View the State of a Mirrored Database (SQL Server Management Studio)</span></span>
  <span data-ttu-id="3ab64-103">Pendant une session de mise en miroir de bases de données, vous pouvez afficher l’état dans la page **Mise en miroir** de la boîte de dialogue **Propriétés de la base de données** .</span><span class="sxs-lookup"><span data-stu-id="3ab64-103">During a database mirroring session, you can view the status on the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
### <a name="to-view-the-status-of-a-database-mirroring-session"></a><span data-ttu-id="3ab64-104">Pour afficher l'état d'une session de mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="3ab64-104">To view the status of a database mirroring session</span></span>  
  
1.  <span data-ttu-id="3ab64-105">Après vous être connecté à l'instance du serveur principal, dans l'Explorateur d'objets, cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="3ab64-105">After connecting to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="3ab64-106">Développez **Bases de données**et sélectionnez la base de données à mettre en miroir.</span><span class="sxs-lookup"><span data-stu-id="3ab64-106">Expand **Databases**, and select the database to be mirrored.</span></span>  
  
3.  <span data-ttu-id="3ab64-107">Cliquez avec le bouton droit sur la base de données, sélectionnez **Tâches**, puis cliquez sur **Miroir**.</span><span class="sxs-lookup"><span data-stu-id="3ab64-107">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="3ab64-108">La page **Mise en miroir** de la boîte de dialogue **Propriétés de la base de données** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="3ab64-108">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="3ab64-109">Quand la mise en miroir a commencé, le volet **État** affiche l’état de la session de mise en miroir de bases de données comme si vous aviez sélectionné la page **Mise en miroir** ou cliqué sur le bouton **Actualiser** .</span><span class="sxs-lookup"><span data-stu-id="3ab64-109">After mirroring begins, the **Status** panel displays the status of the database mirroring session as of when you selected the **Mirroring** page or clicked the **Refresh** button.</span></span> <span data-ttu-id="3ab64-110">Les états possibles sont :</span><span class="sxs-lookup"><span data-stu-id="3ab64-110">The possible states are as follows:</span></span>  
  
    |<span data-ttu-id="3ab64-111">États</span><span class="sxs-lookup"><span data-stu-id="3ab64-111">States</span></span>|<span data-ttu-id="3ab64-112">Explication</span><span class="sxs-lookup"><span data-stu-id="3ab64-112">Explanation</span></span>|  
    |------------|-----------------|  
    |\<blank>|<span data-ttu-id="3ab64-113">Aucune session de mise en miroir de base de données n’existe et aucune activité n’est à signaler dans la page **Mise en miroir** .</span><span class="sxs-lookup"><span data-stu-id="3ab64-113">No database mirroring session exists and there is no activity to report on the **Mirroring** page.</span></span>|  
    |<span data-ttu-id="3ab64-114">Suspendu</span><span class="sxs-lookup"><span data-stu-id="3ab64-114">Paused</span></span>|<span data-ttu-id="3ab64-115">La base de données principale est en cours d'exécution, mais n'envoie aucun journal au serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="3ab64-115">The principal database is running but is not sending any logs to the mirror server.</span></span> <span data-ttu-id="3ab64-116">La copie miroir de la base de données n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="3ab64-116">The mirror copy of the database is not available.</span></span>|  
    |<span data-ttu-id="3ab64-117">Aucune connexion</span><span class="sxs-lookup"><span data-stu-id="3ab64-117">No connection</span></span>|<span data-ttu-id="3ab64-118">L'instance du serveur principal ne peut pas se connecter à son partenaire ou à l'instance du serveur témoin (le cas échéant)</span><span class="sxs-lookup"><span data-stu-id="3ab64-118">The principal server instance cannot connect to its partner or to the witness server instance (if any)</span></span>|  
    |<span data-ttu-id="3ab64-119">Synchronisation</span><span class="sxs-lookup"><span data-stu-id="3ab64-119">Synchronizing</span></span>|<span data-ttu-id="3ab64-120">Le contenu de la base de données en miroir est décalé par rapport à celui de la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="3ab64-120">The contents of the mirror database are lagging behind the contents of the principal database.</span></span> <span data-ttu-id="3ab64-121">L'instance de serveur principal envoie des enregistrements de journal à l'instance de serveur miroir, laquelle applique les modifications à la base de données miroir pour la restaurer par progression.</span><span class="sxs-lookup"><span data-stu-id="3ab64-121">The principal server instance is sending log records to the mirror server instance, which is applying the changes to the mirror database to roll it forward.</span></span><br /><br /> <span data-ttu-id="3ab64-122">Au début d'une session de mise en miroir de bases de données, les bases de données miroir et serveur sont en état de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="3ab64-122">At the start of a database mirroring session, the mirror and principal databases are in the synchronizing state.</span></span>|  
    |<span data-ttu-id="3ab64-123">Basculement</span><span class="sxs-lookup"><span data-stu-id="3ab64-123">Failover</span></span>|<span data-ttu-id="3ab64-124">Sur l'instance du serveur principal, un basculement manuel (échange de rôles) a commencé, mais n'a pas encore été accepté par le miroir.</span><span class="sxs-lookup"><span data-stu-id="3ab64-124">On the principal server instance, a manual failover (role swap) has begun but has not yet accepted by the mirror.</span></span>|  
    |<span data-ttu-id="3ab64-125">Synchronisé</span><span class="sxs-lookup"><span data-stu-id="3ab64-125">Synchronized</span></span>|<span data-ttu-id="3ab64-126">La base de données miroir contient les mêmes données que la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="3ab64-126">The mirror database contains the same data as the principal database.</span></span> <span data-ttu-id="3ab64-127">Les basculements manuel et automatique sont possibles *uniquement* à l’état synchronisé.</span><span class="sxs-lookup"><span data-stu-id="3ab64-127">Manual and automatic failover are possible *only* in the synchronized state.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3ab64-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3ab64-128">See Also</span></span>  
 [<span data-ttu-id="3ab64-129">États de la mise en miroir &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3ab64-129">Mirroring States &#40;SQL Server&#41;</span></span>](mirroring-states-sql-server.md)  
  
  
