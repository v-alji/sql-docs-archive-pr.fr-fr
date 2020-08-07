---
title: Accès réseau à un point de terminaison de mise en miroir de bases de données
description: Découvrez comment autoriser l’accès réseau Windows authenticatino à un point de terminaison de mise en miroir de bases de données pour SQL Server.
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Windows authentication [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 28c8fec5-5feb-4c84-8d72-f2bd1ae3b40d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0d1d8786d128ef2cc99fe571e33f89c4c4e7699c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612466"
---
# <a name="allow-network-access-to-a-database-mirroring-endpoint-using-windows-authentication-sql-server"></a><span data-ttu-id="98ee9-103">Autoriser l'accès sur le réseau à un point de terminaison de mise en miroir de bases de données au moyen de l'authentification Windows (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="98ee9-103">Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication (SQL Server)</span></span>
  <span data-ttu-id="98ee9-104">L'utilisation de l'authentification Windows pour connecter les points de terminaison de mise en miroir de bases de données de deux instances de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] requiert une configuration manuelle des comptes de connexion dans les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="98ee9-104">Using Windows Authentication for connecting the database mirroring endpoints of two instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] requires manual configuration of login accounts under the following conditions:</span></span>  
  
-   <span data-ttu-id="98ee9-105">Si les instances de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] fonctionnent comme des services sous des comptes de domaine différents (dans les mêmes domaines ou dans des domaines approuvés), la connexion de chaque compte doit être créée en **maître** sur chacune des instances de serveur distant, et cette connexion doit disposer d’autorisations CONNECT sur le point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="98ee9-105">If the instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] run as services under different domain accounts (in the same or trusted domains), the login of each account must be created in **master** on each of the remote server instances and that login must be granted CONNECT permissions on the endpoint.</span></span>  
  
-   <span data-ttu-id="98ee9-106">Si les instances de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] fonctionnent comme le compte de service réseau, la connexion de chaque compte d’ordinateur hôte (*nom_domaine***\\***nom_ordinateur$* ) doit être créée en **maître** sur chacune des instances de serveur distant, et cette connexion doit disposer d’autorisations CONNECT sur le point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="98ee9-106">If the instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] run as the Network Service account, the login of the each host computer account (*DomainName***\\***ComputerName$*) must be created in **master** on each of the remote server instances and that login must be granted CONNECT permissions on the endpoint.</span></span> <span data-ttu-id="98ee9-107">En effet, une instance de serveur s'exécutant sous le compte de service réseau s'authentifie à l'aide du compte de domaine de l'ordinateur hôte.</span><span class="sxs-lookup"><span data-stu-id="98ee9-107">This is because a server instance running under the Network Service account authenticates using the domain account of the host computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98ee9-108">Vérifiez qu'il existe un point de terminaison pour chaque instance du serveur.</span><span class="sxs-lookup"><span data-stu-id="98ee9-108">Ensure that an endpoint exists for each of the server instances.</span></span> <span data-ttu-id="98ee9-109">Pour plus d’informations, consultez [Créer un point de terminaison de mise en miroir de bases de données pour l’authentification Windows &#40;Transact-SQL&#41;](database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="98ee9-109">For more information, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
### <a name="to-configure-logins-for-windows-authentication"></a><span data-ttu-id="98ee9-110">Pour configurer des connexions pour l'authentification Windows</span><span class="sxs-lookup"><span data-stu-id="98ee9-110">To configure logins for Windows Authentication</span></span>  
  
1.  <span data-ttu-id="98ee9-111">Pour le compte d'utilisateur de chaque instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], créez une connexion sur les autres instances de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98ee9-111">For the user account of each instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], create a login on the other instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="98ee9-112">Utilisez une instruction [CREATE LOGIN](/sql/t-sql/statements/create-login-transact-sql) avec la clause FROM WINDOWS.</span><span class="sxs-lookup"><span data-stu-id="98ee9-112">Use a [CREATE LOGIN](/sql/t-sql/statements/create-login-transact-sql) statement with the FROM WINDOWS clause.</span></span>  
  
     <span data-ttu-id="98ee9-113">Pour plus d’informations, consultez [Créer un compte de connexion](../relational-databases/security/authentication-access/create-a-login.md).</span><span class="sxs-lookup"><span data-stu-id="98ee9-113">For more information, see [Create a Login](../relational-databases/security/authentication-access/create-a-login.md).</span></span>  
  
2.  <span data-ttu-id="98ee9-114">En outre, pour vérifier que l'utilisateur de connexion a accès au point de terminaison, utilisez l'instruction [GRANT](/sql/t-sql/statements/grant-transact-sql) pour accorder des autorisations de connexion sur le point de terminaison à la connexion.</span><span class="sxs-lookup"><span data-stu-id="98ee9-114">Also, to ensure that the login user has access to the endpoint, use the [GRANT](/sql/t-sql/statements/grant-transact-sql) statement to grant connect permissions on the endpoint to the login.</span></span> <span data-ttu-id="98ee9-115">Notez que l'attribution d'autorisations de connexion n'est pas nécessaire si l'utilisateur est un administrateur.</span><span class="sxs-lookup"><span data-stu-id="98ee9-115">Note that granting connect permissions to the endpoint is unnecessary if the user is an Administrator.</span></span>  
  
     <span data-ttu-id="98ee9-116">Pour en savoir plus, voir [Grant a Permission to a Principal](../relational-databases/security/authentication-access/grant-a-permission-to-a-principal.md).</span><span class="sxs-lookup"><span data-stu-id="98ee9-116">For more information, see [Grant a Permission to a Principal](../relational-databases/security/authentication-access/grant-a-permission-to-a-principal.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="98ee9-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="98ee9-117">Example</span></span>  
 <span data-ttu-id="98ee9-118">L'exemple [!INCLUDE[tsql](../includes/tsql-md.md)] suivant crée une connexion [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pour un compte d'utilisateur nommé `Otheruser` qui appartient à un domaine du nom de `Adomain`.</span><span class="sxs-lookup"><span data-stu-id="98ee9-118">The following [!INCLUDE[tsql](../includes/tsql-md.md)] example creates a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login for a user account named `Otheruser` that belongs to a domain called `Adomain`.</span></span> <span data-ttu-id="98ee9-119">Des autorisations de connexion sont ensuite octroyées à cet utilisateur pour le point de terminaison de la mise en miroir de bases de données préexistantes appelé `Mirroring_Endpoint`.</span><span class="sxs-lookup"><span data-stu-id="98ee9-119">The example then grants this user connect permissions to a pre-existing database mirroring endpoint named `Mirroring_Endpoint`.</span></span>  
  
```  
USE master;  
GO  
CREATE LOGIN [Adomain\Otheruser] FROM WINDOWS;  
GO  
GRANT CONNECT on ENDPOINT::Mirroring_Endpoint TO [Adomain\Otheruser];  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="98ee9-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="98ee9-120">See Also</span></span>  
 <span data-ttu-id="98ee9-121">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="98ee9-121">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="98ee9-122">[Mise en miroir de bases de données &#40;SQL Server&#41;](database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="98ee9-122">[Database Mirroring &#40;SQL Server&#41;](database-mirroring/database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="98ee9-123">[Sécurité de transport pour la mise en miroir de bases de données et les groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](database-mirroring/transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="98ee9-123">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](database-mirroring/transport-security-database-mirroring-always-on-availability.md) </span></span>  
 [<span data-ttu-id="98ee9-124">Point de terminaison de mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="98ee9-124">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](database-mirroring/the-database-mirroring-endpoint-sql-server.md)  
  
  
