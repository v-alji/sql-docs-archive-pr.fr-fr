---
title: Créer le catalogue SSIS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 6ed56d36-18d9-40c2-b51f-f2a4c71d1e73
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2572cc131f34a21171054a159e3b7968c453a780
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602233"
---
# <a name="create-the-ssis-catalog"></a><span data-ttu-id="b68b1-102">Créer le catalogue SSIS</span><span class="sxs-lookup"><span data-stu-id="b68b1-102">Create the SSIS Catalog</span></span>
  <span data-ttu-id="b68b1-103">Après avoir conçu et testé des packages dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], vous pouvez déployer les projets qui contiennent les packages sur un serveur [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b68b1-103">After you design and test packages in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], you can deploy the projects that contain the packages to an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="b68b1-104">Avant de pouvoir déployer des projets sur le serveur [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], celui-ci doit contenir le catalogue `SSISDB`.</span><span class="sxs-lookup"><span data-stu-id="b68b1-104">Before you can deploy the projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, the server must contain the `SSISDB` catalog.</span></span> <span data-ttu-id="b68b1-105">Le programme d'installation de [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] ne crée pas automatiquement le catalogue ; vous devez le créer manuellement à l'aide des instructions suivantes.</span><span class="sxs-lookup"><span data-stu-id="b68b1-105">The installation program for [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] does not automatically create the catalog; you need to manually create the catalog by using the following instructions.</span></span>  
  
 <span data-ttu-id="b68b1-106">Vous pouvez créer le catalogue SSISDB dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b68b1-106">You can create the SSISDB catalog in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="b68b1-107">Vous pouvez également créer le catalogue par programmation en utilisant Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b68b1-107">You also create the catalog programmatically by using Windows PowerShell.</span></span>  
  
### <a name="to-create-the-ssisdb-catalog-in-sql-server-management-studio"></a><span data-ttu-id="b68b1-108">Pour créer le catalogue SSISDB dans SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b68b1-108">To create the SSISDB catalog in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="b68b1-109">Ouvrez [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b68b1-109">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="b68b1-110">Connectez-vous au moteur de base de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b68b1-110">Connect to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Database Engine.</span></span>  
  
3.  <span data-ttu-id="b68b1-111">Dans l’Explorateur d’objets, développez le nœud du serveur, cliquez avec le bouton droit sur le nœud **Catalogues Integration Services** , puis cliquez sur **Créer un catalogue**.</span><span class="sxs-lookup"><span data-stu-id="b68b1-111">In Object Explorer, expand the server node, right-click the **Integration Services Catalogs** node, and then click **Create Catalog**.</span></span>  
  
4.  <span data-ttu-id="b68b1-112">Cliquez sur **Activer l'intégration du CLR**.</span><span class="sxs-lookup"><span data-stu-id="b68b1-112">Click **Enable CLR Integration**.</span></span>  
  
     <span data-ttu-id="b68b1-113">Le catalogue utilise des procédures stockées du CLR.</span><span class="sxs-lookup"><span data-stu-id="b68b1-113">The catalog uses CLR stored procedures.</span></span>  
  
5.  <span data-ttu-id="b68b1-114">Cliquez sur **Activer l’exécution automatique des procédures stockées Integration Services au démarrage de SQL Server** pour permettre à la procédure stockée [catalog.startup](/sql/integration-services/system-stored-procedures/catalog-startup) de s’exécuter à chaque redémarrage de l’instance de serveur [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b68b1-114">Click **Enable automatic execution of Integration Services stored procedure at SQL Server startup** to enable the [catalog.startup](/sql/integration-services/system-stored-procedures/catalog-startup) stored procedure to run each time the [!INCLUDE[ssIS](../includes/ssis-md.md)] server instance is restarted.</span></span>  
  
     <span data-ttu-id="b68b1-115">La procédure stockée effectue la maintenance de l'état des opérations pour le catalogue SSISDB.</span><span class="sxs-lookup"><span data-stu-id="b68b1-115">The stored procedure performs maintenance of the state of operations for the SSISDB catalog.</span></span> <span data-ttu-id="b68b1-116">Elle résout l'état de tous les packages en cours d'exécution si et quand l'instance de serveur [!INCLUDE[ssIS](../includes/ssis-md.md)] s'arrête.</span><span class="sxs-lookup"><span data-stu-id="b68b1-116">It fixes the status of any packages there were running if and when the [!INCLUDE[ssIS](../includes/ssis-md.md)] server instance goes down.</span></span>  
  
6.  <span data-ttu-id="b68b1-117">Entrez un mot de passe, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b68b1-117">Enter a password, and then click **Ok**.</span></span>  
  
     <span data-ttu-id="b68b1-118">Le mot de passe protège la clé principale de la base de données utilisée pour le chiffrement des données du catalogue.</span><span class="sxs-lookup"><span data-stu-id="b68b1-118">The password protects the database master key that is used for encrypting the catalog data.</span></span> <span data-ttu-id="b68b1-119">Enregistrez le mot de passe dans un emplacement sécurisé.</span><span class="sxs-lookup"><span data-stu-id="b68b1-119">Save the password in a secure location.</span></span> <span data-ttu-id="b68b1-120">Il est également recommandé de sauvegarder la clé principale de base de données.</span><span class="sxs-lookup"><span data-stu-id="b68b1-120">It is recommended that you also back up the database master key.</span></span> <span data-ttu-id="b68b1-121">Pour plus d'informations, consultez [Back Up a Database Master Key](../relational-databases/security/encryption/back-up-a-database-master-key.md).</span><span class="sxs-lookup"><span data-stu-id="b68b1-121">For more information, see [Back Up a Database Master Key](../relational-databases/security/encryption/back-up-a-database-master-key.md).</span></span>  
  
### <a name="to-create-the-ssisdb-catalog-programmatically"></a><span data-ttu-id="b68b1-122">Pour créer le catalogue SSISDB par programmation</span><span class="sxs-lookup"><span data-stu-id="b68b1-122">To create the SSISDB catalog programmatically</span></span>  
  
1.  <span data-ttu-id="b68b1-123">Exécutez le script PowerShell suivant :</span><span class="sxs-lookup"><span data-stu-id="b68b1-123">Execute the following PowerShell script:</span></span>  
  
    ```powershell
    # Load the IntegrationServices Assembly  
    [Reflection.Assembly]::LoadWithPartialName("Microsoft.SqlServer.Management.IntegrationServices")  
  
    # Store the IntegrationServices Assembly namespace to avoid typing it every time  
    $ISNamespace = "Microsoft.SqlServer.Management.IntegrationServices"  
  
    Write-Host "Connecting to server ..."  
  
    # Create a connection to the server  
    $sqlConnectionString = "Data Source=localhost;Initial Catalog=master;Integrated Security=SSPI;"  
    $sqlConnection = New-Object System.Data.SqlClient.SqlConnection $sqlConnectionString  
  
    # Create the Integration Services object  
    $integrationServices = New-Object $ISNamespace".IntegrationServices" $sqlConnection  
  
    # Provision a new SSIS Catalog  
    $catalog = New-Object $ISNamespace".Catalog" ($integrationServices, "SSISDB", "P@assword1")  
    $catalog.Create()
    ```  
  
     <span data-ttu-id="b68b1-124">Vous trouverez d’autres exemples d’utilisation de Windows PowerShell et de l’espace de noms <xref:Microsoft.SqlServer.Management.IntegrationServices> dans l’entrée de blog [SSIS et PowerShell dans SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=242539), sur blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="b68b1-124">For more examples of how to use Windows PowerShell and the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace, see the blog entry, [SSIS and PowerShell in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=242539), on blogs.msdn.com.</span></span> <span data-ttu-id="b68b1-125">Pour obtenir une vue d'ensemble de l'espace de noms et des exemples de code, consultez l'entrée de blog, [A Glimpse of the SSIS Catalog Managed Object Model](https://techcommunity.microsoft.com/t5/sql-server-integration-services/a-glimpse-of-the-ssis-catalog-managed-object-model/ba-p/387892), sur blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="b68b1-125">For an overview of the namespace and code examples, see the blog entry, [A Glimpse of the SSIS Catalog Managed Object Model](https://techcommunity.microsoft.com/t5/sql-server-integration-services/a-glimpse-of-the-ssis-catalog-managed-object-model/ba-p/387892), on blogs.msdn.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b68b1-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b68b1-126">See Also</span></span>  
 <span data-ttu-id="b68b1-127">[Catalogue SSIS](catalog/ssis-catalog.md) </span><span class="sxs-lookup"><span data-stu-id="b68b1-127">[SSIS Catalog](catalog/ssis-catalog.md) </span></span>  
 [<span data-ttu-id="b68b1-128">Sauvegarder, restaurer et déplacer le catalogue SSIS</span><span class="sxs-lookup"><span data-stu-id="b68b1-128">Backup, Restore, and Move the SSIS Catalog</span></span>](../../2014/integration-services/backup-restore-and-move-the-ssis-catalog.md)  
