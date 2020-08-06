---
title: Exporter une application de la couche Données | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.exportdac.settings.f1
- sql12.swb. exportdac.settings.f1
- sql12.swb.exportdac.welcome.f1
- sql12.swb. exportdac.summary.f1
- sql12.swb.exportdac.progress.f1
- sql12.swb.exportdac.summary.f1
- sql12.swb.exportdac.results.f1
- sql12.swb. exportdac.results.f1
helpviewer_keywords:
- How to [DAC], export
- wizard [DAC], export
- export DAC
- data-tier application [SQL Server], export
ms.assetid: 61915bc5-0f5f-45ac-8cfe-3452bc185558
author: stevestein
ms.author: sstein
ms.openlocfilehash: d5e1bbfc5c38dee5e7f29598086d87b680880641
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612942"
---
# <a name="export-a-data-tier-application"></a><span data-ttu-id="d404e-102">Exporter une application de la couche Données</span><span class="sxs-lookup"><span data-stu-id="d404e-102">Export a Data-tier Application</span></span>
  <span data-ttu-id="d404e-103">L'exportation d'une application de la couche Données (DAC) déployée ou d'une base de données crée un fichier d'exportation qui inclut les définitions des objets de la base de données et toutes les données contenues dans les tables.</span><span class="sxs-lookup"><span data-stu-id="d404e-103">Exporting a deployed data-tier application (DAC) or database creates an export file that includes both the definitions of the objects in the database and all of the data contained in the tables.</span></span> <span data-ttu-id="d404e-104">Le fichier d'exportation peut ensuite être importé dans une autre instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)]ou dans [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d404e-104">The export file can then be imported to another instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], or to [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)].</span></span> <span data-ttu-id="d404e-105">Les opérations d'exportation-importation peuvent être combinées pour migrer une DAC entre différentes instances, pour créer une sauvegarde logique ou pour créer une copie sur site d'une base de données déployée dans [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d404e-105">The export-import operations can be combined to migrate a DAC between instances, to create a logical backup, or to create an on-premise copy of a database deployed in [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="d404e-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="d404e-106">Before You Begin</span></span>  
 <span data-ttu-id="d404e-107">Le processus d'exportation génère un fichier d'exportation DAC en deux étapes.</span><span class="sxs-lookup"><span data-stu-id="d404e-107">The export process builds a DAC export file in two stages.</span></span>  
  
1.  <span data-ttu-id="d404e-108">L’exportation génère une définition de la DAC dans le fichier d’exportation (fichier BACPAC), de la même manière que l’extraction d’une DAC génère une définition de la DAC dans un fichier de package DAC.</span><span class="sxs-lookup"><span data-stu-id="d404e-108">The export builds a DAC definition in the export file - BACPAC file - in the same way a DAC extract builds a DAC definition in a DAC package file.</span></span> <span data-ttu-id="d404e-109">La définition de la DAC exportée inclut tous les objets de la base de données active.</span><span class="sxs-lookup"><span data-stu-id="d404e-109">The exported DAC definition includes all of the objects in the current database.</span></span> <span data-ttu-id="d404e-110">Si le processus d'exportation est exécuté sur une base de données à l'origine déployée à partir de la DAC et si des modifications ont été apportées directement à la base de données après le déploiement, la définition exportée correspond au jeu d'objets dans la base de données, pas à ce qui a été défini dans la DAC d'origine.</span><span class="sxs-lookup"><span data-stu-id="d404e-110">If the export process is run against a database that was originally deployed from a DAC, and changes were made directly to the database after deployment, the exported definition matches the object set in the database, not what was defined in the original DAC.</span></span>  
  
2.  <span data-ttu-id="d404e-111">L'exportation copie en bloc les données de toutes les tables dans la base de données et les incorpore dans le fichier d'exportation.</span><span class="sxs-lookup"><span data-stu-id="d404e-111">The export bulk copies out the data from all of the tables in the database and incorporates the data into the export file.</span></span>  
  
 <span data-ttu-id="d404e-112">Le processus d'exportation définit la version de la DAC sur 1.0.0.0 et la description de la DAC dans le fichier d'exportation sur une chaîne vide.</span><span class="sxs-lookup"><span data-stu-id="d404e-112">The export process sets the DAC version to 1.0.0.0 and the DAC description in the export file to an empty string.</span></span> <span data-ttu-id="d404e-113">Si la base de données a été déployée à partir de la DAC, la définition de la DAC dans le fichier d'exportation contient le nom donné à la DAC d'origine, sinon le nom de la DAC est défini sur le nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="d404e-113">If the database was deployed from a DAC, the DAC definition in the export file contains the name given to the original DAC, otherwise the DAC name is set to the database name.</span></span>  
  

###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="d404e-114">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="d404e-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="d404e-115">Une DAC ou une base de données peut uniquement être exportée à partir d'une base de données dans [!INCLUDE[ssSDS](../../includes/sssds-md.md)]ou [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="d404e-115">A DAC or database can only be exported from a database in [!INCLUDE[ssSDS](../../includes/sssds-md.md)], or [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) or later.</span></span>  
  
 <span data-ttu-id="d404e-116">Vous ne pouvez pas exporter une base de données contenant des objets qui ne sont pas pris en charge dans une DAC ou contenant des utilisateurs à relation contenant-contenu.</span><span class="sxs-lookup"><span data-stu-id="d404e-116">You cannot export a database that has objects that are not supported in a DAC, or contained users.</span></span> <span data-ttu-id="d404e-117">Pour plus d'informations sur les types d'objets pris en charge dans une DAC, consultez [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span><span class="sxs-lookup"><span data-stu-id="d404e-117">For more information about the types of objects supported in a DAC, see [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d404e-118">Autorisations</span><span class="sxs-lookup"><span data-stu-id="d404e-118">Permissions</span></span>  
 <span data-ttu-id="d404e-119">L’exportation d’une DAC requiert au minimum des autorisations ALTER ANY LOGIN et VIEW DEFINITION de la portée de la base de données, ainsi que des autorisations SELECT sur **sys.sql_expression_dependencies**.</span><span class="sxs-lookup"><span data-stu-id="d404e-119">Exporting a DAC requires at least ALTER ANY LOGIN and database scope VIEW DEFINITION permissions, as well as SELECT permissions on **sys.sql_expression_dependencies**.</span></span> <span data-ttu-id="d404e-120">L'exportation d'une DAC peut être réalisée par les membres du rôle serveur fixe securityadmin également membres du rôle de base de données fixe database_owner dans la base de données à partir de laquelle est extraite la DAC.</span><span class="sxs-lookup"><span data-stu-id="d404e-120">Exporting a DAC can be done by members of the securityadmin fixed server role who are also members of the database_owner fixed database role in the database from which the DAC is exported.</span></span> <span data-ttu-id="d404e-121">Les membres du rôle serveur fixe sysadmin ou le compte d’administrateur système intégré de SQL Server nommé **sa** peuvent également exporter une DAC.</span><span class="sxs-lookup"><span data-stu-id="d404e-121">Members of the sysadmin fixed server role or the built-in SQL Server system administrator account named **sa** can also export a DAC.</span></span>  
  
##  <a name="using-the-export-data-tier-application-wizard"></a><a name="UsingDeployDACWizard"></a><span data-ttu-id="d404e-122">Utilisation de l’Assistant Exporter l’application de la couche données</span><span class="sxs-lookup"><span data-stu-id="d404e-122">Using the Export Data-tier Application Wizard</span></span>  
 <span data-ttu-id="d404e-123">**Pour exporter une DAC à l'aide d'un Assistant**</span><span class="sxs-lookup"><span data-stu-id="d404e-123">**To Export a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="d404e-124">Connectez-vous à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], sur site ou dans [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d404e-124">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], whether on-premise or in [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span></span>  
  
2.  <span data-ttu-id="d404e-125">Dans l' **Explorateur d'objets**, développez le nœud de l'instance à partir de laquelle vous voulez exporter la DAC.</span><span class="sxs-lookup"><span data-stu-id="d404e-125">In **Object Explorer**, expand the node for the instance from which you want to export the DAC.</span></span>  
  
3.  <span data-ttu-id="d404e-126">Cliquez avec le bouton droit sur le nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="d404e-126">Right-click the database name.</span></span>  
  
4.  <span data-ttu-id="d404e-127">Cliquez sur **Tâches**, puis sélectionnez **Exporter une application de la couche Données...**</span><span class="sxs-lookup"><span data-stu-id="d404e-127">Click **Tasks** and then select **Export Data-tier Application...**</span></span>  
  
5.  <span data-ttu-id="d404e-128">Renseignez les boîtes de dialogue de l'Assistant :</span><span class="sxs-lookup"><span data-stu-id="d404e-128">Complete the wizard dialogs:</span></span>  
  
    -   [<span data-ttu-id="d404e-129">Page Introduction</span><span class="sxs-lookup"><span data-stu-id="d404e-129">Introduction Page</span></span>](#Introduction)  
  
    -   [<span data-ttu-id="d404e-130">Page Paramètres d'exportation</span><span class="sxs-lookup"><span data-stu-id="d404e-130">Export Settings Page</span></span>](#Export_settings)  
  
    -   [<span data-ttu-id="d404e-131">Page Validation</span><span class="sxs-lookup"><span data-stu-id="d404e-131">Validation Page</span></span>](#Validation)  
  
    -   [<span data-ttu-id="d404e-132">Page Résumé</span><span class="sxs-lookup"><span data-stu-id="d404e-132">Summary Page</span></span>](#Summary)  
  
    -   [<span data-ttu-id="d404e-133">Page progression</span><span class="sxs-lookup"><span data-stu-id="d404e-133">Progress Page</span></span>](#Progress)  
  
    -   [<span data-ttu-id="d404e-134">Page Résultats</span><span class="sxs-lookup"><span data-stu-id="d404e-134">Results Page</span></span>](#Results)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="d404e-135">Page Introduction</span><span class="sxs-lookup"><span data-stu-id="d404e-135">Introduction Page</span></span>  
 <span data-ttu-id="d404e-136">Cette page décrit les étapes de l'Assistant Exporter l'application de la couche Données.</span><span class="sxs-lookup"><span data-stu-id="d404e-136">This page describes the steps for the Export Data-tier Application Wizard.</span></span>  
  
 <span data-ttu-id="d404e-137">**Options**</span><span class="sxs-lookup"><span data-stu-id="d404e-137">**Options**</span></span>  
  
 <span data-ttu-id="d404e-138">**Ne plus afficher cette page.**</span><span class="sxs-lookup"><span data-stu-id="d404e-138">**Do not show this page again.**</span></span> <span data-ttu-id="d404e-139">- Activez la case à cocher pour ne plus afficher la page Introduction à l'avenir.</span><span class="sxs-lookup"><span data-stu-id="d404e-139">- Click the check box to stop the Introduction page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="d404e-140">**Suivant** - Passe à la page **Sélectionner le package DAC** .</span><span class="sxs-lookup"><span data-stu-id="d404e-140">**Next** - Proceeds to the **Select DAC Package** page.</span></span>  
  
 <span data-ttu-id="d404e-141">**Annuler** -annule l’opération et ferme l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="d404e-141">**Cancel** - Cancels the operation and closes the Wizard.</span></span>  
  
##  <a name="export-settings-page"></a><a name="Export_settings"></a><span data-ttu-id="d404e-142">Page Paramètres d’exportation</span><span class="sxs-lookup"><span data-stu-id="d404e-142">Export Settings Page</span></span>  
 <span data-ttu-id="d404e-143">Utilisez cette page pour indiquer l'emplacement où vous souhaitez créer le fichier BACPAC.</span><span class="sxs-lookup"><span data-stu-id="d404e-143">Use this page to specify the location where you want the BACPAC file to be created.</span></span>  
  
-   <span data-ttu-id="d404e-144">**Enregistrer sur le disque local** - Crée un fichier de BACPAC dans un répertoire sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="d404e-144">**Save to local disk** - Creates a BACPAC file in a directory on the local computer.</span></span> <span data-ttu-id="d404e-145">Cliquez sur **Parcourir...** pour explorer l’ordinateur local, ou spécifiez le chemin d’accès dans l’espace fourni.</span><span class="sxs-lookup"><span data-stu-id="d404e-145">Click **Browse...** to navigate the local computer, or specify the path in the space provided.</span></span> <span data-ttu-id="d404e-146">Le chemin d'accès doit inclure un nom de fichier et l'extension .bacpac.</span><span class="sxs-lookup"><span data-stu-id="d404e-146">The path name must include a file name and the .bacpac extension.</span></span>  
  
-   <span data-ttu-id="d404e-147">**Enregistrer dans Azure** - Crée un fichier BACPAC dans un conteneur Azure.</span><span class="sxs-lookup"><span data-stu-id="d404e-147">**Save to Azure** - Creates a BACPAC file in an Azure container.</span></span> <span data-ttu-id="d404e-148">Vous devez vous connecter à un conteneur Azure afin de valider cette option.</span><span class="sxs-lookup"><span data-stu-id="d404e-148">You must connect to an Azure container in order to validate this option.</span></span> <span data-ttu-id="d404e-149">Notez que cette option requiert également que vous spécifiiez un répertoire local pour le fichier temporaire.</span><span class="sxs-lookup"><span data-stu-id="d404e-149">Note that this option also requires that you specify a local directory for the temporary file.</span></span> <span data-ttu-id="d404e-150">Notez que le fichier temporaire est créé à l'emplacement spécifié et qu'il y reste une fois l'opération terminée.</span><span class="sxs-lookup"><span data-stu-id="d404e-150">Note that the temporary file will be created at the specified location and will remain there after the operation completes.</span></span>  
  
 <span data-ttu-id="d404e-151">Pour spécifier un sous-ensemble de tables à exporter, utilisez l'option **Avancé** .</span><span class="sxs-lookup"><span data-stu-id="d404e-151">To specify a subset of tables to export, use the **Advanced** option.</span></span>  
  
##  <a name="validation-page"></a><a name="Validation"></a><span data-ttu-id="d404e-152">Page validation</span><span class="sxs-lookup"><span data-stu-id="d404e-152">Validation Page</span></span>  
 <span data-ttu-id="d404e-153">Utilisez la page de validation pour passer en revue tous les problèmes qui empêchent l'opération.</span><span class="sxs-lookup"><span data-stu-id="d404e-153">Use the validation page to review any issues that block the operation.</span></span> <span data-ttu-id="d404e-154">Pour continuer, résolvez les problèmes bloquants, puis cliquez sur **Réexécuter la validation** pour vous assurer que la validation est réussie.</span><span class="sxs-lookup"><span data-stu-id="d404e-154">To continue, resolve blocking issues and then click **Re-run Validation** to ensure that validation is successful.</span></span>  
  
 <span data-ttu-id="d404e-155">Pour continuer, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d404e-155">To continue, click **Next**.</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="d404e-156">Page Résumé</span><span class="sxs-lookup"><span data-stu-id="d404e-156">Summary Page</span></span>  
 <span data-ttu-id="d404e-157">Utilisez cette page pour passer en revue la source spécifiée et les paramètres cibles de l'opération.</span><span class="sxs-lookup"><span data-stu-id="d404e-157">Use this page to review the specified source and target settings for the operation.</span></span> <span data-ttu-id="d404e-158">Pour terminer l'exportation à l'aide des paramètres spécifiés, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="d404e-158">To complete the export operation using the specified settings, click **Finish**.</span></span> <span data-ttu-id="d404e-159">Pour annuler l'exportation et quitter l'Assistant, cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="d404e-159">To cancel the export operation and exit the Wizard, click **Cancel**.</span></span>  
  
##  <a name="progress-page"></a><a name="Progress"></a> <span data-ttu-id="d404e-160">Page Progression</span><span class="sxs-lookup"><span data-stu-id="d404e-160">Progress Page</span></span>  
 <span data-ttu-id="d404e-161">Cette page affiche une barre de progression indiquant l'état de l'opération.</span><span class="sxs-lookup"><span data-stu-id="d404e-161">This page displays a progress bar that indicates the status of the operation.</span></span> <span data-ttu-id="d404e-162">Pour afficher l'état détaillé, cliquez sur l'option **Afficher les détails** .</span><span class="sxs-lookup"><span data-stu-id="d404e-162">To view detailed status, click the **View details** option.</span></span>  
  
##  <a name="results-page"></a><a name="Results"></a><span data-ttu-id="d404e-163">Page résultats</span><span class="sxs-lookup"><span data-stu-id="d404e-163">Results Page</span></span>  
 <span data-ttu-id="d404e-164">Cette page signale la réussite ou l'échec de l'exportation et affiche les résultats de chaque action.</span><span class="sxs-lookup"><span data-stu-id="d404e-164">This page reports the success or failure of the export operation, showing the results of each action.</span></span> <span data-ttu-id="d404e-165">Toute action pour laquelle une erreur s'est produite aura un lien dans la colonne **Résultat** .</span><span class="sxs-lookup"><span data-stu-id="d404e-165">Any action that encountered an error will have a link in the **Result** column.</span></span> <span data-ttu-id="d404e-166">Cliquez sur le lien pour consulter le rapport d'erreur de cette action.</span><span class="sxs-lookup"><span data-stu-id="d404e-166">Click the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="d404e-167">Cliquez sur **Terminer** pour fermer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="d404e-167">Click **Finish** to close the Wizard.</span></span>  
  
##  <a name="using-a-net-framework-application"></a><a name="NetApp"></a><span data-ttu-id="d404e-168">Utilisation d’une application .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d404e-168">Using a .Net Framework Application</span></span>  
 <span data-ttu-id="d404e-169">**Pour exporter une DAC à l’aide de la méthode Export() dans une application .Net Framework.**</span><span class="sxs-lookup"><span data-stu-id="d404e-169">**To export a DAC using the Export() method in a .Net Framework application.**</span></span>  
  
 <span data-ttu-id="d404e-170">Pour afficher un exemple de code, téléchargez l'exemple d'application DAC sur [Codeplex](https://go.microsoft.com/fwlink/?LinkId=219575)</span><span class="sxs-lookup"><span data-stu-id="d404e-170">To view a code example, download the DAC sample application on [Codeplex](https://go.microsoft.com/fwlink/?LinkId=219575)</span></span>  
  
1.  <span data-ttu-id="d404e-171">Créez un objet serveur SMO et définissez-le sur l'instance qui contient la DAC à exporter.</span><span class="sxs-lookup"><span data-stu-id="d404e-171">Create a SMO Server object and set it to the instance that contains the DAC to be exported.</span></span>  
  
2.  <span data-ttu-id="d404e-172">Ouvrez un objet `ServerConnection` et connectez-vous à la même instance.</span><span class="sxs-lookup"><span data-stu-id="d404e-172">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="d404e-173">Utilisez la méthode `Export` de type `Microsoft.SqlServer.Management.Dac.DacStore` pour exporter la DAC.</span><span class="sxs-lookup"><span data-stu-id="d404e-173">Use the `Export` method of the `Microsoft.SqlServer.Management.Dac.DacStore` type to export the DAC.</span></span> <span data-ttu-id="d404e-174">Spécifiez le nom de la DAC à exporter, ainsi que le chemin d'accès au dossier où le fichier d'exportation doit être placé.</span><span class="sxs-lookup"><span data-stu-id="d404e-174">Specify the name of the DAC to be exported, and the path to the folder where the export file is to be placed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d404e-175">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d404e-175">See Also</span></span>  
 <span data-ttu-id="d404e-176">[Applications de la couche Données](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="d404e-176">[Data-tier Applications](data-tier-applications.md) </span></span>  
 [<span data-ttu-id="d404e-177">Extraire une DAC d’une base de données</span><span class="sxs-lookup"><span data-stu-id="d404e-177">Extract a DAC From a Database</span></span>](extract-a-dac-from-a-database.md)  
  
  
