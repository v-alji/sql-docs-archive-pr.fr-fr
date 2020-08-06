---
title: Réparer une installation SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 90c11b28-892b-44d6-978e-0eee48c75b7d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f3e382137a971b3f8b23cf1d814bff9908f04150
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701543"
---
# <a name="drop-a-sql-server-2014-installation"></a><span data-ttu-id="cade4-102">Ignorer une installation de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="cade4-102">Drop a SQL Server 2014 Installation</span></span>
  <span data-ttu-id="cade4-103">L'opération de réparation peut être utilisée dans les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="cade4-103">Repair operation can be used in the following scenarios:</span></span>  
  
-   <span data-ttu-id="cade4-104">Réparer une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui est endommagée après une installation réussie.</span><span class="sxs-lookup"><span data-stu-id="cade4-104">Repair an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is corrupted after it was successfully installed.</span></span>  
  
-   <span data-ttu-id="cade4-105">Réparer une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si l'opération de mise à niveau est annulée ou échoue une fois que le nom de l'instance est mappé à l'instance nouvellement mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="cade4-105">Repair an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if the upgrade operation is cancelled or fails after the instance name is mapped to the newly-upgraded instance.</span></span>  
  
    -   <span data-ttu-id="cade4-106">Si le message suivant s'affiche dans le journal résumé, vous pouvez réparer l'instance de mise à niveau qui a échoué :</span><span class="sxs-lookup"><span data-stu-id="cade4-106">If you see the following message in the summary log, you can repair the failed upgrade instance:</span></span>  
  
         <span data-ttu-id="cade4-107">La mise à niveau de[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a échoué.</span><span class="sxs-lookup"><span data-stu-id="cade4-107">"[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] upgrade failed.</span></span> <span data-ttu-id="cade4-108">Pour continuer, déterminez la cause de l'échec, résolvez le problème, puis réparez votre installation. »</span><span class="sxs-lookup"><span data-stu-id="cade4-108">To continue, investigate the reason for the failure, correct the problem, and then repair your installation."</span></span>  
  
    -   <span data-ttu-id="cade4-109">Si le message suivant s'affiche dans le journal résumé, vous devez désinstaller, puis réinstaller [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cade4-109">If you see the following message in the summary log, you need to uninstall and reinstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cade4-110">Vous ne pouvez pas réparer l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cade4-110">You cannot repair the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
         <span data-ttu-id="cade4-111">La mise à niveau de[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a échoué.</span><span class="sxs-lookup"><span data-stu-id="cade4-111">"[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] upgrade failed.</span></span> <span data-ttu-id="cade4-112">Pour continuer, déterminez la cause de l'échec, résolvez le problème. »</span><span class="sxs-lookup"><span data-stu-id="cade4-112">To continue, investigate the reason for the failure, correct the problem."</span></span>  
  
 <span data-ttu-id="cade4-113">Lorsque vous réparez une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="cade4-113">When you repair an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="cade4-114">tous les fichiers manquants ou endommagés sont remplacés ;</span><span class="sxs-lookup"><span data-stu-id="cade4-114">All missing or corrupt files are replaced.</span></span>  
  
-   <span data-ttu-id="cade4-115">toutes les clés de Registre manquantes ou endommagées sont remplacées ;</span><span class="sxs-lookup"><span data-stu-id="cade4-115">All missing or corrupt registry keys are replaced.</span></span>  
  
-   <span data-ttu-id="cade4-116">les valeurs par défaut sont définies pour toutes les valeurs de configuration manquantes ou non valides.</span><span class="sxs-lookup"><span data-stu-id="cade4-116">All missing or invalid configuration values are set to default values.</span></span>  
  
 <span data-ttu-id="cade4-117">Avant de continuer, pour les clusters de basculement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , passez en revue les informations importantes suivantes :</span><span class="sxs-lookup"><span data-stu-id="cade4-117">Before you continue, for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover clusters, review the following important information:</span></span>  
  
-   <span data-ttu-id="cade4-118">La réparation doit être effectuée sur des nœuds de cluster individuels.</span><span class="sxs-lookup"><span data-stu-id="cade4-118">Repair must be run on individual cluster nodes.</span></span>  
  
-   <span data-ttu-id="cade4-119">Pour réparer un nœud de cluster de basculement après une préparation ayant échoué, utilisez **Supprimer un nœud** et effectuez à nouveau la préparation.</span><span class="sxs-lookup"><span data-stu-id="cade4-119">To repair a failover cluster node after a failed Prepare operation, use **Remove node** and then perform the Prepare step again.</span></span> <span data-ttu-id="cade4-120">Pour plus d’informations, consultez [Ajouter ou supprimer des nœuds dans un cluster de basculement SQL Server &#40;programme d’installation&#41;](../../sql-server/failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span><span class="sxs-lookup"><span data-stu-id="cade4-120">For more information, see [Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;](../../sql-server/failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span></span>  
  
### <a name="to-repair-a-failed-installation-of-ssnoversion-from-the-installation-center"></a><span data-ttu-id="cade4-121">Pour réparer une installation défectueuse de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à partir du centre d'installation</span><span class="sxs-lookup"><span data-stu-id="cade4-121">To repair a failed installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the Installation Center</span></span>  
  
1.  <span data-ttu-id="cade4-122">Lancez le programme d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (setup.exe) à partir du support d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cade4-122">Launch the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup program (setup.exe) from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation media.</span></span>  
  
2.  <span data-ttu-id="cade4-123">Après avoir vérifié les composants requis et le système, le programme d'installation affiche la page Centre d'installation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cade4-123">After prerequisites and system verification, the Setup program will display the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Center page.</span></span>  
  
3.  <span data-ttu-id="cade4-124">Cliquez sur **Maintenance** dans la zone de navigation gauche, puis sur **Réparer** pour démarrer la réparation.</span><span class="sxs-lookup"><span data-stu-id="cade4-124">Click **Maintenance** in the left-hand navigation area, and then click **Repair** to start the repair operation.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="cade4-125">Si le Centre d'Installation a été lancé à l'aide du menu Démarrer, vous devez fournir l'emplacement actuel du support d'installation.</span><span class="sxs-lookup"><span data-stu-id="cade4-125">If the Installation Center was launched using the start menu, you will need to provide the location of the installation media at this time.</span></span>  
  
4.  <span data-ttu-id="cade4-126">La règle de support d'installation et les routines de fichiers sont exécutées pour garantir que les composants requis sont installés sur votre système et que les règles de validation du programme d'installation ont été correctement exécutées sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="cade4-126">Setup support rule and file routines will run to ensure that your system has prerequisites installed and that the computer passes Setup validation rules.</span></span> <span data-ttu-id="cade4-127">Cliquez sur **OK** ou sur **Installer** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="cade4-127">Click **OK** or **Install** to continue.</span></span>  
  
5.  <span data-ttu-id="cade4-128">Dans la page Sélectionner une instance, sélectionnez l’instance à réparer, puis cliquez sur **Suivant** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="cade4-128">On the Select Instance page, select the instance to repair, and then click **Next** to continue.</span></span>  
  
6.  <span data-ttu-id="cade4-129">Les règles de réparation sont exécutées pour valider l'opération.</span><span class="sxs-lookup"><span data-stu-id="cade4-129">The repair rules will run to validate the operation.</span></span> <span data-ttu-id="cade4-130">Pour continuer, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cade4-130">To continue, click **Next**.</span></span>  
  
7.  <span data-ttu-id="cade4-131">La page Prêt à réparer indique que l'opération peut se poursuivre.</span><span class="sxs-lookup"><span data-stu-id="cade4-131">The Ready to Repair page indicates that the operation is ready to proceed.</span></span> <span data-ttu-id="cade4-132">Pour continuer, cliquez sur **Réparer**.</span><span class="sxs-lookup"><span data-stu-id="cade4-132">To continue, click **Repair**.</span></span>  
  
8.  <span data-ttu-id="cade4-133">La page Progression de la réparation indique l'état de l'opération de réparation.</span><span class="sxs-lookup"><span data-stu-id="cade4-133">The Repair Progress page shows the status of the repair operation.</span></span> <span data-ttu-id="cade4-134">La page Terminé indique que l'opération est terminée.</span><span class="sxs-lookup"><span data-stu-id="cade4-134">The Complete page indicates that the operation is finished.</span></span>  
  
### <a name="to-repair-a-failed-installation-of-ssnoversion-using-command-prompt"></a><span data-ttu-id="cade4-135">Pour réparer une installation défectueuse de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide de l'invite de commandes</span><span class="sxs-lookup"><span data-stu-id="cade4-135">To repair a failed installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Command Prompt</span></span>  
  
1.  <span data-ttu-id="cade4-136">À une invite de commandes, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="cade4-136">Run the following command at a command prompt:</span></span>  
  
    ```  
    Setup.exe /q /ACTION=Repair /INSTANCENAME=instancename  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cade4-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cade4-137">See Also</span></span>  
 <span data-ttu-id="cade4-138">[Afficher et lire les fichiers journaux d’installation de SQL Server](view-and-read-sql-server-setup-log-files.md) </span><span class="sxs-lookup"><span data-stu-id="cade4-138">[View and Read SQL Server Setup Log Files](view-and-read-sql-server-setup-log-files.md) </span></span>  
 [<span data-ttu-id="cade4-139">Rubriques de procédures relatives à l'installation</span><span class="sxs-lookup"><span data-stu-id="cade4-139">Installation How-to Topics</span></span>](../../sql-server/install/installation-how-to-topics.md)  
  
  
