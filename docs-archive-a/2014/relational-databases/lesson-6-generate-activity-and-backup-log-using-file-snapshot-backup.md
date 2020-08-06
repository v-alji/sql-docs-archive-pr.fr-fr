---
title: 'Leçon 7 : déplacer vos fichiers de données vers le stockage Azure | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 26aa534a-afe7-4a14-b99f-a9184fc699bd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 753863d7b8b8d8fa554f1579bee6837c525efd9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612323"
---
# <a name="lesson-7-move-your-data-files-to-azure-storage"></a><span data-ttu-id="fea12-102">Leçon 7 : Déplacer vos fichiers de données dans le Stockage Azure</span><span class="sxs-lookup"><span data-stu-id="fea12-102">Lesson 7: Move your data files to Azure Storage</span></span>
  <span data-ttu-id="fea12-103">Dans cette leçon, vous allez apprendre à déplacer vos fichiers de données vers le stockage Azure (mais pas votre instance SQL Server).</span><span class="sxs-lookup"><span data-stu-id="fea12-103">In this lesson, you will learn how to move your data files to Azure Storage (but not your SQL Server instance).</span></span> <span data-ttu-id="fea12-104">Pour suivre cette leçon, vous n'avez pas besoin de terminer les leçons 4, 5 et 6.</span><span class="sxs-lookup"><span data-stu-id="fea12-104">To follow this lesson, you do not need to complete Lesson 4, 5, and 6.</span></span>  
  
 <span data-ttu-id="fea12-105">Pour déplacer vos fichiers de données vers le stockage Azure, vous pouvez utiliser l' `ALTER DATABASE` instruction, car elle permet de modifier l’emplacement des fichiers de données.</span><span class="sxs-lookup"><span data-stu-id="fea12-105">To move your data files to Azure Storage, you can use the `ALTER DATABASE` statement as it helps to change the location of the data files.</span></span>  
  
 <span data-ttu-id="fea12-106">Cette leçon suppose que vous avez déjà effectué les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="fea12-106">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="fea12-107">Vous avez un compte de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="fea12-107">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="fea12-108">Vous avez créé un conteneur sous votre compte de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="fea12-108">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="fea12-109">Vous avez créé une stratégie sur un conteneur avec des droits en lecture, écriture et création de liste.</span><span class="sxs-lookup"><span data-stu-id="fea12-109">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="fea12-110">Vous avez également généré une clé SAS.</span><span class="sxs-lookup"><span data-stu-id="fea12-110">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="fea12-111">Vous avez créé des informations d'identification SQL Server sur l'ordinateur source.</span><span class="sxs-lookup"><span data-stu-id="fea12-111">You have created a SQL Server credential on the source machine.</span></span>  
  
 <span data-ttu-id="fea12-112">Ensuite, procédez comme suit pour déplacer vos fichiers de données vers le stockage Azure :</span><span class="sxs-lookup"><span data-stu-id="fea12-112">Next, use the following steps to move your data files to Azure Storage:</span></span>  
  
1.  <span data-ttu-id="fea12-113">Tout d'abord, créez une base de données de test dans la machine source et ajoutez-lui des données.</span><span class="sxs-lookup"><span data-stu-id="fea12-113">First, create a test database in the source machine and add some data to it.</span></span>  
  
    ```sql  
  
    USE master;   
    CREATE DATABASE TestDB1Alter;   
    GO   
    USE TestDB1Alter;   
    GO   
    CREATE TABLE Table1 (Col1 int primary key, Col2 varchar(20));   
    GO   
    INSERT INTO Table1 (Col1, Col2) VALUES (1, 'string1'), (2, 'string2');   
    GO  
  
    ```  
  
2.  <span data-ttu-id="fea12-114">Exécutez le code ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="fea12-114">Run the following code:</span></span>  
  
    ```sql  
  
    -- In the following statement, modify the path specified in FILENAME to   
    -- the new location of the file in Azure Storage container.   
    ALTER DATABASE TestDB1Alter    
        MODIFY FILE ( NAME = TestDB1Alter,    
                    FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontaineralter/TestDB1AlterData.mdf');   
    GO  
  
    ```  
  
3.  <span data-ttu-id="fea12-115">Lorsque vous exécutez cette opération, le message suivant s’affiche : « le fichier «TestDB1Alter » a été modifié dans le catalogue système.</span><span class="sxs-lookup"><span data-stu-id="fea12-115">When you run this, you will see this message: "The file "TestDB1Alter" has been modified in the system catalog.</span></span> <span data-ttu-id="fea12-116">Le nouveau chemin sera utilisé au prochain démarrage de la base de données.»</span><span class="sxs-lookup"><span data-stu-id="fea12-116">The new path will be used the next time the database is started."</span></span>  
  
4.  <span data-ttu-id="fea12-117">Ensuite, mettez la base de données hors connexion.</span><span class="sxs-lookup"><span data-stu-id="fea12-117">Then, set the database offline.</span></span>  
  
    ```sql  
  
    ALTER DATABASE TestDB1Alter SET OFFLINE;   
    GO  
  
    ```  
  
5.  <span data-ttu-id="fea12-118">À présent, vous devez copier les fichiers de données vers le stockage Azure à l’aide de l’une des méthodes suivantes : [outil AzCopy](https://docs.microsoft.com/archive/blogs/windowsazurestorage/azcopy-uploadingdownloading-files-for-windows-azure-blobs), [page put](https://msdn.microsoft.com/library/azure/ee691975.aspx), référence de la [bibliothèque cliente de stockage](https://msdn.microsoft.com/library/azure/dn261237.aspx)ou outil d’exploration de stockage tiers.</span><span class="sxs-lookup"><span data-stu-id="fea12-118">Now, you need to copy the data files to Azure Storage by using one of the following methods: [AzCopy Tool](https://docs.microsoft.com/archive/blogs/windowsazurestorage/azcopy-uploadingdownloading-files-for-windows-azure-blobs), [Put Page](https://msdn.microsoft.com/library/azure/ee691975.aspx), [Storage Client Library Reference](https://msdn.microsoft.com/library/azure/dn261237.aspx), or a third-party storage explorer tool.</span></span>  
  
     <span data-ttu-id="fea12-119">**Important :** Lorsque vous utilisez cette nouvelle amélioration, veillez toujours à créer un objet blob de pages et non un objet blob de blocs.</span><span class="sxs-lookup"><span data-stu-id="fea12-119">**Important:** When using this new enhancement, always make sure that you create a page blob not a block blob.</span></span>  
  
6.  <span data-ttu-id="fea12-120">Ensuite, mettez la base de données en ligne.</span><span class="sxs-lookup"><span data-stu-id="fea12-120">Then, set the database online.</span></span>  
  
    ```sql  
  
    ALTER DATABASE TestDB1Alter SET ONLINE;   
    GO  
  
    ```  
  
 <span data-ttu-id="fea12-121">**Leçon suivante :**</span><span class="sxs-lookup"><span data-stu-id="fea12-121">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="fea12-122">Leçon 8. Restaurer une base de données dans Azure Storage</span><span class="sxs-lookup"><span data-stu-id="fea12-122">Lesson 8. Restore a database to Azure Storage</span></span>](lesson-7-restore-a-database-to-a-point-in-time.md)  
  
  
