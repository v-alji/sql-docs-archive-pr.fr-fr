---
title: Historique de la mise en miroir de bases de données | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dbmmonitor.databasemirroringhistory.f1
ms.assetid: 1d6e4b10-4a23-47d7-9918-c417992f09d3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3e32ad9bfdce15413d89fbd5ba3d79a5ef14f7a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612465"
---
# <a name="database-mirroring-history"></a><span data-ttu-id="6cc5d-102">Historique de la mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="6cc5d-102">Database Mirroring History</span></span>
  <span data-ttu-id="6cc5d-103">Utilisez cette boîte de dialogue pour afficher l'historique d'état de la mise en miroir d'une base de données sur une instance de serveur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-103">Use this dialog box to view the history of mirroring status for a mirrored database on a specified server instance.</span></span>  
  
 <span data-ttu-id="6cc5d-104">**Pour utiliser SQL Server Management Studio pour contrôler la mise en miroir de base de données**</span><span class="sxs-lookup"><span data-stu-id="6cc5d-104">**To use SQL Server Management Studio to monitor database mirroring**</span></span>  
  
-   [<span data-ttu-id="6cc5d-105">Démarrer le moniteur de mise en miroir de bases de données &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6cc5d-105">Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;</span></span>](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md)  
  
## <a name="options"></a><span data-ttu-id="6cc5d-106">Options</span><span class="sxs-lookup"><span data-stu-id="6cc5d-106">Options</span></span>  
 <span data-ttu-id="6cc5d-107">**Instance de serveur**</span><span class="sxs-lookup"><span data-stu-id="6cc5d-107">**Server instance**</span></span>  
 <span data-ttu-id="6cc5d-108">Nom de l'instance de serveur à partir de laquelle l'historique est généré.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-108">Name of the server instance from which the history is being reported.</span></span>  
  
 <span data-ttu-id="6cc5d-109">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="6cc5d-109">**Database**</span></span>  
 <span data-ttu-id="6cc5d-110">Nom de la base de données dont l'historique est généré.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-110">Name of the database whose history is being reported.</span></span>  
  
 <span data-ttu-id="6cc5d-111">**Filtrer la liste par**</span><span class="sxs-lookup"><span data-stu-id="6cc5d-111">**Filter list by**</span></span>  
 <span data-ttu-id="6cc5d-112">Répertorie les valeurs de filtre.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-112">Lists filter values.</span></span> <span data-ttu-id="6cc5d-113">La sélection d'une nouvelle valeur a pour effet d'actualiser automatiquement la grille.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-113">Choosing a new value refreshes the grid automatically.</span></span>  
  
 <span data-ttu-id="6cc5d-114">Les valeurs de filtre possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="6cc5d-114">The possible filter values are:</span></span>  
  
-   <span data-ttu-id="6cc5d-115">Deux dernières heures</span><span class="sxs-lookup"><span data-stu-id="6cc5d-115">Last two hours</span></span>  
  
-   <span data-ttu-id="6cc5d-116">Quatre dernières heures</span><span class="sxs-lookup"><span data-stu-id="6cc5d-116">Last four hours</span></span>  
  
-   <span data-ttu-id="6cc5d-117">Huit dernières heures</span><span class="sxs-lookup"><span data-stu-id="6cc5d-117">Last eight hours</span></span>  
  
-   <span data-ttu-id="6cc5d-118">Dernier jour</span><span class="sxs-lookup"><span data-stu-id="6cc5d-118">Last day</span></span>  
  
-   <span data-ttu-id="6cc5d-119">Deux derniers jours</span><span class="sxs-lookup"><span data-stu-id="6cc5d-119">Last two days</span></span>  
  
-   <span data-ttu-id="6cc5d-120">100 derniers enregistrements</span><span class="sxs-lookup"><span data-stu-id="6cc5d-120">Last 100 records</span></span>  
  
-   <span data-ttu-id="6cc5d-121">500 derniers enregistrements</span><span class="sxs-lookup"><span data-stu-id="6cc5d-121">Last 500 records</span></span>  
  
-   <span data-ttu-id="6cc5d-122">1 000 derniers enregistrements</span><span class="sxs-lookup"><span data-stu-id="6cc5d-122">Last 1000 records</span></span>  
  
-   <span data-ttu-id="6cc5d-123">Tous les enregistrements</span><span class="sxs-lookup"><span data-stu-id="6cc5d-123">All records</span></span>  
  
 <span data-ttu-id="6cc5d-124">**Actualiser**</span><span class="sxs-lookup"><span data-stu-id="6cc5d-124">**Refresh**</span></span>  
 <span data-ttu-id="6cc5d-125">Permet d'actualiser la liste historique.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-125">Click to refresh the history list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6cc5d-126">Cette boîte de dialogue n'actualise pas automatiquement la liste historique.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-126">This dialog box does not automatically refresh the history list.</span></span> <span data-ttu-id="6cc5d-127">Pour ce faire, cliquez sur **Actualiser** ou sélectionnez une autre option de filtre.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-127">To refresh the list, either click **Refresh** or choose another filter option.</span></span> <span data-ttu-id="6cc5d-128">Seuls les membres du rôle de serveur fixe **sysadmin** peuvent mettre à jour l’historique de la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-128">Only members of the **sysadmin** fixed server role can update the mirroring history.</span></span>  
  
 <span data-ttu-id="6cc5d-129">**History**</span><span class="sxs-lookup"><span data-stu-id="6cc5d-129">**History**</span></span>  
 <span data-ttu-id="6cc5d-130">Affiche la liste historique.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-130">Displays the history list.</span></span> <span data-ttu-id="6cc5d-131">Cliquez sur un en-tête de colonne pour trier la grille par rapport à cette colonne.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-131">Clicking on a column header sorts the grid by that column.</span></span> <span data-ttu-id="6cc5d-132">La liste comporte les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="6cc5d-132">The list contains the following columns:</span></span>  
  
|<span data-ttu-id="6cc5d-133">Nom de la colonne</span><span class="sxs-lookup"><span data-stu-id="6cc5d-133">Column name</span></span>|<span data-ttu-id="6cc5d-134">Description</span><span class="sxs-lookup"><span data-stu-id="6cc5d-134">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="6cc5d-135">**Durée enregistrée**</span><span class="sxs-lookup"><span data-stu-id="6cc5d-135">**Time Recorded**</span></span>|<span data-ttu-id="6cc5d-136">Horodatage de la ligne d'historique.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-136">Timestamp of the history row.</span></span>|  
|<span data-ttu-id="6cc5d-137">**Rôle**</span><span class="sxs-lookup"><span data-stu-id="6cc5d-137">**Role**</span></span>|<span data-ttu-id="6cc5d-138">Rôle actuel de la mise en miroir de l'instance de serveur pour cette base de données : Principal ou Miroir.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-138">Current mirroring role of the server instance for this database, either Principal or Mirror.</span></span>|  
|<span data-ttu-id="6cc5d-139">**État de la mise en miroir**</span><span class="sxs-lookup"><span data-stu-id="6cc5d-139">**Mirroring State**</span></span>|<span data-ttu-id="6cc5d-140">État de la base de données :</span><span class="sxs-lookup"><span data-stu-id="6cc5d-140">State of the database:</span></span><br /><br /> <span data-ttu-id="6cc5d-141">Déconnecté</span><span class="sxs-lookup"><span data-stu-id="6cc5d-141">Disconnected</span></span><br /><br /> <span data-ttu-id="6cc5d-142">Basculement en attente</span><span class="sxs-lookup"><span data-stu-id="6cc5d-142">Pending Failover</span></span><br /><br /> <span data-ttu-id="6cc5d-143">Interrompu</span><span class="sxs-lookup"><span data-stu-id="6cc5d-143">Suspended</span></span><br /><br /> <span data-ttu-id="6cc5d-144">Synchronisé</span><span class="sxs-lookup"><span data-stu-id="6cc5d-144">Synchronized</span></span><br /><br /> <span data-ttu-id="6cc5d-145">Synchronisation</span><span class="sxs-lookup"><span data-stu-id="6cc5d-145">Synchronizing</span></span><br /><br /> <span data-ttu-id="6cc5d-146">Unknown</span><span class="sxs-lookup"><span data-stu-id="6cc5d-146">Unknown</span></span>|  
|<span data-ttu-id="6cc5d-147">**Connexion témoin**</span><span class="sxs-lookup"><span data-stu-id="6cc5d-147">**Witness Connection**</span></span>|<span data-ttu-id="6cc5d-148">État de la connexion témoin dans la session de mise en miroir de la base de données : Connecté ou Déconnecté.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-148">State of the witness connection in the mirroring session of the database, either Connected or Disconnected.</span></span> <span data-ttu-id="6cc5d-149">En l'absence de témoin, la valeur est NULL.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-149">If there is no witness, the value is NULL.</span></span>|  
|<span data-ttu-id="6cc5d-150">**Journal non envoyé**</span><span class="sxs-lookup"><span data-stu-id="6cc5d-150">**Unsent Log**</span></span>|<span data-ttu-id="6cc5d-151">Taille, en kilo-octets (Ko), du journal non envoyé dans la file d'attente d'envoi sur l'instance de serveur principal.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-151">Size, in kilobytes (KB), of the unsent log in the send queue on the principal server instance.</span></span>|  
|<span data-ttu-id="6cc5d-152">**Durée à envoyer**</span><span class="sxs-lookup"><span data-stu-id="6cc5d-152">**Time to Send**</span></span>|<span data-ttu-id="6cc5d-153">Durée approximative requise par l’instance de serveur principal pour envoyer le journal qui se trouve actuellement dans la file d’attente d’envoi vers l’instance de serveur miroir ( *taux d’envoi*).</span><span class="sxs-lookup"><span data-stu-id="6cc5d-153">Approximate amount of time the principal server instance will require to send the log that is currently in the send queue to the mirror server instance (the *send rate*).</span></span> <span data-ttu-id="6cc5d-154">Étant donné que le taux de transactions entrantes peut varier sensiblement, la durée d'envoi du journal est une estimation.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-154">Because the rate of incoming transactions can vary significantly, the time to send log is an estimate.</span></span> <span data-ttu-id="6cc5d-155">Cependant, le taux d'envoi peut être utile pour obtenir une estimation approximative de la durée requise pour effectuer un basculement manuel.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-155">However, the send rate can be useful for roughly estimating the time required for a manual failover.</span></span>|  
|<span data-ttu-id="6cc5d-156">**Send Rate**</span><span class="sxs-lookup"><span data-stu-id="6cc5d-156">**Send Rate**</span></span>|<span data-ttu-id="6cc5d-157">Taux d'envoi des transactions à l'instance de serveur miroir, en Ko par seconde.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-157">Rate at which transactions are being sent to the mirror server instance, in KB per second.</span></span>|  
|<span data-ttu-id="6cc5d-158">**Taux de nouvelles transactions**</span><span class="sxs-lookup"><span data-stu-id="6cc5d-158">**New Transaction Rate**</span></span>|<span data-ttu-id="6cc5d-159">Taux auquel des transactions entrantes sont ajoutées au journal du principal, en Ko par seconde.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-159">Rate at which incoming transactions are being entered into the principal's log, in KB per second.</span></span> <span data-ttu-id="6cc5d-160">Pour déterminer si la mise en miroir est en retard, à jour ou en cours de mise à niveau, comparez cette valeur à la valeur du champ **Durée à envoyer** .</span><span class="sxs-lookup"><span data-stu-id="6cc5d-160">To determine whether mirroring is falling behind, staying up, or catching up, compare this value to the **Time to Send** value.</span></span>|  
|<span data-ttu-id="6cc5d-161">**Transaction non envoyée la plus ancienne**</span><span class="sxs-lookup"><span data-stu-id="6cc5d-161">**Oldest Unsent Transaction**</span></span>|<span data-ttu-id="6cc5d-162">Âge de la transaction non envoyée la plus ancienne dans la file d'attente d'envoi.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-162">Age of the oldest unsent transaction in the send queue.</span></span> <span data-ttu-id="6cc5d-163">La durée de vie de cette transaction indique la quantité de transactions en minutes qui n'ont pas encore été envoyées à l'instance de serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-163">The age of this transaction indicates how many minutes of transactions have not yet been sent to the mirror server instance.</span></span> <span data-ttu-id="6cc5d-164">Cette valeur permet de mesurer la perte de données potentielle en termes de temps.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-164">This value helps measure the potential for data loss in terms of time.</span></span>|  
|<span data-ttu-id="6cc5d-165">**Journal non restauré**</span><span class="sxs-lookup"><span data-stu-id="6cc5d-165">**Unrestored Log**</span></span>|<span data-ttu-id="6cc5d-166">Quantité de journal en attente dans la file d'attente de restauration par progression, en Ko.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-166">The amount of log waiting in the redo queue, in KB.</span></span>|  
|<span data-ttu-id="6cc5d-167">**Durée à restaurer**</span><span class="sxs-lookup"><span data-stu-id="6cc5d-167">**Time to Restore**</span></span>|<span data-ttu-id="6cc5d-168">Nombre approximatif de minutes requises pour que le journal actuellement dans la file d'attente de restauration par progression soit appliqué à la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-168">Approximate number of minutes required for the log currently in the redo queue to be applied to the mirror database.</span></span>|  
|<span data-ttu-id="6cc5d-169">**Taux de restauration**</span><span class="sxs-lookup"><span data-stu-id="6cc5d-169">**Restore Rate**</span></span>|<span data-ttu-id="6cc5d-170">Taux de restauration des transactions dans la base de données en miroir, en Ko par seconde.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-170">Rate at which transactions are being restored into the mirror database, in KB per second.</span></span>|  
|<span data-ttu-id="6cc5d-171">**Temps de traitement de validation de miroir**</span><span class="sxs-lookup"><span data-stu-id="6cc5d-171">**Mirror Commit Overhead**</span></span>|<span data-ttu-id="6cc5d-172">Délai moyen par transaction en millisecondes (uniquement en modes synchrones).</span><span class="sxs-lookup"><span data-stu-id="6cc5d-172">Average delay per transaction in milliseconds (only in synchronous modes).</span></span> <span data-ttu-id="6cc5d-173">Ce délai correspond au temps de traitement pendant lequel l'instance de serveur principal attend que l'instance de serveur miroir écrive l'enregistrement du journal de transaction dans la file d'attente de restauration par progression.</span><span class="sxs-lookup"><span data-stu-id="6cc5d-173">This delay is the amount of overhead incurred while the principal server instance waits for the mirror server instance to write the transaction's log record into the redo queue.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6cc5d-174">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6cc5d-174">See Also</span></span>  
 <span data-ttu-id="6cc5d-175">[Démarrer le moniteur de mise en miroir de bases de données &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="6cc5d-175">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="6cc5d-176">[Surveillance de la mise en miroir de bases de données &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6cc5d-176">[Monitoring Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="6cc5d-177">Démarrer l’Assistant Configuration de la sécurité de mise en miroir de bases de données &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6cc5d-177">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
  
