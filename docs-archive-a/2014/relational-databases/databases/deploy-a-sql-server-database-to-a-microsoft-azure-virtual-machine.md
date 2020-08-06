---
title: Déployer une base de données SQL Server sur une machine virtuelle Microsoft Azure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.deploymentwizard.deploymentsettings.f1
- sql12.swb.deploymentwizard.progress.f1
- sql11.swb.usevmdialog.f1
- sql11.swb.deploymentwizard.f1
- sql12.swb.deploymentwizard.azuresignin.f1
- sql11.swb.deploymentwizard.summary.f1
- sql11.swb.deploymentwizard.azuresignin.f1
- sql12.swb.deploymentwizard.f1
- sql12.swb.sqlvmdialog.f1
- sql11.swb.newvmdialog.f1
- sql12.swb.deploymentwizard.results.f1
- sql11.swb.deploymentwizard.progress.f1
- sql12.swb.newvmdialog.f1
- sql12.swb.deploymentwizard.sourcesettings.f1
- sql12.swb.usevmdialog.f1
- sql11.swb.deploymentwizard.sourcesettings.f1
- sql11.swb.deploymentwizard.results.f1
- sql12.swb.deploymentwizard.summary.f1
- sql11.swb.deploymentwizard.deploymentsettings.f1
helpviewer_keywords:
- Deploy a database
- Deploy to Azure VM
- Migrate to Azure
- Azure virtual machine
- Migrate to Azure VM
- Migrate to the cloud
- SQL Server Management Studio
- SSMS
- Deploy database wizard
- Deploy a SQL Server database to Azure
- Azure VM
ms.assetid: 5e82e66a-262e-4d4f-aa89-39cb62696d06
author: stevestein
ms.author: sstein
ms.openlocfilehash: d48c06db038a775811cba6705fbaf1d97a960f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705167"
---
# <a name="deploy-a-sql-server-database-to-a-microsoft-azure-virtual-machine"></a><span data-ttu-id="850f4-102">Déployer une base de données SQL Server sur une machine virtuelle Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="850f4-102">Deploy a SQL Server Database to a Microsoft Azure Virtual Machine</span></span>
  <span data-ttu-id="850f4-103">Utilisez l’Assistant **déployer une base de données SQL Server sur une machine virtuelle Azure** pour déployer une base de données à partir d’une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] vers [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans une machine virtuelle Azure.</span><span class="sxs-lookup"><span data-stu-id="850f4-103">Use the **Deploy a SQL Server Database to an Azure VM** wizard to deploy a database from an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in an Azure Virtual Machine (VM).</span></span> <span data-ttu-id="850f4-104">L'Assistant utilise une sauvegarde complète de la base de données ; par conséquent, il copie toujours le schéma complet de la base de données et les données d'une base de données utilisateur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="850f4-104">The wizard utilizes a full database backup operation, so it always copies the complete database schema and the data from a SQL Server user database.</span></span> <span data-ttu-id="850f4-105">L'Assistant effectue également toutes les configurations de machine virtuelle Windows Azure pour vous ; par conséquent, aucune configuration préalable de machine virtuelle n'est requise.</span><span class="sxs-lookup"><span data-stu-id="850f4-105">The wizard also does all of the Azure VM configuration for you, so no pre-configuration of the VM is required.</span></span>  
  
 <span data-ttu-id="850f4-106">Vous ne pouvez pas utiliser l'Assistant pour les sauvegardes différentielles, car il ne remplace pas une base de données existante portant le même nom de base de données.</span><span class="sxs-lookup"><span data-stu-id="850f4-106">You cannot use the wizard for differential backups because the wizard will not overwrite an existing database that has the same database name.</span></span> <span data-ttu-id="850f4-107">Pour remplacer une base de données existante sur la machine virtuelle, vous devez d'abord supprimer la base de données existante ou modifier le nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="850f4-107">To replace an existing database on the VM, you must first drop the existing database or change the database name.</span></span> <span data-ttu-id="850f4-108">S'il existe un conflit de noms entre le nom de la base de données d'une opération de déploiement en cours et d'une base de données existante sur la machine virtuelle, l'Assistant suggère un nom de base de données avec suffixe pour la base de données en cours pour vous permettre d'effectuer cette opération.</span><span class="sxs-lookup"><span data-stu-id="850f4-108">If there is a naming conflict between the database name for an in-flight deploy operation and an existing database on the VM, the wizard will suggest an appended database name for the in-flight database to enable you to complete the operation.</span></span>  
  
##  <a name="before-you-begin"></a><a name="before_you_begin"></a> <span data-ttu-id="850f4-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="850f4-109">Before You Begin</span></span>  
 <span data-ttu-id="850f4-110">Pour exécuter cet Assistant, vous devez être en mesure de fournir les informations suivantes et avoir défini ces paramètres de configuration :</span><span class="sxs-lookup"><span data-stu-id="850f4-110">To complete this wizard, you must be able to provide the following information and have these configuration settings in place:</span></span>  
  
-   <span data-ttu-id="850f4-111">Les détails de compte Microsoft associés à votre abonnement Azure.</span><span class="sxs-lookup"><span data-stu-id="850f4-111">The Microsoft account details associated with your Azure subscription.</span></span>  
  
-   <span data-ttu-id="850f4-112">Votre profil de publication Azure.</span><span class="sxs-lookup"><span data-stu-id="850f4-112">Your Azure publishing profile.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="850f4-113">SQL Server prend actuellement en charge la version 2.0 du profil de publication.</span><span class="sxs-lookup"><span data-stu-id="850f4-113">SQL Server currently supports publishing profile version 2.0.</span></span> <span data-ttu-id="850f4-114">Pour télécharger la version prise en charge du profil de publication, consultez [Télécharger le profil de publication 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span><span class="sxs-lookup"><span data-stu-id="850f4-114">To download the supported version of the publishing profile, see [Download Publishing Profile 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span></span>  
  
-   <span data-ttu-id="850f4-115">Le certificat de gestion téléchargé dans votre abonnement Azure.</span><span class="sxs-lookup"><span data-stu-id="850f4-115">The management certificate uploaded to your Azure subscription.</span></span>  
  
-   <span data-ttu-id="850f4-116">Certificat de gestion enregistré dans le magasin de certificats personnel de l'ordinateur local sur lequel l'Assistant s'exécute.</span><span class="sxs-lookup"><span data-stu-id="850f4-116">The management certificate saved into the personal certificate store on the computer where the wizard is running.</span></span>  
  
-   <span data-ttu-id="850f4-117">Vous devez disposer d'un emplacement de stockage temporaire disponible sur l'ordinateur sur lequel la base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est hébergée.</span><span class="sxs-lookup"><span data-stu-id="850f4-117">You must have a temporary storage location that is available to the computer where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database is hosted.</span></span> <span data-ttu-id="850f4-118">L'emplacement de stockage temporaire doit également être disponible sur l'ordinateur sur lequel s'exécute l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="850f4-118">The temporary storage location must also be available to the computer where the wizard is running.</span></span>  
  
-   <span data-ttu-id="850f4-119">Si vous déployez la base de données sur un ordinateur virtuel existant, l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doit être configurée pour écouter sur un port TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="850f4-119">If you are deploying the database to an existing VM, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be configured to listen on a TCP/IP port.</span></span>  
  
-   <span data-ttu-id="850f4-120">Une machine virtuelle Azure ou une image de galerie que vous prévoyez d’utiliser pour la création de la machine virtuelle doit avoir la SQL Server adaptateur cloud configurée et en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="850f4-120">Either an Azure VM or Gallery image you plan to use for creation of the VM must have the SQL Server Cloud Adapter configured and running.</span></span>  
  
-   <span data-ttu-id="850f4-121">Vous devez configurer un point de terminaison ouvert pour votre SQL Server adaptateur cloud sur la passerelle Azure avec le port privé 11435.</span><span class="sxs-lookup"><span data-stu-id="850f4-121">You must configure an open endpoint for your SQL Server Cloud Adapter on the Azure gateway with private port 11435.</span></span>  
  
 <span data-ttu-id="850f4-122">En outre, si vous envisagez de déployer votre base de données dans une machine virtuelle Azure existante, vous devez également être en mesure de fournir les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="850f4-122">In addition, if you plan to deploy your database into an existing Azure VM, you must also be able to provide:</span></span>  
  
-   <span data-ttu-id="850f4-123">Nom DNS du service de cloud computing qui héberge votre ordinateur virtuel.</span><span class="sxs-lookup"><span data-stu-id="850f4-123">The DNS name of the cloud service that hosts your VM.</span></span>  
  
-   <span data-ttu-id="850f4-124">Informations d'identification de l'administrateur pour l'ordinateur virtuel.</span><span class="sxs-lookup"><span data-stu-id="850f4-124">Administrator credentials for the VM.</span></span>  
  
-   <span data-ttu-id="850f4-125">Informations d'identifications avec privilèges d'opérateur Backup sur la base de données que vous prévoyez de déployer, à partir de l'instance source de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="850f4-125">Credentials with Backup operator privileges on the database you plan to deploy, from the source instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="850f4-126">Pour plus d’informations sur l’exécution de SQL Server dans des machines virtuelles Azure, consultez se [préparer à migrer vers SQL Server dans les machines virtuelles Azure](https://msdn.microsoft.com/library/dn133142.aspx).</span><span class="sxs-lookup"><span data-stu-id="850f4-126">For more information about running SQL Server in Azure virtual machines, see [Getting Ready to Migrate to SQL Server in Azure Virtual Machines](https://msdn.microsoft.com/library/dn133142.aspx).</span></span>  
  
 <span data-ttu-id="850f4-127">Sur les ordinateurs qui exécutent des systèmes d'exploitation Windows Server, vous devez utiliser les paramètres de configuration suivants pour exécuter l'Assistant :</span><span class="sxs-lookup"><span data-stu-id="850f4-127">On computers running Windows Server operating systems, you must use the following configuration settings to run this wizard:</span></span>  
  
-   <span data-ttu-id="850f4-128">Désactivez la configuration de sécurité renforcée : utilisez le Gestionnaire de serveur > Serveur local pour définir la configuration de sécurité renforcée (ESC) d’Internet Explorer sur **OFF**.</span><span class="sxs-lookup"><span data-stu-id="850f4-128">Turn off Enhanced Security Configuration:  Use Server Manager > Local Server to set Internet Explorer Enhanced Security Configuration (ESC) to **OFF**.</span></span>  
  
-   <span data-ttu-id="850f4-129">Activez JavaScript : Internet Explorer > Options Internet > Sécurité > Niveau client > Création de scripts > Active Scripting : **Activer**.</span><span class="sxs-lookup"><span data-stu-id="850f4-129">Enable JavaScript:  Internet Explorer > Internet Options > Security > Customer Level > Scripting > Active Scripting: **Enable**.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="limitations"></a> <span data-ttu-id="850f4-130">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="850f4-130">Limitations and Restrictions</span></span>  
 <span data-ttu-id="850f4-131">La limite de taille de la base de données pour cette opération est 1 To.</span><span class="sxs-lookup"><span data-stu-id="850f4-131">The database size limitation for this operation is 1 TB.</span></span>  
  
 <span data-ttu-id="850f4-132">Ce déploiement est disponible dans SQL Server Management Studio pour [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="850f4-132">This deployment feature is available in SQL Server Management Studio for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span></span>  
  
 <span data-ttu-id="850f4-133">Cette fonctionnalité de déploiement sert uniquement avec les bases de données utilisateur ; le déploiement de bases de données système n'est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="850f4-133">This deployment feature is for use only with user databases; deploying system databases is not supported.</span></span>  
  
 <span data-ttu-id="850f4-134">La fonctionnalité de déploiement ne prend pas en charge les services hébergés qui sont associés à un groupe d'affinités.</span><span class="sxs-lookup"><span data-stu-id="850f4-134">The deployment feature does not support hosted services that are associated with an Affinity Group.</span></span> <span data-ttu-id="850f4-135">Par exemple, les comptes de stockage associés à un groupe d'affinités ne peuvent pas être sélectionnés pour être utilisés sur la page **Paramètres de déploiement** de cet Assistant.</span><span class="sxs-lookup"><span data-stu-id="850f4-135">For example, storage accounts associated with an Affinity Group cannot be selected for use on the **Deployment Settings** page of this wizard.</span></span>  
  
 <span data-ttu-id="850f4-136">La version de SQL Server dans la machine virtuelle doit être identique ou ultérieure à la version de SQL Server source.</span><span class="sxs-lookup"><span data-stu-id="850f4-136">The SQL Server version in the VM must be the same or later than the source SQL Server version.</span></span> <span data-ttu-id="850f4-137">SQL Server versions de base de données qui peuvent être déployées sur une machine virtuelle Azure à l’aide de cet Assistant :</span><span class="sxs-lookup"><span data-stu-id="850f4-137">SQL Server database versions that can be deployed to an Azure VM using this wizard:</span></span>  
  
-   <span data-ttu-id="850f4-138">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="850f4-138">SQL Server 2008</span></span>  
  
-   <span data-ttu-id="850f4-139">SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="850f4-139">SQL Server 2008 R2</span></span>  
  
-   <span data-ttu-id="850f4-140">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="850f4-140">SQL Server 2012</span></span>  
  
-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]  
  
 <span data-ttu-id="850f4-141">SQL Server versions de base de données qui s’exécutent dans une base de données de machine virtuelle Azure peuvent être déployées sur :</span><span class="sxs-lookup"><span data-stu-id="850f4-141">SQL Server database versions running in an Azure VM database can be deployed to:</span></span>  
  
-   <span data-ttu-id="850f4-142">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="850f4-142">SQL Server 2012</span></span>  
  
-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]  
  
 <span data-ttu-id="850f4-143">S'il existe un conflit de noms entre le nom de la base de données d'une opération de déploiement en cours et d'une base de données existante sur la machine virtuelle, l'Assistant suggère un nom de base de données avec suffixe pour la base de données en cours pour vous permettre d'effectuer cette opération.</span><span class="sxs-lookup"><span data-stu-id="850f4-143">If there is a naming conflict between the database name for an in-flight deploy operation and an existing database on the VM, the wizard will suggest an appended database name for the in-flight database to enable you to complete the operation.</span></span>  
  
###  <a name="considerations-for-deploying-a-filestream-enabled-database-to-an-azure-vm"></a><a name="filestream"></a> <span data-ttu-id="850f4-144">Éléments à prendre en considération pour déployer une base de données FILESTREAM sur des machines virtuelles Windows Azure</span><span class="sxs-lookup"><span data-stu-id="850f4-144">Considerations for Deploying a FILESTREAM-enabled Database to an Azure VM</span></span>  
 <span data-ttu-id="850f4-145">Tenez compte des instructions et des restrictions suivantes lorsque vous déployez des bases de données possédant des objets blob stockés dans des objets FILESTREAM :</span><span class="sxs-lookup"><span data-stu-id="850f4-145">Note the following guidelines and restrictions when deploying databases that have BLOBS stored in FILESTREAM objects:</span></span>  
  
-   <span data-ttu-id="850f4-146">La fonctionnalité de déploiement ne peut pas déployer une base de données FILESTREAM dans de nouvelles machines virtuelles.</span><span class="sxs-lookup"><span data-stu-id="850f4-146">The deployment feature cannot deploy a FILESTREAM-enabled database into a new VM.</span></span> <span data-ttu-id="850f4-147">Si FILESTREAM n'est pas activé dans la machine virtuelle avant d'exécuter l'Assistant, l'opération de restauration de base de données échouera et l'Assistant ne pourra pas achever l'opération.</span><span class="sxs-lookup"><span data-stu-id="850f4-147">If FILESTREAM is not enabled in the VM before you run the wizard, the database restore operation will fail and the wizard operation will not be able to complete successfully.</span></span> <span data-ttu-id="850f4-148">Pour déployer correctement une base de données qui utilise FILESTREAM, activez FILESTREAM dans l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur la machine virtuelle hôte avant de lancer l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="850f4-148">To successfully deploy a database that uses FILESTREAM, enable FILESTREAM in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on the host VM before launching the wizard.</span></span> <span data-ttu-id="850f4-149">Pour plus d’informations, consultez [FILESTREAM (SQL Server)](https://msdn.microsoft.com/library/gg471497.aspx).</span><span class="sxs-lookup"><span data-stu-id="850f4-149">For more information, see [FILESTREAM (SQL Server)](https://msdn.microsoft.com/library/gg471497.aspx).</span></span>  
  
-   <span data-ttu-id="850f4-150">Si votre base de données utilise l'OLTP en mémoire, déployez la base de données sur une machine virtuelle Azure sans aucune modification à la base de données.</span><span class="sxs-lookup"><span data-stu-id="850f4-150">If your database utilizes In-Memory OLTP, you can deploy the database to an Azure VM without any modifications to the database.</span></span> <span data-ttu-id="850f4-151">Pour plus d’informations, consultez [OLTP en mémoire (optimisation en mémoire)](https://msdn.microsoft.com/library/dn133186\(SQL.120\).aspx).</span><span class="sxs-lookup"><span data-stu-id="850f4-151">For more information, see [In-Memory OLTP (In-Memory Optimization)](https://msdn.microsoft.com/library/dn133186\(SQL.120\).aspx).</span></span>  
  
###  <a name="considerations-for-geographic-distribution-of-assets"></a><a name="geography"></a><span data-ttu-id="850f4-152">Considérations relatives à la répartition géographique des ressources</span><span class="sxs-lookup"><span data-stu-id="850f4-152">Considerations for Geographic Distribution of Assets</span></span>  
 <span data-ttu-id="850f4-153">Notez que les actifs suivants doivent se trouver dans la même région géographique :</span><span class="sxs-lookup"><span data-stu-id="850f4-153">Note that the following assets must be located in the same geographic region:</span></span>  
  
-   <span data-ttu-id="850f4-154">Service cloud</span><span class="sxs-lookup"><span data-stu-id="850f4-154">Cloud Service</span></span>  
  
-   <span data-ttu-id="850f4-155">Emplacement de la machine virtuelle</span><span class="sxs-lookup"><span data-stu-id="850f4-155">VM Location</span></span>  
  
-   <span data-ttu-id="850f4-156">Service de stockage de disque de données</span><span class="sxs-lookup"><span data-stu-id="850f4-156">Data Disk Storage Service</span></span>  
  
 <span data-ttu-id="850f4-157">Si les actifs répertoriés ci-dessus ne sont pas colocalisés, l'Assistant ne pourra pas terminer l'opération.</span><span class="sxs-lookup"><span data-stu-id="850f4-157">If the assets listed above are not co-located, the wizard will not be able to complete successfully.</span></span>  
  
###  <a name="wizard-configuration-settings"></a><a name="configuration_settings"></a> <span data-ttu-id="850f4-158">Assistant Paramètres de configuration</span><span class="sxs-lookup"><span data-stu-id="850f4-158">Wizard Configuration Settings</span></span>  
 <span data-ttu-id="850f4-159">Utilisez les informations de configuration suivantes pour modifier les paramètres d'un déploiement de base de données de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vers une machine virtuelle Azure.</span><span class="sxs-lookup"><span data-stu-id="850f4-159">Use the following configuration details to modify settings for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database deployment to an Azure VM.</span></span>  
  
-   <span data-ttu-id="850f4-160">**Chemin par défaut du fichier de configuration** - %LOCALAPPDATA%\SQL Server\Deploy to SQL in WA VM\DeploymentSettings.xml</span><span class="sxs-lookup"><span data-stu-id="850f4-160">**Default path for the configuration file** - %LOCALAPPDATA%\SQL Server\Deploy to SQL in WA VM\DeploymentSettings.xml</span></span>  
  
-   <span data-ttu-id="850f4-161">**Structure du fichier de configuration**</span><span class="sxs-lookup"><span data-stu-id="850f4-161">**Configuration file structure**</span></span>  
  
    -   \<DeploymentSettings>  
  
        -   <span data-ttu-id="850f4-162"><OtherSettings</span><span class="sxs-lookup"><span data-stu-id="850f4-162"><OtherSettings</span></span>  
  
            -   <span data-ttu-id="850f4-163">TraceLevel = "débogage"\<!-- Logging level --></span><span class="sxs-lookup"><span data-stu-id="850f4-163">TraceLevel="Debug" \<!-- Logging level --></span></span>  
  
            -   <span data-ttu-id="850f4-164">BackupPath = " \\ \\ [nom serveur] \\ [volume] \\ "\<!-- The last used path for backup. Used as default in the wizard. --></span><span class="sxs-lookup"><span data-stu-id="850f4-164">BackupPath="\\\\[server name]\\[volume]\\" \<!-- The last used path for backup. Used as default in the wizard. --></span></span>  
  
            -   <span data-ttu-id="850f4-165">CleanupDisabled = false/>\<!-- Wizard will not delete intermediate files and Azure objects (VM, CS, SA). --></span><span class="sxs-lookup"><span data-stu-id="850f4-165">CleanupDisabled = False /> \<!-- Wizard will not delete intermediate files and Azure objects (VM, CS, SA). --></span></span>  
  
        -   <span data-ttu-id="850f4-166"><PublishProfile\<!-- The last used publish profile information. --></span><span class="sxs-lookup"><span data-stu-id="850f4-166"><PublishProfile \<!-- The last used publish profile information. --></span></span>  
  
            -   <span data-ttu-id="850f4-167">Certificate = "12A34B567890123ABCD4EF567A8"\<!-- The certificate for use in the wizard. --></span><span class="sxs-lookup"><span data-stu-id="850f4-167">Certificate="12A34B567890123ABCD4EF567A8" \<!-- The certificate for use in the wizard. --></span></span>  
  
            -   <span data-ttu-id="850f4-168">Subscription = "1a2b34c5-67d8-90ef-AB12-xxxxxxxxxxxxx"\<!-- The subscription for use in the wizard. --></span><span class="sxs-lookup"><span data-stu-id="850f4-168">Subscription="1a2b34c5-67d8-90ef-ab12-xxxxxxxxxxxxx" \<!-- The subscription for use in the wizard. --></span></span>  
  
            -   <span data-ttu-id="850f4-169">Name = « mon abonnement »\<!-- The name of the subscription. --></span><span class="sxs-lookup"><span data-stu-id="850f4-169">Name="My Subscription" \<!-- The name of the subscription. --></span></span>  
  
            -   <span data-ttu-id="850f4-170">Publisher="" /></span><span class="sxs-lookup"><span data-stu-id="850f4-170">Publisher="" /></span></span>  
  
    -   \</DeploymentSettings>  
  
 <span data-ttu-id="850f4-171">**Valeurs du fichier de configuration**</span><span class="sxs-lookup"><span data-stu-id="850f4-171">**Configuration file values**</span></span>  
  
###  <a name="permissions"></a><a name="permissions"></a> <span data-ttu-id="850f4-172">Autorisations</span><span class="sxs-lookup"><span data-stu-id="850f4-172">Permissions</span></span>  
 <span data-ttu-id="850f4-173">La base de données déployée doit avoir un état normal, doit être accessible au compte d'utilisateur qui exécute l'Assistant, et le compte d'utilisateur doit avoir les autorisations requises pour exécuter une opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="850f4-173">The database being deployed must be in a normal state, the database must be accessible to the user account running the wizard, and the user account must have permissions to perform a backup operation.</span></span>  
  
##  <a name="using-the-deploy-database-to-azure-vm-wizard"></a><a name="launch_wizard"></a><span data-ttu-id="850f4-174">Utilisation de l’Assistant déployer une base de données sur une machine virtuelle Azure</span><span class="sxs-lookup"><span data-stu-id="850f4-174">Using the Deploy Database to Azure VM Wizard</span></span>  
 <span data-ttu-id="850f4-175">**Pour lancer l'Assistant, suivez les étapes suivantes :**</span><span class="sxs-lookup"><span data-stu-id="850f4-175">**To launch the wizard, use the following steps:**</span></span>  
  
1.  <span data-ttu-id="850f4-176">Utilisez SQL Server Management Studio pour vous connecter à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec la base de données que vous souhaitez déployer.</span><span class="sxs-lookup"><span data-stu-id="850f4-176">Use SQL Server Management Studio to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with the database you want to deploy.</span></span>  
  
2.  <span data-ttu-id="850f4-177">Dans l' **Explorateur d'objets**, développez le nom de l'instance, puis développez le nœud **Bases de données** .</span><span class="sxs-lookup"><span data-stu-id="850f4-177">In **Object Explorer**, expand the instance name, then expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="850f4-178">Cliquez avec le bouton droit sur la base de données que vous souhaitez déployer, sélectionnez **tâches**, puis sélectionnez **déployer la base de données sur une machine virtuelle Azure...**</span><span class="sxs-lookup"><span data-stu-id="850f4-178">Right-click the database you want to deploy, select **Tasks**, and then select **Deploy Database to Azure VM...**</span></span>  
  

  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="850f4-179">Page Introduction</span><span class="sxs-lookup"><span data-stu-id="850f4-179">Introduction Page</span></span>  
 <span data-ttu-id="850f4-180">Cette page décrit l’Assistant **déploiement d’une base de données SQL Server sur une machine virtuelle Azure** .</span><span class="sxs-lookup"><span data-stu-id="850f4-180">This page describes the **Deploy a SQL Server Database to an Azure VM** wizard.</span></span>  
  
 <span data-ttu-id="850f4-181">**Options**</span><span class="sxs-lookup"><span data-stu-id="850f4-181">**Options**</span></span>  
  
-   <span data-ttu-id="850f4-182">**Ne plus afficher cette page.**</span><span class="sxs-lookup"><span data-stu-id="850f4-182">**Do not show this page again.**</span></span> <span data-ttu-id="850f4-183">- Cochez cette case pour ne plus afficher la page Introduction à l'avenir.</span><span class="sxs-lookup"><span data-stu-id="850f4-183">- Click this check box to stop the Introduction page from being displayed in the future.</span></span>  
  
-   <span data-ttu-id="850f4-184">**Suivant** – Passe à la page **Paramètres de la source**.</span><span class="sxs-lookup"><span data-stu-id="850f4-184">**Next** - Proceeds to the **Source Settings** page.</span></span>  
  
-   <span data-ttu-id="850f4-185">**Annuler** -annule l’opération et ferme l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="850f4-185">**Cancel** - Cancels the operation and closes the wizard.</span></span>  
  
-   <span data-ttu-id="850f4-186">**Aide** : ouvre la rubrique d’aide MSDN de l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="850f4-186">**Help** - Launches the MSDN Help topic for the wizard.</span></span>  
  
##  <a name="source-settings"></a><a name="Source_settings"></a><span data-ttu-id="850f4-187">Paramètres de la source</span><span class="sxs-lookup"><span data-stu-id="850f4-187">Source Settings</span></span>  
 <span data-ttu-id="850f4-188">Utilisez cette page pour vous connecter à l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui héberge la base de données que vous souhaitez déployer sur la machine virtuelle Azure.</span><span class="sxs-lookup"><span data-stu-id="850f4-188">Use this page to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the database you want to deploy to the Azure VM.</span></span> <span data-ttu-id="850f4-189">Vous allez également spécifier un emplacement temporaire pour les fichiers à enregistrer à partir de l’ordinateur local avant leur transfert vers Azure.</span><span class="sxs-lookup"><span data-stu-id="850f4-189">You will also specify a temporary location for files to be saved from the local machine before they are transferred to Azure.</span></span> <span data-ttu-id="850f4-190">Il peut s'agir d'un emplacement réseau partagé.</span><span class="sxs-lookup"><span data-stu-id="850f4-190">This can be a shared, network location.</span></span>  
  
 <span data-ttu-id="850f4-191">**Options**</span><span class="sxs-lookup"><span data-stu-id="850f4-191">**Options**</span></span>  
  
-   <span data-ttu-id="850f4-192">Cliquez sur **se connecter...** , puis spécifiez les détails de connexion pour l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui héberge la base de données à déployer.</span><span class="sxs-lookup"><span data-stu-id="850f4-192">Click **Connect...** and then specify connection details for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the database to deploy.</span></span>  
  
-   <span data-ttu-id="850f4-193">Utilisez la liste déroulante **Sélectionner une base de données** pour spécifier la base de données à déployer.</span><span class="sxs-lookup"><span data-stu-id="850f4-193">Use the **Select Database** drop-down list to specify the database to deploy.</span></span>  
  
-   <span data-ttu-id="850f4-194">Dans le champ **autres paramètres** , spécifiez un dossier partagé qui sera accessible au service de machine virtuelle Azure.</span><span class="sxs-lookup"><span data-stu-id="850f4-194">In the **Other Settings** field, specify a shared folder that will be accessible to the Azure VM service.</span></span>  
  
##  <a name="azure-sign-in"></a><a name="Azure_sign-in"></a><span data-ttu-id="850f4-195">Connexion à Azure</span><span class="sxs-lookup"><span data-stu-id="850f4-195">Azure Sign-in</span></span>  
 <span data-ttu-id="850f4-196">Utilisez cette page pour vous connecter à Azure et fournir le certificat de gestion ou la publication des détails du profil.</span><span class="sxs-lookup"><span data-stu-id="850f4-196">Use this page to connect to Azure and provide management certificate or publishing profile details.</span></span>  
  
 <span data-ttu-id="850f4-197">**Options**</span><span class="sxs-lookup"><span data-stu-id="850f4-197">**Options**</span></span>  
  
-   <span data-ttu-id="850f4-198">**Certificat de gestion** : utilisez cette option pour spécifier un certificat à partir du magasin de certificats local qui correspond au certificat de gestion d’Azure.</span><span class="sxs-lookup"><span data-stu-id="850f4-198">**Management Certificate** - Use this option to specify a certificate from the local certificate store that matches the management certificate from Azure.</span></span>  
  
-   <span data-ttu-id="850f4-199">**Profil de publication** : utilisez cette option si vous avez déjà téléchargé un profil de publication sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="850f4-199">**Publishing Profile** - Use this option if you already have a publishing profile downloaded to your computer.</span></span>  
  
-   <span data-ttu-id="850f4-200">**Se connecter** -Utilisez cette option pour vous connecter à Azure à l’aide d’un compte Microsoft (par exemple, un compte Live ID ou Hotmail) pour générer et télécharger un nouveau certificat de gestion.</span><span class="sxs-lookup"><span data-stu-id="850f4-200">**Sign In** - Use this option to sign in to Azure using a Microsoft account - for example, a Live ID or Hotmail account - to generate and download a new management certificate.</span></span> <span data-ttu-id="850f4-201">Notez que le nombre de certificats par abonnement est limité.</span><span class="sxs-lookup"><span data-stu-id="850f4-201">Note that the number of certificates per subscription is limited.</span></span>  
  
-   <span data-ttu-id="850f4-202">**Abonnement** : sélectionnez, tapez ou collez votre ID d’abonnement Azure qui correspond au certificat de gestion à partir du magasin de certificats local ou d’un profil de publication.</span><span class="sxs-lookup"><span data-stu-id="850f4-202">**Subscription** - Select, type, or paste your Azure subscription ID that matches the management certificate from the local certificate store or a publishing profile.</span></span>  
  
##  <a name="deployment-settings-page"></a><a name="Deployment_settings"></a><span data-ttu-id="850f4-203">Page Paramètres de déploiement</span><span class="sxs-lookup"><span data-stu-id="850f4-203">Deployment Settings Page</span></span>  
 <span data-ttu-id="850f4-204">Utilisez cette page pour spécifier le serveur de destination et fournir des détails sur votre nouvelle base de données.</span><span class="sxs-lookup"><span data-stu-id="850f4-204">Use this page to specify the destination server and to provide details about your new database.</span></span>  
  
 <span data-ttu-id="850f4-205">**Options**</span><span class="sxs-lookup"><span data-stu-id="850f4-205">**Options**</span></span>  
  
-   <span data-ttu-id="850f4-206">**Machine virtuelle Azure** : spécifiez les détails de la machine virtuelle qui hébergera la base de données SQL Server :</span><span class="sxs-lookup"><span data-stu-id="850f4-206">**Azure Virtual Machine** - Specify details for the VM that will host the SQL Server database:</span></span>  
  
-   <span data-ttu-id="850f4-207">**Nom du service Cloud** : spécifiez le nom du service qui héberge la machine virtuelle.</span><span class="sxs-lookup"><span data-stu-id="850f4-207">**Cloud Service name** - Specify the name of the service that hosts the VM.</span></span> <span data-ttu-id="850f4-208">Pour créer un service de cloud computing, spécifiez un nom.</span><span class="sxs-lookup"><span data-stu-id="850f4-208">To create a new Cloud Service, specify a name for the new Cloud Service.</span></span>  
  
-   <span data-ttu-id="850f4-209">**Nom de la machine virtuelle** : spécifiez le nom de la machine virtuelle qui hébergera la base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="850f4-209">**Virtual Machine name** - Specify the name of the VM that will host the SQL Server database.</span></span> <span data-ttu-id="850f4-210">Pour créer une nouvelle machine virtuelle Azure, spécifiez un nom pour la nouvelle machine virtuelle.</span><span class="sxs-lookup"><span data-stu-id="850f4-210">To create a new Azure VM, specify a name for the new VM.</span></span>  
  
-   <span data-ttu-id="850f4-211">**Paramètres** : utilisez le bouton paramètres pour créer un nouvel ordinateur virtuel pour héberger la base de données de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="850f4-211">**Settings** - Use the Settings button to create a new VM to host the SQL Server database.</span></span> <span data-ttu-id="850f4-212">Si vous utilisez une machine virtuelle existante, les informations spécifiées seront utilisées pour authentifier vos informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="850f4-212">If you are using an existing VM, the information you provide will be used to authenticate your credentials.</span></span>  
  
-   <span data-ttu-id="850f4-213">**Compte de stockage** : sélectionnez le compte de stockage dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="850f4-213">**Storage account** - Select the storage account from the drop-down list.</span></span> <span data-ttu-id="850f4-214">Pour créer un compte de stockage, spécifiez un nom.</span><span class="sxs-lookup"><span data-stu-id="850f4-214">To create a new storage account, specify a name for the new account.</span></span> <span data-ttu-id="850f4-215">Notez que les comptes de stockage associés à un groupe d'affinités ne seront pas disponibles dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="850f4-215">Note that storage accounts associated with an Affinity Group will not be available in the drop-down list.</span></span>  
  
-   <span data-ttu-id="850f4-216">**Base de données cible** : spécifiez les détails de la base de données cible.</span><span class="sxs-lookup"><span data-stu-id="850f4-216">**Target Database** - Specify details for the target database.</span></span>  
  
-   <span data-ttu-id="850f4-217">**Connexion au serveur** : détails de connexion du serveur.</span><span class="sxs-lookup"><span data-stu-id="850f4-217">**Server Connection** - Connection details for the server.</span></span>  
  
-   <span data-ttu-id="850f4-218">**Base de données** : spécifiez ou confirmez le nom d’une nouvelle base de données.</span><span class="sxs-lookup"><span data-stu-id="850f4-218">**Database** - Specify or confirm the name of a new database.</span></span> <span data-ttu-id="850f4-219">Si le nom de la base de données existe déjà sur l'instance SQL Server de destination, modifiez le nom.</span><span class="sxs-lookup"><span data-stu-id="850f4-219">If the database name already exists on the destination SQL Server instance, we suggest that you specify a modified database name.</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="850f4-220">Page Résumé</span><span class="sxs-lookup"><span data-stu-id="850f4-220">Summary Page</span></span>  
 <span data-ttu-id="850f4-221">Utilisez cette page pour passer en revue les paramètres spécifiés pour l'opération.</span><span class="sxs-lookup"><span data-stu-id="850f4-221">Use this page to review the specified settings for the operation.</span></span> <span data-ttu-id="850f4-222">Pour terminer le déploiement à l'aide des paramètres spécifiés, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="850f4-222">To complete the deploy operation using the specified settings, click **Finish**.</span></span> <span data-ttu-id="850f4-223">Pour annuler l’opération de déploiement et quitter l’Assistant, cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="850f4-223">To cancel the deploy operation and exit the wizard, click **Cancel**.</span></span>  
  
 <span data-ttu-id="850f4-224">Des étapes manuelles peuvent être nécessaires pour déployer les détails de la base de données dans la base de données SQL Server sur la machine virtuelle Azure.</span><span class="sxs-lookup"><span data-stu-id="850f4-224">There may be manual steps required to deploy database details to the SQL Server database on the Azure VM.</span></span> <span data-ttu-id="850f4-225">Ces étapes seront décrites de façon détaillée.</span><span class="sxs-lookup"><span data-stu-id="850f4-225">These steps will be outlined in detail for you.</span></span>  
  
##  <a name="results-page"></a><a name="Results"></a><span data-ttu-id="850f4-226">Page résultats</span><span class="sxs-lookup"><span data-stu-id="850f4-226">Results Page</span></span>  
 <span data-ttu-id="850f4-227">Cette page signale la réussite ou l'échec de l'opération de déploiement, affichant les résultats de chaque action.</span><span class="sxs-lookup"><span data-stu-id="850f4-227">This page reports the success or failure of the deploy operation, showing the results of each action.</span></span> <span data-ttu-id="850f4-228">Toute action pour laquelle une erreur s'est produite comportera une indication dans la colonne **Résultat** .</span><span class="sxs-lookup"><span data-stu-id="850f4-228">Any action that encountered an error will have an indication in the **Result** column.</span></span> <span data-ttu-id="850f4-229">Cliquez sur le lien pour consulter le rapport d'erreur de cette action.</span><span class="sxs-lookup"><span data-stu-id="850f4-229">Click the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="850f4-230">Cliquez sur **Terminer** pour fermer l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="850f4-230">Click **Finish** to close the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="850f4-231">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="850f4-231">See Also</span></span>  
 <span data-ttu-id="850f4-232">[adaptateur cloud pour SQL Server](../../database-engine/cloud-adapter-for-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="850f4-232">[Cloud Adapter for SQL Server](../../database-engine/cloud-adapter-for-sql-server.md) </span></span>  
 <span data-ttu-id="850f4-233">[Gestion du cycle de vie des bases de données](../database-lifecycle-management.md) </span><span class="sxs-lookup"><span data-stu-id="850f4-233">[Database Lifecycle Management](../database-lifecycle-management.md) </span></span>  
 <span data-ttu-id="850f4-234">[Exporter une application de la couche données](../data-tier-applications/export-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="850f4-234">[Export a Data-tier Application](../data-tier-applications/export-a-data-tier-application.md) </span></span>  
 <span data-ttu-id="850f4-235">[Importer un fichier baBACPAC pour créer une nouvelle base de données utilisateur](../data-tier-applications/import-a-bacpac-file-to-create-a-new-user-database.md) </span><span class="sxs-lookup"><span data-stu-id="850f4-235">[Import a BACPAC File to Create a New User Database](../data-tier-applications/import-a-bacpac-file-to-create-a-new-user-database.md) </span></span>  
 <span data-ttu-id="850f4-236">[Azure SQL Database la sauvegarde et la restauration](https://msdn.microsoft.com/library/azure/jj650016.aspx) </span><span class="sxs-lookup"><span data-stu-id="850f4-236">[Azure SQL Database Backup and Restore](https://msdn.microsoft.com/library/azure/jj650016.aspx) </span></span>  
 <span data-ttu-id="850f4-237">[Déploiement de SQL Server dans des machines virtuelles Azure](https://msdn.microsoft.com/library/dn133141.aspx) </span><span class="sxs-lookup"><span data-stu-id="850f4-237">[SQL Server Deployment in Azure Virtual Machines](https://msdn.microsoft.com/library/dn133141.aspx) </span></span>  
 [<span data-ttu-id="850f4-238">Préparation à la migration vers SQL Server dans des machines virtuelles Azure</span><span class="sxs-lookup"><span data-stu-id="850f4-238">Getting Ready to Migrate to SQL Server in Azure Virtual Machines</span></span>](https://msdn.microsoft.com/library/dn133142.aspx)  
  
  
