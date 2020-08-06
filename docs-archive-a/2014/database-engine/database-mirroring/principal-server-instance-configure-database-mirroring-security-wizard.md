---
title: Instance de serveur principal (Configurer l’Assistant Sécurité de mise en miroir de bases de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.principalsrvr.f1
ms.assetid: 58af27d7-c5dd-4669-be6b-b472bc2c8ef4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2632b5ffd5355065b4b5c1f905b3b6e5c5b6204d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701838"
---
# <a name="principal-server-instance-configure-database-mirroring-security-wizard"></a><span data-ttu-id="58bcc-102">Instance de serveur principal (Configurer l'Assistant Sécurité de mise en miroir de bases de données)</span><span class="sxs-lookup"><span data-stu-id="58bcc-102">Principal Server Instance (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="58bcc-103">Cette page vous permet de spécifier des informations sur l'instance de serveur de la base de données principal.</span><span class="sxs-lookup"><span data-stu-id="58bcc-103">Use this page to specify information about the server instance of the principal database.</span></span> <span data-ttu-id="58bcc-104">La base de données principale est la copie de la base de données qui commence la session de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="58bcc-104">The principal database is the copy of the database that begins the mirroring session.</span></span> <span data-ttu-id="58bcc-105">Une fois que la session a commencé, la base de données principale est la copie de la base de données qui accepte les modifications d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="58bcc-105">After the session has begun, the principal database is the copy of the database that accepts user changes.</span></span> <span data-ttu-id="58bcc-106">(Lorsqu'un basculement a lieu, les rôles principal et de mise en miroir sont échangés ; par conséquent, la base de données principale initiale peut ne pas demeurer la base de données principale.)</span><span class="sxs-lookup"><span data-stu-id="58bcc-106">(When a failover occurs, the principal and mirroring roles are swapped; therefore, the initial principal database might not remain the principal database.)</span></span>  
  
 <span data-ttu-id="58bcc-107">**Pour configurer la mise en miroir de bases de données à l'aide de SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="58bcc-107">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="58bcc-108">Établir une session de mise en miroir de bases de données au moyen de l’authentification Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="58bcc-108">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="58bcc-109">Démarrer l’Assistant Configuration de la sécurité de mise en miroir de bases de données &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="58bcc-109">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="58bcc-110">Options</span><span class="sxs-lookup"><span data-stu-id="58bcc-110">Options</span></span>  
 <span data-ttu-id="58bcc-111">**Instance de serveur principal**</span><span class="sxs-lookup"><span data-stu-id="58bcc-111">**Principal server instance**</span></span>  
 <span data-ttu-id="58bcc-112">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , la mise en miroir de base de données est toujours configurée à partir du serveur principal ; c'est pourquoi l'instance de serveur active est toujours l'instance de serveur principal.</span><span class="sxs-lookup"><span data-stu-id="58bcc-112">Because database mirroring in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is always configured from the principal server, the current server instance is always the principal server instance.</span></span>  
  
 <span data-ttu-id="58bcc-113">**Port de l’écouteur**</span><span class="sxs-lookup"><span data-stu-id="58bcc-113">**Listener Port**</span></span>  
 <span data-ttu-id="58bcc-114">Le comportement de cette option varie comme suit selon qu'il existe ou non un point de terminaison de mise en miroir pour cette instance du serveur :</span><span class="sxs-lookup"><span data-stu-id="58bcc-114">The behavior of this option depends on whether the mirroring endpoint exists for this server instance, as follows:</span></span>  
  
-   <span data-ttu-id="58bcc-115">Si le port d’écoute n’existe pas pour cette instance de serveur, le numéro de port 5022 est affiché dans la zone de texte **Port** .</span><span class="sxs-lookup"><span data-stu-id="58bcc-115">If the listener port does not exist for this server instance, port number 5022 is displayed in the **Port** text box.</span></span> <span data-ttu-id="58bcc-116">Vous pouvez utiliser n'importe quel numéro de port disponible, tel que 7022.</span><span class="sxs-lookup"><span data-stu-id="58bcc-116">You can use any available port number, such as, 7022.</span></span>  
  
-   <span data-ttu-id="58bcc-117">Si le point de terminaison de mise en miroir existe déjà, son numéro de port est affiché.</span><span class="sxs-lookup"><span data-stu-id="58bcc-117">When the mirroring endpoint already exists, the port number from the endpoint is displayed.</span></span> <span data-ttu-id="58bcc-118">Si vous devez modifier le port, utilisez une commande ALTER ENDPOINT.</span><span class="sxs-lookup"><span data-stu-id="58bcc-118">If you need to change the port, use an ALTER ENDPOINT command.</span></span> <span data-ttu-id="58bcc-119">Pour plus d’informations, consultez [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="58bcc-119">For more information, see [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="58bcc-120">Un numéro de port est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="58bcc-120">A port number is required.</span></span>  
  
 <span data-ttu-id="58bcc-121">**Nom du point de terminaison**</span><span class="sxs-lookup"><span data-stu-id="58bcc-121">**Endpoint name**</span></span>  
 <span data-ttu-id="58bcc-122">Si le point de terminaison de mise en miroir existe pour cette instance du serveur, le nom du point de terminaison est affiché ici.</span><span class="sxs-lookup"><span data-stu-id="58bcc-122">If the mirroring endpoint exists for this server instance, the endpoint name is displayed here.</span></span> <span data-ttu-id="58bcc-123">Si le point de terminaison n'existe pas, vous pouvez spécifier son nom.</span><span class="sxs-lookup"><span data-stu-id="58bcc-123">If the endpoint does not exist, you can specify the name of the endpoint.</span></span>  
  
 <span data-ttu-id="58bcc-124">**Chiffrer les données envoyées via ce point de terminaison**</span><span class="sxs-lookup"><span data-stu-id="58bcc-124">**Encrypt data sent through this endpoint**</span></span>  
 <span data-ttu-id="58bcc-125">Par défaut, le chiffrement est activé.</span><span class="sxs-lookup"><span data-stu-id="58bcc-125">By default, encryption is enabled.</span></span> <span data-ttu-id="58bcc-126">Lorsqu'il est activé, il devient obligatoire (et non simplement pris en charge) et il utilise les valeurs par défaut pour toutes les options de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="58bcc-126">When enabled, encryption is required (not merely supported) and uses the default values for all of the encryption options.</span></span> <span data-ttu-id="58bcc-127">Pour plus d’informations, consultez [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="58bcc-127">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
 <span data-ttu-id="58bcc-128">Pour désactiver le chiffrement, désactivez la case à cocher.</span><span class="sxs-lookup"><span data-stu-id="58bcc-128">To disable encryption, clear the check box.</span></span> <span data-ttu-id="58bcc-129">Pour réactiver le chiffrement, activez la case à cocher.</span><span class="sxs-lookup"><span data-stu-id="58bcc-129">To re-enable encryption, select the check box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58bcc-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="58bcc-130">See Also</span></span>  
 <span data-ttu-id="58bcc-131">[Point de terminaison de mise en miroir de bases de données &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="58bcc-131">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="58bcc-132">[Propriétés de la base de données &#40;page Mise en miroir&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="58bcc-132">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="58bcc-133">[Créer un point de terminaison de mise en miroir de bases de données pour l’authentification Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="58bcc-133">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="58bcc-134">[Démarrer le moniteur de mise en miroir de bases de données &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="58bcc-134">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="58bcc-135">Mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58bcc-135">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
