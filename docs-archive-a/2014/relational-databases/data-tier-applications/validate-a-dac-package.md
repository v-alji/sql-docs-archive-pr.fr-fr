---
title: Valider un package DAC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- data-tier application [SQL Server], validate
- data-tier application [SQL Server], compare
- validate DAC
- compare DACs
- data-tier application [SQL Server], view
- view DAC
ms.assetid: 726ffcc2-9221-424a-8477-99e3f85f03bd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 078c7bfeef2ff8636243f4853c03de252c7b9289
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614120"
---
# <a name="validate-a-dac-package"></a><span data-ttu-id="cc5f8-102">Valider un package DAC</span><span class="sxs-lookup"><span data-stu-id="cc5f8-102">Validate a DAC Package</span></span>
  <span data-ttu-id="cc5f8-103">Il est conseillé d'examiner le contenu d'un package DAC avant de le déployer en production et de valider les actions de mise à niveau avant de mettre à niveau une DAC existante.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-103">It is a good practice to review the contents of a DAC package before deploying it in production, and to validate the upgrade actions before upgrading an existing DAC.</span></span> <span data-ttu-id="cc5f8-104">Ceci tout particulièrement lors du déploiement de packages qui n'ont pas été développés dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-104">This is especially true when deploying packages that were not developed in your organization.</span></span>  
  
1.  <span data-ttu-id="cc5f8-105">**Avant de commencer :**  [Prérequis](#Prerequisites)</span><span class="sxs-lookup"><span data-stu-id="cc5f8-105">**Before you begin:**  [Prerequisites](#Prerequisites)</span></span>  
  
2.  <span data-ttu-id="cc5f8-106">**Pour mettre à niveau une DAC à l’aide de** :  [Afficher le contenu d’une DAC](#ViewDACContents), [Afficher les modifications de base de données](#ViewDBChanges), [Afficher les actions de mise à niveau](#ViewUpgradeActions), [Comparer les DAC](#CompareDACs)</span><span class="sxs-lookup"><span data-stu-id="cc5f8-106">**To upgrade a DAC, using:**  [View the Contents of a DAC](#ViewDACContents), [View Database Changes](#ViewDBChanges), [View Upgrade Actions](#ViewUpgradeActions), [Compare DACs](#CompareDACs)</span></span>  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="cc5f8-107">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="cc5f8-107">Prerequisites</span></span>  
 <span data-ttu-id="cc5f8-108">Nous vous recommandons de ne pas déployer un package DAC provenant de sources inconnues ou non approuvées.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-108">We recommend that you do not deploy a DAC package from unknown or untrusted sources.</span></span> <span data-ttu-id="cc5f8-109">Ces DAC peuvent contenir du code malveillant susceptible d'exécuter un code [!INCLUDE[tsql](../../includes/tsql-md.md)] indésirable ou de provoquer des erreurs en modifiant le schéma.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-109">Such DACs could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema.</span></span> <span data-ttu-id="cc5f8-110">Avant d’utiliser une DAC provenant d’une source inconnue ou non approuvée, déployez-la sur une instance de test isolée de [!INCLUDE[ssDE](../../includes/ssde-md.md)], exécutez [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) sur la base de données sur un serveur autre qu’un serveur de production et examinez également le code (par exemple les procédures stockées ou tout autre code défini par l’utilisateur) contenu dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-110">Before you use a DAC from an unknown or untrusted source, deploy it on an isolated test instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], run [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database, and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
##  <a name="view-the-contents-of-a-dac"></a><a name="ViewDACContents"></a> <span data-ttu-id="cc5f8-111">Afficher le contenu d'une DAC</span><span class="sxs-lookup"><span data-stu-id="cc5f8-111">View the Contents of a DAC</span></span>  
 <span data-ttu-id="cc5f8-112">Il existe deux mécanismes d'affichage du contenu d'un package d'application de la couche Données (DAC).</span><span class="sxs-lookup"><span data-stu-id="cc5f8-112">There are two mechanisms for viewing the contents of a data-tier application (DAC) package.</span></span> <span data-ttu-id="cc5f8-113">Vous pouvez importer le package DAC vers un projet DAC dans les outils de développement de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-113">You can import the DAC package to a DAC project in SQL Server Developer Tools.</span></span> <span data-ttu-id="cc5f8-114">Vous pouvez décompresser le contenu du package dans un dossier.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-114">You can unpack the contents of the package to a folder.</span></span>  
  
 <span data-ttu-id="cc5f8-115">**Afficher une DAC dans les outils de développement de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="cc5f8-115">**View a DAC in SQL Server Developer Tools**</span></span>  
  
1.  <span data-ttu-id="cc5f8-116">Dans le menu **Fichier**, sélectionnez **Nouveau**, puis **Projet**.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-116">Open the **File** menu, select **New**, and then select **Project...**.</span></span>  
  
2.  <span data-ttu-id="cc5f8-117">Sélectionnez le modèle de projet **SQL Server** , puis spécifiez un **Nom**, un **Emplacement**et un **Nom de solution**.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-117">Select the **SQL Server** project template, and specify a **Name**, **Location**, and **Solution name**.</span></span>  
  
3.  <span data-ttu-id="cc5f8-118">Dans l’**Explorateur de solutions**, cliquez avec le bouton droit sur le nœud de projet, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-118">In **Solution Explorer**, right click the project node and select **Properties...**.</span></span>  
  
4.  <span data-ttu-id="cc5f8-119">Sous l’onglet **Paramètres du projet** , dans la section **Type de sortie** , cochez la case **Application de la couche Données (fichier .dacpac)** , puis fermez la boîte de dialogue de propriétés.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-119">On the **Project Settings** tab, in the **Output Types** section, select the **Data-tier Application (.dacpac File)** check box, and then close the properties dialog.</span></span>  
  
5.  <span data-ttu-id="cc5f8-120">Dans l’**Explorateur de solutions**, cliquez avec le bouton droit sur le nœud du projet et sélectionnez **Importer une application de la couche Données**.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-120">In **Solution Explorer**, right click the project node and select **Import Data-tier Application...**.</span></span>  
  
6.  <span data-ttu-id="cc5f8-121">Utilisez l’ **Explorateur de solutions** pour ouvrir tous les fichiers de la DAC, tels que la stratégie de sélection du serveur et les scripts de pré- et post-déploiement.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-121">Use **Solution Explorer** to open all of the files in the DAC, such as the server selection policy and the pre- and post-deployment scripts.</span></span>  
  
7.  <span data-ttu-id="cc5f8-122">Utilisez le **Mode schéma** pour examiner tous les objets du schéma, en particulier le code des objets, comme les fonctions ou les procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-122">Use the **Schema View** to review all of the objects in the schema, particularly reviewing the code in objects such as functions or stored procedures.</span></span>  
  
 <span data-ttu-id="cc5f8-123">**Afficher une DAC dans un dossier**</span><span class="sxs-lookup"><span data-stu-id="cc5f8-123">**View a DAC in a Folder**</span></span>  
  
-   <span data-ttu-id="cc5f8-124">Décompressez le package DAC dans un dossier en suivant les instructions fournies dans [Unpack a DAC Package](unpack-a-dac-package.md).</span><span class="sxs-lookup"><span data-stu-id="cc5f8-124">Unpack the DAC package into a folder by following the instructions in [Unpack a DAC Package](unpack-a-dac-package.md).</span></span>  
  
-   <span data-ttu-id="cc5f8-125">Affichez le contenu des scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] en les ouvrant dans l'Éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc5f8-125">View the contents of the [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts by opening them in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
-   <span data-ttu-id="cc5f8-126">Affichez le contenu des fichiers texte dans des outils tels que le Bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-126">View the contents of the text files in tools such as notepad.</span></span>  
  
##  <a name="view-database-changes"></a><a name="ViewDBChanges"></a> <span data-ttu-id="cc5f8-127">Afficher les modifications de base de données</span><span class="sxs-lookup"><span data-stu-id="cc5f8-127">View Database Changes</span></span>  
 <span data-ttu-id="cc5f8-128">Après la version actuelle de la DAC déployée en production, des modifications ont pu être apportées directement à la base de données associée qui peuvent être en conflit avec le schéma défini dans une nouvelle version de la DAC.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-128">After the current version of a DAC was deployed to production, changes may have been made directly to the associated database that might conflict with the schema defined in a new version of the DAC.</span></span> <span data-ttu-id="cc5f8-129">Avant la mise à niveau vers une nouvelle version de la DAC, vérifiez si de telles modifications ont été apportées à la base de données.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-129">Before upgrading to a new version of the DAC, check to see if such changes have been made to the database.</span></span>  
  
 <span data-ttu-id="cc5f8-130">**Afficher les modifications de base de données à l'aide d'un Assistant**</span><span class="sxs-lookup"><span data-stu-id="cc5f8-130">**View Database Changes by Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="cc5f8-131">Exécutez l’Assistant **Mettre à niveau une application de la couche Données** , en spécifiant la DAC actuellement déployée et le package DAC qui contient la nouvelle version de la DAC.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-131">Run the **Upgrade Data-tier Application** wizard, specifying the currently deployed DAC and the DAC package containing the new version of the DAC.</span></span>  
  
2.  <span data-ttu-id="cc5f8-132">Sur la page de **Détecter les modifications** , examinez le rapport des modifications apportées à la base de données.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-132">On the **Detect Change** page, review the report of the changes that have been made to the database.</span></span>  
  
3.  <span data-ttu-id="cc5f8-133">Sélectionnez **Annuler** si vous ne souhaitez pas poursuivre la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-133">Select **Cancel** if you do not want to continue with the upgrade.</span></span>  
  
4.  <span data-ttu-id="cc5f8-134">Pour plus d’informations sur l’utilisation de l’Assistant, consultez [Mettre à niveau une application de la couche Données](upgrade-a-data-tier-application.md).</span><span class="sxs-lookup"><span data-stu-id="cc5f8-134">For more information on using the wizard, see [Upgrade a Data-tier Application](upgrade-a-data-tier-application.md).</span></span>  
  
### <a name="view-database-changes-by-using-powershell"></a><span data-ttu-id="cc5f8-135">Afficher les modifications de base de données à l'aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc5f8-135">View Database Changes by Using PowerShell</span></span>
  
1.  <span data-ttu-id="cc5f8-136">Créez un objet serveur SMO et définissez-le sur l'instance qui contient la DAC à afficher.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-136">Create a SMO Server object and set it to the instance that contains the DAC to be viewed.</span></span>  
  
2.  <span data-ttu-id="cc5f8-137">Ouvrez un objet `ServerConnection` et connectez-vous à la même instance.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-137">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="cc5f8-138">Spécifiez le nom de la DAC dans une variable.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-138">Specify the DAC name in a variable.</span></span>  
  
4.  <span data-ttu-id="cc5f8-139">Utilisez la méthode `GetDatabaseChanges()` pour récupérer un objet `ChangeResults`, et redirigez l'objet vers un fichier texte pour générer un rapport simple des objets nouveaux, supprimés et modifiés.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-139">Use the `GetDatabaseChanges()` method to retrieve a `ChangeResults` object, and pipe the object to a text file to generate a simple report of new, deleted, and changed objects.</span></span>  
  
### <a name="view-database-changes-example-powershell"></a><span data-ttu-id="cc5f8-140">Afficher une exemple de modifications de base de données (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="cc5f8-140">View Database Changes Example (PowerShell)</span></span>
  
 <span data-ttu-id="cc5f8-141">L'exemple suivant signale toutes les modifications de base de données qui ont été apportées dans une DAC déployée nommée MyApplication.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-141">The following example reports any database changes that have been made in a deployed DAC named MyApplicaiton.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Specify the DAC instance name.  
$dacName  = "MyApplication"  
  
## Generate the change list and save to file.  
$dacChanges = $dacstore.GetDatabaseChanges($dacName) | Out-File -Filepath C:\DACScripts\MyApplicationChanges.txt  
```  
  
##  <a name="view-upgrade-actions"></a><a name="ViewUpgradeActions"></a> <span data-ttu-id="cc5f8-142">Afficher les actions de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="cc5f8-142">View Upgrade Actions</span></span>  
 <span data-ttu-id="cc5f8-143">Avant d'utiliser une nouvelle version d'un package DAC en vue de mettre à niveau une DAC déployée à partir d'une version antérieure d'un package DAC, vous pouvez générer un rapport contenant les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] qui seront exécutées durant la mise à niveau, puis passer en revue ces instructions.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-143">Before using a new version of a DAC package to upgrade a DAC that was deployed from an earlier DAC package, you can generate a report that contains the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that will be run during the upgrade, and then review the statements.</span></span>  
  
 <span data-ttu-id="cc5f8-144">**Signaler les actions de mise à niveau à l'aide d'un Assistant**</span><span class="sxs-lookup"><span data-stu-id="cc5f8-144">**Report Upgrade Actions by Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="cc5f8-145">Exécutez l’Assistant **Mettre à niveau une application de la couche Données** , en spécifiant la DAC actuellement déployée et le package DAC qui contient la nouvelle version de la DAC.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-145">Run the **Upgrade Data-tier Application** wizard, specifying the currently deployed DAC and the DAC package containing the new version of the DAC.</span></span>  
  
2.  <span data-ttu-id="cc5f8-146">Sur la page **Résumé** , examinez le rapport des actions de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-146">On the **Summary** page, review the report of the upgrade actions.</span></span>  
  
3.  <span data-ttu-id="cc5f8-147">Sélectionnez **Annuler** si vous ne souhaitez pas poursuivre la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-147">Select **Cancel** if you do not want to continue with the upgrade.</span></span>  
  
4.  <span data-ttu-id="cc5f8-148">Pour plus d’informations sur l’utilisation de l’Assistant, consultez [Mettre à niveau une application de la couche Données](upgrade-a-data-tier-application.md).</span><span class="sxs-lookup"><span data-stu-id="cc5f8-148">For more information on using the wizard, see [Upgrade a Data-tier Application](upgrade-a-data-tier-application.md).</span></span>  
  
 <span data-ttu-id="cc5f8-149">**Signaler les actions de mise à niveau à l'aide de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="cc5f8-149">**Report Upgrade Actions by Using PowerShell**</span></span>  
  
1.  <span data-ttu-id="cc5f8-150">Créez un objet serveur SMO et définissez-le sur l'instance qui contient la DAC déployée.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-150">Create a SMO Server object and set it to the instance that contains the deployed DAC.</span></span>  
  
2.  <span data-ttu-id="cc5f8-151">Ouvrez un objet `ServerConnection` et connectez-vous à la même instance.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-151">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="cc5f8-152">Utilisez `System.IO.File` pour charger le fichier de package DAC.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-152">Use `System.IO.File` to load the DAC package file.</span></span>  
  
4.  <span data-ttu-id="cc5f8-153">Spécifiez le nom de la DAC dans une variable.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-153">Specify the DAC name in a variable.</span></span>  
  
5.  <span data-ttu-id="cc5f8-154">Utilisez la méthode `GetIncrementalUpgradeScript()` pour obtenir la liste des instructions Transact-SQL qui seraient exécutées par une mise à niveau et redirigez cette liste vers un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-154">Use the `GetIncrementalUpgradeScript()` method to get a list of the Transact-SQL statements an upgrade would run, and pipe the list to a text file.</span></span>  
  
6.  <span data-ttu-id="cc5f8-155">Fermez le flux de fichier utilisé pour lire le fichier de package DAC.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-155">Close the file stream used to read the DAC package file.</span></span>  
  
### <a name="view-upgrade-actions-example-powershell"></a><span data-ttu-id="cc5f8-156">Afficher un exemple d'actions de mise à niveau (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="cc5f8-156">View Upgrade Actions Example (PowerShell)</span></span>
  
 <span data-ttu-id="cc5f8-157">L'exemple suivant signale les instructions Transact-SQL qui seraient exécutées pour mettre à niveau une DAC nommée MyApplication vers le schéma défini dans un fichier MyApplicationVNext.dacpac.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-157">The following example reports the Transact-SQL statements that would be run to upgrading a DAC named MyApplicaiton to the schema defined in a MyApplicationVNext.dacpac file.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Load the DAC package file.  
$dacpacPath = "C:\MyDACs\MyApplicationVNext.dacpac"  
$fileStream = [System.IO.File]::Open($dacpacPath,[System.IO.FileMode]::OpenOrCreate)  
$dacType = [Microsoft.SqlServer.Management.Dac.DacType]::Load($fileStream)  
  
## Specify the DAC instance name.  
$dacName  = "MyApplication"  
  
## Generate the upgrade script and save to file.  
$dacstore.GetIncrementalUpgradeScript($dacName, $dacType) | Out-File -Filepath C:\DACScripts\MyApplicationUpgrade.sql  
  
## Close the filestream to the new DAC package.  
$fileStream.Close()  
```  
  
##  <a name="compare-dacs"></a><a name="CompareDACs"></a><span data-ttu-id="cc5f8-158">Comparer DAC</span><span class="sxs-lookup"><span data-stu-id="cc5f8-158">Compare DACs</span></span>  
 <span data-ttu-id="cc5f8-159">Avant de mettre à niveau une DAC, il est conseillé d'examiner les différences dans la base de données et les objets au niveau de l'instance entre les DAC actuelles et nouvelles.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-159">Before upgrading a DAC, it is a good practice to review the differences in the database and instance-level objects between the current and new DACs.</span></span> <span data-ttu-id="cc5f8-160">Si vous ne disposez pas d'une copie du package de la DAC actuelle, vous pouvez extraire un package de la base de données actuelle.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-160">If you do not have a copy of the package for the current DAC, you can extract a package from the current database.</span></span>  
  
 <span data-ttu-id="cc5f8-161">Si vous importez les deux packages DAC dans des projets DAC dans les outils de développement de SQL Server, vous pouvez utiliser l'outil Comparaison de schémas pour analyser les différences entre les deux DAC.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-161">If you import both DAC packages into DAC projects in SQL Server Developer Tools, you can use the Schema Compare tool to analyze the differences between the two DACs.</span></span>  
  
 <span data-ttu-id="cc5f8-162">Ou bien, décompressez les DAC dans des dossiers distincts.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-162">Alternatively, unpack the DACs into separate folders.</span></span> <span data-ttu-id="cc5f8-163">Vous pouvez ensuite utiliser un outil de comparaison, tel que l'utilitaire WinDiff, pour analyser les différences.</span><span class="sxs-lookup"><span data-stu-id="cc5f8-163">You can then use a difference tool, such as the WinDiff utility, to analyze the differences.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc5f8-164">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cc5f8-164">See Also</span></span>  
 <span data-ttu-id="cc5f8-165">[Applications de la couche Données](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="cc5f8-165">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="cc5f8-166">[Déployer une application de la couche données](deploy-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="cc5f8-166">[Deploy a Data-tier Application](deploy-a-data-tier-application.md) </span></span>  
 [<span data-ttu-id="cc5f8-167">Mettre à niveau une application de la couche données</span><span class="sxs-lookup"><span data-stu-id="cc5f8-167">Upgrade a Data-tier Application</span></span>](upgrade-a-data-tier-application.md)  
