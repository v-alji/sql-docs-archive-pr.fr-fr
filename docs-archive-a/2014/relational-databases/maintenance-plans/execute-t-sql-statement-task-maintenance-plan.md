---
title: Exécuter la tâche de l’instruction T-SQL (Plan de maintenance) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.tsql.f1
helpviewer_keywords:
- Execute T-SQL Statement Task dialog box
ms.assetid: fef3e259-0c47-4f6e-ade0-aee95e3d6c1a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 63738758ce228a51ab6c75eb11a681eec3b27352
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612310"
---
# <a name="execute-t-sql-statement-task-maintenance-plan"></a><span data-ttu-id="7f63f-102">Exécuter la tâche de l’instruction T-SQL (Plan de maintenance)</span><span class="sxs-lookup"><span data-stu-id="7f63f-102">Execute T-SQL Statement Task (Maintenance Plan)</span></span>
  <span data-ttu-id="7f63f-103">Utilisez la boîte de dialogue **Exécuter la tâche de l’instruction T-SQL** pour personnaliser le plan de maintenance en y ajoutant les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] de votre choix.</span><span class="sxs-lookup"><span data-stu-id="7f63f-103">Use the **Execute T-SQL Statement Task** dialog to customize your maintenance plan by adding [!INCLUDE[tsql](../../includes/tsql-md.md)] statements of your choice to this maintenance plan.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7f63f-104">Options</span><span class="sxs-lookup"><span data-stu-id="7f63f-104">Options</span></span>  
 <span data-ttu-id="7f63f-105">**Connection**</span><span class="sxs-lookup"><span data-stu-id="7f63f-105">**Connection**</span></span>  
 <span data-ttu-id="7f63f-106">Sélectionnez la connexion serveur à utiliser pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="7f63f-106">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="7f63f-107">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="7f63f-107">**New**</span></span>  
 <span data-ttu-id="7f63f-108">Crée une nouvelle connexion serveur à utiliser pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="7f63f-108">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="7f63f-109">La boîte de dialogue **Nouvelle connexion** est décrite ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="7f63f-109">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="7f63f-110">**Expiration du délai d'exécution**</span><span class="sxs-lookup"><span data-stu-id="7f63f-110">**Execution time out**</span></span>  
 <span data-ttu-id="7f63f-111">Temps d'attente (en secondes) avant l'expiration du délai pour l'exécution de la tâche (arrêt de la tâche).</span><span class="sxs-lookup"><span data-stu-id="7f63f-111">Time (seconds) to wait for task completion before timing out (terminating task).</span></span>  
  
 <span data-ttu-id="7f63f-112">**Instruction T-SQL**</span><span class="sxs-lookup"><span data-stu-id="7f63f-112">**T-SQL statement**</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="7f63f-113">Instructions à exécuter.</span><span class="sxs-lookup"><span data-stu-id="7f63f-113">statements to execute.</span></span>  
  
 <span data-ttu-id="7f63f-114">**Vue T-SQL**</span><span class="sxs-lookup"><span data-stu-id="7f63f-114">**View T-SQL**</span></span>  
 <span data-ttu-id="7f63f-115">Affiche les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] exécutées sur le serveur pour cette tâche, selon les options sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="7f63f-115">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7f63f-116">Si le nombre d'objets impliqués est élevé, l'affichage des instructions peut prendre un temps considérable.</span><span class="sxs-lookup"><span data-stu-id="7f63f-116">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="7f63f-117">Boîte de dialogue Nouvelle connexion</span><span class="sxs-lookup"><span data-stu-id="7f63f-117">New Connection Dialog Box</span></span>  
 <span data-ttu-id="7f63f-118">**Nom de connexion**</span><span class="sxs-lookup"><span data-stu-id="7f63f-118">**Connection name**</span></span>  
 <span data-ttu-id="7f63f-119">Entrez un nom pour la nouvelle connexion.</span><span class="sxs-lookup"><span data-stu-id="7f63f-119">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="7f63f-120">**Sélectionnez ou entrez un nom de serveur.**</span><span class="sxs-lookup"><span data-stu-id="7f63f-120">**Select or enter a server name**</span></span>  
 <span data-ttu-id="7f63f-121">Sélectionnez un serveur auquel établir la connexion pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="7f63f-121">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="7f63f-122">**Actualiser**</span><span class="sxs-lookup"><span data-stu-id="7f63f-122">**Refresh**</span></span>  
 <span data-ttu-id="7f63f-123">Actualise la liste des serveurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="7f63f-123">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="7f63f-124">**Entrez des informations pour vous connecter au serveur**</span><span class="sxs-lookup"><span data-stu-id="7f63f-124">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="7f63f-125">Spécifiez le mode d'authentification sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="7f63f-125">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="7f63f-126">**Utiliser la sécurité intégrée à Windows NT**</span><span class="sxs-lookup"><span data-stu-id="7f63f-126">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="7f63f-127">Permet de se connecter à une instance du [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] avec l’authentification [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="7f63f-127">Connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="7f63f-128">**Utiliser un nom d'utilisateur et un mot de passe spécifiques**</span><span class="sxs-lookup"><span data-stu-id="7f63f-128">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="7f63f-129">Se connecte à une instance de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] à l'aide de l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7f63f-129">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="7f63f-130">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="7f63f-130">This option is not available.</span></span>  
  
 <span data-ttu-id="7f63f-131">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="7f63f-131">**User name**</span></span>  
 <span data-ttu-id="7f63f-132">Fournit le nom d'utilisateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à utiliser pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="7f63f-132">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="7f63f-133">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="7f63f-133">This option is not available.</span></span>  
  
 <span data-ttu-id="7f63f-134">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="7f63f-134">**Password**</span></span>  
 <span data-ttu-id="7f63f-135">Fournit un mot de passe à utiliser pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="7f63f-135">Provide a password to use when authenticating.</span></span> <span data-ttu-id="7f63f-136">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="7f63f-136">This option is not available.</span></span>  
  
  
