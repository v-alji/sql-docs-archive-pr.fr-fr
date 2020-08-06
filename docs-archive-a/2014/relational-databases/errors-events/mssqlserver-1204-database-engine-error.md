---
title: MSSQLSERVER_1204 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1204 (Database Engine error)
ms.assetid: de6ece78-79de-484d-9224-ca0f7645815f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7ca03c19552b88e391d2de053193a70531571ece
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604530"
---
# <a name="mssqlserver_1204"></a><span data-ttu-id="8e9ba-102">MSSQLSERVER_1204</span><span class="sxs-lookup"><span data-stu-id="8e9ba-102">MSSQLSERVER_1204</span></span>
    
## <a name="details"></a><span data-ttu-id="8e9ba-103">Détails</span><span class="sxs-lookup"><span data-stu-id="8e9ba-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8e9ba-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="8e9ba-104">Product Name</span></span>|<span data-ttu-id="8e9ba-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8e9ba-105">SQL Server</span></span>|  
|<span data-ttu-id="8e9ba-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="8e9ba-106">Event ID</span></span>|<span data-ttu-id="8e9ba-107">1204</span><span class="sxs-lookup"><span data-stu-id="8e9ba-107">1204</span></span>|  
|<span data-ttu-id="8e9ba-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="8e9ba-108">Event Source</span></span>|<span data-ttu-id="8e9ba-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8e9ba-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8e9ba-110">Composant</span><span class="sxs-lookup"><span data-stu-id="8e9ba-110">Component</span></span>|<span data-ttu-id="8e9ba-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8e9ba-111">SQLEngine</span></span>|  
|<span data-ttu-id="8e9ba-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="8e9ba-112">Symbolic Name</span></span>|<span data-ttu-id="8e9ba-113">LK_OUTOF</span><span class="sxs-lookup"><span data-stu-id="8e9ba-113">LK_OUTOF</span></span>|  
|<span data-ttu-id="8e9ba-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="8e9ba-114">Message Text</span></span>|<span data-ttu-id="8e9ba-115">L'instance du moteur de base de données SQL Server ne peut pas obtenir une ressource LOCK en ce moment.</span><span class="sxs-lookup"><span data-stu-id="8e9ba-115">The instance of the SQL Server Database Engine cannot obtain a LOCK resource at this time.</span></span> <span data-ttu-id="8e9ba-116">Réexécutez votre instruction lorsque le nombre d'utilisateurs actifs est moindre.</span><span class="sxs-lookup"><span data-stu-id="8e9ba-116">Rerun your statement when there are fewer active users.</span></span> <span data-ttu-id="8e9ba-117">Demandez à l'administrateur de base de données de vérifier la configuration du verrou et de la mémoire pour cette instance, ou de vérifier les longues transactions.</span><span class="sxs-lookup"><span data-stu-id="8e9ba-117">Ask the database administrator to check the lock and memory configuration for this instance, or to check for long-running transactions.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8e9ba-118">Explication</span><span class="sxs-lookup"><span data-stu-id="8e9ba-118">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8e9ba-119">ne peut pas obtenir de ressource de verrouillage.</span><span class="sxs-lookup"><span data-stu-id="8e9ba-119">cannot obtain a lock resource.</span></span> <span data-ttu-id="8e9ba-120">Cela peut être dû à l'une des raisons suivantes :</span><span class="sxs-lookup"><span data-stu-id="8e9ba-120">This can be caused by either of the following reasons:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8e9ba-121">ne peut pas allouer plus de mémoire à partir du système d’exploitation, soit parce que d’autres processus l’utilisent, soit parce que le serveur fonctionne avec l’option **Mémoire maximum du serveur** configurée.</span><span class="sxs-lookup"><span data-stu-id="8e9ba-121">cannot allocate more memory from the operating system, either because other processes are using it, or because the server is operating with the **max server memory** option configured.</span></span>  
  
-   <span data-ttu-id="8e9ba-122">Le gestionnaire de verrous n'utilisera pas plus de 60 % de la mémoire disponible pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e9ba-122">The lock manager will not use more than 60 percent of the memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8e9ba-123">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="8e9ba-123">User Action</span></span>  
 <span data-ttu-id="8e9ba-124">Si vous pensez que SQL Server ne peut pas allouer suffisamment de mémoire, essayez de procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="8e9ba-124">If you suspect that SQL Server cannot allocate sufficient memory, try the following:</span></span>  
  
-   <span data-ttu-id="8e9ba-125">Si des applications autres que SQL Server consomment des ressources, essayez d'arrêter ces applications ou envisagez de les exécuter sur un serveur distinct.</span><span class="sxs-lookup"><span data-stu-id="8e9ba-125">If applications besides SQL Server are consuming resources, try stopping these applications or consider running them on a separate server.</span></span> <span data-ttu-id="8e9ba-126">Cela libérera de la mémoire à partir d'autres processus pour SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8e9ba-126">This will remove release memory from other processes for SQL Server.</span></span>  
  
-   <span data-ttu-id="8e9ba-127">Si vous avez configuré l'option max server memory, augmentez la valeur de ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="8e9ba-127">If you have configured max server memory, increase max server memory setting.</span></span>  
  
 <span data-ttu-id="8e9ba-128">Si vous pensez que le gestionnaire de verrous a utilisé la quantité maximale de mémoire disponible, identifiez la transaction qui maintient le plus de verrous et mettez-y fin.</span><span class="sxs-lookup"><span data-stu-id="8e9ba-128">If you suspect that the lock manager has used the maximum amount of available memory identify the transaction that is holding the most locks and terminate it.</span></span> <span data-ttu-id="8e9ba-129">Le script ci-dessous identifiera la transaction avec le plus de verrous :</span><span class="sxs-lookup"><span data-stu-id="8e9ba-129">The following script will identify the transaction with the most locks:</span></span>  
  
```  
SELECT request_session_id, COUNT (*) num_locks  
FROM sys.dm_tran_locks  
GROUP BY request_session_id   
ORDER BY count (*) DESC  
```  
  
 <span data-ttu-id="8e9ba-130">Considérez l'ID de session le plus élevé et mettez-y fin à l'aide de la commande KILL.</span><span class="sxs-lookup"><span data-stu-id="8e9ba-130">Take the highest session id, and terminate it using the KILL command.</span></span>  
  
  
