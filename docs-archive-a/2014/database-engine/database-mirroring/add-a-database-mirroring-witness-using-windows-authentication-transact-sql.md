---
title: Ajouter un témoin de mise en miroir de bases de données à l’aide de l’authentification Windows (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- witness [SQL Server], establishing
- Windows authentication [SQL Server]
- database mirroring [SQL Server], witness
ms.assetid: bf5e87df-91a4-49f9-ae88-2a6dcf644510
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 88684c3a1ca12ea579859759ed804ca281647fa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603038"
---
# <a name="add-a-database-mirroring-witness-using-windows-authentication-transact-sql"></a><span data-ttu-id="8dc70-102">Ajouter un témoin de mise en miroir de bases de données à l'aide de l'authentification Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8dc70-102">Add a Database Mirroring Witness Using Windows Authentication (Transact-SQL)</span></span>
  <span data-ttu-id="8dc70-103">Pour configurer un témoin pour une base de données, le propriétaire de la base de données attribue à une instance de moteur de base de données le rôle de serveur témoin.</span><span class="sxs-lookup"><span data-stu-id="8dc70-103">To set up a witness for a database, the database owner assigns a Database Engine instance to the role of witness server.</span></span> <span data-ttu-id="8dc70-104">L'instance de serveur témoin peut être exécutée sur le même ordinateur que l'instance de serveur principal ou miroir, mais cela réduit alors considérablement la robustesse du basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="8dc70-104">The witness server instance can run on the same computer as the principal or mirror server instance, but this substantially reduces the robustness of automatic failover.</span></span>  
  
 <span data-ttu-id="8dc70-105">Nous vous recommandons fortement de faire résider le témoin sur un ordinateur séparé.</span><span class="sxs-lookup"><span data-stu-id="8dc70-105">We strongly recommend that the witness reside on a separate computer.</span></span> <span data-ttu-id="8dc70-106">Un serveur donné peut participer à plusieurs sessions simultanées de mise en miroir de bases de données avec des partenaires identiques ou différents.</span><span class="sxs-lookup"><span data-stu-id="8dc70-106">A given server can participate in multiple concurrent database mirroring sessions with the same or different partners.</span></span> <span data-ttu-id="8dc70-107">Un serveur donné peut être partenaire dans certaines sessions et témoin dans d'autres.</span><span class="sxs-lookup"><span data-stu-id="8dc70-107">A given server can be a partner in some sessions and a witness in other sessions.</span></span>  
  
 <span data-ttu-id="8dc70-108">Le témoin est destiné uniquement au mode haute sécurité avec basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="8dc70-108">The witness is intended exclusively for high-safety mode with automatic failover.</span></span> <span data-ttu-id="8dc70-109">Avant de définir un témoin, nous vous recommandons fortement de vérifier que la propriété SAFETY a la valeur active FULL.</span><span class="sxs-lookup"><span data-stu-id="8dc70-109">Before you set a witness, we strongly recommend that you ensure that the SAFETY property is currently set to FULL.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8dc70-110">Nous vous recommandons de configurer la mise en miroir de bases de données durant les heures creuses, car cela peut affecter les performances.</span><span class="sxs-lookup"><span data-stu-id="8dc70-110">We recommend that you configure database mirroring during off-peak hours because configuration can impact performance.</span></span>  
  
### <a name="to-establish-a-witness"></a><span data-ttu-id="8dc70-111">Pour établir un témoin</span><span class="sxs-lookup"><span data-stu-id="8dc70-111">To establish a witness</span></span>  
  
1.  <span data-ttu-id="8dc70-112">Sur l'instance de serveur témoin, assurez-vous qu'un point de terminaison existe pour la mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="8dc70-112">On the witness server instance, ensure that an endpoint exists for database mirroring.</span></span> <span data-ttu-id="8dc70-113">Quel que soit le nombre de sessions de mise en miroir à prendre en charge, l'instance de serveur ne doit disposer que d'un seul point de terminaison de mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="8dc70-113">Regardless of the number of mirroring session to be supported, the server instance must have only one database mirroring endpoint.</span></span> <span data-ttu-id="8dc70-114">Si vous envisagez d’utiliser cette instance de serveur exclusivement comme témoin dans les sessions de mise en miroir de bases de données, attribuez le rôle de témoin au point de terminaison (témoin de rôle **=** ).</span><span class="sxs-lookup"><span data-stu-id="8dc70-114">If you intend to use this server instance exclusively as a witness in database mirroring sessions, assign the role of witness to the endpoint (ROLE **=** WITNESS).</span></span> <span data-ttu-id="8dc70-115">Si vous souhaitez utiliser cette instance de serveur comme partenaire dans une ou plusieurs sessions de mise en miroir de bases de données, attribuez le rôle ALL au point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="8dc70-115">If you intend to use this server instance as a partner in one or more other database mirroring sessions, assign the role of the endpoint as ALL.</span></span>  
  
     <span data-ttu-id="8dc70-116">Pour exécuter une instruction SET WITNESS, la session de mise en miroir de bases de données doit déjà être démarrée (entre les partenaires) et la valeur STATE du point de terminaison du témoin doit être STARTED.</span><span class="sxs-lookup"><span data-stu-id="8dc70-116">To execute a SET WITNESS statement, the database mirroring session must already be started (between the partners), and the STATE of the endpoint of the witness must be set to STARTED.</span></span>  
  
     <span data-ttu-id="8dc70-117">Pour savoir si l'instance de serveur témoin possède son point de terminaison de mise en miroir de bases de données et pour connaître son rôle et son état, utilisez sur cette instance l'instruction Transact-SQL suivante :</span><span class="sxs-lookup"><span data-stu-id="8dc70-117">To learn whether the witness server instance has its database mirroring endpoint and to learn its role and state, on that instance, use the following Transact-SQL statement:</span></span>  
  
    ```  
    SELECT role_desc, state_desc FROM sys.database_mirroring_endpoints  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="8dc70-118">Si le point de terminaison de mise en miroir de base de données existe et est déjà utilisé, nous vous recommandons d'utiliser ce point de terminaison pour toute session établie sur l'instance du serveur.</span><span class="sxs-lookup"><span data-stu-id="8dc70-118">If a database mirroring endpoint exists and is already in use, we recommend that you use that endpoint for every session on the server instance.</span></span> <span data-ttu-id="8dc70-119">La suppression d'un point de terminaison en cours d'utilisation perturbe les connexions des sessions existantes.</span><span class="sxs-lookup"><span data-stu-id="8dc70-119">Dropping an in-use endpoint disrupts the connections of the existing sessions.</span></span> <span data-ttu-id="8dc70-120">Si un témoin a été défini pour une session, la suppression du point de terminaison de la mise en miroir peut provoquer la perte du quorum par le serveur principal de cette session ; si cela se produit, la base de données est mise en mode hors connexion et ses utilisateurs sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="8dc70-120">If a witness has been set for a session, dropping the database mirroring endpoint can cause the principal server of that session to lose quorum; if that occurs, the database is taken offline and its users are disconnected.</span></span> <span data-ttu-id="8dc70-121">Pour plus d’informations, consultez [Quorum : effets d’un témoin sur la disponibilité de la base de données &#40;Mise en miroir de bases de données&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="8dc70-121">For more information, see [Quorum: How a Witness Affects Database Availability &#40;Database Mirroring&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="8dc70-122">Si le témoin ne dispose pas d’un point de terminaison, consultez [Créer un point de terminaison de mise en miroir de bases de données pour l’authentification Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="8dc70-122">If the witness lacks an endpoint, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
2.  <span data-ttu-id="8dc70-123">Si les instances partenaires s'exécutent sous différents comptes d'utilisateurs de domaine, créez une connexion pour ces différents comptes dans la base de données master de chaque instance.</span><span class="sxs-lookup"><span data-stu-id="8dc70-123">If the partner instances are running under different domain user accounts, create a login for the different accounts in the master database of each instance.</span></span> <span data-ttu-id="8dc70-124">Pour plus d’informations, consultez [Autoriser l’accès sur le réseau à un point de terminaison de mise en miroir de bases de données au moyen de l’authentification Windows &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="8dc70-124">For more information, see [Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span></span>  
  
3.  <span data-ttu-id="8dc70-125">Connectez-vous au serveur principal et exécutez l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="8dc70-125">Connect to the principal server and issue the following statement:</span></span>  
  
     <span data-ttu-id="8dc70-126">ALTER DATABASE *<database_name>* témoin **=** _<server_network_address_></span><span class="sxs-lookup"><span data-stu-id="8dc70-126">ALTER DATABASE *<database_name>* SET WITNESS **=** _<server_network_address>_</span></span>  
  
     <span data-ttu-id="8dc70-127">où *<nom_base_de_données>* est le nom de la base de données à mettre en miroir (ce nom est identique sur les deux partenaires) et *<adresse_réseau_serveur>* est l’adresse réseau du serveur de l’instance de serveur témoin.</span><span class="sxs-lookup"><span data-stu-id="8dc70-127">where *<database_name>* is the name of the database to be mirrored (this name is the same on both partners), and *<server_network_address>* is the server network address of the witness server instance.</span></span>  
  
     <span data-ttu-id="8dc70-128">La syntaxe pour une adresse réseau de serveur est la suivante :</span><span class="sxs-lookup"><span data-stu-id="8dc70-128">The syntax for a server network address is as follows:</span></span>  
  
     <span data-ttu-id="8dc70-129">TCP **://** \<_system-address> _**:**\<*port>\*</span><span class="sxs-lookup"><span data-stu-id="8dc70-129">TCP **://**\<_system-address>_**:**\<*port>\*</span></span>  
  
     <span data-ttu-id="8dc70-130">où \<*system-address>\* est une chaîne qui identifie de façon non ambiguë l’ordinateur de destination, et \<*port>\* le numéro de port utilisé par le point de terminaison de mise en miroir de l’instance de serveur partenaire.</span><span class="sxs-lookup"><span data-stu-id="8dc70-130">where \<*system-address>\* is a string that unambiguously identifies the destination computer system, and \<*port>\* is the port number used by the mirroring endpoint of the partner server instance.</span></span> <span data-ttu-id="8dc70-131">Pour plus d’informations, consultez [Spécifier une adresse réseau de serveur &#40;mise en miroir de bases de données&#41;](specify-a-server-network-address-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="8dc70-131">For more information, see [Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="8dc70-132">Ainsi, sur l'instance de serveur principal, l'instruction ALTER DATABASE suivante définit le témoin.</span><span class="sxs-lookup"><span data-stu-id="8dc70-132">For example, on the principal server instance, the following ALTER DATABASE statement sets the witness.</span></span> <span data-ttu-id="8dc70-133">Le nom de la base de données est **AdventureWorks**, l’adresse système est DBSERVER3 (nom du système témoin) et le port utilisé par le point de terminaison de mise en miroir de bases de données du témoin est `7022` :</span><span class="sxs-lookup"><span data-stu-id="8dc70-133">The database name is **AdventureWorks**, the system address is DBSERVER3-the name of the witness system, and the port used by the database mirroring endpoint of the witness is `7022`:</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
      SET WITNESS = 'TCP://DBSERVER3:7022'  
    ```  
  
## <a name="example"></a><span data-ttu-id="8dc70-134">Exemple</span><span class="sxs-lookup"><span data-stu-id="8dc70-134">Example</span></span>  
 <span data-ttu-id="8dc70-135">L'exemple suivant installe un témoin de mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="8dc70-135">The following example establishes a data mirroring witness.</span></span> <span data-ttu-id="8dc70-136">Sur l'instance du serveur témoin (instance par défaut sur `WITNESSHOST4`) :</span><span class="sxs-lookup"><span data-stu-id="8dc70-136">On the witness server instance (default instance on `WITNESSHOST4`):</span></span>  
  
1.  <span data-ttu-id="8dc70-137">Créez un point de terminaison pour cette instance de serveur, afin que le rôle WITNESS utilise uniquement le port `7022`.</span><span class="sxs-lookup"><span data-stu-id="8dc70-137">Create an endpoint for this server instance for the WITNESS role only using port `7022`.</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=WITNESS)  
    GO  
    ```  
  
2.  <span data-ttu-id="8dc70-138">Créez une connexion pour les comptes d'utilisateurs de domaine des instances partenaires s'ils sont différents. Supposez, par exemple, que le témoin s'exécute sous `SOMEDOMAIN\witnessuser`tandis que les partenaires s'exécutent sous `MYDOMAIN\dbousername`.</span><span class="sxs-lookup"><span data-stu-id="8dc70-138">Create a login for domain user account of partner instances, if different; for example, assume that the witness is running as `SOMEDOMAIN\witnessuser`, but the partners are running as `MYDOMAIN\dbousername`.</span></span> <span data-ttu-id="8dc70-139">Créez une connexion pour les partenaires comme suit :</span><span class="sxs-lookup"><span data-stu-id="8dc70-139">Create a login for the partners, as follows:</span></span>  
  
    ```  
    --Create a login for the partner server instances,  
    --which are both running as MYDOMAIN\dbousername:  
    USE master ;  
    GO  
    CREATE LOGIN [MYDOMAIN\dbousername] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account   
    --of partners  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [MYDOMAIN\dbousername];  
    GO  
    ```  
  
3.  <span data-ttu-id="8dc70-140">Sur chacune des instances partenaires, créez une connexion pour l'instance de serveur témoin :</span><span class="sxs-lookup"><span data-stu-id="8dc70-140">On each of the partner server instances, create a login for the witness server instance:</span></span>  
  
    ```  
    --Create a login for the witness server instance,  
    --which is running as SOMEDOMAIN\witnessuser:  
    USE master ;  
    GO  
    CREATE LOGIN [SOMEDOMAIN\witnessuser] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account   
    --of partners  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [SOMEDOMAIN\witnessuser];  
    GO  
    ```  
  
4.  <span data-ttu-id="8dc70-141">Sur le serveur principal, définissez le témoin (qui se trouve sur `WITNESSHOST4`) :</span><span class="sxs-lookup"><span data-stu-id="8dc70-141">On the principal server, set the witness (which is on `WITNESSHOST4`):</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET WITNESS =   
        'TCP://WITNESSHOST4:7022'  
    GO  
    ```  
  
> [!NOTE]  
>  <span data-ttu-id="8dc70-142">L'adresse réseau du serveur signale l'instance de serveur cible par son numéro de port qui est mappé avec le point de terminaison mis en miroir de l'instance.</span><span class="sxs-lookup"><span data-stu-id="8dc70-142">The server network address indicates the target server instance by the port number, which maps to the mirroring endpoint of the instance.</span></span>  
  
 <span data-ttu-id="8dc70-143">Pour voir un exemple illustrant la configuration de la sécurité, la préparation de la base de données miroir, la définition des serveurs partenaires et l’ajout d’un témoin, consultez [Configuration de la mise en miroir d’une base de données &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="8dc70-143">For a complete example showing security setup, preparing the mirror database, setting up the partners, and adding a witness, see [Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dc70-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8dc70-144">See Also</span></span>  
 <span data-ttu-id="8dc70-145">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8dc70-145">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="8dc70-146">[Autoriser l’accès sur le réseau à un point de terminaison de mise en miroir de bases de données au moyen de l’authentification Windows &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="8dc70-146">[Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md) </span></span>  
 <span data-ttu-id="8dc70-147">[Créer un point de terminaison de mise en miroir de bases de données pour l’authentification Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="8dc70-147">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="8dc70-148">[Établir une session de mise en miroir de bases de données au moyen de l’authentification Windows &#40;Transact-SQL&#41;](database-mirroring-establish-session-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="8dc70-148">[Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;](database-mirroring-establish-session-windows-authentication.md) </span></span>  
 <span data-ttu-id="8dc70-149">[Supprimer le témoin d’une session de mise en miroir de bases de données &#40;SQL Server&#41;](remove-the-witness-from-a-database-mirroring-session-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8dc70-149">[Remove the Witness from a Database Mirroring Session &#40;SQL Server&#41;](remove-the-witness-from-a-database-mirroring-session-sql-server.md) </span></span>  
 [<span data-ttu-id="8dc70-150">Témoin de mise en miroir de base de données</span><span class="sxs-lookup"><span data-stu-id="8dc70-150">Database Mirroring Witness</span></span>](database-mirroring-witness.md)  
  
  
