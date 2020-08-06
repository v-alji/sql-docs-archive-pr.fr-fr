---
title: Installer PowerPivot à partir de l’invite de commandes | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 7f1f2b28-c9f5-49ad-934b-02f2fa6b9328
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 54f30142cdc2e39b3ec565d4f965fdad675405e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613780"
---
# <a name="install-powerpivot-from-the-command-prompt"></a><span data-ttu-id="5ee1c-102">Installer PowerPivot à partir de l'invite de commandes</span><span class="sxs-lookup"><span data-stu-id="5ee1c-102">Install PowerPivot from the Command Prompt</span></span>
  <span data-ttu-id="5ee1c-103">Vous pouvez exécuter le programme d'installation depuis la ligne de commande pour installer SQL Server PowerPivot pour SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-103">You can run Setup from the command line to install SQL Server PowerPivot for SharePoint.</span></span> <span data-ttu-id="5ee1c-104">Vous devez inclure le paramètre de `/ROLE` dans votre commande et exclure le paramètre `/FEATURES`.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-104">You must include the `/ROLE` parameter in your command and exclude the `/FEATURES` parameter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5ee1c-105">Prérequis</span><span class="sxs-lookup"><span data-stu-id="5ee1c-105">Prerequisites</span></span>  
 <span data-ttu-id="5ee1c-106">L'édition entreprise SharePoint Server 2010 Enterprise Edition dotée du Service Pack 1 (SP1) doit être installée.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-106">SharePoint Server 2010 enterprise edition with Service Pack 1 (SP1) must be installed.</span></span>  
  
 <span data-ttu-id="5ee1c-107">Vous devez utiliser des comptes de domaine pour configurer Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-107">You must use domain accounts to provision Analysis Services.</span></span>  
  
 <span data-ttu-id="5ee1c-108">L'ordinateur doit être joint au même domaine que la batterie de serveurs SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-108">The computer must be joined to the same domain as the SharePoint farm.</span></span>  
  
##  <a name="role-based-installation-options"></a><a name="Commands"></a><span data-ttu-id="5ee1c-109">Options d’installation basées sur/ROLE</span><span class="sxs-lookup"><span data-stu-id="5ee1c-109">/ROLE based installation options</span></span>  
 <span data-ttu-id="5ee1c-110">Dans les déploiements PowerPivot pour SharePoint, le paramètre `/ROLE` est utilisé à la place du paramètre `/FEATURES`.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-110">For PowerPivot for SharePoint deployments, the `/ROLE` parameter is used in place of the `/FEATURES` parameter.</span></span> <span data-ttu-id="5ee1c-111">Les valeurs valides sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="5ee1c-111">Valid values include:</span></span>  
  
-   `SPI_AS_ExistingFarm`  
  
-   `SPI_AS_NewFarm`  
  
 <span data-ttu-id="5ee1c-112">Ces deux rôles installent les fichiers d'application, de configuration et de déploiement qui permettent à un PowerPivot pour SharePoint de s'exécuter dans une batterie de serveurs SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-112">Both roles install application, configuration, and deployment files that enable a PowerPivot for SharePoint to run in a SharePoint farm.</span></span> <span data-ttu-id="5ee1c-113">La spécification de l'un ou l'autre rôle forcera le programme d'installation à vérifier les configurations matérielle et logicielle requises pour l'intégration SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-113">Specifying either role will cause Setup to check for hardware and software requirements necessary for SharePoint integration.</span></span>  
  
 <span data-ttu-id="5ee1c-114">L'option batterie de serveurs existante suppose qu'une batterie de serveurs SharePoint est déjà en place.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-114">The existing farm option assumes that a SharePoint farm is already in place.</span></span> <span data-ttu-id="5ee1c-115">L’option nouvelle batterie de serveurs part du principe que vous allez créer une batterie de serveurs ; Il prend en charge l’ajout d’une instance de Moteur de base de données dans la syntaxe de la ligne de commande afin que vous puissiez utiliser l’instance Moteur de base de données en tant que serveur de base de données de la batterie de serveurs.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-115">The new farm option assumes that you will create a new farm; it supports the addition of a Database Engine instance in the command line syntax so that you can use the Database Engine instance as the farm's database server.</span></span>  
  
 <span data-ttu-id="5ee1c-116">Contrairement aux versions précédentes, toutes les tâches de configuration du serveur sont effectuées comme après l'installation.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-116">In contrast with the previous releases, all server configuration tasks are performed as post-installation tasks.</span></span> <span data-ttu-id="5ee1c-117">Si vous automatisez les étapes d'installation et de configuration, vous pouvez utiliser PowerShell pour configurer le serveur.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-117">If you are automating installation and configuration steps, you can use PowerShell to configure the server.</span></span> <span data-ttu-id="5ee1c-118">Pour plus d’informations, consultez [configuration de PowerPivot à l’aide de Windows PowerShell](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-configuration-using-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="5ee1c-118">For more information, see [PowerPivot Configuration using Windows PowerShell](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-configuration-using-windows-powershell).</span></span>  
  
## <a name="example-commands"></a><span data-ttu-id="5ee1c-119">Exemple de commandes</span><span class="sxs-lookup"><span data-stu-id="5ee1c-119">Example Commands</span></span>  
 <span data-ttu-id="5ee1c-120">Les exemples suivants illustrent l'utilisation de chaque option.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-120">The following examples illustrate the usage of each option.</span></span> <span data-ttu-id="5ee1c-121">Le premier exemple montre `SPI_AS_ExistingFarm`.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-121">Example 1 shows `SPI_AS_ExistingFarm`.</span></span>  
  
```cmd
Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /ROLE=SPI_AS_ExistingFarm /INSTANCENAME=PowerPivot /INDICATEPROGRESS/ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
```  
  
 <span data-ttu-id="5ee1c-122">Le deuxième exemple montre `SPI_AS_NewFarm`.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-122">Example 2 shows `SPI_AS_NewFarm`.</span></span> <span data-ttu-id="5ee1c-123">Notez qu'il inclut des paramètres de configuration du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-123">Notice that it includes parameters for provisioning the Database Engine.</span></span>  
  
```cmd
Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /ROLE=SPI_AS_NewFarm /INSTANCENAME=PowerPivot /INDICATEPROGRESS/SQLSVCACCOUNT=<DomainName\UserName> /SQLSVCPASSWORD=<StrongPassword> /SQLSYSADMINACCOUNTS=<DomainName\UserName> /AGTSVCACCOUNT=<DomainName\UserName> /AGTSVCPASSWORD=<StrongPassword> /ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
```  
  
##  <a name="modifying-the-command-syntax"></a><a name="Join"></a><span data-ttu-id="5ee1c-124">Modification de la syntaxe de la commande</span><span class="sxs-lookup"><span data-stu-id="5ee1c-124">Modifying the command syntax</span></span>  
 <span data-ttu-id="5ee1c-125">Utilisez la procédure suivante pour modifier la syntaxe de commande de l'exemple.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-125">Use the following steps to modify the example command syntax.</span></span>  
  
1.  <span data-ttu-id="5ee1c-126">Copiez la commande suivante dans le Bloc-notes :</span><span class="sxs-lookup"><span data-stu-id="5ee1c-126">Copy the following command into Notepad:</span></span>  
  
    ```cmd
    Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /ROLE=SPI_AS_ExistingFarm /INSTANCENAME=PowerPivot /INDICATEPROGRESS/ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
    ```  
  
     <span data-ttu-id="5ee1c-127">Le paramètre `/q` exécute le programme d'installation en mode silencieux, ce qui supprime l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-127">The `/q` parameter runs Setup in quiet mode, which suppresses the user interface.</span></span>  
  
     <span data-ttu-id="5ee1c-128">Le paramètre `/IAcceptSQLServerLicenseTerms` est indispensable lorsque le paramètre `/q` ou `/qs` est spécifié pour les installations sans assistance.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-128">The `/IAcceptSQLServerLicenseTerms` is required when the `/q` or `/qs` parameter is specified for un-attended installations.</span></span>  
  
     <span data-ttu-id="5ee1c-129">Le paramètre `/action` indique au programme d'installation d'effectuer une installation.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-129">The `/action` parameter instructs Setup to perform an installation.</span></span>  
  
     <span data-ttu-id="5ee1c-130">Le paramètre `/role` indique au programme d'installation d'installer le programme et les fichiers de configuration Analysis Services nécessaires pour PowerPivot for SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-130">The `/role` parameter instructs Setup to install the Analysis Services program and configuration files required for PowerPivot for SharePoint.</span></span> <span data-ttu-id="5ee1c-131">Ce rôle détecte et utilise également les informations de connectivité de la batterie existante pour accéder à la base de données de configuration SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-131">This role also detects and uses the existing farm connectivity information to access the SharePoint configuration database.</span></span> <span data-ttu-id="5ee1c-132">Ce paramètre est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-132">This parameter is required.</span></span> <span data-ttu-id="5ee1c-133">Utilisez-le à la place du paramètre `/features` pour spécifier les composants à installer.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-133">Use it instead of the `/features` parameter to specify the components to install.</span></span>  
  
     <span data-ttu-id="5ee1c-134">Le paramètre `/instancename` spécifie 'PowerPivot' comme une instance nommée.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-134">The `/instancename` parameter specifies 'PowerPivot' as a named instance.</span></span> <span data-ttu-id="5ee1c-135">Cette valeur est codée en dur et ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-135">This value is hard-coded and cannot be changed.</span></span> <span data-ttu-id="5ee1c-136">Elle est spécifiée dans la commande à titre éducatif, pour que vous sachiez comment le service est installé.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-136">It is specified in the command for educational purposes so that you know how the service is installed.</span></span>  
  
     <span data-ttu-id="5ee1c-137">Le paramètre `/indicateprogress` vous permet de surveiller la progression dans la fenêtre d'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-137">The `/indicateprogress` parameter allows you to monitor progress in the command prompt window.</span></span>  
  
2.  <span data-ttu-id="5ee1c-138">Le paramètre `PID` est omis de la commande, ce qui entraîne l'installation d'Evaluation edition.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-138">The `PID` parameter is omitted from the command, which causes the Evaluation edition to be installed.</span></span> <span data-ttu-id="5ee1c-139">Si vous souhaitez installer Enterprise Edition, ajoutez le paramètre PID à votre commande d'installation et fournissez une clé de produit valide.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-139">If you want to install the Enterprise edition, add the PID to your Setup command and provide a valid product key.</span></span>  
  
    ```  
    /PID=<product key for an Enterprise installation>  
    ```  
  
3.  <span data-ttu-id="5ee1c-140">Remplacez les espaces réservés pour \<domain\username> et \<StrongPassword> par des comptes d’utilisateur et des mots de passe valides.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-140">Replace the placeholders for \<domain\username> and \<StrongPassword>with valid user accounts and passwords.</span></span>  
  
     <span data-ttu-id="5ee1c-141">Les `/assvaccount` paramètres et **/ASSVCPASSWORD** sont utilisés pour configurer l' [!INCLUDE[ssGeminiSrv](../../includes/ssgeminisrv-md.md)] instance sur le serveur d’applications.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-141">The `/assvaccount` and **/assvcpassword** parameters are used to configure the [!INCLUDE[ssGeminiSrv](../../includes/ssgeminisrv-md.md)] instance on the application server.</span></span> <span data-ttu-id="5ee1c-142">Remplacez ces espaces réservés par des informations de compte valides.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-142">Replace these placeholders with valid account information.</span></span>  
  
     <span data-ttu-id="5ee1c-143">Le paramètre **/ASSYSADMINACCOUNTS** doit être défini sur l’identité de l’utilisateur qui exécute SQL Server installation.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-143">The **/assysadminaccounts** parameter must be set to the identity of the user who is running SQL Server Setup.</span></span> <span data-ttu-id="5ee1c-144">Vous devez spécifier au moins un administrateur système.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-144">You must specify at least one system administrator.</span></span> <span data-ttu-id="5ee1c-145">Notez que le programme d'installation de SQL Server n'accorde plus d'autorisations sysadmin automatiques aux membres du groupe intégré Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-145">Note that SQL Server Setup no long grants automatic sysadmin permissions to members of the built-in Administrators group.</span></span>  
  
4.  <span data-ttu-id="5ee1c-146">Supprimez les sauts de ligne.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-146">Remove line breaks.</span></span>  
  
5.  <span data-ttu-id="5ee1c-147">Sélectionnez l’intégralité de la commande, puis cliquez sur **copier** dans le menu Edition.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-147">Select the entire command and then click **Copy** on the Edit menu.</span></span>  
  
6.  <span data-ttu-id="5ee1c-148">Ouvrez une invite de commandes d'administrateur.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-148">Open an administrator command prompt.</span></span> <span data-ttu-id="5ee1c-149">Pour ce faire, cliquez sur **Démarrer**, cliquez avec le bouton droit sur l’invite de commandes, puis sélectionnez **exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-149">To do this, click **Start**, right-click the command prompt, and select **Run as administrator**.</span></span>  
  
7.  <span data-ttu-id="5ee1c-150">Accédez au lecteur ou au dossier partagé qui contient le support d'installation de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-150">Navigate to the drive or shared folder that contains the SQL Server installation media.</span></span>  
  
8.  <span data-ttu-id="5ee1c-151">Collez la commande modifiée dans la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-151">Paste the revised command into the command line.</span></span> <span data-ttu-id="5ee1c-152">Pour ce faire, cliquez sur l’icône dans le coin supérieur gauche de la fenêtre d’invite de commandes, pointez sur **modifier**, puis cliquez sur **coller**.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-152">To do this, click the icon in the top left corner of the command prompt window, point to **Edit**, and then click **Paste**.</span></span>  
  
9. <span data-ttu-id="5ee1c-153">Appuyez sur **entrée** pour exécuter la commande.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-153">Press **Enter** to run the command.</span></span> <span data-ttu-id="5ee1c-154">Attendez que l'installation soit terminée.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-154">Wait for setup to complete.</span></span> <span data-ttu-id="5ee1c-155">Vous pouvez surveiller la progression de l'installation dans la fenêtre d'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-155">You can monitor Setup's progress in the command prompt window.</span></span>  
  
10. <span data-ttu-id="5ee1c-156">Pour vérifier l'installation, vérifiez le fichier summary.txt dans \Program Files\SQL Server\120\Setup Bootstrap\Log.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-156">To verify installation, check the summary.txt file at \Program Files\SQL Server\120\Setup Bootstrap\Log.</span></span> <span data-ttu-id="5ee1c-157">Le résultat final doit indiquer « Réussite » si le serveur a été installé sans erreurs.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-157">Final result should say "Passed" if the server installed without errors.</span></span>  
  
11. <span data-ttu-id="5ee1c-158">Configurez le serveur.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-158">Configure the server.</span></span> <span data-ttu-id="5ee1c-159">Vous devez au minimum déployer des solution, créer une application de service et activer la fonction pour chaque collection de sites.</span><span class="sxs-lookup"><span data-stu-id="5ee1c-159">At a minimum, you must deploy solutions, create a service application, and enable the feature for each site collection.</span></span> <span data-ttu-id="5ee1c-160">Pour plus d’informations, consultez [configurer ou réparer PowerPivot pour SharePoint 2010 &#40;outil de configuration powerpivot&#41;](../../../2014/analysis-services/configure-repair-powerpivot-sharepoint-2010.md) ou [administration et configuration du serveur PowerPivot dans l’administration centrale](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-server-administration-and-configuration-in-central-administration).</span><span class="sxs-lookup"><span data-stu-id="5ee1c-160">For more information, see [Configure or Repair PowerPivot for SharePoint 2010 &#40;PowerPivot Configuration Tool&#41;](../../../2014/analysis-services/configure-repair-powerpivot-sharepoint-2010.md) or [PowerPivot Server Administration and Configuration in Central Administration](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-server-administration-and-configuration-in-central-administration).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ee1c-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5ee1c-161">See Also</span></span>  
 <span data-ttu-id="5ee1c-162">[Configurer des comptes de service PowerPivot](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/configure-power-pivot-service-accounts) </span><span class="sxs-lookup"><span data-stu-id="5ee1c-162">[Configure PowerPivot Service Accounts](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/configure-power-pivot-service-accounts) </span></span>  
 [<span data-ttu-id="5ee1c-163">PowerPivot for SharePoint 2010 Installation</span><span class="sxs-lookup"><span data-stu-id="5ee1c-163">PowerPivot for SharePoint 2010 Installation</span></span>](../../../2014/sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
