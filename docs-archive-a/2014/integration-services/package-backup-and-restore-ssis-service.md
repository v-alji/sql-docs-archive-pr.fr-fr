---
title: Sauvegarde et restauration de packages (service SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SSIS packages, backup and restore
- backing up packages [Integration Services]
- packages [Integration Services], backup and restore
- SQL Server Integration Services packages, backup and restore
- restoring packages [Integration Services]
- Integration Services packages, backup and restore
ms.assetid: c67d3b83-a6c8-40de-920f-9236de4ac87f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c4cd6f3856b69485c01e4b38d89e2f7e2ec56f74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613540"
---
# <a name="package-backup-and-restore-ssis-service"></a><span data-ttu-id="128bb-102">Sauvegarde et restauration de packages (Service SSIS)</span><span class="sxs-lookup"><span data-stu-id="128bb-102">Package Backup and Restore (SSIS Service)</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="128bb-103">Cette rubrique présente le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , un service Windows qui permet de gérer les packages [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="128bb-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="128bb-104">prend en charge le service pour la compatibilité avec les versions antérieures de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="128bb-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="128bb-105">À compter de [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], vous pouvez gérer des objets tels que des packages sur le serveur Integration Services.</span><span class="sxs-lookup"><span data-stu-id="128bb-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="128bb-106">Les packages [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] peuvent être enregistrés dans le système de fichiers ou dans msdb, base de données système [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="128bb-106">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages can be saved to the file system or msdb, a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] system database.</span></span> <span data-ttu-id="128bb-107">Les packages enregistrés dans msdb peuvent être sauvegardés et restaurés à l’aide des fonctionnalités de sauvegarde et de restauration de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="128bb-107">Packages saved to msdb can be backed up and restored using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backup and restore features.</span></span>  
  
 <span data-ttu-id="128bb-108">Pour plus d’informations sur la sauvegarde et la restauration de la base de données msdb, cliquez sur l’une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="128bb-108">For more information about backing up and restoring the msdb database, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="128bb-109">Sauvegarder et restaurer des bases de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="128bb-109">Back Up and Restore of SQL Server Databases</span></span>](../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md)  
  
-   [<span data-ttu-id="128bb-110">Sauvegarde et restauration des bases de données système &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="128bb-110">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](../relational-databases/backup-restore/back-up-and-restore-of-system-databases-sql-server.md)  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="128bb-111">comprend l’utilitaire d’invite de commandes **dtutil** (dtutil.exec) qui permet de gérer les packages.</span><span class="sxs-lookup"><span data-stu-id="128bb-111">includes the **dtutil** command-prompt utility (dtutil.exec), which you can use to manage packages.</span></span> <span data-ttu-id="128bb-112">Pour plus d’informations, consultez [dtutil Utility](dtutil-utility.md).</span><span class="sxs-lookup"><span data-stu-id="128bb-112">For more information, see [dtutil Utility](dtutil-utility.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="128bb-113">Fichiers de configuration</span><span class="sxs-lookup"><span data-stu-id="128bb-113">Configuration Files</span></span>  
 <span data-ttu-id="128bb-114">Tous les fichiers de configuration inclus dans les packages sont stockés dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="128bb-114">Any configuration files that the packages include are stored in the file system.</span></span> <span data-ttu-id="128bb-115">Ces fichiers ne sont pas sauvegardés en même temps que la base de données msdb. Vous devez donc vérifier que les fichiers de configuration sont sauvegardés régulièrement dans le cadre de votre plan de sécurisation des packages enregistrés dans msdb.</span><span class="sxs-lookup"><span data-stu-id="128bb-115">These files are not backed up when you back up the msdb database; therefore, you should make sure that the configuration files are backed up regularly as part of your plan for securing packages saved to msdb.</span></span> <span data-ttu-id="128bb-116">Pour inclure les configurations dans la sauvegarde de la base de données msdb, vous devez envisager d’utiliser le type de configuration [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] à la place des configurations basées sur les fichiers.</span><span class="sxs-lookup"><span data-stu-id="128bb-116">To include configurations in the backup of the msdb database, you should consider using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration type instead of file-based configurations.</span></span>  
  
## <a name="packages-stored-in-the-file-system"></a><span data-ttu-id="128bb-117">Packages stockés dans le système de fichiers</span><span class="sxs-lookup"><span data-stu-id="128bb-117">Packages Stored in the File System</span></span>  
 <span data-ttu-id="128bb-118">La sauvegarde des packages enregistrés dans le système de fichiers doit être incluse dans le plan de sauvegarde du système de fichiers du serveur.</span><span class="sxs-lookup"><span data-stu-id="128bb-118">The backup of packages that are saved to the file system should be included in the plan for backing up the file system of the server.</span></span> <span data-ttu-id="128bb-119">Le ficher de configuration du service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , dont le nom par défaut est MsDtsSrvr.ini.xml, donne la liste des dossiers sur le serveur contrôlé par le service.</span><span class="sxs-lookup"><span data-stu-id="128bb-119">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service configuration file, which has the default name MsDtsSrvr.ini.xml, lists the folders on the server that the service monitors.</span></span> <span data-ttu-id="128bb-120">Vous devez vous assurer que ces dossiers sont sauvegardés.</span><span class="sxs-lookup"><span data-stu-id="128bb-120">You should make sure these folders are backed up.</span></span> <span data-ttu-id="128bb-121">En outre, les packages peuvent être stockés dans d'autres dossiers sur le serveur et vous devez vous assurer que ces dossiers sont inclus dans la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="128bb-121">Additionally, packages may be stored in other folders on the server and you should make sure to include these folders in the backup.</span></span>  
  
  
