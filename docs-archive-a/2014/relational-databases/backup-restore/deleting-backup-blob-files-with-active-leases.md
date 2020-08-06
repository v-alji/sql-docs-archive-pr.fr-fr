---
title: Suppression de fichiers de sauvegarde d’objets blob avec des baux actifs | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 13a8f879-274f-4934-a722-b4677fc9a782
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 02aea910589633a5c3ec79e283c757727b4d92cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604586"
---
# <a name="deleting-backup-blob-files-with-active-leases"></a><span data-ttu-id="854a3-102">Suppression de fichiers de sauvegarde d'objets blob avec des baux actifs</span><span class="sxs-lookup"><span data-stu-id="854a3-102">Deleting Backup Blob Files with Active Leases</span></span>
  <span data-ttu-id="854a3-103">Lors de la sauvegarde ou de la restauration à partir du stockage Azure, SQL Server acquiert un bail infini pour verrouiller l’accès exclusif à l’objet BLOB.</span><span class="sxs-lookup"><span data-stu-id="854a3-103">When backing up to or restoring from Azure storage, SQL Server acquires an infinite lease in order to lock exclusive access to the blob.</span></span> <span data-ttu-id="854a3-104">Lorsque le processus de sauvegarde ou de restauration est terminé, le bail est libéré.</span><span class="sxs-lookup"><span data-stu-id="854a3-104">When the backup or restore process is successfully completed, the lease is released.</span></span> <span data-ttu-id="854a3-105">Si une sauvegarde ou une restauration échoue, le processus de sauvegarde tente de nettoyer tout objet blob non valide.</span><span class="sxs-lookup"><span data-stu-id="854a3-105">If a backup or restore fails, the backup process attempts to clean up any invalid blob.</span></span> <span data-ttu-id="854a3-106">Toutefois, si la sauvegarde échoue en raison d'un problème de connectivité du réseau prolongé, le processus de sauvegarde peut ne pas être à nouveau en mesure d'accéder à l'objet blob et celui-ci peut rester orphelin.</span><span class="sxs-lookup"><span data-stu-id="854a3-106">However, if the backup fails due to prolonged or sustained network connectivity failure, the backup  process may not be able gain access to the blob and the blob may remain orphaned.</span></span> <span data-ttu-id="854a3-107">Par conséquent, l'objet blob ne peut pas être écrit ou supprimé tant que le bail n'a pas été libéré.</span><span class="sxs-lookup"><span data-stu-id="854a3-107">This means that the blob cannot be written to or deleted until the lease is released.</span></span> <span data-ttu-id="854a3-108">Cette rubrique explique comment libérer le bail et supprimer l'objet blob.</span><span class="sxs-lookup"><span data-stu-id="854a3-108">This topic describes how to release the lease and deleting the blob..</span></span>  
  
 <span data-ttu-id="854a3-109">Pour plus d’informations sur les types de baux, consultez cet [article](https://go.microsoft.com/fwlink/?LinkId=275664).</span><span class="sxs-lookup"><span data-stu-id="854a3-109">For more information on the types of leases, read this [article](https://go.microsoft.com/fwlink/?LinkId=275664).</span></span>  
  
 <span data-ttu-id="854a3-110">Si l'opération de sauvegarde échoue, elle peut générer un fichier de sauvegarde non valide.</span><span class="sxs-lookup"><span data-stu-id="854a3-110">If the backup operation fails, it can result in a backup file that is not valid.</span></span>  <span data-ttu-id="854a3-111">Le fichier de sauvegarde d'objet blob peut également avoir un bail actif, ce qui empêche sa suppression ou son remplacement.</span><span class="sxs-lookup"><span data-stu-id="854a3-111">The backup blob file might also have an active lease, preventing it from being deleted or overwritten.</span></span>  <span data-ttu-id="854a3-112">Pour pouvoir supprimer ou remplacer des objets blob de ce type, le bail doit d'abord être résilié. En cas d'échec de la sauvegarde, nous vous recommandons de nettoyer les baux et de supprimer les objets blob.</span><span class="sxs-lookup"><span data-stu-id="854a3-112">In order to delete or overwrite such blobs, the lease should first be broken.If there are backup failures, we recommend that you clean up leases and delete blobs.</span></span> <span data-ttu-id="854a3-113">Vous pouvez également définir un nettoyage périodique dans le cadre des tâches de gestion du stockage.</span><span class="sxs-lookup"><span data-stu-id="854a3-113">You can also choose cleanup periodically as part of storage management tasks.</span></span>  
  
 <span data-ttu-id="854a3-114">En cas d'échec d'une restauration, les restaurations suivantes ne sont pas bloquées. Par conséquent, le bail actif ne pose pas problème.</span><span class="sxs-lookup"><span data-stu-id="854a3-114">If there is a restore failure, subsequent restores are not blocked, and therefore the active lease may not be an issue.</span></span> <span data-ttu-id="854a3-115">La résiliation du bail est uniquement nécessaire lorsque vous devez remplacer ou supprimer l'objet blob.</span><span class="sxs-lookup"><span data-stu-id="854a3-115">Breaking the lease is only necessary when you have to overwrite or delete the blob.</span></span>  
  
## <a name="managing-orphaned-blobs"></a><span data-ttu-id="854a3-116">Gestion des objets blob orphelins</span><span class="sxs-lookup"><span data-stu-id="854a3-116">Managing Orphaned Blobs</span></span>  
 <span data-ttu-id="854a3-117">Les étapes suivantes décrivent la procédure de nettoyage après l'échec d'une activité de sauvegarde ou de restauration.</span><span class="sxs-lookup"><span data-stu-id="854a3-117">The follow steps describe how to clean up after failed backup or restore activity.</span></span> <span data-ttu-id="854a3-118">Toutes les opérations peuvent être effectuées à l'aide de scripts PowerShell.</span><span class="sxs-lookup"><span data-stu-id="854a3-118">All the steps can be done using PowerShell scripts.</span></span> <span data-ttu-id="854a3-119">Un exemple de code est fourni dans la section suivante :</span><span class="sxs-lookup"><span data-stu-id="854a3-119">A code example is provided in the following section:</span></span>  
  
1.  <span data-ttu-id="854a3-120">**Identification des objets blob avec baux :** si vous avez un script ou un processus qui exécute les processus de sauvegarde, vous pouvez capturer l’erreur dans le script ou le processus et l’utiliser pour nettoyer les objets blob.</span><span class="sxs-lookup"><span data-stu-id="854a3-120">**Identifying blobs that have leases:** If you have a script or a process that runs the backup processes, you might be able to capture the failure within the script or process and use that to clean up the blobs.</span></span>   <span data-ttu-id="854a3-121">Vous pouvez également utiliser les propriétés LeaseStats et LeastState pour identifier les objets blob auxquels des baux sont associés.</span><span class="sxs-lookup"><span data-stu-id="854a3-121">You can also use the LeaseStats and LeastState properties to identify the blobs that have leases on them.</span></span> <span data-ttu-id="854a3-122">Une fois que vous avez identifié les objets blob, nous vous recommandons de consulter la liste et de vérifier la validité du fichier de sauvegarde avant de supprimer l'objet blob.</span><span class="sxs-lookup"><span data-stu-id="854a3-122">Once you have identified the blobs, we recommend that you review the list, verify the validity of the backup file before deleting the blob.</span></span>  
  
2.  <span data-ttu-id="854a3-123">**Résiliation du bail :** une demande autorisée peut résilier le bail sans fournir d’ID de bail.</span><span class="sxs-lookup"><span data-stu-id="854a3-123">**Breaking the lease:** An authorized request can break the lease without supplying a lease ID.</span></span> <span data-ttu-id="854a3-124">Pour plus d’informations, consultez [cet article](https://go.microsoft.com/fwlink/?LinkID=275664) .</span><span class="sxs-lookup"><span data-stu-id="854a3-124">See [here](https://go.microsoft.com/fwlink/?LinkID=275664) for more information.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="854a3-125">SQL Server génère un ID de bail pour établir un accès exclusif pendant l'opération de restauration.</span><span class="sxs-lookup"><span data-stu-id="854a3-125">SQL Server issues a lease ID to establish exclusive access during the restore operation.</span></span> <span data-ttu-id="854a3-126">L'ID de bail de la restauration est BAC2BAC2BAC2BAC2BAC2BAC2BAC2BAC2.</span><span class="sxs-lookup"><span data-stu-id="854a3-126">The restore lease ID is BAC2BAC2BAC2BAC2BAC2BAC2BAC2BAC2.</span></span>  
  
3.  <span data-ttu-id="854a3-127">**Suppression de l’objet blob :** pour supprimer un objet blob dont le bail est actif, vous devez d’abord résilier le bail.</span><span class="sxs-lookup"><span data-stu-id="854a3-127">**Deleting the Blob:** To delete a blob that has an active lease, you must first break the lease.</span></span>  
  
###  <a name="powershell-script-example"></a><a name="Code_Example"></a><span data-ttu-id="854a3-128">Exemple de script PowerShell</span><span class="sxs-lookup"><span data-stu-id="854a3-128">PowerShell Script Example</span></span>  
 <span data-ttu-id="854a3-129">Important si vous exécutez PowerShell 2,0, vous risquez de rencontrer des problèmes lors du chargement de l’assembly Microsoft WindowsAzure.Storage.dll. \*\* \* \* \* \* \*\*</span><span class="sxs-lookup"><span data-stu-id="854a3-129">**\*\* Important \*\*** If you are running PowerShell 2.0, you may have problems loading the Microsoft WindowsAzure.Storage.dll assembly.</span></span> <span data-ttu-id="854a3-130">Nous vous recommandons d'effectuer une mise à niveau vers Powershell 3.0 pour résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="854a3-130">We recommend that you upgrade to Powershell 3.0 to solve the issue.</span></span> <span data-ttu-id="854a3-131">Vous pouvez également utiliser la solution de contournement suivante pour PowerShell 2.0 :</span><span class="sxs-lookup"><span data-stu-id="854a3-131">You may also use the following workaround for PowerShell 2.0:</span></span>  
  
-   <span data-ttu-id="854a3-132">Créez ou modifiez le fichier powershell.exe.config pour charger les assemblies .NET 2.0 et .NET 4.0 au moment de l'exécution avec les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="854a3-132">Create or modify the powershell.exe.config file to load .NET 2.0 and .NET 4.0 assemblies at runtime with the following:</span></span>  
  
    ```xml
    <?xml version="1.0"?>
    <configuration>
        <startup useLegacyV2RuntimeActivationPolicy="true">
            <supportedRuntime version="v4.0.30319"/>
            <supportedRuntime version="v2.0.50727"/>
        </startup>
    </configuration>
    ```  
  
 <span data-ttu-id="854a3-133">L'exemple suivant montre comment identifier les objets blob qui ont des baux actifs, puis résilier ces derniers.</span><span class="sxs-lookup"><span data-stu-id="854a3-133">The following example illustrates identifying blobs that have active leases and then breaking them.</span></span> <span data-ttu-id="854a3-134">Il montre également comment filtrer les identificateurs de bail de la version.</span><span class="sxs-lookup"><span data-stu-id="854a3-134">The example also demonstrates how filter for release lease IDs.</span></span>  
  
 <span data-ttu-id="854a3-135">Conseils pour l'exécution de ce script</span><span class="sxs-lookup"><span data-stu-id="854a3-135">Tips on running this script</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="854a3-136">Si une sauvegarde dans le service de stockage d’objets BLOB Azure s’exécute en même temps que ce script, la sauvegarde peut échouer, car ce script interrompt le bail que la sauvegarde essaie d’acquérir en même temps.</span><span class="sxs-lookup"><span data-stu-id="854a3-136">If a backup to Azure Blob storage service is running at the same time as this script, the backup can fail since this script will break the lease that the backup is trying to acquire at the same time.</span></span> <span data-ttu-id="854a3-137">Nous recommandons d'exécuter ce script au cours d'une fenêtre de maintenance ou lorsqu'aucune sauvegarde n'est prévue.</span><span class="sxs-lookup"><span data-stu-id="854a3-137">We recommend running this script during a maintenance windows or when no backups are expected to run.</span></span>  
  
1.  <span data-ttu-id="854a3-138">Quand vous exécutez ce script, vous êtes invité à fournir des valeurs pour le compte de stockage, la clé de stockage, le conteneur et les paramètres de chemin d’accès et de nom de l’assembly de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="854a3-138">When you run this script, you will be prompted to provide values for the storage account, storage key, container, and the Azure storage assembly path and name parameters.</span></span> <span data-ttu-id="854a3-139">Le chemin d'accès de l'assembly de stockage est le répertoire d'installation de l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="854a3-139">The path of the storage is assembly is the installation directory of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="854a3-140">Le nom de fichier de l'assembly de stockage est Microsoft.WindowsAzure.Storage.dll.</span><span class="sxs-lookup"><span data-stu-id="854a3-140">The file name for the storage assembly is Microsoft.WindowsAzure.Storage.dll.</span></span> <span data-ttu-id="854a3-141">Voici un exemple des commandes et valeurs entrées :</span><span class="sxs-lookup"><span data-stu-id="854a3-141">Following is an example of the prompts and values entered:</span></span>  
  
    ```  
    cmdlet  at command pipeline position 1  
    Supply values for the following parameters:  
    storageAccount: mycloudstorageaccount  
    storageKey: 0BopKY7eEha3gBnistYk+904nf  
    blobContainer: mycontainer   
    storageAssemblyPath: C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn\Microsoft.WindowsAzure.Storage.dll  
    ```  
  
2.  <span data-ttu-id="854a3-142">Si aucun objet blob ne dispose d'un bail verrouillé, vous devez voir le message suivant :</span><span class="sxs-lookup"><span data-stu-id="854a3-142">If there are no blobs that have locked leases you should see the following message:</span></span>  
  
     <span data-ttu-id="854a3-143">**Il n'existe aucun objet blob à l'état bail verrouillé**</span><span class="sxs-lookup"><span data-stu-id="854a3-143">**There are no blobs with locked lease status**</span></span>  
  
     <span data-ttu-id="854a3-144">S'il existe des objets blob avec des baux verrouillés, vous devez voir les messages suivants :</span><span class="sxs-lookup"><span data-stu-id="854a3-144">If there are blobs with locked leases, you should see the following messages:</span></span>  
  
     <span data-ttu-id="854a3-145">**Résiliation de baux**</span><span class="sxs-lookup"><span data-stu-id="854a3-145">**Breaking Leases**</span></span>  
  
     <span data-ttu-id="854a3-146">**Le bail sur \<URL of the Blob> est un bail de restauration : ce message s’affiche uniquement si vous avez un objet BLOB avec un bail de restauration toujours actif.**</span><span class="sxs-lookup"><span data-stu-id="854a3-146">**The lease on \<URL of the Blob> is a restore lease: You will see this message only if you have a blob with a restore lease that is still active.**</span></span>  
  
     <span data-ttu-id="854a3-147">**Le bail sur \<URL of the Blob> n’est pas un bail de restauration avec rupture de bail sur \<URL of the Bob> .**</span><span class="sxs-lookup"><span data-stu-id="854a3-147">**The lease on \<URL of the Blob> is not a restore lease Breaking lease on \<URL of the Bob>.**</span></span>  
  
```powershell
param(  
       [Parameter(Mandatory=$true)]  
       [string]$storageAccount,  
       [Parameter(Mandatory=$true)]  
       [string]$storageKey,  
       [Parameter(Mandatory=$true)]  
       [string]$blobContainer,  
       [Parameter(Mandatory=$true)]  
       [string]$storageAssemblyPath  
)  
  
# Well known Restore Lease ID  
$restoreLeaseId = "BAC2BAC2BAC2BAC2BAC2BAC2BAC2BAC2"  
  
# Load the storage assembly without locking the file for the duration of the PowerShell session  
$bytes = [System.IO.File]::ReadAllBytes($storageAssemblyPath)  
[System.Reflection.Assembly]::Load($bytes)  
  
$cred = New-Object 'Microsoft.WindowsAzure.Storage.Auth.StorageCredentials' $storageAccount, $storageKey  
$client = New-Object 'Microsoft.WindowsAzure.Storage.Blob.CloudBlobClient' "https://$storageAccount.blob.core.windows.net", $cred  
$container = $client.GetContainerReference($blobContainer)  
  
#list all the blobs  
$allBlobs = $container.ListBlobs()
  
$lockedBlobs = @()  
# filter blobs that are have Lease Status as "locked"  
foreach($blob in $allBlobs)  
{  
    $blobProperties = $blob.Properties
    if($blobProperties.LeaseStatus -eq "Locked")  
    {  
        $lockedBlobs += $blob  
    }  
}  
  
if ($lockedBlobs.Count -eq 0)  
{
    Write-Host " There are no blobs with locked lease status"  
}

if($lockedBlobs.Count -gt 0)  
{  
    Write-Host "Breaking leases"  
    foreach($blob in $lockedBlobs )
    {  
        try  
        {  
            $blob.AcquireLease($null, $restoreLeaseId, $null, $null, $null)  
            Write-Host "The lease on $($blob.Uri) is a restore lease"  
        }  
        catch [Microsoft.WindowsAzure.Storage.StorageException]  
        {  
            if($_.Exception.RequestInformation.HttpStatusCode -eq 409)  
            {  
                Write-Host "The lease on $($blob.Uri) is not a restore lease"  
            }  
        }  
  
        Write-Host "Breaking lease on $($blob.Uri)"  
        $blob.BreakLease($(New-TimeSpan), $null, $null, $null) | Out-Null  
    }  
}
```  
  
## <a name="see-also"></a><span data-ttu-id="854a3-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="854a3-148">See Also</span></span>  
 [<span data-ttu-id="854a3-149">Bonnes pratiques et résolution des problèmes liés à la sauvegarde SQL Server vers une URL</span><span class="sxs-lookup"><span data-stu-id="854a3-149">SQL Server Backup to URL Best Practices and Troubleshooting</span></span>](sql-server-backup-to-url-best-practices-and-troubleshooting.md)  
