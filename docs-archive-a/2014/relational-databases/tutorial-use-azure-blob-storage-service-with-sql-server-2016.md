---
title: 'Didacticiel : SQL Server de fichiers de données dans le service de stockage Azure | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: e69be67d-da1c-41ae-8c9a-6b12c8c2fb61
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 21a0fc11706a0c5ee35cf71e1af69f2927adc9db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614459"
---
# <a name="tutorial-sql-server-data-files-in-azure-storage-service"></a><span data-ttu-id="be1fd-102">Tutoriel : Fichiers de données SQL Server dans le service de Stockage Azure</span><span class="sxs-lookup"><span data-stu-id="be1fd-102">Tutorial: SQL Server Data Files in Azure Storage service</span></span>
  <span data-ttu-id="be1fd-103">Bienvenue dans le didacticiel SQL Server fichiers de données dans le service de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="be1fd-103">Welcome to the  SQL Server Data Files in Azure Storage Service tutorial.</span></span> <span data-ttu-id="be1fd-104">Ce tutoriel explique comment stocker directement des fichiers de données SQL Server dans le service de stockage d’objets blob Azure.</span><span class="sxs-lookup"><span data-stu-id="be1fd-104">This tutorial helps you understand how to store SQL Server data files in the Azure Blob storage service directly.</span></span>  
  
 <span data-ttu-id="be1fd-105">La prise en charge de l’intégration de SQL Server pour le service de stockage d’objets BLOB Azure est SQL Server une amélioration de 2014.</span><span class="sxs-lookup"><span data-stu-id="be1fd-105">SQL Server integration support for the Azure Blob storage service is a SQL Server 2014 enhancement.</span></span> <span data-ttu-id="be1fd-106">Pour obtenir une vue d’ensemble des fonctionnalités et des avantages de l’utilisation de cette fonctionnalité, consultez [SQL Server des fichiers de données dans Azure](databases/sql-server-data-files-in-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="be1fd-106">For an overview of the functionality and benefits of using this functionality, see [SQL Server Data Files in Azure](databases/sql-server-data-files-in-microsoft-azure.md).</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="be1fd-107">Contenu du didacticiel</span><span class="sxs-lookup"><span data-stu-id="be1fd-107">What you will learn</span></span>  
 <span data-ttu-id="be1fd-108">Ce didacticiel vous montre comment stocker des fichiers de données SQL Server dans le service de stockage Azure en plusieurs leçons.</span><span class="sxs-lookup"><span data-stu-id="be1fd-108">This tutorial shows you how to store SQL Server Data Files in Azure Storage service in multiple lessons.</span></span> <span data-ttu-id="be1fd-109">Chaque leçon traite d' une tâche spécifique.</span><span class="sxs-lookup"><span data-stu-id="be1fd-109">Each lesson is focused on a specific task.</span></span> <span data-ttu-id="be1fd-110">Tout d’abord, vous allez apprendre à créer un compte de stockage et un conteneur dans Azure.</span><span class="sxs-lookup"><span data-stu-id="be1fd-110">First, you will learn how to create a storage account and a container in Azure.</span></span> <span data-ttu-id="be1fd-111">Ensuite, vous allez apprendre à créer un SQL Server informations d’identification pour pouvoir intégrer SQL Server à Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="be1fd-111">Then, you will learn how to create a SQL Server credential to be able to integrate SQL Server with Azure Storage.</span></span> <span data-ttu-id="be1fd-112">Ensuite, vous allez créer une base de données directement dans le stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="be1fd-112">Then, you will create a database in Azure Storage directly.</span></span> <span data-ttu-id="be1fd-113">Par ailleurs, le didacticiel décrit le chiffrement, la migration et les scénarios de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="be1fd-113">In addition, the tutorial will demonstrate encryption, migration, and backup and restore scenarios.</span></span>  
  
 <span data-ttu-id="be1fd-114">Ce didacticiel est divisé en neuf leçons :</span><span class="sxs-lookup"><span data-stu-id="be1fd-114">This tutorial is divided into nine lessons:</span></span>  
  
 <span data-ttu-id="be1fd-115">**[Leçon 1 : Créer un compte et un conteneur Stockage Azure](../tutorials/lesson-1-create-windows-azure-storage-account-and-container.md)**</span><span class="sxs-lookup"><span data-stu-id="be1fd-115">**[Lesson 1: Create Azure Storage Account and Container](../tutorials/lesson-1-create-windows-azure-storage-account-and-container.md)**</span></span>  
 <span data-ttu-id="be1fd-116">Dans cette leçon, vous allez créer un compte de stockage Azure et un conteneur.</span><span class="sxs-lookup"><span data-stu-id="be1fd-116">In this lesson, you create an Azure Storage account and a container.</span></span>  
  
 <span data-ttu-id="be1fd-117">**[Leçon 2. Créer une stratégie sur un conteneur et générer une signature d’accès partagé &#40;clé de&#41; SAS](lesson-1-create-stored-access-policy-and-shared-access-signature.md)**</span><span class="sxs-lookup"><span data-stu-id="be1fd-117">**[Lesson 2. Create a policy on container and generate a Shared Access Signature &#40;SAS&#41; key](lesson-1-create-stored-access-policy-and-shared-access-signature.md)**</span></span>  
 <span data-ttu-id="be1fd-118">Dans cette leçon, vous allez créer une stratégie sur le conteneur d'objets blob et générer une signature d'accès partagé.</span><span class="sxs-lookup"><span data-stu-id="be1fd-118">In this lesson, you create a policy on the Blob container and also generate a shared access signature.</span></span>  
  
 <span data-ttu-id="be1fd-119">**[Leçon 3 : Créer des informations d'identification SQL Server](lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)**</span><span class="sxs-lookup"><span data-stu-id="be1fd-119">**[Lesson 3: Create a SQL Server Credential](lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)**</span></span>  
 <span data-ttu-id="be1fd-120">Dans cette leçon, vous allez créer des informations d’identification afin de stocker les informations de sécurité utilisées pour accéder au compte de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="be1fd-120">In this lesson, you create a Credential to store security information used to access the Azure storage account.</span></span>  
  
 <span data-ttu-id="be1fd-121">**[Leçon 4 : Créer une base de données dans Stockage Azure](../relational-databases/lesson-3-database-backup-to-url.md)**</span><span class="sxs-lookup"><span data-stu-id="be1fd-121">**[Lesson 4: Create a database in Azure Storage](../relational-databases/lesson-3-database-backup-to-url.md)**</span></span>  
 <span data-ttu-id="be1fd-122">Dans cette leçon, vous allez créer une base de données dans stockage Azure à l’aide de l’option créer un nom de fichier de base de données.</span><span class="sxs-lookup"><span data-stu-id="be1fd-122">In this lesson, you create a database in Azure Storage using CREATE Database FILENAME option.</span></span>  
  
 <span data-ttu-id="be1fd-123">**[Leçon 5. &#40;facultatif&#41; chiffrer votre base de données à l’aide de TDE](../relational-databases/lesson-4-restore-database-to-virtual-machine-from-url.md)**</span><span class="sxs-lookup"><span data-stu-id="be1fd-123">**[Lesson 5. &#40;Optional&#41; Encrypt your database using TDE](../relational-databases/lesson-4-restore-database-to-virtual-machine-from-url.md)**</span></span>  
 <span data-ttu-id="be1fd-124">Dans cette leçon, vous allez chiffrer votre base de données à l'aide d'un chiffrement transparent des données (TDE) et d'un certificat de serveur.</span><span class="sxs-lookup"><span data-stu-id="be1fd-124">In this lesson, you encrypt your database by using a transparent data encryption (TDE) and a server certificate.</span></span>  
  
 <span data-ttu-id="be1fd-125">**[Leçon 6 : Migrer une base de données d’une machine source locale vers une machine de destination dans Azure](lesson-5-backup-database-using-file-snapshot-backup.md)**</span><span class="sxs-lookup"><span data-stu-id="be1fd-125">**[Lesson 6: Migrate a database from a source machine on-premises to a destination machine in Azure](lesson-5-backup-database-using-file-snapshot-backup.md)**</span></span>  
 <span data-ttu-id="be1fd-126">Dans cette leçon, vous migrez une base de données locale vers une machine virtuelle dans Azure à l’aide de l’option CREATe DATABASE FOR ATTACH.</span><span class="sxs-lookup"><span data-stu-id="be1fd-126">In this lesson, you migrate a database from on-premises to a virtual machine in Azure using CREATE DATABASE FOR ATTACH option.</span></span>  
  
 <span data-ttu-id="be1fd-127">**[Leçon 7 : Déplacer vos fichiers de données dans le Stockage Azure](../relational-databases/lesson-6-generate-activity-and-backup-log-using-file-snapshot-backup.md)**</span><span class="sxs-lookup"><span data-stu-id="be1fd-127">**[Lesson 7: Move your data files to Azure Storage](../relational-databases/lesson-6-generate-activity-and-backup-log-using-file-snapshot-backup.md)**</span></span>  
 <span data-ttu-id="be1fd-128">Dans cette leçon, vous allez déplacer vos fichiers de données vers le stockage Azure à l’aide de l’instruction ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="be1fd-128">In this lesson, you move your data files to Azure Storage using ALTER DATABASE statement.</span></span>  
  
 <span data-ttu-id="be1fd-129">**[Leçon 8. Restaurer une base de données dans Azure Storage](../relational-databases/lesson-7-restore-a-database-to-a-point-in-time.md)**</span><span class="sxs-lookup"><span data-stu-id="be1fd-129">**[Lesson 8. Restore a database to Azure Storage](../relational-databases/lesson-7-restore-a-database-to-a-point-in-time.md)**</span></span>  
 <span data-ttu-id="be1fd-130">Dans cette leçon, vous allez restaurer une base de données dans Azure Storage à l’aide de l’option RESTORE DATABASE MOVE.</span><span class="sxs-lookup"><span data-stu-id="be1fd-130">In this lesson, you restore a database to Azure Storage using RESTORE Database MOVE option.</span></span>  
  
 <span data-ttu-id="be1fd-131">**[Leçon 9. Restaurer une base de données à partir du stockage Azure](lesson-8-restore-as-new-database-from-log-backup.md)**</span><span class="sxs-lookup"><span data-stu-id="be1fd-131">**[Lesson 9. Restore a database from Azure Storage](lesson-8-restore-as-new-database-from-log-backup.md)**</span></span>  
 <span data-ttu-id="be1fd-132">Dans cette leçon, vous allez restaurer une base de données à partir du stockage Azure à l’aide de l’option RESTORE DATABASE MOVE.</span><span class="sxs-lookup"><span data-stu-id="be1fd-132">In this lesson, you restore a database from Azure Storage using RESTORE Database MOVE option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be1fd-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="be1fd-133">See Also</span></span>  
 [<span data-ttu-id="be1fd-134">Fichiers de données SQL Server dans Azure</span><span class="sxs-lookup"><span data-stu-id="be1fd-134">SQL Server Data Files in Azure</span></span>](databases/sql-server-data-files-in-microsoft-azure.md)  
  
  
