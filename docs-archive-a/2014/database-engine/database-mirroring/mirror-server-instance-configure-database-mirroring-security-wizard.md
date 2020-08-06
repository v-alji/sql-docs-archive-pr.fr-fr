---
title: Instance de serveur miroir (Configurer l’Assistant Sécurité de mise en miroir de bases de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.mirrorsrvr.f1
ms.assetid: 53223432-615e-440f-904d-925d33ec2144
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 889e62af592d8d23f2aca0d752f1c7f535df883a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709915"
---
# <a name="mirror-server-instance-configure-database-mirroring-security-wizard"></a><span data-ttu-id="5dd66-102">Instance de serveur miroir (Configurer l'Assistant Sécurité de mise en miroir de bases de données)</span><span class="sxs-lookup"><span data-stu-id="5dd66-102">Mirror Server Instance (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="5dd66-103">Cette page vous permet de spécifier des informations sur l'instance de serveur avec la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="5dd66-103">Use this page to specify information about the server instance with the mirror database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5dd66-104">L'instance de serveur miroir doit exécuter la même édition de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)](Standard ou Entreprise) que l'instance de serveur principal.</span><span class="sxs-lookup"><span data-stu-id="5dd66-104">The mirror server instance must be running the same edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], either Standard or Enterprise, as the principal server instance.</span></span> <span data-ttu-id="5dd66-105">En outre, nous vous conseillons vivement d'exécuter les instances sur des systèmes comparables pouvant gérer des charges de travail identiques.</span><span class="sxs-lookup"><span data-stu-id="5dd66-105">Also, we strongly recommend that they run on comparable systems that can handle identical workloads.</span></span>  
  
 <span data-ttu-id="5dd66-106">**Pour configurer la mise en miroir de bases de données à l'aide de SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="5dd66-106">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="5dd66-107">Établir une session de mise en miroir de bases de données au moyen de l’authentification Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="5dd66-107">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="5dd66-108">Démarrer l’Assistant Configuration de la sécurité de mise en miroir de bases de données &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="5dd66-108">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="5dd66-109">Options</span><span class="sxs-lookup"><span data-stu-id="5dd66-109">Options</span></span>  
 <span data-ttu-id="5dd66-110">**Instance de serveur miroir**</span><span class="sxs-lookup"><span data-stu-id="5dd66-110">**Mirror server instance**</span></span>  
 <span data-ttu-id="5dd66-111">Si une instance de serveur miroir est déjà spécifiée (dans la page **Mise en miroir** de la boîte de dialogue **Propriétés de la base de données** ), cette instance est affichée. Pour plus d’informations, consultez [Propriétés de la base de données &#40;page Mise en miroir&#41;](../../relational-databases/databases/database-properties-mirroring-page.md).</span><span class="sxs-lookup"><span data-stu-id="5dd66-111">If a mirror server instance is already specified (on the **Mirroring** page of the **Database Properties** dialog box), that instance is displayed; for more information, see [Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md).</span></span>  
  
 <span data-ttu-id="5dd66-112">Dans le cas contraire, entrez le nom de l'instance de serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="5dd66-112">Otherwise, enter the name of the mirror server instance.</span></span> <span data-ttu-id="5dd66-113">Notez que l'instance de serveur miroir ne peut pas être identique à l'instance de serveur principal.</span><span class="sxs-lookup"><span data-stu-id="5dd66-113">Note that the mirror server instance cannot be the same as the principal server instance.</span></span>  
  
 <span data-ttu-id="5dd66-114">**Connexion**</span><span class="sxs-lookup"><span data-stu-id="5dd66-114">**Connect**</span></span>  
 <span data-ttu-id="5dd66-115">Si aucune instance de serveur miroir n’a été spécifiée, cliquez sur **Se connecter**</span><span class="sxs-lookup"><span data-stu-id="5dd66-115">If a mirror server instance has not been specified, click **Connect**.</span></span> <span data-ttu-id="5dd66-116">pour afficher la boîte de dialogue **Se connecter au serveur** , dans laquelle vous pouvez spécifier l’instance de serveur et établir une connexion.</span><span class="sxs-lookup"><span data-stu-id="5dd66-116">This displays the **Connect to Server** dialog box in which you can specify the server instance and establish a connection.</span></span>  
  
 <span data-ttu-id="5dd66-117">Si l’instance a été spécifiée, mais que l’Assistant ne propose pas de connexion doté d’autorisations suffisantes pour vérifier l’existence du point de terminaison, cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="5dd66-117">If the instance has been specified, but the wizard lacks a connection with sufficient permission to check for the existence of the endpoint, click **Connect**.</span></span> <span data-ttu-id="5dd66-118">Dans la boîte de dialogue **Se connecter au serveur** qui s’affiche, l’instance de serveur est présélectionnée et ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="5dd66-118">This displays the **Connect to Server** dialog box with the server instance pre-selected and unchangeable.</span></span> <span data-ttu-id="5dd66-119">Spécifiez un compte de domaine qui possède une autorisation suffisante et connectez-vous à l'instance du serveur.</span><span class="sxs-lookup"><span data-stu-id="5dd66-119">Specify a domain account with sufficient permission, and connect to the server instance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5dd66-120">Au moment de se connecter à l’instance du serveur, l’Assistant de configuration de la sécurité de mise en miroir de bases de données utilise les informations d’identification fournies dans la boîte de dialogue **Se connecter au serveur** .</span><span class="sxs-lookup"><span data-stu-id="5dd66-120">When connecting to the server instance, the Configure Database Mirroring Security Wizard uses the credentials provided in the **Connect to Server** dialog box.</span></span> <span data-ttu-id="5dd66-121">Celles-ci diffèrent des informations d'identification d'une session de mise en miroir, qui utilise les informations d'identification du compte de démarrage où l'instance de serveur est en cours d'exécution en tant que service.</span><span class="sxs-lookup"><span data-stu-id="5dd66-121">These are different from the credentials of a mirroring session, which uses the credentials of the startup account where the server instance is running as a service.</span></span>  
  
 <span data-ttu-id="5dd66-122">**Port de l’écouteur**</span><span class="sxs-lookup"><span data-stu-id="5dd66-122">**Listener Port**</span></span>  
 <span data-ttu-id="5dd66-123">Le comportement de cette option varie comme suit selon qu'il existe ou non un point de terminaison de mise en miroir pour cette instance du serveur :</span><span class="sxs-lookup"><span data-stu-id="5dd66-123">The behavior of this option depends on whether the mirroring endpoint exists for this server instance, as follows:</span></span>  
  
-   <span data-ttu-id="5dd66-124">Si aucun port d’écoute n’existe pour l’instance de serveur, le numéro de port 5022 est affiché dans la zone de texte **Port** .</span><span class="sxs-lookup"><span data-stu-id="5dd66-124">If a listener port does not exist for the server instance, port number 5022 is displayed in the **Port** text box.</span></span> <span data-ttu-id="5dd66-125">Vous pouvez utiliser n'importe quel numéro de port disponible, tel que 7022.</span><span class="sxs-lookup"><span data-stu-id="5dd66-125">You can use any available port number, such as 7022.</span></span>  
  
-   <span data-ttu-id="5dd66-126">Lorsque le point de terminaison de mise en miroir existe déjà, le numéro de port issu de ce point de terminaison est affiché.</span><span class="sxs-lookup"><span data-stu-id="5dd66-126">When the mirroring endpoint already exists, the port number from that endpoint is displayed.</span></span> <span data-ttu-id="5dd66-127">Si vous devez modifier le port, utilisez une commande ALTER ENDPOINT.</span><span class="sxs-lookup"><span data-stu-id="5dd66-127">If you need to change the port, use an ALTER ENDPOINT command.</span></span> <span data-ttu-id="5dd66-128">Pour plus d’informations, consultez [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5dd66-128">For more information, see [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5dd66-129">Un numéro de port est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="5dd66-129">A port number is required.</span></span>  
  
 <span data-ttu-id="5dd66-130">**Nom du point de terminaison**</span><span class="sxs-lookup"><span data-stu-id="5dd66-130">**Endpoint name**</span></span>  
 <span data-ttu-id="5dd66-131">Si le point de terminaison de mise en miroir existe pour cette instance du serveur, le nom du point de terminaison est affiché ici.</span><span class="sxs-lookup"><span data-stu-id="5dd66-131">If the mirroring endpoint exists for this server instance, the endpoint name is displayed here.</span></span> <span data-ttu-id="5dd66-132">Si le point de terminaison n'existe pas, vous pouvez spécifier son nom.</span><span class="sxs-lookup"><span data-stu-id="5dd66-132">If the endpoint does not exist, you can specify the name of the endpoint.</span></span>  
  
 <span data-ttu-id="5dd66-133">**Chiffrer les données envoyées via ce point de terminaison**</span><span class="sxs-lookup"><span data-stu-id="5dd66-133">**Encrypt data sent through this endpoint**</span></span>  
 <span data-ttu-id="5dd66-134">Par défaut, le chiffrement est activé.</span><span class="sxs-lookup"><span data-stu-id="5dd66-134">By default, encryption is enabled.</span></span> <span data-ttu-id="5dd66-135">Lorsqu'il est activé, il devient obligatoire (et non simplement pris en charge) et il utilise les valeurs par défaut pour toutes les options de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="5dd66-135">When enabled, encryption is required (not merely supported) and uses the default values for all of the encryption options.</span></span> <span data-ttu-id="5dd66-136">Pour plus d’informations, consultez [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5dd66-136">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
 <span data-ttu-id="5dd66-137">Pour désactiver le chiffrement, désactivez la case à cocher.</span><span class="sxs-lookup"><span data-stu-id="5dd66-137">To disable encryption, clear the check box.</span></span> <span data-ttu-id="5dd66-138">Pour réactiver le chiffrement, activez la case à cocher.</span><span class="sxs-lookup"><span data-stu-id="5dd66-138">To re-enable encryption, select the check box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dd66-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5dd66-139">See Also</span></span>  
 <span data-ttu-id="5dd66-140">[Point de terminaison de mise en miroir de bases de données &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5dd66-140">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="5dd66-141">[Propriétés de la base de données &#40;page Mise en miroir&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="5dd66-141">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="5dd66-142">[Créer un point de terminaison de mise en miroir de bases de données pour l’authentification Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="5dd66-142">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="5dd66-143">[Démarrer le moniteur de mise en miroir de bases de données &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="5dd66-143">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="5dd66-144">Mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5dd66-144">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
