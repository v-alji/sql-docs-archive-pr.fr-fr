---
title: Définir et récupérer les informations de version | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- historical information [SQL Server]
- source controls [SQL Server Management Studio], version information
- retrieving version information
- current file version information
- version control services [SQL Server], retrieving version information
- version control services [SQL Server], setting version information
- status information [SQL Server], source control files
- historical information [SQL Server], source control files
ms.assetid: c3f253c4-4e3d-48e8-8d90-bd6ee899faf7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: eff3d40ba9b663ba8611508c5b9f0c9961005b81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696027"
---
# <a name="set-and-retrieve-version-information"></a><span data-ttu-id="33d1c-102">Définir et récupérer des informations sur la version</span><span class="sxs-lookup"><span data-stu-id="33d1c-102">Set and Retrieve Version Information</span></span>
  <span data-ttu-id="33d1c-103">Les informations sur une version comprennent l'historique et l'état en cours d'un fichier sous contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="33d1c-103">Version information includes the history and current status of a source-controlled file.</span></span> <span data-ttu-id="33d1c-104">[!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe gère un historique complet pour chaque fichier sous contrôle de code source, de sorte que vous puissiez suivre l'évolution d'un ou de plusieurs fichiers dans le temps.</span><span class="sxs-lookup"><span data-stu-id="33d1c-104">For every source-controlled file, [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe maintains a comprehensive history, so you can track the evolution of one or more files over time.</span></span> <span data-ttu-id="33d1c-105">Vous pouvez également utiliser ces informations pour récupérer une copie locale d'une version d'un fichier ou pour comparer deux versions d'un fichier.</span><span class="sxs-lookup"><span data-stu-id="33d1c-105">You can also use this information to retrieve a local copy of any version of the file or to compare any two file versions.</span></span>  
  
 <span data-ttu-id="33d1c-106">L'historique d'un fichier comprend les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="33d1c-106">The history of a file includes:</span></span>  
  
-   <span data-ttu-id="33d1c-107">Numéro de version, indiquant la séquence de la version parmi les autres versions du même fichier</span><span class="sxs-lookup"><span data-stu-id="33d1c-107">The version number, which identifies its sequence among other versions of the same file.</span></span>  
  
-   <span data-ttu-id="33d1c-108">action effectuée.</span><span class="sxs-lookup"><span data-stu-id="33d1c-108">The action performed.</span></span> <span data-ttu-id="33d1c-109">Parmi les opérations de suivi figurent la création, l'archivage et la suppression de fichiers.</span><span class="sxs-lookup"><span data-stu-id="33d1c-109">Tracked operations include file creation, check in, and deletion.</span></span>  
  
-   <span data-ttu-id="33d1c-110">Nom d'utilisateur de la personne à l'origine de l'action impliquant le fichier</span><span class="sxs-lookup"><span data-stu-id="33d1c-110">The user name of the person who performed an action involving the file.</span></span>  
  
-   <span data-ttu-id="33d1c-111">Date et heure d'exécution de l'opération</span><span class="sxs-lookup"><span data-stu-id="33d1c-111">The date and time when the operation was performed.</span></span>  
  
 <span data-ttu-id="33d1c-112">Visual SourceSafe gère également les informations relatives à l'état en cours de la solution actuellement chargée.</span><span class="sxs-lookup"><span data-stu-id="33d1c-112">Visual SourceSafe also maintains current status information on the currently loaded solution.</span></span> <span data-ttu-id="33d1c-113">Ces informations fournissent un instantané de l'état actuel du fichier :</span><span class="sxs-lookup"><span data-stu-id="33d1c-113">This information provides a snapshot of the current state of the file, including:</span></span>  
  
-   <span data-ttu-id="33d1c-114">Identité de l'utilisateur ayant extrait le fichier</span><span class="sxs-lookup"><span data-stu-id="33d1c-114">The identity of the user who has the file checked out.</span></span>  
  
-   <span data-ttu-id="33d1c-115">Dernier numéro de la version du fichier sélectionné</span><span class="sxs-lookup"><span data-stu-id="33d1c-115">The latest version number of the selected file.</span></span>  
  
-   <span data-ttu-id="33d1c-116">Date de création de la version</span><span class="sxs-lookup"><span data-stu-id="33d1c-116">The date when the version was created.</span></span>  
  
-   <span data-ttu-id="33d1c-117">Commentaire de l'utilisateur associé à la version</span><span class="sxs-lookup"><span data-stu-id="33d1c-117">The user comment associated with the version.</span></span>  
  
-   <span data-ttu-id="33d1c-118">Chemins vers les projets avec lesquels le fichier est partagé</span><span class="sxs-lookup"><span data-stu-id="33d1c-118">The paths to the projects with which the file is shared.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="33d1c-119">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="33d1c-119">In This Section</span></span>  
  
-   [<span data-ttu-id="33d1c-120">Afficher l'historique d'un fichier</span><span class="sxs-lookup"><span data-stu-id="33d1c-120">View File History</span></span>](../../2014/database-engine/view-file-history.md)  
  
-   [<span data-ttu-id="33d1c-121">Afficher l'historique d'un projet</span><span class="sxs-lookup"><span data-stu-id="33d1c-121">View Project History</span></span>](../../2014/database-engine/view-project-history.md)  
  
-   [<span data-ttu-id="33d1c-122">Afficher l'état d'un fichier</span><span class="sxs-lookup"><span data-stu-id="33d1c-122">View File Status</span></span>](../../2014/database-engine/view-file-status.md)  
  
-   [<span data-ttu-id="33d1c-123">Récupérer des fichiers</span><span class="sxs-lookup"><span data-stu-id="33d1c-123">Retrieve Files</span></span>](../../2014/database-engine/retrieve-files.md)  
  
-   [<span data-ttu-id="33d1c-124">Désigner une version comme étant la dernière version</span><span class="sxs-lookup"><span data-stu-id="33d1c-124">Specify a Version as the Latest Version</span></span>](../../2014/database-engine/specify-a-version-as-the-latest-version.md)  
  
-   [<span data-ttu-id="33d1c-125">Comparer des fichiers</span><span class="sxs-lookup"><span data-stu-id="33d1c-125">Compare Files</span></span>](../../2014/database-engine/compare-files.md)  
  
-   [<span data-ttu-id="33d1c-126">Partager des fichiers</span><span class="sxs-lookup"><span data-stu-id="33d1c-126">Share Files</span></span>](../../2014/database-engine/share-files.md)  
  
-   [<span data-ttu-id="33d1c-127">Créer des rapports d'état et historiques</span><span class="sxs-lookup"><span data-stu-id="33d1c-127">Create History and Status Reports</span></span>](../../2014/database-engine/create-history-and-status-reports.md)  
  
## <a name="see-also"></a><span data-ttu-id="33d1c-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="33d1c-128">See Also</span></span>  
 [<span data-ttu-id="33d1c-129">Présentation du contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="33d1c-129">Source Control Basics</span></span>](../../2014/database-engine/source-control-basics.md)  
  
  
