---
title: Sauvegarder, restaurer et déplacer le catalogue SSIS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: bf806aef-8556-48ab-aed5-e95de9a2204e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f9de552ddd54168f516f42d9988302561616fd65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604111"
---
# <a name="backup-restore-and-move-the-ssis-catalog"></a><span data-ttu-id="0f0b3-102">Sauvegarder, restaurer et déplacer le catalogue SSIS</span><span class="sxs-lookup"><span data-stu-id="0f0b3-102">Backup, Restore, and Move the SSIS Catalog</span></span>
  [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] <span data-ttu-id="0f0b3-103">comprend la base de données SSISDB.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-103">includes the SSISDB database.</span></span> <span data-ttu-id="0f0b3-104">Interrogez les vues de la base de données SSISDB pour inspecter les objets, les paramètres et les données opérationnelles stockés dans le catalogue **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="0f0b3-104">You query views in the SSISDB database to inspect objects, settings, and operational data that are stored in the **SSISDB** catalog.</span></span> <span data-ttu-id="0f0b3-105">Cette rubrique fournit des instructions sur la sauvegarde et la restauration de la base de données.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-105">This topic provides instructions for backing up and restoring the database.</span></span>  
  
 <span data-ttu-id="0f0b3-106">Le catalogue **SSISDB** stocke les packages que vous avez déployés sur le serveur [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f0b3-106">The **SSISDB** catalog stores the packages that you've deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="0f0b3-107">Pour plus d’informations sur le catalogue, consultez [Catalogue SSIS](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="0f0b3-107">For more information about the catalog, see [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
##  <a name="to-back-up-the-ssis-database"></a><a name="backup"></a> <span data-ttu-id="0f0b3-108">Pour sauvegarder la base de données SSIS</span><span class="sxs-lookup"><span data-stu-id="0f0b3-108">To Back up the SSIS Database</span></span>  
  
1.  <span data-ttu-id="0f0b3-109">Ouvrez [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] et connectez-vous à une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f0b3-109">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="0f0b3-110">Sauvegardez la clé principale de la base de données SSISDB, à l'aide de l'instruction Transact-SQL BACKUP MASTER KEY.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-110">Back up the master key for the SSISDB database, by using the BACKUP MASTER KEY Transact-SQL statement.</span></span> <span data-ttu-id="0f0b3-111">La clé est stockée dans un fichier que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-111">The key is stored in a file that you specify.</span></span> <span data-ttu-id="0f0b3-112">Utilisez un mot de passe pour chiffrer la clé principale dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-112">Use a password to encrypt the master key in the file.</span></span>  
  
     <span data-ttu-id="0f0b3-113">Pour plus d’informations sur l’instruction, consultez [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0f0b3-113">For more information about the statement, see [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span></span>  
  
     <span data-ttu-id="0f0b3-114">Dans l’exemple suivant, la clé principale est exportée vers le fichier `c:\temp directory\RCTestInstKey` .</span><span class="sxs-lookup"><span data-stu-id="0f0b3-114">In the following example, the master key is exported to the `c:\temp directory\RCTestInstKey` file.</span></span> <span data-ttu-id="0f0b3-115">Le mot de passe `LS2Setup!` est utilisé pour chiffrer la clé principale.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-115">The `LS2Setup!` password is used to encrypt the master key.</span></span>  
  
    ```  
    backup master key to file = 'c:\temp\RCTestInstKey'  
           encryption by password = 'LS2Setup!'  
  
    ```  
  
3.  <span data-ttu-id="0f0b3-116">Sauvegardez la base de données SSISDB à l’aide de la boîte de dialogue **Sauvegarder la base de données** dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f0b3-116">Back up the SSISDB database by using the **Backup Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="0f0b3-117">Pour plus d’informations, consultez [Procédure : sauvegarder une base de données (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=231812).</span><span class="sxs-lookup"><span data-stu-id="0f0b3-117">For more information, see [How to: Back Up a Database (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=231812).</span></span>  
  
4.  <span data-ttu-id="0f0b3-118">Générez le script CREATE LOGIN pour ##MS_SSISServerCleanupJobLogin## en procédant comme suit.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-118">Generate the CREATE LOGIN script for ##MS_SSISServerCleanupJobLogin##, by doing the following.</span></span> <span data-ttu-id="0f0b3-119">Pour plus d’informations, consultez [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0f0b3-119">For more information, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
    1.  <span data-ttu-id="0f0b3-120">Dans l’Explorateur d’objets de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], développez le nœud **Sécurité** , puis le nœud **Connexions** .</span><span class="sxs-lookup"><span data-stu-id="0f0b3-120">In Object Explorer in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expand the **Security** node and then expand the **Logins** node.</span></span>  
  
    2.  <span data-ttu-id="0f0b3-121">Cliquez avec le bouton droit sur **##MS_SSISServerCleanupJobLogin##** , puis cliquez sur **Générer un script de la connexion en tant que** > **CREATE To** > **Nouvelle fenêtre d’éditeur de requête**.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-121">Right-click **##MS_SSISServerCleanupJobLogin##**, and then click **Script Login as** > **CREATE To** > **New Query Editor Window**.</span></span>  
  
5.  <span data-ttu-id="0f0b3-122">Si vous devez restaurer la base de données SSISDB sur une instance [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] où le catalogue SSISDB n’a jamais été créé, générez le script CREATE PROCEDURE pour sp_ssis_startup en effectuant les opérations suivantes.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-122">If you will be restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, generate the CREATE PROCEDURE script for sp_ssis_startup, by doing the following.</span></span> <span data-ttu-id="0f0b3-123">Pour plus d’informations, consultez [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0f0b3-123">For more information, see [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span></span>  
  
    1.  <span data-ttu-id="0f0b3-124">Dans l’Explorateur d’objets, développez le nœud **bases de données** , puis développez le nœud **bases de données système de**la  >  **master**  >  **programmabilité**principale  >  **procédures stockées** .</span><span class="sxs-lookup"><span data-stu-id="0f0b3-124">In Object Explorer, expand the **Databases** node and then expand the **System Databases** > **master** > **Programmability** > **Stored Procedures** node.</span></span>  
  
    2.  <span data-ttu-id="0f0b3-125">Cliquez avec le bouton droit sur **dbo.sp_ssis_startup**, puis cliquez sur **Générer un script de la procédure stockée en tant que** > **CREATE To** > **Nouvelle fenêtre d’éditeur de requête**.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-125">Right click **dbo.sp_ssis_startup**, and then click **Script Stored Procedure as** > **CREATE To** > **New Query Editor Window**.</span></span>  
  
6.  <span data-ttu-id="0f0b3-126">Assurez-vous que Le SQL Server Agent a démarré.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-126">Confirm that SQL Server Agent has been started</span></span>  
  
7.  <span data-ttu-id="0f0b3-127">Si vous devez restaurer la base de données SSISDB sur une instance [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] où le catalogue SSISDB n’a jamais été créé, générez un script pour la tâche de maintenance de serveur SSIS en effectuant les opérations suivantes.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-127">If you will be restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, generate a script for the SSIS Server Maintenance Job by doing the following.</span></span> <span data-ttu-id="0f0b3-128">Le script est créé automatiquement dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent quand le catalogue SSISDB est créé.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-128">The script is created in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent automatically when the SSISDB catalog is created.</span></span> <span data-ttu-id="0f0b3-129">Le travail permet de nettoyer les journaux d'opérations de nettoyage en dehors de la période de conservation et de supprimer les versions antérieures des projets.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-129">The job helps clean up cleanup operation logs outside the retention window and remove older versions of projects.</span></span>  
  
    1.  <span data-ttu-id="0f0b3-130">Dans l’Explorateur d’objets, développez le nœud **SQL Server Agent** , puis le nœud **Travaux** .</span><span class="sxs-lookup"><span data-stu-id="0f0b3-130">In Object Explorer, expand the **SQL Server Agent** node and then expand the **Jobs** node.</span></span>  
  
    2.  <span data-ttu-id="0f0b3-131">Cliquez avec le bouton droit sur travail de maintenance du serveur SSIS, puis cliquez sur créer un **travail de script**dans une  >  **CREATE To**  >  **nouvelle fenêtre**de l’éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-131">Right click SSIS Server Maintenance Job, and then click **Script Job as** > **CREATE To** > **New Query Editor Window**.</span></span>  
  
### <a name="to-restore-the-ssis-database"></a><span data-ttu-id="0f0b3-132">Pour restaurer la base de données SSIS</span><span class="sxs-lookup"><span data-stu-id="0f0b3-132">To Restore the SSIS Database</span></span>  
  
1.  <span data-ttu-id="0f0b3-133">Si vous restaurez la base de données SSISDB sur une instance [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] où le catalogue SSISDB n'a jamais été créé, activez le CLR en exécutant la procédure stockée sp_configure.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-133">If you are restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, enable common language runtime (clr) by running the sp_configure stored procedure.</span></span> <span data-ttu-id="0f0b3-134">Pour plus d’informations, consultez [sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) et [clr enabled (option de configuration de serveur)](https://go.microsoft.com/fwlink/?LinkId=231855).</span><span class="sxs-lookup"><span data-stu-id="0f0b3-134">For more information, see [sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) and [clr enabled Option](https://go.microsoft.com/fwlink/?LinkId=231855).</span></span>  
  
    ```  
    use master   
           sp_configure 'clr enabled', 1  
           reconfigure  
  
    ```  
  
2.  <span data-ttu-id="0f0b3-135">Vous restaurez la base de données SSISDB sur une instance [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] où le catalogue SSISDB n'a jamais été créé, créez la clé asymétrique et la connexion à partir de la clé asymétrique et accordez l'autorisation UNSAFE à la connexion.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-135">If you are restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, create the asymmetric key and the login from the asymmetric key, and grant UNSAFE permission to the login.</span></span>  
  
    ```  
    Create Asymmetric key MS_SQLEnableSystemAssemblyLoadingKey  
           FROM Executable File = 'C:\Program Files\Microsoft SQL Server\110\DTS\Binn\Microsoft.SqlServer.IntegrationServices.Server.dll'  
  
    ```  
  
     [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="0f0b3-136">Les procédures stockées CLR exigent l’octroi d’autorisations UNSAFE à la connexion, car cette dernière nécessite un accès supplémentaire aux ressources restreintes, par exemple l’API Win32 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-136">CLR stored procedures require UNSAFE permissions to be granted to the login because the login requires additional access to restricted resources, such as the Microsoft Win32 API.</span></span> <span data-ttu-id="0f0b3-137">Pour plus d’informations sur l’autorisation de code UNSAFE, consultez [Création d’un assembly](../relational-databases/clr-integration/assemblies/creating-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="0f0b3-137">For more information about the UNSAFE code permission, see [Creating an Assembly](../relational-databases/clr-integration/assemblies/creating-an-assembly.md).</span></span>  
  
    ```  
    Create Login MS_SQLEnableSystemAssemblyLoadingUser  
           FROM Asymmetric key MS_SQLEnableSystemAssemblyLoadingKey   
  
           Grant unsafe Assembly to MS_SQLEnableSystemAssemblyLoadingUser  
  
    ```  
  
3.  <span data-ttu-id="0f0b3-138">Restaurez la base de données SSISDB à partir de la sauvegarde, à l’aide de la boîte de dialogue **Restaurer la base de données** dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f0b3-138">Restore the SSISDB database from the backup by using the **Restore Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="0f0b3-139">Pour plus d'informations, consultez les rubriques ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-139">For more information, see the following topics.</span></span>  
  
    -   [<span data-ttu-id="0f0b3-140">Restaurer la base de données &#40;page Général&#41;</span><span class="sxs-lookup"><span data-stu-id="0f0b3-140">Restore Database &#40;General Page&#41;</span></span>](general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="0f0b3-141">Restaurer la base de données &#40;page Fichiers&#41;</span><span class="sxs-lookup"><span data-stu-id="0f0b3-141">Restore Database &#40;Files Page&#41;</span></span>](../relational-databases/backup-restore/restore-database-files-page.md)  
  
    -   [<span data-ttu-id="0f0b3-142">Restaurer la base de données &#40;page Options&#41;</span><span class="sxs-lookup"><span data-stu-id="0f0b3-142">Restore Database &#40;Options Page&#41;</span></span>](../relational-databases/backup-restore/restore-database-options-page.md)  
  
4.  <span data-ttu-id="0f0b3-143">Exécutez les scripts que vous avez créés dans la procédure [Pour sauvegarder la base de données SSIS](#backup) pour ##MS_SSISServerCleanupJobLogin##, sp_ssis_startup et le travail de maintenance de serveur SSIS.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-143">Execute the scripts that you created in the [To Back up the SSIS Database](#backup) for ##MS_SSISServerCleanupJobLogin##, sp_ssis_startup, and SSIS Server Maintenance Job.</span></span> <span data-ttu-id="0f0b3-144">Assurez-vous que SQL Server Agent a démarré.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-144">Confirm that SQL Server Agent has been started.</span></span>  
  
5.  <span data-ttu-id="0f0b3-145">Exécutez l'instruction suivante afin de définir la procédure sp_ssis_startup pour l'exécution automatique.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-145">Run the following statement to set the sp_ssis_startup prodecure for autoexecution.</span></span> <span data-ttu-id="0f0b3-146">Pour plus d’informations, consultez [sp_procoption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0f0b3-146">For more information, see [sp_procoption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql).</span></span>  
  
    ```  
    EXEC sp_procoption N'sp_ssis_startup','startup','on'  
    ```  
  
6.  <span data-ttu-id="0f0b3-147">Mappez l’utilisateur SSISDB ##MS_SSISServerCleanupJobUser## (base de données SSISDB) à ##MS_SSISServerCleanupJobLogin##, à l’aide de la boîte de dialogue **Propriétés de la connexion** dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f0b3-147">Map the SSISDB user ##MS_SSISServerCleanupJobUser## (SSISDB database) to ##MS_SSISServerCleanupJobLogin##, by using the **Login Properties** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
7.  <span data-ttu-id="0f0b3-148">Restaurez la clé principale à l'aide de l'une des méthodes suivantes.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-148">Restore the master key by using one of the following methods.</span></span> <span data-ttu-id="0f0b3-149">Pour plus d’informations sur le chiffrement, consultez [Hiérarchie de chiffrement](../relational-databases/security/encryption/encryption-hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="0f0b3-149">For more information about encryption, see [Encryption Hierarchy](../relational-databases/security/encryption/encryption-hierarchy.md).</span></span>  
  
    -   <span data-ttu-id="0f0b3-150">**Méthode 1**</span><span class="sxs-lookup"><span data-stu-id="0f0b3-150">**Method 1**</span></span>  
  
         <span data-ttu-id="0f0b3-151">Utilisez cette méthode si vous avez déjà effectué une sauvegarde de la clé principale de base de données et si vous disposez du mot de passe de chiffrement de la clé principale.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-151">Use this method if you've already performed a backup of the database master key, and you have the password used to encrypt the master key.</span></span>  
  
        ```  
               Restore master key from file = 'c:\temp\RCTestInstKey'  
               Decryption by password = 'LS2Setup!' -- 'Password used to encrypt the master key during SSISDB backup'  
               Encryption by password = 'LS3Setup!' -- 'New Password'  
               Force  
  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="0f0b3-152">Assurez-vous que le compte de service [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] dispose des autorisations nécessaires pour lire le fichier de clé de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-152">Confirm that the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service account has permissions to read the backup key file.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="0f0b3-153">Le message d’avertissement suivant s’affiche dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] si la clé principale de base de données n’a pas encore été chiffrée par la clé principale du service.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-153">You will see the following warning message displayed in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] if the database master key has not yet been encrypted by the service master key.</span></span> <span data-ttu-id="0f0b3-154">Ignorez le message d'avertissement.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-154">Ignore the warning message.</span></span>  
        >   
        >  <span data-ttu-id="0f0b3-155">**Impossible de déchiffrer la clé principale active. Cette erreur a été ignorée, car l’option FORCE a été spécifiée.**</span><span class="sxs-lookup"><span data-stu-id="0f0b3-155">**The current master key cannot be decrypted. The error was ignored because the FORCE option was specified.**</span></span>  
        >   
        >  <span data-ttu-id="0f0b3-156">L'argument FORCE spécifie que le processus de restauration doit continuer même si la clé principale de base de données actuelle n'est pas ouverte.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-156">The FORCE argument specifies that the restore process should continue even if the current database master key is not open.</span></span> <span data-ttu-id="0f0b3-157">Pour le catalogue SSISDB, comme la clé principale de base de données n'a pas été ouverte sur l'instance où vous restaurez la base de données, vous voyez s'afficher ce message.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-157">For the SSISDB catalog, because the database master key has not been opened on the instance where you are restoring the database, you will see this message.</span></span>  
  
    -   <span data-ttu-id="0f0b3-158">**Méthode 2**</span><span class="sxs-lookup"><span data-stu-id="0f0b3-158">**Method 2**</span></span>  
  
         <span data-ttu-id="0f0b3-159">Utilisez cette méthode si vous disposez du mot de passe d'origine utilisé pour créer SSISDB.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-159">Use this method if you have the original password that was used to create SSISDB.</span></span>  
  
        ```  
        open master key decryption by password = 'LS1Setup!' --'Password used when creating SSISDB'  
               Alter Master Key Add encryption by Service Master Key  
        ```  
  
8.  <span data-ttu-id="0f0b3-160">Déterminez si le schéma de catalogue SSISDB et les binaires [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] (assembly SQLCLR et ISServerExec) sont compatibles en exécutant [catalog.check_schema_version](/sql/integration-services/system-stored-procedures/catalog-check-schema-version).</span><span class="sxs-lookup"><span data-stu-id="0f0b3-160">Determine whether the SSISDB catalog schema and the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] binaries (ISServerExec and SQLCLR assembly) are compatible, by running [catalog.check_schema_version](/sql/integration-services/system-stored-procedures/catalog-check-schema-version).</span></span>  
  
9. <span data-ttu-id="0f0b3-161">Pour vérifier que la base de données SSISDB a été restaurée correctement, effectuez des opérations sur le catalogue SSISDB, par exemple exécutez des packages déployés sur le serveur [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0f0b3-161">To confirm that the SSISDB database has been restored successfully, perform operations against the SSISDB catalog such as running packages that have been deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="0f0b3-162">Pour plus d’informations, consultez [Exécuter un package sur le serveur SSIS à l’aide de SQL Server Management Studio](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="0f0b3-162">For more information, see [Run a Package on the SSIS Server Using SQL Server Management Studio](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md).</span></span>  
  
### <a name="to-move-the-ssis-database"></a><span data-ttu-id="0f0b3-163">Pour déplacer la base de données SSIS</span><span class="sxs-lookup"><span data-stu-id="0f0b3-163">To Move the SSIS Database</span></span>  
  
-   <span data-ttu-id="0f0b3-164">Suivez les instructions pour déplacer les bases de données utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-164">Follow the instructions for moving user databases.</span></span> <span data-ttu-id="0f0b3-165">Pour plus d’informations, consultez [Déplacer des bases de données utilisateur](../relational-databases/databases/move-user-databases.md).</span><span class="sxs-lookup"><span data-stu-id="0f0b3-165">For more information, see [Move User Databases](../relational-databases/databases/move-user-databases.md).</span></span>  
  
     <span data-ttu-id="0f0b3-166">Veillez à sauvegarder la clé principale de la base de données SSISDB et à protéger le fichier de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-166">Ensure that you back up the master key for the SSISDB database and protect the backup file.</span></span> <span data-ttu-id="0f0b3-167">Pour plus d’informations, consultez [Pour sauvegarder la base de données SSIS](#backup).</span><span class="sxs-lookup"><span data-stu-id="0f0b3-167">For more information, see [To Back up the SSIS Database](#backup).</span></span>  
  
     <span data-ttu-id="0f0b3-168">Vérifiez que les objets Integration Services (SSIS) appropriés sont créés dans la nouvelle instance [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] où le catalogue SSISDB n’a pas encore été créé.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-168">Ensure that the Integration Services (SSIS) relevant objects are created in the new [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog has not yet been created.</span></span>  
  
  
