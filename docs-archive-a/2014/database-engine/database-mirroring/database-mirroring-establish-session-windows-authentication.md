---
title: Établir une session de mise en miroir de bases de données à l’aide de l’authentification Windows (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Windows authentication [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 143c68a5-589f-4e7f-be59-02707e1a430a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f3088333fbfd4babd209df07f8880c838ce626d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601678"
---
# <a name="establish-a-database-mirroring-session-using-windows-authentication-transact-sql"></a><span data-ttu-id="52131-102">Établir une session de mise en miroir de bases de données au moyen de l'authentification Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="52131-102">Establish a Database Mirroring Session Using Windows Authentication (Transact-SQL)</span></span>
    
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="52131-103">Utilisez [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] à la place.</span><span class="sxs-lookup"><span data-stu-id="52131-103">Use [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] instead.</span></span>  
  
 <span data-ttu-id="52131-104">Après avoir préparé la base de données miroir (voir [Préparer une base de données miroir pour la mise en miroir &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md)), vous pouvez établir une session de mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="52131-104">After the mirror database is prepared (see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md)), you can establish a database mirroring session.</span></span> <span data-ttu-id="52131-105">Le principal, le serveur miroir et le serveur témoin doivent être trois instances distinctes, ayant chacune un système d'hébergement qui lui est propre.</span><span class="sxs-lookup"><span data-stu-id="52131-105">The principal, mirror, and witness server instances must be separate server instances, which should be on separate host systems.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="52131-106">Il est recommandé de configurer la mise en miroir de la base de données pendant les heures creuses, car la configuration de la mise en miroir peut avoir une incidence sur les performances.</span><span class="sxs-lookup"><span data-stu-id="52131-106">We recommend that you configure database mirroring during off-peak hours because configuring mirroring can impact performance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="52131-107">Une instance de serveur peut participer à plusieurs sessions simultanées de mise en miroir de bases de données avec des partenaires identiques ou différents.</span><span class="sxs-lookup"><span data-stu-id="52131-107">A given server instance can participate in multiple concurrent database mirroring sessions with the same or different partners.</span></span> <span data-ttu-id="52131-108">Une instance de serveur peut être partenaire dans certaines sessions et témoin dans d'autres.</span><span class="sxs-lookup"><span data-stu-id="52131-108">A server instance can be a partner in some sessions and a witness in other sessions.</span></span> <span data-ttu-id="52131-109">L'instance du serveur miroir doit être en train d'exécuter la même édition de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] comme instance de serveur principal.</span><span class="sxs-lookup"><span data-stu-id="52131-109">The mirror server instance must be running the same edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as the principal server instance.</span></span> <span data-ttu-id="52131-110">La mise en miroir de bases de données n’est pas disponible dans toutes les éditions de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="52131-110">Database mirroring is not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="52131-111">Pour obtenir une liste des fonctionnalités prises en charge par les éditions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="52131-111">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="52131-112">En outre, nous vous conseillons vivement d'exécuter les instances sur des systèmes comparables pouvant gérer des charges de travail identiques.</span><span class="sxs-lookup"><span data-stu-id="52131-112">Also, we strongly recommend that they run on comparable systems that can handle identical workloads.</span></span>  
  
### <a name="to-establish-a-database-mirroring-session"></a><span data-ttu-id="52131-113">Pour établir une session de mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="52131-113">To establish a database mirroring session</span></span>  
  
1.  <span data-ttu-id="52131-114">Création de la base de données miroir</span><span class="sxs-lookup"><span data-stu-id="52131-114">Create the mirror database.</span></span> <span data-ttu-id="52131-115">Pour plus d’informations, consultez [Préparer une base de données miroir pour la mise en miroir &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="52131-115">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="52131-116">Configurez la sécurité sur chaque instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="52131-116">Set up security on each server instance.</span></span>  
  
     <span data-ttu-id="52131-117">Chaque instance de serveur participant à une session de mise en miroir de bases de données requiert un point de terminaison de mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="52131-117">Each server instance in a database mirroring session requires a database mirroring endpoint.</span></span> <span data-ttu-id="52131-118">Si le point de terminaison n'existe pas, vous devez le créer.</span><span class="sxs-lookup"><span data-stu-id="52131-118">If the endpoint does not exist, you must create it.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="52131-119">Le type d'authentification utilisé pour la mise en miroir de la base de données par une instance de serveur est une propriété de son point de terminaison de mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="52131-119">The form of authentication used for database mirroring by a server instance is a property of its database mirroring endpoint.</span></span> <span data-ttu-id="52131-120">Deux types de sécurité de transport sont disponibles pour la mise en miroir de bases de données : l’authentification Windows ou l’authentification basée sur les certificats.</span><span class="sxs-lookup"><span data-stu-id="52131-120">Two types of transport security are available for database mirroring: Windows Authentication or certificate-based authentication.</span></span> <span data-ttu-id="52131-121">Pour plus d’informations, consultez [sécurité de transport pour la mise en miroir de bases de données et groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="52131-121">For more information, see [Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md).</span></span>  
  
     <span data-ttu-id="52131-122">Sur chaque serveur partenaire, assurez-vous de la présence d'un point de terminaison pour la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="52131-122">On each partner server, ensure that an endpoint exists for database mirroring.</span></span> <span data-ttu-id="52131-123">Indépendamment du nombre de sessions de mise en miroir à prendre en charge, l'instance du serveur ne peut avoir qu'un seul point de terminaison de mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="52131-123">Regardless of the number of mirroring sessions to be supported, the server instance can have only one database mirroring endpoint.</span></span> <span data-ttu-id="52131-124">Si vous envisagez d’utiliser cette instance de serveur exclusivement pour les partenaires de sessions de mise en miroir, vous pouvez attribuer le rôle de partenaire au point de terminaison (ROLE **=** PARTNER).</span><span class="sxs-lookup"><span data-stu-id="52131-124">If you intend to use this server instance exclusively for partners in database mirroring sessions, you can assign the role of partner to the endpoint (ROLE**=** PARTNER).</span></span> <span data-ttu-id="52131-125">Si vous comptez aussi utiliser ce serveur comme témoin dans d'autres sessions, attribuez au point de terminaison le rôle ALL.</span><span class="sxs-lookup"><span data-stu-id="52131-125">If you intend also to use this server for the witness in other database mirroring sessions, assign the role of the endpoint as ALL.</span></span>  
  
     <span data-ttu-id="52131-126">Pour exécuter une instruction SET PARTNER, le paramètre STATE des points de terminaison des deux partenaires doit avoir la valeur STARTED.</span><span class="sxs-lookup"><span data-stu-id="52131-126">To execute a SET PARTNER statement, the STATE of the endpoints of both partners must be set to STARTED.</span></span>  
  
     <span data-ttu-id="52131-127">Pour savoir si une instance de serveur dispose d'un point de terminaison de mise en miroir de bases de données et pour connaître son rôle et son état (sur cette instance), utilisez l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante :</span><span class="sxs-lookup"><span data-stu-id="52131-127">To learn whether a server instance has a database mirroring endpoint and to learn its role and state, on that instance, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    SELECT role_desc, state_desc FROM sys.database_mirroring_endpoints  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="52131-128">Ne reconfigurez pas un point de terminaison de mise en miroir de base de données en cours d'utilisation.</span><span class="sxs-lookup"><span data-stu-id="52131-128">Do not reconfigure an in-use database mirroring endpoint.</span></span> <span data-ttu-id="52131-129">Si le point de terminaison de mise en miroir de base de données existe et est déjà utilisé, nous vous recommandons d'utiliser ce point de terminaison pour toute session établie sur l'instance du serveur.</span><span class="sxs-lookup"><span data-stu-id="52131-129">If a database mirroring endpoint exists and is already in use, we recommend that you use that endpoint for every session on the server instance.</span></span> <span data-ttu-id="52131-130">La suppression d'un point de terminaison en cours d'utilisation peut entraîner son redémarrage et perturber les connexions des sessions existantes, ce qui peut être perçu comme une erreur par les autres instances de serveurs.</span><span class="sxs-lookup"><span data-stu-id="52131-130">Dropping an in-use endpoint can cause the endpoint to restart, disrupting the connections of the existing sessions, which can appear to be an error to the other server instances.</span></span> <span data-ttu-id="52131-131">Cela est particulièrement important en mode haute sécurité avec basculement automatique, où la reconfiguration d'un point de terminaison sur un partenaire peut déclencher un basculement.</span><span class="sxs-lookup"><span data-stu-id="52131-131">This is particularly important in high-safety mode with automatic failover, in which reconfiguring the endpoint on a partner could cause a failover to occur.</span></span> <span data-ttu-id="52131-132">Par ailleurs, si un témoin a été défini pour une session, la suppression du point de terminaison de la mise en miroir de bases de données peut provoquer la perte du quorum par le serveur principal de cette session ; si cela se produit, la base de données est mise en mode hors connexion et ses utilisateurs sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="52131-132">Also, if a witness has been set for a session, dropping the database mirroring endpoint can cause the principal server of that session to lose quorum; if that occurs, the database is taken offline and its users are disconnected.</span></span> <span data-ttu-id="52131-133">Pour plus d’informations, consultez [Quorum : effets d’un témoin sur la disponibilité de la base de données &#40;Mise en miroir de bases de données&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="52131-133">For more information, see [Quorum: How a Witness Affects Database Availability &#40;Database Mirroring&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="52131-134">Si l’un ou l’autre partenaire ne dispose pas d’un point de terminaison, consultez [Créer un point de terminaison de mise en miroir de bases de données pour l’authentification Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="52131-134">If either partner lacks an endpoint, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
3.  <span data-ttu-id="52131-135">Si des instances de serveurs s'exécutent sous différents comptes d'utilisateurs de domaine, chaque instance requiert une connexion à la base de données **master** de toutes les autres.</span><span class="sxs-lookup"><span data-stu-id="52131-135">If server instances are running under different domain user accounts, each requires a login in the **master** database of the others.</span></span> <span data-ttu-id="52131-136">Si la connexion n'existe pas, vous devez la créer.</span><span class="sxs-lookup"><span data-stu-id="52131-136">If the login does not exist, you must create it.</span></span> <span data-ttu-id="52131-137">Pour plus d’informations, consultez [Autoriser l’accès sur le réseau à un point de terminaison de mise en miroir de bases de données au moyen de l’authentification Windows &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="52131-137">For more information, see [Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span></span>  
  
4.  <span data-ttu-id="52131-138">Pour définir le serveur principal comme partenaire sur la base de données miroir, connectez-vous au serveur miroir et exécutez l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="52131-138">To set the principal server as partner on the mirror database, connect to the mirror server, and issue the following statement:</span></span>  
  
     <span data-ttu-id="52131-139">ALTER DATABASE *<nom_base_de_données>* SET PARTNER **=**_<adresse_réseau_serveur>_</span><span class="sxs-lookup"><span data-stu-id="52131-139">ALTER DATABASE *<database_name>* SET PARTNER **=**_<server_network_address>_</span></span>  
  
     <span data-ttu-id="52131-140">où *<nom_base_de_données>* correspond au nom de la base de données à mettre en miroir (ce nom est identique sur les deux partenaires) et *<adresse_réseau_serveur>* est l’adresse réseau du serveur principal.</span><span class="sxs-lookup"><span data-stu-id="52131-140">where *<database_name>* is the name of the database to be mirrored (this name is the same on both partners), and *<server_network_address>* is the server network address of the principal server.</span></span>  
  
     <span data-ttu-id="52131-141">La syntaxe pour une adresse réseau de serveur est la suivante :</span><span class="sxs-lookup"><span data-stu-id="52131-141">The syntax for a server network address is as follows:</span></span>  
  
     <span data-ttu-id="52131-142">TCP<strong>://</strong> \<*system-address> \*<strong>:</strong> \<*port> \*</span><span class="sxs-lookup"><span data-stu-id="52131-142">TCP<strong>://</strong>\<*system-address>*<strong>:</strong>\<*port>*</span></span>  
  
     <span data-ttu-id="52131-143">où \<*system-address>\* est une chaîne qui identifie de façon non ambiguë l’ordinateur de destination, et \<*port>\* le numéro de port utilisé par le point de terminaison de mise en miroir de l’instance de serveur partenaire.</span><span class="sxs-lookup"><span data-stu-id="52131-143">where \<*system-address>\* is a string that unambiguously identifies the destination computer system, and \<*port>\* is the port number used by the mirroring endpoint of the partner server instance.</span></span> <span data-ttu-id="52131-144">Pour plus d’informations, consultez [Spécifier une adresse réseau de serveur &#40;mise en miroir de bases de données&#41;](specify-a-server-network-address-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="52131-144">For more information, see [Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="52131-145">Par exemple, sur l'instance de serveur miroir, l'instruction ALTER DATABASE suivante définit le partenaire comme instance de serveur principal d'origine.</span><span class="sxs-lookup"><span data-stu-id="52131-145">For example, on the mirror server instance, the following ALTER DATABASE statement sets the partner as the original principal server instance.</span></span> <span data-ttu-id="52131-146">Le nom de la base de données est **AdventureWorks**, l’adresse système est DBSERVER1 (nom du système du partenaire) et le port utilisé par le point de terminaison de la mise en miroir de la base de données du partenaire est 7022 :</span><span class="sxs-lookup"><span data-stu-id="52131-146">The database name is **AdventureWorks**, the system address is DBSERVER1-the name of the partner's system-and the port used by the partner's database mirroring endpoint is 7022:</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
       SET PARTNER = 'TCP://DBSERVER1:7022'  
    ```  
  
     <span data-ttu-id="52131-147">Cette instruction prépare le serveur miroir à former une session lorsqu'il sera contacté par le serveur principal.</span><span class="sxs-lookup"><span data-stu-id="52131-147">This statement prepares the mirror server to form a session when it is contacted by the principal server.</span></span>  
  
5.  <span data-ttu-id="52131-148">Pour définir le serveur miroir comme partenaire sur la base de données principale, connectez-vous au serveur principal et exécutez l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="52131-148">To set the mirror server as partner on the principal database, connect to the principal server, and issue the following statement:</span></span>  
  
     <span data-ttu-id="52131-149">ALTER DATABASE *<nom_base_de_données>* SET PARTNER **=**_<adresse_réseau_serveur>_</span><span class="sxs-lookup"><span data-stu-id="52131-149">ALTER DATABASE *<database_name>* SET PARTNER **=**_<server_network_address>_</span></span>  
  
     <span data-ttu-id="52131-150">Pour plus d'informations, consultez l'étape 4.</span><span class="sxs-lookup"><span data-stu-id="52131-150">For more information, see step 4.</span></span>  
  
     <span data-ttu-id="52131-151">Par exemple, sur l'instance de serveur principal, l'instruction ALTER DATABASE suivante définit le partenaire comme instance de serveur miroir d'origine.</span><span class="sxs-lookup"><span data-stu-id="52131-151">For example, on the principal server instance, the following ALTER DATABASE statement sets the partner as the original mirror server instance.</span></span> <span data-ttu-id="52131-152">Le nom de la base de données est **AdventureWorks**, l’adresse système est DBSERVER2 (nom du système du partenaire) et le port utilisé par le point de terminaison de la mise en miroir de la base de données du partenaire est 7025 :</span><span class="sxs-lookup"><span data-stu-id="52131-152">The database name is **AdventureWorks**, the system address is DBSERVER2-the name of the partner's system-and the port used by the partner's database mirroring endpoint is 7025:</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks SET PARTNER = 'TCP://DBSERVER2:7022'  
    ```  
  
     <span data-ttu-id="52131-153">La saisie de cette instruction sur le serveur principal démarre la session de mise en miroir des bases de données.</span><span class="sxs-lookup"><span data-stu-id="52131-153">Entering this statement on the principal server begins the database mirroring session.</span></span>  
  
6.  <span data-ttu-id="52131-154">Par défaut, les sessions sont définies sur une sécurité des transactions totale (valeur de SAFETY définie sur FULL), la session est donc démarrée en mode haute sécurité sans basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="52131-154">By default a session is set to full transaction safety (SAFETY is set to FULL), which starts the session in synchronous, high-safety mode without automatic failover.</span></span> <span data-ttu-id="52131-155">Pour reconfigurer la session pour qu'elle s'exécute en mode haute sécurité avec basculement automatique ou en mode haute performance asynchrone, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="52131-155">You can reconfigure the session to run in high-safety mode with automatic failover or in asynchronous, high-performance mode, as follows:</span></span>  
  
    -   <span data-ttu-id="52131-156">**Mode haute sécurité avec basculement automatique**</span><span class="sxs-lookup"><span data-stu-id="52131-156">**High-safety mode with automatic failover**</span></span>  
  
         <span data-ttu-id="52131-157">Si vous souhaitez qu'une session en mode haute sécurité prenne en charge le basculement automatique, ajoutez une instance de serveur témoin.</span><span class="sxs-lookup"><span data-stu-id="52131-157">If you want a high-safety mode session to support automatic failover, add a witness server instance.</span></span> <span data-ttu-id="52131-158">Pour plus d’informations, consultez [Ajouter un témoin de mise en miroir de bases de données à l’aide de l’authentification Windows &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="52131-158">For more information, see [Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span></span>  
  
    -   <span data-ttu-id="52131-159">**Mode hautes performances**</span><span class="sxs-lookup"><span data-stu-id="52131-159">**High-performance mode**</span></span>  
  
         <span data-ttu-id="52131-160">Si vous ne voulez pas utiliser le basculement automatique et si vous préférez privilégier les performances par rapport à la disponibilité, désactivez la sécurité des transactions.</span><span class="sxs-lookup"><span data-stu-id="52131-160">Alternatively, if you do not want automatic failover and you prefer to emphasize performance over availability, turn off transaction safety.</span></span> <span data-ttu-id="52131-161">Pour plus d’informations, consultez [Modifier la sécurité des transactions dans une session de mise en miroir de bases de données &#40;Transact-SQL&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="52131-161">For more information, see [Change Transaction Safety in a Database Mirroring Session &#40;Transact-SQL&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md).</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="52131-162">En mode hautes performances, la valeur de WITNESS doit être définie sur OFF.</span><span class="sxs-lookup"><span data-stu-id="52131-162">In high-performance mode, WITNESS should be set to OFF.</span></span> <span data-ttu-id="52131-163">Pour plus d’informations, consultez [Quorum : effets d’un témoin sur la disponibilité de la base de données &#40;Mise en miroir de bases de données&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="52131-163">For more information, see [Quorum: How a Witness Affects Database Availability &#40;Database Mirroring&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="52131-164">Exemple</span><span class="sxs-lookup"><span data-stu-id="52131-164">Example</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="52131-165">L'exemple suivant établit une session de mise en miroir de base de données entre partenaires d'une base de données miroir existante.</span><span class="sxs-lookup"><span data-stu-id="52131-165">The following example establishes a database mirroring session between partners for an existing mirror database.</span></span> <span data-ttu-id="52131-166">Pour plus d’informations sur la création d’une base de données miroir, consultez [Préparer une base de données miroir pour la mise en miroir &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="52131-166">For information on creating a mirror database, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md)=.</span></span>  
  
 <span data-ttu-id="52131-167">L'exemple montre les étapes de base à suivre pour créer une session de mise en miroir de bases de données sans témoin.</span><span class="sxs-lookup"><span data-stu-id="52131-167">The example shows the basic steps for creating a database mirroring session without a witness.</span></span> <span data-ttu-id="52131-168">Les deux partenaires sont les instances de serveur par défaut présentes sur deux systèmes informatiques (PARTNERHOST1 et PARTNERHOST5).</span><span class="sxs-lookup"><span data-stu-id="52131-168">The two partners are the default server instances on two computer systems (PARTNERHOST1 and PARTNERHOST5).</span></span> <span data-ttu-id="52131-169">Ces deux instances partenaires exécutent le même compte d'utilisateur de domaine Windows (MYDOMAIN\dbousername).</span><span class="sxs-lookup"><span data-stu-id="52131-169">The two partner instances run the same Windows domain user account (MYDOMAIN\dbousername).</span></span>  
  
1.  <span data-ttu-id="52131-170">Sur l'instance de serveur principal (instance par défaut sur PARTNERHOST1), créez un point de terminaison qui prend en charge tous les rôles par le biais du port 7022 :</span><span class="sxs-lookup"><span data-stu-id="52131-170">On the principal server instance (default instance on PARTNERHOST1), create an endpoint that supports all roles using port 7022:</span></span>  
  
    ```  
    --create an endpoint for this instance  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO  
    --Partners under same domain user; login already exists in master.  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="52131-171">Pour obtenir un exemple illustrant comment configurer une connexion, consultez [Autoriser l’accès sur le réseau à un point de terminaison de mise en miroir de bases de données au moyen de l’authentification Windows &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="52131-171">For an example of how to setup a login, see [Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span></span>  
  
2.  <span data-ttu-id="52131-172">Sur l'instance de serveur miroir (instance par défaut sur PARTNERHOST5), créez un point de terminaison qui prend en charge tous les rôles par le biais du port 7022 :</span><span class="sxs-lookup"><span data-stu-id="52131-172">On the mirror server instance (default instance on PARTNERHOST5), create an endpoint that supports all roles using port 7022:</span></span>  
  
    ```  
    --create an endpoint for this instance  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO  
    --Partners under same domain user; login already exists in master.  
    ```  
  
3.  <span data-ttu-id="52131-173">Sur l'instance de serveur principal (sur PARTNERHOST1), procédez à la sauvegarde de la base de données :</span><span class="sxs-lookup"><span data-stu-id="52131-173">On the principal server instance (on PARTNERHOST1), back up the database:</span></span>  
  
    ```  
    BACKUP DATABASE AdventureWorks   
        TO DISK = 'C:\AdvWorks_dbmirror.bak'   
        WITH FORMAT  
    GO  
    ```  
  
4.  <span data-ttu-id="52131-174">Sur l'instance de serveur miroir (sur `PARTNERHOST5`), restaurez la base de données :</span><span class="sxs-lookup"><span data-stu-id="52131-174">On the mirror server instance (on `PARTNERHOST5`), restore the database:</span></span>  
  
    ```  
    RESTORE DATABASE AdventureWorks   
        FROM DISK = 'Z:\AdvWorks_dbmirror.bak'   
        WITH NORECOVERY  
    GO  
    ```  
  
5.  <span data-ttu-id="52131-175">Après avoir créé la sauvegarde complète de base de données, vous devez créer une sauvegarde du journal sur la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="52131-175">After you create the full database backup, you must create a log backup on the principal database.</span></span> <span data-ttu-id="52131-176">Par exemple, l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante sauvegarde le journal dans le même fichier utilisé par la sauvegarde de base de données antérieure :</span><span class="sxs-lookup"><span data-stu-id="52131-176">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement backs up the log to the same file used by the preceding database backup:</span></span>  
  
    ```  
    BACKUP LOG AdventureWorks   
        TO DISK = 'C:\AdventureWorks.bak'   
    GO  
    ```  
  
6.  <span data-ttu-id="52131-177">Avant de démarrer la mise en miroir, vous devez appliquer la sauvegarde du journal requise (et toutes les sauvegardes de journal ultérieures).</span><span class="sxs-lookup"><span data-stu-id="52131-177">Before you can start mirroring, you must apply the required log backup (and any subsequent log backups).</span></span>  
  
     <span data-ttu-id="52131-178">Par exemple, l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante restaure le premier journal à partir de C:\AdventureWorks.bak :</span><span class="sxs-lookup"><span data-stu-id="52131-178">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement restores the first log from C:\AdventureWorks.bak:</span></span>  
  
    ```  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\ AdventureWorks.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
7.  <span data-ttu-id="52131-179">Sur l'instance de serveur miroir, définissez l'instance de serveur sur PARTNERHOST1 comme étant le partenaire (ce qui en fait le serveur principal initial) :</span><span class="sxs-lookup"><span data-stu-id="52131-179">On the mirror server instance, set the server instance on PARTNERHOST1 as the partner (making it the initial principal server):</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks   
        SET PARTNER =   
        'TCP://PARTNERHOST1:7022'  
    GO  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="52131-180">Une session de mise en miroir de bases de données s'exécute par défaut en mode synchrone, ce qui dépend de la sécurité des transactions totale (SAFETY défini sur FULL).</span><span class="sxs-lookup"><span data-stu-id="52131-180">default, a database mirroring session runs in synchronous mode, which depends on having full transaction safety (SAFETY is set to FULL).</span></span> <span data-ttu-id="52131-181">Pour qu'une session s'exécute en mode hautes performances asynchrone, définissez SAFETY sur OFF.</span><span class="sxs-lookup"><span data-stu-id="52131-181">To cause a session to run in asynchronous, high-performance mode, set SAFETY to OFF.</span></span> <span data-ttu-id="52131-182">Pour plus d'informations, voir [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span><span class="sxs-lookup"><span data-stu-id="52131-182">For more information, see [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span></span>  
  
8.  <span data-ttu-id="52131-183">Dans l'instance de serveur principal, définissez l'instance de serveur sur `PARTNERHOST5` comme étant le partenaire (ce qui en fait le serveur miroir initial) :</span><span class="sxs-lookup"><span data-stu-id="52131-183">On the principal server instance, set the server instance on `PARTNERHOST5` as the partner (making it the initial mirror server):</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://PARTNERHOST5:7022'  
    GO  
    ```  
  
9. <span data-ttu-id="52131-184">Si vous avez l'intention d'utiliser le mode haute sécurité avec basculement automatique, vous pouvez éventuellement définir l'instance de serveur témoin.</span><span class="sxs-lookup"><span data-stu-id="52131-184">Optionally, if you intend to use high-safety mode with automatic failover, set up the witness server instance.</span></span> <span data-ttu-id="52131-185">Pour plus d’informations, consultez [Ajouter un témoin de mise en miroir de bases de données à l’aide de l’authentification Windows &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="52131-185">For more information, see [Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="52131-186">Pour voir un exemple illustrant la configuration de la sécurité, la préparation de la base de données miroir, la définition des serveurs partenaires et l’ajout d’un témoin, consultez [Configuration de la mise en miroir d’une base de données &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="52131-186">For a complete example showing security setup, preparing the mirror database, setting up the partners, and adding a witness, see [Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52131-187">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="52131-187">See Also</span></span>  
 <span data-ttu-id="52131-188">[Configuration de la mise en miroir d’une base de données &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="52131-188">[Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="52131-189">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="52131-189">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="52131-190">[Autoriser l’accès sur le réseau à un point de terminaison de mise en miroir de bases de données au moyen de l’authentification Windows &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="52131-190">[Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md) </span></span>  
 <span data-ttu-id="52131-191">[Préparer une base de données miroir pour la mise en miroir &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="52131-191">[Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="52131-192">[Créer un point de terminaison de mise en miroir de bases de données pour l’authentification Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="52131-192">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="52131-193">[Mise en miroir de bases de données et copie des journaux de transaction &#40;SQL Server&#41;](database-mirroring-and-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="52131-193">[Database Mirroring and Log Shipping &#40;SQL Server&#41;](database-mirroring-and-log-shipping-sql-server.md) </span></span>  
 <span data-ttu-id="52131-194">[Mise en miroir de bases de données &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="52131-194">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="52131-195">[Mise en miroir de bases de données et réplication &#40;SQL Server&#41;](database-mirroring-and-replication-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="52131-195">[Database Mirroring and Replication &#40;SQL Server&#41;](database-mirroring-and-replication-sql-server.md) </span></span>  
 <span data-ttu-id="52131-196">[Configuration de la mise en miroir d’une base de données &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="52131-196">[Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="52131-197">[Spécifier une adresse réseau de serveur &#40;mise en miroir de bases de données&#41;](specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="52131-197">[Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md) </span></span>  
 [<span data-ttu-id="52131-198">Modes de fonctionnement de la mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="52131-198">Database Mirroring Operating Modes</span></span>](database-mirroring-operating-modes.md)  
  
  
