---
title: MSSQLSERVER_5235 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5235 (Database Engine error)
ms.assetid: 1aa7e6a5-7ccb-43c8-a1fd-d50e92e0a798
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 42c807944d7506a6a118de97ccd8c2c488942c8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707592"
---
# <a name="mssqlserver_5235"></a><span data-ttu-id="9b9cc-102">MSSQLSERVER_5235</span><span class="sxs-lookup"><span data-stu-id="9b9cc-102">MSSQLSERVER_5235</span></span>
    
## <a name="details"></a><span data-ttu-id="9b9cc-103">Détails</span><span class="sxs-lookup"><span data-stu-id="9b9cc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9b9cc-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="9b9cc-104">Product Name</span></span>|<span data-ttu-id="9b9cc-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9b9cc-105">SQL Server</span></span>|  
|<span data-ttu-id="9b9cc-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="9b9cc-106">Event ID</span></span>|<span data-ttu-id="9b9cc-107">5235</span><span class="sxs-lookup"><span data-stu-id="9b9cc-107">5235</span></span>|  
|<span data-ttu-id="9b9cc-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="9b9cc-108">Event Source</span></span>|<span data-ttu-id="9b9cc-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9b9cc-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9b9cc-110">Composant</span><span class="sxs-lookup"><span data-stu-id="9b9cc-110">Component</span></span>|<span data-ttu-id="9b9cc-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9b9cc-111">SQLEngine</span></span>|  
|<span data-ttu-id="9b9cc-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="9b9cc-112">Symbolic Name</span></span>|<span data-ttu-id="9b9cc-113">DBCC4_ERRORLOG_SUMMARY_PREMATURE_TERMINATION</span><span class="sxs-lookup"><span data-stu-id="9b9cc-113">DBCC4_ERRORLOG_SUMMARY_PREMATURE_TERMINATION</span></span>|  
|<span data-ttu-id="9b9cc-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="9b9cc-114">Message Text</span></span>|<span data-ttu-id="9b9cc-115">[EMERGENCY] DBCC DBCC_COMMAND_DETAILS exécuté par USER_NAME s'est terminé anormalement à cause de l'état d'erreur ERROR_STATE.</span><span class="sxs-lookup"><span data-stu-id="9b9cc-115">[EMERGENCY] DBCC DBCC_COMMAND_DETAILS executed by USER_NAME terminated abnormally due to error state ERROR_STATE.</span></span> <span data-ttu-id="9b9cc-116">Temps écoulé : HOURS heures MINUTES minutes SECONDS secondes.</span><span class="sxs-lookup"><span data-stu-id="9b9cc-116">Elapsed time: HOURS hours MINUTES minutes SECONDS seconds.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9b9cc-117">Explication</span><span class="sxs-lookup"><span data-stu-id="9b9cc-117">Explanation</span></span>  
 <span data-ttu-id="9b9cc-118">Il s'agit du message de synthèse que DBCC inscrit dans le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] lorsqu'un arrêt inattendu se produit au cours de l'exécution de la commande.</span><span class="sxs-lookup"><span data-stu-id="9b9cc-118">This is the summary message that DBCC prints to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log when an unexpected termination occurs while the command is running.</span></span> <span data-ttu-id="9b9cc-119">L'état d'erreur signalé dans le message définit le type d'arrêt inattendu.</span><span class="sxs-lookup"><span data-stu-id="9b9cc-119">The error state reported in the message defines the type of unexpected termination.</span></span>  
  
 <span data-ttu-id="9b9cc-120">Le tableau ci-dessous liste et définit les états d'erreur.</span><span class="sxs-lookup"><span data-stu-id="9b9cc-120">The following table lists and defines the error states.</span></span>  
  
|<span data-ttu-id="9b9cc-121">État d'erreur</span><span class="sxs-lookup"><span data-stu-id="9b9cc-121">Error state</span></span>|<span data-ttu-id="9b9cc-122">Définition</span><span class="sxs-lookup"><span data-stu-id="9b9cc-122">Definition</span></span>|  
|-----------------|----------------|  
|<span data-ttu-id="9b9cc-123">État 0</span><span class="sxs-lookup"><span data-stu-id="9b9cc-123">State 0</span></span>|<span data-ttu-id="9b9cc-124">L'instruction a pris fin en raison d'une altération des métadonnées qui s'est avérée fatale.</span><span class="sxs-lookup"><span data-stu-id="9b9cc-124">The statement was terminated because of a fatal metadata corruption.</span></span> <span data-ttu-id="9b9cc-125">Ce message sera accompagné d’une ou de plusieurs instances de l’erreur 8930.</span><span class="sxs-lookup"><span data-stu-id="9b9cc-125">This message will be accompanied by one or more instances of error 8930.</span></span>|  
|<span data-ttu-id="9b9cc-126">État 1</span><span class="sxs-lookup"><span data-stu-id="9b9cc-126">State 1</span></span>|<span data-ttu-id="9b9cc-127">L'instruction a pris fin en raison d'un échec de contrôle interne.</span><span class="sxs-lookup"><span data-stu-id="9b9cc-127">The statement was terminated because of an internal check failure.</span></span> <span data-ttu-id="9b9cc-128">Ce message sera accompagné d'une ou plusieurs instances de l'erreur 8967.</span><span class="sxs-lookup"><span data-stu-id="9b9cc-128">This message will be accompanied by one or more instances of error 8967.</span></span>|  
|<span data-ttu-id="9b9cc-129">État 2</span><span class="sxs-lookup"><span data-stu-id="9b9cc-129">State 2</span></span>|<span data-ttu-id="9b9cc-130">Les contrôles de table système basiques effectués par les principales tables système du moteur de stockage ont échoué.</span><span class="sxs-lookup"><span data-stu-id="9b9cc-130">Basic system table checks of the core storage engine system tables failed.</span></span> <span data-ttu-id="9b9cc-131">Ce message sera accompagné d’une ou de plusieurs instances des erreurs [7984](mssqlserver-7984-database-engine-error.md), 7985, [7986](mssqlserver-7986-database-engine-error.md), [7987](mssqlserver-7987-database-engine-error.md) ou [7988](mssqlserver-7988-database-engine-error.md).</span><span class="sxs-lookup"><span data-stu-id="9b9cc-131">This message will be accompanied by one or more instances of error [7984](mssqlserver-7984-database-engine-error.md), 7985, [7986](mssqlserver-7986-database-engine-error.md), [7987](mssqlserver-7987-database-engine-error.md), or [7988](mssqlserver-7988-database-engine-error.md).</span></span>|  
|<span data-ttu-id="9b9cc-132">État 3</span><span class="sxs-lookup"><span data-stu-id="9b9cc-132">State 3</span></span>|<span data-ttu-id="9b9cc-133">La réparation en mode urgence DBCC a échoué parce que la base de données n'a pas pu être démarrée après la reconstruction du journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="9b9cc-133">DBCC emergency-mode repair failed because the database could not be started after rebuilding the transaction log.</span></span> <span data-ttu-id="9b9cc-134">Ce message sera accompagné de l'erreur 7909.</span><span class="sxs-lookup"><span data-stu-id="9b9cc-134">This message will be accompanied by error 7909.</span></span>|  
|<span data-ttu-id="9b9cc-135">État 4</span><span class="sxs-lookup"><span data-stu-id="9b9cc-135">State 4</span></span>|<span data-ttu-id="9b9cc-136">Un échec d'assertion ou une violation d'accès se sont produits au cours de l'exécution de la commande.</span><span class="sxs-lookup"><span data-stu-id="9b9cc-136">A failed assertion or access violation occurred during the execution of the command.</span></span>|  
|<span data-ttu-id="9b9cc-137">État 5</span><span class="sxs-lookup"><span data-stu-id="9b9cc-137">State 5</span></span>|<span data-ttu-id="9b9cc-138">Une panne inconnue s'est produite et a arrêté la commande DBCC de manière inattendue.</span><span class="sxs-lookup"><span data-stu-id="9b9cc-138">An unknown failure occurred that unexpectedly terminated the DBCC command.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="9b9cc-139">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="9b9cc-139">User Action</span></span>  
 <span data-ttu-id="9b9cc-140">Le tableau ci-dessous décrit les actions que l'utilisateur doit effectuer pour l'état d'erreur spécifié.</span><span class="sxs-lookup"><span data-stu-id="9b9cc-140">The following table provides the user action that is appropriate for the specified error state.</span></span>  
  
|<span data-ttu-id="9b9cc-141">État d'erreur</span><span class="sxs-lookup"><span data-stu-id="9b9cc-141">Error state</span></span>|<span data-ttu-id="9b9cc-142">Action requise</span><span class="sxs-lookup"><span data-stu-id="9b9cc-142">User action</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="9b9cc-143">État 0</span><span class="sxs-lookup"><span data-stu-id="9b9cc-143">State 0</span></span>|<span data-ttu-id="9b9cc-144">Procédez à une restauration à partir d'une sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="9b9cc-144">Restore from backup.</span></span>|  
|<span data-ttu-id="9b9cc-145">État 1</span><span class="sxs-lookup"><span data-stu-id="9b9cc-145">State 1</span></span>|<span data-ttu-id="9b9cc-146">Contactez le [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service clientèle et le Support technique.</span><span class="sxs-lookup"><span data-stu-id="9b9cc-146">Contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>|  
|<span data-ttu-id="9b9cc-147">État 2</span><span class="sxs-lookup"><span data-stu-id="9b9cc-147">State 2</span></span>|<span data-ttu-id="9b9cc-148">Procédez à une restauration à partir d'une sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="9b9cc-148">Restore from backup.</span></span>|  
|<span data-ttu-id="9b9cc-149">État 3</span><span class="sxs-lookup"><span data-stu-id="9b9cc-149">State 3</span></span>|<span data-ttu-id="9b9cc-150">Procédez à une restauration à partir d'une sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="9b9cc-150">Restore from backup.</span></span>|  
|<span data-ttu-id="9b9cc-151">État 4</span><span class="sxs-lookup"><span data-stu-id="9b9cc-151">State 4</span></span>|<span data-ttu-id="9b9cc-152">Contactez le Service clientèle et le Support technique.</span><span class="sxs-lookup"><span data-stu-id="9b9cc-152">Contact CSS.</span></span>|  
|<span data-ttu-id="9b9cc-153">État 5</span><span class="sxs-lookup"><span data-stu-id="9b9cc-153">State 5</span></span>|<span data-ttu-id="9b9cc-154">Réexécutez la commande.</span><span class="sxs-lookup"><span data-stu-id="9b9cc-154">Run the command again.</span></span> <span data-ttu-id="9b9cc-155">Si le problème persiste, contactez le Service clientèle et le Support technique.</span><span class="sxs-lookup"><span data-stu-id="9b9cc-155">If the problem persists, contact CSS.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9b9cc-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9b9cc-156">See Also</span></span>  
 [<span data-ttu-id="9b9cc-157">DBCC &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9b9cc-157">DBCC &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-transact-sql)  
  
  
