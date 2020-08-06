---
title: Définir ou changer le classement de la base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- collations [SQL Server], database
- database collations [SQL Server]
ms.assetid: 1379605c-1242-4ac8-ab1b-e2a2b5b1f895
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6d7f7c3e3ddba7ba0ea9701993dbe0fad3a8d975
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614652"
---
# <a name="set-or-change-the-database-collation"></a><span data-ttu-id="2b399-102">Définir ou changer le classement de la base de données</span><span class="sxs-lookup"><span data-stu-id="2b399-102">Set or Change the Database Collation</span></span>
  <span data-ttu-id="2b399-103">Cette rubrique explique comment définir et modifier le classement de base de données dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b399-103">This topic describes how set and change the database collation in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2b399-104">Si aucun classement n'est spécifié, celui du serveur est utilisé.</span><span class="sxs-lookup"><span data-stu-id="2b399-104">If no collation is specified, the server collation is used.</span></span>  
  
 <span data-ttu-id="2b399-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="2b399-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2b399-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="2b399-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2b399-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="2b399-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="2b399-108">Recommandations</span><span class="sxs-lookup"><span data-stu-id="2b399-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="2b399-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2b399-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2b399-110">**Pour définir ou modifier le classement de base de données, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="2b399-110">**To set or change the database collation, using:**</span></span>  
  
     [<span data-ttu-id="2b399-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2b399-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2b399-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2b399-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2b399-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="2b399-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="2b399-114">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="2b399-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="2b399-115">Les classements Windows Unicode seulement peuvent être utilisés uniquement avec la clause COLLATE afin d'appliquer des classements aux types de données `nchar`, `nvarchar` et `ntext` sur les données de niveau de colonne et de niveau d'expression.</span><span class="sxs-lookup"><span data-stu-id="2b399-115">Windows Unicode-only collations can only be used with the COLLATE clause to apply collations to the `nchar`, `nvarchar`, and `ntext` data types on column level and expression-level data.</span></span> <span data-ttu-id="2b399-116">Ils ne peuvent pas être utilisés avec la clause COLLATE pour modifier le classement d'une instance de serveur ou de base de données.</span><span class="sxs-lookup"><span data-stu-id="2b399-116">They cannot be used with the COLLATE clause to change the collation of a database or server instance.</span></span>  
  
-   <span data-ttu-id="2b399-117">Si le classement spécifié ou le classement utilisé par l'objet référencé utilise une page de codes non gérée par Windows, le [!INCLUDE[ssDE](../../includes/ssde-md.md)] affiche une erreur.</span><span class="sxs-lookup"><span data-stu-id="2b399-117">If the specified collation or the collation used by the referenced object uses a code page that is not supported by Windows, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] displays an error.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="2b399-118">Recommandations</span><span class="sxs-lookup"><span data-stu-id="2b399-118">Recommendations</span></span>  
  
-   <span data-ttu-id="2b399-119">Vous trouverez les noms des classements pris en charge dans [Nom de classement Windows &#40;Transact-SQL&#41;](/sql/t-sql/statements/windows-collation-name-transact-sql) et [Nom du classement SQL Server &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql). Vous pouvez également utiliser la fonction système [sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="2b399-119">You can find the supported collation names in [Windows Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/windows-collation-name-transact-sql) and [SQL Server Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql); or you can use the [sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) system function.</span></span>  
  
-   <span data-ttu-id="2b399-120">Lorsque vous modifiez le classement d'une base de données, vous changez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="2b399-120">When you change the database collation, you change the following:</span></span>  
  
    -   <span data-ttu-id="2b399-121">Toutes les colonnes `char`, `varchar`, `text`, `nchar`, `nvarchar` ou `ntext` présentes dans les tables système sont modifiées en fonction du nouveau classement.</span><span class="sxs-lookup"><span data-stu-id="2b399-121">Any `char`, `varchar`, `text`, `nchar`, `nvarchar`, or `ntext` columns in system tables are changed to the new collation.</span></span>  
  
    -   <span data-ttu-id="2b399-122">Tous les paramètres `char`, `varchar`, `text`, `nchar`, `nvarchar`, ou `ntext` existants et les valeurs de retour scalaires destinés aux procédures stockées et aux fonctions définies par l'utilisateur sont modifiés en fonction du nouveau classement.</span><span class="sxs-lookup"><span data-stu-id="2b399-122">All existing `char`, `varchar`, `text`, `nchar`, `nvarchar`, or `ntext` parameters and scalar return values for stored procedures and user-defined functions are changed to the new collation.</span></span>  
  
    -   <span data-ttu-id="2b399-123">Les types de données système `char`, `varchar`, `text`, `nchar`, `nvarchar`, ou `ntext` et tous les types de données définis par l'utilisateur sur la base de ces types de données système sont modifiés en fonction du nouveau classement par défaut.</span><span class="sxs-lookup"><span data-stu-id="2b399-123">The `char`, `varchar`, `text`, `nchar`, `nvarchar`, or `ntext` system data types, and all user-defined data types based on these system data types, are changed to the new default collation.</span></span>  
  
-   <span data-ttu-id="2b399-124">Vous pouvez modifier le classement de tous les objets créés dans une base de données utilisateur à l'aide de la clause COLLATE de l'instruction [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="2b399-124">You can change the collation of any new objects that are created in a user database by using the COLLATE clause of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement.</span></span> <span data-ttu-id="2b399-125">Cette instruction ne modifie pas le classement des colonnes dans les tables définies par l'utilisateur existantes.</span><span class="sxs-lookup"><span data-stu-id="2b399-125">This statement does not change the collation of the columns in any existing user-defined tables.</span></span> <span data-ttu-id="2b399-126">Celles-ci peuvent être modifiées à l'aide de la clause COLLECT de l'instruction [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2b399-126">These can be changed by using the COLLATE clause of [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2b399-127">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2b399-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2b399-128">Autorisations</span><span class="sxs-lookup"><span data-stu-id="2b399-128">Permissions</span></span>  
 <span data-ttu-id="2b399-129">CREATE DATABASE</span><span class="sxs-lookup"><span data-stu-id="2b399-129">CREATE DATABASE</span></span>  
 <span data-ttu-id="2b399-130">Nécessite l’autorisation CREATe DATABASE dans la base de données **Master** , ou nécessite l’autorisation CREATe any Database ou ALTER ANY DATABASE.</span><span class="sxs-lookup"><span data-stu-id="2b399-130">Requires CREATE DATABASE permission in the **master** database, or requires CREATE ANY DATABASE, or ALTER ANY DATABASE permission.</span></span>  
  
 <span data-ttu-id="2b399-131">ALTER DATABASE</span><span class="sxs-lookup"><span data-stu-id="2b399-131">ALTER DATABASE</span></span>  
 <span data-ttu-id="2b399-132">Nécessite l'autorisation ALTER sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="2b399-132">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2b399-133">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2b399-133">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-or-change-the-database-collation"></a><span data-ttu-id="2b399-134">Pour définir ou modifier le classement de base de données</span><span class="sxs-lookup"><span data-stu-id="2b399-134">To set or change the database collation</span></span>  
  
1.  <span data-ttu-id="2b399-135">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], développez cette instance, puis développez **Bases de données**.</span><span class="sxs-lookup"><span data-stu-id="2b399-135">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="2b399-136">Si vous créez une base de données, cliquez avec le bouton droit sur **Bases de données** , puis sélectionnez **Nouvelle base de données**.</span><span class="sxs-lookup"><span data-stu-id="2b399-136">If you are creating a new database, right-click **Databases** and then click **New Database**.</span></span> <span data-ttu-id="2b399-137">Si vous ne souhaitez pas définir le classement par défaut, cliquez sur la page **Options** , puis sélectionnez un classement dans la liste déroulante **Classement** .</span><span class="sxs-lookup"><span data-stu-id="2b399-137">If you do not want the default collation, click the **Options** page, and select a collation from the **Collation** drop-down list.</span></span>  
  
     <span data-ttu-id="2b399-138">Sinon, si la base de données existe déjà, cliquez avec le bouton droit sur la base de données de votre choix et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="2b399-138">Alternatively, if the database already exists, right-click the database that you want and click **Properties**.</span></span> <span data-ttu-id="2b399-139">Cliquez sur la page **Options** , puis sélectionnez un classement dans la liste déroulante **Classement** .</span><span class="sxs-lookup"><span data-stu-id="2b399-139">Click the **Options** page, and select a collation from the **Collation** drop-down list.</span></span>  
  
3.  <span data-ttu-id="2b399-140">Une fois que vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b399-140">After you are finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2b399-141">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2b399-141">Using Transact-SQL</span></span>  
  
#### <a name="to-set-the-database-collation"></a><span data-ttu-id="2b399-142">Pour définir le classement de base de données</span><span class="sxs-lookup"><span data-stu-id="2b399-142">To set the database collation</span></span>  
  
1.  <span data-ttu-id="2b399-143">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b399-143">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2b399-144">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="2b399-144">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2b399-145">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="2b399-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="2b399-146">Cet exemple montre comment utiliser la clause [COLLATE](/sql/t-sql/statements/collations) pour spécifier un nom de classement.</span><span class="sxs-lookup"><span data-stu-id="2b399-146">This example shows how to use the [COLLATE](/sql/t-sql/statements/collations) clause to specify a collation name.</span></span> <span data-ttu-id="2b399-147">L'exemple crée la base de données `MyOptionsTest` qui utilise le classement `Latin1_General_100_CS_AS_SC` .</span><span class="sxs-lookup"><span data-stu-id="2b399-147">The example creates the database `MyOptionsTest` that uses the `Latin1_General_100_CS_AS_SC` collation.</span></span> <span data-ttu-id="2b399-148">Après avoir créé la base de données, exécutez l'instruction `SELECT` pour vérifier le paramètre.</span><span class="sxs-lookup"><span data-stu-id="2b399-148">After you create the database, execute the `SELECT` statement to verify the setting.</span></span>  
  
```sql  
USE master;  
GO  
IF DB_ID (N'MyOptionsTest') IS NOT NULL  
DROP DATABASE MyOptionsTest;  
GO  
CREATE DATABASE MyOptionsTest  
COLLATE Latin1_General_100_CS_AS_SC;  
GO  
  
--Verify the collation setting.  
SELECT name, collation_name  
FROM sys.databases  
WHERE name = N'MyOptionsTest';  
GO  
  
```  
  
#### <a name="to-change-the-database-collation"></a><span data-ttu-id="2b399-149">Pour modifier le classement de la base de données</span><span class="sxs-lookup"><span data-stu-id="2b399-149">To change the database collation</span></span>  
  
1.  <span data-ttu-id="2b399-150">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b399-150">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2b399-151">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="2b399-151">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2b399-152">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="2b399-152">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="2b399-153">Cet exemple montre comment utiliser la clause [COLLATE](/sql/t-sql/statements/collations) dans une instruction [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) pour modifier le nom du classement.</span><span class="sxs-lookup"><span data-stu-id="2b399-153">This example shows how to use the [COLLATE](/sql/t-sql/statements/collations) clause in an [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement to change the collation name.</span></span> <span data-ttu-id="2b399-154">Exécutez l'instruction `SELECT` pour vérifier la modification.</span><span class="sxs-lookup"><span data-stu-id="2b399-154">Execute the `SELECT` statement to verify the change.</span></span>  
  
```sql  
USE master;  
GO  
ALTER DATABASE MyOptionsTest  
COLLATE French_CI_AS ;  
GO  
  
--Verify the collation setting.  
SELECT name, collation_name  
FROM sys.databases  
WHERE name = N'MyOptionsTest';  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b399-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2b399-155">See Also</span></span>  
 <span data-ttu-id="2b399-156">[Prise en charge d'Unicode et du classement](collation-and-unicode-support.md) </span><span class="sxs-lookup"><span data-stu-id="2b399-156">[Collation and Unicode Support](collation-and-unicode-support.md) </span></span>  
 <span data-ttu-id="2b399-157">[sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b399-157">[sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span></span>  
 <span data-ttu-id="2b399-158">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b399-158">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="2b399-159">[Nom du classement SQL Server &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b399-159">[SQL Server Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql) </span></span>  
 <span data-ttu-id="2b399-160">[Nom de classement Windows &#40;Transact-SQL&#41;](/sql/t-sql/statements/windows-collation-name-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b399-160">[Windows Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/windows-collation-name-transact-sql) </span></span>  
 <span data-ttu-id="2b399-161">[COLLATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/collations) </span><span class="sxs-lookup"><span data-stu-id="2b399-161">[COLLATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/collations) </span></span>  
 <span data-ttu-id="2b399-162">[Priorité de classement &#40;Transact-SQL&#41;](/sql/t-sql/statements/collation-precedence-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b399-162">[Collation Precedence &#40;Transact-SQL&#41;](/sql/t-sql/statements/collation-precedence-transact-sql) </span></span>  
 <span data-ttu-id="2b399-163">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b399-163">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span></span>  
 <span data-ttu-id="2b399-164">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b399-164">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="2b399-165">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b399-165">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 [<span data-ttu-id="2b399-166">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2b399-166">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
