---
title: Modifier les paramètres de configuration d’une base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- database configuration [SQL Server]
- configuration options [SQL Server], databases
- modifying database configuration settings
ms.assetid: c29c3385-5043-400f-bb4e-044a4c9a9a4b
author: stevestein
ms.author: sstein
ms.openlocfilehash: f9edecefae5154bb66a65e38724d9e77a94fdbb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709591"
---
# <a name="change-the-configuration-settings-for-a-database"></a><span data-ttu-id="b7561-102">Modifier les paramètres de configuration d'une base de données</span><span class="sxs-lookup"><span data-stu-id="b7561-102">Change the Configuration Settings for a Database</span></span>
  <span data-ttu-id="b7561-103">Cette rubrique explique comment modifier les options de base de données dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7561-103">This topic describes how to change database-level options in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b7561-104">Ces options sont spécifiques à chaque base de données et n'affectent pas les autres.</span><span class="sxs-lookup"><span data-stu-id="b7561-104">These options are unique to each database and do not affect other databases.</span></span>  
  
 <span data-ttu-id="b7561-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="b7561-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b7561-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="b7561-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b7561-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="b7561-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b7561-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b7561-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b7561-109">**Pour modifier les paramètres d'option d'une base de données, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="b7561-109">**To change the option settings for a database, using:**</span></span>  
  
     [<span data-ttu-id="b7561-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b7561-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b7561-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b7561-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b7561-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="b7561-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b7561-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="b7561-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b7561-114">Seuls l’administrateur système, le propriétaire de la base de données, les membres des rôles serveur fixes **sysadmin** et **dbcreator** et des rôles de base de données fixes **db_owner** peuvent modifier ces options.</span><span class="sxs-lookup"><span data-stu-id="b7561-114">Only the system administrator, database owner, members of the **sysadmin** and **dbcreator** fixed server roles and **db_owner** fixed database roles can modify these options.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b7561-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b7561-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b7561-116">Autorisations</span><span class="sxs-lookup"><span data-stu-id="b7561-116">Permissions</span></span>  
 <span data-ttu-id="b7561-117">Nécessite l'autorisation ALTER sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="b7561-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b7561-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b7561-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-option-settings-for-a-database"></a><span data-ttu-id="b7561-119">Pour modifier les paramètres d'option d'une base de données</span><span class="sxs-lookup"><span data-stu-id="b7561-119">To change the option settings for a database</span></span>  
  
1.  <span data-ttu-id="b7561-120">Dans l’Explorateur d’objets, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] , développez le serveur, puis **Bases de données**, cliquez avec le bouton droit sur une base de données, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b7561-120">In Object Explorer, connect to a [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance, expand the server, expand **Databases**, right-click a database, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b7561-121">Dans la boîte de dialogue **Propriétés de la base de données** , cliquez sur **Options** pour accéder à la plupart des paramètres de configuration.</span><span class="sxs-lookup"><span data-stu-id="b7561-121">In the **Database Properties** dialog box, click **Options** to access most of the configuration settings.</span></span> <span data-ttu-id="b7561-122">Les configurations de fichiers et de groupes de fichiers, la mise en miroir et la copie des journaux de transactions sont sur leurs pages respectives.</span><span class="sxs-lookup"><span data-stu-id="b7561-122">File and filegroup configurations, mirroring and log shipping are on their respective pages.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b7561-123">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b7561-123">Using Transact-SQL</span></span>  
  
#### <a name="to-change-the-option-settings-for-a-database"></a><span data-ttu-id="b7561-124">Pour modifier les paramètres d'option d'une base de données</span><span class="sxs-lookup"><span data-stu-id="b7561-124">To change the option settings for a database</span></span>  
  
1.  <span data-ttu-id="b7561-125">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7561-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b7561-126">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="b7561-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b7561-127">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="b7561-127">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b7561-128">Cet exemple définit les options de mode de récupération et de vérification de pages de données pour l'exemple de base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b7561-128">This example sets the recovery model and data page verification options for the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase7](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase7)]  
  
 <span data-ttu-id="b7561-129">Pour plus d’exemples, consultez [Options ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="b7561-129">For more examples, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7561-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b7561-130">See Also</span></span>  
 <span data-ttu-id="b7561-131">[Niveau de compatibilité ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span><span class="sxs-lookup"><span data-stu-id="b7561-131">[ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span></span>  
 <span data-ttu-id="b7561-132">[Mise en miroir de bases de données ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="b7561-132">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="b7561-133">[ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span><span class="sxs-lookup"><span data-stu-id="b7561-133">[ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span></span>  
 <span data-ttu-id="b7561-134">[Modifier le nom d'une base de données](rename-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="b7561-134">[Rename a Database](rename-a-database.md) </span></span>  
 [<span data-ttu-id="b7561-135">Réduire une base de données</span><span class="sxs-lookup"><span data-stu-id="b7561-135">Shrink a Database</span></span>](shrink-a-database.md)  
  
  
