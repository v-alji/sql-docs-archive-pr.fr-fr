---
title: MSSQL_ENG014117 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014117 error
ms.assetid: e5906a76-9511-4c47-8826-8c765b58a39d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e4694aacc7d1f5ee31f4ff54d8cdd4256b48f713
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599928"
---
# <a name="mssql_eng014117"></a><span data-ttu-id="e3674-102">MSSQL_ENG014117</span><span class="sxs-lookup"><span data-stu-id="e3674-102">MSSQL_ENG014117</span></span>
    
## <a name="message-details"></a><span data-ttu-id="e3674-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="e3674-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e3674-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="e3674-104">Product Name</span></span>|<span data-ttu-id="e3674-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e3674-105">SQL Server</span></span>|  
|<span data-ttu-id="e3674-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="e3674-106">Event ID</span></span>|<span data-ttu-id="e3674-107">14117</span><span class="sxs-lookup"><span data-stu-id="e3674-107">14117</span></span>|  
|<span data-ttu-id="e3674-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="e3674-108">Event Source</span></span>|<span data-ttu-id="e3674-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e3674-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e3674-110">Composant</span><span class="sxs-lookup"><span data-stu-id="e3674-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="e3674-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="e3674-111">Symbolic Name</span></span>||  
|<span data-ttu-id="e3674-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="e3674-112">Message Text</span></span>|<span data-ttu-id="e3674-113">'%1!' n'est pas configuré comme base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="e3674-113">'%s' is not configured as a distribution database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e3674-114">Explication</span><span class="sxs-lookup"><span data-stu-id="e3674-114">Explanation</span></span>  
 <span data-ttu-id="e3674-115">Cette erreur peut se produire si une ou plusieurs des conditions suivantes sont vraies :</span><span class="sxs-lookup"><span data-stu-id="e3674-115">This error can occur if one or both of the following are true:</span></span>  
  
-   <span data-ttu-id="e3674-116">L'entrée pour la base de données de distribution est manquante dans **msdb..MSdistributiondbs**.</span><span class="sxs-lookup"><span data-stu-id="e3674-116">The entry for the specified distribution database is missing from **msdb..MSdistributiondbs**.</span></span>  
  
-   <span data-ttu-id="e3674-117">Il n'y a pas d'entrée pour le serveur local dans la base de données **master** , ou bien l'entrée qui s'y trouve n'est pas correcte.</span><span class="sxs-lookup"><span data-stu-id="e3674-117">There is not an entry for the local server in the **master** database, or the entry that is there is incorrect.</span></span>  
  
     <span data-ttu-id="e3674-118">La réplication requiert que tous les serveurs d'une topologie soient enregistrés avec le nom d'ordinateur et un nom d'instance facultatif (dans le cas d'une instance cluster, le nom du serveur virtuel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec le nom d'instance facultatif).</span><span class="sxs-lookup"><span data-stu-id="e3674-118">Replication expects all servers in a topology to be registered using the computer name with an optional instance name (in the case of a clustered instance, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] virtual server name with the optional instance name).</span></span> <span data-ttu-id="e3674-119">Pour que la réplication fonctionne correctement, la valeur renvoyée par `SELECT @@SERVERNAME` pour chaque serveur de la topologie doit correspondre au nom d'ordinateur ou au nom de serveur virtuel avec le nom d'instance facultatif.</span><span class="sxs-lookup"><span data-stu-id="e3674-119">For replication to function properly, the value returned by `SELECT @@SERVERNAME` for each server in the topology should match the computer name or virtual server name with the optional instance name.</span></span>  
  
     <span data-ttu-id="e3674-120">La réplication n'est pas prise en charge si vous avez inscrit une des instances [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] par adresse IP ou par nom de domaine pleinement qualifié (FQDN).</span><span class="sxs-lookup"><span data-stu-id="e3674-120">Replication is not supported if you have registered any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances by IP address or by Fully Qualified Domain Name (FQDN).</span></span> <span data-ttu-id="e3674-121">Si vous aviez une des instances [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] inscrites par adresse IP ou par nom de domaine pleinement qualifié dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] quand vous avez configuré la réplication, cette erreur a pu se produire.</span><span class="sxs-lookup"><span data-stu-id="e3674-121">If you had any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances registered by IP address or by FQDN in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] when you configured replication, this error could be raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e3674-122">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e3674-122">User Action</span></span>  
 <span data-ttu-id="e3674-123">Vérifiez que l'instance du serveur de distribution est inscrite correctement.</span><span class="sxs-lookup"><span data-stu-id="e3674-123">Verify that the Distributor instance is registered properly.</span></span> <span data-ttu-id="e3674-124">Si le nom réseau de l'ordinateur et le nom de l'instance SQL Server diffèrent, effectuez une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="e3674-124">If the network name of the computer and the name of the SQL Server instance differ, either:</span></span>  
  
-   <span data-ttu-id="e3674-125">Ajoutez le nom de l'instance SQL Server comme nom réseau valide.</span><span class="sxs-lookup"><span data-stu-id="e3674-125">Add the SQL Server instance name as a valid network name.</span></span> <span data-ttu-id="e3674-126">Pour définir un autre nom réseau, une méthode possible consiste à l'ajouter au fichier hosts local.</span><span class="sxs-lookup"><span data-stu-id="e3674-126">One method to set an alternative network name is to add it to the local hosts file.</span></span> <span data-ttu-id="e3674-127">Le fichier hosts local est installé par défaut dans le répertoire WINDOWS\system32\drivers\etc ou WINNT\system32\drivers\etc. Pour plus d'informations, reportez-vous à la documentation Windows.</span><span class="sxs-lookup"><span data-stu-id="e3674-127">The local hosts file is located by default at WINDOWS\system32\drivers\etc or WINNT\system32\drivers\etc. For more information, see the Windows documentation.</span></span>  
  
     <span data-ttu-id="e3674-128">Si, par exemple, le nom d'ordinateur est comp1, l'adresse IP de l'ordinateur 10.193.17.129 et le nom de l'instance inst1/nominst, ajoutez l'entrée suivante au fichier des hôtes :</span><span class="sxs-lookup"><span data-stu-id="e3674-128">For example, if the computer name is comp1 and the computer has an IP address of 10.193.17.129, and the instance name is inst1/instname, add the following entry to the hosts file:</span></span>  
  
     <span data-ttu-id="e3674-129">10.193.17.129 inst1</span><span class="sxs-lookup"><span data-stu-id="e3674-129">10.193.17.129 inst1</span></span>  
  
-   <span data-ttu-id="e3674-130">Désactivez la distribution, inscrivez l'instance puis réactivez la distribution.</span><span class="sxs-lookup"><span data-stu-id="e3674-130">Disable distribution, register the instance, and then reestablish distribution.</span></span> <span data-ttu-id="e3674-131">Si la valeur de @@SERVERNAME n’est pas correcte pour une instance non-cluster, effectuez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="e3674-131">If the value of @@SERVERNAME is not correct for a nonclustered instance, follow these steps:</span></span>  
  
    ```  
    sp_dropserver '<old_name>', 'droplogins'  
    go  
    sp_addserver '<new_name>', 'local'  
    go  
    ```  
  
     <span data-ttu-id="e3674-132">Après avoir exécuté la procédure stockée [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql), vous devez redémarrer le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour que la modification apportée à @@SERVERNAME soit prise en compte.</span><span class="sxs-lookup"><span data-stu-id="e3674-132">After you execute the [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql) stored procedure, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service for the change to @@SERVERNAME to take effect.</span></span>  
  
     <span data-ttu-id="e3674-133">Si la valeur de @@SERVERNAME n’est pas correcte pour une instance cluster, vous devez changer le nom à l’aide de l’administrateur de cluster.</span><span class="sxs-lookup"><span data-stu-id="e3674-133">If the value of @@SERVERNAME is not correct for a clustered instance, you must change the name using Cluster Administrator.</span></span> <span data-ttu-id="e3674-134">Pour plus d’informations, consultez [Instances de cluster de basculement AlwaysOn (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e3674-134">For more information, see [AlwaysOn Failover Cluster Instances (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span></span>  
  
 <span data-ttu-id="e3674-135">Après avoir vérifié que l'instance du serveur de distribution est inscrite correctement, vérifiez que la base de données de distribution figure dans **msdb..MSdistributiondbs**.</span><span class="sxs-lookup"><span data-stu-id="e3674-135">After verifying that the Distributor instance is registered properly, verify that the distribution database is listed in **msdb..MSdistributiondbs**.</span></span> <span data-ttu-id="e3674-136">Si elle ne s'y trouve pas :</span><span class="sxs-lookup"><span data-stu-id="e3674-136">If it is not listed:</span></span>  
  
1.  <span data-ttu-id="e3674-137">Créez un script de la configuration de la distribution.</span><span class="sxs-lookup"><span data-stu-id="e3674-137">Script out the distribution configuration.</span></span> <span data-ttu-id="e3674-138">Pour plus d'informations, voir [Scripting Replication](scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="e3674-138">For more information, see [Scripting Replication](scripting-replication.md).</span></span>  
  
2.  <span data-ttu-id="e3674-139">Désactivez la distribution puis réactivez-la.</span><span class="sxs-lookup"><span data-stu-id="e3674-139">Disable distribution and then re-enable it.</span></span> <span data-ttu-id="e3674-140">Pour plus d'informations, voir [Configure Distribution](configure-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="e3674-140">For more information, see [Configure Distribution](configure-distribution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3674-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e3674-141">See Also</span></span>  
 [<span data-ttu-id="e3674-142">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="e3674-142">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
