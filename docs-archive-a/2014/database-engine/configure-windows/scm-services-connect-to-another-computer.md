---
title: Se connecter à un autre ordinateur (Gestionnaire de configuration SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server], other computers
ms.assetid: c4c1e94f-4f5f-431e-8b5b-d5ff97baf723
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f3d478cebc1ca36ccb8f87b0355b7c8fe0a928cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614842"
---
# <a name="connect-to-another-computer-sql-server-configuration-manager"></a><span data-ttu-id="94bea-102">Se connecter à un autre ordinateur (Gestionnaire de configuration SQL Server)</span><span class="sxs-lookup"><span data-stu-id="94bea-102">Connect to Another Computer (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="94bea-103">Cette rubrique explique comment se connecter à un autre ordinateur dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94bea-103">This topic describes how to connect to another computer in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="94bea-104">Suivez la première procédure pour ouvrir la Console de gestion [!INCLUDE[msCoName](../../includes/msconame-md.md)] (mmc) de Gestion de l'ordinateur Windows, connectez-vous à l'ordinateur et développez l'arborescence Services et Applications.</span><span class="sxs-lookup"><span data-stu-id="94bea-104">Follow the first procedure to open the Windows Computer Management [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console (mmc), connect to the computer, and expand the Services and Applications tree.</span></span> <span data-ttu-id="94bea-105">Suivez la deuxième procédure pour créer un fichier avec un lien vers le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur un ordinateur distant.</span><span class="sxs-lookup"><span data-stu-id="94bea-105">Follow the second procedure to create a file with a link to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager on a remote computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="94bea-106">Certaines actions ne peuvent pas être effectuées par le Gestionnaire de configuration lors de la connexion à distance.</span><span class="sxs-lookup"><span data-stu-id="94bea-106">Some actions cannot be performed by Configuration Manager when connecting remotely.</span></span>  
  
 <span data-ttu-id="94bea-107">Pour démarrer, arrêter, interrompre ou reprendre les services sur un autre ordinateur, vous pouvez également vous connecter au serveur à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], cliquer avec le bouton droit sur le serveur ou l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , puis cliquer sur l'action souhaitée.</span><span class="sxs-lookup"><span data-stu-id="94bea-107">To start, stop, pause, or resume services on another computer, you can also connect to the server with [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click the server or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent and then click the desired action.</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-connect-to-another-computer-with-windows-computer-management"></a><span data-ttu-id="94bea-108">Pour se connecter à un autre ordinateur avec la Gestion de l'ordinateur Windows</span><span class="sxs-lookup"><span data-stu-id="94bea-108">To connect to another computer with Windows Computer Management</span></span>  
  
1.  <span data-ttu-id="94bea-109">Dans le menu **Démarrer** , cliquez avec le bouton droit sur **Poste de travail**, puis cliquez sur **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="94bea-109">On the **Start** menu, right-click **My Computer**, and then click **Manage.**</span></span>  
  
2.  <span data-ttu-id="94bea-110">Dans **Gestion de l’ordinateur**, cliquez avec le bouton droit sur **Gestion de l’ordinateur (local)**, puis cliquez sur **Se connecter à un autre ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="94bea-110">In **Computer Management**, right-click **Computer Management (Local)**, and then click **Connect to another computer**.</span></span>  
  
3.  <span data-ttu-id="94bea-111">Dans la boîte de dialogue **Sélectionner un ordinateur** , dans la zone de texte **Un autre ordinateur** , tapez le nom de l'ordinateur que vous voulez gérer et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="94bea-111">In the **Select Computer** dialog box, in the **Another computer** text box, type the name of the computer you want to manage, and then click **OK**.</span></span>  
  
     <span data-ttu-id="94bea-112">La Gestion de l'ordinateur affiche les services exécutés sur l'ordinateur distant.</span><span class="sxs-lookup"><span data-stu-id="94bea-112">Computer Management displays the services running on the remote computer.</span></span> <span data-ttu-id="94bea-113">Le nœud de niveau supérieur devient alors **Gestion de l’ordinateur** \<*remotecomputer*>.</span><span class="sxs-lookup"><span data-stu-id="94bea-113">The top-level node changes to **Computer Management** \<*remotecomputer*>.</span></span>  
  
4.  <span data-ttu-id="94bea-114">Dans l'arborescence de la console, développez **Services et applications**, puis **Gestionnaire de configuration SQL Server** pour gérer les services de l'ordinateur distant.</span><span class="sxs-lookup"><span data-stu-id="94bea-114">In the console tree, expand **Services and Applications**, and then expand **SQL Server Configuration Manager** to manage the remote computer's services.</span></span>  
  
#### <a name="to-save-a-link-to-sql-server-configuration-manager-for-another-computer"></a><span data-ttu-id="94bea-115">Pour enregistrer un lien vers le Gestionnaire de configuration SQL Server pour un autre ordinateur</span><span class="sxs-lookup"><span data-stu-id="94bea-115">To save a link to SQL Server Configuration Manager for another computer</span></span>  
  
1.  <span data-ttu-id="94bea-116">Dans le menu **Démarrer** , cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="94bea-116">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="94bea-117">Dans la zone **ouvrir** , tapez `mmc -a` pour ouvrir la [!INCLUDE[msCoName](../../includes/msconame-md.md)] console de gestion en mode auteur.</span><span class="sxs-lookup"><span data-stu-id="94bea-117">In the **Open** box, type `mmc -a` to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console in author mode.</span></span>  
  
3.  <span data-ttu-id="94bea-118">Dans le menu **Fichier** , cliquez sur **Ajouter/Supprimer un composant logiciel enfichable**.</span><span class="sxs-lookup"><span data-stu-id="94bea-118">On the **File** menu, click **Add/Remove Snap-in**.</span></span>  
  
4.  <span data-ttu-id="94bea-119">Dans la fenêtre **Ajouter/Supprimer un composant logiciel enfichable** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="94bea-119">In the **Add/Remove Snap-in** window, click **Add**.</span></span>  
  
5.  <span data-ttu-id="94bea-120">Dans la fenêtre **Ajout d’un composant logiciel enfichable autonome** , cliquez sur **Gestion de l’ordinateur** , puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="94bea-120">In the **Add Standalone Snap-in** window, click **Computer Management** and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="94bea-121">Dans la fenêtre **Gestion de l'ordinateur** , cliquez sur **Un autre ordinateur**, tapez le nom de l'ordinateur distant que vous souhaitez gérer, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="94bea-121">In the **Computer Management** window, click **Another computer**, type the name of the remote computer you wish to manage, and then click **Finish**.</span></span>  
  
7.  <span data-ttu-id="94bea-122">Dans la fenêtre **Ajout d’un composant logiciel enfichable autonome** , cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="94bea-122">In the **Add Standalone Snap-in** window, click **Close**.</span></span>  
  
8.  <span data-ttu-id="94bea-123">Dans la fenêtre **Ajouter/Supprimer un composant logiciel enfichable** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="94bea-123">In the **Add/Remove Snap-in** window, click **OK**.</span></span>  
  
9. <span data-ttu-id="94bea-124">Développez Gestion de l' **ordinateur ( ***\<computer name>*** )**, puis **services et applications**.</span><span class="sxs-lookup"><span data-stu-id="94bea-124">Expand **Computer Management (***\<computer name>***)**, and **Services and Applications**.</span></span>  
  
10. <span data-ttu-id="94bea-125">Cliquez avec le bouton droit sur **Gestionnaire de configuration SQL Server**, puis cliquez sur **Nouvelle fenêtre à partir d’ici**.</span><span class="sxs-lookup"><span data-stu-id="94bea-125">Right-click **SQL Server Configuration Manager**, and then click **New Window from here**.</span></span>  
  
11. <span data-ttu-id="94bea-126">Dans le menu **Fenêtre**, cliquez sur **Racine de la console** pour revenir à la première fenêtre et supprimez-la.</span><span class="sxs-lookup"><span data-stu-id="94bea-126">On the **Window** menu, click **Console Root**, to switch back to the first window, and delete the window.</span></span>  
  
12. <span data-ttu-id="94bea-127">Dans le menu **fichier** , cliquez sur **Enregistrer sous**, puis enregistrez le fichier dans le dossier de votre choix, avec un nom approprié avec l' `.msc` extension de fichier.</span><span class="sxs-lookup"><span data-stu-id="94bea-127">On the **File** menu, click **Save As**, and save the file in the desired folder, with an appropriate name with the `.msc` file extension.</span></span> <span data-ttu-id="94bea-128">Fermez [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console.</span><span class="sxs-lookup"><span data-stu-id="94bea-128">Close the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console.</span></span>  
  
13. <span data-ttu-id="94bea-129">Pour ouvrir le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur l'ordinateur cible, double-cliquez sur le fichier.</span><span class="sxs-lookup"><span data-stu-id="94bea-129">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager on the target computer, double-click the file.</span></span> <span data-ttu-id="94bea-130">Si vous le souhaitez, enregistrez un lien vers le fichier sur le bureau ou dans le menu **Démarrer** .</span><span class="sxs-lookup"><span data-stu-id="94bea-130">If desired, save a link to the file on the desktop or in the **Start** menu.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="94bea-131">Si vous utilisez le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur un ordinateur distant, le nom de l'ordinateur ne va pas de soi et il est possible d'arrêter ou de configurer accidentellement un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="94bea-131">When using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager on a remote computer, the computer name is not obvious and it is possible to mistakenly stop or configure the wrong computer.</span></span> <span data-ttu-id="94bea-132">Sous l'onglet **Service** , activez la case à cocher **Nom de l'hôte** pour confirmer le nom de l'ordinateur avant de modifier un service.</span><span class="sxs-lookup"><span data-stu-id="94bea-132">On the **Service** tab, check the **Host Name** box to confirm the computer name before modifying a service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94bea-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="94bea-133">See Also</span></span>  
 [<span data-ttu-id="94bea-134">Configurer WMI pour afficher l'état du serveur dans les outils SQL Server</span><span class="sxs-lookup"><span data-stu-id="94bea-134">Configure WMI to Show Server Status in SQL Server Tools</span></span>](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md)  
  
  
