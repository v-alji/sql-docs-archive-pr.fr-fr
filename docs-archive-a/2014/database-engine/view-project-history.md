---
title: Afficher l’historique du projet | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- viewing project history
- version control services [SQL Server], project history
- projects [SQL Server Management Studio], historical information
- historical information [SQL Server], projects
ms.assetid: be0ea2ac-4a35-429c-9c9e-4001ea9035a4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 85028141050e19e6ed6394a5bb17709ac8f906ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614188"
---
# <a name="view-project-history"></a><span data-ttu-id="7f050-102">Afficher l'historique d'un projet</span><span class="sxs-lookup"><span data-stu-id="7f050-102">View Project History</span></span>
  <span data-ttu-id="7f050-103">L'historique d'un projet [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe (VSS) comporte la liste de toutes les actions effectuées sur chacun des fichiers du projet en question (création, ajout, suppression, récupération de fichiers…).</span><span class="sxs-lookup"><span data-stu-id="7f050-103">The history of a [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe (VSS) project includes a list of all the actions taken on each of the project files, including file creation, addition, deletion, and recovery.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7f050-104">Un projet Visual SourceSafe est plus souvent appelé dossier de serveur de contrôle de code source, emplacement dans lequel la version de serveur d'un fichier sous contrôle de code source est stockée sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="7f050-104">A Visual SourceSafe project is more commonly referred to as the source control server folder, the location where the server version of a source-controlled file is stored on the server.</span></span>  
  
 <span data-ttu-id="7f050-105">Vous pouvez utiliser [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pour examiner l'historique d'un projet Visual SourceSafe dont fait partie la solution actuellement chargée.</span><span class="sxs-lookup"><span data-stu-id="7f050-105">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to examine the history of the Visual SourceSafe project to which the currently loaded solution belongs.</span></span> <span data-ttu-id="7f050-106">En fonction des informations figurant dans l'historique d'un projet, vous pouvez récupérer des copies locales des versions d'un fichier, restaurer des versions supprimées ou partager la version d'un fichier avec d'autres projets.</span><span class="sxs-lookup"><span data-stu-id="7f050-106">Based on the information displayed as part of the history of a project, you can retrieve local copies of file versions, restore deleted versions, or share a file version between projects.</span></span>  
  
### <a name="to-view-the-history-of-a-vss-project"></a><span data-ttu-id="7f050-107">Pour afficher l'historique d'un projet VSS</span><span class="sxs-lookup"><span data-stu-id="7f050-107">To view the history of a VSS project</span></span>  
  
1.  <span data-ttu-id="7f050-108">Dans l’Explorateur de solutions, sélectionnez le projet.</span><span class="sxs-lookup"><span data-stu-id="7f050-108">In Solution Explorer, select the project.</span></span>  
  
2.  <span data-ttu-id="7f050-109">Dans le menu **fichier** , pointez sur **contrôle de code source** , puis cliquez sur **afficher l’historique**.</span><span class="sxs-lookup"><span data-stu-id="7f050-109">On the **File** menu, point to **Source Control** and click **View History**.</span></span>  
  
3.  <span data-ttu-id="7f050-110">Dans la boîte **de dialogue historique de** \<Project> , effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="7f050-110">In the **History of** \<Project> dialog box, perform any of the following actions:</span></span>  
  
    -   <span data-ttu-id="7f050-111">Afficher la copie d'un fichier sélectionné dans le système de contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="7f050-111">View the source control system's copy of a selected file.</span></span>  
  
    -   <span data-ttu-id="7f050-112">Afficher des informations détaillées sur un fichier sélectionné</span><span class="sxs-lookup"><span data-stu-id="7f050-112">View detailed information about a selected file.</span></span>  
  
    -   <span data-ttu-id="7f050-113">Récupérer un fichier sélectionné sur votre disque local</span><span class="sxs-lookup"><span data-stu-id="7f050-113">Retrieve a selected file to your local disk.</span></span>  
  
    -   <span data-ttu-id="7f050-114">Extraire un fichier sélectionné</span><span class="sxs-lookup"><span data-stu-id="7f050-114">Check out a selected file.</span></span>  
  
    -   <span data-ttu-id="7f050-115">Partager un fichier sélectionné avec deux projets de contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="7f050-115">Share a selected file between two source control projects.</span></span>  
  
    -   <span data-ttu-id="7f050-116">Envoyer le rapport de l'historique vers une imprimante, un fichier ou le Presse-Papiers</span><span class="sxs-lookup"><span data-stu-id="7f050-116">Export the history report to a printer, a file, or the Clipboard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f050-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7f050-117">See Also</span></span>  
 <span data-ttu-id="7f050-118">[Définir et récupérer les informations de version](../../2014/database-engine/set-and-retrieve-version-information.md) </span><span class="sxs-lookup"><span data-stu-id="7f050-118">[Set and Retrieve Version Information](../../2014/database-engine/set-and-retrieve-version-information.md) </span></span>  
 <span data-ttu-id="7f050-119">[Afficher l’état du fichier](../../2014/database-engine/view-file-status.md) </span><span class="sxs-lookup"><span data-stu-id="7f050-119">[View File Status](../../2014/database-engine/view-file-status.md) </span></span>  
 <span data-ttu-id="7f050-120">[Récupérer les fichiers](../../2014/database-engine/retrieve-files.md) </span><span class="sxs-lookup"><span data-stu-id="7f050-120">[Retrieve Files](../../2014/database-engine/retrieve-files.md) </span></span>  
 [<span data-ttu-id="7f050-121">Comparer des fichiers</span><span class="sxs-lookup"><span data-stu-id="7f050-121">Compare Files</span></span>](../../2014/database-engine/compare-files.md)  
  
  
