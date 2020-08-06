---
title: Tâche Notifier l’opérateur (Plan de maintenance) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.notifyoperator.f1
helpviewer_keywords:
- Notify Operator Task dialog box
ms.assetid: 39c0797c-ad2b-4591-85c9-a23a7f902895
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4feb59622c2a42de67193c75d545a6b8a2a08863
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611070"
---
# <a name="notify-operator-task-maintenance-plan"></a><span data-ttu-id="b882d-102">Tâche Notifier l'opérateur (Plan de maintenance)</span><span class="sxs-lookup"><span data-stu-id="b882d-102">Notify Operator Task (Maintenance Plan)</span></span>
  <span data-ttu-id="b882d-103">Utilisez la boîte de dialogue **Tâche Notifier l’opérateur** pour ajouter une notification automatique à ce plan de maintenance.</span><span class="sxs-lookup"><span data-stu-id="b882d-103">Use the **Notify Operators Task** dialog to add an automatic notification to this maintenance plan.</span></span> <span data-ttu-id="b882d-104">Pour utiliser cette tâche, la messagerie de base de données doit être activée et correctement configurée avec MSDB comme base de données hôte de messagerie, et vous devez disposer d’un opérateur [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent avec une adresse de messagerie valide.</span><span class="sxs-lookup"><span data-stu-id="b882d-104">To use this task you must have Database Mail enabled and properly configured with MSDB as a Mail Host Database, and have a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operator with a valid e-mail address.</span></span>  
  
 <span data-ttu-id="b882d-105">Cette tâche utilise la procédure stockée sp_notify_operator.</span><span class="sxs-lookup"><span data-stu-id="b882d-105">This task uses the sp_notify_operator stored procedure.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b882d-106">Options</span><span class="sxs-lookup"><span data-stu-id="b882d-106">Options</span></span>  
 <span data-ttu-id="b882d-107">**Connection**</span><span class="sxs-lookup"><span data-stu-id="b882d-107">**Connection**</span></span>  
 <span data-ttu-id="b882d-108">Sélectionnez la connexion serveur à utiliser pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="b882d-108">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="b882d-109">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="b882d-109">**New**</span></span>  
 <span data-ttu-id="b882d-110">Crée une nouvelle connexion serveur à utiliser pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="b882d-110">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="b882d-111">La boîte de dialogue **Nouvelle connexion** est décrite ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="b882d-111">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="b882d-112">**Opérateurs à notifier**</span><span class="sxs-lookup"><span data-stu-id="b882d-112">**Operators to notify**</span></span>  
 <span data-ttu-id="b882d-113">Spécifiez le destinataire du courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="b882d-113">Specify the recipient of the e-mail.</span></span>  
  
 <span data-ttu-id="b882d-114">**Objet du message de notification**</span><span class="sxs-lookup"><span data-stu-id="b882d-114">**Notification message subject**</span></span>  
 <span data-ttu-id="b882d-115">Spécifiez le texte à inclure dans la ligne Objet du message de notification.</span><span class="sxs-lookup"><span data-stu-id="b882d-115">Specify the text to include in the notification message subject line.</span></span>  
  
 <span data-ttu-id="b882d-116">**Corps du message de notification**</span><span class="sxs-lookup"><span data-stu-id="b882d-116">**Notification message body**</span></span>  
 <span data-ttu-id="b882d-117">Spécifiez le texte à inclure dans le corps du message de notification.</span><span class="sxs-lookup"><span data-stu-id="b882d-117">Specify the text to include in the notification message body.</span></span>  
  
 <span data-ttu-id="b882d-118">**Vue T-SQL**</span><span class="sxs-lookup"><span data-stu-id="b882d-118">**View T-SQL**</span></span>  
 <span data-ttu-id="b882d-119">Affiche les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] exécutées sur le serveur pour cette tâche, selon les options sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="b882d-119">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b882d-120">Si le nombre d'objets impliqués est élevé, l'affichage des instructions peut prendre un temps considérable.</span><span class="sxs-lookup"><span data-stu-id="b882d-120">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="b882d-121">Boîte de dialogue Nouvelle connexion</span><span class="sxs-lookup"><span data-stu-id="b882d-121">New Connection Dialog Box</span></span>  
 <span data-ttu-id="b882d-122">**Nom de connexion**</span><span class="sxs-lookup"><span data-stu-id="b882d-122">**Connection name**</span></span>  
 <span data-ttu-id="b882d-123">Entrez un nom pour la nouvelle connexion.</span><span class="sxs-lookup"><span data-stu-id="b882d-123">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="b882d-124">**Sélectionnez ou entrez un nom de serveur.**</span><span class="sxs-lookup"><span data-stu-id="b882d-124">**Select or enter a server name**</span></span>  
 <span data-ttu-id="b882d-125">Sélectionnez un serveur auquel établir la connexion pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="b882d-125">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="b882d-126">**Actualiser**</span><span class="sxs-lookup"><span data-stu-id="b882d-126">**Refresh**</span></span>  
 <span data-ttu-id="b882d-127">Actualise la liste des serveurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="b882d-127">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="b882d-128">**Entrez des informations pour vous connecter au serveur**</span><span class="sxs-lookup"><span data-stu-id="b882d-128">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="b882d-129">Spécifiez le mode d'authentification sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="b882d-129">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="b882d-130">**Utiliser la sécurité intégrée à Windows NT**</span><span class="sxs-lookup"><span data-stu-id="b882d-130">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="b882d-131">Permet de se connecter à une instance du [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] avec l’authentification [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="b882d-131">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="b882d-132">**Utiliser un nom d'utilisateur et un mot de passe spécifiques**</span><span class="sxs-lookup"><span data-stu-id="b882d-132">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="b882d-133">Permet de se connecter à une instance du [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] en utilisant l’authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b882d-133">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="b882d-134">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="b882d-134">This option is not available.</span></span>  
  
 <span data-ttu-id="b882d-135">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="b882d-135">**User name**</span></span>  
 <span data-ttu-id="b882d-136">Fournit le nom d'utilisateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à utiliser pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="b882d-136">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="b882d-137">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="b882d-137">This option is not available.</span></span>  
  
 <span data-ttu-id="b882d-138">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="b882d-138">**Password**</span></span>  
 <span data-ttu-id="b882d-139">Fournit un mot de passe à utiliser pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="b882d-139">Provide a password to use when authenticating.</span></span> <span data-ttu-id="b882d-140">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="b882d-140">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b882d-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b882d-141">See Also</span></span>  
 <span data-ttu-id="b882d-142">[Messagerie de base de données](../database-mail/database-mail.md) </span><span class="sxs-lookup"><span data-stu-id="b882d-142">[Database Mail](../database-mail/database-mail.md) </span></span>  
 [<span data-ttu-id="b882d-143">sp_notify_operator &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b882d-143">sp_notify_operator &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-notify-operator-transact-sql)  
  
  
