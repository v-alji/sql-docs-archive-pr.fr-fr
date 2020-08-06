---
title: Créer une base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], creating
- database creation [SQL Server], SQL Server Management Studio
- creating databases
ms.assetid: 4c4beea2-6cbc-4352-9db6-49ea8130bb64
author: stevestein
ms.author: sstein
ms.openlocfilehash: fe42e394482e3abf4d87c00c6e79ee84db6ba278
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604567"
---
# <a name="create-a-database"></a><span data-ttu-id="09743-102">Créer une base de données</span><span class="sxs-lookup"><span data-stu-id="09743-102">Create a Database</span></span>
  <span data-ttu-id="09743-103">Cette rubrique explique comment créer une base de données dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09743-103">This topic describes how to create a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="09743-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="09743-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="09743-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="09743-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="09743-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="09743-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="09743-107">Composants requis</span><span class="sxs-lookup"><span data-stu-id="09743-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="09743-108">Recommandations</span><span class="sxs-lookup"><span data-stu-id="09743-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="09743-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="09743-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="09743-110">**Pour créer une base de données, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="09743-110">**To create a database, using:**</span></span>  
  
     [<span data-ttu-id="09743-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="09743-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="09743-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="09743-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="09743-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="09743-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="09743-114">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="09743-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="09743-115">Vous pouvez spécifier un maximum de 32 767 bases de données sur une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09743-115">A maximum of 32,767 databases can be specified on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="09743-116">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="09743-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="09743-117">L'instruction CREATE DATABASE doit être exécutée en mode de validation automatique (mode de gestion des transactions par défaut) et n'est pas autorisée dans une transaction explicite ou implicite.</span><span class="sxs-lookup"><span data-stu-id="09743-117">The CREATE DATABASE statement must run in autocommit mode (the default transaction management mode) and is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="09743-118">Recommandations</span><span class="sxs-lookup"><span data-stu-id="09743-118">Recommendations</span></span>  
  
-   <span data-ttu-id="09743-119">La base de données [master](master-database.md) doit être sauvegardée chaque fois qu'une base de données utilisateur est créée, modifiée ou supprimée.</span><span class="sxs-lookup"><span data-stu-id="09743-119">The [master](master-database.md) database should be backed up whenever a user database is created, modified, or dropped.</span></span>  
  
-   <span data-ttu-id="09743-120">Lorsque vous créez une base de données, attribuez aux fichiers une taille aussi grande que possible, en tenant compte du volume maximal de données qu'est censée contenir la base de données.</span><span class="sxs-lookup"><span data-stu-id="09743-120">When you create a database, make the data files as large as possible based on the maximum amount of data you expect in the database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="09743-121">Sécurité</span><span class="sxs-lookup"><span data-stu-id="09743-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="09743-122">Autorisations</span><span class="sxs-lookup"><span data-stu-id="09743-122">Permissions</span></span>  
 <span data-ttu-id="09743-123">Nécessite l'autorisation CREATE DATABASE sur la base de données master, ou l'autorisation ALTER ANY DATABASE ou VIEW ANY DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="09743-123">Requires CREATE DATABASE permission in the master database, or requires CREATE ANY DATABASE, or ALTER ANY DATABASE permission.</span></span>  
  
 <span data-ttu-id="09743-124">Pour garder le contrôle de l'utilisation du disque sur une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], l'autorisation de création de bases de données est généralement limitée à quelques comptes de connexion.</span><span class="sxs-lookup"><span data-stu-id="09743-124">To maintain control over disk use on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], permission to create databases is typically limited to a few login accounts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="09743-125">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="09743-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-database"></a><span data-ttu-id="09743-126">Pour créer une base de données</span><span class="sxs-lookup"><span data-stu-id="09743-126">To create a database</span></span>  
  
1.  <span data-ttu-id="09743-127">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="09743-127">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="09743-128">Cliquez avec le bouton droit sur **Bases de données**, puis cliquez sur **Nouvelle base de données**.</span><span class="sxs-lookup"><span data-stu-id="09743-128">Right-click **Databases**, and then click **New Database**.</span></span>  
  
3.  <span data-ttu-id="09743-129">Dans **Nouvelle base de données**, entrez le nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="09743-129">In **New Database**, enter a database name.</span></span>  
  
4.  <span data-ttu-id="09743-130">Pour créer la base de données en acceptant toutes les valeurs par défaut, cliquez sur **OK**, sinon effectuez les étapes facultatives ci-après.</span><span class="sxs-lookup"><span data-stu-id="09743-130">To create the database by accepting all default values, click **OK**; otherwise, continue with the following optional steps.</span></span>  
  
5.  <span data-ttu-id="09743-131">Pour changer le nom du propriétaire, cliquez sur ( **...** ) pour sélectionner un autre propriétaire.</span><span class="sxs-lookup"><span data-stu-id="09743-131">To change the owner name, click (**...**) to select another owner.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="09743-132">L’option **Utiliser l’indexation de texte intégral** est toujours activée et estompée, car toutes les bases de données utilisateur sont activées pour la recherche en texte intégral à compter de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09743-132">The **Use full-text indexing** option is always checked and dimmed because, beginning in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], all user databases are full-text enabled.</span></span>  
  
6.  <span data-ttu-id="09743-133">Pour modifier les valeurs par défaut des données primaires et des fichiers journaux de transactions, dans la grille **Fichiers de la base de données** , cliquez sur la cellule appropriée, puis entrez la nouvelle valeur.</span><span class="sxs-lookup"><span data-stu-id="09743-133">To change the default values of the primary data and transaction log files, in the **Database files** grid, click the appropriate cell and enter the new value.</span></span> <span data-ttu-id="09743-134">Pour plus d’informations, consultez [Ajouter des fichiers de données ou journaux à une base de données](add-data-or-log-files-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="09743-134">For more information, see [Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md).</span></span>  
  
7.  <span data-ttu-id="09743-135">Pour modifier le classement de la base de données, sélectionnez la page **Options** , puis sélectionnez un classement dans la liste.</span><span class="sxs-lookup"><span data-stu-id="09743-135">To change the collation of the database, select the **Options** page, and then select a collation from the list.</span></span>  
  
8.  <span data-ttu-id="09743-136">Pour modifier le mode de récupération, sélectionnez la page **Options** , puis sélectionnez un mode de récupération dans la liste.</span><span class="sxs-lookup"><span data-stu-id="09743-136">To change the recovery model, select the **Options** page and select a recovery model from the list.</span></span>  
  
9. <span data-ttu-id="09743-137">Pour modifier les options de la base de données, sélectionnez la page **Options** , puis apportez les modifications de votre choix.</span><span class="sxs-lookup"><span data-stu-id="09743-137">To change database options, select the **Options** page, and then modify the database options.</span></span> <span data-ttu-id="09743-138">Pour obtenir une description de chaque option, consultez [Options ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="09743-138">For a description of each option, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
10. <span data-ttu-id="09743-139">Pour ajouter un nouveau groupe de fichiers, cliquez sur la page **Groupes de fichiers** .</span><span class="sxs-lookup"><span data-stu-id="09743-139">To add a new filegroup, click the **Filegroups** page.</span></span> <span data-ttu-id="09743-140">Cliquez sur **Ajouter** , puis entrez les valeurs du groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="09743-140">Click **Add** and then enter the values for the filegroup.</span></span>  
  
11. <span data-ttu-id="09743-141">Pour ajouter une propriété étendue à la base de données, sélectionnez la page **Propriétés étendues** .</span><span class="sxs-lookup"><span data-stu-id="09743-141">To add an extended property to the database, select the **Extended Properties** page.</span></span>  
  
    1.  <span data-ttu-id="09743-142">Dans la colonne **Nom** , entrez le nom de la propriété étendue.</span><span class="sxs-lookup"><span data-stu-id="09743-142">In the **Name** column, enter a name for the extended property.</span></span>  
  
    2.  <span data-ttu-id="09743-143">Dans la colonne **Valeur** , entrez le texte de la propriété étendue.</span><span class="sxs-lookup"><span data-stu-id="09743-143">In the **Value** column, enter the extended property text.</span></span> <span data-ttu-id="09743-144">Par exemple, vous pouvez entrer une description de la base de données.</span><span class="sxs-lookup"><span data-stu-id="09743-144">For example, enter one or more statements that describe the database.</span></span>  
  
12. <span data-ttu-id="09743-145">Pour créer la base de données, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="09743-145">To create the database, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="09743-146">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="09743-146">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-database"></a><span data-ttu-id="09743-147">Pour créer une base de données</span><span class="sxs-lookup"><span data-stu-id="09743-147">To create a database</span></span>  
  
1.  <span data-ttu-id="09743-148">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09743-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="09743-149">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="09743-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="09743-150">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="09743-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="09743-151">Cet exemple crée la base de données `Sales`.</span><span class="sxs-lookup"><span data-stu-id="09743-151">This example creates the database `Sales`.</span></span> <span data-ttu-id="09743-152">Le mot clé PRIMARY n'étant pas utilisé, le premier fichier (`Sales`_`dat`) devient le fichier principal.</span><span class="sxs-lookup"><span data-stu-id="09743-152">Because the keyword PRIMARY is not used, the first file (`Sales`_`dat`) becomes the primary file.</span></span> <span data-ttu-id="09743-153">Le paramètre SIZE n'étant spécifié ni en Mo ni en Ko pour le fichier `Sales`\_`dat` , la valeur par défaut est Mo et il est alloué en mégaoctets.</span><span class="sxs-lookup"><span data-stu-id="09743-153">Because neither MB nor KB is specified in the SIZE parameter for the `Sales`\_`dat` file, it uses MB and is allocated in megabytes.</span></span> <span data-ttu-id="09743-154">La base de données `Sales`\_`log` est alloué en mégaoctets car le suffixe `MB` est défini explicitement dans le paramètre `SIZE` .</span><span class="sxs-lookup"><span data-stu-id="09743-154">The `Sales`\_`log` file is allocated in megabytes because the `MB` suffix is explicitly stated in the `SIZE` parameter.</span></span>  
  
```sql  
USE master ;  
GO  
CREATE DATABASE Sales  
ON   
( NAME = Sales_dat,  
    FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\saledat.mdf',  
    SIZE = 10,  
    MAXSIZE = 50,  
    FILEGROWTH = 5 )  
LOG ON  
( NAME = Sales_log,  
    FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\salelog.ldf',  
    SIZE = 5MB,  
    MAXSIZE = 25MB,  
    FILEGROWTH = 5MB ) ;  
GO  
```  
  
 <span data-ttu-id="09743-155">Pour obtenir plus d’exemples, consultez [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="09743-155">For more examples, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09743-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="09743-156">See Also</span></span>  
 <span data-ttu-id="09743-157">[Database Files and Filegroups](database-files-and-filegroups.md) </span><span class="sxs-lookup"><span data-stu-id="09743-157">[Database Files and Filegroups](database-files-and-filegroups.md) </span></span>  
 <span data-ttu-id="09743-158">[Attacher et détacher une base de données &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="09743-158">[Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span></span>  
 <span data-ttu-id="09743-159">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="09743-159">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="09743-160">Ajouter des fichiers de données ou journaux à une base de données</span><span class="sxs-lookup"><span data-stu-id="09743-160">Add Data or Log Files to a Database</span></span>](add-data-or-log-files-to-a-database.md)  
  
  
