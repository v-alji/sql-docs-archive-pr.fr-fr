---
title: Configurer une base de données miroir pour utiliser la propriété Trustworthy (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- TRUSTWORTHY database option
- mirror database [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 6993b076-78ef-453e-b0ea-e341b8e5ee3e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6cd46a08037bcb6eee178a96d84bdab358e5350d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701760"
---
# <a name="set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql"></a><span data-ttu-id="a548e-102">Configurer une base de données miroir pour utiliser la propriété Trustworthy (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a548e-102">Set Up a Mirror Database to Use the Trustworthy Property (Transact-SQL)</span></span>
  <span data-ttu-id="a548e-103">Lorsqu'une base de données est sauvegardée, la valeur OFF est attribuée à la propriété TRUSTWORTHY de la base de données.</span><span class="sxs-lookup"><span data-stu-id="a548e-103">When a database is backed up, the TRUSTWORTHY database property is set to OFF.</span></span> <span data-ttu-id="a548e-104">Par conséquent, la propriété TRUSTWORTHY d'une nouvelle base de données miroir a toujours la valeur OFF.</span><span class="sxs-lookup"><span data-stu-id="a548e-104">Therefore, on a new mirror database TRUSTWORTHY is always OFF.</span></span> <span data-ttu-id="a548e-105">Si la base de données doit être fiable après un basculement, des opérations de configuration supplémentaires sont requises après le début de la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="a548e-105">If the database needs to be trustworthy after a failover, extra setup steps are necessary after mirroring begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a548e-106">Pour plus d’informations sur cette propriété de base de données, consultez [Propriété de base de données TRUSTWORTHY](../../relational-databases/security/trustworthy-database-property.md).</span><span class="sxs-lookup"><span data-stu-id="a548e-106">For information about this database property, see [TRUSTWORTHY Database Property](../../relational-databases/security/trustworthy-database-property.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="a548e-107">Procédure</span><span class="sxs-lookup"><span data-stu-id="a548e-107">Procedure</span></span>  
  
#### <a name="to-setup-a-mirror-database-to-use-the-trustworthy-property"></a><span data-ttu-id="a548e-108">Pour configurer une base de données miroir pour qu'elle utilise la propriété Trustworthy</span><span class="sxs-lookup"><span data-stu-id="a548e-108">To setup a mirror database to use the Trustworthy Property</span></span>  
  
1.  <span data-ttu-id="a548e-109">Sur l'instance du serveur principal, vérifiez que la propriété Trustworthy de la base de données principale est activée.</span><span class="sxs-lookup"><span data-stu-id="a548e-109">On the principal server instance, verify that the principal database has the Trustworthy property turned on.</span></span>  
  
    ```  
    SELECT name, database_id, is_trustworthy_on FROM sys.databases   
    ```  
  
     <span data-ttu-id="a548e-110">Pour plus d’informations, consultez [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a548e-110">For more information, see [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span></span>  
  
2.  <span data-ttu-id="a548e-111">Après avoir démarré la mise en miroir, vérifiez que la base de données est actuellement la base de données principale, que la session utilise un mode de fonctionnement synchrone et que la session est toujours synchronisée.</span><span class="sxs-lookup"><span data-stu-id="a548e-111">After starting mirroring, verify that the database is currently the principal database, the session is using a synchronous operating mode, and the session is already synchronized.</span></span>  
  
    ```  
    SELECT database_id, mirroring_role, mirroring_safety_level_desc, mirroring_state_desc FROM sys.database_mirroring  
    ```  
  
     <span data-ttu-id="a548e-112">Pour plus d’informations, consultez [sys.database_mirroring &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a548e-112">For more information, see [sys.database_mirroring &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span></span>  
  
3.  <span data-ttu-id="a548e-113">Une fois la session de mise en miroir synchronisée, basculez manuellement vers la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="a548e-113">Once the mirroring session is synchronized, manually fail over to the mirror database.</span></span>  
  
     <span data-ttu-id="a548e-114">Cette opération est possible dans SQL Server Management Studio ou en utilisant Transact-SQL :</span><span class="sxs-lookup"><span data-stu-id="a548e-114">This can be done in either SQL Server Management Studio or using Transact-SQL:</span></span>  
  
    -   [<span data-ttu-id="a548e-115">Basculer manuellement une session de mise en miroir de bases de données &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a548e-115">Manually Fail Over a Database Mirroring Session &#40;SQL Server Management Studio&#41;</span></span>](manually-fail-over-a-database-mirroring-session-sql-server-management-studio.md)  
  
    -   [<span data-ttu-id="a548e-116">Basculer manuellement une session de mise en miroir de bases de données &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a548e-116">Manually Fail Over a Database Mirroring Session &#40;Transact-SQL&#41;</span></span>](manually-fail-over-a-database-mirroring-session-transact-sql.md)  
  
4.  <span data-ttu-id="a548e-117">Activez la propriété Trustworthy de la base de données en utilisant la commande ALTER DATABASE suivante :</span><span class="sxs-lookup"><span data-stu-id="a548e-117">Turn on the trustworthy database property using the following ALTER DATABASE command:</span></span>  
  
    ```  
    ALTER DATABASE <database_name> SET TRUSTWORTHY ON  
    ```  
  
     <span data-ttu-id="a548e-118">Pour plus d’informations, consultez [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a548e-118">For more information, see[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
5.  <span data-ttu-id="a548e-119">Vous pouvez également basculer manuellement de nouveau vers la base de données principale d'origine.</span><span class="sxs-lookup"><span data-stu-id="a548e-119">Optionally, manually failover again to return to the original principal.</span></span>  
  
6.  <span data-ttu-id="a548e-120">Vous pouvez également passer en mode hautes performances asynchrone en attribuant la valeur OFF à SAFETY et en garantissant que WITNESS a aussi la valeur OFF.</span><span class="sxs-lookup"><span data-stu-id="a548e-120">Optionally, switch to asynchronous, high-performance mode by setting SAFETY to OFF and ensuring that WITNESS is also set to OFF.</span></span>  
  
     <span data-ttu-id="a548e-121">Dans Transact-SQL :</span><span class="sxs-lookup"><span data-stu-id="a548e-121">In Transact-SQL:</span></span>  
  
    -   [<span data-ttu-id="a548e-122">Modifier la sécurité des transactions dans une session de mise en miroir de bases de données &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a548e-122">Change Transaction Safety in a Database Mirroring Session &#40;Transact-SQL&#41;</span></span>](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md)  
  
    -   [<span data-ttu-id="a548e-123">Supprimer le témoin d’une session de mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a548e-123">Remove the Witness from a Database Mirroring Session &#40;SQL Server&#41;</span></span>](remove-the-witness-from-a-database-mirroring-session-sql-server.md)  
  
     <span data-ttu-id="a548e-124">Dans SQL Server Management Studio :</span><span class="sxs-lookup"><span data-stu-id="a548e-124">In SQL Server Management Studio:</span></span>  
  
    -   [<span data-ttu-id="a548e-125">Établir une session de mise en miroir de bases de données au moyen de l’authentification Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a548e-125">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
## <a name="see-also"></a><span data-ttu-id="a548e-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a548e-126">See Also</span></span>  
 <span data-ttu-id="a548e-127">[Propriété de base de données TRUSTWORTHY](../../relational-databases/security/trustworthy-database-property.md) </span><span class="sxs-lookup"><span data-stu-id="a548e-127">[TRUSTWORTHY Database Property](../../relational-databases/security/trustworthy-database-property.md) </span></span>  
 [<span data-ttu-id="a548e-128">Configurer une base de données miroir chiffrée</span><span class="sxs-lookup"><span data-stu-id="a548e-128">Set Up an Encrypted Mirror Database</span></span>](set-up-an-encrypted-mirror-database.md)  
  
  
