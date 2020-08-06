---
title: Taraudage de données | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 2d847adf-4b3d-4949-a195-ef43de275077
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 053b34add45354d0df71fa73a72f8786cc706d15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697036"
---
# <a name="data-flow-taps"></a><span data-ttu-id="c4551-102">Drainage des flux de données</span><span class="sxs-lookup"><span data-stu-id="c4551-102">Data Flow Taps</span></span>
  [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] <span data-ttu-id="c4551-103">introduit une nouvelle fonctionnalité qui vous permet d'ajouter un drainage des données au niveau du chemin d'accès d'un flux de données d'un package au moment de l'exécution et diriger la sortie à partir du drainage des données vers un fichier externe.</span><span class="sxs-lookup"><span data-stu-id="c4551-103">introduces a new feature that allows you to add a data tap on a data flow path of a package at runtime and direct the output from the data tap to an external file.</span></span> <span data-ttu-id="c4551-104">Pour utiliser cette fonctionnalité, vous devez déployer votre projet SSIS à l'aide du modèle de déploiement de projet sur un serveur SSIS.</span><span class="sxs-lookup"><span data-stu-id="c4551-104">To use this feature, you must deploy your SSIS project using the project deployment model to an SSIS Server.</span></span> <span data-ttu-id="c4551-105">Après avoir déployé le package sur le serveur, vous devez exécuter des scripts T-SQL sur la base de données SSISDB pour ajouter des drainages de données avant d'exécuter le package.</span><span class="sxs-lookup"><span data-stu-id="c4551-105">After you deploy the package to the server, you need to execute T-SQL scripts against the SSISDB database to add data taps before executing the package.</span></span> <span data-ttu-id="c4551-106">Voici un exemple de scénario :</span><span class="sxs-lookup"><span data-stu-id="c4551-106">Here is a sample scenario:</span></span>  
  
1.  <span data-ttu-id="c4551-107">Créez une instance d’exécution d’un package à l’aide de la procédure stockée [catalog.create_execution &#40;base de données SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="c4551-107">Create an execution instance of a package by using the [catalog.create_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database) stored procedure.</span></span>  
  
2.  <span data-ttu-id="c4551-108">Ajoutez un drainage de données à l’aide d’une procédure stockée [catalog.add_data_tap](/sql/integration-services/system-stored-procedures/catalog-add-data-tap) ou [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid) .</span><span class="sxs-lookup"><span data-stu-id="c4551-108">Add a data tap by using either [catalog.add_data_tap](/sql/integration-services/system-stored-procedures/catalog-add-data-tap) or [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid) stored procedure.</span></span>  
  
3.  <span data-ttu-id="c4551-109">Démarrez l’instance d’exécution du package à l’aide de [catalog.start_execution &#40;base de données SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="c4551-109">Start the execution instance of the package by using the [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span></span>  
  
 <span data-ttu-id="c4551-110">Voici un exemple de script SQL qui exécute les étapes décrites dans le scénario ci-dessus :</span><span class="sxs-lookup"><span data-stu-id="c4551-110">Here is a sample SQL script that performs the steps described in the above scenario:</span></span>  
  
```  
  
Declare @execid bigint  
EXEC [SSISDB].[catalog].[create_execution] @folder_name=N'ETL Folder', @project_name=N'ETL Project', @package_name=N'Package.dtsx', @execution_id=@execid OUTPUT  
EXEC [SSISDB].[catalog].add_data_tap @execution_id = @execid, @task_package_path = '\Package\Data Flow Task', @dataflow_path_id_string = 'Paths[Flat File Source.Flat File Source Output]', @data_filename = 'output.txt'  
EXEC [SSISDB].[catalog].[start_execution] @execid  
  
```  
  
 <span data-ttu-id="c4551-111">Les paramètres folder_name, project_name et package_name de la procédure stockée create_execution correspondent au dossier, au projet et au package dans le catalogue Integration Services.</span><span class="sxs-lookup"><span data-stu-id="c4551-111">The folder name, project name, and package name parameters of the create_execution stored procedure correspond to the folder, project, and package names in the Integration Services catalog.</span></span> <span data-ttu-id="c4551-112">Vous pouvez obtenir les noms de dossier, projet et package à utiliser dans l'appel de create_execution dans SQL Server Management Studio comme le montre l'image suivante.</span><span class="sxs-lookup"><span data-stu-id="c4551-112">You can get the folder, project, and package names to use in the create_execution call from the SQL Server Management Studio as shown in the following image.</span></span> <span data-ttu-id="c4551-113">Si le projet SSIS ne s'affiche pas ici, vous n'avez peut-être pas encore déployé le projet sur le serveur SSIS.</span><span class="sxs-lookup"><span data-stu-id="c4551-113">If you do not see your SSIS project here, you may not have deployed the project to SSIS server yet.</span></span> <span data-ttu-id="c4551-114">Cliquez avec le bouton droit sur le projet SSIS dans Visual Studio, puis cliquez sur Déployer pour déployer le projet sur le serveur SSIS prévu.</span><span class="sxs-lookup"><span data-stu-id="c4551-114">Right-click on SSIS project in Visual Studio and click Deploy to deploy the project to the expected SSIS server.</span></span>  
  
 <span data-ttu-id="c4551-115">Au lieu de taper des instructions SQL, générez le script d'exécution de package en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="c4551-115">Instead of typing the SQL statements, you can generate the execute package script by performing the following steps:</span></span>  
  
1.  <span data-ttu-id="c4551-116">Cliquez avec le bouton droit sur **Package.dtsx** , puis sélectionnez **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c4551-116">Right-click **Package.dtsx** and click **Execute**.</span></span>  
  
2.  <span data-ttu-id="c4551-117">Cliquez sur le bouton de la barre d'outils **Script** pour générer le script.</span><span class="sxs-lookup"><span data-stu-id="c4551-117">Click **Script** toolbar button to generate the script.</span></span>  
  
3.  <span data-ttu-id="c4551-118">Ajoutez l'instruction add_data_tap avant l'appel de start_execution.</span><span class="sxs-lookup"><span data-stu-id="c4551-118">Now, add the add_data_tap statement before the start_execution call.</span></span>  
  
 <span data-ttu-id="c4551-119">Le paramètre task_package_path de la procédure stockée add_data_tap correspond à la propriété PackagePath de la tâche de flux de données dans Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c4551-119">The task_package_path parameter of add_data_tap stored procedure corresponds to the PackagePath property of the data flow task in Visual Studio.</span></span> <span data-ttu-id="c4551-120">Dans Visual Studio, cliquez avec le bouton droit sur **Tâche de flux de données**, puis cliquez sur **Propriétés** pour lancer la fenêtre Propriétés.</span><span class="sxs-lookup"><span data-stu-id="c4551-120">In Visual Studio, right-click the **Data Flow Task**, and click **Properties** to launch the Properties window.</span></span>  <span data-ttu-id="c4551-121">Notez la valeur de la propriété **PackagePath** pour l’utiliser comme valeur du paramètre task_package_path de l’appel de procédure stockée add_data_tap.</span><span class="sxs-lookup"><span data-stu-id="c4551-121">Note the value of the **PackagePath** property to use it as a value for the task_package_path parameter for add_data_tap stored procedure call.</span></span>  
  
 <span data-ttu-id="c4551-122">Le paramètre dataflow_path_id_string de la procédure stockée add_data_tap correspond à la propriété IdentificationString du chemin d'accès de flux de données auquel vous voulez ajouter un drainage de données.</span><span class="sxs-lookup"><span data-stu-id="c4551-122">The dataflow_path_id_string  parameter of add_data_tap stored procedure corresponds to the IdentificationString property of the data flow path to which you want to add a data tap.</span></span> <span data-ttu-id="c4551-123">Pour obtenir dataflow_path_id_string, cliquez sur le chemin de flux de données (flèche entre les tâches du flux de données), et notez la valeur de la propriété **IdentificationString** dans la fenêtre Propriétés.</span><span class="sxs-lookup"><span data-stu-id="c4551-123">To get the dataflow_path_id_string, click the data flow path (arrow between tasks in the data flow), and note the value of the **IdentificationString** property in the Properties window.</span></span>  
  
 <span data-ttu-id="c4551-124">Quand vous exécutez le script, le fichier de sortie est stocké dans \<Program Files>\Microsoft SQL Server\110\DTS\DataDumps.</span><span class="sxs-lookup"><span data-stu-id="c4551-124">When you execute the script, the output file is stored in \<Program Files>\Microsoft SQL Server\110\DTS\DataDumps.</span></span> <span data-ttu-id="c4551-125">S'il existe déjà un fichier du même nom, un nouveau fichier avec un suffixe (par exemple : output[1].txt) est créé.</span><span class="sxs-lookup"><span data-stu-id="c4551-125">If a file with the name already exists, a new file with a suffix (for example: output[1].txt)  is created.</span></span>  
  
 <span data-ttu-id="c4551-126">Comme mentionné précédemment, vous pouvez également utiliser la procédure stockée [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid)plutôt que add_data_tap.</span><span class="sxs-lookup"><span data-stu-id="c4551-126">As mentioned earlier, you can also use [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid)stored procedure instead of using add_data_tap stored procedure.</span></span> <span data-ttu-id="c4551-127">Cette procédure stockée accepte l'ID de tâche de flux de données comme paramètre au lieu de task_package_path.</span><span class="sxs-lookup"><span data-stu-id="c4551-127">This stored procedure takes the ID of data flow task as a parameter instead of task_package_path.</span></span> <span data-ttu-id="c4551-128">L'ID de tâche de flux de données est disponible dans la fenêtre Propriétés de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c4551-128">You can get the ID of data flow task from the properties window in Visual Studio.</span></span>  
  
## <a name="removing-a-data-tap"></a><span data-ttu-id="c4551-129">Suppression d'un drainage de données</span><span class="sxs-lookup"><span data-stu-id="c4551-129">Removing a data tap</span></span>  
 <span data-ttu-id="c4551-130">Vous pouvez supprimer un drainage de données avant de lancer l’exécution à l’aide de la procédure stockée [catalog.remove_data_tap](/sql/integration-services/system-stored-procedures/catalog-remove-data-tap) .</span><span class="sxs-lookup"><span data-stu-id="c4551-130">You can remove a data tap before starting the execution by using the [catalog.remove_data_tap](/sql/integration-services/system-stored-procedures/catalog-remove-data-tap) stored procedure.</span></span> <span data-ttu-id="c4551-131">Cette procédure stockée accepte l'ID de drainage de données comme paramètre, que vous pouvez obtenir en tant que résultat de la procédure stockée add_data_tap.</span><span class="sxs-lookup"><span data-stu-id="c4551-131">This stored procedure takes the ID of data tap as a parameter, which you can get as an output of the add_data_tap stored procedure.</span></span>  
  
```  
  
DECLARE @tap_id bigint  
EXEC [SSISDB].[catalog].add_data_tap @execution_id = @execid, @task_package_path = '\Package\Data Flow Task', @dataflow_path_id_string = 'Paths[Flat File Source.Flat File Source Output]', @data_filename = 'output.txt' @data_tap_id=@tap_id OUTPUT  
EXEC [SSISDB].[catalog].remove_data_tap @tap_id  
  
```  
  
## <a name="listing-all-data-taps"></a><span data-ttu-id="c4551-132">Création de la liste de tous les drainages de données</span><span class="sxs-lookup"><span data-stu-id="c4551-132">Listing all data taps</span></span>  
 <span data-ttu-id="c4551-133">Vous pouvez également afficher la liste de tous les drainages de données à l'aide de l'affichage catalog.execution_data_taps.</span><span class="sxs-lookup"><span data-stu-id="c4551-133">You can also list all the data taps by using the catalog.execution_data_taps view.</span></span> <span data-ttu-id="c4551-134">Cet exemple extrait les drainages de données pour une instance d'exécution de spécification (ID : 54).</span><span class="sxs-lookup"><span data-stu-id="c4551-134">The following example extracts data taps for a specification execution instance (ID: 54).</span></span>  
  
```  
select * from [SSISDB].[catalog].execution_data_taps where execution_id=@execid  
```  
  
## <a name="performance-consideration"></a><span data-ttu-id="c4551-135">Observation relative aux performances</span><span class="sxs-lookup"><span data-stu-id="c4551-135">Performance consideration</span></span>  
 <span data-ttu-id="c4551-136">Le fait d'activer le niveau de journalisation détaillée et d'ajouter des drainages de données augmente les opérations d'E/S effectuées par votre solution d'intégration de données.</span><span class="sxs-lookup"><span data-stu-id="c4551-136">Enabling verbose logging level and adding data taps increase the I/O operations performed by your data integration solution.</span></span> <span data-ttu-id="c4551-137">Par conséquent, il est recommandé d'ajouter des drainages de données uniquement à des fins de dépannage.</span><span class="sxs-lookup"><span data-stu-id="c4551-137">Hence, we recommend that you add data taps only for troubleshooting purposes</span></span>  
  
## <a name="video"></a><span data-ttu-id="c4551-138">Vidéo</span><span class="sxs-lookup"><span data-stu-id="c4551-138">Video</span></span>  
 <span data-ttu-id="c4551-139">Cette [vidéo sur TechNet](https://technet.microsoft.com/sqlserver/dn600163) montre comment ajouter/utiliser des drainages de données dans le catalogue SQL Server 2012 SSISDB qui permettent de déboguer des packages par programmation et de capturer les résultats partiels au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="c4551-139">This [video on TechNet](https://technet.microsoft.com/sqlserver/dn600163) demonstrates how to add/use data taps in SQL Server 2012 SSISDB catalog that help with debugging packages programmatically and capturing the partial results at the runtime.</span></span> <span data-ttu-id="c4551-140">Elle explique également comment répertorier/supprimer ces drainages de données et les meilleures pratiques pour l'utilisation des drainages de données dans des packages SSIS.</span><span class="sxs-lookup"><span data-stu-id="c4551-140">It also discusses how to list/ remove these data taps and best practices for using data taps in SSIS packages.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="c4551-141">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="c4551-141">Related Tasks</span></span>  
 [<span data-ttu-id="c4551-142">Débogage d’un flux de données</span><span class="sxs-lookup"><span data-stu-id="c4551-142">Debugging Data Flow</span></span>](troubleshooting/debugging-data-flow.md)  
  
 [<span data-ttu-id="c4551-143">Outils de dépannage pour l’exécution des packages</span><span class="sxs-lookup"><span data-stu-id="c4551-143">Troubleshooting Tools for Package Execution</span></span>](troubleshooting/troubleshooting-tools-for-package-execution.md)  
  
  
