---
title: MSSQL_ENG014010 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014010 error
ms.assetid: 6ea84f2f-e7a2-4028-9ea9-af0d2eba660e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c3d989eb7ae78562fb77d9896545539ba4ca3c7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600811"
---
# <a name="mssql_eng014010"></a><span data-ttu-id="bddef-102">MSSQL_ENG014010</span><span class="sxs-lookup"><span data-stu-id="bddef-102">MSSQL_ENG014010</span></span>
    
## <a name="message-details"></a><span data-ttu-id="bddef-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="bddef-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bddef-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="bddef-104">Product Name</span></span>|<span data-ttu-id="bddef-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bddef-105">SQL Server</span></span>|  
|<span data-ttu-id="bddef-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="bddef-106">Event ID</span></span>|<span data-ttu-id="bddef-107">14010</span><span class="sxs-lookup"><span data-stu-id="bddef-107">14010</span></span>|  
|<span data-ttu-id="bddef-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="bddef-108">Event Source</span></span>|<span data-ttu-id="bddef-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bddef-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bddef-110">Composant</span><span class="sxs-lookup"><span data-stu-id="bddef-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="bddef-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="bddef-111">Symbolic Name</span></span>||  
|<span data-ttu-id="bddef-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="bddef-112">Message Text</span></span>|<span data-ttu-id="bddef-113">Le serveur '%s' n'est pas défini comme serveur d'abonnements.</span><span class="sxs-lookup"><span data-stu-id="bddef-113">The server '%s' is not defined as a subscription server.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bddef-114">Explication</span><span class="sxs-lookup"><span data-stu-id="bddef-114">Explanation</span></span>  
 <span data-ttu-id="bddef-115">La réplication requiert que tous les serveurs d'une topologie soient enregistrés avec le nom d'ordinateur et un nom d'instance facultatif (dans le cas d'une instance cluster, le nom du serveur virtuel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec le nom d'instance facultatif).</span><span class="sxs-lookup"><span data-stu-id="bddef-115">Replication expects all servers in a topology to be registered using the computer name with an optional instance name (in the case of a clustered instance, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] virtual server name with the optional instance name).</span></span> <span data-ttu-id="bddef-116">Pour que la réplication fonctionne correctement, la valeur renvoyée par `SELECT @@SERVERNAME` pour chaque serveur de la topologie doit correspondre au nom d'ordinateur ou au nom de serveur virtuel avec le nom d'instance facultatif.</span><span class="sxs-lookup"><span data-stu-id="bddef-116">For replication to function properly, the value returned by `SELECT @@SERVERNAME` for each server in the topology should match the computer name or virtual server name with the optional instance name.</span></span>  
  
 <span data-ttu-id="bddef-117">La réplication n'est pas prise en charge si vous avez inscrit une des instances [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] par adresse IP ou par nom de domaine pleinement qualifié (FQDN).</span><span class="sxs-lookup"><span data-stu-id="bddef-117">Replication is not supported if you have registered any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances by IP address or by Fully Qualified Domain Name (FQDN).</span></span> <span data-ttu-id="bddef-118">Cette erreur peut se produire si vous avez une des instances [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] inscrite par adresse IP ou par nom complet de domaine (FQDN) dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] lorsque vous avez configuré la réplication.</span><span class="sxs-lookup"><span data-stu-id="bddef-118">If you have any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances registered by IP address or by FQDN in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] when you configured replication, this error could be raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bddef-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="bddef-119">User Action</span></span>  
 <span data-ttu-id="bddef-120">Vérifiez que toutes les instances [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de la topologie sont inscrites correctement.</span><span class="sxs-lookup"><span data-stu-id="bddef-120">Verify that all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances in the topology are registered properly.</span></span> <span data-ttu-id="bddef-121">Si le nom réseau de l'ordinateur et le nom de l'instance SQL Server diffèrent, effectuez une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="bddef-121">If the network name of the computer and the name of the SQL Server instance differ, either:</span></span>  
  
-   <span data-ttu-id="bddef-122">Ajoutez le nom de l'instance SQL Server comme nom réseau valide.</span><span class="sxs-lookup"><span data-stu-id="bddef-122">Add the SQL Server instance name as a valid network name.</span></span> <span data-ttu-id="bddef-123">Pour définir un autre nom réseau, une méthode possible consiste à l'ajouter au fichier hosts local.</span><span class="sxs-lookup"><span data-stu-id="bddef-123">One method to set an alternative network name is to add it to the local hosts file.</span></span> <span data-ttu-id="bddef-124">Le fichier hosts local est installé par défaut dans le répertoire WINDOWS\system32\drivers\etc ou WINNT\system32\drivers\etc. Pour plus d'informations, reportez-vous à la documentation Windows.</span><span class="sxs-lookup"><span data-stu-id="bddef-124">The local hosts file is located by default at WINDOWS\system32\drivers\etc or WINNT\system32\drivers\etc. For more information, see the Windows documentation.</span></span>  
  
     <span data-ttu-id="bddef-125">Si, par exemple, le nom d'ordinateur est comp1, l'adresse IP de l'ordinateur 10.193.17.129 et le nom de l'instance inst1/nominst, ajoutez l'entrée suivante au fichier des hôtes :</span><span class="sxs-lookup"><span data-stu-id="bddef-125">For example, if the computer name is comp1 and the computer has an IP address of 10.193.17.129, and the instance name is inst1/instname, add the following entry to the hosts file:</span></span>  
  
     <span data-ttu-id="bddef-126">10.193.17.129 inst1</span><span class="sxs-lookup"><span data-stu-id="bddef-126">10.193.17.129 inst1</span></span>  
  
-   <span data-ttu-id="bddef-127">Supprimez la réplication, inscrivez chaque instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , puis rétablissez la réplication.</span><span class="sxs-lookup"><span data-stu-id="bddef-127">Remove replication, register each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, and then reestablish replication.</span></span> <span data-ttu-id="bddef-128">Si la valeur de @@SERVERNAME n’est pas correcte pour une instance non-cluster, effectuez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="bddef-128">If the value of @@SERVERNAME is not correct for a nonclustered instance, follow these steps:</span></span>  
  
    ```  
    sp_dropserver '<old_name>', 'droplogins'  
    go  
    sp_addserver '<new_name>', 'local'  
    go  
    ```  
  
     <span data-ttu-id="bddef-129">Après avoir exécuté la procédure stockée [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql), vous devez redémarrer le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour que la modification apportée à @@SERVERNAME soit prise en compte.</span><span class="sxs-lookup"><span data-stu-id="bddef-129">After you execute the [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql) stored procedure, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service for the change to @@SERVERNAME to take effect.</span></span>  
  
     <span data-ttu-id="bddef-130">Si la valeur de @@SERVERNAME n’est pas correcte pour une instance cluster, vous devez changer le nom à l’aide de l’administrateur de cluster.</span><span class="sxs-lookup"><span data-stu-id="bddef-130">If the value of @@SERVERNAME is not correct for a clustered instance, you must change the name using Cluster Administrator.</span></span> <span data-ttu-id="bddef-131">Pour plus d’informations, consultez [instances de cluster de basculement Alwayson &#40;SQL Server&#41;](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bddef-131">For more information, see [AlwaysOn Failover Cluster Instances &#40;SQL Server&#41;](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bddef-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bddef-132">See Also</span></span>  
 <span data-ttu-id="bddef-133">[@@SERVERNAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/servername-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bddef-133">[@@SERVERNAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/servername-transact-sql) </span></span>  
 [<span data-ttu-id="bddef-134">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="bddef-134">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
