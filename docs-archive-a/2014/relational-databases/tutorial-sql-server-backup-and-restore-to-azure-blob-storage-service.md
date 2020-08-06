---
title: 'Didacticiel : Sauvegarde et restauration SQL Server dans le service Stockage Blob Azure | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 9e1d94ce-2c93-45d1-ae2a-2a7d1fa094c4
author: rothja
ms.author: jroth
ms.openlocfilehash: d15200968011cdb314829736512f39730782dc0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696700"
---
# <a name="tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service"></a><span data-ttu-id="85a40-102">Tutoriel : Sauvegarde et restauration SQL Server avec le service Stockage Blob Azure</span><span class="sxs-lookup"><span data-stu-id="85a40-102">Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service</span></span>
  <span data-ttu-id="85a40-103">Bienvenue dans le Prise en main avec SQL Server didacticiel sauvegarde et restauration avec le service de stockage d’objets BLOB Azure.</span><span class="sxs-lookup"><span data-stu-id="85a40-103">Welcome to the Getting Started with SQL Server Backup and Restore with Azure Blob Storage Service tutorial.</span></span> <span data-ttu-id="85a40-104">Ce didacticiel vous aide à comprendre comment écrire des sauvegardes et les restaurer à partir du service Stockage Blob Azure.</span><span class="sxs-lookup"><span data-stu-id="85a40-104">This tutorial helps you understand how to write backups to and restore from the Azure Blob storage service.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="85a40-105">Contenu du didacticiel</span><span class="sxs-lookup"><span data-stu-id="85a40-105">What You Will Learn</span></span>  
 <span data-ttu-id="85a40-106">Ce didacticiel montre comment créer un compte de stockage Windows et un conteneur d'objets blob, créer des informations d'identification pour accéder au compte de stockage, écrire une sauvegarde dans le service d'objet blob et effectuer une restauration simple.</span><span class="sxs-lookup"><span data-stu-id="85a40-106">This tutorial shows you how to create a Windows Storage account, a blob container, creating credentials to access the storage account, writing a backup to the blob service, and performing a simple restore.</span></span> <span data-ttu-id="85a40-107">Ce didacticiel est divisé en quatre leçons :</span><span class="sxs-lookup"><span data-stu-id="85a40-107">This tutorial is divided into four lessons:</span></span>  
  
 [<span data-ttu-id="85a40-108">Leçon 1 : créer des objets de stockage Azure</span><span class="sxs-lookup"><span data-stu-id="85a40-108">Lesson 1: Create Azure Storage Objects</span></span>](../tutorials/lesson-1-create-windows-azure-storage-objects.md)  
 <span data-ttu-id="85a40-109">Dans cette leçon, vous allez créer un compte de stockage Azure et un conteneur d’objets blob.</span><span class="sxs-lookup"><span data-stu-id="85a40-109">In this lesson, you create an Azure storage account and a blob container.</span></span>  
  
 [<span data-ttu-id="85a40-110">Leçon 2 : Créer des informations d'identification SQL Server</span><span class="sxs-lookup"><span data-stu-id="85a40-110">Lesson 2: Create a SQL Server Credential</span></span>](../tutorials/lesson-2-create-a-sql-server-credential.md)  
 <span data-ttu-id="85a40-111">Dans cette leçon, vous allez créer des informations d’identification afin de stocker les informations de sécurité utilisées pour accéder au compte de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="85a40-111">In this lesson, you create a Credential to store security information used to access the Azure storage account.</span></span>  
  
 [<span data-ttu-id="85a40-112">Leçon 3 : Écrire une sauvegarde de base de données complète dans le service Stockage Blob Azure</span><span class="sxs-lookup"><span data-stu-id="85a40-112">Lesson 3: Write a Full Database Backup to the Azure Blob Storage Service</span></span>](../tutorials/lesson-3-write-a-full-database-backup-to-the-windows-azure-blob-storage-service.md)  
 <span data-ttu-id="85a40-113">Dans cette leçon, vous allez publier une instruction T-SQL pour écrire une sauvegarde de la base de données AdventureWorks2012 dans le service Stockage Blob Azure.</span><span class="sxs-lookup"><span data-stu-id="85a40-113">In this lesson, you issue a T-SQL statement to write a backup of the AdventureWorks2012 database to the Azure Blob storage service.</span></span>  
  
 [<span data-ttu-id="85a40-114">Leçon 4 : Effectuer une restauration d’une sauvegarde de base de données complète</span><span class="sxs-lookup"><span data-stu-id="85a40-114">Lesson 4: Perform a Restore From a Full Database Backup</span></span>](../tutorials/lesson-4-perform-a-restore-from-a-full-database-backup.md)  
 <span data-ttu-id="85a40-115">Dans cette leçon, vous allez publier une instruction T-SQL pour effectuer une restauration d'une sauvegarde de la base de données que vous avez créée au cours de la leçon précédente.</span><span class="sxs-lookup"><span data-stu-id="85a40-115">In this lesson, you issue a T-SQL statement to restore from the database backup you created in the previous lesson.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="85a40-116">Spécifications</span><span class="sxs-lookup"><span data-stu-id="85a40-116">Requirements</span></span>  
 <span data-ttu-id="85a40-117">Pour suivre ce didacticiel, vous devez connaître les concepts de sauvegarde et de restauration [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] et la syntaxe T-SQL.</span><span class="sxs-lookup"><span data-stu-id="85a40-117">To complete this tutorial, you must be familiar with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backup and restore concepts and T-SQL syntax.</span></span> <span data-ttu-id="85a40-118">Pour utiliser ce didacticiel, votre système doit répondre aux spécifications suivantes :</span><span class="sxs-lookup"><span data-stu-id="85a40-118">To use this tutorial, your system must meet the following requirements:</span></span>  
  
-   <span data-ttu-id="85a40-119">Une instance de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] et la base de données AdventureWorks2012 doivent être installées.</span><span class="sxs-lookup"><span data-stu-id="85a40-119">An instance of [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)], and AdventureWorks2012 database installed.</span></span>  
  
     <span data-ttu-id="85a40-120">L’instance SQL Server peut être installée sur site ou sur une machine virtuelle Azure.</span><span class="sxs-lookup"><span data-stu-id="85a40-120">The SQL Server instance can be on-premises or in an Azure Virtual Machine.</span></span>  
  
     <span data-ttu-id="85a40-121">Vous pouvez utiliser une base de données utilisateur en remplacement d'AdventureWorks2012, puis modifier la syntaxe TSQL en conséquence.</span><span class="sxs-lookup"><span data-stu-id="85a40-121">You can use a user database in place of AdventureWorks2012, and modify the tsql syntax accordingly.</span></span>  
  
-   <span data-ttu-id="85a40-122">Le compte d’utilisateur utilisé pour émettre les commandes BACKUP (sauvegarder) ou RESTORE (restaurer) doit figurer dans le rôle de base de données **db_backup operator** avec les autorisations **Modifier des informations d’identification** .</span><span class="sxs-lookup"><span data-stu-id="85a40-122">The user account that is used to issue BACKUP or RESTORE commands should be in the **db_backup operator** database role with **Alter any credential** permissions.</span></span>  
  
### <a name="additional-reading"></a><span data-ttu-id="85a40-123">Lectures supplémentaires</span><span class="sxs-lookup"><span data-stu-id="85a40-123">Additional Reading</span></span>  
 <span data-ttu-id="85a40-124">Les ressources suivantes sont des lectures recommandées afin de comprendre les concepts et les bonnes pratiques pour l’utilisation du service Stockage Blob Azure pour les sauvegardes [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85a40-124">Following are some recommended reading to understand the concepts, best practices when using Azure Blob storage service for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backups.</span></span>  
  
1.  [<span data-ttu-id="85a40-125">Sauvegarde et restauration SQL Server avec le service Stockage Blob Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="85a40-125">SQL Server Backup and Restore with Azure Blob Storage Service</span></span>](backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md)  
  
2.  [<span data-ttu-id="85a40-126">Bonnes pratiques et résolution des problèmes liés à la sauvegarde SQL Server vers une URL</span><span class="sxs-lookup"><span data-stu-id="85a40-126">SQL Server Backup to URL Best Practices and Troubleshooting</span></span>](backup-restore/sql-server-backup-to-url-best-practices-and-troubleshooting.md)  
  
  
