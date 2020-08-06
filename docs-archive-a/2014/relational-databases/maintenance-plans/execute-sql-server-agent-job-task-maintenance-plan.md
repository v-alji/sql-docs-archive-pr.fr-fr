---
title: Tâche Exécuter le travail de SQL Server Agent (Plan de maintenance) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.executejob.f1
helpviewer_keywords:
- Execute SQL Server Agent Job Task dialog box
ms.assetid: 4ed75956-ebb8-4d8c-9c16-fc0eb00bd3a0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b997d5144b113102ba0ed2d9d1df59b6707acbee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612309"
---
# <a name="execute-sql-server-agent-job-task-maintenance-plan"></a><span data-ttu-id="fdc5a-102">Tâche Exécuter le travail de SQL Server Agent (Plan de maintenance)</span><span class="sxs-lookup"><span data-stu-id="fdc5a-102">Execute SQL Server Agent Job Task (Maintenance Plan)</span></span>
  <span data-ttu-id="fdc5a-103">La boîte de dialogue **Tâche Exécuter le travail de l'Agent SQL Server** vous permet d'exécuter les travaux de l'Agent Microsoft SQL Server dans le cadre d'un plan de maintenance.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-103">Use the **Execute SQL Server Agent Job Task** dialog to execute Microsoft SQL Server Agent jobs within a maintenance plan.</span></span> <span data-ttu-id="fdc5a-104">Cette option n'est pas disponible si vous ne possédez pas de travaux de l'Agent SQL Server sur la connexion sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-104">This option will not be available if you have no SQL Server Agent jobs on the selected connection.</span></span>  
  
 <span data-ttu-id="fdc5a-105">Cette tâche utilise l’instruction **.sp_start_job** .</span><span class="sxs-lookup"><span data-stu-id="fdc5a-105">This task uses the **.sp_start_job** statement.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="fdc5a-106">Liste d’éléments UI</span><span class="sxs-lookup"><span data-stu-id="fdc5a-106">UI element list</span></span>  
 <span data-ttu-id="fdc5a-107">**Connection**</span><span class="sxs-lookup"><span data-stu-id="fdc5a-107">**Connection**</span></span>  
 <span data-ttu-id="fdc5a-108">Sélectionnez la connexion serveur à utiliser pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-108">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="fdc5a-109">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="fdc5a-109">**New**</span></span>  
 <span data-ttu-id="fdc5a-110">Crée une nouvelle connexion serveur à utiliser pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-110">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="fdc5a-111">La boîte de dialogue **Nouvelle connexion** est décrite ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-111">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="fdc5a-112">**Travaux d'Agent SQL disponibles**</span><span class="sxs-lookup"><span data-stu-id="fdc5a-112">**Available SQL Agent jobs**</span></span>  
 <span data-ttu-id="fdc5a-113">Permet de sélectionner le travail à exécuter.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-113">Select the job to execute.</span></span> <span data-ttu-id="fdc5a-114">La grille fournit le **Nom du travail** et la **Description** permettant d'identifier les travaux.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-114">The grid provides the **Job name** and **Description** to identify the jobs.</span></span>  
  
 <span data-ttu-id="fdc5a-115">**Vue T-SQL**</span><span class="sxs-lookup"><span data-stu-id="fdc5a-115">**View T-SQL**</span></span>  
 <span data-ttu-id="fdc5a-116">Affiche les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] exécutées sur le serveur pour cette tâche, selon les options sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-116">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fdc5a-117">Si le nombre d'objets impliqués est élevé, l'affichage des instructions peut prendre un temps considérable.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-117">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="fdc5a-118">Boîte de dialogue Nouvelle connexion</span><span class="sxs-lookup"><span data-stu-id="fdc5a-118">New Connection Dialog Box</span></span>  
 <span data-ttu-id="fdc5a-119">**Nom de connexion**</span><span class="sxs-lookup"><span data-stu-id="fdc5a-119">**Connection name**</span></span>  
 <span data-ttu-id="fdc5a-120">Entrez un nom pour la nouvelle connexion.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-120">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="fdc5a-121">**Sélectionnez ou entrez un nom de serveur.**</span><span class="sxs-lookup"><span data-stu-id="fdc5a-121">**Select or enter a server name**</span></span>  
 <span data-ttu-id="fdc5a-122">Sélectionnez un serveur auquel établir la connexion pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-122">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="fdc5a-123">**Actualiser**</span><span class="sxs-lookup"><span data-stu-id="fdc5a-123">**Refresh**</span></span>  
 <span data-ttu-id="fdc5a-124">Actualise la liste des serveurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-124">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="fdc5a-125">**Entrez des informations pour vous connecter au serveur**</span><span class="sxs-lookup"><span data-stu-id="fdc5a-125">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="fdc5a-126">Spécifiez le mode d'authentification sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-126">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="fdc5a-127">**Utiliser la sécurité intégrée à Windows NT**</span><span class="sxs-lookup"><span data-stu-id="fdc5a-127">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="fdc5a-128">Permet de se connecter à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec l’authentification Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-128">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Microsoft Windows Authentication.</span></span>  
  
 <span data-ttu-id="fdc5a-129">**Utiliser un nom d'utilisateur et un mot de passe spécifiques**</span><span class="sxs-lookup"><span data-stu-id="fdc5a-129">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="fdc5a-130">Permet de se connecter à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en utilisant l’authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fdc5a-130">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="fdc5a-131">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-131">This option is not available.</span></span>  
  
 <span data-ttu-id="fdc5a-132">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="fdc5a-132">**User name**</span></span>  
 <span data-ttu-id="fdc5a-133">Fournit le nom d'utilisateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à utiliser pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-133">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="fdc5a-134">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-134">This option is not available.</span></span>  
  
 <span data-ttu-id="fdc5a-135">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="fdc5a-135">**Password**</span></span>  
 <span data-ttu-id="fdc5a-136">Fournit un mot de passe à utiliser pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-136">Provide a password to use when authenticating.</span></span> <span data-ttu-id="fdc5a-137">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="fdc5a-137">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdc5a-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fdc5a-138">See Also</span></span>  
 <span data-ttu-id="fdc5a-139">[sp_add_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fdc5a-139">[sp_add_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql) </span></span>  
 <span data-ttu-id="fdc5a-140">[Créer un travail](../../ssms/agent/create-a-job.md) </span><span class="sxs-lookup"><span data-stu-id="fdc5a-140">[Create a Job](../../ssms/agent/create-a-job.md) </span></span>  
 [<span data-ttu-id="fdc5a-141">sp_start_job &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fdc5a-141">sp_start_job &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql)  
  
  
