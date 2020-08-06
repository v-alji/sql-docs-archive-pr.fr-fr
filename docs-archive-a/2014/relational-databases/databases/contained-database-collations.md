---
title: Classements de base de données autonome | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- contained database, collations
ms.assetid: 4b44f6b9-2359-452f-8bb1-5520f2528483
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2648dbedea7708c4f39c922c56bba96cf38b0c0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702971"
---
# <a name="contained-database-collations"></a><span data-ttu-id="d71f0-102">Classements de base de données autonome</span><span class="sxs-lookup"><span data-stu-id="d71f0-102">Contained Database Collations</span></span>
  <span data-ttu-id="d71f0-103">Diverses propriétés affectent l'ordre de tri et la sémantique d'égalité des données textuelles, notamment le respect de la casse, le respect des accents et la langue de base utilisée.</span><span class="sxs-lookup"><span data-stu-id="d71f0-103">Various properties affect the sort order and equality semantics of textual data, including case sensitivity, accent sensitivity, and the base language being used.</span></span> <span data-ttu-id="d71f0-104">Ces qualités sont exprimées à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] par le choix du classement des données.</span><span class="sxs-lookup"><span data-stu-id="d71f0-104">These qualities are expressed to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through the choice of collation for the data.</span></span> <span data-ttu-id="d71f0-105">Pour une explication plus approfondie des classements eux-mêmes, consultez [Prise en charge d’Unicode et du classement](../collations/collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="d71f0-105">For a more in-depth discussion of collations themselves, see [Collation and Unicode Support](../collations/collation-and-unicode-support.md).</span></span>  
  
 <span data-ttu-id="d71f0-106">Les classements ne s'appliquent pas seulement aux données stockées dans les tables utilisateur, mais à tout le texte géré par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], notamment les métadonnées, les objets temporaires, les noms de variable, etc. Leur gestion est différente dans une base de données autonome et dans une base de données non autonome.</span><span class="sxs-lookup"><span data-stu-id="d71f0-106">Collations apply not only to data stored in user tables, but to all text handled by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], including metadata, temporary objects, variable names, etc. The handling of these differs in contained and non-contained databases.</span></span> <span data-ttu-id="d71f0-107">Cette modification n'affecte pas de nombreux utilisateurs, mais permet l'indépendance et l'uniformité des instances.</span><span class="sxs-lookup"><span data-stu-id="d71f0-107">This change will not affect many users, but helps provide instance independence and uniformity.</span></span> <span data-ttu-id="d71f0-108">Cependant, elle peut provoquer également quelques confusions, ainsi que des problèmes pour les sessions qui accèdent à la fois à des bases de données autonomes et à des bases de données non autonomes.</span><span class="sxs-lookup"><span data-stu-id="d71f0-108">But this may also cause some confusion, as well as problems for sessions that access both contained and non-contained databases.</span></span>  
  
 <span data-ttu-id="d71f0-109">Cette rubrique apporte des éclaircissements sur le contenu de la modification et indique où celle-ci peut entraîner des problèmes.</span><span class="sxs-lookup"><span data-stu-id="d71f0-109">This topic clarifies the content of the change, and examines areas where the change may cause problems.</span></span>  
  
## <a name="non-contained-databases"></a><span data-ttu-id="d71f0-110">Bases de données sans relation contenant-contenu</span><span class="sxs-lookup"><span data-stu-id="d71f0-110">Non-Contained Databases</span></span>  
 <span data-ttu-id="d71f0-111">Toutes les bases de données ont un classement par défaut (qui peut être défini lors de la création ou de la modification d'une base de données).</span><span class="sxs-lookup"><span data-stu-id="d71f0-111">All databases have a default collation (which can be set when creating or altering a database.</span></span> <span data-ttu-id="d71f0-112">Ce classement est utilisé pour toutes les métadonnées de la base de données, et comme valeur par défaut de toutes les colonnes de chaîne dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="d71f0-112">This collation is used for all metadata in the database, as well as the default for all string columns within the database.</span></span> <span data-ttu-id="d71f0-113">Les utilisateurs peuvent choisir un classement différent pour une colonne particulière à l'aide de la clause `COLLATE`.</span><span class="sxs-lookup"><span data-stu-id="d71f0-113">Users can choose a different collation for any particular column by using the `COLLATE` clause.</span></span>  
  
### <a name="example-1"></a><span data-ttu-id="d71f0-114">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="d71f0-114">Example 1</span></span>  
 <span data-ttu-id="d71f0-115">Par exemple, supposons que nous travaillons à Beijing et que nous utilisons un classement chinois :</span><span class="sxs-lookup"><span data-stu-id="d71f0-115">For example, if we were working in Beijing, we might use a Chinese collation:</span></span>  
  
```sql  
ALTER DATABASE MyDB COLLATE Chinese_Simplified_Pinyin_100_CI_AS;  
```  
  
 <span data-ttu-id="d71f0-116">Si nous créons une colonne, son classement par défaut sera ce classement chinois, mais nous pouvons en choisir un autre si nous le voulons :</span><span class="sxs-lookup"><span data-stu-id="d71f0-116">Now if we create a column, its default collation will be this Chinese collation, but we can choose another one if we want:</span></span>  
  
```sql  
CREATE TABLE MyTable  
      (mycolumn1 nvarchar,  
      mycolumn2 nvarchar COLLATE Frisian_100_CS_AS);  
GO  
SELECT name, collation_name  
FROM sys.columns  
WHERE name LIKE 'mycolumn%' ;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```sql  
name            collation_name  
--------------- ----------------------------------  
mycolumn1       Chinese_Simplified_Pinyin_100_CI_AS  
mycolumn2       Frisian_100_CS_AS  
```  
  
 <span data-ttu-id="d71f0-117">Cela semble relativement simple, mais plusieurs problèmes se posent.</span><span class="sxs-lookup"><span data-stu-id="d71f0-117">This appears relatively simple, but several problems arise.</span></span> <span data-ttu-id="d71f0-118">Étant donné que le classement d’une colonne dépend de la base de données dans laquelle la table est créée, des problèmes se posent lors de l’utilisation de tables temporaires qui sont stockées dans `tempdb` .</span><span class="sxs-lookup"><span data-stu-id="d71f0-118">Because the collation for a column is dependent on the database in which the table is created, problems arise with the use of temporary tables which are stored in `tempdb`.</span></span> <span data-ttu-id="d71f0-119">Le classement de `tempdb` correspond généralement au classement de l’instance, qui ne doit pas nécessairement correspondre au classement de la base de données.</span><span class="sxs-lookup"><span data-stu-id="d71f0-119">The collation of `tempdb` usually matches the collation for the instance, which does not have to match the database collation.</span></span>  
  
### <a name="example-2"></a><span data-ttu-id="d71f0-120">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="d71f0-120">Example 2</span></span>  
 <span data-ttu-id="d71f0-121">Par exemple, examinez la base de données (chinoise) ci-dessus utilisée sur une instance avec un classement **Latin1_General** :</span><span class="sxs-lookup"><span data-stu-id="d71f0-121">For example, consider the (Chinese) database above when used on an instance with a **Latin1_General** collation:</span></span>  
  
```sql  
CREATE TABLE T1 (T1_txt nvarchar(max)) ;  
GO  
CREATE TABLE #T2 (T2_txt nvarchar(max)) ;  
GO  
```  
  
 <span data-ttu-id="d71f0-122">À première vue, ces deux tables semblent avoir le même schéma, mais comme les classements des bases de données diffèrent, les valeurs sont en fait incompatibles :</span><span class="sxs-lookup"><span data-stu-id="d71f0-122">At first glance, these two tables look like they have the same schema, but since the collations of the databases differ, the values are actually incompatible:</span></span>  
  
```  
SELECT T1_txt, T2_txt  
FROM T1   
JOIN #T2   
    ON T1.T1_txt = #T2.T2_txt  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 <span data-ttu-id="d71f0-123">Msg 468, Niveau 16, État 9, Ligne 2</span><span class="sxs-lookup"><span data-stu-id="d71f0-123">Msg 468, Level 16, State 9, Line 2</span></span>  
  
 <span data-ttu-id="d71f0-124">Impossible de résoudre le conflit de classement entre « Latin1_General_100_CI_AS_KS_WS_SC » et « Chinese_Simplified_Pinyin_100_CI_AS » dans l'opération égal à.</span><span class="sxs-lookup"><span data-stu-id="d71f0-124">Cannot resolve the collation conflict between "Latin1_General_100_CI_AS_KS_WS_SC" and Chinese_Simplified_Pinyin_100_CI_AS" in the equal to operation.</span></span>  
  
 <span data-ttu-id="d71f0-125">Nous pouvons résoudre ce problème en classant la table temporaire de façon explicite.</span><span class="sxs-lookup"><span data-stu-id="d71f0-125">We can fix this by explicitly collating the temporary table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d71f0-126">simplifie quelque peu cette opération en fournissant le mot clé `DATABASE_DEFAULT` pour la clause `COLLATE`.</span><span class="sxs-lookup"><span data-stu-id="d71f0-126">makes this somewhat easier by providing the `DATABASE_DEFAULT` keyword for the `COLLATE` clause.</span></span>  
  
```sql  
CREATE TABLE T1 (T1_txt nvarchar(max)) ;  
GO  
CREATE TABLE #T2 (T2_txt nvarchar(max) COLLATE DATABASE_DEFAULT);  
GO  
SELECT T1_txt, T2_txt  
FROM T1   
JOIN #T2   
    ON T1.T1_txt = #T2.T2_txt ;  
```  
  
 <span data-ttu-id="d71f0-127">Ce code s'exécute maintenant sans erreur.</span><span class="sxs-lookup"><span data-stu-id="d71f0-127">This now runs without error.</span></span>  
  
 <span data-ttu-id="d71f0-128">Nous pouvons également consulter le comportement dépendant du classement avec des variables.</span><span class="sxs-lookup"><span data-stu-id="d71f0-128">We can also see collation-dependent behavior with variables.</span></span> <span data-ttu-id="d71f0-129">Observez la fonction suivante :</span><span class="sxs-lookup"><span data-stu-id="d71f0-129">Consider the following function:</span></span>  
  
```  
CREATE FUNCTION f(@x INT) RETURNS INT  
AS BEGIN   
      DECLARE @I INT = 1  
      DECLARE @?? INT = 2  
      RETURN @x * @i  
END;  
```  
  
 <span data-ttu-id="d71f0-130">C'est une fonction assez particulière.</span><span class="sxs-lookup"><span data-stu-id="d71f0-130">This is a rather peculiar function.</span></span> <span data-ttu-id="d71f0-131">Dans un classement qui respecte la casse, le @i dans la clause return ne peut pas être lié à @I ou à @ ??.</span><span class="sxs-lookup"><span data-stu-id="d71f0-131">In a case-sensitive collation, the @i in the return clause cannot bind to either @I or @??.</span></span> <span data-ttu-id="d71f0-132">Dans un classement Latin1_General sans respect de la casse, @i est lié à @I, et la fonction retourne 1.</span><span class="sxs-lookup"><span data-stu-id="d71f0-132">In a case-insensitive Latin1_General collation, @i binds to @I, and the function returns 1.</span></span> <span data-ttu-id="d71f0-133">Mais dans un classement turc ne respectant pas la casse, est @i lié à @ ??, et la fonction retourne 2.</span><span class="sxs-lookup"><span data-stu-id="d71f0-133">But in a case-insensitive Turkish collation, @i binds to @??, and the function returns 2.</span></span> <span data-ttu-id="d71f0-134">Cela peut causer des dégâts dans une base de données qui se déplace entre des instances aux classements différents.</span><span class="sxs-lookup"><span data-stu-id="d71f0-134">This can wreak havoc on a database that moves between instances with different collations.</span></span>  
  
## <a name="contained-databases"></a><span data-ttu-id="d71f0-135">Bases de données autonomes</span><span class="sxs-lookup"><span data-stu-id="d71f0-135">Contained Databases</span></span>  
 <span data-ttu-id="d71f0-136">Comme un objectif de la conception de bases de données autonomes est de les rendre autonomes, la dépendance de l'instance et des classements de `tempdb` doit être supprimée.</span><span class="sxs-lookup"><span data-stu-id="d71f0-136">Since a design objective of contained databases is to make them self-contained, the dependence on the instance and `tempdb` collations must be severed.</span></span> <span data-ttu-id="d71f0-137">Pour cela, les bases de données autonomes présentent le concept de classement de catalogue.</span><span class="sxs-lookup"><span data-stu-id="d71f0-137">To do this, contained databases introduce the concept of the catalog collation.</span></span> <span data-ttu-id="d71f0-138">Le classement de catalogue est utilisé pour les métadonnées système et les objets transitoires.</span><span class="sxs-lookup"><span data-stu-id="d71f0-138">The catalog collation is used for system metadata and transient objects.</span></span> <span data-ttu-id="d71f0-139">Des informations complémentaires sont fournies ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="d71f0-139">Details are provided below.</span></span>  
  
 <span data-ttu-id="d71f0-140">Dans une base de données autonome, le classement de catalogue est **Latin1_General_100_CI_AS_WS_KS_SC**.</span><span class="sxs-lookup"><span data-stu-id="d71f0-140">In a contained database, the catalog collation **Latin1_General_100_CI_AS_WS_KS_SC**.</span></span> <span data-ttu-id="d71f0-141">Ce classement est le même pour toutes les bases de données autonomes sur toutes les instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et ne peut pas être changé.</span><span class="sxs-lookup"><span data-stu-id="d71f0-141">This collation is the same for all contained databases on all instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and cannot be changed.</span></span>  
  
 <span data-ttu-id="d71f0-142">Le classement de base de données est conservé, mais est utilisé uniquement comme classement par défaut des données utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d71f0-142">The database collation is retained, but is only used as the default collation for user data.</span></span> <span data-ttu-id="d71f0-143">Par défaut, le classement de base de données est égal au classement de la base de données model, mais peut être modifié par l’utilisateur via une `CREATE` `ALTER DATABASE` commande ou comme avec les bases de données sans relation contenant-contenu.</span><span class="sxs-lookup"><span data-stu-id="d71f0-143">By default, the database collation is equal to the model database collation, but can be changed by the user through a `CREATE` or `ALTER DATABASE` command as with non-contained databases.</span></span>  
  
 <span data-ttu-id="d71f0-144">Un nouveau mot clé, `CATALOG_DEFAULT`, est disponible dans la clause `COLLATE`.</span><span class="sxs-lookup"><span data-stu-id="d71f0-144">A new keyword, `CATALOG_DEFAULT`, is available in the `COLLATE` clause.</span></span> <span data-ttu-id="d71f0-145">Il est utilisé comme un raccourci du classement actuel de métadonnées à la fois dans les bases de données autonomes et non autonomes.</span><span class="sxs-lookup"><span data-stu-id="d71f0-145">This is used as a shortcut to the current collation of metadata in both contained and non-contained databases.</span></span> <span data-ttu-id="d71f0-146">Autrement dit, dans une base de données non autonome, `CATALOG_DEFAULT` retourne le classement de base de données actuel, puisque les métadonnées sont assemblées dans le classement de base de données.</span><span class="sxs-lookup"><span data-stu-id="d71f0-146">That is, in a non-contained database, `CATALOG_DEFAULT` will return the current database collation, since metadata is collated in the database collation.</span></span> <span data-ttu-id="d71f0-147">Dans une base de données autonome, ces deux valeurs peuvent être différentes, puisque l'utilisateur peut modifier le classement de base de données afin qu'il ne corresponde pas au classement de catalogue.</span><span class="sxs-lookup"><span data-stu-id="d71f0-147">In a contained database, these two values may be different, since the user can change the database collation so that it does not match the catalog collation.</span></span>  
  
 <span data-ttu-id="d71f0-148">Le comportement de différents objets dans les bases de données autonomes ou non autonomes est résumé dans ce tableau :</span><span class="sxs-lookup"><span data-stu-id="d71f0-148">The behavior of various objects in both non-contained and contained databases is summarized in this table:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="d71f0-149">**Item**</span><span class="sxs-lookup"><span data-stu-id="d71f0-149">**Item**</span></span>|<span data-ttu-id="d71f0-150">**Base de données non autonome**</span><span class="sxs-lookup"><span data-stu-id="d71f0-150">**Non-Contained Database**</span></span>|<span data-ttu-id="d71f0-151">**Base de données autonome**</span><span class="sxs-lookup"><span data-stu-id="d71f0-151">**Contained Database**</span></span>|  
|<span data-ttu-id="d71f0-152">Données utilisateur (valeur par défaut)</span><span class="sxs-lookup"><span data-stu-id="d71f0-152">User Data (default)</span></span>|<span data-ttu-id="d71f0-153">DATABASE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d71f0-153">DATABASE_DEFAULT</span></span>|<span data-ttu-id="d71f0-154">DATABASE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d71f0-154">DATABASE_DEFAULT</span></span>|  
|<span data-ttu-id="d71f0-155">Données Temp (valeur par défaut)</span><span class="sxs-lookup"><span data-stu-id="d71f0-155">Temp Data (default)</span></span>|<span data-ttu-id="d71f0-156">Classement TempDB</span><span class="sxs-lookup"><span data-stu-id="d71f0-156">TempDB Collation</span></span>|<span data-ttu-id="d71f0-157">DATABASE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d71f0-157">DATABASE_DEFAULT</span></span>|  
|<span data-ttu-id="d71f0-158">Métadonnées</span><span class="sxs-lookup"><span data-stu-id="d71f0-158">Metadata</span></span>|<span data-ttu-id="d71f0-159">DATABASE_DEFAULT / CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d71f0-159">DATABASE_DEFAULT / CATALOG_DEFAULT</span></span>|<span data-ttu-id="d71f0-160">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d71f0-160">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="d71f0-161">Métadonnées temporaires</span><span class="sxs-lookup"><span data-stu-id="d71f0-161">Temporary Metadata</span></span>|<span data-ttu-id="d71f0-162">Classement TempDB</span><span class="sxs-lookup"><span data-stu-id="d71f0-162">tempdb Collation</span></span>|<span data-ttu-id="d71f0-163">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d71f0-163">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="d71f0-164">Variables</span><span class="sxs-lookup"><span data-stu-id="d71f0-164">Variables</span></span>|<span data-ttu-id="d71f0-165">Classement d'instance</span><span class="sxs-lookup"><span data-stu-id="d71f0-165">Instance Collation</span></span>|<span data-ttu-id="d71f0-166">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d71f0-166">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="d71f0-167">Étiquettes goto</span><span class="sxs-lookup"><span data-stu-id="d71f0-167">Goto Labels</span></span>|<span data-ttu-id="d71f0-168">Classement d'instance</span><span class="sxs-lookup"><span data-stu-id="d71f0-168">Instance Collation</span></span>|<span data-ttu-id="d71f0-169">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d71f0-169">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="d71f0-170">Noms de curseur</span><span class="sxs-lookup"><span data-stu-id="d71f0-170">Cursor Names</span></span>|<span data-ttu-id="d71f0-171">Classement d'instance</span><span class="sxs-lookup"><span data-stu-id="d71f0-171">Instance Collation</span></span>|<span data-ttu-id="d71f0-172">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d71f0-172">CATALOG_DEFAULT</span></span>|  
  
 <span data-ttu-id="d71f0-173">Si nous examinons l'exemple de table temp décrit précédemment, nous pouvons voir que ce comportement de classement rend la clause `COLLATE` explicite inutile dans la plupart des utilisations de table temp.</span><span class="sxs-lookup"><span data-stu-id="d71f0-173">If we temp table example previously described, we can see that this collation behavior eliminates the need for an explicit `COLLATE` clause in most temp table uses.</span></span> <span data-ttu-id="d71f0-174">Dans une base de données autonome, ce code s'exécute désormais sans erreur, même si les classements d'instance et de base de données diffèrent :</span><span class="sxs-lookup"><span data-stu-id="d71f0-174">In a contained database, this code now runs without error, even if the database and instance collations differ:</span></span>  
  
```sql  
CREATE TABLE T1 (T1_txt nvarchar(max)) ;  
GO  
CREATE TABLE #T2 (T2_txt nvarchar(max));  
GO  
SELECT T1_txt, T2_txt  
FROM T1   
JOIN #T2   
    ON T1.T1_txt = #T2.T2_txt ;  
```  
  
 <span data-ttu-id="d71f0-175">Cela fonctionne parce que `T1_txt` et `T2_txt` sont assemblés dans le classement de base de données de la base de données autonome.</span><span class="sxs-lookup"><span data-stu-id="d71f0-175">This works because both `T1_txt` and `T2_txt` are collated in the database collation of the contained database.</span></span>  
  
## <a name="crossing-between-contained-and-uncontained-contexts"></a><span data-ttu-id="d71f0-176">Passer d'un contexte à relation contenant-contenu à un contexte sans relation contenant-contenu</span><span class="sxs-lookup"><span data-stu-id="d71f0-176">Crossing Between Contained and Uncontained Contexts</span></span>  
 <span data-ttu-id="d71f0-177">Tant qu'une session dans une base de données autonome reste contenue, elle doit rester dans la base de données à laquelle elle s'est connectée.</span><span class="sxs-lookup"><span data-stu-id="d71f0-177">As long as a session in a contained database remains contained, it must remain within the database to which it connected.</span></span> <span data-ttu-id="d71f0-178">Dans ce cas, le comportement est très simple.</span><span class="sxs-lookup"><span data-stu-id="d71f0-178">In this case the behavior is very straightforward.</span></span> <span data-ttu-id="d71f0-179">Mais si une session passe d'un contexte à relation contenant-contenu à un contexte sans relation contenant-contenu, le comportement devient plus complexe, puisque deux ensembles de règles doivent être liés.</span><span class="sxs-lookup"><span data-stu-id="d71f0-179">But if a session crosses between contained and non-contained contexts, the behavior becomes more complex, since the two sets of rules must be bridged.</span></span> <span data-ttu-id="d71f0-180">Cela peut arriver dans une base de données partiellement autonome, puisqu'un utilisateur peut exécuter une opération `USE` sur une autre base de données.</span><span class="sxs-lookup"><span data-stu-id="d71f0-180">This can happen in a partially-contained database, since a user may `USE` to another database.</span></span> <span data-ttu-id="d71f0-181">Dans ce cas, la différence des règles de classement est gérée selon le principe suivant.</span><span class="sxs-lookup"><span data-stu-id="d71f0-181">In this case, the difference in collation rules is handled by the following principle.</span></span>  
  
-   <span data-ttu-id="d71f0-182">Le comportement du classement d'un lot est déterminé par la base de données dans laquelle commence le lot.</span><span class="sxs-lookup"><span data-stu-id="d71f0-182">The collation behavior for a batch is determined by the database in which the batch begins.</span></span>  
  
 <span data-ttu-id="d71f0-183">Notez que cette décision est prise avant l'émission d'une commande, notamment la commande `USE`initiale.</span><span class="sxs-lookup"><span data-stu-id="d71f0-183">Note that this decision is made before any commands are issued, including an initial `USE`.</span></span> <span data-ttu-id="d71f0-184">Autrement dit, si un lot commence dans une base de données autonome, mais que la première commande est un `USE` sur une base de données non autonome, le comportement du classement autonome sera toujours utilisé pour le lot.</span><span class="sxs-lookup"><span data-stu-id="d71f0-184">That is, if a batch begins in a contained database, but the first command is a `USE` to a non-contained database, the contained collation behavior will still be used for the batch.</span></span> <span data-ttu-id="d71f0-185">En conséquence, une référence à une variable, par exemple, peut donner plusieurs résultats possibles :</span><span class="sxs-lookup"><span data-stu-id="d71f0-185">Given this, a reference to a variable, for example, may have multiple possible outcomes:</span></span>  
  
-   <span data-ttu-id="d71f0-186">La référence peut trouver exactement une correspondance.</span><span class="sxs-lookup"><span data-stu-id="d71f0-186">The reference may find exactly one match.</span></span> <span data-ttu-id="d71f0-187">Dans ce cas, la référence fonctionnera sans erreur.</span><span class="sxs-lookup"><span data-stu-id="d71f0-187">In this case, the reference will work without error.</span></span>  
  
-   <span data-ttu-id="d71f0-188">La référence peut pas trouver de correspondance dans le classement actuel alors qu'il en existait une auparavant.</span><span class="sxs-lookup"><span data-stu-id="d71f0-188">The reference may not find a match in the current collation where there was one before.</span></span> <span data-ttu-id="d71f0-189">Cela génère une erreur indiquant que la variable n'existe pas, bien qu'elle ait été apparemment créée.</span><span class="sxs-lookup"><span data-stu-id="d71f0-189">This will raise an error indicating that the variable does not exist, even though it was apparently created.</span></span>  
  
-   <span data-ttu-id="d71f0-190">La référence peut trouver plusieurs correspondances qui étaient distinctes à l'origine.</span><span class="sxs-lookup"><span data-stu-id="d71f0-190">The reference may find multiple matches that were originally distinct.</span></span> <span data-ttu-id="d71f0-191">Cela génère également une erreur.</span><span class="sxs-lookup"><span data-stu-id="d71f0-191">This will also raise an error.</span></span>  
  
 <span data-ttu-id="d71f0-192">Illustrons ceci par quelques exemples.</span><span class="sxs-lookup"><span data-stu-id="d71f0-192">We'll illustrate this with a few examples.</span></span> <span data-ttu-id="d71f0-193">Pour ces exemples, nous supposons une base de données partiellement autonome, nommée `MyCDB`, dont le classement de base de données est défini sur le classement par défaut, **Latin1_General_100_CI_AS_WS_KS_SC**.</span><span class="sxs-lookup"><span data-stu-id="d71f0-193">For these we assume there is a partially-contained database named `MyCDB` with its database collation set to the default collation, **Latin1_General_100_CI_AS_WS_KS_SC**.</span></span> <span data-ttu-id="d71f0-194">Nous supposons que le classement d'instance est `Latin1_General_100_CS_AS_WS_KS_SC`.</span><span class="sxs-lookup"><span data-stu-id="d71f0-194">We assume that the instance collation is `Latin1_General_100_CS_AS_WS_KS_SC`.</span></span> <span data-ttu-id="d71f0-195">Les deux classements diffèrent uniquement en fonction du respect de la casse.</span><span class="sxs-lookup"><span data-stu-id="d71f0-195">The two collations differ only in case sensitivity.</span></span>  
  
### <a name="example-1"></a><span data-ttu-id="d71f0-196">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="d71f0-196">Example 1</span></span>  
 <span data-ttu-id="d71f0-197">L'exemple suivant illustre le cas où la référence trouve exactement une correspondance.</span><span class="sxs-lookup"><span data-stu-id="d71f0-197">The following example illustrates the case where the reference finds exactly one match.</span></span>  
  
```  
USE MyCDB;  
GO  
  
CREATE TABLE #a(x int);  
INSERT INTO #a VALUES(1);  
GO  
  
USE master;  
GO  
  
SELECT * FROM #a;  
GO  
  
Results:  
  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
x  
-----------  
1  
```  
  
 <span data-ttu-id="d71f0-198">Dans ce cas, le #a identifié est lié à la fois au classement de catalogue qui ne respecte pas la casse et au classement d'instance qui respecte la casse ; donc le code fonctionne.</span><span class="sxs-lookup"><span data-stu-id="d71f0-198">In this case, the identified #a binds in both the case-insensitive catalog collation and the case-sensitive instance collation, and the code works.</span></span>  
  
### <a name="example-2"></a><span data-ttu-id="d71f0-199">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="d71f0-199">Example 2</span></span>  
 <span data-ttu-id="d71f0-200">L'exemple suivant illustre le cas où la référence ne trouve pas de correspondance dans le classement actuel alors qu'il en existait une auparavant.</span><span class="sxs-lookup"><span data-stu-id="d71f0-200">The following example illustrates the case where the reference does not find a match in the current collation where there was one before.</span></span>  
  
```  
USE MyCDB;  
GO  
  
CREATE TABLE #a(x int);  
INSERT INTO #A VALUES(1);  
GO  
```  
  
 <span data-ttu-id="d71f0-201">Ici, le #A est lié à #a dans le classement par défaut qui ne respecte pas la casse, et l'insertion fonctionne,</span><span class="sxs-lookup"><span data-stu-id="d71f0-201">Here, the #A binds to #a in the case-insensitive default collation, and the insert works,</span></span>  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
(1 row(s) affected)  
```  
  
 <span data-ttu-id="d71f0-202">mais si nous continuons le script...</span><span class="sxs-lookup"><span data-stu-id="d71f0-202">But if we continue the script...</span></span>  
  
```  
USE master;  
GO  
  
SELECT * FROM #A;  
GO  
```  
  
 <span data-ttu-id="d71f0-203">Nous obtenons une erreur lors de la tentative de lier #A dans le classement d'instance qui respecte la casse ;</span><span class="sxs-lookup"><span data-stu-id="d71f0-203">We get an error trying to bind to #A in the case-sensitive instance collation;</span></span>  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 <span data-ttu-id="d71f0-204">Msg 208, Niveau 16, État 0, Ligne 2</span><span class="sxs-lookup"><span data-stu-id="d71f0-204">Msg 208, Level 16, State 0, Line 2</span></span>  
  
 <span data-ttu-id="d71f0-205">Nom d'objet '#A' non valide.</span><span class="sxs-lookup"><span data-stu-id="d71f0-205">Invalid object name '#A'.</span></span>  
  
### <a name="example-3"></a><span data-ttu-id="d71f0-206">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="d71f0-206">Example 3</span></span>  
 <span data-ttu-id="d71f0-207">L'exemple suivant illustre le cas où la référence trouve plusieurs correspondances qui étaient distinctes à l'origine.</span><span class="sxs-lookup"><span data-stu-id="d71f0-207">The following example illustrates the case where the reference finds multiple matches that were originally distinct.</span></span> <span data-ttu-id="d71f0-208">Tout d’abord, nous commençons dans `tempdb` (qui a le même classement respectant la casse que notre instance) et nous exécutons les instructions suivantes.</span><span class="sxs-lookup"><span data-stu-id="d71f0-208">First, we start in `tempdb` (which has the same case-sensitive collation as our instance) and execute the following statements.</span></span>  
  
```  
USE tempdb;  
GO  
  
CREATE TABLE #a(x int);  
GO  
CREATE TABLE #A(x int);  
GO  
INSERT INTO #a VALUES(1);  
GO  
INSERT INTO #A VALUES(2);  
GO  
```  
  
 <span data-ttu-id="d71f0-209">Ce code réussit, puisque les tables sont distinctes dans ce classement :</span><span class="sxs-lookup"><span data-stu-id="d71f0-209">This succeeds, since the tables are distinct in this collation:</span></span>  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
(1 row(s) affected)  
(1 row(s) affected)  
```  
  
 <span data-ttu-id="d71f0-210">Si nous nous déplaçons dans notre base de données autonome, toutefois, nous constatons que nous ne pouvons plus créer de liaison avec ces tables.</span><span class="sxs-lookup"><span data-stu-id="d71f0-210">If we move into our contained database, however, we find that we can no longer bind to these tables.</span></span>  
  
```  
USE MyCDB;  
GO  
SELECT * FROM #a;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 <span data-ttu-id="d71f0-211">Msg 12800, Niveau 16, État 1, Ligne 2</span><span class="sxs-lookup"><span data-stu-id="d71f0-211">Msg 12800, Level 16, State 1, Line 2</span></span>  
  
 <span data-ttu-id="d71f0-212">La référence au nom de table temporaire '#a' est ambiguë et ne peut pas être résolue.</span><span class="sxs-lookup"><span data-stu-id="d71f0-212">The reference to temp table name '#a' is ambiguous and cannot be resolved.</span></span> <span data-ttu-id="d71f0-213">Les candidats possibles sont '#a' et '#A.'</span><span class="sxs-lookup"><span data-stu-id="d71f0-213">Possible candidates are '#a' and '#A'.</span></span>  
  
## <a name="conclusion"></a><span data-ttu-id="d71f0-214">Conclusion</span><span class="sxs-lookup"><span data-stu-id="d71f0-214">Conclusion</span></span>  
 <span data-ttu-id="d71f0-215">Le comportement du classement des bases de données autonomes diffère légèrement de celui des bases de données non autonomes.</span><span class="sxs-lookup"><span data-stu-id="d71f0-215">The collation behavior of contained databases differs subtly from that in non-contained databases.</span></span> <span data-ttu-id="d71f0-216">Ce comportement est généralement bénéfique, car il apporte une indépendance par rapport à l'instance et de la simplicité.</span><span class="sxs-lookup"><span data-stu-id="d71f0-216">This behavior is generally beneficial, providing instance-independence and simplicity.</span></span> <span data-ttu-id="d71f0-217">Certains utilisateurs peuvent avoir des problèmes, en particulier lorsqu'une session accède à la fois à des bases de données autonomes et non autonomes.</span><span class="sxs-lookup"><span data-stu-id="d71f0-217">Some users may have issues, particularly when a session accesses both contained and non-contained databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d71f0-218">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d71f0-218">See Also</span></span>  
 [<span data-ttu-id="d71f0-219">Bases de données autonomes</span><span class="sxs-lookup"><span data-stu-id="d71f0-219">Contained Databases</span></span>](contained-databases.md)  
  
  
