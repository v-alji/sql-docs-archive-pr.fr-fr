---
title: Définir ou changer le classement des colonnes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- tempdb database [SQL Server], collations
- collations [SQL Server], column
ms.assetid: d7a9638b-717c-4680-9b98-8849081e08be
author: stevestein
ms.author: sstein
ms.openlocfilehash: 05b8211569b6ce83faaec043e5eb527a60f0ddab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614653"
---
# <a name="set-or-change-the-column-collation"></a><span data-ttu-id="1fb76-102">Définir ou changer le classement des colonnes</span><span class="sxs-lookup"><span data-stu-id="1fb76-102">Set or Change the Column Collation</span></span>
  <span data-ttu-id="1fb76-103">Vous pouvez remplacer le classement de la base de données pour les données `char`, `varchar`, `text`, `nchar`, `nvarchar` et `ntext` en spécifiant un classement différent pour une colonne spécifique d'une table et en utilisant l'un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="1fb76-103">You can override the database collation for `char`, `varchar`, `text`, `nchar`, `nvarchar`, and `ntext` data by specifying a different collation for a specific column of a table and using one of the following:</span></span>  
  
-   <span data-ttu-id="1fb76-104">Clause COLLATE de [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) et [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1fb76-104">The COLLATE clause of [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) and [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span> <span data-ttu-id="1fb76-105">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="1fb76-105">For example:</span></span>  
  
    ```  
    CREATE TABLE dbo.MyTable  
      (PrimaryKey   int PRIMARY KEY,  
       CharCol      varchar(10) COLLATE French_CI_AS NOT NULL  
      );  
    GO  
    ALTER TABLE dbo.MyTable ALTER COLUMN CharCol  
                varchar(10)COLLATE Latin1_General_CI_AS NOT NULL;  
    GO  
    ```  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="1fb76-106">.</span><span class="sxs-lookup"><span data-stu-id="1fb76-106">.</span></span> <span data-ttu-id="1fb76-107">Pour plus d’informations, consultez [Prise en charge d’Unicode et du classement](collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="1fb76-107">For more information, [Collation and Unicode Support](collation-and-unicode-support.md).</span></span>  
  
-   <span data-ttu-id="1fb76-108">Utilisation `Column.Collation` de la propriété dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Smo (Management Objects).</span><span class="sxs-lookup"><span data-stu-id="1fb76-108">Using the `Column.Collation` property in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="1fb76-109">Vous ne pouvez pas modifier le classement d'une colonne actuellement référencée par l'un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="1fb76-109">You cannot change the collation of a column that is currently referenced by any one of the following:</span></span>  
  
-   <span data-ttu-id="1fb76-110">une colonne calculée ;</span><span class="sxs-lookup"><span data-stu-id="1fb76-110">A computed column</span></span>  
  
-   <span data-ttu-id="1fb76-111">un index ;</span><span class="sxs-lookup"><span data-stu-id="1fb76-111">An index</span></span>  
  
-   <span data-ttu-id="1fb76-112">des statistiques de distribution, générées automatiquement ou à l'aide de l'instruction CREATE STATISTICS ;</span><span class="sxs-lookup"><span data-stu-id="1fb76-112">Distribution statistics, either generated automatically or by the CREATE STATISTICS statement</span></span>  
  
-   <span data-ttu-id="1fb76-113">une contrainte CHECK ;</span><span class="sxs-lookup"><span data-stu-id="1fb76-113">A CHECK constraint</span></span>  
  
-   <span data-ttu-id="1fb76-114">une contrainte FOREIGN KEY.</span><span class="sxs-lookup"><span data-stu-id="1fb76-114">A FOREIGN KEY constraint</span></span>  
  
 <span data-ttu-id="1fb76-115">Quand vous utilisez **tempdb**, la clause [COLLATE](/sql/t-sql/statements/collations) contient une option *database_default* pour spécifier qu’une colonne de table temporaire utilise, pour la connexion, le classement par défaut de la base de données utilisateur active à la place du classement de **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="1fb76-115">When you work with **tempdb**, the [COLLATE](/sql/t-sql/statements/collations) clause includes a *database_default* option to specify that a column in a temporary table uses the collation default of the current user database for the connection instead of the collation of **tempdb**.</span></span>  
  
## <a name="collations-and-text-columns"></a><span data-ttu-id="1fb76-116">Classements et colonnes text</span><span class="sxs-lookup"><span data-stu-id="1fb76-116">Collations and text Columns</span></span>  
 <span data-ttu-id="1fb76-117">Vous pouvez insérer ou mettre à jour les valeurs d'une colonne `text` dont le classement est différent de la page de codes du classement par défaut de la base de données.</span><span class="sxs-lookup"><span data-stu-id="1fb76-117">You can insert or update values in a `text` column whose collation is different from the code page of the default collation of the database.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1fb76-118">convertit implicitement les valeurs en fonction du classement de la colonne.</span><span class="sxs-lookup"><span data-stu-id="1fb76-118">implicitly converts the values to the collation of the column.</span></span>  
  
## <a name="collations-and-tempdb"></a><span data-ttu-id="1fb76-119">Classements et tempdb</span><span class="sxs-lookup"><span data-stu-id="1fb76-119">Collations and tempdb</span></span>  
 <span data-ttu-id="1fb76-120">La base de données **tempdb** est créée à chaque démarrage de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et a le même classement par défaut que la base de données **model** .</span><span class="sxs-lookup"><span data-stu-id="1fb76-120">The **tempdb** database is built every time [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started and has the same default collation as the **model** database.</span></span> <span data-ttu-id="1fb76-121">Il est en général identique au classement par défaut de l'instance.</span><span class="sxs-lookup"><span data-stu-id="1fb76-121">This is typically the same as the default collation of the instance.</span></span> <span data-ttu-id="1fb76-122">Si vous créez une base de données utilisateur et spécifiez un classement par défaut différent de **model**, la base de données utilisateur a un classement par défaut différent de **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="1fb76-122">If you create a user database and specify a different default collation than **model**, the user database has a different default collation than **tempdb**.</span></span> <span data-ttu-id="1fb76-123">Toutes les procédures stockées ou tables temporaires sont créées et stockées dans **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="1fb76-123">All temporary stored procedures or temporary tables are created and stored in **tempdb**.</span></span> <span data-ttu-id="1fb76-124">En d'autres termes, toutes les colonnes implicites des tables temporaires et toutes les constantes, variables et paramètres modifiables par défaut des procédures stockées temporaires ont d'autres classements que les objets comparables créés dans les tables et procédures stockées permanentes.</span><span class="sxs-lookup"><span data-stu-id="1fb76-124">This means that all implicit columns in temporary tables and all coercible-default constants, variables, and parameters in temporary stored procedures have collations that are different from comparable objects created in permanent tables and stored procedures.</span></span>  
  
 <span data-ttu-id="1fb76-125">Ceci pourrait provoquer des problèmes de non-correspondance de classement entre les bases de données définies par l'utilisateur et les objets de base de données système.</span><span class="sxs-lookup"><span data-stu-id="1fb76-125">This could lead to problems with a mismatch in collations between user-defined databases and system database objects.</span></span> <span data-ttu-id="1fb76-126">Par exemple, une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilise le classement Latin1_General_CS_AS et vous exécutez les instructions suivantes :</span><span class="sxs-lookup"><span data-stu-id="1fb76-126">For example, an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the Latin1_General_CS_AS collation and you execute the following statements:</span></span>  
  
```  
CREATE DATABASE TestDB COLLATE Estonian_CS_AS;  
USE TestDB;  
CREATE TABLE TestPermTab (PrimaryKey int PRIMARY KEY, Col1 nchar );  
```  
  
 <span data-ttu-id="1fb76-127">Dans ce système, la base de données **tempdb** utilise le classement Latin1_General_CS_AS avec la page de codes 1252, et `TestDB` et `TestPermTab.Col1` utilisent le classement `Estonian_CS_AS` avec la page de codes 1257.</span><span class="sxs-lookup"><span data-stu-id="1fb76-127">In this system, the **tempdb** database uses the Latin1_General_CS_AS collation with code page 1252, and `TestDB` and `TestPermTab.Col1` use the `Estonian_CS_AS` collation with code page 1257.</span></span> <span data-ttu-id="1fb76-128">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="1fb76-128">For example:</span></span>  
  
```  
USE TestDB;  
GO  
-- Create a temporary table with the same column declarations  
-- as TestPermTab  
CREATE TABLE #TestTempTab (PrimaryKey int PRIMARY KEY, Col1 nchar );  
INSERT INTO #TestTempTab  
         SELECT * FROM TestPermTab;  
GO  
```  
  
 <span data-ttu-id="1fb76-129">Dans l’exemple précédent, la base de données **tempdb** utilise le classement Latin1_General_CS_AS, et `TestDB` et `TestTab.Col1` utilisent le classement `Estonian_CS_AS` .</span><span class="sxs-lookup"><span data-stu-id="1fb76-129">With the previous example, the **tempdb** database uses the Latin1_General_CS_AS collation, and `TestDB` and `TestTab.Col1` use the `Estonian_CS_AS` collation.</span></span> <span data-ttu-id="1fb76-130">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="1fb76-130">For example:</span></span>  
  
```  
SELECT * FROM TestPermTab AS a INNER JOIN #TestTempTab on a.Col1 = #TestTempTab.Col1;  
```  
  
 <span data-ttu-id="1fb76-131">Comme **tempdb** utilise le classement par défaut du serveur et que `TestPermTab.Col1` utilise un autre classement, SQL Server affiche l’erreur suivante : impossible de résoudre le conflit de classement entre « Latin1_General_100_CI_AS_KS_WS » et « Chinese_Simplified_Pinyin_100_CI_AS » dans l’opération égal à.</span><span class="sxs-lookup"><span data-stu-id="1fb76-131">Because **tempdb** uses the default server collation and `TestPermTab.Col1` uses a different collation, SQL Server returns this error: "Cannot resolve collation conflict between 'Latin1_General_CI_AS_KS_WS' and 'Estonian_CS_AS' in equal to operation."</span></span>  
  
 <span data-ttu-id="1fb76-132">Pour éviter l'erreur, vous pouvez utiliser une des solutions suivantes :</span><span class="sxs-lookup"><span data-stu-id="1fb76-132">To prevent the error, you can use one of the following alternatives:</span></span>  
  
-   <span data-ttu-id="1fb76-133">Spécifiez que la colonne de table temporaire utilise le classement par défaut de la base de données utilisateur à la place de **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="1fb76-133">Specify that the temporary table column use the default collation of the user database, not **tempdb**.</span></span> <span data-ttu-id="1fb76-134">Cela permet à la table temporaire de fonctionner avec des tables formatées de la même manière dans différentes bases de données, si votre système l'exige.</span><span class="sxs-lookup"><span data-stu-id="1fb76-134">This enables the temporary table to work with similarly formatted tables in multiple databases, if that is required of your system.</span></span>  
  
    ```  
    CREATE TABLE #TestTempTab  
       (PrimaryKey int PRIMARY KEY,  
        Col1 nchar COLLATE database_default  
       );  
    ```  
  
-   <span data-ttu-id="1fb76-135">Spécifiez le classement approprié pour la colonne `#TestTempTab` :</span><span class="sxs-lookup"><span data-stu-id="1fb76-135">Specify the correct collation for the `#TestTempTab` column:</span></span>  
  
    ```  
    CREATE TABLE #TestTempTab  
       (PrimaryKey int PRIMARY KEY,  
        Col1 nchar COLLATE Estonian_CS_AS  
       );  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1fb76-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1fb76-136">See Also</span></span>  
 <span data-ttu-id="1fb76-137">[Définir ou modifier le classement du serveur](set-or-change-the-server-collation.md) </span><span class="sxs-lookup"><span data-stu-id="1fb76-137">[Set or Change the Server Collation](set-or-change-the-server-collation.md) </span></span>  
 <span data-ttu-id="1fb76-138">[Définir ou modifier le classement de la base de données](set-or-change-the-database-collation.md) </span><span class="sxs-lookup"><span data-stu-id="1fb76-138">[Set or Change the Database Collation](set-or-change-the-database-collation.md) </span></span>  
 [<span data-ttu-id="1fb76-139">Prise en charge d'Unicode et du classement</span><span class="sxs-lookup"><span data-stu-id="1fb76-139">Collation and Unicode Support</span></span>](collation-and-unicode-support.md)  
  
  
