---
title: 'Leçon 4 : créer une base de données dans le stockage Azure | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: a9ae1501-b614-49d3-b975-6569da8350b2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 50fca85111d5897b738e577e7735049e0b055a03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614039"
---
# <a name="lesson-4-create-a-database-in-azure-storage"></a><span data-ttu-id="de4cf-102">Leçon 4 : Créer une base de données dans Stockage Azure</span><span class="sxs-lookup"><span data-stu-id="de4cf-102">Lesson 4: Create a database in Azure Storage</span></span>
  <span data-ttu-id="de4cf-103">Dans cette leçon, vous allez apprendre à créer une base de données à l’aide de la fonctionnalité fichiers de données SQL Server dans Azure.</span><span class="sxs-lookup"><span data-stu-id="de4cf-103">In this lesson, you will learn how to create a database using the SQL Server Data Files in Azure feature.</span></span> <span data-ttu-id="de4cf-104">Notez que vous devez avoir terminé les leçons 1, 2 et 3 avant d'effectuer les tâches de cette leçon.</span><span class="sxs-lookup"><span data-stu-id="de4cf-104">Note that before this lesson, you must complete the Lesson 1, 2, and 3.</span></span> <span data-ttu-id="de4cf-105">La leçon 3 est une étape très importante, car vous devez stocker les informations relatives à votre conteneur de stockage Azure, ainsi que le nom de la stratégie et la clé SAS qui lui sont associés dans le magasin d’informations d’identification SQL Server avant la leçon 4.</span><span class="sxs-lookup"><span data-stu-id="de4cf-105">Lesson 3 is a very important step because you need to store the information about your Azure storage container and its associated policy name and SAS key in the SQL Server credential store before Lesson 4.</span></span>  
  
 <span data-ttu-id="de4cf-106">Pour chaque conteneur de stockage utilisé par un fichier de données ou un fichier journal, vous devez créer des informations d'identification SQL Server dont le nom correspond au chemin d'accès du conteneur.</span><span class="sxs-lookup"><span data-stu-id="de4cf-106">For each storage container used by a data or log file, you must create a SQL Server Credential whose name matches the container path.</span></span> <span data-ttu-id="de4cf-107">Ensuite, vous pouvez créer une nouvelle base de données dans le stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="de4cf-107">Then, you can create a new database in Azure Storage</span></span>  
  
 <span data-ttu-id="de4cf-108">Cette leçon suppose que vous avez déjà effectué les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="de4cf-108">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="de4cf-109">Vous avez un compte de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="de4cf-109">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="de4cf-110">Vous avez créé un conteneur sous votre compte de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="de4cf-110">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="de4cf-111">Vous avez créé une stratégie sur un conteneur avec des droits en lecture, écriture et création de liste.</span><span class="sxs-lookup"><span data-stu-id="de4cf-111">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="de4cf-112">Vous avez également généré une clé SAS.</span><span class="sxs-lookup"><span data-stu-id="de4cf-112">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="de4cf-113">Vous avez créé des informations d'identification SQL Server sur l'ordinateur source.</span><span class="sxs-lookup"><span data-stu-id="de4cf-113">You have created a SQL Server credential on the source machine.</span></span>  
  
 <span data-ttu-id="de4cf-114">Pour créer une base de données dans Azure à l’aide de la fonctionnalité fichiers de données SQL Server dans stockage Azure, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="de4cf-114">To create a database in Azure using the SQL Server Data Files in Azure Storage feature, follow these steps:</span></span>  
  
1.  <span data-ttu-id="de4cf-115">Connectez-vous à SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="de4cf-115">Connect to SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="de4cf-116">Dans l'Explorateur d'objets, connectez-vous à l'instance du moteur de base de données installée.</span><span class="sxs-lookup"><span data-stu-id="de4cf-116">In Object Explorer, connect to the instance of Database Engine installed.</span></span>  
  
3.  <span data-ttu-id="de4cf-117">Dans la barre d'outils standard, cliquez sur Nouvelle requête.</span><span class="sxs-lookup"><span data-stu-id="de4cf-117">On the Standard tool bar, click New Query.</span></span>  
  
4.  <span data-ttu-id="de4cf-118">Copiez et collez l'exemple suivant dans la fenêtre de requête et modifiez-le si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="de4cf-118">Copy and paste the following example into the query window, modify as needed.</span></span> <span data-ttu-id="de4cf-119">Notez que le champ FILENAME fait référence au chemin d'accès d'URI de la base de données dans le conteneur de stockage et doit commencer par https.</span><span class="sxs-lookup"><span data-stu-id="de4cf-119">Note that the FILENAME field refers to the URI path of the database file in storage container and it must start with https.</span></span>  
  
    ```  
  
    --Create a database that uses a SQL Server credential    
    CREATE DATABASE TestDB1    
    ON   
    (NAME = TestDB1_data,   
       FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Data.mdf')   
     LOG ON   
    (NAME = TestDB1_log,   
        FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Log.ldf')   
    GO  
  
    ```  
  
     <span data-ttu-id="de4cf-120">Ajoutez des données à votre base de données.</span><span class="sxs-lookup"><span data-stu-id="de4cf-120">Add some data to your database.</span></span>  
  
    ```  
  
    USE TestDB1;   
    GO   
    CREATE TABLE Table1 (Col1 int primary key, Col2 varchar(20));   
    GO   
    INSERT INTO Table1 (Col1, Col2) VALUES (1, 'string1'), (2, 'string2');   
    GO  
  
    ```  
  
5.  <span data-ttu-id="de4cf-121">Pour afficher la nouvelle base de données TestDB1 sur votre serveur SQL Server local, actualisez les bases de données dans l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="de4cf-121">To see the new TestDB1 in your on-premises SQL Server, refresh databases in the Object Explorer.</span></span>  
  
6.  <span data-ttu-id="de4cf-122">De même, pour afficher la base de données nouvellement créée dans votre compte de stockage, connectez-vous à votre compte de stockage via SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="de4cf-122">Similarly, to see the newly created database in your storage account, connect to your storage account via SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="de4cf-123">Pour plus d’informations sur la façon de se connecter à un stockage Azure à l’aide de SQL Server Management Studio, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="de4cf-123">For information on how to connect to an Azure storage using SQL Server Management Studio, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="de4cf-124">Tout d'abord, obtenez les informations sur le compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="de4cf-124">First, get the storage account information.</span></span> <span data-ttu-id="de4cf-125">Connectez-vous au Portail de gestion.</span><span class="sxs-lookup"><span data-stu-id="de4cf-125">Log in to the Management Portal.</span></span> <span data-ttu-id="de4cf-126">Cliquez ensuite sur **stockage** et choisissez votre compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="de4cf-126">Then, click **Storage** and choose your storage account.</span></span> <span data-ttu-id="de4cf-127">Quand un compte de stockage est sélectionné, cliquez sur **gérer les clés d’accès** au bas de la page.</span><span class="sxs-lookup"><span data-stu-id="de4cf-127">When a storage account is selected, click **Manage Access Keys** at the bottom of the page.</span></span> <span data-ttu-id="de4cf-128">Cela permet d'ouvrir une fenêtre de dialogue similaire :</span><span class="sxs-lookup"><span data-stu-id="de4cf-128">This opens a similar dialog window:</span></span>  
  
         <span data-ttu-id="de4cf-129">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-1.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="de4cf-129">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-1.gif "SQL 14 CTP2")</span></span>  
  
    2.  <span data-ttu-id="de4cf-130">Copiez les valeurs **nom du compte de stockage** et clé d' **accès primaire** dans la fenêtre de dialogue **connexion au stockage Azure** dans SSMS.</span><span class="sxs-lookup"><span data-stu-id="de4cf-130">Copy the **Storage Account Name** and **Primary Access Key** values to the **Connect to Azure Storage** dialog window in SSMS.</span></span> <span data-ttu-id="de4cf-131">Cliquez ensuite sur **Connecter**.</span><span class="sxs-lookup"><span data-stu-id="de4cf-131">Then, click **Connect**.</span></span> <span data-ttu-id="de4cf-132">Les informations sur les conteneurs du compte de stockage s'affichent dans SSMS, comme illustré dans la capture d'écran suivante :</span><span class="sxs-lookup"><span data-stu-id="de4cf-132">This brings the information about storage account containers to SSMS as shown in the following screenshot:</span></span>  
  
         <span data-ttu-id="de4cf-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="de4cf-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="de4cf-134">La capture d’écran suivante illustre la nouvelle base de données créée à la fois dans l’environnement de stockage local et Azure.</span><span class="sxs-lookup"><span data-stu-id="de4cf-134">The following screenshot demonstrates the new created database both in on-premises and Azure Storage environment.</span></span>  
  
 <span data-ttu-id="de4cf-135">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2b.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="de4cf-135">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2b.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="de4cf-136">**Remarque :** S’il existe des références actives aux fichiers de données dans un conteneur, toute tentative de suppression des informations d’identification de SQL Server associées échoue.</span><span class="sxs-lookup"><span data-stu-id="de4cf-136">**Note:** If there are any active references to data files in a container, any attempts to delete the associated SQL Server credential fails.</span></span> <span data-ttu-id="de4cf-137">De même, s'il existe déjà un bail sur un fichier de base de données spécifique d'un objet blob et que vous voulez le supprimer, vous devez d'abord résilier le bail sur l'objet blob.</span><span class="sxs-lookup"><span data-stu-id="de4cf-137">Similarly, if there is already a lease on a specific database file in a blob and you want to delete it, first you need to break the lease on the blob.</span></span> <span data-ttu-id="de4cf-138">Pour rompre le bail, vous pouvez utiliser un [objet blob de bail](https://msdn.microsoft.com/library/azure/ee691972.aspx).</span><span class="sxs-lookup"><span data-stu-id="de4cf-138">To break the lease, you can use [Lease Blob](https://msdn.microsoft.com/library/azure/ee691972.aspx).</span></span>  
  
 <span data-ttu-id="de4cf-139">Grâce à cette nouvelle fonctionnalité, configurez SQL Server afin que les instructions CREATE DATABASE créent par défaut une base de données activée pour le cloud.</span><span class="sxs-lookup"><span data-stu-id="de4cf-139">Using this new feature, you can configure SQL Server so that any CREATE DATABASE statement will default to a cloud enabled database.</span></span> <span data-ttu-id="de4cf-140">En d’autres termes, vous pouvez définir des emplacements de données et de journaux par défaut dans les propriétés de SQL Server Management Studio instance de serveur. ainsi, chaque fois que vous créez une base de données, tous les fichiers de base de données (. mdf,. ldf) sont créés en tant qu’objets BLOB de pages dans le stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="de4cf-140">In other words, you can set default data and log locations in SQL Server Management Studio Server instance properties so anytime you create a database, all database files (.mdf, .ldf) are created as page blobs in Azure Storage.</span></span>  
  
 <span data-ttu-id="de4cf-141">Pour créer une base de données dans Azure Storage à l’aide de SQL Server Management Studio interface utilisateur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="de4cf-141">To create a database in Azure Storage by using SQL Server Management Studio user interface, perform these steps:</span></span>  
  
1.  <span data-ttu-id="de4cf-142">Dans l'Explorateur d'objets, connectez-vous à une instance du moteur de base de données SQL Server et développez-la.</span><span class="sxs-lookup"><span data-stu-id="de4cf-142">In Object Explorer, connect to an instance of the SQL Server Database Engine and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="de4cf-143">Cliquez avec le bouton droit sur Bases de données, puis cliquez sur Nouvelle base de données.</span><span class="sxs-lookup"><span data-stu-id="de4cf-143">Right-click Databases, and then click New Database.</span></span>  
  
3.  <span data-ttu-id="de4cf-144">Dans la boîte de dialogue Nouvelle base de données, tapez un nom de base de données.</span><span class="sxs-lookup"><span data-stu-id="de4cf-144">In the New Database dialog window, type a database name.</span></span>  
  
4.  <span data-ttu-id="de4cf-145">Modifiez les valeurs par défaut des données primaires et des fichiers journaux de transactions, dans la grille Fichiers de la base de données, cliquez sur la cellule appropriée, puis entrez la nouvelle valeur.</span><span class="sxs-lookup"><span data-stu-id="de4cf-145">Change the default values of the primary data and transaction log files, in the Database files grid, click the appropriate cell and enter the new value.</span></span> <span data-ttu-id="de4cf-146">Spécifiez également le chemin d'accès de l'emplacement du fichier.</span><span class="sxs-lookup"><span data-stu-id="de4cf-146">Also, specify the path for the file location.</span></span> <span data-ttu-id="de4cf-147">Pour le chemin d'accès, tapez le chemin d'accès de l'URL du conteneur de stockage, notamment `https://teststorageaccnt.blob.core.windows.net/testcontainer/`.</span><span class="sxs-lookup"><span data-stu-id="de4cf-147">For Path, type the URL path of the storage container, such as `https://teststorageaccnt.blob.core.windows.net/testcontainer/`.</span></span> <span data-ttu-id="de4cf-148">Pour le nom de fichier, entrez les noms de fichiers physique des fichiers de base de données (.mdf, .ldf).</span><span class="sxs-lookup"><span data-stu-id="de4cf-148">For FileName, type the physical file names of the database files (.mdf, .ldf).</span></span>  
  
     <span data-ttu-id="de4cf-149">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-4.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="de4cf-149">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-4.gif "SQL 14 CTP2")</span></span>  
  
     <span data-ttu-id="de4cf-150">Pour plus d’informations, consultez [Ajouter des fichiers de données ou journaux à une base de données](databases/add-data-or-log-files-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="de4cf-150">For more information, see [Add Data or Log Files to a Database](databases/add-data-or-log-files-to-a-database.md).</span></span>  
  
5.  <span data-ttu-id="de4cf-151">Conservez toutes les autres valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="de4cf-151">Keep all other default values.</span></span>  
  
6.  <span data-ttu-id="de4cf-152">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="de4cf-152">Click OK.</span></span>  
  
 <span data-ttu-id="de4cf-153">Pour afficher la nouvelle base de données TestDB1 sur votre serveur SQL Server local, actualisez les bases de données dans l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="de4cf-153">To see the new TestDB1 in your on-premises SQL Server, refresh databases in the Object Explorer.</span></span> <span data-ttu-id="de4cf-154">De même, pour afficher la base de données nouvellement créée dans votre compte de stockage, connectez-vous à votre compte de stockage via SQL Server Management Studio (SSMS), comme expliqué précédemment dans cette leçon.</span><span class="sxs-lookup"><span data-stu-id="de4cf-154">Similarly, to see the newly created database in your storage account, connect to your storage account via SQL Server Management Studio (SSMS) as explained earlier in this lesson.</span></span>  
  
 <span data-ttu-id="de4cf-155">**Leçon suivante :**</span><span class="sxs-lookup"><span data-stu-id="de4cf-155">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="de4cf-156">Leçon 5. &#40;facultatif&#41; chiffrer votre base de données à l’aide de TDE</span><span class="sxs-lookup"><span data-stu-id="de4cf-156">Lesson 5. &#40;Optional&#41; Encrypt your database using TDE</span></span>](../relational-databases/lesson-4-restore-database-to-virtual-machine-from-url.md)  
  
  
