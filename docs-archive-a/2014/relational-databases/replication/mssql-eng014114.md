---
title: MSSQL_ENG014114 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014114 error
ms.assetid: f5f04590-e1c6-40d8-ab2b-98c791a0fc44
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3ba2a1fde59f55eecbfeeec46555567cde964f8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599927"
---
# <a name="mssql_eng014114"></a><span data-ttu-id="f8638-102">MSSQL_ENG014114</span><span class="sxs-lookup"><span data-stu-id="f8638-102">MSSQL_ENG014114</span></span>
    
## <a name="message-details"></a><span data-ttu-id="f8638-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="f8638-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f8638-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="f8638-104">Product Name</span></span>|<span data-ttu-id="f8638-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f8638-105">SQL Server</span></span>|  
|<span data-ttu-id="f8638-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="f8638-106">Event ID</span></span>|<span data-ttu-id="f8638-107">14114</span><span class="sxs-lookup"><span data-stu-id="f8638-107">14114</span></span>|  
|<span data-ttu-id="f8638-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="f8638-108">Event Source</span></span>|<span data-ttu-id="f8638-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f8638-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f8638-110">Composant</span><span class="sxs-lookup"><span data-stu-id="f8638-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="f8638-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="f8638-111">Symbolic Name</span></span>||  
|<span data-ttu-id="f8638-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="f8638-112">Message Text</span></span>|<span data-ttu-id="f8638-113">'%1!' n'est pas configuré en tant que distributeur.</span><span class="sxs-lookup"><span data-stu-id="f8638-113">'%s' is not configured as a Distributor.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f8638-114">Explication</span><span class="sxs-lookup"><span data-stu-id="f8638-114">Explanation</span></span>  
 <span data-ttu-id="f8638-115">Si le message d'erreur spécifie une instance particulière autre que 'null', l'instance spécifiée n'a pas été correctement configurée pour être reconnue comme serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="f8638-115">If the error message specifies a particular instance, rather than 'null', the instance specified has not been properly configured to be recognized as a Distributor.</span></span>  
  
 <span data-ttu-id="f8638-116">Si le message spécifie 'null' comme serveur de distribution, il n'y a pas d'entrée pour le serveur local dans la base de données **master** , ou bien l'entrée est incorrecte (peut-être parce que l'ordinateur a été renommé).</span><span class="sxs-lookup"><span data-stu-id="f8638-116">If the message specifies 'null' as a Distributor, there is no entry for the local server in **master** database, or the entry is incorrect (perhaps because the computer was renamed).</span></span> <span data-ttu-id="f8638-117">La réplication requiert que tous les serveurs d'une topologie soient enregistrés avec le nom d'ordinateur et un nom d'instance facultatif (dans le cas d'une instance cluster, le nom du serveur virtuel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec le nom d'instance facultatif).</span><span class="sxs-lookup"><span data-stu-id="f8638-117">Replication expects all servers in a topology to be registered using the computer name with an optional instance name (in the case of a clustered instance, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] virtual server name with the optional instance name).</span></span> <span data-ttu-id="f8638-118">Pour que la réplication fonctionne correctement, la valeur renvoyée par `SELECT @@SERVERNAME` pour chaque serveur de la topologie doit correspondre au nom d'ordinateur ou au nom de serveur virtuel avec le nom d'instance facultatif.</span><span class="sxs-lookup"><span data-stu-id="f8638-118">For replication to function properly, the value returned by `SELECT @@SERVERNAME` for each server in the topology should match the computer name or virtual server name with the optional instance name.</span></span>  
  
 <span data-ttu-id="f8638-119">La réplication n'est pas prise en charge si vous avez inscrit une des instances [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] par adresse IP ou par nom de domaine pleinement qualifié (FQDN).</span><span class="sxs-lookup"><span data-stu-id="f8638-119">Replication is not supported if you have registered any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances by IP address or by Fully Qualified Domain Name (FQDN).</span></span> <span data-ttu-id="f8638-120">Si vous aviez une des instances [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] inscrites par adresse IP ou par nom de domaine pleinement qualifié dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] quand vous avez configuré la réplication, cette erreur a pu se produire.</span><span class="sxs-lookup"><span data-stu-id="f8638-120">If you had any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances registered by IP address or by FQDN in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] when you configured replication, this error could be raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f8638-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="f8638-121">User Action</span></span>  
 <span data-ttu-id="f8638-122">Si le message d'erreur spécifie une instance particulière, configurez le serveur comme serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="f8638-122">If the error message specifies a particular instance, configure the server as a Distributor.</span></span> <span data-ttu-id="f8638-123">Pour plus d'informations, voir [Configure Distribution](configure-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="f8638-123">For more information, see [Configure Distribution](configure-distribution.md).</span></span>  
  
 <span data-ttu-id="f8638-124">Si le message d'erreur ne spécifie pas d'instance particulière ('null'), vérifiez que l'instance du serveur de distribution est inscrit correctement.</span><span class="sxs-lookup"><span data-stu-id="f8638-124">If the message does not specify a particular instance ('null'), verify that the Distributor instance is registered properly.</span></span> <span data-ttu-id="f8638-125">Si le nom réseau de l'ordinateur et le nom de l'instance SQL Server diffèrent, effectuez une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="f8638-125">If the network name of the computer and the name of the SQL Server instance differ, either:</span></span>  
  
-   <span data-ttu-id="f8638-126">Ajoutez le nom de l'instance SQL Server comme nom réseau valide.</span><span class="sxs-lookup"><span data-stu-id="f8638-126">Add the SQL Server instance name as a valid network name.</span></span> <span data-ttu-id="f8638-127">Pour définir un autre nom réseau, une méthode possible consiste à l'ajouter au fichier hosts local.</span><span class="sxs-lookup"><span data-stu-id="f8638-127">One method to set an alternative network name is to add it to the local hosts file.</span></span> <span data-ttu-id="f8638-128">Le fichier hosts local est installé par défaut dans le répertoire WINDOWS\system32\drivers\etc ou WINNT\system32\drivers\etc. Pour plus d'informations, reportez-vous à la documentation Windows.</span><span class="sxs-lookup"><span data-stu-id="f8638-128">The local hosts file is located by default at WINDOWS\system32\drivers\etc or WINNT\system32\drivers\etc. For more information, see the Windows documentation.</span></span>  
  
     <span data-ttu-id="f8638-129">Si, par exemple, le nom d'ordinateur est comp1, l'adresse IP de l'ordinateur 10.193.17.129 et le nom de l'instance inst1/nominst, ajoutez l'entrée suivante au fichier des hôtes :</span><span class="sxs-lookup"><span data-stu-id="f8638-129">For example, if the computer name is comp1 and the computer has an IP address of 10.193.17.129, and the instance name is inst1/instname, add the following entry to the hosts file:</span></span>  
  
     <span data-ttu-id="f8638-130">10.193.17.129 inst1</span><span class="sxs-lookup"><span data-stu-id="f8638-130">10.193.17.129 inst1</span></span>  
  
-   <span data-ttu-id="f8638-131">Désactivez la distribution, inscrivez l'instance puis réactivez la distribution.</span><span class="sxs-lookup"><span data-stu-id="f8638-131">Disable distribution, register the instance, and then reestablish distribution.</span></span> <span data-ttu-id="f8638-132">Si la valeur de @@SERVERNAME n’est pas correcte pour une instance non-cluster, effectuez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="f8638-132">If the value of @@SERVERNAME is not correct for a nonclustered instance, follow these steps:</span></span>  
  
    ```  
    sp_dropserver '<old_name>', 'droplogins'  
    go  
    sp_addserver '<new_name>', 'local'  
    go  
    ```  
  
     <span data-ttu-id="f8638-133">Après avoir exécuté la procédure stockée [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql), vous devez redémarrer le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour que la modification apportée à @@SERVERNAME soit prise en compte.</span><span class="sxs-lookup"><span data-stu-id="f8638-133">After you execute the [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql) stored procedure, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service for the change to @@SERVERNAME to take effect.</span></span>  
  
     <span data-ttu-id="f8638-134">Si la valeur de @@SERVERNAME n’est pas correcte pour une instance cluster, vous devez changer le nom à l’aide de l’administrateur de cluster.</span><span class="sxs-lookup"><span data-stu-id="f8638-134">If the value of @@SERVERNAME is not correct for a clustered instance, you must change the name using Cluster Administrator.</span></span> <span data-ttu-id="f8638-135">Pour plus d’informations, consultez [Instances de cluster de basculement AlwaysOn (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f8638-135">For more information, see [AlwaysOn Failover Cluster Instances (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8638-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f8638-136">See Also</span></span>  
 [<span data-ttu-id="f8638-137">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="f8638-137">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
