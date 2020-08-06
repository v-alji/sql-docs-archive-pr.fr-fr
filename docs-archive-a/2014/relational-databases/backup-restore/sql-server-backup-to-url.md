---
title: Sauvegarde SQL Server vers une URL | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 11be89e9-ff2a-4a94-ab5d-27d8edf9167d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6918a099e00b1de9e773320b5c6c0e4089859e02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703027"
---
# <a name="sql-server-backup-to-url"></a><span data-ttu-id="a1218-102">Sauvegarde SQL Server vers une URL</span><span class="sxs-lookup"><span data-stu-id="a1218-102">SQL Server Backup to URL</span></span>
  <span data-ttu-id="a1218-103">Cette rubrique présente les concepts, la configuration requise et les composants nécessaires à l’utilisation du service de stockage d’objets BLOB Azure en tant que destination de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="a1218-103">This topic introduces the concepts, requirements and components necessary to use the Azure Blob storage service as a backup destination.</span></span> <span data-ttu-id="a1218-104">Les fonctionnalités de sauvegarde et de restauration sont identiques ou similaires à l'utilisation de l'option DISK ou TAPE, à quelques différences près.</span><span class="sxs-lookup"><span data-stu-id="a1218-104">The backup and restore functionality are same or similar to when using DISK or TAPE, with a few differences.</span></span> <span data-ttu-id="a1218-105">Les différences, les exceptions notables et des exemples de code sont inclus dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="a1218-105">The differences are and any notable exceptions, and a few code examples are included in this topic.</span></span>  
  
## <a name="requirements-components-and-concepts"></a><span data-ttu-id="a1218-106">Configuration requise, composants et concepts</span><span class="sxs-lookup"><span data-stu-id="a1218-106">Requirements, Components, and Concepts</span></span>  
 <span data-ttu-id="a1218-107">**Dans cette section :**</span><span class="sxs-lookup"><span data-stu-id="a1218-107">**In this section:**</span></span>  
  
-   [<span data-ttu-id="a1218-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a1218-108">Security</span></span>](#security)  
  
-   [<span data-ttu-id="a1218-109">Présentation des principaux éléments et concepts</span><span class="sxs-lookup"><span data-stu-id="a1218-109">Introduction to Key Components and Concepts</span></span>](#intorkeyconcepts)  
  
-   [<span data-ttu-id="a1218-110">Service de stockage d’objets BLOB Azure</span><span class="sxs-lookup"><span data-stu-id="a1218-110">Azure Blob Storage Service</span></span>](#Blob)  
  
-   [<span data-ttu-id="a1218-111">Composants SQL Server</span><span class="sxs-lookup"><span data-stu-id="a1218-111">SQL Server Components</span></span>](#sqlserver)  
  
-   [<span data-ttu-id="a1218-112">Limitations</span><span class="sxs-lookup"><span data-stu-id="a1218-112">Limitations</span></span>](#limitations)  
  
-   [<span data-ttu-id="a1218-113">Prise en charge des instructions Backup/Restore</span><span class="sxs-lookup"><span data-stu-id="a1218-113">Support for Backup/Restore Statements</span></span>](#Support)  
  
-   [<span data-ttu-id="a1218-114">Utilisation de la tâche de sauvegarde dans SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a1218-114">Using Backup Task in SQL Server Management Studio</span></span>](sql-server-backup-to-url.md#BackupTaskSSMS)  
  
-   [<span data-ttu-id="a1218-115">Sauvegarde SQL Server vers une URL à l'aide de l'Assistant Plan de maintenance</span><span class="sxs-lookup"><span data-stu-id="a1218-115">SQL Server Backup to URL Using Maintenance Plan Wizard</span></span>](sql-server-backup-to-url.md#MaintenanceWiz)  
  
-   [<span data-ttu-id="a1218-116">Restauration à partir du stockage Azure à l’aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a1218-116">Restoring from Azure storage Using SQL Server Management Studio</span></span>](sql-server-backup-to-url.md#RestoreSSMS)  
  
###  <a name="security"></a><a name="security"></a> <span data-ttu-id="a1218-117">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a1218-117">Security</span></span>  
 <span data-ttu-id="a1218-118">Voici les considérations relatives à la sécurité et la configuration requise pour la sauvegarde ou la restauration à partir des services de stockage d’objets BLOB Azure.</span><span class="sxs-lookup"><span data-stu-id="a1218-118">The following are security considerations and requirements when backing up to or restoring from the Azure Blob storage services.</span></span>  
  
-   <span data-ttu-id="a1218-119">Lorsque vous créez un conteneur pour le service de stockage d’objets BLOB Azure, nous vous recommandons de définir l’accès sur **privé**.</span><span class="sxs-lookup"><span data-stu-id="a1218-119">When creating a container for the Azure Blob storage service, we recommend that you set the access to **private**.</span></span> <span data-ttu-id="a1218-120">La définition d’un accès privé limite l’accès aux seuls utilisateurs ou comptes capables de fournir les informations nécessaires pour s’authentifier auprès du compte Azure.</span><span class="sxs-lookup"><span data-stu-id="a1218-120">Setting the access to private restricts the access to users or accounts able to provide the necessary information to authenticate to the Azure account.</span></span>  
  
    > [!IMPORTANT]  
    >  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="a1218-121">requiert que le nom du compte Azure et l’authentification de la clé d’accès soient stockés dans les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="a1218-121">requires Azure account name and access key authentication to be stored in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Credential.</span></span> <span data-ttu-id="a1218-122">Ces informations sont utilisées pour l’authentification auprès du compte Azure lorsqu’il effectue des opérations de sauvegarde ou de restauration.</span><span class="sxs-lookup"><span data-stu-id="a1218-122">This information is used to authenticate to the Azure account when it performs backup or restore operations.</span></span>  
  
-   <span data-ttu-id="a1218-123">Le compte d’utilisateur utilisé pour émettre les commandes BACKUP (sauvegarder) ou RESTORE (restaurer) doit figurer dans le rôle de base de données **db_backup operator** avec les autorisations **Modifier des informations d’identification** .</span><span class="sxs-lookup"><span data-stu-id="a1218-123">The user account that is used to issue BACKUP or RESTORE commands should be in the **db_backup operator** database role with **Alter any credential** permissions.</span></span>  
  
###  <a name="introduction-to-key-components-and-concepts"></a><a name="intorkeyconcepts"></a><span data-ttu-id="a1218-124">Présentation des principaux composants et concepts</span><span class="sxs-lookup"><span data-stu-id="a1218-124">Introduction to Key Components and Concepts</span></span>  
 <span data-ttu-id="a1218-125">Les deux sections suivantes présentent le service de stockage d’objets BLOB Azure, ainsi que les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] composants utilisés lors de la sauvegarde ou de la restauration à partir du service de stockage d’objets BLOB Azure.</span><span class="sxs-lookup"><span data-stu-id="a1218-125">The following two sections introduce the Azure Blob storage service, and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components used when backing up to or restoring from the Azure Blob storage service.</span></span> <span data-ttu-id="a1218-126">Il est important de comprendre les composants et leur interaction pour effectuer une sauvegarde ou une restauration à partir du service de stockage d’objets BLOB Azure.</span><span class="sxs-lookup"><span data-stu-id="a1218-126">It is important to understand the components and the interaction between them to do a backup to or restore from the Azure Blob storage service.</span></span>  
  
 <span data-ttu-id="a1218-127">La création d’un compte Azure est la première étape de ce processus.</span><span class="sxs-lookup"><span data-stu-id="a1218-127">Creating an Azure account is the first step to this process.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="a1218-128">utilise le **nom du compte de stockage Azure** et ses valeurs de **clé d’accès** pour authentifier et écrire et lire les objets BLOB dans le service de stockage.</span><span class="sxs-lookup"><span data-stu-id="a1218-128">uses the **Azure storage account name** and its **access key** values to authenticate and write and read blobs to the storage service.</span></span> <span data-ttu-id="a1218-129">Les informations d'identification de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stockent ces informations et sont utilisées lors des opérations de sauvegarde ou de restauration.</span><span class="sxs-lookup"><span data-stu-id="a1218-129">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Credential stores this authentication information and is used during the backup or restore operations.</span></span> <span data-ttu-id="a1218-130">Pour une procédure pas à pas complète de création d’un compte de stockage et d’exécution d’une restauration simple, consultez [didacticiel utilisation du service de stockage Azure pour la sauvegarde et la restauration de SQL Server](https://go.microsoft.com/fwlink/?LinkId=271615).</span><span class="sxs-lookup"><span data-stu-id="a1218-130">For a complete walkthrough of creating a storage account and performing a simple restore, see [Tutorial Using Azure Storage Service for SQL Server Backup and Restore](https://go.microsoft.com/fwlink/?LinkId=271615).</span></span>  
  
 <span data-ttu-id="a1218-131">![mappage de la compte de stockage à l'information d'identification](../../tutorials/media/backuptocloud-storage-credential-mapping.gif "mappage de la compte de stockage à l'information d'identification")</span><span class="sxs-lookup"><span data-stu-id="a1218-131">![mapping storage account to sql credentials](../../tutorials/media/backuptocloud-storage-credential-mapping.gif "mapping storage account to sql credentials")</span></span>  
  
###  <a name="azure-blob-storage-service"></a><a name="Blob"></a><span data-ttu-id="a1218-132">Service de stockage d’objets BLOB Azure</span><span class="sxs-lookup"><span data-stu-id="a1218-132">Azure Blob Storage Service</span></span>  
 <span data-ttu-id="a1218-133">**Compte de stockage :** Le compte de stockage constitue le point de départ de tous les services de stockage.</span><span class="sxs-lookup"><span data-stu-id="a1218-133">**Storage Account:** The storage account is the starting point for all storage services.</span></span> <span data-ttu-id="a1218-134">Pour accéder au service de stockage d’objets BLOB Azure, commencez par créer un compte de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="a1218-134">To access the Azure Blob Storage service, first create an Azure storage account.</span></span> <span data-ttu-id="a1218-135">Le **nom du compte de stockage** et ses propriétés de **clé d’accès** sont requis pour l’authentification auprès du service de stockage d’objets BLOB Azure et de ses composants.</span><span class="sxs-lookup"><span data-stu-id="a1218-135">The **storage account name** and its **access key** properties are required to authenticate to the Azure Blob Storage service and its components.</span></span>  
  
 <span data-ttu-id="a1218-136">**Conteneur :** Un conteneur permet de regrouper un ensemble d’objets BLOB et peut stocker un nombre illimité d’objets BLOB.</span><span class="sxs-lookup"><span data-stu-id="a1218-136">**Container:** A container provides a grouping of a set of Blobs, and can store an unlimited number of Blobs.</span></span> <span data-ttu-id="a1218-137">Pour écrire une [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sauvegarde dans le service d’objets BLOB Azure, vous devez avoir au moins le conteneur racine créé.</span><span class="sxs-lookup"><span data-stu-id="a1218-137">To write a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup to the Azure Blob service, you must have at least the root container created.</span></span>  
  
 <span data-ttu-id="a1218-138">**Objet blob :** Fichier de tout type et de toute taille.</span><span class="sxs-lookup"><span data-stu-id="a1218-138">**Blob:** A file of any type and size.</span></span> <span data-ttu-id="a1218-139">Il existe deux types d’objets BLOB qui peuvent être stockés dans le service de stockage d’objets BLOB Azure : les objets BLOB de blocs et de pages.</span><span class="sxs-lookup"><span data-stu-id="a1218-139">There are two types of blobs that can be stored in the Azure Blob storage service: block and page blobs.</span></span> <span data-ttu-id="a1218-140">La sauvegarde [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilise des objets blob de pages en tant que type d'objet blob.</span><span class="sxs-lookup"><span data-stu-id="a1218-140">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup uses page Blobs as the Blob type.</span></span> <span data-ttu-id="a1218-141">Les objets BLOB sont adressables à l’aide du format d’URL suivant : https:// \<storage account> . blob.Core.Windows.net/\<container>/\<blob></span><span class="sxs-lookup"><span data-stu-id="a1218-141">Blobs are addressable using the following URL format: https://\<storage account>.blob.core.windows.net/\<container>/\<blob></span></span>  
  
 <span data-ttu-id="a1218-142">![Stockage Blob Azure](../../database-engine/media/backuptocloud-blobarchitecture.gif "Stockage Blob Azure")</span><span class="sxs-lookup"><span data-stu-id="a1218-142">![Azure Blob Storage](../../database-engine/media/backuptocloud-blobarchitecture.gif "Azure Blob Storage")</span></span>  
  
 <span data-ttu-id="a1218-143">Pour plus d’informations sur le service de stockage d’objets BLOB Azure, consultez la page [utilisation du service de stockage d’objets BLOB Azure](https://www.windowsazure.com/develop/net/how-to-guides/blob-storage/)</span><span class="sxs-lookup"><span data-stu-id="a1218-143">For more information about the Azure Blob storage service, see [How to use the Azure Blob Storage Service](https://www.windowsazure.com/develop/net/how-to-guides/blob-storage/)</span></span>  
  
 <span data-ttu-id="a1218-144">Pour plus d’informations sur les blobs, consultez [Présentation des objets blob de blocs et des objets blob de pages](https://msdn.microsoft.com/library/windowsazure/ee691964.aspx)</span><span class="sxs-lookup"><span data-stu-id="a1218-144">For more information about page Blobs, see [Understanding Block and Page Blobs](https://msdn.microsoft.com/library/windowsazure/ee691964.aspx)</span></span>  
  
###  <a name="ssnoversion-components"></a><a name="sqlserver"></a> <span data-ttu-id="a1218-145">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Composants</span><span class="sxs-lookup"><span data-stu-id="a1218-145">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Components</span></span>  
 <span data-ttu-id="a1218-146">**URL :** Une URL spécifie un URI (Uniform Resource Identifier) pour un fichier de sauvegarde unique.</span><span class="sxs-lookup"><span data-stu-id="a1218-146">**URL:** A URL specifies a Uniform Resource Identifier (URI) to a unique backup file.</span></span> <span data-ttu-id="a1218-147">L'URL est utilisée pour indiquer l'emplacement et le nom du fichier de sauvegarde de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a1218-147">The URL is used to provide the location and name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup file.</span></span> <span data-ttu-id="a1218-148">Dans cette implémentation, la seule URL valide est celle qui pointe vers un objet blob de pages dans un compte de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="a1218-148">In this implementation, the only valid URL is one that points to a page Blob in an Azure storage account.</span></span> <span data-ttu-id="a1218-149">L'URL doit pointer vers un objet blob réel et pas un simple conteneur.</span><span class="sxs-lookup"><span data-stu-id="a1218-149">The URL must point to an actual Blob, not just a container.</span></span> <span data-ttu-id="a1218-150">Si l'objet blob n'existe pas, il est créé.</span><span class="sxs-lookup"><span data-stu-id="a1218-150">If the Blob does not exist, it is created.</span></span> <span data-ttu-id="a1218-151">Si un objet BLOB existant est spécifié, la sauvegarde échoue, sauf si l’option « WITH FORMAT » est spécifiée.</span><span class="sxs-lookup"><span data-stu-id="a1218-151">If an existing Blob is specified, BACKUP fails, unless the "WITH FORMAT" option is specified.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="a1218-152">Si vous choisissez de copier et de charger un fichier de sauvegarde dans le service de stockage d’objets BLOB Azure, utilisez l’objet blob de pages comme option de stockage.</span><span class="sxs-lookup"><span data-stu-id="a1218-152">If you choose to copy and upload a backup file to the Azure Blob storage service, use page blob as your storage option.</span></span> <span data-ttu-id="a1218-153">Les restaurations à partir d'objets blob de blocs ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="a1218-153">Restores from Block Blobs are not supported.</span></span> <span data-ttu-id="a1218-154">Une restauration à partir d'un type d'objet blob de blocs échoue avec une erreur.</span><span class="sxs-lookup"><span data-stu-id="a1218-154">RESTORE from a block blob type fails with an error.</span></span>  
  
 <span data-ttu-id="a1218-155">Voici un exemple de valeur d’URL : http [s]://ACCOUNTNAME.Blob.core.windows.net/ \<CONTAINER> / \<FILENAME.bak> .</span><span class="sxs-lookup"><span data-stu-id="a1218-155">Here is a sample URL value: http[s]://ACCOUNTNAME.Blob.core.windows.net/\<CONTAINER>/\<FILENAME.bak>.</span></span> <span data-ttu-id="a1218-156">HTTPS n'est pas obligatoire, mais est recommandé.</span><span class="sxs-lookup"><span data-stu-id="a1218-156">HTTPS is not required, but is recommended.</span></span>  
  
 <span data-ttu-id="a1218-157">**Informations d’identification :** Les informations d'identification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont des objets utilisés pour stocker les informations d'authentification requises pour la connexion à une ressource en dehors de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a1218-157">**Credential:** A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] credential is an object that is used to store authentication information required to connect to a resource outside of SQL Server.</span></span>  <span data-ttu-id="a1218-158">Ici, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] les processus de sauvegarde et de restauration utilisent les informations d’identification pour s’authentifier auprès du service de stockage d’objets BLOB Azure.</span><span class="sxs-lookup"><span data-stu-id="a1218-158">Here, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup and restore processes use credential to authenticate to the Azure Blob storage service.</span></span> <span data-ttu-id="a1218-159">Les informations d'identification contiennent le nom du compte de stockage et ses valeurs de **clé d'accès** .</span><span class="sxs-lookup"><span data-stu-id="a1218-159">The Credential stores the name of the storage account and the storage account **access key** values.</span></span> <span data-ttu-id="a1218-160">Une fois les informations d'identification créées, vous devez les spécifier dans l'option WITH CREDENTIAL lorsque vous publiez des instructions BACKUP/RESTORE.</span><span class="sxs-lookup"><span data-stu-id="a1218-160">Once the credential is created, it must be specified in the WITH CREDENTIAL option when issuing the BACKUP/RESTORE statements.</span></span> <span data-ttu-id="a1218-161">Pour plus d'informations sur l'affichage, la copie ou la régénération des **access keys**de compte de stockage, consultez [Afficher, copier et régénérer les clés d'accès d'un compte de stockage Windows Azure](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span><span class="sxs-lookup"><span data-stu-id="a1218-161">For more information about how to view, copy or regenerate storage account **access keys**, see [Storage Account Access Keys](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span></span>  
  
 <span data-ttu-id="a1218-162">Pour obtenir des instructions détaillées sur la création d'informations d'identification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consultez l'exemple [Create a Credential](#credential) plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="a1218-162">For step by step instructions about how to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Credential, see [Create a Credential](#credential) example later in this topic.</span></span>  
  
 <span data-ttu-id="a1218-163">Pour plus d’informations sur les informations d’identification en général, consultez [Informations d’identification](../security/authentication-access/credentials-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="a1218-163">For general information about credentials, see [Credentials](../security/authentication-access/credentials-database-engine.md)</span></span>  
  
 <span data-ttu-id="a1218-164">Pour plus d’informations sur d’autres exemples d’utilisation des informations d’identification, consultez [créer un Proxy SQL Server Agent](../../ssms/agent/create-a-sql-server-agent-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="a1218-164">For information, on other examples where credentials are used, see [Create a SQL Server Agent Proxy](../../ssms/agent/create-a-sql-server-agent-proxy.md).</span></span>  
  
###  <a name="limitations"></a><a name="limitations"></a> <span data-ttu-id="a1218-165">Limitations</span><span class="sxs-lookup"><span data-stu-id="a1218-165">Limitations</span></span>  
  
-   <span data-ttu-id="a1218-166">La sauvegarde dans le stockage Premium n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="a1218-166">Backup to premium storage is not supported.</span></span>  
  
-   <span data-ttu-id="a1218-167">La taille de sauvegarde maximale prise en charge est de 1 To.</span><span class="sxs-lookup"><span data-stu-id="a1218-167">The maximum backup size supported is 1 TB.</span></span>  
  
-   <span data-ttu-id="a1218-168">Publiez des instructions de sauvegarde ou de restauration à l'aide de TSQL, de SMO ou d'applets de commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a1218-168">You can issue backup or restore statements by using TSQL, SMO, or PowerShell cmdlets.</span></span> <span data-ttu-id="a1218-169">Une sauvegarde ou une restauration à partir du service de stockage d’objets BLOB Azure à l’aide de SQL Server Management Studio Assistant de sauvegarde ou de restauration n’est pas activée actuellement.</span><span class="sxs-lookup"><span data-stu-id="a1218-169">A backup to or restoring from the Azure Blob storage service by using SQL Server Management Studio Backup or Restore wizard is not currently enabled.</span></span>  
  
-   <span data-ttu-id="a1218-170">La création d'un nom d'unité logique n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="a1218-170">Creating a logical device name is not supported.</span></span> <span data-ttu-id="a1218-171">Par conséquent, l'ajout d'une URL comme unité de sauvegarde à l'aide de sp_dumpdevice ou de SQL Server Management Studio n'est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="a1218-171">So adding URL as a backup device using sp_dumpdevice or through SQL Server Management Studio is not supported.</span></span>  
  
-   <span data-ttu-id="a1218-172">L'ajout d'objets blob de sauvegarde existants n'est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="a1218-172">Appending to existing backup blobs is not supported.</span></span> <span data-ttu-id="a1218-173">Les sauvegardes vers un objet blob existant peuvent uniquement être remplacées à l'aide de l'option WITH FORMAT.</span><span class="sxs-lookup"><span data-stu-id="a1218-173">Backups to an existing Blob can only be overwritten by using the WITH FORMAT option.</span></span>  
  
-   <span data-ttu-id="a1218-174">La sauvegarde vers plusieurs objets blob dans le cadre d'une opération de sauvegarde n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="a1218-174">Backup to multiple blobs in a single backup operation is not supported.</span></span> <span data-ttu-id="a1218-175">Par exemple, le code suivant retourne une erreur :</span><span class="sxs-lookup"><span data-stu-id="a1218-175">For example, the following returns an error:</span></span>  
  
    ```sql
    BACKUP DATABASE AdventureWorks2012
    TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_1.bak'
       URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_2.bak'
          WITH CREDENTIAL = 'mycredential'
         ,STATS = 5;  
    GO
    ```  
  
-   <span data-ttu-id="a1218-176">La spécification d'une taille de bloc avec `BACKUP` n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="a1218-176">Specifying a block size with `BACKUP` is not supported.</span></span>  
  
-   <span data-ttu-id="a1218-177">La spécification de `MAXTRANSFERSIZE` n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="a1218-177">Specifying `MAXTRANSFERSIZE` is not supported.</span></span>  
  
-   <span data-ttu-id="a1218-178">La spécification des options backupset `RETAINDAYS` et `EXPIREDATE` n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="a1218-178">Specifying backupset options - `RETAINDAYS` and `EXPIREDATE` are not supported.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a1218-179">est soumis à une limite de 259 caractères pour le nom d'une unité de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="a1218-179">has a maximum limit of 259 characters for a backup device name.</span></span> <span data-ttu-id="a1218-180">BACKUP TO URL utilise 36 caractères pour les éléments requis utilisés pour spécifier l’URL « https://.blob.core.windows.net//.bak  », ce qui laisse 223 caractères pour les noms de compte, de conteneur et d’objet blob réunis.</span><span class="sxs-lookup"><span data-stu-id="a1218-180">The BACKUP TO URL consumes 36 characters for the required elements used to specify the URL - 'https://.blob.core.windows.net//.bak', leaving 223 characters for account, container, and blob names put together.</span></span>  
  
###  <a name="support-for-backuprestore-statements"></a><a name="Support"></a> <span data-ttu-id="a1218-181">Prise en charge des instructions de sauvegarde/restauration</span><span class="sxs-lookup"><span data-stu-id="a1218-181">Support for Backup/Restore Statements</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="a1218-182">Instruction de sauvegarde/restauration</span><span class="sxs-lookup"><span data-stu-id="a1218-182">Backup/Restore Statement</span></span>|<span data-ttu-id="a1218-183">Prise en charge</span><span class="sxs-lookup"><span data-stu-id="a1218-183">Supported</span></span>|<span data-ttu-id="a1218-184">Exceptions</span><span class="sxs-lookup"><span data-stu-id="a1218-184">Exceptions</span></span>|<span data-ttu-id="a1218-185">Commentaires</span><span class="sxs-lookup"><span data-stu-id="a1218-185">Comments</span></span>|  
|<span data-ttu-id="a1218-186">BACKUP</span><span class="sxs-lookup"><span data-stu-id="a1218-186">BACKUP</span></span>|<span data-ttu-id="a1218-187">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-187">&#x2713;</span></span>|<span data-ttu-id="a1218-188">BLOCKSIZE et MAXTRANSFERSIZE ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="a1218-188">BLOCKSIZE, and MAXTRANSFERSIZE are not supported.</span></span>|<span data-ttu-id="a1218-189">Requiert la spécification de WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="a1218-189">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="a1218-190">RESTORE</span><span class="sxs-lookup"><span data-stu-id="a1218-190">RESTORE</span></span>|<span data-ttu-id="a1218-191">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-191">&#x2713;</span></span>||<span data-ttu-id="a1218-192">Requiert la spécification de WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="a1218-192">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="a1218-193">RESTORE FILELISTONLY</span><span class="sxs-lookup"><span data-stu-id="a1218-193">RESTORE FILELISTONLY</span></span>|<span data-ttu-id="a1218-194">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-194">&#x2713;</span></span>||<span data-ttu-id="a1218-195">Requiert la spécification de WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="a1218-195">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="a1218-196">RESTORE HEADERONLY</span><span class="sxs-lookup"><span data-stu-id="a1218-196">RESTORE HEADERONLY</span></span>|<span data-ttu-id="a1218-197">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-197">&#x2713;</span></span>||<span data-ttu-id="a1218-198">Requiert la spécification de WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="a1218-198">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="a1218-199">RESTORE LABELONLY</span><span class="sxs-lookup"><span data-stu-id="a1218-199">RESTORE LABELONLY</span></span>|<span data-ttu-id="a1218-200">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-200">&#x2713;</span></span>||<span data-ttu-id="a1218-201">Requiert la spécification de WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="a1218-201">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="a1218-202">RESTORE VERIFYONLY</span><span class="sxs-lookup"><span data-stu-id="a1218-202">RESTORE VERIFYONLY</span></span>|<span data-ttu-id="a1218-203">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-203">&#x2713;</span></span>||<span data-ttu-id="a1218-204">Requiert la spécification de WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="a1218-204">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="a1218-205">RESTORE REWINDONLY</span><span class="sxs-lookup"><span data-stu-id="a1218-205">RESTORE REWINDONLY</span></span>|<span data-ttu-id="a1218-206">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-206">&#x2713;</span></span>|||  
  
 <span data-ttu-id="a1218-207">Pour plus d’informations sur la syntaxe et les instructions de sauvegarde, consultez [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a1218-207">For syntax and general information about backup statements, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
 <span data-ttu-id="a1218-208">Pour plus d’informations sur la syntaxe et les instructions de restauration, consultez [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a1218-208">For syntax and general information about restore statements, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
### <a name="support-for-backup-arguments"></a><span data-ttu-id="a1218-209">Prise en charge des arguments de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="a1218-209">Support for Backup Arguments</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="a1218-210">Argument</span><span class="sxs-lookup"><span data-stu-id="a1218-210">Argument</span></span>|<span data-ttu-id="a1218-211">Prise en charge</span><span class="sxs-lookup"><span data-stu-id="a1218-211">Supported</span></span>|<span data-ttu-id="a1218-212">Exception</span><span class="sxs-lookup"><span data-stu-id="a1218-212">Exception</span></span>|<span data-ttu-id="a1218-213">Commentaires</span><span class="sxs-lookup"><span data-stu-id="a1218-213">Comments</span></span>|  
|<span data-ttu-id="a1218-214">DATABASE</span><span class="sxs-lookup"><span data-stu-id="a1218-214">DATABASE</span></span>|<span data-ttu-id="a1218-215">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-215">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-216">LOG</span><span class="sxs-lookup"><span data-stu-id="a1218-216">LOG</span></span>|<span data-ttu-id="a1218-217">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-217">&#x2713;</span></span>|||  
||  
|<span data-ttu-id="a1218-218">TO (URL)</span><span class="sxs-lookup"><span data-stu-id="a1218-218">TO (URL)</span></span>|<span data-ttu-id="a1218-219">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-219">&#x2713;</span></span>|<span data-ttu-id="a1218-220">Contrairement à DISK et TAPE, URL ne prend pas en charge la spécification ou la création d'un nom logique.</span><span class="sxs-lookup"><span data-stu-id="a1218-220">Unlike DISK and TAPE, URL does not support specifying or creating a logical name.</span></span>|<span data-ttu-id="a1218-221">Cet argument est utilisé pour spécifier le chemin d'accès de l'URL du fichier de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="a1218-221">This argument is used to specify the URL path for the backup file.</span></span>|  
|<span data-ttu-id="a1218-222">MIRROR TO</span><span class="sxs-lookup"><span data-stu-id="a1218-222">MIRROR TO</span></span>|<span data-ttu-id="a1218-223">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-223">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-224">**WITH OPTIONS :**</span><span class="sxs-lookup"><span data-stu-id="a1218-224">**WITH OPTIONS:**</span></span>||||  
|<span data-ttu-id="a1218-225">CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="a1218-225">CREDENTIAL</span></span>|<span data-ttu-id="a1218-226">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-226">&#x2713;</span></span>||<span data-ttu-id="a1218-227">WITH CREDENTIAL est pris en charge uniquement lors de l’utilisation de l’option BACKUP TO URL pour sauvegarder dans le service de stockage d’objets BLOB Azure.</span><span class="sxs-lookup"><span data-stu-id="a1218-227">WITH CREDENTIAL is only supported when using BACKUP TO URL option to back up to the Azure Blob storage service.</span></span>|  
|<span data-ttu-id="a1218-228">DIFFERENTIAL</span><span class="sxs-lookup"><span data-stu-id="a1218-228">DIFFERENTIAL</span></span>|<span data-ttu-id="a1218-229">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-229">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-230">COPY_ONLY</span><span class="sxs-lookup"><span data-stu-id="a1218-230">COPY_ONLY</span></span>|<span data-ttu-id="a1218-231">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-231">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-232">COMPRESSION&#124;NO_COMPRESSION</span><span class="sxs-lookup"><span data-stu-id="a1218-232">COMPRESSION&#124;NO_COMPRESSION</span></span>|<span data-ttu-id="a1218-233">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-233">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-234">Description</span><span class="sxs-lookup"><span data-stu-id="a1218-234">DESCRIPTION</span></span>|<span data-ttu-id="a1218-235">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-235">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-236">NAME</span><span class="sxs-lookup"><span data-stu-id="a1218-236">NAME</span></span>|<span data-ttu-id="a1218-237">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-237">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-238">EXPIREDATE &#124; RETAINDAYS</span><span class="sxs-lookup"><span data-stu-id="a1218-238">EXPIREDATE &#124; RETAINDAYS</span></span>|<span data-ttu-id="a1218-239">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-239">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-240">NOINIT &#124; INIT</span><span class="sxs-lookup"><span data-stu-id="a1218-240">NOINIT &#124; INIT</span></span>|<span data-ttu-id="a1218-241">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-241">&#x2713;</span></span>||<span data-ttu-id="a1218-242">Cette option est ignorée si elle est utilisée.</span><span class="sxs-lookup"><span data-stu-id="a1218-242">This option is ignored if used.</span></span><br /><br /> <span data-ttu-id="a1218-243">L'ajout aux objets blob n'est pas possible.</span><span class="sxs-lookup"><span data-stu-id="a1218-243">Appending to blobs is not possible.</span></span> <span data-ttu-id="a1218-244">Pour remplacer une sauvegarde, utilisez l'argument FORMAT.</span><span class="sxs-lookup"><span data-stu-id="a1218-244">To overwrite a backup use the FORMAT argument.</span></span>|  
|<span data-ttu-id="a1218-245">NOSKIP &#124; SKIP</span><span class="sxs-lookup"><span data-stu-id="a1218-245">NOSKIP &#124; SKIP</span></span>|<span data-ttu-id="a1218-246">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-246">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-247">NOFORMAT &#124; FORMAT</span><span class="sxs-lookup"><span data-stu-id="a1218-247">NOFORMAT &#124; FORMAT</span></span>|<span data-ttu-id="a1218-248">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-248">&#x2713;</span></span>||<span data-ttu-id="a1218-249">Cette option est ignorée si elle est utilisée.</span><span class="sxs-lookup"><span data-stu-id="a1218-249">This option is ignored if used.</span></span><br /><br /> <span data-ttu-id="a1218-250">Une sauvegarde effectuée sur un objet blob existant échoue à moins que WITH FORMAT ne soit spécifié.</span><span class="sxs-lookup"><span data-stu-id="a1218-250">A backup taken to an existing blob fails unless WITH FORMAT is specified.</span></span> <span data-ttu-id="a1218-251">L'objet blob existant est remplacé lorsque WITH FORMAT est spécifié.</span><span class="sxs-lookup"><span data-stu-id="a1218-251">The existing blob is overwritten when WITH FORMAT is specified.</span></span>|  
|<span data-ttu-id="a1218-252">MEDIADESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a1218-252">MEDIADESCRIPTION</span></span>|<span data-ttu-id="a1218-253">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-253">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-254">MEDIANAME</span><span class="sxs-lookup"><span data-stu-id="a1218-254">MEDIANAME</span></span>|<span data-ttu-id="a1218-255">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-255">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-256">BLOCKSIZE</span><span class="sxs-lookup"><span data-stu-id="a1218-256">BLOCKSIZE</span></span>|<span data-ttu-id="a1218-257">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-257">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-258">BUFFERCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1218-258">BUFFERCOUNT</span></span>|<span data-ttu-id="a1218-259">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-259">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-260">MAXTRANSFERSIZE</span><span class="sxs-lookup"><span data-stu-id="a1218-260">MAXTRANSFERSIZE</span></span>|<span data-ttu-id="a1218-261">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-261">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-262">NO_CHECKSUM &#124; CHECKSUM</span><span class="sxs-lookup"><span data-stu-id="a1218-262">NO_CHECKSUM &#124; CHECKSUM</span></span>|<span data-ttu-id="a1218-263">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-263">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-264">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span><span class="sxs-lookup"><span data-stu-id="a1218-264">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span></span>|<span data-ttu-id="a1218-265">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-265">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-266">STATS</span><span class="sxs-lookup"><span data-stu-id="a1218-266">STATS</span></span>|<span data-ttu-id="a1218-267">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-267">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-268">REWIND &#124; NOREWIND</span><span class="sxs-lookup"><span data-stu-id="a1218-268">REWIND &#124; NOREWIND</span></span>|<span data-ttu-id="a1218-269">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-269">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-270">UNLOAD &#124; NOUNLOAD</span><span class="sxs-lookup"><span data-stu-id="a1218-270">UNLOAD &#124; NOUNLOAD</span></span>|<span data-ttu-id="a1218-271">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-271">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-272">NORECOVERY &#124; STANDBY</span><span class="sxs-lookup"><span data-stu-id="a1218-272">NORECOVERY &#124; STANDBY</span></span>|<span data-ttu-id="a1218-273">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-273">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-274">NO_TRUNCATE</span><span class="sxs-lookup"><span data-stu-id="a1218-274">NO_TRUNCATE</span></span>|<span data-ttu-id="a1218-275">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-275">&#x2713;</span></span>|||  
  
 <span data-ttu-id="a1218-276">Pour plus d’informations sur les arguments de Backup, consultez [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a1218-276">For more information about backup arguments, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
### <a name="support-for-restore-arguments"></a><span data-ttu-id="a1218-277">Prise en charge des arguments de restauration</span><span class="sxs-lookup"><span data-stu-id="a1218-277">Support for Restore Arguments</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="a1218-278">Argument</span><span class="sxs-lookup"><span data-stu-id="a1218-278">Argument</span></span>|<span data-ttu-id="a1218-279">Prise en charge</span><span class="sxs-lookup"><span data-stu-id="a1218-279">Supported</span></span>|<span data-ttu-id="a1218-280">Exceptions</span><span class="sxs-lookup"><span data-stu-id="a1218-280">Exceptions</span></span>|<span data-ttu-id="a1218-281">Commentaires</span><span class="sxs-lookup"><span data-stu-id="a1218-281">Comments</span></span>|  
|<span data-ttu-id="a1218-282">DATABASE</span><span class="sxs-lookup"><span data-stu-id="a1218-282">DATABASE</span></span>|<span data-ttu-id="a1218-283">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-283">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-284">LOG</span><span class="sxs-lookup"><span data-stu-id="a1218-284">LOG</span></span>|<span data-ttu-id="a1218-285">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-285">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-286">FROM (URL)</span><span class="sxs-lookup"><span data-stu-id="a1218-286">FROM (URL)</span></span>|<span data-ttu-id="a1218-287">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-287">&#x2713;</span></span>||<span data-ttu-id="a1218-288">L'argument FROM URL est utilisé pour spécifier le chemin d'accès de l'URL du fichier de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="a1218-288">The FROM URL argument is used to specify the URL path for the backup file.</span></span>|  
|<span data-ttu-id="a1218-289">**WITH Options:**</span><span class="sxs-lookup"><span data-stu-id="a1218-289">**WITH Options:**</span></span>||||  
|<span data-ttu-id="a1218-290">CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="a1218-290">CREDENTIAL</span></span>|<span data-ttu-id="a1218-291">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-291">&#x2713;</span></span>||<span data-ttu-id="a1218-292">WITH CREDENTIAL est pris en charge uniquement lors de l’utilisation de l’option Restore FROM URL pour restaurer à partir du service de stockage d’objets BLOB Azure.</span><span class="sxs-lookup"><span data-stu-id="a1218-292">WITH CREDENTIAL is only supported when using RESTORE FROM URL option to restore from Azure Blob Storage service.</span></span>|  
|<span data-ttu-id="a1218-293">PARTIAL</span><span class="sxs-lookup"><span data-stu-id="a1218-293">PARTIAL</span></span>|<span data-ttu-id="a1218-294">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-294">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-295">RECOVERY &#124; NORECOVERY &#124; STANDBY</span><span class="sxs-lookup"><span data-stu-id="a1218-295">RECOVERY &#124; NORECOVERY &#124; STANDBY</span></span>|<span data-ttu-id="a1218-296">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-296">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-297">LOADHISTORY</span><span class="sxs-lookup"><span data-stu-id="a1218-297">LOADHISTORY</span></span>|<span data-ttu-id="a1218-298">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-298">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-299">MOVE</span><span class="sxs-lookup"><span data-stu-id="a1218-299">MOVE</span></span>|<span data-ttu-id="a1218-300">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-300">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-301">REPLACE</span><span class="sxs-lookup"><span data-stu-id="a1218-301">REPLACE</span></span>|<span data-ttu-id="a1218-302">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-302">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-303">RESTART</span><span class="sxs-lookup"><span data-stu-id="a1218-303">RESTART</span></span>|<span data-ttu-id="a1218-304">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-304">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-305">RESTRICTED_USER</span><span class="sxs-lookup"><span data-stu-id="a1218-305">RESTRICTED_USER</span></span>|<span data-ttu-id="a1218-306">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-306">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-307">FILE</span><span class="sxs-lookup"><span data-stu-id="a1218-307">FILE</span></span>|<span data-ttu-id="a1218-308">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-308">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-309">PASSWORD</span><span class="sxs-lookup"><span data-stu-id="a1218-309">PASSWORD</span></span>|<span data-ttu-id="a1218-310">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-310">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-311">MEDIANAME</span><span class="sxs-lookup"><span data-stu-id="a1218-311">MEDIANAME</span></span>|<span data-ttu-id="a1218-312">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-312">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-313">MEDIAPASSWORD</span><span class="sxs-lookup"><span data-stu-id="a1218-313">MEDIAPASSWORD</span></span>|<span data-ttu-id="a1218-314">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-314">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-315">BLOCKSIZE</span><span class="sxs-lookup"><span data-stu-id="a1218-315">BLOCKSIZE</span></span>|<span data-ttu-id="a1218-316">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-316">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-317">BUFFERCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1218-317">BUFFERCOUNT</span></span>|<span data-ttu-id="a1218-318">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-318">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-319">MAXTRANSFERSIZE</span><span class="sxs-lookup"><span data-stu-id="a1218-319">MAXTRANSFERSIZE</span></span>|<span data-ttu-id="a1218-320">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-320">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-321">CHECKSUM &#124; NO_CHECKSUM</span><span class="sxs-lookup"><span data-stu-id="a1218-321">CHECKSUM &#124; NO_CHECKSUM</span></span>|<span data-ttu-id="a1218-322">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-322">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-323">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span><span class="sxs-lookup"><span data-stu-id="a1218-323">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span></span>|<span data-ttu-id="a1218-324">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-324">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-325">FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="a1218-325">FILESTREAM</span></span>|<span data-ttu-id="a1218-326">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-326">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-327">STATS</span><span class="sxs-lookup"><span data-stu-id="a1218-327">STATS</span></span>|<span data-ttu-id="a1218-328">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-328">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-329">REWIND &#124; NOREWIND</span><span class="sxs-lookup"><span data-stu-id="a1218-329">REWIND &#124; NOREWIND</span></span>|<span data-ttu-id="a1218-330">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-330">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-331">UNLOAD &#124; NOUNLOAD</span><span class="sxs-lookup"><span data-stu-id="a1218-331">UNLOAD &#124; NOUNLOAD</span></span>|<span data-ttu-id="a1218-332">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-332">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-333">KEEP_REPLICATION</span><span class="sxs-lookup"><span data-stu-id="a1218-333">KEEP_REPLICATION</span></span>|<span data-ttu-id="a1218-334">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-334">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-335">KEEP_CDC</span><span class="sxs-lookup"><span data-stu-id="a1218-335">KEEP_CDC</span></span>|<span data-ttu-id="a1218-336">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-336">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-337">ENABLE_BROKER &#124; ERROR_BROKER_CONVERSATIONS &#124; NEW_BROKER</span><span class="sxs-lookup"><span data-stu-id="a1218-337">ENABLE_BROKER &#124; ERROR_BROKER_CONVERSATIONS &#124; NEW_BROKER</span></span>|<span data-ttu-id="a1218-338">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-338">&#x2713;</span></span>|||  
|<span data-ttu-id="a1218-339">STOPAT &#124; STOPATMARK &#124; STOPBEFOREMARK</span><span class="sxs-lookup"><span data-stu-id="a1218-339">STOPAT &#124; STOPATMARK &#124; STOPBEFOREMARK</span></span>|<span data-ttu-id="a1218-340">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="a1218-340">&#x2713;</span></span>|||  
  
 <span data-ttu-id="a1218-341">Pour plus d’informations sur les arguments de Restore, consultez [Arguments RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a1218-341">For more information about Restore arguments, see [RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql).</span></span>  
  
##  <a name="using-backup-task-in-sql-server-management-studio"></a><a name="BackupTaskSSMS"></a><span data-ttu-id="a1218-342">Utilisation de la tâche de sauvegarde dans SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a1218-342">Using Backup Task in SQL Server Management Studio</span></span>  
 <span data-ttu-id="a1218-343">La tâche de sauvegarde de SQL Server Management Studio a été améliorée de façon à inclure l’URL comme l’une des options de destination, ainsi que d’autres objets de prise en charge nécessaires à la sauvegarde dans le stockage Azure, comme les informations d’identification SQL.</span><span class="sxs-lookup"><span data-stu-id="a1218-343">The Backup task in SQL Server Management Studio has been enhanced to include URL as one of the destination options, and other supporting objects required to backup to Azure storage like the SQL Credential.</span></span>  
  
 <span data-ttu-id="a1218-344">Les étapes suivantes décrivent les modifications apportées à la tâche sauvegarder la base de données pour permettre la sauvegarde vers le stockage Azure :</span><span class="sxs-lookup"><span data-stu-id="a1218-344">The following steps describe the changes made to the Back Up Database task to allow for backing up to Azure storage.:</span></span>  
  
1.  <span data-ttu-id="a1218-345">Démarrez SQL Server Management Studio et connectez-vous à une instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a1218-345">Start SQL Server Management Studio and connect to the SQL Server instance.</span></span>  <span data-ttu-id="a1218-346">Sélectionnez une base de données que vous souhaitez sauvegarder, cliquez avec le bouton droit sur **tâches**, puis sélectionnez **sauvegarder..**. La boîte de dialogue sauvegarder la base de données s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="a1218-346">Select a database you want to backup, and right click on **Tasks**, and select **Back Up..**. This opens the Back Up Database dialog box.</span></span>  
  
2.  <span data-ttu-id="a1218-347">Sur la page général, l’option **URL** permet de créer une sauvegarde dans le stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="a1218-347">On the general page the **URL** option is used to create a backup to Azure storage.</span></span> <span data-ttu-id="a1218-348">Lorsque vous sélectionnez cette option, les autres options activées sur cette page s'affichent :</span><span class="sxs-lookup"><span data-stu-id="a1218-348">When you select this option, you see other options enabled on this page:</span></span>  
  
    1.  <span data-ttu-id="a1218-349">**Nom du fichier :** nom du fichier de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="a1218-349">**File Name:** Name of the backup file.</span></span>  
  
    2.  <span data-ttu-id="a1218-350">**Informations d'identification SQL :** spécifiez des informations d'identification SQL Server existantes, ou pour en créer des nouvelles, cliquez sur **Créer** à côté de la zone Informations d'identification SQL.</span><span class="sxs-lookup"><span data-stu-id="a1218-350">**SQL Credential:** You can either specify an existing SQL Server Credential, or can create a new one by clicking on the **Create** next to the SQL Credential box.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="a1218-351">La boîte de dialogue qui s'ouvre lorsque vous cliquez sur **Créer** requiert un certificat de gestion ou le profil de publication de l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="a1218-351">The dialog that opens when you click **Create** requires a management certificate or the publishing profile for the subscription.</span></span> <span data-ttu-id="a1218-352">SQL Server prend actuellement en charge la version 2.0 du profil de publication.</span><span class="sxs-lookup"><span data-stu-id="a1218-352">SQL Server currently supports publishing profile version 2.0.</span></span> <span data-ttu-id="a1218-353">Pour télécharger la version prise en charge du profil de publication, consultez [Télécharger le profil de publication 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span><span class="sxs-lookup"><span data-stu-id="a1218-353">To download the supported version of the publishing profile, see [Download Publishing Profile 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span></span>  
        >   
        >  <span data-ttu-id="a1218-354">Si vous n'avez pas accès au certificat de gestion ou au profil de publication, vous pouvez créer des informations d'identification SQL en spécifiant le nom du compte de stockage et les informations de clé d'accès à l'aide de Transact-SQL ou de SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="a1218-354">If you do not have access to the management certificate or publishing profile, you can create a SQL Credential by specifying the storage account name and access key information using Transact-SQL or SQL Server Management Studio.</span></span> <span data-ttu-id="a1218-355">Consultez l'exemple de code dans la section [Créer des informations d'identification](#credential) pour créer des informations d'identification à l'aide de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="a1218-355">See the sample code in the [Create a Credential](#credential) section to create a credential using Transact-SQL.</span></span> <span data-ttu-id="a1218-356">Vous pouvez également utiliser SQL Server Management Studio, depuis l'instance du moteur de base de données, et cliquer avec le bouton droit sur **Sécurité**, puis sélectionner **Nouveau**, puis **Informations d'identification**.</span><span class="sxs-lookup"><span data-stu-id="a1218-356">Alternatively, using SQL Server Management Studio, from the database engine instance, right click **Security**, select **New**, and select **Credential**.</span></span> <span data-ttu-id="a1218-357">Spécifiez le nom du compte de stockage pour **Identité** et la clé d'accès dans le champ **Mot de passe** .</span><span class="sxs-lookup"><span data-stu-id="a1218-357">Specify the storage account name for **Identity** and the access key in the **Password** field.</span></span>  
  
    3.  <span data-ttu-id="a1218-358">**Conteneur de stockage Azure :** Nom du conteneur de stockage Azure dans lequel stocker les fichiers de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="a1218-358">**Azure storage container:** The name of the Azure storage container to store the backup files.</span></span>  
  
    4.  <span data-ttu-id="a1218-359">**Préfixe d'URL :** ce préfixe est généré automatiquement en utilisant les informations spécifiées dans les champs décrits dans les étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="a1218-359">**URL prefix:** This is built automatically using the information specified in the fields described in the previous steps.</span></span> <span data-ttu-id="a1218-360">Si vous modifiez manuellement cette valeur, assurez-vous qu'elle correspond aux autres informations spécifiées précédemment.</span><span class="sxs-lookup"><span data-stu-id="a1218-360">If you do edit this value manually, make sure it matches with the other information you provided previously.</span></span> <span data-ttu-id="a1218-361">Par exemple, si vous modifiez l'URL de stockage, vérifiez que les informations d'identification SQL sont définies pour l'authentification auprès du même compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="a1218-361">For example if you modify the storage URL, make sure the SQL Credential is set to authenticate to the same storage account.</span></span>  
  
 <span data-ttu-id="a1218-362">Quand vous sélectionnez URL comme destination, certaines options de la page **Options de support** sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="a1218-362">When you select URL as the destination, certain options in the **Media Options** page are disabled.</span></span>  <span data-ttu-id="a1218-363">Les rubriques suivantes contiennent d'autres informations sur la boîte de dialogue Sauvegarder la base de données :</span><span class="sxs-lookup"><span data-stu-id="a1218-363">The following topics have more information on the Back Up Database dialog:</span></span>  
  
 [<span data-ttu-id="a1218-364">Sauvegarder la base de données &#40;page Général&#41;</span><span class="sxs-lookup"><span data-stu-id="a1218-364">Back Up Database &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
 [<span data-ttu-id="a1218-365">Sauvegarder la base de données &#40;page Options de support&#41;</span><span class="sxs-lookup"><span data-stu-id="a1218-365">Back Up Database &#40;Media Options Page&#41;</span></span>](back-up-database-media-options-page.md)  
  
 [<span data-ttu-id="a1218-366">Sauvegarder la base de données &#40;page Options de sauvegarde&#41;</span><span class="sxs-lookup"><span data-stu-id="a1218-366">Back Up Database &#40;Backup Options Page&#41;</span></span>](back-up-database-backup-options-page.md)  
  
 [<span data-ttu-id="a1218-367">Créer des informations d’identification - Authentification Azure Storage</span><span class="sxs-lookup"><span data-stu-id="a1218-367">Create Credential - Authenticate to Azure Storage</span></span>](create-credential-authenticate-to-azure-storage.md)  
  
##  <a name="sql-server-backup-to-url-using-maintenance-plan-wizard"></a><a name="MaintenanceWiz"></a><span data-ttu-id="a1218-368">SQL Server de la sauvegarde sur une URL à l’aide de l’Assistant Plan de maintenance</span><span class="sxs-lookup"><span data-stu-id="a1218-368">SQL Server Backup to URL Using Maintenance Plan Wizard</span></span>  
 <span data-ttu-id="a1218-369">Comme pour la tâche de sauvegarde décrite précédemment, l’Assistant Plan de maintenance de SQL Server Management Studio a été amélioré pour inclure l' **URL** comme l’une des options de destination, ainsi que d’autres objets de prise en charge nécessaires à la sauvegarde dans le stockage Azure, comme les informations d’identification SQL.</span><span class="sxs-lookup"><span data-stu-id="a1218-369">Similar to the backup task described previously, the Maintenance Plan Wizard in SQL Server Management Studio has been enhanced to include **URL** as one of the destination options, and other supporting objects required to backup to Azure storage like the SQL Credential.</span></span> <span data-ttu-id="a1218-370">Pour plus d'informations, consultez la section **Définir les tâches de sauvegarde** dans [Using Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md#SSMSProcedure).</span><span class="sxs-lookup"><span data-stu-id="a1218-370">For more information, see  the **Define Backup Tasks** section in [Using Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md#SSMSProcedure).</span></span>  
  
##  <a name="restoring-from-azure-storage-using-sql-server-management-studio"></a><a name="RestoreSSMS"></a><span data-ttu-id="a1218-371">Restauration à partir d’Azure Storage à l’aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a1218-371">Restoring from Azure storage Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="a1218-372">Si vous restaurez une base de données, l'option **URL** est incluse en tant qu'unité à partir de laquelle la restauration doit être effectuée.</span><span class="sxs-lookup"><span data-stu-id="a1218-372">If you are restoring a database, **URL** is included as the device to restore from.</span></span> <span data-ttu-id="a1218-373">Les étapes suivantes décrivent les modifications apportées à la tâche de restauration pour autoriser la restauration à partir du stockage Azure :</span><span class="sxs-lookup"><span data-stu-id="a1218-373">Following steps describe the changes in the Restore task to allow restoring from Azure storage:</span></span>  
  
1.  <span data-ttu-id="a1218-374">Lorsque vous sélectionnez **Périphériques** dans la page **Général** de la tâche de restauration dans SQL Server Management Studio, la boîte de dialogue **Sélectionner les unités de sauvegarde** s'ouvre et comprend l'option **URL** comme type de support de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="a1218-374">When you select **Devices** in the **General** page of the Restore task in SQL Server Management Studio, this takes you to the **Select backup devices** dialog box which includes **URL** as a backup media type.</span></span>  
  
2.  <span data-ttu-id="a1218-375">Lorsque vous sélectionnez **URL** et cliquez sur **Ajouter**, la boîte de dialogue **Se connecter au stockage Windows Azure** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="a1218-375">When you select **URL** and click **Add**, this opens the **Connect to Azure storage** dialog.</span></span> <span data-ttu-id="a1218-376">Spécifiez les informations d’identification SQL pour l’authentification auprès du stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="a1218-376">Specify the SQL Credential information to authenticate to Azure storage.</span></span>  
  
3.  <span data-ttu-id="a1218-377">SQL Server se connecte ensuite au stockage Azure à l’aide des informations d’identification SQL que vous avez fournies et ouvre la boîte **de dialogue localiser le fichier de sauvegarde dans Azure** .</span><span class="sxs-lookup"><span data-stu-id="a1218-377">SQL Server then connects to Azure storage using the SQL Credential information you provided and opens the **Locate Backup File in Azure** dialog.</span></span> <span data-ttu-id="a1218-378">Les fichiers de sauvegarde résidant dans le stockage s'affichent sur cette page.</span><span class="sxs-lookup"><span data-stu-id="a1218-378">The backup files residing in the storage are displayed on this page.</span></span> <span data-ttu-id="a1218-379">Sélectionnez le fichier à utiliser pour la restauration, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1218-379">Select the file you want to use to restore and click **OK**.</span></span> <span data-ttu-id="a1218-380">Vous revenez dans la boîte de dialogue **Sélectionner les unités de sauvegarde**, et lorsque vous cliquez sur **OK**, vous revenez dans la boîte de dialogue principale **Restaurer** où vous pourrez effectuer la restauration.</span><span class="sxs-lookup"><span data-stu-id="a1218-380">This takes you back to the **Select Backup Devices** dialog, and Clicking **OK** on this dialog takes you back to the main **Restore** dialog where you will be able complete the restore.</span></span>  <span data-ttu-id="a1218-381">Pour plus d'informations, consultez les rubriques ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="a1218-381">For more information see, the following topics:</span></span>  
  
     [<span data-ttu-id="a1218-382">Restaurer la base de données &#40;page Général&#41;</span><span class="sxs-lookup"><span data-stu-id="a1218-382">Restore Database &#40;General Page&#41;</span></span>](restore-database-general-page.md)  
  
     [<span data-ttu-id="a1218-383">Restaurer la base de données &#40;page Fichiers&#41;</span><span class="sxs-lookup"><span data-stu-id="a1218-383">Restore Database &#40;Files Page&#41;</span></span>](restore-database-files-page.md)  
  
     [<span data-ttu-id="a1218-384">Restaurer la base de données &#40;page Options&#41;</span><span class="sxs-lookup"><span data-stu-id="a1218-384">Restore Database &#40;Options Page&#41;</span></span>](restore-database-options-page.md)  
  
##  <a name="code-examples"></a><a name="Examples"></a> <span data-ttu-id="a1218-385">Exemples de code</span><span class="sxs-lookup"><span data-stu-id="a1218-385">Code Examples</span></span>  
 <span data-ttu-id="a1218-386">Cette section contient les exemples suivants :</span><span class="sxs-lookup"><span data-stu-id="a1218-386">This section contains the following examples.</span></span>  
  
-   [<span data-ttu-id="a1218-387">Créer des informations d'identification</span><span class="sxs-lookup"><span data-stu-id="a1218-387">Create a Credential</span></span>](#credential)  
  
-   [<span data-ttu-id="a1218-388">Sauvegarde d'une base de données complète</span><span class="sxs-lookup"><span data-stu-id="a1218-388">Backing up a complete database</span></span>](#complete)  
  
-   [<span data-ttu-id="a1218-389">Sauvegarde de la base de données et du journal</span><span class="sxs-lookup"><span data-stu-id="a1218-389">Backing up the database and log</span></span>](#databaselog)  
  
-   [<span data-ttu-id="a1218-390">Création d'une sauvegarde complète du groupe de fichiers principal</span><span class="sxs-lookup"><span data-stu-id="a1218-390">Creating a full file backup of the primary filegroup</span></span>](#filebackup)  
  
-   [<span data-ttu-id="a1218-391">Création d'une sauvegarde différentielle du groupe de fichiers principal</span><span class="sxs-lookup"><span data-stu-id="a1218-391">Creating a differential file backup of the primary filegroups</span></span>](#differential)  
  
-   [<span data-ttu-id="a1218-392">Restauration d’une base de données et déplacement des fichiers</span><span class="sxs-lookup"><span data-stu-id="a1218-392">Restoring a database and move files</span></span>](#restoredbwithmove)  
  
-   [<span data-ttu-id="a1218-393">Restauration jusqu'à une date et heure en utilisant STOPAT</span><span class="sxs-lookup"><span data-stu-id="a1218-393">Restoring to a point-in-time using STOPAT</span></span>](#PITR)  
  
###  <a name="create-a-credential"></a><a name="credential"></a> <span data-ttu-id="a1218-394">Créer des informations d'identification</span><span class="sxs-lookup"><span data-stu-id="a1218-394">Create a Credential</span></span>  
 <span data-ttu-id="a1218-395">L’exemple suivant crée des informations d’identification qui stockent les informations d’authentification Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="a1218-395">The following example creates a credential that stores the Azure Storage authentication information.</span></span>  

   ```sql
   IF NOT EXISTS  
   (SELECT * FROM sys.credentials   
   WHERE credential_identity = 'mycredential')  
   CREATE CREDENTIAL mycredential WITH IDENTITY = 'mystorageaccount'  
   ,SECRET = '<storage access key>' ;  
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
   string secret = "<storage access key>";  
  
   // Create a Credential  
   string credentialName = "mycredential";  
   Credential credential = new Credential(server, credentialName);  
   credential.Create(identity, secret);  
   ```  
  
   ```powershell
   # create variables  
   $storageAccount = "mystorageaccount"  
   $storageKey = "<storage access key>"  
   $secureString = ConvertTo-SecureString $storageKey  -asplaintext -force  
   $credentialName = "mycredential"  
  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # Create a credential  
   New-SqlCredential -Name $credentialName -Path $srvpath -Identity $storageAccount -Secret $secureString
   ```  
  
###  <a name="backing-up-a-complete-database"></a><a name="complete"></a><span data-ttu-id="a1218-396">Sauvegarde d’une base de données complète</span><span class="sxs-lookup"><span data-stu-id="a1218-396">Backing up a complete database</span></span>  
 <span data-ttu-id="a1218-397">L’exemple suivant sauvegarde la base de données AdventureWorks2012 dans le service de stockage d’objets BLOB Azure.</span><span class="sxs-lookup"><span data-stu-id="a1218-397">The following example backs up the AdventureWorks2012 database to the Azure Blob storage service.</span></span>
  
   ```sql
   BACKUP DATABASE AdventureWorks2012   
   TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.bak'   
         WITH CREDENTIAL = 'mycredential'   
         ,COMPRESSION  
         ,STATS = 5;  
   GO
   ```  
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string url = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backup.Devices.AddDevice(url, DeviceType.Url);  
   backup.SqlBackup(server);  
   ```
  
   ```powershell
   # create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"   
   # for default instance, the $srvpath varilable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to SQL Server Instance  
   CD $srvPath   
   $backupFile = $backupUrlContainer + "AdventureWorks2012" +  ".bak"  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On
   ```  
  
###  <a name="backing-up-the-database-and-log"></a><a name="databaselog"></a><span data-ttu-id="a1218-398">Sauvegarde de la base de données et du journal</span><span class="sxs-lookup"><span data-stu-id="a1218-398">Backing up the database and log</span></span>  
 <span data-ttu-id="a1218-399">L'exemple suivant sauvegarde l'exemple de base de données AdventureWorks2012 qui utilise par défaut le mode de récupération simple.</span><span class="sxs-lookup"><span data-stu-id="a1218-399">The following example backups up the AdventureWorks2012 sample database, which uses the simple recovery model by default.</span></span> <span data-ttu-id="a1218-400">Pour prendre en charge les sauvegardes de fichier journal, la base de données AdventureWorks2012 est modifiée pour utiliser le mode de récupération complète.</span><span class="sxs-lookup"><span data-stu-id="a1218-400">To support log backups, the AdventureWorks2012 database is modified to use the full recovery model.</span></span> <span data-ttu-id="a1218-401">L’exemple crée ensuite une sauvegarde complète de base de données dans l’objet BLOB Azure et, après une période d’activité de mise à jour, sauvegarde le journal.</span><span class="sxs-lookup"><span data-stu-id="a1218-401">The example then creates a full database backup to Azure Blob, and after a period of update activity, backs up the log.</span></span> <span data-ttu-id="a1218-402">Cet exemple crée un nom de fichier de sauvegarde avec un tampon d'horodateur.</span><span class="sxs-lookup"><span data-stu-id="a1218-402">This example creates a backup file name with a datetime stamp.</span></span>  
  
   ```sql
   -- To permit log backups, before the full database backup, modify the database   
   -- to use the full recovery model.  
   USE master;  
   GO  
   ALTER DATABASE AdventureWorks2012  
      SET RECOVERY FULL;  
   GO  
  
   -- Back up the full AdventureWorks2012 database.  
          -- First create a file name for the backup file with DateTime stamp  
  
   DECLARE @Full_Filename AS VARCHAR (300);  
   SET @Full_Filename = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_Full_'+   
   REPLACE (REPLACE (REPLACE (CONVERT (VARCHAR (40), GETDATE (), 120), '-','_'),':', '_'),' ', '_') + '.bak';   
   --Back up Adventureworks2012 database  
  
   BACKUP DATABASE AdventureWorks2012  
   TO URL =  @Full_Filename  
   WITH CREDENTIAL = 'mycredential';  
   ,COMPRESSION  
   GO  
   -- Back up the AdventureWorks2012 log.  
   DECLARE @Log_Filename AS VARCHAR (300);  
   SET @Log_Filename = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_Log_'+   
   REPLACE (REPLACE (REPLACE (CONVERT (VARCHAR (40), GETDATE (), 120), '-','_'),':', '_'),' ', '_') + '.trn';  
   BACKUP LOG AdventureWorks2012  
    TO URL = @Log_Filename  
    WITH CREDENTIAL = 'mycredential'  
    ,COMPRESSION;  
   GO  
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url for data backup  
   string urlDataBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}_Data-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Database to Url  
   Backup backupData = new Backup();  
   backupData.CredentialName = credentialName;  
   backupData.Database = dbName;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backupData.Devices.AddDevice(urlDataBackup, DeviceType.Url);  
   backupData.SqlBackup(server);  
  
   // Generate Unique Url for data backup  
   string urlLogBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}_Log-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Database Log to Url  
   Backup backupLog = new Backup();  
   backupLog.CredentialName = credentialName;  
   backupLog.Database = dbName;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backupLog.Devices.AddDevice(urlLogBackup, DeviceType.Url);  
   backupLog.Action = BackupActionType.Log;  
   backupLog.SqlBackup(server);  
   ```  

   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to theSQL Server Instance
   CD $srvPath   
   #Create a unique file name for the full database backup  
   $backupFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   #Backup Database to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Database    
  
   #Create a unique file name for log backup  
  
   $backupFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".trn"  
  
   #Backup Log to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Log
   ```  
  
###  <a name="creating-a-full-file-backup-of-the-primary-filegroup"></a><a name="filebackup"></a><span data-ttu-id="a1218-403">Création d’une sauvegarde complète du groupe de fichiers primaire</span><span class="sxs-lookup"><span data-stu-id="a1218-403">Creating a full file backup of the primary filegroup</span></span>  
 <span data-ttu-id="a1218-404">L'exemple suivant crée une sauvegarde complète du groupe de fichiers principal.</span><span class="sxs-lookup"><span data-stu-id="a1218-404">The following example creates a full file backup of the primary filegroup.</span></span>
  
   ```sql
   --Back up the files in Primary:  
   BACKUP DATABASE AdventureWorks2012  
       FILEGROUP = 'Primary'  
       TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012files.bck'  
       WITH CREDENTIAL = 'mycredential'  
       ,COMPRESSION;  
   GO  
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string url = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-{3}.bck",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Action = BackupActionType.Files;  
   backup.DatabaseFileGroups.Add("PRIMARY");  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backup.Devices.AddDevice(url, DeviceType.Url);  
   backup.SqlBackup(server);
   ```
  
   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to the SQL Server Instance  
  
   CD $srvPath   
   #Create a unique file name for the file backup  
   $backupFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bck"  
  
   #Backup Primary File Group to URL  
  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Files -DatabaseFileGroup Primary
   ```  
  
###  <a name="creating-a-differential-file-backup-of-the-primary-filegroup"></a><a name="differential"></a><span data-ttu-id="a1218-405">Création d’une sauvegarde différentielle du groupe de fichiers primaire</span><span class="sxs-lookup"><span data-stu-id="a1218-405">Creating a differential file backup of the primary filegroup</span></span>  
 <span data-ttu-id="a1218-406">L'exemple suivant crée une sauvegarde différentielle du groupe de fichiers principal.</span><span class="sxs-lookup"><span data-stu-id="a1218-406">The following example creates a differential file backup of the primary filegroup.</span></span>  
  
   ```sql
   --Back up the files in Primary:  
   BACKUP DATABASE AdventureWorks2012  
       FILEGROUP = 'Primary'  
       TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012filesdiff.bck'  
       WITH   
          CREDENTIAL = 'mycredential'  
          ,COMPRESSION  
      ,DIFFERENTIAL;  
   GO
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string url = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Action = BackupActionType.Files;  
   backup.DatabaseFileGroups.Add("PRIMARY");  
   backup.Incremental = true;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backup.Devices.AddDevice(url, DeviceType.Url);  
   backup.SqlBackup(server); 
   ```

   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to SQL Server Instance
   CD $srvPath   
  
   #create a unique file name for the full backup  
   $backupdbFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   #Create a differential backup of the primary filegroup
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Files -DatabaseFileGroup Primary -Incremental
   ```  
  
###  <a name="restore-a-database-and-move-files"></a><a name="restoredbwithmove"></a><span data-ttu-id="a1218-407">Restaurer une base de données et déplacer des fichiers</span><span class="sxs-lookup"><span data-stu-id="a1218-407">Restore a database and move files</span></span>  
 <span data-ttu-id="a1218-408">L'exemple suivant restaure une sauvegarde complète de la base de données et déplace la base de données restaurée vers le répertoire C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Data.</span><span class="sxs-lookup"><span data-stu-id="a1218-408">To restore a full database backup and move the restored database to C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Data directory, use the following steps.</span></span>
  
   ```sql
   -- Backup the tail of the log first
   DECLARE @Log_Filename AS VARCHAR (300);  
   SET @Log_Filename = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_Log_'+   
   REPLACE (REPLACE (REPLACE (CONVERT (VARCHAR (40), GETDATE (), 120), '-','_'),':', '_'),' ', '_') + '.trn';  
   BACKUP LOG AdventureWorks2012  
    TO URL = @Log_Filename  
    WITH CREDENTIAL = 'mycredential'  
    ,NORECOVERY;  
   GO  
  
   RESTORE DATABASE AdventureWorks2012 FROM URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.bak'  
   WITH CREDENTIAL = 'mycredential'  
    ,MOVE 'AdventureWorks2012_data' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf'  
    ,MOVE 'AdventureWorks2012_log' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf'  
    ,STATS = 5
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string urlBackupData = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-Data{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   backup.SqlBackup(server);  
  
   // Generate Unique Url for tail log backup  
   string urlTailLogBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-TailLog{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Tail Log to Url  
   Backup backupTailLog = new Backup();  
   backupTailLog.CredentialName = credentialName;  
   backupTailLog.Database = dbName;  
   backupTailLog.Action = BackupActionType.Log;  
   backupTailLog.NoRecovery = true;  
   backupTailLog.Devices.AddDevice(urlTailLogBackup, DeviceType.Url);  
   backupTailLog.SqlBackup(server);  
  
   // Restore a database and move files  
   string newDataFilePath = server.MasterDBLogPath  + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".mdf";  
   string newLogFilePath = server.MasterDBLogPath  + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".ldf";  
  
   Restore restore = new Restore();  
   restore.CredentialName = credentialName;  
   restore.Database = dbName;  
   restore.ReplaceDatabase = true;  
   restore.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   restore.RelocateFiles.Add(new RelocateFile(dbName, newDataFilePath));  
   restore.RelocateFiles.Add(new RelocateFile(dbName+ "_Log", newLogFilePath));  
   restore.SqlRestore(server);
   ```  

   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTNACENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to SQL Server Instance
   CD $srvPath   
  
   #create a unique file name for the full backup  
   $backupdbFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   # Full database backup to URL  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupdbFile  -SqlCredential $credentialName -CompressionOption On      
  
   #Create a unique file name for the tail log backup  
   $backuplogFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".trn"  
  
   #Backup tail log to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName  -BackupAction Log -NoRecovery    
  
   # Restore Database and move files
   $newDataFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile ("AdventureWorks_Data","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf")  
   $newLogFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile("AdventureWorks_Log","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf")  
  
   Restore-SqlDatabase -Database AdventureWorks2012 -SqlCredential $credentialName -BackupFile $backupdbFile -RelocateFile @($newDataFilePath,$newLogFilePath)
   ```  
  
###  <a name="restoring-to-a-point-in-time-using-stopat"></a><a name="PITR"></a> <span data-ttu-id="a1218-409">Restauration jusqu'à une date et heure en utilisant STOPAT</span><span class="sxs-lookup"><span data-stu-id="a1218-409">Restoring to a point-in-time using STOPAT</span></span>  
 <span data-ttu-id="a1218-410">L'exemple suivant restaure une base de données dans l'état où elle se trouvait à un moment donné et montre une opération de restauration.</span><span class="sxs-lookup"><span data-stu-id="a1218-410">The following example restores a database to its state to a point in time, and shows a restore operation.</span></span>  
  
   ```sql
   RESTORE DATABASE AdventureWorks FROM URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.bak'   
   WITH   
     CREDENTIAL = 'mycredential'  
    ,MOVE 'AdventureWorks2012_data' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf'  
    ,Move 'AdventureWorks2012_log' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf'  
    ,NORECOVERY  
    --,REPLACE  
    ,STATS = 5;  
   GO   
  
   RESTORE LOG AdventureWorks FROM URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.trn'   
   WITH CREDENTIAL = 'mycredential'  
    ,RECOVERY   
    ,STOPAT = 'Oct 23, 2012 5:00 PM'   
   GO  
   ```  
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string urlBackupData = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-Data{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   backup.SqlBackup(server);  
  
   // Generate Unique Url for Tail Log backup  
   string urlTailLogBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-TailLog{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Tail Log to Url  
   Backup backupTailLog = new Backup();  
   backupTailLog.CredentialName = credentialName;  
   backupTailLog.Database = dbName;  
   backupTailLog.Action = BackupActionType.Log;  
   backupTailLog.NoRecovery = true;  
   backupTailLog.Devices.AddDevice(urlTailLogBackup, DeviceType.Url);  
   backupTailLog.SqlBackup(server);  
  
   // Restore a database and move files  
   string newDataFilePath = server.MasterDBLogPath + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".mdf";  
   string newLogFilePath = server.MasterDBLogPath + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".ldf";  
  
   Restore restore = new Restore();  
   restore.CredentialName = credentialName;  
   restore.Database = dbName;  
   restore.ReplaceDatabase = true;  
   restore.NoRecovery = true;  
   restore.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   restore.RelocateFiles.Add(new RelocateFile(dbName, newDataFilePath));  
   restore.RelocateFiles.Add(new RelocateFile(dbName + "_Log", newLogFilePath));  
   restore.SqlRestore(server);  
      
   // Restore transaction Log with stop at   
   Restore restoreLog = new Restore();  
   restoreLog.CredentialName = credentialName;  
   restoreLog.Database = dbName;  
   restoreLog.Action = RestoreActionType.Log;  
   restoreLog.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   restoreLog.ToPointInTime = DateTime.Now.ToString();   
   restoreLog.SqlRestore(server);
   ```
  
   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # Navigate to SQL Server Instance Directory
   CD $srvPath   
  
   #create a unique file name for the full backup  
   $backupdbFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   # Full database backup to URL  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupdbFile  -SqlCredential $credentialName -CompressionOption On     
  
   #Create a unique file name for the tail log backup  
   $backuplogFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".trn"  
  
   #Backup tail log to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName  -BackupAction Log -NoRecovery     
  
   # Restore Database and move files
   $newDataFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile ("AdventureWorks_Data","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf")  
   $newLogFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile("AdventureWorks_Log","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf")  
  
   Restore-SqlDatabase -Database AdventureWorks2012 -SqlCredential $credentialName -BackupFile $backupdbFile -RelocateFile @($newDataFilePath,$newLogFilePath) -NoRecovery    
  
   # Restore Transaction log with Stop At:  
   Restore-SqlDatabase -Database AdventureWorks2012 -SqlCredential $credentialName -BackupFile $backuplogFile  -ToPointInTime (Get-Date).ToString()
   ```  
  
## <a name="see-also"></a><span data-ttu-id="a1218-411">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a1218-411">See Also</span></span>  
 <span data-ttu-id="a1218-412">[Meilleures pratiques et dépannage de sauvegarde SQL Server vers une URL](sql-server-backup-to-url-best-practices-and-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="a1218-412">[SQL Server Backup to URL Best Practices and Troubleshooting](sql-server-backup-to-url-best-practices-and-troubleshooting.md) </span></span>  
 [<span data-ttu-id="a1218-413">Sauvegarde et restauration des bases de données système &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a1218-413">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](back-up-and-restore-of-system-databases-sql-server.md)   
