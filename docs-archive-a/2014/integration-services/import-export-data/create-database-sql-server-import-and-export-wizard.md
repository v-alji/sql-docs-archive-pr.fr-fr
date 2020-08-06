---
title: Créer la base de données (Assistant Importation et Exportation SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.createdatabase.f1
ms.assetid: 56a8a79f-086c-4bdc-8888-0045bb4b0cbf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 617b3fe10a17ae2d8659b51e85cdb3fed4470506
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611891"
---
# <a name="create-database-sql-server-import-and-export-wizard"></a><span data-ttu-id="940e4-102">Créer la base de données (Assistant Importation et Exportation SQL Server)</span><span class="sxs-lookup"><span data-stu-id="940e4-102">Create Database (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="940e4-103">Utilisez la page **créer une base de données** pour définir une nouvelle base de données pour un fichier de destination.</span><span class="sxs-lookup"><span data-stu-id="940e4-103">Use the **Create Database** page to define a new database for a destination file.</span></span>  
  
 <span data-ttu-id="940e4-104">Cette page offre un sous-ensemble des options disponibles pour la création d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="940e4-104">This page offers a subset of the available options for creating a new database.</span></span> <span data-ttu-id="940e4-105">Pour afficher toutes les options, utilisez [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="940e4-105">To view all the options, use [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="940e4-106">Pour en savoir plus sur cet Assistant, consultez [Assistant Importation et Exportation SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="940e4-106">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="940e4-107">Pour en savoir plus sur les options de démarrage de l’Assistant et sur les autorisations requises pour exécuter correctement l’Assistant, consultez [exécuter l’Assistant importation et exportation SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="940e4-107">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="940e4-108">La fonction de l'Assistant Importation et Exportation SQL Server est de copier des données d'une source vers une destination.</span><span class="sxs-lookup"><span data-stu-id="940e4-108">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="940e4-109">L'Assistant peut également créer une base de données de destination et des tables de destination à votre intention.</span><span class="sxs-lookup"><span data-stu-id="940e4-109">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="940e4-110">Toutefois, si vous devez copier plusieurs tables ou bases de données, ou autres types d'objets de bases de données, vous devez plutôt utiliser l'Assistant Copie de base de données.</span><span class="sxs-lookup"><span data-stu-id="940e4-110">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="940e4-111">Pour plus d'informations, consultez [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="940e4-111">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="940e4-112">Options</span><span class="sxs-lookup"><span data-stu-id="940e4-112">Options</span></span>  
 <span data-ttu-id="940e4-113">**Nom**</span><span class="sxs-lookup"><span data-stu-id="940e4-113">**Name**</span></span>  
 <span data-ttu-id="940e4-114">Fournissez un nom unique pour la base de données SQL Server de destination.</span><span class="sxs-lookup"><span data-stu-id="940e4-114">Provide a unique name for the destination SQL Server database.</span></span> <span data-ttu-id="940e4-115">Veillez à respecter les conventions SQL Server lorsque vous nommez la base de données.</span><span class="sxs-lookup"><span data-stu-id="940e4-115">Make sure that you follow SQL Server conventions when you name this database.</span></span>  
  
 <span data-ttu-id="940e4-116">**Nom du fichier de données**</span><span class="sxs-lookup"><span data-stu-id="940e4-116">**Data file name**</span></span>  
 <span data-ttu-id="940e4-117">Affiche le nom du fichier de données.</span><span class="sxs-lookup"><span data-stu-id="940e4-117">View the name of the data file.</span></span> <span data-ttu-id="940e4-118">Il est issu du nom de la base de données que vous avez fourni précédemment.</span><span class="sxs-lookup"><span data-stu-id="940e4-118">This is derived from the database name you provided earlier.</span></span>  
  
 <span data-ttu-id="940e4-119">**Nom du fichier journal**</span><span class="sxs-lookup"><span data-stu-id="940e4-119">**Log file name**</span></span>  
 <span data-ttu-id="940e4-120">Affiche le nom du fichier journal.</span><span class="sxs-lookup"><span data-stu-id="940e4-120">View the name of the log file.</span></span> <span data-ttu-id="940e4-121">Il est issu du nom de la base de données que vous avez fourni précédemment.</span><span class="sxs-lookup"><span data-stu-id="940e4-121">This is derived from the database name you provided earlier.</span></span>  
  
 <span data-ttu-id="940e4-122">**Taille initiale (fichier de données)**</span><span class="sxs-lookup"><span data-stu-id="940e4-122">**Initial size (data file)**</span></span>  
 <span data-ttu-id="940e4-123">Définissez le nombre de mégaoctets de la taille initiale du fichier de données.</span><span class="sxs-lookup"><span data-stu-id="940e4-123">Specify the number of megabytes for the initial size of the data file.</span></span>  
  
 <span data-ttu-id="940e4-124">**Aucune croissance autorisée (fichier de données)**</span><span class="sxs-lookup"><span data-stu-id="940e4-124">**No growth allowed (data file)**</span></span>  
 <span data-ttu-id="940e4-125">Indiquez si la taille du fichier de données peut augmenter au-delà de la taille initiale spécifiée.</span><span class="sxs-lookup"><span data-stu-id="940e4-125">Indicate whether the data file can grow beyond the specified initial size.</span></span>  
  
 <span data-ttu-id="940e4-126">**Augmenter de (fichier de données)**</span><span class="sxs-lookup"><span data-stu-id="940e4-126">**Grow by percentage (data file)**</span></span>  
 <span data-ttu-id="940e4-127">Définissez le pourcentage d'augmentation de la taille du fichier de données.</span><span class="sxs-lookup"><span data-stu-id="940e4-127">Specify a percentage by which the data file can grow.</span></span>  
  
 <span data-ttu-id="940e4-128">**Augmenter de (taille) (fichier de données)**</span><span class="sxs-lookup"><span data-stu-id="940e4-128">**Grow by size (data file)**</span></span>  
 <span data-ttu-id="940e4-129">Définissez le nombre d'octets d'augmentation de la taille du fichier de données.</span><span class="sxs-lookup"><span data-stu-id="940e4-129">Specify a number of megabytes by which the data file can grow.</span></span>  
  
 <span data-ttu-id="940e4-130">**Taille initiale (fichier journal)**</span><span class="sxs-lookup"><span data-stu-id="940e4-130">**Initial size (log file)**</span></span>  
 <span data-ttu-id="940e4-131">Définissez le nombre de mégaoctets de la taille initiale du fichier journal.</span><span class="sxs-lookup"><span data-stu-id="940e4-131">Specify the number of megabytes for the initial size of the log file.</span></span>  
  
 <span data-ttu-id="940e4-132">**Aucune croissance autorisée (fichier journal)**</span><span class="sxs-lookup"><span data-stu-id="940e4-132">**No growth allowed (log file)**</span></span>  
 <span data-ttu-id="940e4-133">Indiquez si la taille du fichier journal peut augmenter au-delà de la taille initiale spécifiée.</span><span class="sxs-lookup"><span data-stu-id="940e4-133">Indicate whether the log file can grow beyond the specified initial size.</span></span>  
  
 <span data-ttu-id="940e4-134">**Augmenter de (pourcentage) (fichier journal)**</span><span class="sxs-lookup"><span data-stu-id="940e4-134">**Grow by percentage (log file)**</span></span>  
 <span data-ttu-id="940e4-135">Définissez le pourcentage d'augmentation du fichier journal.</span><span class="sxs-lookup"><span data-stu-id="940e4-135">Specify a percentage by which the log file can grow.</span></span>  
  
 <span data-ttu-id="940e4-136">**Augmenter de (taille) (fichier journal)**</span><span class="sxs-lookup"><span data-stu-id="940e4-136">**Grow by size (log file)**</span></span>  
 <span data-ttu-id="940e4-137">Définissez le nombre d'octets d'augmentation de la taille du fichier journal.</span><span class="sxs-lookup"><span data-stu-id="940e4-137">Specify a number of megabytes by which the log file can grow.</span></span>  
  
  
