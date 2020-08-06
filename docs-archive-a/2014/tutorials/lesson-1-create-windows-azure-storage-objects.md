---
title: 'Leçon 1 : créer des objets de stockage Azure | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 74edd1fd-ab00-46f7-9e29-7ba3f1a446c5
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: d46c6d22ffd92dbf8035bff140960af8ef56122d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601846"
---
# <a name="lesson-1-create-azure-storage-objects"></a><span data-ttu-id="d4617-102">Leçon 1 : Créer des objets de stockage Azure</span><span class="sxs-lookup"><span data-stu-id="d4617-102">Lesson 1: Create Azure Storage Objects</span></span>
  <span data-ttu-id="d4617-103">Avant de créer des sauvegardes [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] dans le Cloud de stockage, vous devez tout d'abord créer un compte de stockage, puis un conteneur d'objets blob.</span><span class="sxs-lookup"><span data-stu-id="d4617-103">Before you can create [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backups on cloud storage, you must first create a storage account, and then a blob container.</span></span> <span data-ttu-id="d4617-104">La leçon 1 vous guide tout au long des étapes de connexion à la Portail de gestion Azure, en créant un compte de stockage et un conteneur d’objets BLOB.</span><span class="sxs-lookup"><span data-stu-id="d4617-104">Lesson 1 walks you through the steps of Logging into the Azure Management Portal, creating a storage account and a blob container.</span></span>  
  
## <a name="create-a-storage-account"></a><span data-ttu-id="d4617-105">Créer un compte de stockage</span><span class="sxs-lookup"><span data-stu-id="d4617-105">Create a storage Account</span></span>  
 <span data-ttu-id="d4617-106">Pour créer un compte de stockage à partir du Portail de gestion Azure, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d4617-106">To create a storage account from the Azure Management Portal, use the following steps:</span></span>  
  
1.  <span data-ttu-id="d4617-107">Connectez-vous au portail de gestion Azure à l'aide de votre compte.</span><span class="sxs-lookup"><span data-stu-id="d4617-107">Log in to the Azure Management Portal using your account.</span></span> <span data-ttu-id="d4617-108">Si vous n’avez pas de compte Azure, [consultez la version d’évaluation gratuite de 3 mois d’Azure](https://go.microsoft.com/fwlink/?LinkId=271927).</span><span class="sxs-lookup"><span data-stu-id="d4617-108">If you do not have an Azure account, [visit Azure 3-Month free trial](https://go.microsoft.com/fwlink/?LinkId=271927).</span></span>  
  
     <span data-ttu-id="d4617-109">![Écran de connexion Azure](../../2014/tutorials/media/windowazurelogin-backuptocloud.gif "Écran de connexion Azure")</span><span class="sxs-lookup"><span data-stu-id="d4617-109">![Azure Login Screen](../../2014/tutorials/media/windowazurelogin-backuptocloud.gif "Azure Login Screen")</span></span>  
  
2.  <span data-ttu-id="d4617-110">Pour créer un compte de stockage, suivez les instructions pas à pas détaillées [ici](https://go.microsoft.com/fwlink/?LinkId=271926).</span><span class="sxs-lookup"><span data-stu-id="d4617-110">Use the step by step instructions detailed [here](https://go.microsoft.com/fwlink/?LinkId=271926), to create a storage account.</span></span>  
  
3.  <span data-ttu-id="d4617-111">Accédez au compte de stockage créé à l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="d4617-111">Browse to the storage account you created in previous step.</span></span> <span data-ttu-id="d4617-112">Dans le centre en bas de la page Web, cliquez sur **gérer les clés**.</span><span class="sxs-lookup"><span data-stu-id="d4617-112">From the bottom center of the web page, click **MANAGE KEYS**.</span></span> <span data-ttu-id="d4617-113">Les informations de compte sont affichées.</span><span class="sxs-lookup"><span data-stu-id="d4617-113">The account information is displayed.</span></span> <span data-ttu-id="d4617-114">Copiez le nom du compte de stockage et les clés d'accès.</span><span class="sxs-lookup"><span data-stu-id="d4617-114">Copy the storage account name, and the Access Keys.</span></span> <span data-ttu-id="d4617-115">Ces informations sont nécessaires pour créer des informations d'identification stockées dans SQL.</span><span class="sxs-lookup"><span data-stu-id="d4617-115">This information is required to create SQL Stored Credentials.</span></span> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="d4617-116">utilise ces informations pour accéder au compte de stockage et créer des sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="d4617-116">uses this information to access the storage account and create backups.</span></span>  
  
     <span data-ttu-id="d4617-117">![Capture d’écran des clés de compte de stockage Azure](../../2014/tutorials/media/manageaccesskeys-backuptocloud.gif "Capture d’écran des clés de compte de stockage Azure")</span><span class="sxs-lookup"><span data-stu-id="d4617-117">![Screen shot of Azure Storage Account Keys](../../2014/tutorials/media/manageaccesskeys-backuptocloud.gif "Screen shot of Azure Storage Account Keys")</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d4617-118">Vous pouvez également créer un compte de stockage par programme à l'aide des API REST.</span><span class="sxs-lookup"><span data-stu-id="d4617-118">You can also create a storage account programmatically using REST APIs.</span></span> <span data-ttu-id="d4617-119">Pour plus d'informations, consultez [Créer un compte de stockage](https://go.microsoft.com/fwlink/?LinkId=271928).</span><span class="sxs-lookup"><span data-stu-id="d4617-119">For more information, see [Create Storage Account](https://go.microsoft.com/fwlink/?LinkId=271928).</span></span>  
  
### <a name="create-a-blob-container"></a><span data-ttu-id="d4617-120">Créer un conteneur d'objets blob</span><span class="sxs-lookup"><span data-stu-id="d4617-120">Create a Blob Container</span></span>  
 <span data-ttu-id="d4617-121">Un conteneur regroupe un ensemble d’objets blob.</span><span class="sxs-lookup"><span data-stu-id="d4617-121">A container provides a grouping of a set of blobs.</span></span> <span data-ttu-id="d4617-122">Tous les objets blob doivent figurer dans un conteneur.</span><span class="sxs-lookup"><span data-stu-id="d4617-122">All blobs must be in a container.</span></span> <span data-ttu-id="d4617-123">Un compte peut contenir un nombre illimité de conteneurs, mais doit comporter au moins un conteneur.</span><span class="sxs-lookup"><span data-stu-id="d4617-123">An account can contain an unlimited number of containers, but must have at least one container.</span></span> <span data-ttu-id="d4617-124">Un conteneur peut stocker un nombre illimité d’objets blob.</span><span class="sxs-lookup"><span data-stu-id="d4617-124">A container can store an unlimited number of blobs.</span></span>  
  
 <span data-ttu-id="d4617-125">Pour créer un conteneur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d4617-125">To create a Container, use the following steps:</span></span>  
  
1.  <span data-ttu-id="d4617-126">Sélectionnez le compte de stockage, cliquez sur l’onglet **conteneurs** , puis cliquez sur **Ajouter un conteneur** en bas de l’écran pour ouvrir une nouvelle boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d4617-126">Select the storage account, click the **CONTAINERS** tab and click **ADD CONTAINER** at the bottom of the screen which opens a new dialog box.</span></span>  
  
     <span data-ttu-id="d4617-127">![Création d'un conteneur dans le portail de gestion](../../2014/tutorials/media/backuptocloud.gif "Création d'un conteneur dans le portail de gestion")</span><span class="sxs-lookup"><span data-stu-id="d4617-127">![Creating a Container in the Management Portal](../../2014/tutorials/media/backuptocloud.gif "Creating a Container in the Management Portal")</span></span>  
  
2.  <span data-ttu-id="d4617-128">Entrez le nom du conteneur.</span><span class="sxs-lookup"><span data-stu-id="d4617-128">Enter the name for the container.</span></span> <span data-ttu-id="d4617-129">Notez le nom de conteneur spécifié.</span><span class="sxs-lookup"><span data-stu-id="d4617-129">Make a note of the container name you specified.</span></span> <span data-ttu-id="d4617-130">Ces informations sont utilisées dans l'URL (chemin d'accès au fichier de sauvegarde) dans les instructions T-SQL des leçons 3 et 4.</span><span class="sxs-lookup"><span data-stu-id="d4617-130">This information is used in the URL (path to backup file) in the T-SQL statements in lesson 3 and 4.</span></span>  
  
3.  <span data-ttu-id="d4617-131">Sélectionnez Privé pour le **Type d'accès**.</span><span class="sxs-lookup"><span data-stu-id="d4617-131">Select Private for **Access Type**.</span></span> <span data-ttu-id="d4617-132">Nous vous recommandons de créer des conteneurs privés pour sécuriser vos fichiers de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="d4617-132">We recommend creating private containers for securing your backup files.</span></span>  
  
     <span data-ttu-id="d4617-133">![Création d'un nouveau conteneur d'objets blob](../../2014/tutorials/media/backuptocloud-newblobcontainer.gif "Création d'un nouveau conteneur d'objets blob")</span><span class="sxs-lookup"><span data-stu-id="d4617-133">![Creating a new blob container](../../2014/tutorials/media/backuptocloud-newblobcontainer.gif "Creating a new blob container")</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d4617-134">L'authentification auprès du compte de stockage est requise pour la sauvegarde et la restauration [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] même si vous choisissez de créer un conteneur public.</span><span class="sxs-lookup"><span data-stu-id="d4617-134">Authentication to the storage account is required for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backup and restore even if you choose to create a public container.</span></span>  
    >   
    >  <span data-ttu-id="d4617-135">Vous pouvez également créer un conteneur par programme à l'aide des API REST.</span><span class="sxs-lookup"><span data-stu-id="d4617-135">You can also create a container programmatically using REST APIs.</span></span> <span data-ttu-id="d4617-136">Pour plus d’informations, consultez [créer un conteneur](https://go.microsoft.com/fwlink/?LinkId=271946).</span><span class="sxs-lookup"><span data-stu-id="d4617-136">For more information, see [Create Container](https://go.microsoft.com/fwlink/?LinkId=271946).</span></span>  
  
### <a name="next-lesson"></a><span data-ttu-id="d4617-137">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="d4617-137">Next Lesson</span></span>  
 <span data-ttu-id="d4617-138">[Leçon 2 : créer des informations d’identification de SQL Server](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md).</span><span class="sxs-lookup"><span data-stu-id="d4617-138">[Lesson 2: Create a SQL Server Credential](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md).</span></span>  
  
  
