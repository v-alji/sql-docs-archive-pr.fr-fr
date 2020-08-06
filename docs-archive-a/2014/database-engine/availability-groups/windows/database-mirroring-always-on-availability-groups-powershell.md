---
title: Créer un point de terminaison de mise en miroir de bases de données pour groupes de disponibilité AlwaysOn (SQL Server PowerShell) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], server instance
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], endpoint
ms.assetid: 6197bbe7-67d4-446d-ba5f-cabfa5df77f1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 56058ff8aa72d2471381dd87fb25a3b68356ed36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710792"
---
# <a name="create-a-database-mirroring-endpoint-for-alwayson-availability-groups-sql-server-powershell"></a><span data-ttu-id="98cfb-102">Créer un point de terminaison de mise en miroir de bases de données pour les groupes de disponibilité AlwaysOn (SQL Server PowerShell)</span><span class="sxs-lookup"><span data-stu-id="98cfb-102">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups (SQL Server PowerShell)</span></span>
  <span data-ttu-id="98cfb-103">Cette rubrique explique comment créer un point de terminaison de mise en miroir de bases de données à utiliser par [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="98cfb-103">This topic describes how to create a database mirroring endpoint for use by [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using PowerShell.</span></span>  
  
 <span data-ttu-id="98cfb-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="98cfb-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="98cfb-105">**Avant de commencer :**  [Sécurité](#Security)</span><span class="sxs-lookup"><span data-stu-id="98cfb-105">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="98cfb-106">**Pour créer un point de terminaison de mise en miroir de bases de données, à l'aide de :**  [PowerShell](#PowerShellProcedure)</span><span class="sxs-lookup"><span data-stu-id="98cfb-106">**To create a database mirroring endpoint, using:**  [PowerShell](#PowerShellProcedure)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="98cfb-107">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="98cfb-107">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="98cfb-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="98cfb-108">Security</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="98cfb-109">L'algorithme RC4 est déconseillé.</span><span class="sxs-lookup"><span data-stu-id="98cfb-109">The RC4 algorithm is deprecated.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="98cfb-110">Nous vous recommandons d'utiliser AES.</span><span class="sxs-lookup"><span data-stu-id="98cfb-110">We recommend that you use AES.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="98cfb-111">Autorisations</span><span class="sxs-lookup"><span data-stu-id="98cfb-111">Permissions</span></span>  
 <span data-ttu-id="98cfb-112">Requiert l'autorisation CREATE ENDPOINT ou l'appartenance au rôle serveur fixe sysadmin.</span><span class="sxs-lookup"><span data-stu-id="98cfb-112">Requires CREATE ENDPOINT permission, or membership in the sysadmin fixed server role.</span></span> <span data-ttu-id="98cfb-113">Pour plus d’informations, consultez [Autorisations de point de terminaison GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="98cfb-113">For more information, see [GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="98cfb-114">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="98cfb-114">Using PowerShell</span></span>  
 <span data-ttu-id="98cfb-115">**Pour créer un point de terminaison pour la mise en miroir de bases de données**</span><span class="sxs-lookup"><span data-stu-id="98cfb-115">**To create a database mirroring endpoint**</span></span>  
  
1.  <span data-ttu-id="98cfb-116">Accédez au répertoire (`cd`) de l'instance de serveur pour laquelle vous voulez créer le point de terminaison de mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="98cfb-116">Change directory (`cd`) to the server instance for which you want to create the database mirroring endpoint.</span></span>  
  
2.  <span data-ttu-id="98cfb-117">Utilisez l'applet de commande `New-SqlHadrEndpoint` pour créer le point de terminaison, puis utilisez `Set-SqlHadrEndpoint` pour démarrer le point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="98cfb-117">Use the `New-SqlHadrEndpoint` cmdlet to create the endpoint and then use the `Set-SqlHadrEndpoint` to start the endpoint.</span></span>  
  
###  <a name="example-powershell"></a><a name="PShellExample"></a> <span data-ttu-id="98cfb-118">Exemple (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="98cfb-118">Example (PowerShell)</span></span>  
 <span data-ttu-id="98cfb-119">Les commandes PowerShell suivantes créent un point de terminaison de mise en miroir de bases de données sur une instance de SQL Server (instance de*machine* \\ *Instance*).</span><span class="sxs-lookup"><span data-stu-id="98cfb-119">The following PowerShell commands create a database mirroring endpoint on an instance of SQL Server (*Machine*\\*Instance*).</span></span> <span data-ttu-id="98cfb-120">Le point de terminaison utilise le port 5022.</span><span class="sxs-lookup"><span data-stu-id="98cfb-120">The endpoint uses port 5022.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="98cfb-121">Cet exemple fonctionne uniquement sur une instance de serveur à laquelle aucun point de terminaison de mise en miroir de bases de données n'est actuellement associé.</span><span class="sxs-lookup"><span data-stu-id="98cfb-121">This example works only on a server instance that currently lack a database mirroring endpoint.</span></span>  
  
```powershell
# Create the endpoint.  
$endpoint = New-SqlHadrEndpoint MyMirroringEndpoint -Port 5022 -Path SQLSERVER:\SQL\Machine\Instance  
  
# Start the endpoint  
Set-SqlHadrEndpoint -InputObject $endpoint -State "Started"
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="98cfb-122">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="98cfb-122">Related Tasks</span></span>  
 <span data-ttu-id="98cfb-123">**Pour configurer un point de terminaison de mise en miroir de bases de données**</span><span class="sxs-lookup"><span data-stu-id="98cfb-123">**To Configure a Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="98cfb-124">Créer un point de terminaison de mise en miroir de bases de données pour l’authentification Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="98cfb-124">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="98cfb-125">Utiliser des certificats pour un point de terminaison de mise en miroir de bases de données &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="98cfb-125">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
    -   [<span data-ttu-id="98cfb-126">Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions sortantes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="98cfb-126">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-outbound-connections.md)  
  
    -   [<span data-ttu-id="98cfb-127">Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions entrantes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="98cfb-127">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="98cfb-128">Spécifier une adresse réseau de serveur &#40;mise en miroir de bases de données&#41;</span><span class="sxs-lookup"><span data-stu-id="98cfb-128">Specify a Server Network Address &#40;Database Mirroring&#41;</span></span>](../../database-mirroring/specify-a-server-network-address-database-mirroring.md)  
  
-   [<span data-ttu-id="98cfb-129">Spécifier l’URL de point de terminaison lors de l’ajout ou lors de la modification d’un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="98cfb-129">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
 <span data-ttu-id="98cfb-130">**Pour afficher des informations sur le point de terminaison de mise en miroir de bases de données**</span><span class="sxs-lookup"><span data-stu-id="98cfb-130">**To View Information About the Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="98cfb-131">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="98cfb-131">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="98cfb-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="98cfb-132">See Also</span></span>  
 <span data-ttu-id="98cfb-133">[Créer un groupe de disponibilité &#40;&#41;Transact-SQL](create-an-availability-group-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="98cfb-133">[Create an Availability Group &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md) </span></span>  
 [<span data-ttu-id="98cfb-134">Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="98cfb-134">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
