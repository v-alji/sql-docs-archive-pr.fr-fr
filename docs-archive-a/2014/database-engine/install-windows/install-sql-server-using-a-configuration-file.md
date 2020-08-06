---
title: Installer SQL Server 2014 à l’aide d’un fichier de configuration | Microsoft Docs
ms.custom: ''
ms.date: 01/20/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: a832153a-6775-4bed-83f0-55790766d885
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a2f09ad6253762fe5b525f6c918931f4806c84c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697116"
---
# <a name="install-sql-server-2014-using-a-configuration-file"></a><span data-ttu-id="265a1-102">Installer SQL Server 2014 à l'aide d'un fichier de configuration</span><span class="sxs-lookup"><span data-stu-id="265a1-102">Install SQL Server 2014 Using a Configuration File</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="265a1-103">Le programme d’installation permet de générer un fichier de configuration basé sur les entrées système par défaut et celles effectuées au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="265a1-103">Setup provides the ability to generate a configuration file based upon the system default and run-time inputs.</span></span> <span data-ttu-id="265a1-104">Vous pouvez utiliser le fichier de configuration pour déployer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans la totalité de l'entreprise avec la même configuration.</span><span class="sxs-lookup"><span data-stu-id="265a1-104">You can use the configuration file to deploy [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] throughout the enterprise with the same configuration.</span></span> <span data-ttu-id="265a1-105">Vous pouvez également standardiser les installations manuelles dans l'ensemble de l'entreprise, en créant un fichier de commandes qui lance Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="265a1-105">You can also standardize manual installations throughout the enterprise, by creating a batch file that launches Setup.exe.</span></span>  
  
 <span data-ttu-id="265a1-106">Le programme d'installation prend en charge l'utilisation du fichier de configuration uniquement via l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="265a1-106">Setup supports the use of the configuration file only through the command prompt.</span></span> <span data-ttu-id="265a1-107">L'ordre de traitement des paramètres lors de l'utilisation du fichier de configuration est décrit ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="265a1-107">The processing order of the parameters while using the configuration file is outlined below:</span></span>  
  
-   <span data-ttu-id="265a1-108">Le fichier de configuration remplace les valeurs par défaut d'un package.</span><span class="sxs-lookup"><span data-stu-id="265a1-108">The configuration file overwrites the defaults in a package</span></span>  
  
-   <span data-ttu-id="265a1-109">Les valeurs de la ligne de commande remplacent les valeurs du fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="265a1-109">Command-line values overwrite the values in the configuration file</span></span>  
  
 <span data-ttu-id="265a1-110">Le fichier de configuration permet d'assurer le suivi des paramètres et des valeurs de chaque installation.</span><span class="sxs-lookup"><span data-stu-id="265a1-110">The configuration file can be used to track the parameters and values for each installation.</span></span> <span data-ttu-id="265a1-111">Cela le rend très utile pour vérifier et auditer des installations.</span><span class="sxs-lookup"><span data-stu-id="265a1-111">This makes the configuration file useful for verifying and auditing the installations.</span></span>  
  
## <a name="configuration-file-structure"></a><span data-ttu-id="265a1-112">Structure de fichier de configuration</span><span class="sxs-lookup"><span data-stu-id="265a1-112">Configuration File Structure</span></span>  
 <span data-ttu-id="265a1-113">Le fichier ConfigurationFile.ini est un fichier texte avec des paramètres (paire nom/valeur) et des commentaires descriptifs.</span><span class="sxs-lookup"><span data-stu-id="265a1-113">The ConfigurationFile.ini file is a text file with parameters (name/value pair) and descriptive comments.</span></span>  
  
 <span data-ttu-id="265a1-114">Voici un exemple de fichier ConfigurationFile.ini :</span><span class="sxs-lookup"><span data-stu-id="265a1-114">The following is an example of a ConfigurationFile.ini file:</span></span>  
  
```  
; Microsoft SQL Server Configuration file  
[OPTIONS]  
; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE.   
; This is a required parameter.   
ACTION="Install"  
; Specifies features to install, uninstall, or upgrade.   
; The list of top-level features include SQL, AS, RS, IS, and Tools.   
; The SQL feature will install the database engine, replication, and full-text.   
; The Tools feature will install Management Tools, Books online,   
; SQL Server Data Tools, and other shared components.   
FEATURES=SQL,Tools  
```  
  
#### <a name="how-to-generate-a-configuration-file"></a><span data-ttu-id="265a1-115">Comment générer un fichier de configuration</span><span class="sxs-lookup"><span data-stu-id="265a1-115">How to generate a configuration file</span></span>  
  
1.  <span data-ttu-id="265a1-116">Insérez le support d'installation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="265a1-116">Insert the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation media.</span></span> <span data-ttu-id="265a1-117">Dans le dossier racine, double-cliquez sur Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="265a1-117">From the root folder, double-click Setup.exe.</span></span> <span data-ttu-id="265a1-118">Pour effectuer l'installation à partir d'un partage réseau, recherchez le dossier racine sur le partage, puis double-cliquez sur Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="265a1-118">To install from a network share, locate the root folder on the share, and then double-click Setup.exe.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="265a1-119">Express Edition ne crée pas de fichier de configuration automatiquement.</span><span class="sxs-lookup"><span data-stu-id="265a1-119">Express Edition setup does not create a configuration file automatically.</span></span> <span data-ttu-id="265a1-120">La commande suivante démarre l’installation et crée un fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="265a1-120">The following command will start  setup and create a configuration file.</span></span>  
    >   
    >  <span data-ttu-id="265a1-121">SETUP.exe /UIMODE=Normal /ACTION=INSTALL</span><span class="sxs-lookup"><span data-stu-id="265a1-121">SETUP.exe /UIMODE=Normal /ACTION=INSTALL</span></span>  
  
2.  <span data-ttu-id="265a1-122">Suivez le déroulement des étapes de l'Assistant jusqu'à la page **Prêt pour l'installation** .</span><span class="sxs-lookup"><span data-stu-id="265a1-122">Follow the wizard through to the **Ready to Install** page.</span></span> <span data-ttu-id="265a1-123">Le chemin d'accès au fichier de configuration est spécifié dans la page **Prêt pour l'installation** , dans la section relative au chemin d'accès du fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="265a1-123">The path to the configuration file is specified in the **Ready to Install** page in the configuration file path section.</span></span> <span data-ttu-id="265a1-124">Pour plus d’informations sur l’installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consultez [installer SQL Server 2014 à partir de l’assistant installation &#40;&#41;d' ](install-sql-server-from-the-installation-wizard-setup.md)installation.</span><span class="sxs-lookup"><span data-stu-id="265a1-124">For more information about how to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](install-sql-server-from-the-installation-wizard-setup.md).</span></span>  
  
3.  <span data-ttu-id="265a1-125">Annulez l'exécution du programme d'installation sans réellement terminer l'installation afin de générer le fichier INI.</span><span class="sxs-lookup"><span data-stu-id="265a1-125">Cancel the setup without actually completing the installation, to generate the INI file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="265a1-126">L'infrastructure d'installation écrit tous les paramètres appropriés pour les actions exécutées, à l'exception des informations sensibles comme les mots de passe.</span><span class="sxs-lookup"><span data-stu-id="265a1-126">The setup infrastructure writes out all the appropriate parameters for the actions that were run, with the exception of sensitive information such as passwords.</span></span> <span data-ttu-id="265a1-127">Le paramètre /IAcceptSQLServerLicenseTerms n'est pas écrit dans le fichier de configuration et requiert soit une modification du fichier de configuration, soit une valeur à fournir à l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="265a1-127">The /IAcceptSQLServerLicenseTerms parameter is also not written out to the configuration file and requires either a modification of the configuration file or a value to be supplied at the command prompt.</span></span> <span data-ttu-id="265a1-128">Pour plus d’informations, consultez [Installer SQL Server 2014 à partir de l’invite de commandes](install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="265a1-128">For more information, see [Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md).</span></span> <span data-ttu-id="265a1-129">De plus, une valeur est incluse pour les paramètres booléens pour lesquels une valeur n'est généralement pas fournie via l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="265a1-129">In addition, a value is included for Boolean parameters where a value is usually not supplied through the command prompt.</span></span>  
  
## <a name="using-the-configuration-file-to-install-ssnoversion"></a><span data-ttu-id="265a1-130">Utilisation du fichier de configuration pour installer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="265a1-130">Using the Configuration File to Install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
 <span data-ttu-id="265a1-131">Vous ne pouvez utiliser le fichier de configuration que pour les installations en ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="265a1-131">You can only use the configuration file on command-line installations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="265a1-132">Si vous devez apporter des modifications au fichier de configuration, nous vous recommandons de faire une copie de ce dernier et de l''utiliser.</span><span class="sxs-lookup"><span data-stu-id="265a1-132">If you need to make changes to the configuration file, we recommend that you make a copy and work with the copy.</span></span>  
  
#### <a name="how-to-use-a-configuration-file-to-install-a-stand-alone-ssnoversion-instance"></a><span data-ttu-id="265a1-133">Comment utiliser un fichier de configuration pour installer une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] autonome</span><span class="sxs-lookup"><span data-stu-id="265a1-133">How to use a configuration file to install a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance</span></span>  
  
-   <span data-ttu-id="265a1-134">Exécutez l'installation à partir de l'invite de commandes et spécifiez le fichier ConfigurationFile.ini à l'aide du paramètre *ConfigurationFile* .</span><span class="sxs-lookup"><span data-stu-id="265a1-134">Run the installation through the command prompt and supply the ConfigurationFile.ini using the *ConfigurationFile* parameter.</span></span>  
  
#### <a name="how-to-use-a-configuration-file-to-prepare-and-complete-an-image-of-a-stand-alone-ssnoversion-instance-sysprep"></a><span data-ttu-id="265a1-135">Procédure d'utilisation d'un fichier de configuration afin de préparer et finaliser une image d'une instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] autonome (SysPrep)</span><span class="sxs-lookup"><span data-stu-id="265a1-135">How to use a configuration file to prepare and complete an image of a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (SysPrep)</span></span>  
  
1.  <span data-ttu-id="265a1-136">Pour préparer une ou plusieurs instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et les configurer sur le même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="265a1-136">To prepare one or more instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and configure them on the same machine.</span></span>  
  
    -   <span data-ttu-id="265a1-137">Exécutez **Préparation de l’image d’une instance autonome de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** dans la page **Avancé** du Centre d’installation et capturez le fichier de configuration de préparation d’image.</span><span class="sxs-lookup"><span data-stu-id="265a1-137">Run **Image preparation of a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the **Advanced** page of the Installation Center and capture the prepare image configuration file.</span></span>  
  
    -   <span data-ttu-id="265a1-138">Utilisez le même fichier de configuration de préparation d'image comme modèle pour préparer d'autres instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="265a1-138">Use the same prepare image configuration file as a template to prepare more instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="265a1-139">Exécutez **Finalisation d’image d’une instance autonome préparée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** dans la page **Avancé** du Centre d’installation pour configurer une instance préparée sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="265a1-139">Run **Image completion of a prepared stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the **Advanced** page of the Installation Center to configure a prepared instances on the machine.</span></span>  
  
2.  <span data-ttu-id="265a1-140">Pour préparer une image du système d'exploitation, notamment une instance préparée non configurée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], à l'aide de l'outil SysPrep de Windows.</span><span class="sxs-lookup"><span data-stu-id="265a1-140">To prepare an image of the operating system including an unconfigured prepared instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], using Windows SysPrep tool.</span></span>  
  
    -   <span data-ttu-id="265a1-141">Exécutez **Préparation de l’image d’une instance autonome de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** dans la page Avancé du Centre d’installation et capturez le fichier de configuration de préparation d’image.</span><span class="sxs-lookup"><span data-stu-id="265a1-141">Run the **Image preparation of a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the Advanced page of the Installation Center and capture the prepare image configuration file.</span></span>  
  
    -   <span data-ttu-id="265a1-142">Exécutez **Finalisation d’image d’une instance autonome préparée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** dans la page **Avancé** du Centre d’installation, mais annulez cette opération dans la page **Prêt à finaliser l’image** après avoir capturé le fichier de configuration complet.</span><span class="sxs-lookup"><span data-stu-id="265a1-142">Run the **Image completion of a prepared stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the **Advanced** page of the Installation Center, but cancel it on the **Ready to Complete** page after capturing the complete configuration file.</span></span>  
  
    -   <span data-ttu-id="265a1-143">Le fichier de configuration de finalisation d'image peut être stocké avec l'image Windows pour l'automatisation de la configuration des instances préparées.</span><span class="sxs-lookup"><span data-stu-id="265a1-143">The complete image configuration file can be stored with the Windows image for automating the configuration of the prepared instances.</span></span>  
  
#### <a name="how-to-install-a-ssnoversion-failover-cluster-using-the-configuration-file"></a><span data-ttu-id="265a1-144">Procédure d'installation d'un cluster de basculement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide du fichier de configuration</span><span class="sxs-lookup"><span data-stu-id="265a1-144">How to install a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster using the configuration file</span></span>  
  
1.  <span data-ttu-id="265a1-145">Option d'installation intégrée (créez un cluster de basculement à nœud unique sur un nœud et exécutez AddNode sur les nœuds supplémentaires) :</span><span class="sxs-lookup"><span data-stu-id="265a1-145">Integrated Install option (create a single node failover cluster on a node and for additional nodes, run AddNode on them):</span></span>  
  
    -   <span data-ttu-id="265a1-146">Effectuez l'installation d'un cluster de basculement et capturez le fichier de configuration qui répertorie tous les paramètres d'installation.</span><span class="sxs-lookup"><span data-stu-id="265a1-146">Run the "Install a Failover Cluster" option and capture the configuration file that lists all the installation settings.</span></span>  
  
    -   <span data-ttu-id="265a1-147">Effectuez l’installation du cluster de basculement à partir de la ligne de commande en spécifiant le paramètre *ConfigurationFile* .</span><span class="sxs-lookup"><span data-stu-id="265a1-147">Run the command-line failover cluster install by supplying the *ConfigurationFile* parameter.</span></span>  
  
    -   <span data-ttu-id="265a1-148">Sur un nœud supplémentaire destiné à être ajouté, exécutez AddNode afin de capturer le fichier ConfigurationFile.ini applicable au cluster de basculement existant.</span><span class="sxs-lookup"><span data-stu-id="265a1-148">On an additional node to be added, run AddNode to capture the ConfigurationFile.ini file applicable to the existing failover cluster.</span></span>  
  
    -   <span data-ttu-id="265a1-149">Exécutez AddNode à partir de la ligne de commande sur tous les nœuds supplémentaires destinés à joindre le cluster de basculement, en spécifiant le même fichier de configuration à l'aide du paramètre ConfigurationFile.</span><span class="sxs-lookup"><span data-stu-id="265a1-149">Run the command-line AddNode on all the additional nodes that will join the failover cluster, by supplying the same configuration file using the ConfigurationFile parameter.</span></span>  
  
2.  <span data-ttu-id="265a1-150">Option d'installation avancée (préparez le cluster de basculement sur tous les nœuds de cluster de basculement, puis, après avoir préparé tous les nœuds, exécutez l'opération de création sur le nœud propriétaire du disque partagé) :</span><span class="sxs-lookup"><span data-stu-id="265a1-150">Advanced install option (prepare failover cluster on all failover cluster nodes, then, after preparing all the nodes, run complete on the node that owns the shared disk):</span></span>  
  
    -   <span data-ttu-id="265a1-151">Exécutez **Prepare** sur l'un des nœuds et capturez le fichier ConfigurationFile.ini.</span><span class="sxs-lookup"><span data-stu-id="265a1-151">Run **Prepare** on one of the nodes, and capture the ConfigurationFile.ini file.</span></span>  
  
    -   <span data-ttu-id="265a1-152">Indiquez le même fichier ConfigurationFile.ini au programme d'installation sur tous les nœuds à préparer pour le cluster de basculement.</span><span class="sxs-lookup"><span data-stu-id="265a1-152">Supply the same ConfigurationFile.ini file to Setup on all the nodes that will be prepared for the failover cluster.</span></span>  
  
    -   <span data-ttu-id="265a1-153">Après avoir préparé tous les nœuds, exécutez une opération de création du cluster de basculement sur le nœud propriétaire du disque partagé et capturez le fichier ConfigurationFile.ini.</span><span class="sxs-lookup"><span data-stu-id="265a1-153">After all the nodes have been prepared, run a complete failover cluster operation on the node that owns the shared disk and capture the ConfigurationFile.ini file.</span></span>  
  
    -   <span data-ttu-id="265a1-154">Vous pouvez ensuite spécifier ce fichier ConfigurationFile.ini pour créer le cluster de basculement.</span><span class="sxs-lookup"><span data-stu-id="265a1-154">You can then supply this ConfigurationFile.ini file to complete the failover cluster.</span></span>  
  
#### <a name="how-to-add-or-remove-a-node-to-a-ssnoversion-failover-cluster-using-the-configuration-file"></a><span data-ttu-id="265a1-155">Comment ajouter ou supprimer un nœud dans un cluster de basculement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide du fichier de configuration</span><span class="sxs-lookup"><span data-stu-id="265a1-155">How to add or remove a node to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster using the configuration file</span></span>  
  
-   <span data-ttu-id="265a1-156">Si vous disposez d'un fichier de configuration qui a été précédemment utilisé pour ajouter ou supprimer un nœud dans un cluster de basculement, vous pouvez réutiliser ce même fichier pour ajouter ou supprimer des nœuds supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="265a1-156">If you have a configuration file that was previously used to add a node to or remove a node from a failover cluster, you can reuse that same file to add or remove additional nodes.</span></span>  
  
#### <a name="how-to-upgrade-a-ssnoversion-failover-cluster-using-the-configuration-file"></a><span data-ttu-id="265a1-157">Comment mettre à niveau un cluster de basculement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide du fichier de configuration</span><span class="sxs-lookup"><span data-stu-id="265a1-157">How to upgrade a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster using the configuration file</span></span>  
  
1.  <span data-ttu-id="265a1-158">Exécutez la mise à niveau sur le nœud passif et capturez le fichier ConfigurationFile.ini.</span><span class="sxs-lookup"><span data-stu-id="265a1-158">Run upgrade on the passive node and capture the ConfigurationFile.ini file.</span></span> <span data-ttu-id="265a1-159">Pour ce faire, vous pouvez effectuer la mise à niveau réelle ou sortir à la fin du processus sans effectuer la mise à niveau réelle.</span><span class="sxs-lookup"><span data-stu-id="265a1-159">You can do this either by performing the actual upgrade, or exiting at the end without doing the actual upgrade.</span></span>  
  
2.  <span data-ttu-id="265a1-160">Sur tous les nœuds supplémentaires à mettre à niveau, spécifiez le fichier ConfigurationFile.ini pour exécuter le processus.</span><span class="sxs-lookup"><span data-stu-id="265a1-160">On all the additional nodes to be upgraded, supply the ConfigurationFile.ini file to complete the process.</span></span>  
  
## <a name="sample-syntax"></a><span data-ttu-id="265a1-161">Exemple de syntaxe</span><span class="sxs-lookup"><span data-stu-id="265a1-161">Sample Syntax</span></span>  
 <span data-ttu-id="265a1-162">Voici quelques exemples qui illustrent l'utilisation du fichier de configuration :</span><span class="sxs-lookup"><span data-stu-id="265a1-162">Following are some examples on how to use the configuration file:</span></span>  
  
-   <span data-ttu-id="265a1-163">Pour spécifier le fichier de configuration à l'invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="265a1-163">To specify the configuration file at the command prompt:</span></span>  
  
```  
Setup.exe /ConfigurationFile=MyConfigurationFile.INI  
```  
  
-   <span data-ttu-id="265a1-164">Pour spécifier des mots de passe à l'invite de commandes plutôt que dans le fichier de configuration :</span><span class="sxs-lookup"><span data-stu-id="265a1-164">To specify passwords at the command prompt instead of in the configuration file:</span></span>  
  
```  
Setup.exe /SQLSVCPASSWORD="************" /AGTSVCPASSWORD="************" /ASSVCPASSWORD="************" /ISSVCPASSWORD="************" /RSSVCPASSWORD="************" /ConfigurationFile=MyConfigurationFile.INI  
```  
  
## <a name="see-also"></a><span data-ttu-id="265a1-165">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="265a1-165">See Also</span></span>  
 <span data-ttu-id="265a1-166">[Installer SQL Server 2014 à partir de l’invite de commandes](install-sql-server-from-the-command-prompt.md) </span><span class="sxs-lookup"><span data-stu-id="265a1-166">[Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md) </span></span>  
 <span data-ttu-id="265a1-167">[Installation d’un cluster de basculement SQL Server](../../sql-server/failover-clusters/install/sql-server-failover-cluster-installation.md) </span><span class="sxs-lookup"><span data-stu-id="265a1-167">[SQL Server Failover Cluster Installation](../../sql-server/failover-clusters/install/sql-server-failover-cluster-installation.md) </span></span>  
 [<span data-ttu-id="265a1-168">Mettre à niveau un cluster de basculement SQL Server</span><span class="sxs-lookup"><span data-stu-id="265a1-168">Upgrade a SQL Server Failover Cluster</span></span>](../../sql-server/failover-clusters/windows/upgrade-a-sql-server-failover-cluster-instance.md)  
  
  
