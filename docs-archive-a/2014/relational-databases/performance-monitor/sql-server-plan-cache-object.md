---
title: SQL Server, objet Plan Cache | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Plan Cache object
- SQLServer:Plan Cache
ms.assetid: 225e2b02-8d2f-4f29-9eba-f5847c36ea99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 002cbe261c531c18bdbb2170da9694cc8abde89d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696764"
---
# <a name="sql-server-plan-cache-object"></a><span data-ttu-id="907ac-102">SQL Server - Objet Plan Cache</span><span class="sxs-lookup"><span data-stu-id="907ac-102">SQL Server, Plan Cache Object</span></span>
  <span data-ttu-id="907ac-103">L’objet **Plan Cache** fournit des compteurs qui permettent de surveiller l’utilisation de la mémoire par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour stocker des objets tels que des procédures stockées, des instructions et des déclencheurs [!INCLUDE[tsql](../../includes/tsql-md.md)] ad hoc et préparés.</span><span class="sxs-lookup"><span data-stu-id="907ac-103">The **Plan Cache** object provides counters to monitor how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses memory to store objects such as stored procedures, ad hoc and prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, and triggers.</span></span> <span data-ttu-id="907ac-104">Vous pouvez surveiller simultanément plusieurs instances de l’objet **Plan Cache** , chacune représentant un type différent de plan de requête à surveiller.</span><span class="sxs-lookup"><span data-stu-id="907ac-104">Multiple instances of the **Plan Cache** object can be monitored at the same time, with each instance representing a different type of plan to monitor.</span></span>  
  
 <span data-ttu-id="907ac-105">Ce tableau décrit les compteurs **SQLServer:Plan Cache**.</span><span class="sxs-lookup"><span data-stu-id="907ac-105">This table describes are the **SQLServer:Plan Cache**counters.</span></span>  
  
|<span data-ttu-id="907ac-106">Compteurs Plan Cache SQL Server</span><span class="sxs-lookup"><span data-stu-id="907ac-106">SQL Server Plan Cache counters</span></span>|<span data-ttu-id="907ac-107">Description</span><span class="sxs-lookup"><span data-stu-id="907ac-107">Description</span></span>|  
|------------------------------------|-----------------|  
|<span data-ttu-id="907ac-108">**Taux d'accès au cache**</span><span class="sxs-lookup"><span data-stu-id="907ac-108">**Cache Hit Ratio**</span></span>|<span data-ttu-id="907ac-109">Rapport entre les présences dans le cache et les recherches.</span><span class="sxs-lookup"><span data-stu-id="907ac-109">Ratio between cache hits and lookups.</span></span>|  
|<span data-ttu-id="907ac-110">**Nombre d'objets cache**</span><span class="sxs-lookup"><span data-stu-id="907ac-110">**Cache Object Counts**</span></span>|<span data-ttu-id="907ac-111">Nombre d'objets cache dans le cache.</span><span class="sxs-lookup"><span data-stu-id="907ac-111">Number of cache objects in the cache.</span></span>|  
|<span data-ttu-id="907ac-112">**Pages du cache**</span><span class="sxs-lookup"><span data-stu-id="907ac-112">**Cache Pages**</span></span>|<span data-ttu-id="907ac-113">Nombre de pages de 8 Ko utilisées par des objets cache.</span><span class="sxs-lookup"><span data-stu-id="907ac-113">Number of 8-kilobyte (KB) pages used by cache objects.</span></span>|  
|<span data-ttu-id="907ac-114">**Objets cache en cours d'utilisation**</span><span class="sxs-lookup"><span data-stu-id="907ac-114">**Cache Objects in use**</span></span>|<span data-ttu-id="907ac-115">Nombre d'objets cache en cours d'utilisation.</span><span class="sxs-lookup"><span data-stu-id="907ac-115">Number of cache objects in use.</span></span>|  
  
 <span data-ttu-id="907ac-116">Chaque compteur de l'objet contient les instances suivantes :</span><span class="sxs-lookup"><span data-stu-id="907ac-116">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="907ac-117">Instance Plan Cache</span><span class="sxs-lookup"><span data-stu-id="907ac-117">Plan Cache instance</span></span>|<span data-ttu-id="907ac-118">Description</span><span class="sxs-lookup"><span data-stu-id="907ac-118">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="907ac-119">**_Total**</span><span class="sxs-lookup"><span data-stu-id="907ac-119">**_Total**</span></span>|<span data-ttu-id="907ac-120">Informations sur tous les types d'instances du cache.</span><span class="sxs-lookup"><span data-stu-id="907ac-120">Information for all types of cache instances.</span></span>|  
|<span data-ttu-id="907ac-121">**Plans Sql**</span><span class="sxs-lookup"><span data-stu-id="907ac-121">**Sql Plans**</span></span>|<span data-ttu-id="907ac-122">Plans de requêtes créés à partir d’une requête ad hoc [!INCLUDE[tsql](../../includes/tsql-md.md)] , notamment les requêtes paramétrables automatiquement, ou à partir d’instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] préparées au moyen de **sp_prepare** or **sp_cursorprepare**.</span><span class="sxs-lookup"><span data-stu-id="907ac-122">Query plans produced from an ad hoc [!INCLUDE[tsql](../../includes/tsql-md.md)] query, including auto-parameterized queries, or from [!INCLUDE[tsql](../../includes/tsql-md.md)] statements prepared using **sp_prepare** or **sp_cursorprepare**.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="907ac-123">place en mémoire cache les plans des instructions ad hoc [!INCLUDE[tsql](../../includes/tsql-md.md)] pour une réutilisation ultérieure si l’instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] identique est exécutée par la suite.</span><span class="sxs-lookup"><span data-stu-id="907ac-123">caches the plans for ad hoc [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for later reuse if the identical [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is later executed.</span></span> <span data-ttu-id="907ac-124">Les requêtes paramétrables par l'utilisateur (même sans préparation explicite) sont également surveillées en tant que plans SQL préparés.</span><span class="sxs-lookup"><span data-stu-id="907ac-124">User-parameterized queries (even if not explicitly prepared) are also monitored as Prepared SQL Plans.</span></span>|  
|<span data-ttu-id="907ac-125">**Objet Plans**</span><span class="sxs-lookup"><span data-stu-id="907ac-125">**Object Plans**</span></span>|<span data-ttu-id="907ac-126">Plans de requête générés par la création d'une procédure stockée, d'une fonction ou d'un déclencheur.</span><span class="sxs-lookup"><span data-stu-id="907ac-126">Query plans generated by creating a stored procedure, function, or trigger.</span></span>|  
|<span data-ttu-id="907ac-127">**Arborescences liées**</span><span class="sxs-lookup"><span data-stu-id="907ac-127">**Bound Trees**</span></span>|<span data-ttu-id="907ac-128">Arborescences normalisées pour les vues, les règles, les colonnes calculées et les contraintes de vérification.</span><span class="sxs-lookup"><span data-stu-id="907ac-128">Normalized trees for views, rules, computed columns, and check constraints.</span></span>|  
|<span data-ttu-id="907ac-129">**Procédures stockées étendues**</span><span class="sxs-lookup"><span data-stu-id="907ac-129">**Extended Stored Procedures**</span></span>|<span data-ttu-id="907ac-130">Informations sur les catalogues pour les procédures stockées étendues.</span><span class="sxs-lookup"><span data-stu-id="907ac-130">Catalog information for extended stores procedures.</span></span>|  
|<span data-ttu-id="907ac-131">**Tables temporaires & Variables de table**</span><span class="sxs-lookup"><span data-stu-id="907ac-131">**Temporary Tables & Table Variables**</span></span>|<span data-ttu-id="907ac-132">Informations sur le cache concernant les tables temporaires et les variables de table.</span><span class="sxs-lookup"><span data-stu-id="907ac-132">Cache information related to temporary tables and table variables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="907ac-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="907ac-133">See Also</span></span>  
 <span data-ttu-id="907ac-134">[Mémoire du serveur (option de configuration de serveur)](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span><span class="sxs-lookup"><span data-stu-id="907ac-134">[Server Memory Server Configuration Options](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span></span>  
 <span data-ttu-id="907ac-135">[SQL Server, objet Gestionnaire de tampons](sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="907ac-135">[SQL Server, Buffer Manager Object](sql-server-buffer-manager-object.md) </span></span>  
 [<span data-ttu-id="907ac-136">Analyser l’utilisation des ressources &#40;Moniteur système&#41;</span><span class="sxs-lookup"><span data-stu-id="907ac-136">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
