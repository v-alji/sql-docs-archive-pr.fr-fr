---
title: Leçon 8. Restaurer une base de données dans Azure Storage | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: a9f99670-e1de-441e-972c-69faffcac17a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: adec725d1b519fb67560dc572823ba0a116aaa54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614036"
---
# <a name="lesson-8-restore-a-database-to-azure-storage"></a><span data-ttu-id="26d1f-103">Leçon 8.</span><span class="sxs-lookup"><span data-stu-id="26d1f-103">Lesson 8.</span></span> <span data-ttu-id="26d1f-104">Restaurer une base de données dans le Stockage Azure</span><span class="sxs-lookup"><span data-stu-id="26d1f-104">Restore a database to Azure Storage</span></span>
  <span data-ttu-id="26d1f-105">Dans cette leçon, vous allez apprendre à créer un fichier de sauvegarde localement, puis à le restaurer dans le stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="26d1f-105">In this lesson, you will learn how to create a backup file locally and then restore it to Azure Storage.</span></span> <span data-ttu-id="26d1f-106">Notez que vous pouvez faire en sorte que votre base de données soit locale ou dans une machine virtuelle dans Azure.</span><span class="sxs-lookup"><span data-stu-id="26d1f-106">Note that you can have your database either on either on-premises or in a virtual machine in Azure.</span></span> <span data-ttu-id="26d1f-107">Pour suivre cette leçon, vous n'avez pas besoin de terminer les leçons 4, 5, 6 et 7.</span><span class="sxs-lookup"><span data-stu-id="26d1f-107">To follow this lesson, you do not need to complete Lesson 4, 5, 6, and 7.</span></span>  
  
 <span data-ttu-id="26d1f-108">Cette leçon suppose que vous avez déjà effectué les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="26d1f-108">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="26d1f-109">Vous avez un compte de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="26d1f-109">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="26d1f-110">Vous avez créé un conteneur sous votre compte de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="26d1f-110">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="26d1f-111">Vous avez créé une stratégie sur un conteneur avec des droits en lecture, écriture et création de liste.</span><span class="sxs-lookup"><span data-stu-id="26d1f-111">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="26d1f-112">Vous avez également généré une clé SAS.</span><span class="sxs-lookup"><span data-stu-id="26d1f-112">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="26d1f-113">Vous avez créé des informations d'identification SQL Server sur l'ordinateur source reposant sur la signature d'accès partagé.</span><span class="sxs-lookup"><span data-stu-id="26d1f-113">You have created a SQL Server credential on the source machine based on Shared Access Signature.</span></span>  
  
-   <span data-ttu-id="26d1f-114">Vous avez créé une base de données sur l'ordinateur source.</span><span class="sxs-lookup"><span data-stu-id="26d1f-114">You have created a database in the source machine.</span></span>  
  
 <span data-ttu-id="26d1f-115">Pour restaurer une base de données dans Azure Storage, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="26d1f-115">To restore a database to Azure Storage, you can follow these steps:</span></span>  
  
1.  <span data-ttu-id="26d1f-116">Sur l'ordinateur source, démarrez SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="26d1f-116">In the source machine, start SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="26d1f-117">Lorsque vous êtes connecté à la base de données nouvellement créée, ouvrez la fenêtre de requête.</span><span class="sxs-lookup"><span data-stu-id="26d1f-117">When connected to the newly created database, open the query window.</span></span> <span data-ttu-id="26d1f-118">Exécutez l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="26d1f-118">Run the following statement:</span></span>  
  
    ```sql  
  
    USE TestDB3Restore;   
    GO   
    BACKUP DATABASE TestDB3Restore   
    TO DISK = 'C:\BACKUP\TestDB3Restore.Bak'   
       WITH FORMAT,   
       NAME = 'Full Backup of TestDB3Restore'   
    GO  
  
    ```  
  
3.  <span data-ttu-id="26d1f-119">Ensuite, copiez et exécutez les instructions suivantes dans la fenêtre de requête :</span><span class="sxs-lookup"><span data-stu-id="26d1f-119">Next, copy and run the following statements in the Query window.</span></span>  
  
    ```sql  
  
    USE master;   
    GO   
    RESTORE DATABASE TestDB3Restore    
    FROM DISK = 'C:\BACKUP\TestDB3Restore.bak'    
    WITH REPLACE,   
    MOVE 'TestDB3Restore' TO 'https://teststorageaccnt.blob.core.windows.net/testcontainrestore/TestDB3Restore.mdf',     
    MOVE 'TestDB3Restore_log' TO 'https://teststorageaccnt.blob.core.windows.net/testcontainrestore/TestDB3Restore_log.ldf';   
    GO  
  
    ```  
  
     <span data-ttu-id="26d1f-120">À l'issue de cette étape, votre conteneur doit répertorier les fichiers de données (.mdf) et les fichiers (.ldf) sur le Portail de gestion.</span><span class="sxs-lookup"><span data-stu-id="26d1f-120">At the end of this step, your container should list data (.mdf) and (.ldf) files on the Management Portal.</span></span>  
  
 <span data-ttu-id="26d1f-121">Pour restaurer une base de données avec des fichiers de données et des fichiers journaux pointant vers Azure Storage à l’aide de SQL Server Management Studio interface utilisateur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="26d1f-121">To restore a database with data and log files pointing to Azure Storage using SQL Server Management Studio user interface, perform these steps:</span></span>  
  
1.  <span data-ttu-id="26d1f-122">Dans l' **Explorateur d’objets**, cliquez sur le nom du serveur pour développer l’arborescence du serveur.</span><span class="sxs-lookup"><span data-stu-id="26d1f-122">In **Object Explorer**, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="26d1f-123">Développez **bases de données**, puis sélectionnez votre base de données.</span><span class="sxs-lookup"><span data-stu-id="26d1f-123">Expand **Databases**, and, select your database.</span></span>  
  
3.  <span data-ttu-id="26d1f-124">Cliquez avec le bouton droit sur la base de données, pointez sur **Tâches**, puis cliquez sur **Restaurer**.</span><span class="sxs-lookup"><span data-stu-id="26d1f-124">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="26d1f-125">Sur la page **général** , dans la section source de **restauration** , cliquez sur périphérique **source** .</span><span class="sxs-lookup"><span data-stu-id="26d1f-125">On the **General** page, in the **Restore** source section, click **Source** device.</span></span>  
  
5.  <span data-ttu-id="26d1f-126">Cliquez sur le bouton Parcourir de la zone de texte Périphérique **source** afin d'ouvrir la boîte de dialogue **Sélectionner les unités de sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="26d1f-126">Click the browse button for the **Source** device text box, which opens the **Select Backup Devices** dialog box.</span></span>  
  
6.  <span data-ttu-id="26d1f-127">Dans la zone de texte de support de sauvegarde, sélectionnez **Fichier**, puis cliquez sur le bouton **Ajouter** pour localiser le fichier de sauvegarde (.bak).</span><span class="sxs-lookup"><span data-stu-id="26d1f-127">In the Backup media text box, select **File**, and click the **Add** button to locate the backup (.bak) file.</span></span> <span data-ttu-id="26d1f-128">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="26d1f-128">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="26d1f-129">Cliquez sur **fichiers** sur la première page.</span><span class="sxs-lookup"><span data-stu-id="26d1f-129">Click **Files** on the first page.</span></span>  
  
8.  <span data-ttu-id="26d1f-130">Dans la section **restaurer les fichiers de la base de données** en tant que, sous le champ **Restaurer sous** , tapez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="26d1f-130">In the **Restore Database Files** as section, under **Restore As** field, type the followings:</span></span>  
  
     <span data-ttu-id="26d1f-131">Pour fichier de données, tapez : `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS.mdf` .</span><span class="sxs-lookup"><span data-stu-id="26d1f-131">For data file, type: `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS.mdf`.</span></span> <span data-ttu-id="26d1f-132">Pour fichier journal, tapez : `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS_log.ldf` .</span><span class="sxs-lookup"><span data-stu-id="26d1f-132">For log file, type: `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS_log.ldf`.</span></span>  
  
     <span data-ttu-id="26d1f-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-8.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="26d1f-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-8.gif "SQL 14 CTP2")</span></span>  
  
9. <span data-ttu-id="26d1f-134">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="26d1f-134">Click **OK**.</span></span>  
  
 <span data-ttu-id="26d1f-135">Lorsque la restauration est effectuée, connectez-vous au Portail de gestion.</span><span class="sxs-lookup"><span data-stu-id="26d1f-135">When the restore is done, log in to the Management Portal.</span></span> <span data-ttu-id="26d1f-136">Vous devez pouvoir consulter les fichiers .mdf et .ldf dans le conteneur comme suit :</span><span class="sxs-lookup"><span data-stu-id="26d1f-136">You should be able to see the .mdf and .ldf files in the container as follows:</span></span>  
  
 <span data-ttu-id="26d1f-137">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-9.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="26d1f-137">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-9.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="26d1f-138">**Leçon suivante :**</span><span class="sxs-lookup"><span data-stu-id="26d1f-138">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="26d1f-139">Leçon 9. Restaurer une base de données à partir du stockage Azure</span><span class="sxs-lookup"><span data-stu-id="26d1f-139">Lesson 9. Restore a database from Azure Storage</span></span>](../relational-databases/lesson-8-restore-as-new-database-from-log-backup.md)  
  
  
