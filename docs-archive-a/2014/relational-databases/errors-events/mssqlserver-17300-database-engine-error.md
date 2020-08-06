---
title: MSSQLSERVER_17300 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17300 (Database Engine error)
ms.assetid: c1d6bfb6-28af-4df6-8087-25807602d282
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2f77e39c71901166085d011d6d00f9a4a379bece
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696904"
---
# <a name="mssqlserver_17300"></a><span data-ttu-id="4d8a5-102">MSSQLSERVER_17300</span><span class="sxs-lookup"><span data-stu-id="4d8a5-102">MSSQLSERVER_17300</span></span>
    
## <a name="details"></a><span data-ttu-id="4d8a5-103">Détails</span><span class="sxs-lookup"><span data-stu-id="4d8a5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4d8a5-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="4d8a5-104">Product Name</span></span>|<span data-ttu-id="4d8a5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4d8a5-105">SQL Server</span></span>|  
|<span data-ttu-id="4d8a5-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="4d8a5-106">Event ID</span></span>|<span data-ttu-id="4d8a5-107">17300</span><span class="sxs-lookup"><span data-stu-id="4d8a5-107">17300</span></span>|  
|<span data-ttu-id="4d8a5-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="4d8a5-108">Event Source</span></span>|<span data-ttu-id="4d8a5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4d8a5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4d8a5-110">Composant</span><span class="sxs-lookup"><span data-stu-id="4d8a5-110">Component</span></span>|<span data-ttu-id="4d8a5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4d8a5-111">SQLEngine</span></span>|  
|<span data-ttu-id="4d8a5-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="4d8a5-112">Symbolic Name</span></span>|<span data-ttu-id="4d8a5-113">PROC_OUT_OF_SYSTASK_SESSIONS</span><span class="sxs-lookup"><span data-stu-id="4d8a5-113">PROC_OUT_OF_SYSTASK_SESSIONS</span></span>|  
|<span data-ttu-id="4d8a5-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="4d8a5-114">Message Text</span></span>|<span data-ttu-id="4d8a5-115">SQL Server n'a pas pu exécuter une nouvelle tâche système, soit parce que la mémoire est insuffisante, soit parce que le nombre de sessions configurées dépasse le nombre maximal autorisé sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="4d8a5-115">SQL Server was unable to run a new system task, either because there is insufficient memory or the number of configured sessions exceeds the maximum allowed in the server.</span></span> <span data-ttu-id="4d8a5-116">Vérifiez que le serveur dispose de la mémoire adéquate.</span><span class="sxs-lookup"><span data-stu-id="4d8a5-116">Verify that the server has adequate memory.</span></span> <span data-ttu-id="4d8a5-117">Utilisez sp_configure avec l'option « User connections » pour spécifier le nombre maximal de connexions utilisateur autorisées.</span><span class="sxs-lookup"><span data-stu-id="4d8a5-117">Use sp_configure with option 'user connections' to check the maximum number of user connections allowed.</span></span> <span data-ttu-id="4d8a5-118">Utilisez sys.dm_exec_sessions pour vérifier le nombre actuel de sessions, y compris les processus utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4d8a5-118">Use sys.dm_exec_sessions to check the current number of sessions, including user processes.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4d8a5-119">Explication</span><span class="sxs-lookup"><span data-stu-id="4d8a5-119">Explanation</span></span>  
 <span data-ttu-id="4d8a5-120">Une tentative d'exécution d'une nouvelle tâche système a échoué à cause d'une insuffisance de mémoire ou d'un dépassement du nombre de sessions configurées sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="4d8a5-120">An attempt to run a new system task failed because of insufficient memory or because the number of configured sessions in the server was exceeded.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4d8a5-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="4d8a5-121">User Action</span></span>  
 <span data-ttu-id="4d8a5-122">Vérifiez que le serveur dispose de suffisamment de mémoire.</span><span class="sxs-lookup"><span data-stu-id="4d8a5-122">Verify that the server has enough memory.</span></span> <span data-ttu-id="4d8a5-123">Vérifiez le nombre actuel de tâches système en utilisant sys.dm_exec_sessions et vérifiez la valeur configurée du maximum de connexions utilisateur en utilisant sp_configure.</span><span class="sxs-lookup"><span data-stu-id="4d8a5-123">Verify the current number of system tasks by using sys.dm_exec_sessions, and verify the configured value of maximum user connections by using sp_configure.</span></span>  
  
 <span data-ttu-id="4d8a5-124">Effectuez les tâches suivantes comme il convient :</span><span class="sxs-lookup"><span data-stu-id="4d8a5-124">Perform the following tasks as appropriate:</span></span>  
  
-   <span data-ttu-id="4d8a5-125">Ajoutez de la mémoire au serveur.</span><span class="sxs-lookup"><span data-stu-id="4d8a5-125">Add more memory to the server.</span></span>  
  
-   <span data-ttu-id="4d8a5-126">Mettez fin à une ou plusieurs sessions.</span><span class="sxs-lookup"><span data-stu-id="4d8a5-126">Terminate one or more sessions.</span></span>  
  
-   <span data-ttu-id="4d8a5-127">Augmentez le nombre maximal de connexions utilisateur autorisées sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="4d8a5-127">Increase the maximum number of user connections allowed on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d8a5-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4d8a5-128">See Also</span></span>  
 <span data-ttu-id="4d8a5-129">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4d8a5-129">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="4d8a5-130">[Options de configuration de serveur &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4d8a5-130">[Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="4d8a5-131">[sys.dm_exec_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4d8a5-131">[sys.dm_exec_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) </span></span>  
 <span data-ttu-id="4d8a5-132">[Configurer l’option de configuration de serveur User connections](../../database-engine/configure-windows/configure-the-user-connections-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="4d8a5-132">[Configure the user connections Server Configuration Option](../../database-engine/configure-windows/configure-the-user-connections-server-configuration-option.md) </span></span>  
 [<span data-ttu-id="4d8a5-133">KILL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4d8a5-133">KILL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/kill-transact-sql)  
  
  
