---
title: Basculer manuellement une session de mise en miroir de bases de données (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover [SQL Server], database mirroring
- manual failover [SQL Server]
- database mirroring [SQL Server], failover
ms.assetid: 4ecf9c63-b3a4-4c54-b553-5bc37973232b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7f7f4547058b2dfd4229142dca73a7d9b4bdb239
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709916"
---
# <a name="manually-fail-over-a-database-mirroring-session-sql-server-management-studio"></a><span data-ttu-id="cb818-102">Basculer manuellement une session de mise en miroir de bases de données (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="cb818-102">Manually Fail Over a Database Mirroring Session (SQL Server Management Studio)</span></span>
  <span data-ttu-id="cb818-103">Lorsque la base de données en miroir est synchronisée (que son état est SYNCHRONIZED), le propriétaire de la base de données peut initier un basculement manuel vers le serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="cb818-103">When the mirrored database is synchronized (that is, when the database is in the SYNCHRONIZED state), the database owner can initiate manual failover to the mirror server.</span></span>  
  
 <span data-ttu-id="cb818-104">Lors d'un basculement manuel, les rôles de principal et de serveur miroir sont permutés pour la base de données concernée par le basculement.</span><span class="sxs-lookup"><span data-stu-id="cb818-104">During a manual failover, the principal and mirror server roles are swapped for the database on which the failover occurs.</span></span> <span data-ttu-id="cb818-105">La base de données miroir devient la base de données principale et inversement.</span><span class="sxs-lookup"><span data-stu-id="cb818-105">The mirror database becomes the principal database and the principal database becomes the mirror.</span></span> <span data-ttu-id="cb818-106">Par exemple, le tableau suivant illustre la façon dont les rôles de deux serveurs partenaires de mise en miroir sont permutés à l'occasion d'un basculement manuel : `SQLDBENGINE0_1` et `SQLDBENGINE0_2`.</span><span class="sxs-lookup"><span data-stu-id="cb818-106">For example, the following table shows the how a manual failover swaps the roles of two mirroring partners: `SQLDBENGINE0_1` and `SQLDBENGINE0_2`.</span></span>  
  
|<span data-ttu-id="cb818-107">Serveur</span><span class="sxs-lookup"><span data-stu-id="cb818-107">Server</span></span>|<span data-ttu-id="cb818-108">Avant le basculement</span><span class="sxs-lookup"><span data-stu-id="cb818-108">Before failover</span></span>|<span data-ttu-id="cb818-109">Après le basculement</span><span class="sxs-lookup"><span data-stu-id="cb818-109">After failover</span></span>|  
|------------|---------------------|--------------------|  
|`SQLDBENGINE0_1`|<span data-ttu-id="cb818-110">PRINCIPAL</span><span class="sxs-lookup"><span data-stu-id="cb818-110">PRINCIPAL</span></span>|<span data-ttu-id="cb818-111">MIRROR</span><span class="sxs-lookup"><span data-stu-id="cb818-111">MIRROR</span></span>|  
|`SQLDBENGINE0_2`|<span data-ttu-id="cb818-112">MIRROR</span><span class="sxs-lookup"><span data-stu-id="cb818-112">MIRROR</span></span>|<span data-ttu-id="cb818-113">PRINCIPAL</span><span class="sxs-lookup"><span data-stu-id="cb818-113">PRINCIPAL</span></span>|  
  
 <span data-ttu-id="cb818-114">Sachez que les rôles serveur des autres sessions de mise en miroir de base de données ne sont pas affectés.</span><span class="sxs-lookup"><span data-stu-id="cb818-114">Note that the server roles for other database mirroring sessions are not affected.</span></span> <span data-ttu-id="cb818-115">Pour plus d’informations, consultez [Basculement de rôle durant une session de mise en miroir de bases de données &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cb818-115">For more information, see [Role Switching During a Database Mirroring Session &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md).</span></span>  
  
### <a name="to-manually-fail-over-database-mirroring"></a><span data-ttu-id="cb818-116">Pour effectuer un basculement manuel d'une mise en miroir de base de données</span><span class="sxs-lookup"><span data-stu-id="cb818-116">To manually fail over database mirroring</span></span>  
  
1.  <span data-ttu-id="cb818-117">Connectez-vous à l'instance du serveur principal puis, dans le volet **Explorateur d'objets** , cliquez sur le nom du serveur pour développer l'arborescence.</span><span class="sxs-lookup"><span data-stu-id="cb818-117">Connect to the principal server instance and, in the **Object Explorer** pane, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="cb818-118">Développez **Bases de données**, puis sélectionnez la base de données à basculer.</span><span class="sxs-lookup"><span data-stu-id="cb818-118">Expand **Databases**, and select the database to be failed over.</span></span>  
  
3.  <span data-ttu-id="cb818-119">Cliquez avec le bouton droit sur la base de données, sélectionnez **Tâches**, puis cliquez sur **Miroir**.</span><span class="sxs-lookup"><span data-stu-id="cb818-119">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="cb818-120">La page **Mise en miroir** de la boîte de dialogue **Propriétés de la base de données** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="cb818-120">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="cb818-121">Cliquez sur **Basculement**.</span><span class="sxs-lookup"><span data-stu-id="cb818-121">Click **Failover**.</span></span>  
  
     <span data-ttu-id="cb818-122">Une boîte de confirmation s'affiche.</span><span class="sxs-lookup"><span data-stu-id="cb818-122">A confirmation box appears.</span></span>  <span data-ttu-id="cb818-123">Le serveur principal commence par essayer de se connecter au serveur miroir à l'aide de l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="cb818-123">The principal server begins by trying to connect to the mirror server by using Windows Authentication.</span></span> <span data-ttu-id="cb818-124">Si l’authentification Windows ne fonctionne pas, le serveur principal affiche la boîte de dialogue **Se connecter au serveur** .</span><span class="sxs-lookup"><span data-stu-id="cb818-124">If Windows Authentication does not work, the principal server displays the **Connect to Server** dialog box.</span></span> <span data-ttu-id="cb818-125">Si le serveur miroir utilise l’authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , sélectionnez **Authentification SQL Server** dans la zone **Authentification** .</span><span class="sxs-lookup"><span data-stu-id="cb818-125">If the mirror server uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, select **SQL Server Authentication** in the **Authentication** box.</span></span> <span data-ttu-id="cb818-126">Dans la zone de texte **Connexion** , spécifiez le compte de connexion à utiliser pour se connecter sur le serveur miroir puis, dans la zone de texte **Mot de passe** , spécifiez le mot de passe de ce compte.</span><span class="sxs-lookup"><span data-stu-id="cb818-126">In the **Login** text box, specify the login account to connect with on the mirror server, and in the **Password** text box, specify the password for that account.</span></span>  
  
     <span data-ttu-id="cb818-127">Si le basculement réussit, la boîte de dialogue **Propriétés de la base de données** se ferme.</span><span class="sxs-lookup"><span data-stu-id="cb818-127">If failover succeeds, the **Database Properties** dialog box closes.</span></span> <span data-ttu-id="cb818-128">La base de données miroir devient la base de données principale et inversement.</span><span class="sxs-lookup"><span data-stu-id="cb818-128">The mirror database becomes the principal database and the principal database becomes the mirror.</span></span>  
  
     <span data-ttu-id="cb818-129">Si le basculement échoue, un message d'erreur s'affiche et la boîte de dialogue reste ouverte.</span><span class="sxs-lookup"><span data-stu-id="cb818-129">If failover fails, an error message is displayed and the dialog box remains open.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="cb818-130">Si vous avez modifié des propriétés depuis l’ouverture de la page **Mise en miroir** , ces modifications ne sont pas enregistrées.</span><span class="sxs-lookup"><span data-stu-id="cb818-130">If you have modified any properties since opening the **Mirroring** page, those changes will not be saved.</span></span>  
  
     <span data-ttu-id="cb818-131">La boîte de dialogue se ferme automatiquement.</span><span class="sxs-lookup"><span data-stu-id="cb818-131">The dialog box closes automatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb818-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cb818-132">See Also</span></span>  
 <span data-ttu-id="cb818-133">[Propriétés de la base de données &#40;page Mise en miroir&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="cb818-133">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="cb818-134">[Mise en miroir de bases de données &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cb818-134">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="cb818-135">[Basculer manuellement une session de mise en miroir de bases de données &#40;Transact-SQL&#41;](manually-fail-over-a-database-mirroring-session-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="cb818-135">[Manually Fail Over a Database Mirroring Session &#40;Transact-SQL&#41;](manually-fail-over-a-database-mirroring-session-transact-sql.md) </span></span>  
 <span data-ttu-id="cb818-136">[Suspendre ou reprendre une session de mise en miroir de bases de données &#40;SQL Server&#41;](pause-or-resume-a-database-mirroring-session-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cb818-136">[Pause or Resume a Database Mirroring Session &#40;SQL Server&#41;](pause-or-resume-a-database-mirroring-session-sql-server.md) </span></span>  
 [<span data-ttu-id="cb818-137">Supprimer une mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cb818-137">Remove Database Mirroring &#40;SQL Server&#41;</span></span>](remove-database-mirroring-sql-server.md)  
  
  
