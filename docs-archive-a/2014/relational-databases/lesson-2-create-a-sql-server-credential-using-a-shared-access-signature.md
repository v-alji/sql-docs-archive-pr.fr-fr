---
title: 'Leçon 3 : créer des informations d’identification de SQL Server | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 29e57ebd-828f-4dff-b473-c10ab0b1c597
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 808438e544e3beb18b2e2afa9c399b5666277483
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707523"
---
# <a name="lesson-3-create-a-sql-server-credential"></a><span data-ttu-id="a582d-102">Leçon 3 : Créer des informations d'identification SQL Server</span><span class="sxs-lookup"><span data-stu-id="a582d-102">Lesson 3: Create a SQL Server Credential</span></span>
  <span data-ttu-id="a582d-103">Dans cette leçon, vous allez créer des informations d’identification pour stocker les informations de sécurité utilisées pour accéder au compte de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="a582d-103">In this lesson, you will create a credential to store security information used to access the Azure storage account.</span></span>  
  
 <span data-ttu-id="a582d-104">Les informations d'identification SQL Server sont des objets utilisés pour stocker les informations d'authentification requises pour la connexion à une ressource en dehors de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a582d-104">A SQL Server credential is an object that is used to store authentication information required to connect to a resource outside of SQL Server.</span></span> <span data-ttu-id="a582d-105">Les informations d'identification contiennent le chemin d'accès de l'URI du conteneur de stockage et les valeurs de clé de signature d'accès partagé.</span><span class="sxs-lookup"><span data-stu-id="a582d-105">The credential stores the URI path of the storage container and the shared access signature key values.</span></span> <span data-ttu-id="a582d-106">Pour chaque conteneur de stockage utilisé par un fichier de données ou un fichier journal, vous devez créer des informations d'identification SQL Server dont le nom correspond au chemin d'accès du conteneur.</span><span class="sxs-lookup"><span data-stu-id="a582d-106">For each storage container used by a data or log file, you must create a SQL Server Credential whose name matches the container path.</span></span>  
  
 <span data-ttu-id="a582d-107">Pour obtenir des informations générales sur les informations d’identification, consultez [informations d’identification &#40;Moteur de base de données&#41;](security/authentication-access/credentials-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="a582d-107">For general information about credentials, see [Credentials &#40;Database Engine&#41;](security/authentication-access/credentials-database-engine.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a582d-108">La configuration requise pour la création d’une SQL Server informations d’identification décrites ci-dessous sont spécifiques à la fonctionnalité [fichiers de données SQL Server dans Azure](databases/sql-server-data-files-in-microsoft-azure.md) .</span><span class="sxs-lookup"><span data-stu-id="a582d-108">The requirements for creating a SQL Server credential described below are specific to the [SQL Server Data Files in Azure](databases/sql-server-data-files-in-microsoft-azure.md) feature.</span></span> <span data-ttu-id="a582d-109">Pour plus d'informations sur la création d'informations d'identification pour les processus de sauvegarde dans le stockage Azure, consultez [Lesson 2: Create a SQL Server Credential](../tutorials/lesson-2-create-a-sql-server-credential.md).</span><span class="sxs-lookup"><span data-stu-id="a582d-109">For information on creating credentials for backup processes in Azure storage, see [Lesson 2: Create a SQL Server Credential](../tutorials/lesson-2-create-a-sql-server-credential.md).</span></span>  
  
 <span data-ttu-id="a582d-110">Pour créer des informations d'identification SQL Server, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a582d-110">To create a SQL Server Credential, follow these steps:</span></span>  
  
1.  <span data-ttu-id="a582d-111">Connectez-vous à SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="a582d-111">Connect to SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="a582d-112">Dans l'Explorateur d'objets, connectez-vous à l'instance du moteur de base de données installée.</span><span class="sxs-lookup"><span data-stu-id="a582d-112">In Object Explorer, connect to the instance of Database Engine installed.</span></span>  
  
3.  <span data-ttu-id="a582d-113">Dans la barre d'outils standard, cliquez sur Nouvelle requête.</span><span class="sxs-lookup"><span data-stu-id="a582d-113">On the Standard tool bar, click New Query.</span></span>  
  
4.  <span data-ttu-id="a582d-114">Copiez et collez l'exemple suivant dans la fenêtre de requête et modifiez-le si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a582d-114">Copy and paste the following example into the query window, modify as needed.</span></span> <span data-ttu-id="a582d-115">L’instruction suivante crée un SQL Server informations d’identification pour stocker le certificat d’accès partagé de votre conteneur de stockage.</span><span class="sxs-lookup"><span data-stu-id="a582d-115">The following statement will create a SQL Server Credential to store your storage container's Shared Access Certificate.</span></span>  
  
    ```sql  
  
    USE master  
    CREATE CREDENTIAL credentialname - this name should match the container path and it must start with https.   
       WITH IDENTITY='SHARED ACCESS SIGNATURE', -- this is a mandatory string and do not change it.   
       SECRET = 'sharedaccesssignature' -- this is the shared access signature key that you obtained in Lesson 2.   
    GO  
  
    ```  
  
     <span data-ttu-id="a582d-116">Pour plus d’informations, consultez [créer des informations d’identification &#40;&#41;Transact-SQL](/sql/t-sql/statements/create-credential-transact-sql) dans documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a582d-116">For detailed information, see [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) in SQL Server Books Online.</span></span>  
  
5.  <span data-ttu-id="a582d-117">Pour voir toutes les informations d'identification disponibles, exécutez l'instruction suivante dans la fenêtre de requête :</span><span class="sxs-lookup"><span data-stu-id="a582d-117">To see all available credentials, you can run the following statement in the query window:</span></span>  
  
    ```sql  
    SELECT * from sys.credentials  
    ```  
  
     <span data-ttu-id="a582d-118">Pour plus d’informations sur sys. Credentials, consultez [sys. credentials &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-credentials-transact-sql) dans documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a582d-118">For more information on sys.credentials, see [sys.credentials &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-credentials-transact-sql) in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="a582d-119">**Leçon suivante :**</span><span class="sxs-lookup"><span data-stu-id="a582d-119">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="a582d-120">Leçon 4 : Créer une base de données dans Stockage Azure</span><span class="sxs-lookup"><span data-stu-id="a582d-120">Lesson 4: Create a database in Azure Storage</span></span>](lesson-3-database-backup-to-url.md)  
  
  
