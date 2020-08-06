---
title: MSSQLSERVER_2527 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2527 (Database Engine error)
ms.assetid: 1cef90ef-9c39-44e6-bc7f-316c8f53c10c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 900707634a016ecfd29f9f676e68b4d2f557ccea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603535"
---
# <a name="mssqlserver_2527"></a><span data-ttu-id="ebef5-102">MSSQLSERVER_2527</span><span class="sxs-lookup"><span data-stu-id="ebef5-102">MSSQLSERVER_2527</span></span>
    
## <a name="details"></a><span data-ttu-id="ebef5-103">Détails</span><span class="sxs-lookup"><span data-stu-id="ebef5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ebef5-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="ebef5-104">Product Name</span></span>|<span data-ttu-id="ebef5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ebef5-105">SQL Server</span></span>|  
|<span data-ttu-id="ebef5-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="ebef5-106">Event ID</span></span>|<span data-ttu-id="ebef5-107">2527</span><span class="sxs-lookup"><span data-stu-id="ebef5-107">2527</span></span>|  
|<span data-ttu-id="ebef5-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="ebef5-108">Event Source</span></span>|<span data-ttu-id="ebef5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ebef5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ebef5-110">Composant</span><span class="sxs-lookup"><span data-stu-id="ebef5-110">Component</span></span>|<span data-ttu-id="ebef5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ebef5-111">SQLEngine</span></span>|  
|<span data-ttu-id="ebef5-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="ebef5-112">Symbolic Name</span></span>|<span data-ttu-id="ebef5-113">DBCC_INDEX_FILEGROUP_IS_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="ebef5-113">DBCC_INDEX_FILEGROUP_IS_OFFLINE</span></span>|  
|<span data-ttu-id="ebef5-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="ebef5-114">Message Text</span></span>|<span data-ttu-id="ebef5-115">Impossible de traiter l'index I_NAME de la table O_NAME car le groupe de fichiers F_NAME est hors connexion.</span><span class="sxs-lookup"><span data-stu-id="ebef5-115">Unable to process index I_NAME of table O_NAME because filegroup F_NAME is offline.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ebef5-116">Explication</span><span class="sxs-lookup"><span data-stu-id="ebef5-116">Explanation</span></span>  
 <span data-ttu-id="ebef5-117">Ce message d'information indique qu'il est impossible de vérifier l'index, car l'un des groupes de fichiers qui stocke les données de l'index n'est pas connecté.</span><span class="sxs-lookup"><span data-stu-id="ebef5-117">This informational message indicates that the index cannot be checked because one of the filegroups that stores data for the index is offline.</span></span> <span data-ttu-id="ebef5-118">L'état des fichiers dans un groupe de fichiers détermine la disponibilité du groupe de fichiers tout entier.</span><span class="sxs-lookup"><span data-stu-id="ebef5-118">The state of the files in a filegroup determines the availability of the whole filegroup.</span></span> <span data-ttu-id="ebef5-119">Pour qu'un groupe de fichiers soit disponible, tous ses fichiers doivent être en ligne.</span><span class="sxs-lookup"><span data-stu-id="ebef5-119">For a filegroup to be available, all files within the filegroup must be online.</span></span> <span data-ttu-id="ebef5-120">S’il n’y a pas d’autre problème, tous les autres index du même objet seront vérifiés.</span><span class="sxs-lookup"><span data-stu-id="ebef5-120">If there are no other problems, all other indexes of the same object will be checked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ebef5-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="ebef5-121">User Action</span></span>  
 <span data-ttu-id="ebef5-122">Pour afficher l’état des fichiers du groupe de fichiers spécifié, interrogez l’affichage catalogue **sys.database_files** ou **sys.master_files**.</span><span class="sxs-lookup"><span data-stu-id="ebef5-122">To view the state of the files for the specified filegroup, query either the **sys.database_files** or **sys.master_files** catalog view.</span></span>  
  
 <span data-ttu-id="ebef5-123">Restaurez le fichier hors connexion à partir d'une sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ebef5-123">Restore the offline file from a backup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebef5-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ebef5-124">See Also</span></span>  
 <span data-ttu-id="ebef5-125">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ebef5-125">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 <span data-ttu-id="ebef5-126">[sys. master_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ebef5-126">[sys.master_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) </span></span>  
 [<span data-ttu-id="ebef5-127">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ebef5-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
