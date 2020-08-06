---
title: Déployer et exécuter des packages SSIS à l’aide de procédures stockées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 60914b0c-1f65-45f8-8132-0ca331749fcc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1570207dca6e944b54c553a1d83256d8f4fa3244
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707687"
---
# <a name="deploy-and-execute-ssis-packages-using-stored-procedures"></a><span data-ttu-id="6df30-102">Déployer et exécuter des packages SSIS à l'aide de procédures stockées</span><span class="sxs-lookup"><span data-stu-id="6df30-102">Deploy and Execute SSIS Packages using Stored Procedures</span></span>
  <span data-ttu-id="6df30-103">Lorsque vous configurez un projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] afin d'utiliser le modèle de déploiement de projet, vous pouvez utiliser les procédures stockées du catalogue [!INCLUDE[ssIS](../includes/ssis-md.md)] pour déployer le projet et pour exécuter des packages.</span><span class="sxs-lookup"><span data-stu-id="6df30-103">When you configure an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to use the project deployment model, you can use stored procedures in the [!INCLUDE[ssIS](../includes/ssis-md.md)] catalog to deploy the project and execute the packages.</span></span> <span data-ttu-id="6df30-104">Pour plus d’informations sur le modèle de déploiement de projet, consultez [Déploiement de projets et de packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="6df30-104">For information about the project deployment model, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="6df30-105">Vous pouvez également utiliser [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] pour déployer le projet et pour exécuter des packages.</span><span class="sxs-lookup"><span data-stu-id="6df30-105">You can also use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to deploy the project and execute the packages.</span></span> <span data-ttu-id="6df30-106">Pour plus d’informations, consultez les rubriques de la section **Voir aussi** .</span><span class="sxs-lookup"><span data-stu-id="6df30-106">For more information, see the topics in the **See Also** section.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="6df30-107">Vous pouvez facilement créer des instructions Transact-SQL pour les procédures stockées répertoriées dans la procédure ci-dessous, à l'exception de catalog.deploy_project, en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="6df30-107">You can easily generate the Transact-SQL statements for the stored procedures listed in the procedure below, with the exception of catalog.deploy_project, by doing the following:</span></span>  
> 
>  1.  <span data-ttu-id="6df30-108">Dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], développez le nœud **Catalogues Integration Services** dans l’Explorateur d’objets et accédez au package à exécuter.</span><span class="sxs-lookup"><span data-stu-id="6df30-108">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expand the **Integration Services Catalogs** node in Object Explorer and navigate to the package you want to execute.</span></span>  
> 2.  <span data-ttu-id="6df30-109">Cliquez avec le bouton droit sur le package, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="6df30-109">Right-click the package, and then click **Execute**.</span></span>  
> 3.  <span data-ttu-id="6df30-110">Si nécessaire, définissez les valeurs des paramètres, les propriétés du gestionnaire de connexions, ainsi que les options de l’onglet **Avancé** , telles que le niveau de journalisation.</span><span class="sxs-lookup"><span data-stu-id="6df30-110">As needed, set parameters values, connection manager properties, and options in the **Advanced** tab such as the logging level.</span></span>  
> 
>      <span data-ttu-id="6df30-111">Pour plus d’informations sur les niveaux de journalisation, consultez [Activer la journalisation des exécutions de package sur le serveur SSIS](../../2014/integration-services/enable-logging-for-package-execution-on-the-ssis-server.md).</span><span class="sxs-lookup"><span data-stu-id="6df30-111">For more information about logging levels, see [Enable Logging for Package Execution on the SSIS Server](../../2014/integration-services/enable-logging-for-package-execution-on-the-ssis-server.md).</span></span>  
> 4.  <span data-ttu-id="6df30-112">Avant de cliquer sur **OK** pour exécuter le package, cliquez sur **Script**.</span><span class="sxs-lookup"><span data-stu-id="6df30-112">Before clicking **OK** to execute the package, click **Script**.</span></span> <span data-ttu-id="6df30-113">Transact-SQL s’affiche dans une fenêtre de l’Éditeur de requête dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6df30-113">The Transact-SQL appears in a Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="to-deploy-and-execute-a-package-using-stored-procedures"></a><span data-ttu-id="6df30-114">Pour déployer et exécuter un package à l'aide de procédures stockées</span><span class="sxs-lookup"><span data-stu-id="6df30-114">To deploy and execute a package using stored procedures</span></span>  
  
1.  <span data-ttu-id="6df30-115">Appelez [catalog.deploy_project &#40;base de données SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database) pour déployer le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] qui contient le package sur le serveur [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6df30-115">Call [catalog.deploy_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database) to deploy the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="6df30-116">Pour récupérer le contenu binaire du [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] fichier de déploiement de projet, pour le paramètre \* \@ project_stream\* , utilisez une instruction SELECT avec la fonction OPENROWSET et le fournisseur d’ensembles de lignes en bloc.</span><span class="sxs-lookup"><span data-stu-id="6df30-116">To retrieve the binary contents of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project deployment file, for the *\@project_stream* parameter, use a SELECT statement with the OPENROWSET function and the BULK rowset provider.</span></span> <span data-ttu-id="6df30-117">Le fournisseur d'ensembles de lignes BULK vous permet de lire des données dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="6df30-117">The BULK rowset provider enables you to read data from a file.</span></span> <span data-ttu-id="6df30-118">L'argument SINGLE_BLOB du fournisseur d'ensembles de lignes BULK retourne le contenu du fichier de données sous la forme d'un ensemble de lignes à une seule ligne, une seule colonne de type varbinary (max).</span><span class="sxs-lookup"><span data-stu-id="6df30-118">The SINGLE_BLOB argument for the BULK rowset provider returns the contents of the data file as a single-row, single-column rowset of type varbinary(max).</span></span> <span data-ttu-id="6df30-119">Pour plus d’informations, consultez [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6df30-119">For more information, see [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
     <span data-ttu-id="6df30-120">Dans l’exemple suivant, le projet SSISPackages_ProjectDeployment est déployé dans le dossier SSIS Packages sur le serveur [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6df30-120">In the following example, the SSISPackages_ProjectDeployment project is deployed to the SSIS Packages folder on the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="6df30-121">Les données binaires sont lues à partir du fichier projet (SSISPackage_ProjectDeployment. ISPAC) et sont stockées dans le paramètre \* \@ ProjectBinary\* de type varbinary (max).</span><span class="sxs-lookup"><span data-stu-id="6df30-121">The binary data is read from the project file (SSISPackage_ProjectDeployment.ispac) and is stored in the *\@ProjectBinary* parameter of type varbinary(max).</span></span> <span data-ttu-id="6df30-122">La valeur du paramètre \* \@ ProjectBinary\* est assignée au paramètre \* \@ project_stream\* .</span><span class="sxs-lookup"><span data-stu-id="6df30-122">The *\@ProjectBinary* parameter value is assigned to the *\@project_stream* parameter.</span></span>  
  
    ```  
    DECLARE @ProjectBinary as varbinary(max)  
    DECLARE @operation_id as bigint  
    Set @ProjectBinary = (SELECT * FROM OPENROWSET(BULK 'C:\MyProjects\ SSISPackage_ProjectDeployment.ispac', SINGLE_BLOB) as BinaryData)  
  
    Exec catalog.deploy_project @folder_name = 'SSIS Packages', @project_name = 'DeployViaStoredProc_SSIS', @Project_Stream = @ProjectBinary, @operation_id = @operation_id out  
  
    ```  
  
2.  <span data-ttu-id="6df30-123">Appelez [catalog.create_execution &#40; base de données SSISDB &#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database) pour créer une instance de l’exécution du package et éventuellement [catalog.set_execution_parameter_value &#40;base de données SSISDB &#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database) pour définir les valeurs de paramètres d’exécution.</span><span class="sxs-lookup"><span data-stu-id="6df30-123">Call [catalog.create_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database) to create an instance of the package execution, and optionally call [catalog.set_execution_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database) to set runtime parameter values.</span></span>  
  
     <span data-ttu-id="6df30-124">Dans l'exemple suivant, catalog.create_execution crée une instance d'exécution pour le fichier package.dtsx contenu dans le projet SSISPackage_ProjectDeployment.</span><span class="sxs-lookup"><span data-stu-id="6df30-124">In the following example, catalog.create_execution creates an instance of execution for package.dtsx that is contained in the SSISPackage_ProjectDeployment project.</span></span> <span data-ttu-id="6df30-125">Le projet se trouve dans le dossier SSIS Packages.</span><span class="sxs-lookup"><span data-stu-id="6df30-125">The project is located in the SSIS Packages folder.</span></span> <span data-ttu-id="6df30-126">L'execution_id retourné par la procédure stockée est utilisé dans l'appel à catalog.set_execution_parameter_value.</span><span class="sxs-lookup"><span data-stu-id="6df30-126">The execution_id returned by the stored procedure is used in the call to catalog.set_execution_parameter_value.</span></span> <span data-ttu-id="6df30-127">Cette deuxième procédure stockée attribue au paramètre LOGGING_LEVEL la valeur 3 (journalisation verbose) et attribue à un paramètre de package nommé Parameter1 la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="6df30-127">This second stored procedure sets the LOGGING_LEVEL parameter to 3 (verbose logging) and sets a package parameter named Parameter1 to a value of 1.</span></span>  
  
     <span data-ttu-id="6df30-128">Pour les paramètres tels que LOGGING_LEVEL la valeur d'object_type est 50.</span><span class="sxs-lookup"><span data-stu-id="6df30-128">For parameters such as LOGGING_LEVEL the object_type value is 50.</span></span> <span data-ttu-id="6df30-129">Pour les paramètres de package la valeur d'object_type est 30.</span><span class="sxs-lookup"><span data-stu-id="6df30-129">For package parameters the object_type value is 30.</span></span>  
  
    ```  
    Declare @execution_id bigint  
    EXEC [SSISDB].[catalog].[create_execution] @package_name=N'Package.dtsx', @execution_id=@execution_id OUTPUT, @folder_name=N'SSIS Packages', @project_name=N'SSISPackage_ProjectDeployment', @use32bitruntime=False, @reference_id=1  
  
    Select @execution_id  
    DECLARE @var0 smallint = 3  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=50, @parameter_name=N'LOGGING_LEVEL', @parameter_value=@var0  
  
    DECLARE @var1 int = 1  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=30, @parameter_name=N'Parameter1', @parameter_value=@var1  
  
    GO  
  
    ```  
  
3.  <span data-ttu-id="6df30-130">Appelez [catalog.start_execution &#40;base de données SSISDB &#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) pour exécuter le package.</span><span class="sxs-lookup"><span data-stu-id="6df30-130">Call [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) to execute the package.</span></span>  
  
     <span data-ttu-id="6df30-131">Dans l'exemple suivant, un appel à catalog.start_execution est ajouté à Transact-SQL pour démarrer l'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="6df30-131">In the following example, a call to catalog.start_execution is added to the Transact-SQL to start the package execution.</span></span> <span data-ttu-id="6df30-132">L'execution_id retourné par la procédure stockée catalog.create_execution est utilisé.</span><span class="sxs-lookup"><span data-stu-id="6df30-132">The execution_id returned by the catalog.create_execution stored procedure is used.</span></span>  
  
    ```  
    Declare @execution_id bigint  
    EXEC [SSISDB].[catalog].[create_execution] @package_name=N'Package.dtsx', @execution_id=@execution_id OUTPUT, @folder_name=N'SSIS Packages', @project_name=N'SSISPackage_ProjectDeployment', @use32bitruntime=False, @reference_id=1  
  
    Select @execution_id  
    DECLARE @var0 smallint = 3  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=50, @parameter_name=N'LOGGING_LEVEL', @parameter_value=@var0  
  
    DECLARE @var1 int = 1  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=30, @parameter_name=N'Parameter1', @parameter_value=@var1  
  
    EXEC [SSISDB].[catalog].[start_execution] @execution_id  
    GO  
  
    ```  
  
## <a name="to-deploy-a-project-from-server-to-server-using-stored-procedures"></a><span data-ttu-id="6df30-133">Pour déployer un projet de serveur à serveur à l'aide de procédures stockées</span><span class="sxs-lookup"><span data-stu-id="6df30-133">To deploy a project from server to server using stored procedures</span></span>  
 <span data-ttu-id="6df30-134">Vous pouvez déployer un projet de serveur à serveur à l’aide des procédures stockées [catalog.get_project &#40;base de données SSISDB &#41;](/sql/integration-services/system-stored-procedures/catalog-get-project-ssisdb-database) et [catalog.deploy_project &#40;base de données SSISDB &#41;](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="6df30-134">You can deploy a project from server to server by using the [catalog.get_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-get-project-ssisdb-database) and [catalog.deploy_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database) stored procedures.</span></span>  
  
 <span data-ttu-id="6df30-135">Vous devez effectuer les opérations suivantes avant d'exécuter les procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="6df30-135">You need to do the following before running the stored procedures.</span></span>  
  
-   <span data-ttu-id="6df30-136">Créez un objet serveur lié.</span><span class="sxs-lookup"><span data-stu-id="6df30-136">Create a linked server object.</span></span> <span data-ttu-id="6df30-137">Pour plus d’informations, consultez [Créer des serveurs liés &#40;moteur de base de données SQL Server&#41;](../database-engine/sql-server-database-engine-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6df30-137">For more information, see [Create Linked Servers &#40;SQL Server Database Engine&#41;](../database-engine/sql-server-database-engine-overview.md).</span></span>  
  
     <span data-ttu-id="6df30-138">Dans la page **Options du serveur** de la boîte de dialogue **Propriétés du serveur lié** , attribuez à **RPC** et à **Sortie RPC** la valeur **True**.</span><span class="sxs-lookup"><span data-stu-id="6df30-138">On the **Server Options** page of the **Linked Server Properties** dialog box, set **RPC** and **RPC Out** to **True**.</span></span> <span data-ttu-id="6df30-139">Par ailleurs, attribuez à **Activer la promotion des transactions distribuées pour RPC** la valeur **False**.</span><span class="sxs-lookup"><span data-stu-id="6df30-139">Also, set **Enable Promotion of Distributed Transactions for RPC** to **False**.</span></span>  
  
-   <span data-ttu-id="6df30-140">Vérifiez les paramètres dynamiques du fournisseur que vous avez sélectionné pour le serveur lié : développez le nœud **Fournisseurs** sous **Serveurs liés** dans l’Explorateur d’objets, puis cliquez avec le bouton droit sur le fournisseur et cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="6df30-140">Enable dynamic parameters for the provider you selected for the linked server, by expanding the **Providers** node under **Linked Servers** in Object Explorer, right-clicking the provider, and then clicking **Properties**.</span></span> <span data-ttu-id="6df30-141">Sélectionnez **Activer** en regard de **Paramètre dynamique**.</span><span class="sxs-lookup"><span data-stu-id="6df30-141">Select **Enable** next to **Dynamic parameter.**</span></span>  
  
-   <span data-ttu-id="6df30-142">Vérifiez que le Coordinateur de transactions distribuées (DTC, Distributed Transaction Coordinator) est démarré sur les deux serveurs.</span><span class="sxs-lookup"><span data-stu-id="6df30-142">Confirm that the Distributed Transaction Coordinator (DTC) is started on both servers.</span></span>  
  
 <span data-ttu-id="6df30-143">Appelez catalog.get_project pour retourner les données binaires du projet, puis appelez catalog.deploy_project.</span><span class="sxs-lookup"><span data-stu-id="6df30-143">Call catalog.get_project to return the binary for the project, and then call catalog.deploy_project.</span></span> <span data-ttu-id="6df30-144">La valeur retournée par catalog.get_project est insérée dans une variable de table de type varbinary (max).</span><span class="sxs-lookup"><span data-stu-id="6df30-144">The value returned by catalog.get_project is inserted into a table variable of type varbinary(max).</span></span> <span data-ttu-id="6df30-145">Le serveur lié ne peut pas retourner des résultats qui sont varbinary (max).</span><span class="sxs-lookup"><span data-stu-id="6df30-145">The linked server can't return results that are varbinary(max).</span></span>  
  
 <span data-ttu-id="6df30-146">Dans l'exemple suivant, catalog.get_project retourne une valeur binaire pour le projet SSISPackages sur le serveur lié.</span><span class="sxs-lookup"><span data-stu-id="6df30-146">In the following example, catalog.get_project returns a binary for the SSISPackages project on the linked server.</span></span> <span data-ttu-id="6df30-147">catalog.deploy_project déploie le projet sur le serveur local, dans un dossier nommé DestFolder.</span><span class="sxs-lookup"><span data-stu-id="6df30-147">The catalog.deploy_project deploys the project to the local server, to the folder named DestFolder.</span></span>  
  
```  
declare @resultsTableVar table (  
project_binary varbinary(max)  
)  
  
INSERT @resultsTableVar (project_binary)  
EXECUTE [MyLinkedServer].[SSISDB].[catalog].[get_project] 'Packages', 'SSISPackages'  
  
declare @project_binary varbinary(max)  
select @project_binary = project_binary from @resultsTableVar  
  
exec [SSISDB].[CATALOG].[deploy_project] 'DestFolder', 'SSISPackages', @project_binary  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="6df30-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6df30-148">See Also</span></span>  
 <span data-ttu-id="6df30-149">[Déployer des projets sur Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span><span class="sxs-lookup"><span data-stu-id="6df30-149">[Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span></span>  
 <span data-ttu-id="6df30-150">[Exécuter un package dans SQL Server Data Tools](../../2014/integration-services/run-a-package-in-sql-server-data-tools.md) </span><span class="sxs-lookup"><span data-stu-id="6df30-150">[Run a Package in SQL Server Data Tools](../../2014/integration-services/run-a-package-in-sql-server-data-tools.md) </span></span>  
 [<span data-ttu-id="6df30-151">Exécuter un package sur le serveur SSIS à l’aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6df30-151">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md)  
  
  
