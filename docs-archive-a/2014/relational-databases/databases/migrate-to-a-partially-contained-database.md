---
title: Migrer vers une base de données partiellement autonome | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- contained database, migrating to
ms.assetid: 90faac38-f79e-496d-b589-e8b2fe01c562
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6142d46dc0540e5998fa66d463538d1453a17d84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709520"
---
# <a name="migrate-to-a-partially-contained-database"></a><span data-ttu-id="1b1f9-102">Migrer vers une base de données partiellement autonome</span><span class="sxs-lookup"><span data-stu-id="1b1f9-102">Migrate to a Partially Contained Database</span></span>
  <span data-ttu-id="1b1f9-103">Cette rubrique explique comment se préparer à passer au modèle de base de données partiellement autonome, puis indique la procédure de migration.</span><span class="sxs-lookup"><span data-stu-id="1b1f9-103">This topic discusses how to prepare to change to the partially contained database model and then provides the migration steps.</span></span>  
  
 <span data-ttu-id="1b1f9-104">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="1b1f9-104">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="1b1f9-105">Préparation de la migration d'une base de données</span><span class="sxs-lookup"><span data-stu-id="1b1f9-105">Preparing to Migrate a Database</span></span>](#prepare)  
  
-   [<span data-ttu-id="1b1f9-106">Activer les bases de données autonomes</span><span class="sxs-lookup"><span data-stu-id="1b1f9-106">Enable Contained Databases</span></span>](#enable)  
  
-   [<span data-ttu-id="1b1f9-107">Conversion d'une base de données au modèle partiellement à relation contenant-contenu</span><span class="sxs-lookup"><span data-stu-id="1b1f9-107">Converting a Database to Partially Contained</span></span>](#convert)  
  
-   [<span data-ttu-id="1b1f9-108">Migration des utilisateurs vers des utilisateurs de base de données autonome</span><span class="sxs-lookup"><span data-stu-id="1b1f9-108">Migrating Users to Contained Database Users</span></span>](#users)  
  
##  <a name="preparing-to-migrate-a-database"></a><a name="prepare"></a> <span data-ttu-id="1b1f9-109">Préparation de la migration d'une base de données</span><span class="sxs-lookup"><span data-stu-id="1b1f9-109">Preparing to Migrate a Database</span></span>  
 <span data-ttu-id="1b1f9-110">Passez en revue les éléments suivants lorsque vous envisagez de migrer une base de données vers le modèle de base de données partiellement autonome.</span><span class="sxs-lookup"><span data-stu-id="1b1f9-110">Review the following items when considering migrating a database to the partially contained database model.</span></span>  
  
-   <span data-ttu-id="1b1f9-111">Vous devez comprendre le modèle de base de données partiellement autonome.</span><span class="sxs-lookup"><span data-stu-id="1b1f9-111">You should understand the partially contained database model.</span></span> <span data-ttu-id="1b1f9-112">Pour plus d’informations, consultez [Bases de données autonomes](contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="1b1f9-112">For more information, see [Contained Databases](contained-databases.md).</span></span>  
  
-   <span data-ttu-id="1b1f9-113">Vous devez connaître les risques qui sont propres aux bases de données partiellement autonomes.</span><span class="sxs-lookup"><span data-stu-id="1b1f9-113">You should understand risks that are unique to partially contained databases.</span></span> <span data-ttu-id="1b1f9-114">Pour plus d'informations, consultez [Meilleures pratiques de sécurité recommandées avec les bases de données autonomes](security-best-practices-with-contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="1b1f9-114">For more information, see [Security Best Practices with Contained Databases](security-best-practices-with-contained-databases.md).</span></span>  
  
-   <span data-ttu-id="1b1f9-115">Les bases de données autonomes ne prennent pas en charge la réplication, la capture de données modifiées ou le suivi des modifications.</span><span class="sxs-lookup"><span data-stu-id="1b1f9-115">Contained databases do not support replication, change data capture, or change tracking.</span></span> <span data-ttu-id="1b1f9-116">Vérifiez que la base de données n'utilise pas ces fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="1b1f9-116">Confirm the database does not use these features.</span></span>  
  
-   <span data-ttu-id="1b1f9-117">Passez en revue la liste des fonctionnalités de base de données qui sont modifiées pour les bases de données partiellement autonomes.</span><span class="sxs-lookup"><span data-stu-id="1b1f9-117">Review the list of database features that are modified for partially contained databases.</span></span> <span data-ttu-id="1b1f9-118">Pour plus d’informations, consultez [Fonctionnalités modifiées &#40;base de données à relation contenant-contenu&#41;](modified-features-contained-database.md).</span><span class="sxs-lookup"><span data-stu-id="1b1f9-118">For more information, see [Modified Features &#40;Contained Database&#41;](modified-features-contained-database.md).</span></span>  
  
-   <span data-ttu-id="1b1f9-119">Requête [sys.dm_db_uncontained_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-uncontained-entities-transact-sql) permettant de rechercher des objets ou des fonctionnalités sans relation contenant-contenu dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="1b1f9-119">Query [sys.dm_db_uncontained_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-uncontained-entities-transact-sql) to find uncontained objects or features in the database.</span></span> <span data-ttu-id="1b1f9-120">Pour plus d'informations, consultez</span><span class="sxs-lookup"><span data-stu-id="1b1f9-120">For more information, see.</span></span>  
  
-   <span data-ttu-id="1b1f9-121">Surveillez le XEvent **database_uncontained_usage** pour voir quand des fonctionnalités sans relation contenant-contenu sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="1b1f9-121">Monitor the **database_uncontained_usage** XEvent to see when uncontained features are used.</span></span>  
  
##  <a name="enable-contained-databases"></a><a name="enable"></a> <span data-ttu-id="1b1f9-122">Activer les bases de données autonomes</span><span class="sxs-lookup"><span data-stu-id="1b1f9-122">Enable Contained Databases</span></span>  
 <span data-ttu-id="1b1f9-123">Les bases de données autonomes doivent être activées sur l'instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], avant que les bases de données autonomes puissent être créées.</span><span class="sxs-lookup"><span data-stu-id="1b1f9-123">Contained databases must be enabled on the instance of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], before contained databases can be created.</span></span>  
  
### <a name="enabling-contained-databases-using-transact-sql"></a><span data-ttu-id="1b1f9-124">Activation de bases de données autonomes à l'aide de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1b1f9-124">Enabling Contained Databases Using Transact-SQL</span></span>  
 <span data-ttu-id="1b1f9-125">L'exemple suivant active des bases de données autonomes sur l'instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b1f9-125">The following example enables contained databases on the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
```sql  
sp_configure 'contained database authentication', 1;  
GO  
RECONFIGURE ;  
GO  
```  
  
#### <a name="enabling-contained-databases-using-management-studio"></a><span data-ttu-id="1b1f9-126">Activation de bases de données autonomes à l'aide de Management Studio</span><span class="sxs-lookup"><span data-stu-id="1b1f9-126">Enabling Contained Databases Using Management Studio</span></span>  
 <span data-ttu-id="1b1f9-127">L'exemple suivant active des bases de données autonomes sur l'instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b1f9-127">The following example enables contained databases on the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
1.  <span data-ttu-id="1b1f9-128">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur le nom du serveur, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="1b1f9-128">In Object Explorer, right-click the server name, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="1b1f9-129">Dans la page **Avancé**, dans la section **Autonomie**, affectez à l’option **Activer les bases de données autonomes** la valeur **True**.</span><span class="sxs-lookup"><span data-stu-id="1b1f9-129">On the **Advanced** page, in the **Containment** section, set the **Enable Contained Databases** option to **True**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="converting-a-database-to-partially-contained"></a><a name="convert"></a> <span data-ttu-id="1b1f9-130">Conversion d'une base de données au modèle partiellement à relation contenant-contenu</span><span class="sxs-lookup"><span data-stu-id="1b1f9-130">Converting a Database to Partially Contained</span></span>  
 <span data-ttu-id="1b1f9-131">Une base de données est convertie en base de données autonome en modifiant l’option **CONTAINMENT**.</span><span class="sxs-lookup"><span data-stu-id="1b1f9-131">A database is converted to a contained database by changing the **CONTAINMENT** option.</span></span>  
  
### <a name="converting-a-database-to-partially-contained-using-transact-sql"></a><span data-ttu-id="1b1f9-132">Conversion d'une base de données au modèle partiellement à relation contenant-contenu à l'aide de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1b1f9-132">Converting a Database to Partially Contained Using Transact-SQL</span></span>  
 <span data-ttu-id="1b1f9-133">L'exemple suivant convertit une base de données nommée `Accounting` en base de données partiellement autonome.</span><span class="sxs-lookup"><span data-stu-id="1b1f9-133">The following example converts a database named `Accounting` to a partially contained database.</span></span>  
  
```sql  
USE [master]  
GO  
ALTER DATABASE [Accounting] SET CONTAINMENT = PARTIAL  
GO  
```  
  
### <a name="converting-a-database-to-partially-contained-using-management-studio"></a><span data-ttu-id="1b1f9-134">Conversion d'une base de données au modèle partiellement à relation contenant-contenu à l'aide de Management Studio</span><span class="sxs-lookup"><span data-stu-id="1b1f9-134">Converting a Database to Partially contained Using Management Studio</span></span>  
 <span data-ttu-id="1b1f9-135">L'exemple suivant convertit une base de données en base de données partiellement autonome.</span><span class="sxs-lookup"><span data-stu-id="1b1f9-135">The following example converts a database to a partially contained database.</span></span>  
  
1.  <span data-ttu-id="1b1f9-136">Dans Explorateur d’objets, développez **Bases de données**, cliquez avec le bouton droit sur la base de données à convertir, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="1b1f9-136">In Object Explorer, expand **Databases**, right-click the database to be converted, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="1b1f9-137">Dans la page **Options** , modifiez l’option **Type de relation contenant-contenu** en **Partiel**.</span><span class="sxs-lookup"><span data-stu-id="1b1f9-137">On the **Options** page, change the **Containment type** option to **Partial**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="migrating-users-to-contained-database-users"></a><a name="users"></a> <span data-ttu-id="1b1f9-138">Migration des utilisateurs vers des utilisateurs de base de données autonome</span><span class="sxs-lookup"><span data-stu-id="1b1f9-138">Migrating Users to Contained Database Users</span></span>  
 <span data-ttu-id="1b1f9-139">L'exemple suivant migre tous les utilisateurs basés sur des comptes de connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vers des utilisateurs de base de données autonome avec mots de passe.</span><span class="sxs-lookup"><span data-stu-id="1b1f9-139">The following example migrates all users that are based on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins to contained database users with passwords.</span></span> <span data-ttu-id="1b1f9-140">L'exemple exclut les comptes de connexion qui ne sont pas activés.</span><span class="sxs-lookup"><span data-stu-id="1b1f9-140">The example excludes logins that are not enabled.</span></span> <span data-ttu-id="1b1f9-141">L'exemple doit être exécuté dans la base de données autonome.</span><span class="sxs-lookup"><span data-stu-id="1b1f9-141">The example must be executed in the contained database.</span></span>  
  
```sql  
DECLARE @username sysname ;  
DECLARE user_cursor CURSOR  
    FOR   
        SELECT dp.name   
        FROM sys.database_principals AS dp  
        JOIN sys.server_principals AS sp   
        ON dp.sid = sp.sid  
        WHERE dp.authentication_type = 1 AND sp.is_disabled = 0;  
OPEN user_cursor  
FETCH NEXT FROM user_cursor INTO @username  
    WHILE @@FETCH_STATUS = 0  
    BEGIN  
        EXECUTE sp_migrate_user_to_contained   
        @username = @username,  
        @rename = N'keep_name',  
        @disablelogin = N'disable_login';  
    FETCH NEXT FROM user_cursor INTO @username  
    END  
CLOSE user_cursor ;  
DEALLOCATE user_cursor ;  
```  
  
## <a name="see-also"></a><span data-ttu-id="1b1f9-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1b1f9-142">See Also</span></span>  
 <span data-ttu-id="1b1f9-143">[Bases de données autonomes](contained-databases.md) </span><span class="sxs-lookup"><span data-stu-id="1b1f9-143">[Contained Databases](contained-databases.md) </span></span>  
 <span data-ttu-id="1b1f9-144">[sp_migrate_user_to_contained &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-migrate-user-to-contained-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1b1f9-144">[sp_migrate_user_to_contained &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-migrate-user-to-contained-transact-sql) </span></span>  
 [<span data-ttu-id="1b1f9-145">sys.dm_db_uncontained_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1b1f9-145">sys.dm_db_uncontained_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-uncontained-entities-transact-sql)  
  
  
