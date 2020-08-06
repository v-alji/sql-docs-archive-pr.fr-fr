---
title: Tâche de nettoyage d’historique (Plan de maintenance) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.historycleanup.f1
helpviewer_keywords:
- History Cleanup Task dialog box
ms.assetid: 66bb6c39-958c-4053-a27f-b1118d2567f5
ms.reviewer: ''
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 03ff35b14fc13d2b4446b15501114489b52c421e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612308"
---
# <a name="history-cleanup-task-maintenance-plan"></a><span data-ttu-id="28c37-102">Tâche de nettoyage d'historique (Plan de maintenance)</span><span class="sxs-lookup"><span data-stu-id="28c37-102">History Cleanup Task (Maintenance Plan)</span></span>

  <span data-ttu-id="28c37-103">La boîte de dialogue **Tâche de nettoyage d'historique** vous permet de supprimer les informations d'historique anciennes des tables de la base de données msdb.</span><span class="sxs-lookup"><span data-stu-id="28c37-103">Use the **History Cleanup Task** dialog to discard old historical information from tables in the msdb database.</span></span> <span data-ttu-id="28c37-104">Cette tâche prend en charge la suppression de l'historique de sauvegarde et de restauration, l'historique des travaux de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et l'historique du plan de maintenance.</span><span class="sxs-lookup"><span data-stu-id="28c37-104">This task supports deleting backup and restore history, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Job history, and maintenance plan history.</span></span>  
  
 <span data-ttu-id="28c37-105">Cette instruction utilise les instructions **sp_purge_jobhistory** et **sp_delete_backuphistory** .</span><span class="sxs-lookup"><span data-stu-id="28c37-105">This statement uses the **sp_purge_jobhistory** and **sp_delete_backuphistory** statements.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="28c37-106">Liste d’éléments UI</span><span class="sxs-lookup"><span data-stu-id="28c37-106">UI element list</span></span>  
 <span data-ttu-id="28c37-107">**Connection**</span><span class="sxs-lookup"><span data-stu-id="28c37-107">**Connection**</span></span>  
 <span data-ttu-id="28c37-108">Sélectionnez la connexion serveur à utiliser pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="28c37-108">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="28c37-109">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="28c37-109">**New**</span></span>  
 <span data-ttu-id="28c37-110">Crée une nouvelle connexion serveur à utiliser pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="28c37-110">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="28c37-111">La boîte de dialogue **Nouvelle connexion** est décrite ultérieurement dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="28c37-111">The **New Connection** dialog box is described later in this topic.</span></span>  
  
 <span data-ttu-id="28c37-112">**Sauvegarder et restaurer l'historique**</span><span class="sxs-lookup"><span data-stu-id="28c37-112">**Backup and restore history**</span></span>  
 <span data-ttu-id="28c37-113">La conservation des enregistrements indiquant à quel moment des sauvegardes récentes ont été créées peut aider [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à créer un plan de récupération lorsque vous souhaitez restaurer une base de données.</span><span class="sxs-lookup"><span data-stu-id="28c37-113">Retaining records of when recent backups were created can help [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] create a recovery plan when you want to restore a database.</span></span> <span data-ttu-id="28c37-114">La période de rétention doit être au moins égale à la fréquence des sauvegardes complètes de base de données.</span><span class="sxs-lookup"><span data-stu-id="28c37-114">The retention period should be at least the frequency of full database back ups.</span></span>  
  
 <span data-ttu-id="28c37-115">**Historique des travaux de SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="28c37-115">**SQL Server Agent Job history**</span></span>  
 <span data-ttu-id="28c37-116">Cet historique vous permet de résoudre les problèmes des travaux ayant échoué ou de déterminer la raison pour laquelle des actions se sont produites.</span><span class="sxs-lookup"><span data-stu-id="28c37-116">This history can help you troubleshoot failed jobs, or determine why database actions occurred.</span></span>  
  
 <span data-ttu-id="28c37-117">**Historique du plan de maintenance**</span><span class="sxs-lookup"><span data-stu-id="28c37-117">**Maintenance plan history**</span></span>  
 <span data-ttu-id="28c37-118">Cet historique vous permet de résoudre les problèmes des travaux de plan de maintenance ayant échoué ou de déterminer la raison pour laquelle des actions se sont produites.</span><span class="sxs-lookup"><span data-stu-id="28c37-118">This history can help you troubleshoot failed maintenance plan jobs, or determine why database actions occurred.</span></span>  
  
 <span data-ttu-id="28c37-119">**Supprimer les données d'historique antérieures à**</span><span class="sxs-lookup"><span data-stu-id="28c37-119">**Remove historical data older than**</span></span>  
 <span data-ttu-id="28c37-120">Permet de spécifier l'ancienneté des éléments à supprimer.</span><span class="sxs-lookup"><span data-stu-id="28c37-120">Specify age of items that you want to delete.</span></span>  
  
 <span data-ttu-id="28c37-121">**Vue T-SQL**</span><span class="sxs-lookup"><span data-stu-id="28c37-121">**View T-SQL**</span></span>  
 <span data-ttu-id="28c37-122">Affiche les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] exécutées sur le serveur pour cette tâche, selon les options sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="28c37-122">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28c37-123">Si le nombre d'objets impliqués est élevé, l'affichage des instructions peut prendre un temps considérable.</span><span class="sxs-lookup"><span data-stu-id="28c37-123">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="28c37-124">Boîte de dialogue Nouvelle connexion</span><span class="sxs-lookup"><span data-stu-id="28c37-124">New Connection Dialog Box</span></span>  
 <span data-ttu-id="28c37-125">**Nom de connexion**</span><span class="sxs-lookup"><span data-stu-id="28c37-125">**Connection name**</span></span>  
 <span data-ttu-id="28c37-126">Entrez un nom pour la nouvelle connexion.</span><span class="sxs-lookup"><span data-stu-id="28c37-126">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="28c37-127">**Sélectionnez ou entrez un nom de serveur.**</span><span class="sxs-lookup"><span data-stu-id="28c37-127">**Select or enter a server name**</span></span>  
 <span data-ttu-id="28c37-128">Sélectionnez un serveur auquel établir la connexion pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="28c37-128">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="28c37-129">**Actualiser**</span><span class="sxs-lookup"><span data-stu-id="28c37-129">**Refresh**</span></span>  
 <span data-ttu-id="28c37-130">Actualise la liste des serveurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="28c37-130">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="28c37-131">**Entrez des informations pour vous connecter au serveur**</span><span class="sxs-lookup"><span data-stu-id="28c37-131">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="28c37-132">Spécifiez le mode d'authentification sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="28c37-132">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="28c37-133">**Utiliser la sécurité intégrée à Windows NT**</span><span class="sxs-lookup"><span data-stu-id="28c37-133">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="28c37-134">Permet de se connecter à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] SQL Server en utilisant l'authentification Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="28c37-134">Connect to an instance of the SQL Server [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Microsoft Windows Authentication.</span></span>  
  
 <span data-ttu-id="28c37-135">**Utiliser un nom d'utilisateur et un mot de passe spécifiques**</span><span class="sxs-lookup"><span data-stu-id="28c37-135">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="28c37-136">Permet de se connecter à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] SQL Server via l'authentification SQL Server.</span><span class="sxs-lookup"><span data-stu-id="28c37-136">Connect to an instance of the SQL Server [!INCLUDE[ssDE](../../includes/ssde-md.md)] using SQL Server Authentication.</span></span> <span data-ttu-id="28c37-137">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="28c37-137">This option is not available.</span></span>  
  
 <span data-ttu-id="28c37-138">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="28c37-138">**User name**</span></span>  
 <span data-ttu-id="28c37-139">Fournit le nom d'utilisateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à utiliser pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="28c37-139">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="28c37-140">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="28c37-140">This option is not available.</span></span>  
  
 <span data-ttu-id="28c37-141">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="28c37-141">**Password**</span></span>  
 <span data-ttu-id="28c37-142">Fournit un mot de passe à utiliser pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="28c37-142">Provide a password to use when authenticating.</span></span> <span data-ttu-id="28c37-143">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="28c37-143">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28c37-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="28c37-144">See Also</span></span>  
 <span data-ttu-id="28c37-145">[sp_purge_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="28c37-145">[sp_purge_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql) </span></span>  
 [<span data-ttu-id="28c37-146">sp_delete_backuphistory &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="28c37-146">sp_delete_backuphistory &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql)  
  
  
