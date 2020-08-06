---
title: Synonymes (moteur de base de données) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- synonyms [SQL Server], about synonyms
ms.assetid: 6210e1d5-075f-47e4-ac8d-f84bcf26fbc0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3494f4f5b13c422efb8e2a39597e131c10d81ed1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605327"
---
# <a name="synonyms-database-engine"></a><span data-ttu-id="f0d71-102">Synonymes (Moteur de base de données)</span><span class="sxs-lookup"><span data-stu-id="f0d71-102">Synonyms (Database Engine)</span></span>
  <span data-ttu-id="f0d71-103">Un synonyme est un objet de base de données utilisé aux fins suivantes :</span><span class="sxs-lookup"><span data-stu-id="f0d71-103">A synonym is a database object that serves the following purposes:</span></span>  
  
-   <span data-ttu-id="f0d71-104">Il fournit un nom de remplacement pour un autre objet de base de données, appelé « objet de base », qui peut exister sur un serveur local ou distant.</span><span class="sxs-lookup"><span data-stu-id="f0d71-104">Provides an alternative name for another database object, referred to as the base object, that can exist on a local or remote server.</span></span>  
  
-   <span data-ttu-id="f0d71-105">Il fournit une couche d'abstraction qui protège une application cliente contre les modifications apportées au nom ou à l'emplacement de l'objet de base.</span><span class="sxs-lookup"><span data-stu-id="f0d71-105">Provides a layer of abstraction that protects a client application from changes made to the name or location of the base object.</span></span>  
  
 <span data-ttu-id="f0d71-106">Par exemple, supposons que la table **Employee** de [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)]soit située sur un serveur nommé **Serveur1**.</span><span class="sxs-lookup"><span data-stu-id="f0d71-106">For example, consider the **Employee** table of [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)], located on a server named **Server1**.</span></span> <span data-ttu-id="f0d71-107">Pour faire référence à cette table à partir d’un autre serveur, **Server2**, une application cliente devrait utiliser le nom en quatre parties **Server1.AdventureWorks.Person.Employee**.</span><span class="sxs-lookup"><span data-stu-id="f0d71-107">To reference this table from another server, **Server2**, a client application would have to use the four-part name **Server1.AdventureWorks.Person.Employee**.</span></span> <span data-ttu-id="f0d71-108">En outre, si l'emplacement de la table devait changer, par exemple vers un autre serveur, l'application cliente devrait être modifiée de façon à refléter ce changement.</span><span class="sxs-lookup"><span data-stu-id="f0d71-108">Also, if the location of the table were to change, for example, to another server, the client application would have to be modified to reflect that change.</span></span>  
  
 <span data-ttu-id="f0d71-109">Pour faire face à ces deux situations, vous pouvez créer un synonyme, en l’occurrence **EmpTable**, sur le serveur **Server2** pour la table **Employee** située sur le serveur **Server1**.</span><span class="sxs-lookup"><span data-stu-id="f0d71-109">To address both these issues, you can create a synonym, **EmpTable**, on **Server2** for the **Employee** table on **Server1**.</span></span> <span data-ttu-id="f0d71-110">Maintenant, l’application cliente doit seulement utiliser le nom en une seule partie **EmpTable**pour référencer la table **Employee** .</span><span class="sxs-lookup"><span data-stu-id="f0d71-110">Now, the client application only has to use the single-part name, **EmpTable**, to reference the **Employee** table.</span></span> <span data-ttu-id="f0d71-111">De même, si l’emplacement de la table **Employee** change, vous devez modifier le synonyme **EmpTable**de manière à ce qu’il pointe vers le nouvel emplacement de la table **Employee** .</span><span class="sxs-lookup"><span data-stu-id="f0d71-111">Also, if the location of the **Employee** table changes, you will have to modify the synonym, **EmpTable**, to point to the new location of the **Employee** table.</span></span> <span data-ttu-id="f0d71-112">Étant donné qu’il n’existe pas d’instruction ALTER SYNONYM, vous devez d’abord supprimer le synonyme **EmpTable**, puis le recréer avec le même nom, mais en le faisant pointer vers le nouvel emplacement de la table **Employee**.</span><span class="sxs-lookup"><span data-stu-id="f0d71-112">Because there is no ALTER SYNONYM statement, you first have to drop the synonym, **EmpTable**, and then re-create the synonym with the same name, but point the synonym to the new location of **Employee**.</span></span>  
  
 <span data-ttu-id="f0d71-113">Un synonyme est un objet appartenant à un schéma et, à ce titre, son nom doit être unique.</span><span class="sxs-lookup"><span data-stu-id="f0d71-113">A synonym belongs to a schema, and like other objects in a schema, the name of a synonym must be unique.</span></span> <span data-ttu-id="f0d71-114">Vous pouvez créer des synonymes pour les objets de base de données suivants :</span><span class="sxs-lookup"><span data-stu-id="f0d71-114">You can create synonyms for the following database objects:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0d71-115">Procédure stockée d'un assembly (CLR)</span><span class="sxs-lookup"><span data-stu-id="f0d71-115">Assembly (CLR) stored procedure</span></span>|<span data-ttu-id="f0d71-116">Fonction table d'un assembly (CLR)</span><span class="sxs-lookup"><span data-stu-id="f0d71-116">Assembly (CLR) table-valued function</span></span>|  
|<span data-ttu-id="f0d71-117">Fonction scalaire d'un assembly (CLR)</span><span class="sxs-lookup"><span data-stu-id="f0d71-117">Assembly (CLR) scalar function</span></span>|<span data-ttu-id="f0d71-118">Fonctions d'agrégation d'un assembly (CLR)</span><span class="sxs-lookup"><span data-stu-id="f0d71-118">Assembly (CLR) aggregate functions</span></span>|  
|<span data-ttu-id="f0d71-119">Procédure de réplication et de filtrage</span><span class="sxs-lookup"><span data-stu-id="f0d71-119">Replication-filter-procedure</span></span>|<span data-ttu-id="f0d71-120">Procédure stockée étendue</span><span class="sxs-lookup"><span data-stu-id="f0d71-120">Extended stored procedure</span></span>|  
|<span data-ttu-id="f0d71-121">Fonction scalaire SQL</span><span class="sxs-lookup"><span data-stu-id="f0d71-121">SQL scalar function</span></span>|<span data-ttu-id="f0d71-122">Fonction table SQL</span><span class="sxs-lookup"><span data-stu-id="f0d71-122">SQL table-valued function</span></span>|  
|<span data-ttu-id="f0d71-123">Fonction table inline SQL</span><span class="sxs-lookup"><span data-stu-id="f0d71-123">SQL inline-tabled-valued function</span></span>|<span data-ttu-id="f0d71-124">Procédure stockée SQL</span><span class="sxs-lookup"><span data-stu-id="f0d71-124">SQL stored procedure</span></span>|  
|<span data-ttu-id="f0d71-125">Affichage</span><span class="sxs-lookup"><span data-stu-id="f0d71-125">View</span></span>|<span data-ttu-id="f0d71-126">Table<sup>1</sup> (définie par l’utilisateur)</span><span class="sxs-lookup"><span data-stu-id="f0d71-126">Table<sup>1</sup> (User-defined)</span></span>|  
  
 <span data-ttu-id="f0d71-127"><sup>1</sup> comprend des tables temporaires locales et globales</span><span class="sxs-lookup"><span data-stu-id="f0d71-127"><sup>1</sup> Includes local and global temporary tables</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f0d71-128">Les noms en quatre parties des objets de base de fonction ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="f0d71-128">Four-part names for function base objects are not supported.</span></span>  
  
 <span data-ttu-id="f0d71-129">Un synonyme ne peut pas être l'objet de base d'un autre synonyme ni référencer une fonction d'agrégation définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f0d71-129">A synonym cannot be the base object for another synonym, and a synonym cannot reference a user-defined aggregate function.</span></span>  
  
 <span data-ttu-id="f0d71-130">La liaison entre un synonyme et son objet de base se fait uniquement par le nom.</span><span class="sxs-lookup"><span data-stu-id="f0d71-130">The binding between a synonym and its base object is by name only.</span></span> <span data-ttu-id="f0d71-131">Toute vérification d'existence, de type et d'autorisations sur l'objet de base est différée jusqu'à l'exécution.</span><span class="sxs-lookup"><span data-stu-id="f0d71-131">All existence, type, and permissions checking on the base object is deferred until run time.</span></span> <span data-ttu-id="f0d71-132">Par conséquent, l'objet de base peut être modifié, supprimé ou bien supprimé et remplacé par un autre objet portant le même nom que l'objet de base initial.</span><span class="sxs-lookup"><span data-stu-id="f0d71-132">Therefore, the base object can be modified, dropped, or dropped and replaced by another object that has the same name as the original base object.</span></span> <span data-ttu-id="f0d71-133">Par exemple, prenons l’exemple d’un synonyme, **MesContacts**, qui référence la table **Person.Contact** dans [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0d71-133">For example, consider a synonym, **MyContacts**, that references the **Person.Contact** table in [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)].</span></span> <span data-ttu-id="f0d71-134">Si la table **Contact** est supprimée, puis remplacée par une vue nommée **Person.Contact**, **MyContacts** référence la vue **Person.Contact** .</span><span class="sxs-lookup"><span data-stu-id="f0d71-134">If the **Contact** table is dropped and replaced by a view named **Person.Contact**, **MyContacts** now references the **Person.Contact** view.</span></span>  
  
 <span data-ttu-id="f0d71-135">Les références aux synonymes ne sont pas liées au schéma.</span><span class="sxs-lookup"><span data-stu-id="f0d71-135">References to synonyms are not schema-bound.</span></span> <span data-ttu-id="f0d71-136">Par conséquent, un synonyme peut être supprimé à tout moment.</span><span class="sxs-lookup"><span data-stu-id="f0d71-136">Therefore, a synonym can be dropped at any time.</span></span> <span data-ttu-id="f0d71-137">Toutefois, si vous supprimez un synonyme, vous courez le risque de laisser des références non résolues à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="f0d71-137">However, by dropping a synonym, you run the risk of leaving dangling references to the synonym that was dropped.</span></span> <span data-ttu-id="f0d71-138">Ces références ne sont trouvées qu'au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="f0d71-138">These references will only be found at run time.</span></span>  
  
## <a name="synonyms-and-schemas"></a><span data-ttu-id="f0d71-139">Synonymes et schémas</span><span class="sxs-lookup"><span data-stu-id="f0d71-139">Synonyms and Schemas</span></span>  
 <span data-ttu-id="f0d71-140">Si vous disposez d'un schéma par défaut qui ne vous appartient pas et que vous souhaitez créer un synonyme, vous devez qualifier le nom du synonyme avec le nom d'un schéma dont vous êtes propriétaire.</span><span class="sxs-lookup"><span data-stu-id="f0d71-140">If you have a default schema that you do not own and want to create a synonym, you must qualify the synonym name with the name of a schema that you do own.</span></span> <span data-ttu-id="f0d71-141">Par exemple, si vous êtes propriétaire d’un schéma **x**, mais que **y** est votre schéma par défaut et que vous utilisez l’instruction CREATE SYNONYM, vous devez faire précéder le nom du synonyme du schéma **x**, au lieu d’attribuer au synonyme un nom en une seule partie.</span><span class="sxs-lookup"><span data-stu-id="f0d71-141">For example, if you own a schema **x**, but **y** is your default schema and you use the CREATE SYNONYM statement, you must prefix the name of the synonym with the schema **x**, instead of naming the synonym by using a single-part name.</span></span> <span data-ttu-id="f0d71-142">Pour plus d’informations sur la création de synonymes, consultez [CREATE SYNONYM &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-synonym-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f0d71-142">For more information about how to create synonyms, see [CREATE SYNONYM &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-synonym-transact-sql).</span></span>  
  
## <a name="granting-permissions-on-a-synonym"></a><span data-ttu-id="f0d71-143">Octroi d'autorisations sur un synonyme</span><span class="sxs-lookup"><span data-stu-id="f0d71-143">Granting Permissions on a Synonym</span></span>  
 <span data-ttu-id="f0d71-144">Seuls les propriétaires de synonymes, les membres de **db_owner**ou ceux de **db_ddladmin** peuvent accorder une autorisation sur un synonyme.</span><span class="sxs-lookup"><span data-stu-id="f0d71-144">Only synonym owners, members of **db_owner**, or members of **db_ddladmin** can grant permission on a synonym.</span></span>  
  
 <span data-ttu-id="f0d71-145">Vous pouvez accorder, refuser ou révoquer tout ou partie des autorisations suivantes sur un synonyme :</span><span class="sxs-lookup"><span data-stu-id="f0d71-145">You can GRANT, DENY, REVOKE all or any of the following permissions on a synonym:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0d71-146">CONTROL</span><span class="sxs-lookup"><span data-stu-id="f0d71-146">CONTROL</span></span>|<span data-ttu-id="f0d71-147">Suppression</span><span class="sxs-lookup"><span data-stu-id="f0d71-147">DELETE</span></span>|  
|<span data-ttu-id="f0d71-148">Exécutez</span><span class="sxs-lookup"><span data-stu-id="f0d71-148">EXECUTE</span></span>|<span data-ttu-id="f0d71-149">INSERT</span><span class="sxs-lookup"><span data-stu-id="f0d71-149">INSERT</span></span>|  
|<span data-ttu-id="f0d71-150">SELECT</span><span class="sxs-lookup"><span data-stu-id="f0d71-150">SELECT</span></span>|<span data-ttu-id="f0d71-151">TAKE OWNERSHIP</span><span class="sxs-lookup"><span data-stu-id="f0d71-151">TAKE OWNERSHIP</span></span>|  
|<span data-ttu-id="f0d71-152">UPDATE</span><span class="sxs-lookup"><span data-stu-id="f0d71-152">UPDATE</span></span>|<span data-ttu-id="f0d71-153">VIEW DEFINITION</span><span class="sxs-lookup"><span data-stu-id="f0d71-153">VIEW DEFINITION</span></span>|  
  
## <a name="using-synonyms"></a><span data-ttu-id="f0d71-154">Utilisation de synonymes</span><span class="sxs-lookup"><span data-stu-id="f0d71-154">Using Synonyms</span></span>  
 <span data-ttu-id="f0d71-155">Vous pouvez utiliser les synonymes à la place de leur objet de base référencé dans de nombreuses instructions SQL et leurs contextes d'expression.</span><span class="sxs-lookup"><span data-stu-id="f0d71-155">You can use synonyms in place of their referenced base object in several SQL statements and expression contexts.</span></span> <span data-ttu-id="f0d71-156">Le tableau suivant contient une liste de ces instructions et contextes d'expression :</span><span class="sxs-lookup"><span data-stu-id="f0d71-156">The following table contains a list of these statements and expression contexts:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0d71-157">SELECT</span><span class="sxs-lookup"><span data-stu-id="f0d71-157">SELECT</span></span>|<span data-ttu-id="f0d71-158">INSERT</span><span class="sxs-lookup"><span data-stu-id="f0d71-158">INSERT</span></span>|  
|<span data-ttu-id="f0d71-159">UPDATE</span><span class="sxs-lookup"><span data-stu-id="f0d71-159">UPDATE</span></span>|<span data-ttu-id="f0d71-160">Suppression</span><span class="sxs-lookup"><span data-stu-id="f0d71-160">DELETE</span></span>|  
|<span data-ttu-id="f0d71-161">Exécutez</span><span class="sxs-lookup"><span data-stu-id="f0d71-161">EXECUTE</span></span>|<span data-ttu-id="f0d71-162">Sub-selects</span><span class="sxs-lookup"><span data-stu-id="f0d71-162">Sub-selects</span></span>|  
  
 <span data-ttu-id="f0d71-163">Si vous travaillez avec des synonymes dans les contextes précédemment cités, l'objet de base est affecté.</span><span class="sxs-lookup"><span data-stu-id="f0d71-163">When you are working with synonyms in the contexts previously stated, the base object is affected.</span></span> <span data-ttu-id="f0d71-164">Par exemple, si un synonyme référence un objet de base qui est une table et que vous insérez une ligne dans le synonyme, vous insérez en fait une ligne dans la table référencée.</span><span class="sxs-lookup"><span data-stu-id="f0d71-164">For example, if a synonym references a base object that is a table and you insert a row into the synonym, you are actually inserting a row into the referenced table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f0d71-165">Vous ne pouvez pas référencer un synonyme situé sur un serveur lié.</span><span class="sxs-lookup"><span data-stu-id="f0d71-165">You cannot reference a synonym that is located on a linked server.</span></span>  
  
 <span data-ttu-id="f0d71-166">Vous pouvez utiliser un synonyme en tant que paramètre de la fonction OBJECT_ID ; par contre, la fonction renvoie alors l'ID d'objet du synonyme, et non celui de l'objet de base.</span><span class="sxs-lookup"><span data-stu-id="f0d71-166">You can use a synonym as the parameter for the OBJECT_ID function; however, the function returns the object ID of the synonym, not the base object.</span></span>  
  
 <span data-ttu-id="f0d71-167">Vous ne pouvez pas référencer un synonyme dans une instruction DDL.</span><span class="sxs-lookup"><span data-stu-id="f0d71-167">You cannot reference a synonym in a DDL statement.</span></span> <span data-ttu-id="f0d71-168">Par exemple, les instructions suivantes, qui référencent un synonyme nommé `dbo.MyProduct`, génèrent des erreurs :</span><span class="sxs-lookup"><span data-stu-id="f0d71-168">For example, the following statements, which reference a synonym named `dbo.MyProduct`, generate errors:</span></span>  
  
```  
ALTER TABLE dbo.MyProduct  
   ADD NewFlag int null;  
EXEC ('ALTER TABLE dbo.MyProduct  
   ADD NewFlag int null');  
```  
  
 <span data-ttu-id="f0d71-169">Les instructions d'autorisation suivantes sont associées uniquement au synonyme, et pas à l'objet de base :</span><span class="sxs-lookup"><span data-stu-id="f0d71-169">The following permission statements are associated only with the synonym and not the base object:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0d71-170">GRANT</span><span class="sxs-lookup"><span data-stu-id="f0d71-170">GRANT</span></span>|<span data-ttu-id="f0d71-171">DENY</span><span class="sxs-lookup"><span data-stu-id="f0d71-171">DENY</span></span>|  
|<span data-ttu-id="f0d71-172">REVOKE</span><span class="sxs-lookup"><span data-stu-id="f0d71-172">REVOKE</span></span>||  
  
 <span data-ttu-id="f0d71-173">Les synonymes ne sont pas liés à un schéma et ne peuvent donc pas être référencés dans les contextes d'expression suivants qui sont liés à un schéma :</span><span class="sxs-lookup"><span data-stu-id="f0d71-173">Synonyms are not schema-bound and, therefore, cannot be referenced by the following schema-bound expression contexts:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0d71-174">Contraintes CHECK</span><span class="sxs-lookup"><span data-stu-id="f0d71-174">CHECK constraints</span></span>|<span data-ttu-id="f0d71-175">Colonnes calculées</span><span class="sxs-lookup"><span data-stu-id="f0d71-175">Computed columns</span></span>|  
|<span data-ttu-id="f0d71-176">Expressions par défaut</span><span class="sxs-lookup"><span data-stu-id="f0d71-176">Default expressions</span></span>|<span data-ttu-id="f0d71-177">Expressions de règle</span><span class="sxs-lookup"><span data-stu-id="f0d71-177">Rule expressions</span></span>|  
|<span data-ttu-id="f0d71-178">Vues liées à un schéma</span><span class="sxs-lookup"><span data-stu-id="f0d71-178">Schema-bound views</span></span>|<span data-ttu-id="f0d71-179">Fonctions liées à un schéma</span><span class="sxs-lookup"><span data-stu-id="f0d71-179">Schema-bound functions</span></span>|  
  
 <span data-ttu-id="f0d71-180">Pour plus d’informations sur les fonctions liées au schéma, consultez [Créer des fonctions définies par l’utilisateur &#40;moteur de base de données&#41;](../user-defined-functions/create-user-defined-functions-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="f0d71-180">For more information about schema-bound functions, see [Create User-defined Functions &#40;Database Engine&#41;](../user-defined-functions/create-user-defined-functions-database-engine.md).</span></span>  
  
## <a name="getting-information-about-synonyms"></a><span data-ttu-id="f0d71-181">Obtention d'informations sur les synonymes</span><span class="sxs-lookup"><span data-stu-id="f0d71-181">Getting Information About Synonyms</span></span>  
 <span data-ttu-id="f0d71-182">L'affichage catalogue sys.synonyms contient une entrée pour chaque synonyme dans une base de données déterminée.</span><span class="sxs-lookup"><span data-stu-id="f0d71-182">The sys.synonyms catalog view contains an entry for each synonym in a given database.</span></span> <span data-ttu-id="f0d71-183">Cet affichage catalogue expose les métadonnées synonymes, telles que le nom du synonyme et celui de l'objet de base.</span><span class="sxs-lookup"><span data-stu-id="f0d71-183">This catalog view exposes synonym metadata such as the name of the synonym and the name of the base object.</span></span> <span data-ttu-id="f0d71-184">Pour plus d’informations sur l' `sys.synonyms` affichage catalogue, consultez [sys. synonymes &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-synonyms-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f0d71-184">For more information about the `sys.synonyms` catalog view, see [sys.synonyms &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-synonyms-transact-sql).</span></span>  
  
 <span data-ttu-id="f0d71-185">À l'aide des propriétés étendues, vous pouvez ajouter un texte descriptif ou instructif, des masques d'entrée et des règles de mise en forme comme propriétés d'un synonyme.</span><span class="sxs-lookup"><span data-stu-id="f0d71-185">By using extended properties, you can add descriptive or instructional text, input masks, and formatting rules as properties of a synonym.</span></span> <span data-ttu-id="f0d71-186">Étant donné que la propriété est stockée dans la base de données, toutes les applications qui la lisent peuvent évaluer l'objet de la même manière.</span><span class="sxs-lookup"><span data-stu-id="f0d71-186">Because the property is stored in the database, all applications that read the property can evaluate the object in the same way.</span></span> <span data-ttu-id="f0d71-187">Pour plus d’informations, consultez [sp_addextendedproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f0d71-187">For more information, see [sp_addextendedproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproperty-transact-sql).</span></span>  
  
 <span data-ttu-id="f0d71-188">Pour rechercher le type de base de l'objet de base d'un synonyme, utilisez la fonction OBJECTPROPERTYEX.</span><span class="sxs-lookup"><span data-stu-id="f0d71-188">To find the base type of the base object of a synonym, use the OBJECTPROPERTYEX function.</span></span> <span data-ttu-id="f0d71-189">Pour plus d’informations, consultez [OBJECTPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f0d71-189">For more information, see [OBJECTPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectproperty-transact-sql).</span></span>  
  
### <a name="examples"></a><span data-ttu-id="f0d71-190">Exemples</span><span class="sxs-lookup"><span data-stu-id="f0d71-190">Examples</span></span>  
 <span data-ttu-id="f0d71-191">L'exemple suivant retourne le type de base de l'objet de base d'un synonyme qui est un objet local.</span><span class="sxs-lookup"><span data-stu-id="f0d71-191">The following example returns the base type of a synonym's base object that is a local object.</span></span>  
  
```  
USE tempdb;  
GO  
CREATE SYNONYM MyEmployee   
FOR AdventureWorks2012.HumanResources.Employee;  
GO  
SELECT OBJECTPROPERTYEX(OBJECT_ID('MyEmployee'), 'BaseType') AS BaseType;  
```  
  
 <span data-ttu-id="f0d71-192">L'exemple suivant retourne le type de base de l'objet de base d'un synonyme qui est un objet distant situé sur un serveur appelé `Server1`.</span><span class="sxs-lookup"><span data-stu-id="f0d71-192">The following example returns the base type of a synonym's base object that is a remote object located on a server named `Server1`.</span></span>  
  
```  
EXECUTE sp_addlinkedserver Server1;  
GO  
CREATE SYNONYM MyRemoteEmployee  
FOR Server1.AdventureWorks2012.HumanResources.Employee;  
GO  
SELECT OBJECTPROPERTYEX(OBJECT_ID('MyRemoteEmployee'), 'BaseType') AS BaseType;  
GO  
```  
  
## <a name="related-content"></a><span data-ttu-id="f0d71-193">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="f0d71-193">Related Content</span></span>  
 [<span data-ttu-id="f0d71-194">Créer des synonymes</span><span class="sxs-lookup"><span data-stu-id="f0d71-194">Create Synonyms</span></span>](create-synonyms.md)  
  
 [<span data-ttu-id="f0d71-195">CREATE SYNONYM &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f0d71-195">CREATE SYNONYM &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-synonym-transact-sql)  
  
 [<span data-ttu-id="f0d71-196">DROP SYNONYM &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f0d71-196">DROP SYNONYM &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-synonym-transact-sql)  
  
  
