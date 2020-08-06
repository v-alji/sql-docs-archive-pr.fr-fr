---
title: Mettre en service les abonnements et les alertes pour les applications de service SSRS | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services Shared Service
- SharePoint Mode [Reporting Services]
- SharePoint Mode
- Reporting Services Service Application
- SSRS service application
ms.assetid: d0de3f1f-4887-47fb-bacf-46aaad74c4be
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9c09033b6a31295b8fbe42058cba9059f5d05629
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710300"
---
# <a name="provision-subscriptions-and-alerts-for-ssrs-service-applications"></a><span data-ttu-id="5bd89-102">Configurer les abonnements et les alertes pour les applications de service de SSRS</span><span class="sxs-lookup"><span data-stu-id="5bd89-102">Provision Subscriptions and Alerts for SSRS Service Applications</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="5bd89-103">Les abonnements et les alertes de données nécessitent SQL Server Agent et peuvent exiger la configuration des autorisations de SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="5bd89-103">subscriptions and data alerts require SQL Server Agent and require the configuration of permissions for SQL Server Agent.</span></span> <span data-ttu-id="5bd89-104">Si des messages d'erreur apparaissent indiquant que SQL Server Agent est obligatoire et que vous avez vérifié le fonctionnement de SQL Server Agent, alors vous devez mettre à jour ou vérifier les autorisations.</span><span class="sxs-lookup"><span data-stu-id="5bd89-104">If you see error messages that indicate SQL Server Agent is required and you have verified SQL Server Agent is running, then update or verify permissions.</span></span> <span data-ttu-id="5bd89-105">Cette rubrique traite de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en mode SharePoint et décrit trois méthodes pour mettre à jour les autorisations de SQL Server Agent avec les abonnements [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5bd89-105">The scope of this topic is [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode and the topic describes three ways you can update the permissions of SQL Server Agent with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] subscriptions.</span></span> <span data-ttu-id="5bd89-106">Les informations d'identification que vous utilisez pour les étapes de cette rubrique doivent disposer d'autorisations suffisantes pour accorder des autorisations EXECUTE au rôle RSExecRole pour les objets dans les bases de données de l'application de service, msdb et master.</span><span class="sxs-lookup"><span data-stu-id="5bd89-106">The credentials you use for the steps in this topic need to have sufficient permissions to grant execute permissions to the RSExecRole for objects in the service application, msdb, and master databases.</span></span>

||
|-|
|<span data-ttu-id="5bd89-107">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2013 &#124; SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="5bd89-107">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2013 &#124; SharePoint 2010</span></span>|

 <span data-ttu-id="5bd89-108">![Autorisations d'accès SQL Agent aux bases de données d'application de service](../../../2014/sql-server/install/media/rs-provisionsqlagent.gif "Autorisations d'accès SQL Agent aux bases de données d'application de service")</span><span class="sxs-lookup"><span data-stu-id="5bd89-108">![SQL Agent permissions to Service Application DBs](../../../2014/sql-server/install/media/rs-provisionsqlagent.gif "SQL Agent permissions to Service Application DBs")</span></span>

||<span data-ttu-id="5bd89-109">Description</span><span class="sxs-lookup"><span data-stu-id="5bd89-109">Description</span></span>|
|------|-----------------|
|<span data-ttu-id="5bd89-110">**1**</span><span class="sxs-lookup"><span data-stu-id="5bd89-110">**1**</span></span>|<span data-ttu-id="5bd89-111">Instance du moteur de base de données SQL Server qui héberge les bases de données d'application de service Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="5bd89-111">The instance of SQL Server Database engine that is hosting the Reporting Services service application databases.</span></span>|
|<span data-ttu-id="5bd89-112">**2**</span><span class="sxs-lookup"><span data-stu-id="5bd89-112">**2**</span></span>|<span data-ttu-id="5bd89-113">L'instance d'agent SQL Server pour l'instance du moteur de base de données SQL.</span><span class="sxs-lookup"><span data-stu-id="5bd89-113">The instance of SQL Server agent for the instance of the SQL database engine.</span></span>|
|<span data-ttu-id="5bd89-114">**3**</span><span class="sxs-lookup"><span data-stu-id="5bd89-114">**3**</span></span>|<span data-ttu-id="5bd89-115">Les bases de données d'application de service Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="5bd89-115">The Reporting Services service application databases.</span></span> <span data-ttu-id="5bd89-116">Les noms sont formés sur la base des informations utilisées lors de la création de l'application de service.</span><span class="sxs-lookup"><span data-stu-id="5bd89-116">The names are based on the information used for creating the service application.</span></span> <span data-ttu-id="5bd89-117">Vous trouverez ci-dessous des exemples de noms de bases de données :</span><span class="sxs-lookup"><span data-stu-id="5bd89-117">The following are example database names:</span></span><br /><br /> <span data-ttu-id="5bd89-118">ReportingService_2fbae157295d49df86d0b85760c704b0</span><span class="sxs-lookup"><span data-stu-id="5bd89-118">ReportingService_2fbae157295d49df86d0b85760c704b0</span></span><br /><br /> <span data-ttu-id="5bd89-119">ReportingService_2fbae157295d49df86d0b85760c704b0_Alerting</span><span class="sxs-lookup"><span data-stu-id="5bd89-119">ReportingService_2fbae157295d49df86d0b85760c704b0_Alerting</span></span><br /><br /> <span data-ttu-id="5bd89-120">ReportingService_2fbae157295d49df86d0b85760c704b0TempDB</span><span class="sxs-lookup"><span data-stu-id="5bd89-120">ReportingService_2fbae157295d49df86d0b85760c704b0TempDB</span></span>|
|<span data-ttu-id="5bd89-121">**4**</span><span class="sxs-lookup"><span data-stu-id="5bd89-121">**4**</span></span>|<span data-ttu-id="5bd89-122">Base de données master et MSDB de l'instance du moteur de base de données SQL.</span><span class="sxs-lookup"><span data-stu-id="5bd89-122">The master and MSDB database of the instance of the SQL Server Database engine.</span></span>|

 <span data-ttu-id="5bd89-123">Recourez à l'une des trois méthodes suivantes pour mettre à jour les autorisations :</span><span class="sxs-lookup"><span data-stu-id="5bd89-123">Use one the following three methods to update the permissions:</span></span>

1.  <span data-ttu-id="5bd89-124">Dans la page **Configurer les abonnements et les alertes** , entrez les informations d’identification, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5bd89-124">From the **Provisions and Subscriptions and Alerts** page, type credentials and click **ok**.</span></span>

2.  <span data-ttu-id="5bd89-125">Dans la page Configurer les abonnements et les alertes, cliquez sur le bouton **Télécharger le script** pour télécharger un script Transact-SQL qui peut être utilisé pour configurer les autorisations.</span><span class="sxs-lookup"><span data-stu-id="5bd89-125">From the Provisions and Subscriptions and Alerts page, click the **Download Script** button to download a transact SQL script that can be used to configure permissions.</span></span>

3.  <span data-ttu-id="5bd89-126">Exécutez une applet de commande PowerShell pour générer un script Transact-SQL qui peut être utilisé pour configurer les autorisations.</span><span class="sxs-lookup"><span data-stu-id="5bd89-126">Run a PowerShell cmdlet to build a transact SQL script that can be used to configure permissions.</span></span>

### <a name="to-update-permissions-using-the-provision-page"></a><span data-ttu-id="5bd89-127">Pour mettre à jour les autorisation dans la page de configuration</span><span class="sxs-lookup"><span data-stu-id="5bd89-127">To update permissions using the provision page</span></span>

1.  <span data-ttu-id="5bd89-128">Depuis l’Administration centrale de SharePoint, dans le groupe **Gestion des applications** , cliquez sur **Gérer les applications de service**.</span><span class="sxs-lookup"><span data-stu-id="5bd89-128">From SharePoint Central Administration, in the **Application Management** group click **Manage Service Applications**</span></span>

2.  <span data-ttu-id="5bd89-129">Repérez votre application de service dans la liste et cliquez sur son nom ou cliquez sur la colonne **Type** pour sélectionner l’application de services et cliquez sur le bouton **Gérer** dans le ruban SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5bd89-129">Find your service application in the list and click the name of the application or click the **Type** column to select the services application and click the **Manage** button in the SharePoint ribbon.</span></span>

3.  <span data-ttu-id="5bd89-130">Dans la page **Gérer l’application Reporting Services** , cliquez sur **Configurer les abonnements et les alertes**.</span><span class="sxs-lookup"><span data-stu-id="5bd89-130">On the **Manage Reporting Services Application** page, click **Provision Subscriptions and Alerts**.</span></span>

4.  <span data-ttu-id="5bd89-131">Si l'administrateur SharePoint possède assez de privilèges sur la base de données MASTER et les bases de données d'application de service, entrez ces informations de connexion.</span><span class="sxs-lookup"><span data-stu-id="5bd89-131">If the SharePoint administrator has enough privileges to the Master database and the service application databases, type those credentials.</span></span>

5.  <span data-ttu-id="5bd89-132">Cliquez sur le bouton **OK** .</span><span class="sxs-lookup"><span data-stu-id="5bd89-132">Click the **OK** button.</span></span>

##  <a name="to-download-the-transact-sql-script"></a><a name="bkmk_download"></a> <span data-ttu-id="5bd89-133">Pour télécharger le script Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5bd89-133">To download the Transact-SQL Script</span></span>

1.  <span data-ttu-id="5bd89-134">Depuis l’Administration centrale de SharePoint, dans le groupe **Gestion des applications** , cliquez sur **Gérer les applications de service**.</span><span class="sxs-lookup"><span data-stu-id="5bd89-134">From SharePoint Central Administration, in the **Application Management** group click **Manage Service Applications**</span></span>

2.  <span data-ttu-id="5bd89-135">Repérez votre application de service dans la liste et cliquez sur son nom ou cliquez sur la colonne **Type** pour sélectionner l’application de services et cliquez sur le bouton **Gérer** dans le ruban SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5bd89-135">Find your service application in the list and click the name of the application or click the **Type** column to select the services application and click the **Manage** button in the SharePoint ribbon.</span></span>

3.  <span data-ttu-id="5bd89-136">Dans la page **Gérer l’application Reporting Services** , cliquez sur **Configurer les abonnements et les alertes**.</span><span class="sxs-lookup"><span data-stu-id="5bd89-136">On the **Manage Reporting Services Application** page, click **Provision Subscriptions and Alerts**.</span></span>

4.  <span data-ttu-id="5bd89-137">Dans la zone **Afficher l’état** , vérifiez que l’Agent SQL Server s’exécute.</span><span class="sxs-lookup"><span data-stu-id="5bd89-137">In the **View Status** area, verify SQL Server Agent is running.</span></span>

5.  <span data-ttu-id="5bd89-138">Cliquez sur **Télécharger le script** pour télécharger un script Transact-SQL que vous pouvez exécuter dans SQL Server Management Studio pour accorder des autorisations.</span><span class="sxs-lookup"><span data-stu-id="5bd89-138">Click **Download Script** to download a transact SQL script you can run in SQL Server Management studio to grant permissions.</span></span> <span data-ttu-id="5bd89-139">Le nom du fichier de script créé contient le nom de l’application de service Reporting Services, par exemple **[nom de l’application de service]-GrantRights.sql**.</span><span class="sxs-lookup"><span data-stu-id="5bd89-139">The script file name that is created will contain the name of your Reporting Services service application name, for example **[name of the service application]-GrantRights.sql**.</span></span>

### <a name="to-generate-the-transact-sql-statement-with-powershell"></a><span data-ttu-id="5bd89-140">Pour générer l'instruction Transact-SQL avec PowerShell</span><span class="sxs-lookup"><span data-stu-id="5bd89-140">To generate the Transact-SQL statement with PowerShell</span></span>

1.  <span data-ttu-id="5bd89-141">Vous pouvez également utiliser un applet de commande Windows PowerShell dans SharePoint 2010 Management Shell pour créer le script Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="5bd89-141">You can also use a Windows PowerShell cmdlet in the SharePoint 2010 Management Shell to create the Transact-SQL script.</span></span>

2.  <span data-ttu-id="5bd89-142">Dans le menu **Démarrer** , cliquez sur **Tous les programmes**.</span><span class="sxs-lookup"><span data-stu-id="5bd89-142">On the **Start** menu, click **All Programs**.</span></span>

3.  <span data-ttu-id="5bd89-143">Développez **produits Microsoft sharepoint 2010** , puis cliquez sur **SharePoint 2010 Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5bd89-143">Expand **Microsoft SharePoint 2010 Products** and click **SharePoint 2010 Management Shell**.</span></span>

4.  <span data-ttu-id="5bd89-144">Mettez à jour l'applet de commande PowerShell suivant en remplaçant le nom de la base de données du serveur de rapports, le compte du pool d'applications, et le chemin d'accès de l'instruction.</span><span class="sxs-lookup"><span data-stu-id="5bd89-144">Update the following PowerShell cmdlet by replacing the name of the report server database, application pool account, and the path of the statement.</span></span>

     <span data-ttu-id="5bd89-145">**Syntaxe de cmdlet :** `Get-SPRSDatabaseRightsScript -DatabaseName <ReportingServices database name> -UserName <app pool account> -IsWindowsUser | Out-File <path of statement>`</span><span class="sxs-lookup"><span data-stu-id="5bd89-145">**Syntax of cmdlet:** `Get-SPRSDatabaseRightsScript -DatabaseName <ReportingServices database name> -UserName <app pool account> -IsWindowsUser | Out-File <path of statement>`</span></span>

     <span data-ttu-id="5bd89-146">**Exemple de cmdlet :** `Get-SPRSDatabaseRightsScript -DatabaseName ReportingService_46fd00359f894b828907b254e3f6257c -UserName "NT AUTHORITY\NETWORK SERVICE" -IsWindowsUser | Out-File c:\SQLServerAgentrights.sql`</span><span class="sxs-lookup"><span data-stu-id="5bd89-146">**Sample cmdlet:** `Get-SPRSDatabaseRightsScript -DatabaseName ReportingService_46fd00359f894b828907b254e3f6257c -UserName "NT AUTHORITY\NETWORK SERVICE" -IsWindowsUser | Out-File c:\SQLServerAgentrights.sql`</span></span>

## <a name="using-the-transact-sql-script"></a><span data-ttu-id="5bd89-147">Utilisation du script Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5bd89-147">Using the Transact-SQL Script</span></span>
 <span data-ttu-id="5bd89-148">Les procédures suivantes peuvent être utilisées avec des scripts téléchargés depuis les pages de configuration ou des scripts créés à l'aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5bd89-148">The following procedures can be used with scripts download from the provisions page or scripts created using PowerShell.</span></span>

#### <a name="to-load-the-transact-sql-script-in-sql-server-management-studio"></a><span data-ttu-id="5bd89-149">Pour charger le script Transact-SQL dans SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5bd89-149">To load the Transact-SQL script in SQL Server Management Studio</span></span>

1.  <span data-ttu-id="5bd89-150">Pour ouvrir SQL Server Management Studio, dans le menu **Démarrer** , cliquez sur **Microsoft SQL Server 2012** , puis sur **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="5bd89-150">To open SQL Server Management Studio, on the **Start** menu, click **Microsoft SQL Server 2012** and click **SQL Server Management Studio**.</span></span>

2.  <span data-ttu-id="5bd89-151">Dans la boîte de dialogue **Se connecter au serveur** , définissez les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="5bd89-151">In the **Connect to Server** dialog box set the following options:</span></span>

    -   <span data-ttu-id="5bd89-152">Dans la liste **Type de serveur** , sélectionnez **Moteur de base de données**.</span><span class="sxs-lookup"><span data-stu-id="5bd89-152">In the **Server type** list, select **Database Engine**</span></span>

    -   <span data-ttu-id="5bd89-153">Dans **Nom du serveur**, tapez le nom de l’instance de SQL Server sur laquelle vous souhaitez configurer l’Agent SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5bd89-153">In **Server Name**, type the name of the SQL Server instance on which you want to configure SQL Server Agent.</span></span>

    -   <span data-ttu-id="5bd89-154">Sélectionnez un mode d'authentification.</span><span class="sxs-lookup"><span data-stu-id="5bd89-154">Select an authentication mode.</span></span>

    -   <span data-ttu-id="5bd89-155">Si vous utilisez l'authentification SQL Server pour vous connecter, vous devez fournir un ID de conenxion et un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="5bd89-155">If connecting using SQL Server Authentication, provide a login and password.</span></span>

3.  <span data-ttu-id="5bd89-156">Cliquez sur **Connecter**.</span><span class="sxs-lookup"><span data-stu-id="5bd89-156">Click **Connect**.</span></span>

#### <a name="to-run-the-transact-sql-statement"></a><span data-ttu-id="5bd89-157">Pour exécuter l'instruction Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5bd89-157">To run the Transact-SQL statement</span></span>

1.  <span data-ttu-id="5bd89-158">Dans la barre d’outils de SQL Server Management Studio, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="5bd89-158">On the toolbar of SQL Server Management Studio, click **New Query**.</span></span>

2.  <span data-ttu-id="5bd89-159">Dans le menu **Fichier** , cliquez sur **Ouvrir**, puis sur **Fichier**.</span><span class="sxs-lookup"><span data-stu-id="5bd89-159">On the **File** menu, click **Open**, and then click **File**.</span></span>

3.  <span data-ttu-id="5bd89-160">Accédez au dossier où vous avez enregistré l'instruction Transact-SQL que vous avez générée dans SharePoint 2010 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5bd89-160">Navigate to the folder where you saved the Transact-SQL statement that you generated in SharePoint 2010 Management Shell.</span></span>

4.  <span data-ttu-id="5bd89-161">Cliquez sur le fichier, puis sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="5bd89-161">Click the file and then click **Open**.</span></span>

     <span data-ttu-id="5bd89-162">L'instruction est ajoutée dans la fenêtre de requête.</span><span class="sxs-lookup"><span data-stu-id="5bd89-162">The statement is added to the query window.</span></span>

5.  <span data-ttu-id="5bd89-163">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="5bd89-163">Click **Execute**.</span></span>


