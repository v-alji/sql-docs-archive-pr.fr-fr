---
title: MSSQLSERVER_1222 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1222 (Database Engine error)
ms.assetid: c5b1c2f4-f591-4cc1-aa17-204636a27f29
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ac3fe9314386836633a11f17d6775c75019de93a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600060"
---
# <a name="mssqlserver_1222"></a><span data-ttu-id="e7ef8-102">MSSQLSERVER_1222</span><span class="sxs-lookup"><span data-stu-id="e7ef8-102">MSSQLSERVER_1222</span></span>
    
## <a name="details"></a><span data-ttu-id="e7ef8-103">Détails</span><span class="sxs-lookup"><span data-stu-id="e7ef8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e7ef8-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="e7ef8-104">Product Name</span></span>|<span data-ttu-id="e7ef8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e7ef8-105">SQL Server</span></span>|  
|<span data-ttu-id="e7ef8-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="e7ef8-106">Event ID</span></span>|<span data-ttu-id="e7ef8-107">1222</span><span class="sxs-lookup"><span data-stu-id="e7ef8-107">1222</span></span>|  
|<span data-ttu-id="e7ef8-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="e7ef8-108">Event Source</span></span>|<span data-ttu-id="e7ef8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e7ef8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e7ef8-110">Composant</span><span class="sxs-lookup"><span data-stu-id="e7ef8-110">Component</span></span>|<span data-ttu-id="e7ef8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e7ef8-111">SQLEngine</span></span>|  
|<span data-ttu-id="e7ef8-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="e7ef8-112">Symbolic Name</span></span>|<span data-ttu-id="e7ef8-113">LK_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e7ef8-113">LK_TIMEOUT</span></span>|  
|<span data-ttu-id="e7ef8-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="e7ef8-114">Message Text</span></span>|<span data-ttu-id="e7ef8-115">Délai de requête de verrou dépassé.</span><span class="sxs-lookup"><span data-stu-id="e7ef8-115">Lock request time out period exceeded.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e7ef8-116">Explication</span><span class="sxs-lookup"><span data-stu-id="e7ef8-116">Explanation</span></span>  
 <span data-ttu-id="e7ef8-117">Une autre transaction a maintenu un verrou sur une ressource requise plus longtemps que cette requête pouvait attendre.</span><span class="sxs-lookup"><span data-stu-id="e7ef8-117">Another transaction held a lock on a required resource longer than this query could wait for it.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e7ef8-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e7ef8-118">User Action</span></span>  
 <span data-ttu-id="e7ef8-119">Effectuez les tâches ci-dessous pour atténuer le problème :</span><span class="sxs-lookup"><span data-stu-id="e7ef8-119">Perform the following tasks to alleviate the problem:</span></span>  
  
1.  <span data-ttu-id="e7ef8-120">Localisez la transaction qui maintient le verrou sur la ressource requise, si possible.</span><span class="sxs-lookup"><span data-stu-id="e7ef8-120">Locate the transaction that is holding the lock on the required resource, if possible.</span></span> <span data-ttu-id="e7ef8-121">Utilisez les vues de gestion dynamique **sys.dm_os_waiting_tasks** et **sys.dm_tran_locks**.</span><span class="sxs-lookup"><span data-stu-id="e7ef8-121">Use **sys.dm_os_waiting_tasks** and **sys.dm_tran_locks** dynamic management views.</span></span>  
  
2.  <span data-ttu-id="e7ef8-122">Si la transaction continue à maintenir le verrou, mettez fin à cette transaction, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="e7ef8-122">If the transaction is still holding the lock, terminate that transaction if appropriate.</span></span>  
  
3.  <span data-ttu-id="e7ef8-123">Exécutez de nouveau la requête.</span><span class="sxs-lookup"><span data-stu-id="e7ef8-123">Execute the query again.</span></span>  
  
 <span data-ttu-id="e7ef8-124">Si cette erreur se produit fréquemment, modifiez le délai d'attente de verrouillage ou modifiez les transactions incriminées pour qu'elles maintiennent le verrou moins longtemps.</span><span class="sxs-lookup"><span data-stu-id="e7ef8-124">If this error occurs frequently change the lock time-out period or modify the offending transactions so that they hold the lock for less time.</span></span>  
  
  
