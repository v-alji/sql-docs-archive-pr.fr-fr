---
title: MSSQLSERVER_1418 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1418 (Database Engine error)
ms.assetid: 6e9c7241-0201-44e0-9f8b-b3c4e293f0f6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1fcac03f044aacce5e907824862eb589c97a07d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702944"
---
# <a name="mssqlserver_1418"></a><span data-ttu-id="e0d5f-102">MSSQLSERVER_1418</span><span class="sxs-lookup"><span data-stu-id="e0d5f-102">MSSQLSERVER_1418</span></span>
    
## <a name="details"></a><span data-ttu-id="e0d5f-103">Détails</span><span class="sxs-lookup"><span data-stu-id="e0d5f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e0d5f-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="e0d5f-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="e0d5f-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="e0d5f-105">Event ID</span></span>|<span data-ttu-id="e0d5f-106">1418</span><span class="sxs-lookup"><span data-stu-id="e0d5f-106">1418</span></span>|  
|<span data-ttu-id="e0d5f-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="e0d5f-107">Event Source</span></span>|<span data-ttu-id="e0d5f-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e0d5f-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e0d5f-109">Composant</span><span class="sxs-lookup"><span data-stu-id="e0d5f-109">Component</span></span>|<span data-ttu-id="e0d5f-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e0d5f-110">SQLEngine</span></span>|  
|<span data-ttu-id="e0d5f-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="e0d5f-111">Symbolic Name</span></span>|<span data-ttu-id="e0d5f-112">DBM_PARTNERNOTFOUND</span><span class="sxs-lookup"><span data-stu-id="e0d5f-112">DBM_PARTNERNOTFOUND</span></span>|  
|<span data-ttu-id="e0d5f-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="e0d5f-113">Message Text</span></span>|<span data-ttu-id="e0d5f-114">L'adresse réseau du serveur « %.\*ls » est impossible à atteindre ou elle n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-114">The server network address "%.\*ls" can not be reached or does not exist.</span></span> <span data-ttu-id="e0d5f-115">Vérifiez le nom de l'adresse réseau et que les ports des points de terminaison locaux et distants sont opérationnels.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-115">Check the network address name and that the ports for the local and remote endpoints are operational.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e0d5f-116">Explication</span><span class="sxs-lookup"><span data-stu-id="e0d5f-116">Explanation</span></span>  
 <span data-ttu-id="e0d5f-117">Le point de terminaison réseau du serveur n'a pas répondu car l'adresse réseau spécifiée pour le serveur ne peut pas être atteinte ou n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-117">The server network endpoint did not respond because the specified server network address cannot be reached or does not exist.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e0d5f-118">Par défaut, le système d'exploitation de [!INCLUDE[msCoName](../../includes/msconame-md.md)] bloque tous les ports.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-118">By default, [!INCLUDE[msCoName](../../includes/msconame-md.md)] operating system blocks all ports.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e0d5f-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e0d5f-119">User Action</span></span>  
 <span data-ttu-id="e0d5f-120">Vérifiez le nom de l'adresse réseau et exécutez de nouveau la commande.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-120">Verify the network address name and reissue the command.</span></span>  
  
 <span data-ttu-id="e0d5f-121">Il peut être nécessaire d'appliquer des actions correctives sur les deux serveurs partenaires.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-121">Corrective action might be required on both partners.</span></span> <span data-ttu-id="e0d5f-122">Par exemple, si ce message apparaît lorsque vous essayez d'exécuter une instruction SET PARTNER sur l'instance du serveur principal, il peut impliquer que vous ne devez effectuer une action corrective que sur l'instance du serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-122">For example, if this message is raised when you are trying to run SET PARTNER on the principal server instance, the message might imply that you only have to take corrective action on the mirror server instance.</span></span> <span data-ttu-id="e0d5f-123">Toutefois, des actions correctives peuvent être requises sur les deux serveurs partenaires.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-123">However, corrective actions might be required on both partners.</span></span>  
  
### <a name="additional-corrective-actions"></a><span data-ttu-id="e0d5f-124">Actions correctives supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e0d5f-124">Additional Corrective Actions</span></span>  
  
-   <span data-ttu-id="e0d5f-125">Assurez-vous que la base de données miroir est prête pour la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-125">Make sure that the mirror database is ready for mirroring.</span></span>  
  
-   <span data-ttu-id="e0d5f-126">Assurez-vous que le nom et le port de l'instance du serveur miroir sont corrects.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-126">Make sure that the name and port of the mirror server instance are correct.</span></span>  
  
-   <span data-ttu-id="e0d5f-127">Assurez-vous que l'instance du serveur miroir de destination ne se trouve pas derrière un pare-feu.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-127">Make sure that the destination mirror server instance is not behind a firewall.</span></span>  
  
-   <span data-ttu-id="e0d5f-128">Assurez-vous que l'instance du serveur principal ne se trouve pas derrière un pare-feu.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-128">Make sure that the principal server instance is not behind a firewall.</span></span>  
  
-   <span data-ttu-id="e0d5f-129">Vérifiez que les points de terminaison sont démarrés sur les serveurs partenaires à l’aide de la colonne **state** ou **state_desc** de l’affichage catalogue **sys.database_mirroring_endpoints**.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-129">Verify that the endpoints are started on the partners by using the **state** or **state_desc** column the of the **sys.database_mirroring_endpoints** catalog view.</span></span> <span data-ttu-id="e0d5f-130">Si l'un des points de terminaison n'est pas démarré, exécutez une instruction ALTER ENDPOINT pour le démarrer.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-130">If either endpoint is not started, execute an ALTER ENDPOINT statement to start it.</span></span>  
  
-   <span data-ttu-id="e0d5f-131">Assurez-vous que l'instance du serveur principal est à l'écoute sur le port attribué à son point de terminaison de mise en miroir de bases de données et que l'instance du serveur miroir est à l'écoute sur son port.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-131">Make sure that the principal server instance is listening on the port assigned to its database mirroring endpoint and that and the mirror server instance is listening on its port.</span></span> <span data-ttu-id="e0d5f-132">Pour plus d'informations, consultez « Vérification de la disponibilité des ports », plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-132">For more information, see "Verifying Port Availability," later in this topic.</span></span> <span data-ttu-id="e0d5f-133">Si un serveur partenaire n'est pas à l'écoute sur le port qui lui est attribué, modifiez le point de terminaison de mise en miroir de bases de données pour qu'il soit à l'écoute sur un autre port.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-133">If a partner is not listening on its assigned port, modify the database mirroring endpoint to listen on a different port.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e0d5f-134">Une sécurité configurée de manière incorrecte peut générer un message d'erreur général sur la configuration.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-134">Improperly configured security can cause a general setup error message.</span></span> <span data-ttu-id="e0d5f-135">En règle générale, l'instance de serveur supprime la demande de connexion incorrecte sans répondre.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-135">Typically, the server instance drops the bad connection request without responding.</span></span> <span data-ttu-id="e0d5f-136">Pour l'appelant, une erreur de sécurité/configuration peut sembler due à plusieurs autres facteurs : la base de données miroir peut être dans un état incorrect ou peut ne pas exister, les autorisations peuvent être incorrectes, etc.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-136">To the caller, a security-configuration error could appear to have occurred for a variety of other reasons, such as the mirror database in a bad state or does not exist, incorrect permissions, and so on.</span></span>  
  
### <a name="using-the-error-log-file-for-diagnosis"></a><span data-ttu-id="e0d5f-137">Utilisation du fichier journal des erreurs pour le diagnostic</span><span class="sxs-lookup"><span data-stu-id="e0d5f-137">Using the Error Log File for Diagnosis</span></span>  
 <span data-ttu-id="e0d5f-138">Dans certains cas, seuls les fichiers journaux des erreurs sont disponibles pour une analyse approfondie.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-138">In some cases, only error log files are available for investigation.</span></span> <span data-ttu-id="e0d5f-139">Si c'est le cas, déterminez si le journal des erreurs contient le message d'erreur 26023 pour le port TCP du point de terminaison de mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-139">In these cases, determine whether the error log contains error message 26023 for the TCP port of the database mirroring endpoint.</span></span> <span data-ttu-id="e0d5f-140">Cette erreur de niveau de gravité 16 peut indiquer que le point de terminaison de mise en miroir de bases de données n'est pas démarré.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-140">This error, which is severity 16, might indicate that the database mirroring endpoint is not started.</span></span> <span data-ttu-id="e0d5f-141">Ce message peut apparaître même si l’affichage catalogue **sys.database_mirroring_endpoints** indique que le point de terminaison est démarré.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-141">This message can occur even if **sys.database_mirroring_endpoints** shows the endpoint state as started.</span></span>  
  
 <span data-ttu-id="e0d5f-142">Après avoir résolu les problèmes rencontrés, exécutez de nouveau l’instruction ALTER DATABASE *nom_base_de_données* SET PARTNER sur le serveur principal.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-142">After resolving any issues that you encounter, rerun the ALTER DATABASE *database_name* SET PARTNER statement on the principal server.</span></span>  
  
### <a name="verifying-port-availability"></a><span data-ttu-id="e0d5f-143">Vérification de la disponibilité des ports</span><span class="sxs-lookup"><span data-stu-id="e0d5f-143">Verifying Port Availability</span></span>  
 <span data-ttu-id="e0d5f-144">Lors de la configuration du réseau pour une session de mise en miroir de bases de données, assurez-vous que le point de terminaison de mise en miroir de bases de données de chaque instance de serveur est utilisé uniquement par le processus de mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-144">When you are configuring the network for a database mirroring session, make sure the database mirroring endpoint of each server instance is used by only the database mirroring process.</span></span> <span data-ttu-id="e0d5f-145">Si un autre processus est à l'écoute sur le port attribué à un point de terminaison de mise en miroir de bases de données, les processus de mise en miroir de bases de données des autres instances de serveur ne peuvent pas se connecter au point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-145">If another process is listening on the port assigned to a database mirroring endpoint, the database mirroring processes of the other server instances cannot connect to the endpoint.</span></span>  
  
 <span data-ttu-id="e0d5f-146">Pour afficher tous les ports sur lesquels un serveur Windows est à l’écoute, utilisez l’utilitaire d’invite de commandes **netstat**.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-146">To display all the ports on which a Windows-based server is listening, use the **netstat** command-prompt utility.</span></span> <span data-ttu-id="e0d5f-147">La syntaxe à utiliser pour **netstat** dépend de la version du système d’exploitation Windows.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-147">The syntax for **netstat** depends on the version of the Windows operating system.</span></span> <span data-ttu-id="e0d5f-148">Pour plus d'informations, consultez la documentation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-148">For more information, see the operating system documentation.</span></span>  
  
#### <a name="windows-server-2003-service-pack-1-sp1"></a><span data-ttu-id="e0d5f-149">Windows Server 2003 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="e0d5f-149">Windows Server 2003 Service Pack 1 (SP1)</span></span>  
 <span data-ttu-id="e0d5f-150">Pour répertorier les ports d'écoute et les processus pour lesquels ces ports sont ouverts, entrez la commande ci-dessous à l'invite de commandes Windows :</span><span class="sxs-lookup"><span data-stu-id="e0d5f-150">To list listening ports and the processes that have those ports opened, enter the following command at the Windows command prompt:</span></span>  
  
 <span data-ttu-id="e0d5f-151">**netstat -abn**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-151">**netstat -abn**</span></span>  
  
#### <a name="windows-server-2003-pre-sp1"></a><span data-ttu-id="e0d5f-152">Windows Server 2003 (version antérieure à SP1)</span><span class="sxs-lookup"><span data-stu-id="e0d5f-152">Windows Server 2003 (pre-SP1)</span></span>  
 <span data-ttu-id="e0d5f-153">Pour identifier les ports d'écoute et les processus pour lesquels ces ports sont ouverts, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e0d5f-153">To identify the listening ports and the processes that have those ports opened, follow these steps:</span></span>  
  
1.  <span data-ttu-id="e0d5f-154">Obtenez l'ID de processus.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-154">Obtain the process ID.</span></span>  
  
     <span data-ttu-id="e0d5f-155">Pour connaître l'ID de processus d'une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], connectez-vous à cette instance et utilisez l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante :</span><span class="sxs-lookup"><span data-stu-id="e0d5f-155">To learn the process ID of an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], connect to that instance and use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    SELECT SERVERPROPERTY('ProcessID')   
    ```  
  
     <span data-ttu-id="e0d5f-156">Pour plus d'informations, consultez « SERVERPROPERTY (Transact-SQL) » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0d5f-156">For more information, see "SERVERPROPERTY (Transact-SQL)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="e0d5f-157">Mettez en corrélation l’ID de processus avec la sortie de la commande **netstat** suivante :</span><span class="sxs-lookup"><span data-stu-id="e0d5f-157">Match the process ID with the output of the following **netstat** command:</span></span>  
  
     <span data-ttu-id="e0d5f-158">**netstat -ano**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-158">**netstat -ano**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0d5f-159">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e0d5f-159">See Also</span></span>  
 <span data-ttu-id="e0d5f-160">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e0d5f-160">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="e0d5f-161">[Point de terminaison de mise en miroir de bases de données &#40;SQL Server&#41;](../../database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e0d5f-161">[The Database Mirroring Endpoint &#40;SQL Server&#41;](../../database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="e0d5f-162">[Préparer une base de données miroir pour la mise en miroir &#40;SQL Server&#41;](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e0d5f-162">[Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="e0d5f-163">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e0d5f-163">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span></span>  
 <span data-ttu-id="e0d5f-164">[Spécifier une adresse réseau de serveur &#40;mise en miroir de bases de données&#41;](../../database-engine/database-mirroring/specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="e0d5f-164">[Specify a Server Network Address &#40;Database Mirroring&#41;](../../database-engine/database-mirroring/specify-a-server-network-address-database-mirroring.md) </span></span>  
 <span data-ttu-id="e0d5f-165">[sys.database_mirroring_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e0d5f-165">[sys.database_mirroring_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql) </span></span>  
 [<span data-ttu-id="e0d5f-166">Résoudre des problèmes de configuration de mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e0d5f-166">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/troubleshoot-database-mirroring-configuration-sql-server.md)  
  
  
