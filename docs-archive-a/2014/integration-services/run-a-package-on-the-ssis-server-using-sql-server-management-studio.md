---
title: Exécuter un package sur le serveur SSIS à l’aide de SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 56dc1bf8-99d4-41dc-bdc4-f64f1ccfd688
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d17009988dea54621d4fd7ef542cf452bfe95c6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696919"
---
# <a name="run-a-package-on-the-ssis-server-using-sql-server-management-studio"></a><span data-ttu-id="4070e-102">Exécuter un package sur le serveur SSIS à l’aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4070e-102">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>
  <span data-ttu-id="4070e-103">Après avoir déployé votre projet sur le serveur [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , vous pouvez exécuter le package sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="4070e-103">After you deploy your project to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, you can run the package on the server.</span></span>  
  
 <span data-ttu-id="4070e-104">Vous pouvez utiliser des rapports d'opérations pour afficher des informations sur les packages qui ont été exécutés, ou qui sont actuellement exécutés, sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="4070e-104">You can use operations reports to view information about packages that have run, or are currently running, on the server.</span></span> <span data-ttu-id="4070e-105">Pour plus d'informations, consultez [Reports for the Integration Services Server](../../2014/integration-services/reports-for-the-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="4070e-105">For more information, see [Reports for the Integration Services Server](../../2014/integration-services/reports-for-the-integration-services-server.md).</span></span>  
  
### <a name="to-run-a-package-on-the-server-using-sql-server-management-studio"></a><span data-ttu-id="4070e-106">Pour exécuter un package sur le serveur à l'aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4070e-106">To run a package on the server using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="4070e-107">Ouvrez [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] et connectez-vous à l'instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] qui contient le catalogue [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4070e-107">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that contains the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog.</span></span>  
  
2.  <span data-ttu-id="4070e-108">Dans l’Explorateur d’objets, développez le nœud **Catalogues Integration Services** , développez le nœud **SSISDB** , puis accédez au package contenu dans le projet que vous avez déployé.</span><span class="sxs-lookup"><span data-stu-id="4070e-108">In Object Explorer, expand the **Integration Services Catalogs** node, expand the **SSISDB** node, and navigate to the package contained in the project you deployed.</span></span>  
  
3.  <span data-ttu-id="4070e-109">Cliquez avec le bouton droit sur le nom du package, puis sélectionnez **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="4070e-109">Right-click the package name and select **Execute**.</span></span>  
  
4.  <span data-ttu-id="4070e-110">Configurez l’exécution du package à l’aide des paramètres sous les onglets **Paramètres**, **Gestionnaires de connexions**et **Avancé** de la boîte de dialogue **Exécuter le package** .</span><span class="sxs-lookup"><span data-stu-id="4070e-110">Configure the package execution by using the settings on the **Parameters**, **Connection Managers**, and **Advanced** tabs in the **Execute Package** dialog box.</span></span>  
  
5.  <span data-ttu-id="4070e-111">Cliquez sur **OK** pour exécuter le package.</span><span class="sxs-lookup"><span data-stu-id="4070e-111">Click **OK** to run the package.</span></span>  
  
     <span data-ttu-id="4070e-112">-ou-</span><span class="sxs-lookup"><span data-stu-id="4070e-112">-or-</span></span>  
  
     <span data-ttu-id="4070e-113">Utilisez des procédures stockées pour exécuter le package.</span><span class="sxs-lookup"><span data-stu-id="4070e-113">Use stored procedures to run the package.</span></span> <span data-ttu-id="4070e-114">Cliquez sur **Script** pour générer l’instruction Transact-SQL qui crée et démarre une instance de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="4070e-114">Click **Script** to generate the Transact-SQL statement that creates an instance of the execution and starts an instance of the execution.</span></span> <span data-ttu-id="4070e-115">L'instruction inclut un appel aux procédures stockées catalog.create_execution, catalog.set_execution_parameter_value et catalog.start_execution.</span><span class="sxs-lookup"><span data-stu-id="4070e-115">The statement includes a call to the catalog.create_execution, catalog.set_execution_parameter_value, and catalog.start_execution stored procedures.</span></span> <span data-ttu-id="4070e-116">Pour plus d’informations sur ces procédures stockées, consultez [catalog.create_execution &#40;base de données SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database), [catalog.set_execution_parameter_value &#40;base de données SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database)[catalog.start_execution &#40;base de données SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="4070e-116">For more information about these stored procedures, see [catalog.create_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database), [catalog.set_execution_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database), and [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span></span>  
  
  
