---
title: Démarrer le moniteur de mise en miroir de bases de données (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- monitoring database mirroring [SQL Server]
- Database Mirroring Monitor [SQL Server], starting
- database mirroring [SQL Server], monitoring
ms.assetid: 53165335-97ca-4f88-8e78-22f1839dee98
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67c7b393b28d4d400535281c18c637146a5d8da7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600230"
---
# <a name="start-database-mirroring-monitor-sql-server-management-studio"></a><span data-ttu-id="77059-102">Démarrer le moniteur de mise en miroir de bases de données (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="77059-102">Start Database Mirroring Monitor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="77059-103">Le moniteur de mise en miroir de base de données fait partie du Moniteur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , que vous pouvez démarrer à partir de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77059-103">The Database Mirroring Monitor is part of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Monitor, which is launched from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77059-104">Le Moniteur de mise en miroir de bases de données n’est pas disponible dans toutes les éditions de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77059-104">Database Mirroring Monitor is not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="77059-105">Pour obtenir une liste des fonctionnalités prises en charge par les éditions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="77059-105">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
### <a name="to-launch-the-database-mirroring-monitor"></a><span data-ttu-id="77059-106">Pour lancer l'analyse de mise en miroir de base de données</span><span class="sxs-lookup"><span data-stu-id="77059-106">To launch the Database Mirroring Monitor</span></span>  
  
1.  <span data-ttu-id="77059-107">Après vous être connecté à l'instance du serveur principal, dans l'Explorateur d'objets, cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="77059-107">After connecting to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="77059-108">Développez **Bases de données**, puis sélectionnez la base de données à analyser.</span><span class="sxs-lookup"><span data-stu-id="77059-108">Expand **Databases**, and select the database to be monitored.</span></span>  
  
3.  <span data-ttu-id="77059-109">Cliquez avec le bouton droit sur la base de données, sélectionnez **Tâches**, puis cliquez sur **Lancer le moniteur de mise en miroir de bases de données**.</span><span class="sxs-lookup"><span data-stu-id="77059-109">Right-click the database, select **Tasks**, and then click **Launch Database Mirroring Monitor**.</span></span>  
  
4.  <span data-ttu-id="77059-110">Dans la boîte de dialogue **Moniteur de mise en miroir de bases de données** , cliquez sur **Inscrire la base de données mise en miroir** pour inscrire une ou plusieurs bases de données en miroir.</span><span class="sxs-lookup"><span data-stu-id="77059-110">In the **Database Mirroring Monitor** dialog box, click **Register Mirrored Database** to register one or more mirrored database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="77059-111">Lorsque vous inscrivez une base de données sur un partenaire, elle est automatiquement inscrite sur l'autre partenaire.</span><span class="sxs-lookup"><span data-stu-id="77059-111">When you register a database at one partner, the database is automatically registered at the other partner.</span></span> <span data-ttu-id="77059-112">Si le moniteur possède déjà des informations d'identification de connexion pour l'instance de l'autre partenaire, elles sont utilisées pour établir la connexion.</span><span class="sxs-lookup"><span data-stu-id="77059-112">If the monitor already has connection credentials for the other partner instance, those are used to connect.</span></span> <span data-ttu-id="77059-113">Autrement, le moniteur tente d'établir une connexion avec l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="77059-113">Otherwise the monitor attempts to connect using Windows Authentication.</span></span> <span data-ttu-id="77059-114">Si vous souhaitez modifier les informations d’identification utilisées pour la connexion à l’une des instances de serveur, cliquez sur **Afficher la boîte de dialogue Gérer les connexions serveur lorsque je clique sur OK**.</span><span class="sxs-lookup"><span data-stu-id="77059-114">If you want to change the credentials used to connect to either server instance, click **Show the Manage Server Connections dialog box when I click OK**.</span></span>  
  
 <span data-ttu-id="77059-115">Pour plus d’informations sur le moniteur de mise en miroir de bases de données, consultez [Vue d’ensemble du moniteur de mise en miroir de bases de données](database-mirroring-monitor-overview.md).</span><span class="sxs-lookup"><span data-stu-id="77059-115">For more information about Database Mirroring Monitor, see [Database Mirroring Monitor Overview](database-mirroring-monitor-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77059-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="77059-116">See Also</span></span>  
 <span data-ttu-id="77059-117">[Mise en miroir de bases de données &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="77059-117">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="77059-118">Établir une session de mise en miroir de bases de données au moyen de l’authentification Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="77059-118">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
  
