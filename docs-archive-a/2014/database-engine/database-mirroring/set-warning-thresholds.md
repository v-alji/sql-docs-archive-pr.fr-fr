---
title: Définir des seuils d’avertissement | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dbmmonitor.setwarningthreshold.f1
ms.assetid: 17f93147-e7d9-4092-b4c2-c11b38051171
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2d5fd9c0213d74f3a6b5d0d4cb2f11d3531d336d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701742"
---
# <a name="set-warning-thresholds"></a><span data-ttu-id="ed8d8-102">Définir les seuils d'avertissement</span><span class="sxs-lookup"><span data-stu-id="ed8d8-102">Set Warning Thresholds</span></span>
  <span data-ttu-id="ed8d8-103">Utilisez cette boîte de dialogue pour activer et configurer un ou plusieurs seuils d'avertissement pour la base de données sélectionnée dans l'arborescence de navigation de la boîte de dialogue **Moniteur de mise en miroir de bases de données** .</span><span class="sxs-lookup"><span data-stu-id="ed8d8-103">Use this dialog box to enable and configure one or more warning thresholds for the database selected in the navigation tree of the **Database Mirroring Monitor** dialog box.</span></span>  
  
 <span data-ttu-id="ed8d8-104">La boîte de dialogue tente d'établir une connexion avec les deux instances de serveurs.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-104">The dialog box tries to connect to both server instances.</span></span> <span data-ttu-id="ed8d8-105">Ces connexions sont établies de façon asynchrone.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-105">These connections are established asynchronously.</span></span> <span data-ttu-id="ed8d8-106">La boîte de dialogue affiche l'état de la connexion de chaque partenaire.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-106">The dialog shows the connection status of each partner.</span></span> <span data-ttu-id="ed8d8-107">Si le partenaire n'est pas connecté, vous pouvez cliquer sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-107">If the partner is not connected, you can click **Connect**.</span></span>  
  
 <span data-ttu-id="ed8d8-108">**Pour utiliser SQL Server Management Studio pour contrôler la mise en miroir de base de données**</span><span class="sxs-lookup"><span data-stu-id="ed8d8-108">**To use SQL Server Management Studio to monitor database mirroring**</span></span>  
  
-   [<span data-ttu-id="ed8d8-109">Démarrer le moniteur de mise en miroir de bases de données &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ed8d8-109">Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;</span></span>](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md)  
  
## <a name="options"></a><span data-ttu-id="ed8d8-110">Options</span><span class="sxs-lookup"><span data-stu-id="ed8d8-110">Options</span></span>  
 <span data-ttu-id="ed8d8-111">*Instance de serveur et état de la connexion*</span><span class="sxs-lookup"><span data-stu-id="ed8d8-111">*Server instance and its connection status*</span></span>  
 <span data-ttu-id="ed8d8-112">Nom d’une instance de serveur partenaire au format _système_ **\\** _instance_name_.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-112">Name of a partner server instance in the form _SYSTEM_**\\**_INSTANCE_NAME_.</span></span> <span data-ttu-id="ed8d8-113">Pour une instance de serveur par défaut, seul le nom du système s'affiche.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-113">For a default server instance, only the system name is displayed.</span></span>  
  
 <span data-ttu-id="ed8d8-114">Ce champ indique également si le moniteur est actuellement connecté à cette instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-114">This field also indicates whether the monitor is currently connected to this server instance.</span></span> <span data-ttu-id="ed8d8-115">Les états de connexion possibles sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="ed8d8-115">The possible connection statuses are:</span></span>  
  
-   <span data-ttu-id="ed8d8-116">**Non connecté à**  *nom_instance_serveur*</span><span class="sxs-lookup"><span data-stu-id="ed8d8-116">**Not connected to**  *server_instance_name*</span></span>  
  
-   <span data-ttu-id="ed8d8-117">**Tentative de connexion à**  *nom_instance_serveur*</span><span class="sxs-lookup"><span data-stu-id="ed8d8-117">**Trying to connect to**  *server_instance_name*</span></span>  
  
-   <span data-ttu-id="ed8d8-118">**Connecté à**   *nom_instance_serveur*</span><span class="sxs-lookup"><span data-stu-id="ed8d8-118">**Connected to**  *server_instance_name*</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ed8d8-119">Si vous n’êtes pas membre du rôle de serveur fixe **sysadmin**, l’état est **Connecté à** *nom_instance_serveur* **(Autorisations limitées)** .</span><span class="sxs-lookup"><span data-stu-id="ed8d8-119">If you do are not a member of the **sysadmin** fixed server role, this status is **Connected to** *server_instance_name* **(Limited permissions)**.</span></span>  
  
 <span data-ttu-id="ed8d8-120">Le nom de chaque instance de serveur partenaire est affiché dans un champ d' *instance de serveur et d'état de la connexion* distinct.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-120">The name of each of the partner server instances is displayed in a separate *Server instance and its connection status* field.</span></span> <span data-ttu-id="ed8d8-121">Le premier champ affiche le serveur principal au démarrage du moniteur.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-121">The top field lists the principal server when the monitor started running.</span></span>  
  
 <span data-ttu-id="ed8d8-122">**Se connecter**/**Annuler**</span><span class="sxs-lookup"><span data-stu-id="ed8d8-122">**Connect**/**Cancel**</span></span>  
 <span data-ttu-id="ed8d8-123">Un bouton **Se connecter**/**Annuler** est associé à chaque champ d’ *instance de serveur et état de la connexion* .</span><span class="sxs-lookup"><span data-stu-id="ed8d8-123">A **Connect**/**Cancel** button is associated with each *Server instance and its connection status* fields.</span></span> <span data-ttu-id="ed8d8-124">L'état de ce bouton dépend de l'état de la connexion :</span><span class="sxs-lookup"><span data-stu-id="ed8d8-124">The state of the button depends on the connection status:</span></span>  
  
-   <span data-ttu-id="ed8d8-125">Si aucune connexion à l'instance de serveur n'est établie, l'intitulé du bouton est **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-125">If there is no connection to the server instance, the button text is **Connect**.</span></span> <span data-ttu-id="ed8d8-126">Cliquez sur le bouton pour vous connecter à l'instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-126">Click to connect to the server instance.</span></span>  
  
-   <span data-ttu-id="ed8d8-127">Lorsqu'une tentative de connexion est en cours, l'intitulé du bouton est **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-127">When a connection attempt is in progress, the button text is **Cancel**.</span></span> <span data-ttu-id="ed8d8-128">Cliquez sur le bouton pour annuler la tentative de connexion.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-128">Click to cancel the connection attempt.</span></span>  
  
-   <span data-ttu-id="ed8d8-129">Si le serveur est connecté, le bouton est grisé et son intitulé est **Connecté**.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-129">If the server is connected, the button text is **Connected**, and the button is dimmed.</span></span>  
  
 <span data-ttu-id="ed8d8-130">**Seuils**</span><span class="sxs-lookup"><span data-stu-id="ed8d8-130">**Thresholds**</span></span>  
 <span data-ttu-id="ed8d8-131">La grille **Seuils** affiche les paramètres d’avertissement pour les deux instances de serveurs.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-131">The **Thresholds** grid displays the warnings settings for the two server instances.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed8d8-132">Si une instance de serveur n'est pas connectée, ses colonnes affichent des cellules vides sur un fond gris.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-132">If a server instance is not connected, its columns are displayed with empty cells and a gray background.</span></span> <span data-ttu-id="ed8d8-133">Lorsque la connexion s'ouvre, la grille affiche automatiquement le contenu à partir de l'instance.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-133">When the connection opens, the grid automatically displays the content from the instance.</span></span>  
  
 <span data-ttu-id="ed8d8-134">Cette grille comporte les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="ed8d8-134">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="ed8d8-135">**Avertissements**</span><span class="sxs-lookup"><span data-stu-id="ed8d8-135">**Warnings**</span></span>  
 <span data-ttu-id="ed8d8-136">Répertorie les avertissements pris en charge :</span><span class="sxs-lookup"><span data-stu-id="ed8d8-136">Lists the supported warnings:</span></span>  
  
|<span data-ttu-id="ed8d8-137">Avertissement</span><span class="sxs-lookup"><span data-stu-id="ed8d8-137">Warning</span></span>|<span data-ttu-id="ed8d8-138">Description</span><span class="sxs-lookup"><span data-stu-id="ed8d8-138">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ed8d8-139">**Avertir si le journal non envoyé dépasse le seuil**</span><span class="sxs-lookup"><span data-stu-id="ed8d8-139">**Warn if the unsent log exceeds the threshold**</span></span>|<span data-ttu-id="ed8d8-140">Ce seuil indique la taille en kilo-octets (Ko) du journal non envoyé dans la file d'attente d'envoi sur le principal.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-140">The threshold indicates the number of kilobytes (KB) of the unsent log in the send queue on the principal.</span></span>|  
|<span data-ttu-id="ed8d8-141">**Avertir si le journal non restauré dépasse le seuil**</span><span class="sxs-lookup"><span data-stu-id="ed8d8-141">**Warn if the unrestored log exceeds the threshold**</span></span>|<span data-ttu-id="ed8d8-142">Ce seuil indique la taille (en Ko) de la file d'attente de restauration sur l'instance du serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-142">The threshold indicates the number of KB of the redo queue on the mirror server instance.</span></span>|  
|<span data-ttu-id="ed8d8-143">**Avertir si la durée de vie de la plus ancienne transaction non envoyée dépasse le seuil**</span><span class="sxs-lookup"><span data-stu-id="ed8d8-143">**Warn if the age of the oldest unsent transaction exceeds the threshold**</span></span>|<span data-ttu-id="ed8d8-144">Ce seuil indique la durée exprimée en minutes des transactions qui n'ont pas encore été envoyées depuis la file d'attente d'envoi vers l'instance de serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-144">The threshold indicates the number of minutes of transactions that have not yet been sent from the send queue to the mirror server instance.</span></span> <span data-ttu-id="ed8d8-145">Cette valeur permet de mesurer la perte de données potentielle en termes de temps.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-145">This value helps measure the potential for data loss in terms of time.</span></span>|  
|<span data-ttu-id="ed8d8-146">**Avertir si le temps de traitement de validation de miroir dépasse le seuil**</span><span class="sxs-lookup"><span data-stu-id="ed8d8-146">**Warn if the mirror commit overhead exceeds the threshold**</span></span>|<span data-ttu-id="ed8d8-147">Ce seuil indique le délai en millisecondes par transaction (utile uniquement en mode haute sécurité).</span><span class="sxs-lookup"><span data-stu-id="ed8d8-147">The threshold indicates the number of milliseconds of delay per transaction (relevant only in high-safety mode).</span></span> <span data-ttu-id="ed8d8-148">Ce délai correspond au temps de traitement pendant lequel l'instance de serveur principal attend que l'instance de serveur miroir écrive l'enregistrement du journal de transaction dans la file d'attente de restauration par progression.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-148">This delay is the amount of overhead incurred while the principal server instance waits for the mirror server instance to write the transaction's log record into the redo queue.</span></span>|  
  
 <span data-ttu-id="ed8d8-149">**Activé à «**   *\<server instance>*   **»**</span><span class="sxs-lookup"><span data-stu-id="ed8d8-149">**Enabled at '** *\<server instance>* **'**</span></span>  
 <span data-ttu-id="ed8d8-150">Une case à cocher vide indique que l'avertissement est actuellement désactivé sur l'instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-150">A blank check box indicates that the warning is currently disabled on the server instance.</span></span> <span data-ttu-id="ed8d8-151">Pour activer l'avertissement, activez la case à cocher.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-151">To enable a warning, click its check box.</span></span>  
  
 <span data-ttu-id="ed8d8-152">**Seuil à «**   *\<server instance>*   **»**</span><span class="sxs-lookup"><span data-stu-id="ed8d8-152">**Threshold at '** *\<server instance>* **'**</span></span>  
 <span data-ttu-id="ed8d8-153">Lorsqu'un avertissement est activé, définissez le seuil dans la partie gauche de cette colonne.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-153">When a warning is enabled, set the threshold on the left side of this column.</span></span> <span data-ttu-id="ed8d8-154">Un événement se produit si le seuil spécifié est atteint lors de la mise à jour de la table d'état.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-154">An event occurs if the specified threshold has been reached when the status table is updated.</span></span> <span data-ttu-id="ed8d8-155">Si vous désactivez un seuil après avoir configuré une valeur, cette valeur reste dans le champ et sera utilisée lorsque vous activerez de nouveau l'avertissement.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-155">If you disable a threshold after configuring a value, your value remains in this field and will be used if you re-enable the warning.</span></span>  
  
 <span data-ttu-id="ed8d8-156">Lorsqu'un avertissement n'est pas activé, ce champ est inactif.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-156">When a warning is not enabled, this field is inactive.</span></span>  
  
 <span data-ttu-id="ed8d8-157">**OK**</span><span class="sxs-lookup"><span data-stu-id="ed8d8-157">**OK**</span></span>  
 <span data-ttu-id="ed8d8-158">Quand vous cliquez sur **OK** , cette boîte de dialogue se ferme et les valeurs actuellement spécifiées pour les seuils d’avertissement s’affichent dans la grille **Seuils** de la page à onglets **Avertissements**.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-158">Clicking **OK** closes this dialog box and displays the currently specified values of warning thresholds in the **Thresholds** grid on the **Warnings**tabbed page.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed8d8-159">Notes</span><span class="sxs-lookup"><span data-stu-id="ed8d8-159">Remarks</span></span>  
 <span data-ttu-id="ed8d8-160">Un seuil est applicable à un seul partenaire à la fois, mais nous vous recommandons de définir un seuil pour un événement donné sur les deux partenaires, afin de vous assurer que l'avertissement persiste lors du basculement de la base de données.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-160">A threshold is only applicable at one partner at a time, but we recommend that you set a threshold for a given event on both partners to ensure that the warning persists if the database fails over.</span></span> <span data-ttu-id="ed8d8-161">Le seuil approprié pour chaque partenaire dépend des capacités de performance du système du partenaire.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-161">The appropriate threshold for each partner depends on the performance capabilities of that partner's system.</span></span>  
  
 <span data-ttu-id="ed8d8-162">Un événement est écrit dans le journal des événements pour une performance uniquement si sa valeur est identique ou supérieure au seuil au moment de la mise à jour de la table d'état.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-162">An event is written to the event log for a performance only if its value is at or above its threshold when the status table is being updated.</span></span> <span data-ttu-id="ed8d8-163">Si une valeur maximale atteint momentanément le seuil entre des mises à jour d'état, cette valeur est ignorée.</span><span class="sxs-lookup"><span data-stu-id="ed8d8-163">If a peak value reaches the threshold momentarily between status updates that peak is missed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed8d8-164">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ed8d8-164">See Also</span></span>  
 <span data-ttu-id="ed8d8-165">[Démarrer le moniteur de mise en miroir de bases de données &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="ed8d8-165">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="ed8d8-166">[Surveillance de la mise en miroir de bases de données &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ed8d8-166">[Monitoring Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="ed8d8-167">Démarrer l’Assistant Configuration de la sécurité de mise en miroir de bases de données &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ed8d8-167">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
  
