---
title: Utiliser PowerShell pour sauvegarder plusieurs bases de données dans le service de stockage d’objets BLOB Azure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: f7008339-e69d-4e20-9265-d649da670460
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 95da5d0009f88943029e62960e7429b292242bbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610693"
---
# <a name="use-powershell-to-backup-multiple-databases-to-azure-blob-storage-service"></a><span data-ttu-id="e4ff7-102">Utiliser PowerShell pour sauvegarder plusieurs bases de données dans le service Stockage Blob Azure</span><span class="sxs-lookup"><span data-stu-id="e4ff7-102">Use PowerShell to Backup Multiple Databases to Azure Blob Storage Service</span></span>
  <span data-ttu-id="e4ff7-103">Cette rubrique fournit des exemples de script pouvant être utilisés pour automatiser les sauvegardes dans le service Stockage Blob Azure à l’aide d’applets de commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-103">This topic provides sample scripts that can be used to automate backups to Azure Blob storage service using PowerShell cmdlets.</span></span>  
  
## <a name="overview-of-powershell-cmdlets-for-backup-and-restore"></a><span data-ttu-id="e4ff7-104">Présentation des applets de commande PowerShell pour la sauvegarde et la restauration</span><span class="sxs-lookup"><span data-stu-id="e4ff7-104">Overview of PowerShell cmdlets for Backup and Restore</span></span>  
 <span data-ttu-id="e4ff7-105">`Backup-SqlDatabase` et `Restore-SqlDatabase` sont les deux principales applets de commande disponibles pour effectuer des opérations de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-105">The `Backup-SqlDatabase` and `Restore-SqlDatabase` are the two main cmdlets available to do backup and restore operations.</span></span> <span data-ttu-id="e4ff7-106">De plus, d’autres applets de commande peuvent être nécessaires pour automatiser les sauvegardes dans le service Stockage Blob Azure, comme l’ensemble d’applets de commande **SqlCredential**. Voici une liste des applets de commande PowerShell disponibles dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , qui sont utilisées dans les opérations de sauvegarde et de restauration :</span><span class="sxs-lookup"><span data-stu-id="e4ff7-106">In addition, there are other cmdlets that may be required to automate backups to Azure Blob storage like the set of **SqlCredential** cmdlets  Following is a list of PowerShell cmdlets available in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that are used in backup and restore operations:</span></span>  
  
 <span data-ttu-id="e4ff7-107">Backup-SqlDatabase</span><span class="sxs-lookup"><span data-stu-id="e4ff7-107">Backup-SqlDatabase</span></span>  
 <span data-ttu-id="e4ff7-108">Cette applet de commande permet de créer une sauvegarde [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e4ff7-108">This cmdlet is used to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Backup.</span></span>  
  
 <span data-ttu-id="e4ff7-109">Restore-SqlDatabase</span><span class="sxs-lookup"><span data-stu-id="e4ff7-109">Restore-SqlDatabase</span></span>  
 <span data-ttu-id="e4ff7-110">Utilisée pour restaurer une base de données.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-110">Used to restore a database.</span></span>  
  
 <span data-ttu-id="e4ff7-111">New-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="e4ff7-111">New-SqlCredential</span></span>  
 <span data-ttu-id="e4ff7-112">Cette applet de commande permet de créer des informations d’identification SQL à utiliser pour la sauvegarde SQL Server dans Stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-112">This cmdlet is used to create a SQL Credential to use for SQL Server Backup to Azure Storage.</span></span> <span data-ttu-id="e4ff7-113">Pour plus d’informations sur les informations d’identification et leur utilisation dans SQL Server la sauvegarde et la restauration, consultez [SQL Server la sauvegarde et la restauration avec le service de stockage d’objets BLOB Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="e4ff7-113">For more information on credentials and their use in SQL Server Backup and Restore, see [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
 <span data-ttu-id="e4ff7-114">Get-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="e4ff7-114">Get-SqlCredential</span></span>  
 <span data-ttu-id="e4ff7-115">Cette applet de commande est utilisée pour récupérer l'objet contenant les informations d'identification et ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-115">This cmdlet is used to retrieve the Credential object and its properties.</span></span>  
  
 <span data-ttu-id="e4ff7-116">Remove-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="e4ff7-116">Remove-SqlCredential</span></span>  
 <span data-ttu-id="e4ff7-117">Supprime un objet contenant les informations d'identification SQL</span><span class="sxs-lookup"><span data-stu-id="e4ff7-117">Delete a SQL Credential object</span></span>  
  
 <span data-ttu-id="e4ff7-118">Set-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="e4ff7-118">Set-SqlCredential</span></span>  
 <span data-ttu-id="e4ff7-119">Cette applet de commande est utilisée pour modifier ou définir les propriétés de l'objet contenant les informations d'identification SQL.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-119">This cmdlet is used to change or set the properties of the SQL Credential Object.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="e4ff7-120">Les applets de commande Credential sont utilisées dans les scénarios de sauvegarde et de restauration dans Stockage Blob Azure.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-120">The Credential cmdlets are used in Backup and Restore to Azure Blob storage scenarios.</span></span>  
  
### <a name="powershell-for-multi-database-multi-instance-backup-operations"></a><span data-ttu-id="e4ff7-121">PowerShell pour des opérations de sauvegarde de plusieurs bases de données, sur plusieurs instances</span><span class="sxs-lookup"><span data-stu-id="e4ff7-121">PowerShell for Multi-Database, Multi-Instance Backup Operations</span></span>  
 <span data-ttu-id="e4ff7-122">Les sections suivantes contiennent des scripts pour différentes opérations, notamment créer des informations d'identification SQL sur plusieurs instances de SQL Server, sauvegarder toutes les bases de données utilisateur dans une instance de SQL Server, etc.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-122">The following sections include scripts for various operations like creating a SQL Credential on multiple instance of SQL Server, backing up all user databases in an instance of SQL Server, and such.</span></span> <span data-ttu-id="e4ff7-123">Utilisez ces scripts pour automatiser ou planifier des opérations de sauvegarde en fonction des spécifications de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-123">You can use these scripts to automate or schedule backup operations according to the requirements of your environment.</span></span> <span data-ttu-id="e4ff7-124">Les scripts fournis ici sont des exemples, et peuvent être modifiés ou étendus pour votre environnement.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-124">The scripts provided here are examples, and may be modified or extended for your environment.</span></span>  
  
 <span data-ttu-id="e4ff7-125">Voici quelques observations concernant les exemples de script :</span><span class="sxs-lookup"><span data-stu-id="e4ff7-125">The following are considerations for the sample scripts:</span></span>  
  
1.  <span data-ttu-id="e4ff7-126">**Parcourir les chemins d'accès PowerShell SQL Server :** Windows PowerShell implémente des applets de commande pour parcourir la structure de chemin d'accès qui représente la hiérarchie des objets pris en charge par un fournisseur PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-126">**Navigating SQL Server PowerShell paths:** Windows PowerShell implements cmdlets to navigate the path structure that represents the hierarchy of objects supported by a PowerShell provider.</span></span> <span data-ttu-id="e4ff7-127">Une fois que vous avez accédé à un nœud dans le chemin d'accès, vous pouvez utiliser d'autres applets de commande pour exécuter des opérations de base sur l'objet actif.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-127">When you have navigated to a node in the path, you can use other cmdlets to perform basic operations on the current object.</span></span>  
  
2.  <span data-ttu-id="e4ff7-128">Applet de commande `Get-ChildItem` : Les informations retournées par `Get-ChildItem` dépendent de l'emplacement dans un chemin d'accès PowerShell SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-128">`Get-ChildItem` cmdlet: The information returned by the `Get-ChildItem` depends on the location in a SQL Server PowerShell path.</span></span> <span data-ttu-id="e4ff7-129">Par exemple, si l'emplacement est au niveau de l'ordinateur, cette applet de commande retourne toutes les instances du moteur de base de données SQL Server installées sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-129">For example, if the location is at the computer level, this cmdlet returns all the SQL Server database engine instances installed on the computer.</span></span> <span data-ttu-id="e4ff7-130">Si l'emplacement est au niveau de l'objet, tel que des bases de données, cette applet de commande retourne une liste d'objets de base de données.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-130">As another example, if the location is at the object level such as databases, then this cmdlet returns a list of database objects.</span></span>  <span data-ttu-id="e4ff7-131">Par défaut, l'applet de commande `Get-ChildItem` ne retourne pas d'objets système.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-131">By default the `Get-ChildItem` cmdlet does not return system objects.</span></span>  <span data-ttu-id="e4ff7-132">Pour afficher les objets système, utilisez le paramètre -Force.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-132">Using the -Force parameter you can see the system objects.</span></span>  
  
     <span data-ttu-id="e4ff7-133">Pour plus d’informations, consultez [Navigate SQL Server PowerShell Paths](../../powershell/navigate-sql-server-powershell-paths.md).</span><span class="sxs-lookup"><span data-stu-id="e4ff7-133">For more information, see [Navigate SQL Server PowerShell Paths](../../powershell/navigate-sql-server-powershell-paths.md).</span></span>  
  
3.  <span data-ttu-id="e4ff7-134">Bien que chaque exemple de code puisse être exécuté indépendamment en modifiant les valeurs de variable, vous devez créer un compte de stockage Azure et des informations d’identification SQL pour toutes les opérations de sauvegarde et de restauration dans le service Stockage Blob Azure.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-134">Although each code sample can be tried independently by changing the variable values, creating an Azure Storage Account and a SQL Credential are prerequisites and required for all backup and restore operations to Azure Blob storage service.</span></span>  
  
### <a name="create-a-sql-credential-on-all-the-instances-of-sql-server"></a><span data-ttu-id="e4ff7-135">Créer des informations d'identification SQL sur toutes les instances de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e4ff7-135">Create a SQL Credential on All the Instances of SQL Server</span></span>  
 <span data-ttu-id="e4ff7-136">Il y a deux exemples de script, et les deux créent les informations d’identification SQL « mybackupToURL » sur toutes les instances de SQL Server sur un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-136">There are two sample scripts, and both create a SQL Credential "mybackupToURL" on all the instances of SQL Server on a computer.</span></span> <span data-ttu-id="e4ff7-137">Le premier exemple crée les informations d'identification et n'intercepte pas les exceptions.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-137">The first example creates is simple and creates the credential and does not trap exceptions.</span></span>  <span data-ttu-id="e4ff7-138">Par exemple, s'il existe déjà des informations d'identification avec le même nom sur une des instances de l'ordinateur, le script échoue.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-138">For example, if there was already an existing credential with the same name on one of the instances of the computer, the script would fail.</span></span> <span data-ttu-id="e4ff7-139">Le deuxième exemple intercepte les erreurs et permet au script de continuer.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-139">The second example traps errors and allows the script to continue.</span></span>  
  
```powershell
import-module sqlps  
  
# create variables  
$storageAccount = "mystorageaccount"  
$storageKey = "<storageaccesskeyvalue>"  
$secureString = ConvertTo-SecureString $storageKey  -asplaintext -force  
$credentialName = "mybackuptoURL"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
# get the list of instances  
$instances = Get-ChildItem  
#pipe the instances to new-sqlcredentail cmdlet to create SQL credential  
$instances | New-SqlCredential -Name $credentialName -Identity $storageAccount -Secret $secureString  
```  
  
```powershell
import-module sqlps  
  
# set the parameter values
$storageAccount = "mystorageaccount"  
$storageKey = "<storageaccesskeyvalue>"  
$secureString = ConvertTo-SecureString $storageKey  -asplaintext -force  
$credentialName = "mybackuptoURL"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
# get the list of instances  
$instances = Get-ChildItem  
#loop through instances and create a SQL credential, output any errors  
ForEach ($instance In $instances)  
{  
    Try  
{  
     New-SqlCredential -Name $credentialName -path "SQLServer:\SQL\$($instance.name)" -Identity $storageAccount -Secret $secureString -ea Stop
}  
Catch [Exception]  
    {
            Write-Host "instance - $($instance.name): "$_.Exception.Message
    }
 }
```  
  
### <a name="remove-a-sql-credential-from-all-the-instances-of-sql-server"></a><span data-ttu-id="e4ff7-140">Supprimer des informations d'identification SQL de toutes les instances de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e4ff7-140">Remove A SQL Credential from All the Instances of SQL Server</span></span>  
 <span data-ttu-id="e4ff7-141">Ce script permet de supprimer des informations d'identification spécifiques de toutes les instances de SQL Server installées sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-141">This script can be used to remove a specific credential from all the instances of SQL Server installed on the computer.</span></span> <span data-ttu-id="e4ff7-142">Si l'objet Credential n'existe pas sur une instance spécifique, un message d'erreur s'affiche, et le script continue jusqu'à ce que toutes les instances aient été vérifiées.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-142">If the Credential object does not exist on a specific instance, an error message is displayed, and the script continues until all instances are checked.</span></span>  
  
```powershell
import-module sqlps  
  
cd SQLServer:\SQL\COMPUTERNAME  
$credentialName = "mybackuptoURL"  
  
$instances = Get-ChildItem  
  
ForEach ($instance In $instances)  
   {
    Try  
        {  
            $path = "SQLServer:\SQL\$($instance.name)\credentials\$credentialName"   
            Remove-SqlCredential -Path $path -ea stop   
         }  
         Catch [Exception]  
         {  
            Write-Host $_.Exception.Message
        }
    }  
```  
  
### <a name="full-database-backup-for-all-databases-including-system-databases"></a><span data-ttu-id="e4ff7-143">Sauvegarde complète de base de données pour toutes les bases de données (y compris les bases de données système)</span><span class="sxs-lookup"><span data-stu-id="e4ff7-143">Full Database Backup for all Databases (INCLUDING SYSTEM DATABASES)</span></span>  
 <span data-ttu-id="e4ff7-144">Le script suivant crée des sauvegardes de toutes les bases de données sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-144">The following script creates backups of all databases on the computer.</span></span> <span data-ttu-id="e4ff7-145">Cela inclut les bases de données utilisateur et la base de données système **msdb** .</span><span class="sxs-lookup"><span data-stu-id="e4ff7-145">This includes both user databases and **msdb** system database.</span></span> <span data-ttu-id="e4ff7-146">Le script exclut les bases de données système **tempdb** et **model** .</span><span class="sxs-lookup"><span data-stu-id="e4ff7-146">The script filters out **tempdb** and **model** system databases.</span></span>  
  
```powershell
import-module sqlps  
# set the parameter values  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$credentialName = "mybackuptoURL"  
  
# cd to computer level
cd SQLServer:\SQL\COMPUTERNAME  
$instances = Get-ChildItem
# loop through each instances and backup up all the  databases -filter out tempdb and model databases  
  
 ForEach ($instance In $instances)  
 {  
   $path = "sqlserver:\sql\$($instance.name)\databases"  
   $alldatabases = Get-ChildItem -Force -path $path | Where-Object {$_.name -ne "tempdb" -and $_.name -ne "model"}   
   $alldatabases | Backup-SqlDatabase -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On -script   
 }
```  
  
### <a name="full-database-backup-for-all-user-databases"></a><span data-ttu-id="e4ff7-147">Sauvegarde complète de base de données pour toutes les bases de données utilisateur</span><span class="sxs-lookup"><span data-stu-id="e4ff7-147">Full Database Backup for ALL User Databases</span></span>  
 <span data-ttu-id="e4ff7-148">Le script suivant peut être utilisé pour la sauvegarde de toutes les bases de données utilisateur sur toutes les instances de SQL Server sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-148">The following script can be used to back up all the user databases on all the instances of SQL Server on the computer.</span></span>  
  
```powershell
import-module sqlps
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$credentialName = "mybackuptoURL"  
  
# cd to computer level
cd SQLServer:\SQL\COMPUTERNAME  
$instances = Get-ChildItem
# loop through each instances and backup up all the user databases  
 ForEach ($instance In $instances)  
 {  
    $databases = dir "sqlserver:\sql\$($instance.name)\databases"  
    $databases | Backup-SqlDatabase -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On
 }  
```  
  
### <a name="full-database-backup-for-master-and-msdb-system-databases-on-all-the-instances-of-sql-server"></a><span data-ttu-id="e4ff7-149">Sauvegarde complète des bases de données MASTER et MSDB (bases de données système) sur toutes les instances de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e4ff7-149">Full Database Backup for MASTER and MSDB (SYSTEM DATABASES) On All the Instances of SQL Server</span></span>  
 <span data-ttu-id="e4ff7-150">Le script suivant peut être utilisé pour la sauvegarde des bases de données **master** et **msdb** sur toutes les instances de SQL Server installées sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-150">The following script can be used to back up **master** and **msdb** databases on all the instances of SQL Server installed on the computer.</span></span>  
  
```powershell
import-module sqlps  
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$credentialName = "mybackupToUrl"  
$sysDbs = "master", "msdb"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
$instances = Get-ChildItem
ForEach ($instance In $instances)  
 {  
      ForEach ($s In $sysdbs)  
     {  
        Backup-SqlDatabase -Database $s -path "sqlserver:\sql\$($instance.name)" -BackupContainer  $backupUrlContainer -SqlCredential $credentialName -Compression On   
}
 } 
```  
  
### <a name="full-database-backup-for-all-user-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="e4ff7-151">Sauvegarde complète de toutes les bases de données utilisateur sur une instance de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e4ff7-151">Full Database Backup for All User Databases on an Instance of SQL Server</span></span>  
 <span data-ttu-id="e4ff7-152">Le script suivant est utilisé pour sauvegarder uniquement les bases de données utilisateur disponibles sur une instance nommée de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-152">The following script is used to back up only the user databases available on a named instance of SQL Server.</span></span> <span data-ttu-id="e4ff7-153">Ce script peut être utilisé pour l'instance par défaut sur l'ordinateur en modifiant la valeur du paramètre $srvPath.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-153">The same script can be used for the default instance on the computer by changing the $srvPath parameter value.</span></span>  
  
```powershell
import-module sqlps  
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$srvPath = "SQLServer:\SQL\COMPUTERNAME\INSTANCENAME"  # for default instance, the $srvpath variable is "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
$credentialName = "mybackupToUrl"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
  
#retrieves the database objects for a specific instance  
$databases = dir $srvPath\databases  
  
#backup all the user databases  
$databases | Backup-SqlDatabase -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On  
```  
  
### <a name="full-database-backup-for-only-system-databases-master-and-msdb-on-an-instance-of-sql-server"></a><span data-ttu-id="e4ff7-154">Sauvegarde complète des bases de données système (MASTER et MSDB) sur une instance de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e4ff7-154">Full Database Backup for Only System Databases (MASTER AND MSDB) On an Instance of SQL Server</span></span>  
 <span data-ttu-id="e4ff7-155">Le script complet peut être utilisé pour la sauvegarde des bases de données **master** et **msdb** sur une instance nommée de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-155">The full script can be used to back up the **master** and the **msdb** databases on a named instance of SQL Server.</span></span> <span data-ttu-id="e4ff7-156">Ce script peut être utilisé pour l'instance par défaut sur l'ordinateur en modifiant la valeur du paramètre $srvPath.</span><span class="sxs-lookup"><span data-stu-id="e4ff7-156">The same script can be used for the default instance on the computer by changing the $srvpath parameter value.</span></span>  
  
```powershell
import-module sqlps  
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$srvPath = "SQLServer:\SQL\COMPUTERNAME\INSTANCENAME" # for default instance, the $srvpath variable is "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
$credentialName = "mybackupToUrl"  
  
#navigate to instance level  
cd $srvPath  
  
$sysDbs = "master", "msdb"  
ForEach ($s In $sysDbs)
{  
Backup-SqlDatabase -Database $s -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On  
}
```  
  
## <a name="see-also"></a><span data-ttu-id="e4ff7-157">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e4ff7-157">See Also</span></span>
 <span data-ttu-id="e4ff7-158">[SQL Server la sauvegarde et la restauration avec le service de stockage d’objets BLOB Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) [SQL Server meilleures pratiques et résolution des problèmes de sauvegarde vers une URL](sql-server-backup-to-url-best-practices-and-troubleshooting.md)</span><span class="sxs-lookup"><span data-stu-id="e4ff7-158">[SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) [SQL Server Backup to URL Best Practices and Troubleshooting](sql-server-backup-to-url-best-practices-and-troubleshooting.md)</span></span>  
