---
title: 'Leçon 6 : migrer une base de données d’une machine source locale vers une machine de destination dans Azure | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: d9134ade-7b03-4c5c-8ed3-3bc369a61691
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b9af8a260493561f9728d1677b7667bd3f36cb46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612324"
---
# <a name="lesson-6-migrate-a-database-from-a-source-machine-on-premises-to-a-destination-machine-in-azure"></a><span data-ttu-id="e2e3f-102">Leçon 6 : Migrer une base de données d’une machine source locale vers une machine de destination dans Azure</span><span class="sxs-lookup"><span data-stu-id="e2e3f-102">Lesson 6: Migrate a database from a source machine on-premises to a destination machine in Azure</span></span>
  <span data-ttu-id="e2e3f-103">Cette leçon part du principe que vous disposez déjà d’un autre SQL Server, qui peut résider sur un autre ordinateur local ou sur une machine virtuelle dans Azure.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-103">This lesson assumes that you already have another SQL Server, which might reside in another on-premises computer or in a virtual machine in Azure.</span></span> <span data-ttu-id="e2e3f-104">Pour plus d’informations sur la création d’une machine virtuelle SQL Server dans Azure, consultez [configuration d’une machine virtuelle SQL Server sur Azure](https://www.windowsazure.com/manage/windows/common-tasks/install-sql-server/).</span><span class="sxs-lookup"><span data-stu-id="e2e3f-104">For information on how to create a SQL Server virtual machine in Azure, see [Provisioning a SQL Server Virtual Machine on Azure](https://www.windowsazure.com/manage/windows/common-tasks/install-sql-server/).</span></span> <span data-ttu-id="e2e3f-105">Après avoir configuré une machine virtuelle SQL Server dans Azure, assurez-vous que vous pouvez vous connecter à une instance de SQL Server de cette machine virtuelle via SQL Server Management Studio sur un autre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-105">After provisioning a SQL Server virtual machine in Azure, make sure that you can connect to an instance of SQL Server in this virtual machine via SQL Server Management Studio in another computer.</span></span>  
  
 <span data-ttu-id="e2e3f-106">Cette leçon suppose également que vous avez déjà effectué les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="e2e3f-106">This lesson also assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="e2e3f-107">Vous avez un compte de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-107">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="e2e3f-108">Vous avez créé un conteneur sous votre compte de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-108">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="e2e3f-109">Vous avez créé une stratégie sur un conteneur avec des droits en lecture, écriture et création de liste.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-109">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="e2e3f-110">Vous avez également généré une clé SAS.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-110">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="e2e3f-111">Vous avez créé des informations d'identification SQL Server sur l'ordinateur source.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-111">You have created a SQL Server credential on the source machine.</span></span>  
  
-   <span data-ttu-id="e2e3f-112">Vous avez déjà créé une destination SQL Server machine virtuelle dans Azure.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-112">You already have created a destination SQL Server virtual machine in Azure.</span></span> <span data-ttu-id="e2e3f-113">Nous vous recommandons de la créer en sélectionnant une image de plateforme comprenant SQL Server 2014.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-113">We recommend that you create it by selecting a platform image that includes SQL Server 2014.</span></span>  
  
 <span data-ttu-id="e2e3f-114">Pour migrer une base de données de SQL Server local vers une autre machine virtuelle dans Azure, vous pouvez suivre les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="e2e3f-114">To migrate a database from SQL Server on-premises to another virtual machine in Azure, you can follow these steps:</span></span>  
  
1.  <span data-ttu-id="e2e3f-115">Dans l'ordinateur source (un ordinateur local dans ce didacticiel), ouvrez une fenêtre de requête dans SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-115">In the source machine (which is an on-premises computer in this tutorial), open a query window in SQL Server Management Studio.</span></span> <span data-ttu-id="e2e3f-116">Détachez votre base de données pour la déplacer vers un autre ordinateur en exécutant ces instructions :</span><span class="sxs-lookup"><span data-stu-id="e2e3f-116">Detach your database to move it to another machine by executing these statements:</span></span>  
  
    ```  
    -- Detach the database in the source machine   
    USE master  
    EXEC sp_detach_db 'TestDB1', 'true';  
    ```  
  
2.  <span data-ttu-id="e2e3f-117">Si vous devez transférer une base de données vers un ordinateur de destination, vous devez d'abord le préparer.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-117">If you need to transfer a database to a destination machine, first you must prepare it.</span></span> <span data-ttu-id="e2e3f-118">Pour préparer l'ordinateur de destination, vous devez d'abord créer des informations d'identification SQL Server sur l'ordinateur de destination.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-118">To prepare your destination machine, first you need to create a SQL Server credential in the destination machine.</span></span> <span data-ttu-id="e2e3f-119">S'il s'agit d'une base de données chiffrée, vous devez également importer le certificat de l'ordinateur source vers l'ordinateur de destination.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-119">If it is an encrypted database, you need to import the certificate from the source machine to the destination machine as well.</span></span>  
  
    1.  <span data-ttu-id="e2e3f-120">Pour créer des informations d'identification SQL Server sur l'ordinateur de destination, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e2e3f-120">To create a SQL Server Credential in the destination machine, follow these steps:</span></span>  
  
        1.  <span data-ttu-id="e2e3f-121">Connectez-vous à l'ordinateur de destination via SQL Server Management Studio sur votre ordinateur source.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-121">Connect to the destination machine via SQL Server Management Studio in your source computer.</span></span>  <span data-ttu-id="e2e3f-122">Sinon, démarrez SQL Server Management Studio directement sur votre ordinateur de destination.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-122">Or, start SQL Server Management Studio in your destination computer directly.</span></span>  
  
        2.  <span data-ttu-id="e2e3f-123">Dans la barre d'outils standard , cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-123">On the Standard tool bar, click **New Query**.</span></span>  
  
        3.  <span data-ttu-id="e2e3f-124">Copiez et collez l'exemple suivant dans la fenêtre de requête et modifiez-le si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-124">Copy and paste the following example into the query window, modify as needed.</span></span> <span data-ttu-id="e2e3f-125">L’instruction suivante crée un SQL Server des informations d’identification pour stocker le certificat d’accès partagé de votre conteneur de stockage.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-125">The following statement creates a SQL Server Credential to store your storage container's Shared Access Certificate.</span></span>  
  
            ```sql  
  
            USE master   
            GO   
            CREATE CREDENTIAL [http://teststorageaccnt.blob.core.windows.net/testcontainer]   
            WITH IDENTITY='SHARED ACCESS SIGNATURE',   
            SECRET = 'your SAS key'   
            GO  
  
            ```  
  
        4.  <span data-ttu-id="e2e3f-126">Pour voir toutes les informations d'identification disponibles, exécutez l'instruction suivante dans la fenêtre de requête :</span><span class="sxs-lookup"><span data-stu-id="e2e3f-126">To see all available credentials, you can run the following statement in the query window:</span></span>  
  
            ```sql  
            SELECT * from sys.credentials   
            ```  
  
        5.  <span data-ttu-id="e2e3f-127">Une fois connecté au serveur de destination, ouvrez la fenêtre de requête, et exécutez :</span><span class="sxs-lookup"><span data-stu-id="e2e3f-127">When connected to the destination server, open query window, and run:</span></span>  
  
            ```sql  
  
            -- Create a master key and a server certificate   
            USE master   
            GO   
            CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'MySQLKey01'; -- You may use a different password.   
            GO   
            CREATE CERTIFICATE MySQLCert   
            FROM FILE = 'C:\certs\MySQLCert.CER'   
            WITH PRIVATE KEY   
            (   
            FILE = 'C:\certs\MySQLPrivateKeyFile.PVK',   
            DECRYPTION BY PASSWORD = 'MySQLKey01'   
            );   
            GO  
  
            ```  
  
             <span data-ttu-id="e2e3f-128">À l'issue de cette étape, l'ordinateur de destination a importé le certificat de chiffrement qui a été sauvegardé depuis l'ordinateur source.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-128">At the end of this step, the destination machine has imported the encryption certificate that was backed up from the source machine.</span></span> <span data-ttu-id="e2e3f-129">Ensuite, joignez les fichiers de données dans l'ordinateur de destination.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-129">Next, you can attach the data files in the destination machine.</span></span>  
  
    2.  <span data-ttu-id="e2e3f-130">Ensuite, créez une base de données avec des fichiers de données et des fichiers journaux pointant vers les fichiers existants dans Azure Storage à l’aide de l’option FOR ATTACH.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-130">Then, create a database with data and log files pointing to the existing files in Azure Storage by using FOR ATTACH option.</span></span> <span data-ttu-id="e2e3f-131">Dans la fenêtre de requête, exécutez l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="e2e3f-131">In the query window, run the following statement:</span></span>  
  
        ```sql  
  
        --Create a database on the destination server   
        CREATE DATABASE TestDB1onDest   
        ON   
        (NAME = TestDB1_data,   
            FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Data.mdf' )   
        LOG ON   
         (NAME = TestDB1_log,   
            FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Log.ldf')   
        FOR ATTACH   
        GO  
  
        ```  
  
    3.  <span data-ttu-id="e2e3f-132">Dans l'Explorateur d'objets, cliquez avec le bouton droit sur Bases de données, puis cliquez sur Actualiser.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-132">On the Object Explorer, click Databases, right-click Refresh.</span></span> <span data-ttu-id="e2e3f-133">La base de données TestDB1onDest nouvellement créée doit s'afficher.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-133">You should be able to see the newly created database TestDB1onDest listed.</span></span>  
  
    4.  <span data-ttu-id="e2e3f-134">Ensuite, dans la fenêtre de requête, exécutez l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="e2e3f-134">Next, run the following statement in the query window:</span></span>  
  
        ```sql  
  
        USE TestDB1onDest   
        SELECT * FROM Table1;   
        GO  
  
        ```  
  
         <span data-ttu-id="e2e3f-135">Elle doit répertorier toutes les données entrées dans la leçon 4.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-135">This should list all the data you entered in Lesson 4.</span></span>  
  
 <span data-ttu-id="e2e3f-136">Notez que la base de données chiffrée a été transférée vers une autre instance de calcul sans déplacer de données.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-136">Note that the encrypted database was transferred to another compute instance with no data movement.</span></span>  
  
 <span data-ttu-id="e2e3f-137">Pour créer une base de données avec des fichiers de données et des fichiers journaux pointant vers les fichiers existants dans le stockage Azure à l’aide d’SQL Server Management Studio interface utilisateur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e2e3f-137">To create a database with data and log files pointing to the existing files in Azure Storage using SQL Server Management Studio user interface, perform these steps:</span></span>  
  
1.  <span data-ttu-id="e2e3f-138">Dans l’ **Explorateur d’objets**, connectez-vous à une instance du moteur de base de données SQL Server et développez-la.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-138">In **Object Explorer**, connect to an instance of the SQL Server Database Engine and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="e2e3f-139">Cliquez avec le bouton droit sur **Bases de données**, puis cliquez sur **Nouvelle base de données**.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-139">Right-click **Databases**, and then click **New Database**.</span></span> <span data-ttu-id="e2e3f-140">Ensuite, cliquez avec le bouton droit sur TestDB1.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-140">Then, right-click TestDB1.</span></span> <span data-ttu-id="e2e3f-141">Cliquez sur Tâches, puis cliquez sur Détacher.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-141">Click Tasks, and then click Detach.</span></span> <span data-ttu-id="e2e3f-142">Dans la fenêtre de dialogue Détacher, cochez Supprimer les connexions.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-142">In the Detach dialog window, check Drop Connections.</span></span> <span data-ttu-id="e2e3f-143">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-143">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="e2e3f-144">Connectez-vous à l'ordinateur de destination, sur lequel SQL Server 2014 CTP2 ou version ultérieure est installé.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-144">Connect to the destination machine, which has SQL Server 2014 CTP2 or later.</span></span> <span data-ttu-id="e2e3f-145">Pour préparer l'ordinateur de destination, vous devez créer des informations d'identification SQL Server sur l'ordinateur de destination de façon à indiquer le même conteneur que celui qui contient TestDB1.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-145">To prepare your destination machine, you need to create a SQL Server credential in the destination machine to point to the same container that you put TestDB1 in.</span></span> <span data-ttu-id="e2e3f-146">Si vous rattachez dans le même ordinateur, vous n'avez pas besoin de créer d'autres informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-146">If you are going to re-attach in the same computer, you do not need to create another credential.</span></span>  
  
4.  <span data-ttu-id="e2e3f-147">Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur **bases de données** , puis cliquez sur **attacher**.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-147">In **Object Explorer**, right-click **Databases** and click **Attach**.</span></span>  
  
5.  <span data-ttu-id="e2e3f-148">Dans la boîte de dialogue **attacher des bases de données** , pour spécifier la base de données à attacher, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-148">In the **Attach Databases** dialog box, to specify the database to be attached, click **Add**.</span></span> <span data-ttu-id="e2e3f-149">Dans la boîte de dialogue **Rechercher les fichiers de base de données** :</span><span class="sxs-lookup"><span data-stu-id="e2e3f-149">In the **Locate Database Files** dialog window:</span></span>  
  
     <span data-ttu-id="e2e3f-150">Pour emplacement du fichier de données de la base de données, tapez : `https://teststorageaccnt.blob.core.windows.net/testcontainer/` .</span><span class="sxs-lookup"><span data-stu-id="e2e3f-150">For Database Data File Location, type: `https://teststorageaccnt.blob.core.windows.net/testcontainer/`.</span></span>  
  
     <span data-ttu-id="e2e3f-151">Pour nom de fichier, tapez : `TestDB1Data.mdf` .</span><span class="sxs-lookup"><span data-stu-id="e2e3f-151">For File name, type: `TestDB1Data.mdf`.</span></span>  
  
6.  <span data-ttu-id="e2e3f-152">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2e3f-152">Click **OK**.</span></span>  
  
     <span data-ttu-id="e2e3f-153">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-6-7.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="e2e3f-153">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-6-7.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="e2e3f-154">**Leçon suivante :**</span><span class="sxs-lookup"><span data-stu-id="e2e3f-154">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="e2e3f-155">Leçon 7 : Déplacer vos fichiers de données dans le Stockage Azure</span><span class="sxs-lookup"><span data-stu-id="e2e3f-155">Lesson 7: Move your data files to Azure Storage</span></span>](../relational-databases/lesson-6-generate-activity-and-backup-log-using-file-snapshot-backup.md)  
  
