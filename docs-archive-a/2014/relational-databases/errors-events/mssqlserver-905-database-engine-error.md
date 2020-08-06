---
title: MSSQLSERVER_905 | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 905 (Database Engine error)
ms.assetid: c828bb2e-e554-4f81-b76c-2b3740d2b944
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7dd3c8c5a287e2d123e2a9d1430ecd49b27f29f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604491"
---
# <a name="mssqlserver_905"></a><span data-ttu-id="5f79b-102">MSSQLSERVER_905</span><span class="sxs-lookup"><span data-stu-id="5f79b-102">MSSQLSERVER_905</span></span>
    
## <a name="details"></a><span data-ttu-id="5f79b-103">Détails</span><span class="sxs-lookup"><span data-stu-id="5f79b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5f79b-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="5f79b-104">Product Name</span></span>|<span data-ttu-id="5f79b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5f79b-105">SQL Server</span></span>|  
|<span data-ttu-id="5f79b-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="5f79b-106">Event ID</span></span>|<span data-ttu-id="5f79b-107">905</span><span class="sxs-lookup"><span data-stu-id="5f79b-107">905</span></span>|  
|<span data-ttu-id="5f79b-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="5f79b-108">Event Source</span></span>|<span data-ttu-id="5f79b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5f79b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5f79b-110">Composant</span><span class="sxs-lookup"><span data-stu-id="5f79b-110">Component</span></span>|<span data-ttu-id="5f79b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5f79b-111">SQLEngine</span></span>|  
|<span data-ttu-id="5f79b-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="5f79b-112">Symbolic Name</span></span>|<span data-ttu-id="5f79b-113">DBSTARTUP_EE_PARTITIONING</span><span class="sxs-lookup"><span data-stu-id="5f79b-113">DBSTARTUP_EE_PARTITIONING</span></span>|  
|<span data-ttu-id="5f79b-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="5f79b-114">Message Text</span></span>|<span data-ttu-id="5f79b-115">La base de données '%.\*ls' ne peut pas être démarrée dans cette édition de SQL Server, car elle contient une fonction de partition '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="5f79b-115">Database '%.\*ls' cannot be started in this edition of SQL Server because it contains a partition function '%.\*ls'.</span></span> <span data-ttu-id="5f79b-116">Seule l'édition Entreprise de SQL Server prend en charge le partitionnement.</span><span class="sxs-lookup"><span data-stu-id="5f79b-116">Only Enterprise edition of SQL Server supports partitioning.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5f79b-117">Explication</span><span class="sxs-lookup"><span data-stu-id="5f79b-117">Explanation</span></span>  
 <span data-ttu-id="5f79b-118">La base de données contient un ou plusieurs index ou tables partitionnés.</span><span class="sxs-lookup"><span data-stu-id="5f79b-118">The database contains one or more partitioned tables or indexes.</span></span> <span data-ttu-id="5f79b-119">Cette édition de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne peut pas utiliser le partitionnement.</span><span class="sxs-lookup"><span data-stu-id="5f79b-119">This edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot use partitioning.</span></span> <span data-ttu-id="5f79b-120">Par conséquent, la base de données ne peut pas être démarrée correctement.</span><span class="sxs-lookup"><span data-stu-id="5f79b-120">Therefore, the database cannot be started correctly.</span></span> <span data-ttu-id="5f79b-121">Les tables et les index partitionnés ne sont pas disponibles dans toutes les éditions de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f79b-121">Partitioned tables and indexes are not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5f79b-122">Pour obtenir une liste des fonctionnalités prises en charge par les éditions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="5f79b-122">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5f79b-123">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="5f79b-123">User Action</span></span>  
 <span data-ttu-id="5f79b-124">Détachez la base de données à l'aide de la procédure stockée sp_detach_db.</span><span class="sxs-lookup"><span data-stu-id="5f79b-124">Detach the database by using the sp_detach_db stored procedure.</span></span> <span data-ttu-id="5f79b-125">Déplacez les fichiers, si nécessaire, puis attachez la base de données à une instance d’une édition de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prise en charge en utilisant CREATE DATABASE avec l’option FOR ATTACH ou FOR ATTACH_REBUILD_LOG.</span><span class="sxs-lookup"><span data-stu-id="5f79b-125">Move the files if it is needed, and then attach the database to an instance of a supported [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] edition by using the CREATE DATABASE with the FOR ATTACH or FOR ATTACH_REBUILD_LOG option.</span></span> <span data-ttu-id="5f79b-126">Désactivez le partitionnement sur toutes les tables et supprimez les fonctions de partitionnement.</span><span class="sxs-lookup"><span data-stu-id="5f79b-126">Disable partitioning on all tables and remove the partitioning functions.</span></span> <span data-ttu-id="5f79b-127">Détachez encore la base de données et rattachez-la au serveur actif.</span><span class="sxs-lookup"><span data-stu-id="5f79b-127">Detach the database again, and reattach the database to the current server.</span></span>  
  
  
