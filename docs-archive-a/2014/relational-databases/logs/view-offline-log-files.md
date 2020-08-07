---
title: Afficher les fichiers journaux hors connexion | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Log File Viewer, viewing offline logs
- offline log files
ms.assetid: 9223e474-f224-4907-a4f2-081e11db58f5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2afc1992b54c78f69bfae1fc152b41c20bcd4ea1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612321"
---
# <a name="view-offline-log-files"></a><span data-ttu-id="827b4-102">Afficher les fichiers journaux hors connexion</span><span class="sxs-lookup"><span data-stu-id="827b4-102">View Offline Log Files</span></span>
  <span data-ttu-id="827b4-103">Depuis [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], vous pouvez consulter les fichiers journaux [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à partir d'une instance locale ou distante de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] lorsque l'instance cible est hors connexion ou ne peut pas démarrer.</span><span class="sxs-lookup"><span data-stu-id="827b4-103">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], you can view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files from a local or remote instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] when the target instance is offline or cannot start.</span></span>  
  
 <span data-ttu-id="827b4-104">Vous pouvez accéder aux fichiers journaux hors connexion à partir des serveurs inscrits, ou par programmation via des requêtes WMI et WQL (WMI Query Language).</span><span class="sxs-lookup"><span data-stu-id="827b4-104">You can access the offline log files from Registered Servers, or programmatically through WMI and WQL (WMI Query Language) queries.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="827b4-105">Vous pouvez également utiliser ces méthodes pour vous connecter à une instance qui est en ligne, mais à laquelle, pour une raison quelconque, vous ne pouvez pas vous connecter via une connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="827b4-105">You can also use these methods to connect to an instance that is online, but for some reason, you cannot connect through a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="827b4-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="827b4-106">Before you Begin</span></span>  
 <span data-ttu-id="827b4-107">Pour vous connecter aux fichiers journaux hors connexion, une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doit être installée sur l'ordinateur que vous utilisez pour consulter les fichiers journaux hors connexion, ainsi que sur l'ordinateur où se trouvent les fichiers journaux en question.</span><span class="sxs-lookup"><span data-stu-id="827b4-107">To connect to offline log files, an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be installed on the computer that you are using to view the offline log files, and on the computer where the log files that you want to view are located.</span></span> <span data-ttu-id="827b4-108">Si une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est installée sur les deux ordinateurs, vous pouvez afficher les fichiers hors connexion pour les instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], et pour les instances qui exécutent des versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur ces ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="827b4-108">If an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed on both computers, you can view offline files for instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and for instances that are running earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on either computer.</span></span>  
  
 <span data-ttu-id="827b4-109">Si vous utilisez des serveurs inscrits, l'instance à laquelle vous voulez vous connecter doit être enregistrée sous **Groupes de serveurs locaux** ou **Serveurs de gestion centralisée**</span><span class="sxs-lookup"><span data-stu-id="827b4-109">If you are using Registered Servers, the instance that you want to connect to must be registered under **Local Server Groups** or under **Central Management Servers**.</span></span> <span data-ttu-id="827b4-110">(l'instance peut être enregistrée seule ou être membre d'un groupe de serveurs). Pour plus d'informations sur l'ajout d'une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour des serveurs inscrits, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="827b4-110">(The instance can be registered on its own or be a member of a server group.) For more information about how to add an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to Registered Servers, see the following topics:</span></span>  
  
-   [<span data-ttu-id="827b4-111">Créer ou modifier un groupe de serveurs &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="827b4-111">Create or Edit a Server Group &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/register-servers/create-or-edit-a-server-group-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="827b4-112">Inscrire un serveur connecté &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="827b4-112">Register a Connected Server &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="827b4-113">Créer un serveur d’administration centralisée et un groupe de serveurs &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="827b4-113">Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/register-servers/create-a-central-management-server-and-server-group.md)  
  
 <span data-ttu-id="827b4-114">Pour plus d'informations sur l'affichage des fichiers journaux hors connexion par programmation via des requêtes WMI et WQL, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="827b4-114">For more information about how to view offline log files programmatically through WMI and WQL queries, see the following topics:</span></span>  
  
-   <span data-ttu-id="827b4-115">[Classe SqlErrorLogEvent](../wmi-provider-configuration-classes/sqlerrorlogevent-class.md) (cette rubrique indique comment récupérer des valeurs pour les événements enregistrés dans un fichier journal spécifié).</span><span class="sxs-lookup"><span data-stu-id="827b4-115">[SqlErrorLogEvent Class](../wmi-provider-configuration-classes/sqlerrorlogevent-class.md) (This topic shows how to retrieve values for logged events in a specified log file.)</span></span>  
  
-   <span data-ttu-id="827b4-116">[Classe SqlErrorLogFile](../wmi-provider-configuration-classes/sqlerrorlogfile-class.md) (cette rubrique indique comment récupérer des informations concernant tous les fichiers journaux [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur une instance spécifiée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="827b4-116">[SqlErrorLogFile Class](../wmi-provider-configuration-classes/sqlerrorlogfile-class.md) (This topic shows how to retrieve information about all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files on a specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="827b4-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="827b4-117">Permissions</span></span>  
 <span data-ttu-id="827b4-118">Pour vous connecter à un fichier journal hors connexion, vous devez disposer des autorisations suivantes sur les ordinateurs local et distant :</span><span class="sxs-lookup"><span data-stu-id="827b4-118">To connect to an offline log file, you must have the following permissions on both the local and remote computers:</span></span>  
  
-   <span data-ttu-id="827b4-119">Accès en lecture à l’espace de noms WMI **Root\Microsoft\SqlServer\ComputerManagement12** .</span><span class="sxs-lookup"><span data-stu-id="827b4-119">Read access to the **Root\Microsoft\SqlServer\ComputerManagement12** WMI namespace.</span></span> <span data-ttu-id="827b4-120">Par défaut, tout le monde dispose de l'accès en lecture via l'autorisation Activer le compte.</span><span class="sxs-lookup"><span data-stu-id="827b4-120">By default, everyone has read access through the Enable Account permission.</span></span> <span data-ttu-id="827b4-121">Pour plus d'informations, consultez la procédure « Pour vérifier les autorisations WMI », plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="827b4-121">For more information, see the "To verify WMI permissions" procedure later in this section.</span></span>  
  
-   <span data-ttu-id="827b4-122">Autorisation en lecture pour le dossier qui contient les fichiers journaux des erreurs.</span><span class="sxs-lookup"><span data-stu-id="827b4-122">Read permission to the folder that contains the error log files.</span></span> <span data-ttu-id="827b4-123">Par défaut, ces fichiers journaux se trouvent à l'emplacement suivant (où \<*Drive> représente le lecteur sur lequel vous avez installé [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et \<*InstanceName*> est le nom de l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]) :</span><span class="sxs-lookup"><span data-stu-id="827b4-123">By default the error log files are located in the following path (where \<*Drive>\* represents the drive where you installed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and \<*InstanceName*> is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]):</span></span>  
  
     <span data-ttu-id="827b4-124">**\<Drive>: \Program Files\Microsoft SQL Server\MSSQL12. \<InstanceName> \MSSQL\Log**</span><span class="sxs-lookup"><span data-stu-id="827b4-124">**\<Drive>:\Program Files\Microsoft SQL Server\MSSQL12.\<InstanceName>\MSSQL\Log**</span></span>  
  
 <span data-ttu-id="827b4-125">Pour vérifier les paramètres de sécurité de l'espace de noms WMI, utilisez le composant logiciel enfichable Contrôle WMI.</span><span class="sxs-lookup"><span data-stu-id="827b4-125">To verify WMI namespace security settings, you can use the WMI Control snap-in.</span></span>  
  
#### <a name="to-verify-wmi-permissions"></a><span data-ttu-id="827b4-126">Pour vérifier les autorisations WMI</span><span class="sxs-lookup"><span data-stu-id="827b4-126">To verify WMI permissions</span></span>  
  
1.  <span data-ttu-id="827b4-127">Ouvrez le composant logiciel enfichable Contrôle WMI.</span><span class="sxs-lookup"><span data-stu-id="827b4-127">Open the WMI Control snap-in.</span></span> <span data-ttu-id="827b4-128">Pour ce faire, effectuez l'une des procédures suivantes, en fonction de votre système d'exploitation :</span><span class="sxs-lookup"><span data-stu-id="827b4-128">To do this, do either of the following, depending on the operating system:</span></span>  
  
    -   <span data-ttu-id="827b4-129">Cliquez sur **Démarrer**, tapez `wmimgmt.msc` dans la zone **Rechercher** , puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="827b4-129">Click **Start**, type `wmimgmt.msc` in the **Start Search** box, and then press ENTER.</span></span>  
  
    -   <span data-ttu-id="827b4-130">Cliquez sur **Démarrer**, sur **exécuter**, tapez `wmimgmt.msc` , puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="827b4-130">Click **Start**, click **Run**, type `wmimgmt.msc`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="827b4-131">Par défaut, le composant logiciel enfichable Contrôle WMI gère l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="827b4-131">By default, the WMI Control snap-in manages the local computer.</span></span>  
  
     <span data-ttu-id="827b4-132">Si vous souhaitez vous connecter à un ordinateur distant, suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="827b4-132">If you want to connect to a remote computer, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="827b4-133">Cliquez avec le bouton droit sur **Contrôle WMI (local)** , puis cliquez sur **Se connecter à un autre ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="827b4-133">Right-click **WMI Control (Local)**, and then click **Connect to another computer**.</span></span>  
  
    2.  <span data-ttu-id="827b4-134">Dans la boîte de dialogue **Changer d'ordinateur géré** , cliquez sur **Un autre ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="827b4-134">In the **Change managed computer** dialog box, click **Another computer**.</span></span>  
  
    3.  <span data-ttu-id="827b4-135">Entrez le nom de l'ordinateur distant, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="827b4-135">Enter the remote computer name, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="827b4-136">Cliquez avec le bouton droit sur **contrôle WMI (local)** ou **contrôle WMI (***remotecomputername***)**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="827b4-136">Right-click **WMI Control (Local)** or **WMI Control (***RemoteComputerName***)**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="827b4-137">Dans la boîte de dialogue **Propriétés du Contrôle WMI** , cliquez sur l'onglet **Sécurité** .</span><span class="sxs-lookup"><span data-stu-id="827b4-137">In the **WMI Control Properties** dialog box, click the **Security** tab.</span></span>  
  
5.  <span data-ttu-id="827b4-138">Dans l'arborescence d'espace de noms, localisez l'espace de noms suivant, puis cliquez dessus :</span><span class="sxs-lookup"><span data-stu-id="827b4-138">In the namespace tree, locate and then click the following namespace:</span></span>  
  
     <span data-ttu-id="827b4-139">**Root\Microsoft\SqlServer\ComputerManagement10**</span><span class="sxs-lookup"><span data-stu-id="827b4-139">**Root\Microsoft\SqlServer\ComputerManagement10**</span></span>  
  
6.  <span data-ttu-id="827b4-140">Cliquez sur **Sécurité**.</span><span class="sxs-lookup"><span data-stu-id="827b4-140">Click **Security**.</span></span>  
  
7.  <span data-ttu-id="827b4-141">Assurez-vous que le compte qui sera utilisé a l'autorisation **Activer le compte** .</span><span class="sxs-lookup"><span data-stu-id="827b4-141">Make sure that the account that will be used has the **Enable Account** permission.</span></span> <span data-ttu-id="827b4-142">Cette autorisation autorise l'accès en lecture aux objets WMI.</span><span class="sxs-lookup"><span data-stu-id="827b4-142">This permission allows Read access to WMI objects.</span></span>  
  
### <a name="view-log-files"></a><span data-ttu-id="827b4-143">Afficher les fichiers journaux</span><span class="sxs-lookup"><span data-stu-id="827b4-143">View Log Files</span></span>  
 <span data-ttu-id="827b4-144">La procédure suivante indique comment afficher les fichiers journaux hors connexion via des serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="827b4-144">The following procedure shows how to view offline log files through Registered Servers.</span></span> <span data-ttu-id="827b4-145">Cette procédure suppose que la condition suivante est remplie :</span><span class="sxs-lookup"><span data-stu-id="827b4-145">The procedure assumes the following:</span></span>  
  
 <span data-ttu-id="827b4-146">L'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à laquelle vous voulez vous connecter est déjà enregistrée auprès des serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="827b4-146">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to connect to is already registered in Registered Servers.</span></span>  
  
##### <a name="to-view-log-files-for-instances-that-are-offline"></a><span data-ttu-id="827b4-147">Pour afficher des fichiers journaux d'instances hors connexion</span><span class="sxs-lookup"><span data-stu-id="827b4-147">To view log files for instances that are offline</span></span>  
  
1.  <span data-ttu-id="827b4-148">Si vous souhaitez afficher les fichiers journaux hors connexion sur une instance locale, assurez-vous que vous démarrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] avec des autorisations élevées.</span><span class="sxs-lookup"><span data-stu-id="827b4-148">If you want to view offline log files on a local instance, make sure that you start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] with elevated permissions.</span></span> <span data-ttu-id="827b4-149">Pour ce faire, lorsque vous démarrez [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], cliquez avec le bouton droit sur **SQL Server Management Studio**, puis cliquez sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="827b4-149">To do this, when you start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], right-click **SQL Server Management Studio**, and then click **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="827b4-150">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], dans le menu **Affichage** , cliquez sur **Serveurs inscrits**.</span><span class="sxs-lookup"><span data-stu-id="827b4-150">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Registered Servers**.</span></span>  
  
3.  <span data-ttu-id="827b4-151">Dans l'arborescence de la console, trouvez l'instance sur laquelle vous voulez afficher les fichiers hors connexion.</span><span class="sxs-lookup"><span data-stu-id="827b4-151">In the console tree, locate the instance on which you want to view the offline files.</span></span>  
  
4.  <span data-ttu-id="827b4-152">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="827b4-152">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="827b4-153">Si l’instance est sous **Groupes de serveurs locaux**, développez **Groupes de serveurs locaux**, développez le groupe de serveurs (si l’instance est un membre d’un groupe), cliquez avec le bouton droit sur l’instance, puis cliquez sur **Afficher le journal SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="827b4-153">If the instance is under **Local Server Groups**, expand **Local Server Groups**, expand the server group (if the instance is a member of a group), right-click the instance, and then click **View SQL Server Log**.</span></span>  
  
    -   <span data-ttu-id="827b4-154">Si l’instance est le serveur de gestion centralisée lui-même, développez **Serveurs de gestion centralisée**, cliquez avec le bouton droit sur l’instance, pointez sur **Actions du serveur de gestion centralisée**, puis cliquez sur **Afficher le journal SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="827b4-154">If the instance is the Central Management Server itself, expand **Central Management Servers**, right-click the instance, point to **Central Management Server Actions**, and then click **View SQL Server Log**.</span></span>  
  
    -   <span data-ttu-id="827b4-155">Si l’instance est sous **Serveurs de gestion centralisée**, développez **Serveurs de gestion centralisée**, développez le serveur de gestion centralisée, cliquez avec le bouton droit sur l’instance (ou développez un groupe de serveurs et cliquez avec le bouton droit sur l’instance), puis cliquez sur **Afficher le journal SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="827b4-155">If the instance is under **Central Management Servers**, expand **Central Management Servers**, expand the Central Management Server, right-click the instance (or expand a server group and right-click the instance), and then click **View SQL Server Log**.</span></span>  
  
5.  <span data-ttu-id="827b4-156">Si vous vous connectez à une instance locale, la connexion est établie à l'aide des informations d'identification de l'utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="827b4-156">If you are connecting to a local instance, the connection is made using the current user credentials.</span></span>  
  
     <span data-ttu-id="827b4-157">Si vous vous connectez à une instance distante, dans la boîte de dialogue **Visionneuse du fichier journal - Se connecter en tant que** , effectuez l’une ou l’autre des procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="827b4-157">If you are connecting to a remote instance, in the **Log File Viewer - Connect As** dialog box, do either of the following:</span></span>  
  
    -   <span data-ttu-id="827b4-158">Pour vous connecter en tant qu'utilisateur actuel, assurez-vous que la case à cocher **Se connecter en tant qu'autre utilisateur** est désactivée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="827b4-158">To connect as the current user, make sure that the **Connect as another user** check box is cleared, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="827b4-159">Pour vous connecter en tant qu'autre utilisateur, activez la case à cocher **Se connecter en tant qu'autre utilisateur** , puis cliquez sur **Définir l'utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="827b4-159">To connect as another user, select the **Connect as another user** check box, and then click **Set User**.</span></span> <span data-ttu-id="827b4-160">Lorsqu’un message vous y invite, entrez les informations d’identification de l’utilisateur (avec le nom d’utilisateur au format *nom-domaine*\\*nom-utilisateur*), cliquez sur **OK**, puis cliquez de nouveau sur **OK** pour vous connecter.</span><span class="sxs-lookup"><span data-stu-id="827b4-160">When you are prompted, enter the user credentials (with the user name in the format *domain_name*\\*user_name*), click **OK**, and then click **OK** again to connect.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="827b4-161">Si les fichiers journaux mettent trop de temps à se charger, vous pouvez cliquer sur **Arrêt** dans la barre d’outils de la Visionneuse du fichier journal.</span><span class="sxs-lookup"><span data-stu-id="827b4-161">If the log files take too long to load, you can click **Stop** on the Log File Viewer toolbar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="827b4-162">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="827b4-162">See Also</span></span>  
 [<span data-ttu-id="827b4-163">Visionneuse du fichier journal</span><span class="sxs-lookup"><span data-stu-id="827b4-163">Log File Viewer</span></span>](log-file-viewer.md)  
  
  
