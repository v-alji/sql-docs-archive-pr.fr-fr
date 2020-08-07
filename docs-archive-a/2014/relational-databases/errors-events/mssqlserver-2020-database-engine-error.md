---
title: MSSQLSERVER_2020 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2020 (Database Engine error)
ms.assetid: 4a8bf90f-a083-4c53-84f0-d23c711c8081
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5939267c37e90e7b8456dc01a4af79545e775656
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612878"
---
# <a name="mssqlserver_2020"></a><span data-ttu-id="bd019-102">MSSQLSERVER_2020</span><span class="sxs-lookup"><span data-stu-id="bd019-102">MSSQLSERVER_2020</span></span>
    
## <a name="details"></a><span data-ttu-id="bd019-103">Détails</span><span class="sxs-lookup"><span data-stu-id="bd019-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bd019-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="bd019-104">Product Name</span></span>|<span data-ttu-id="bd019-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bd019-105">SQL Server</span></span>|  
|<span data-ttu-id="bd019-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="bd019-106">Event ID</span></span>|<span data-ttu-id="bd019-107">2020</span><span class="sxs-lookup"><span data-stu-id="bd019-107">2020</span></span>|  
|<span data-ttu-id="bd019-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="bd019-108">Event Source</span></span>|<span data-ttu-id="bd019-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bd019-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bd019-110">Composant</span><span class="sxs-lookup"><span data-stu-id="bd019-110">Component</span></span>|<span data-ttu-id="bd019-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bd019-111">SQLEngine</span></span>|  
|<span data-ttu-id="bd019-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="bd019-112">Symbolic Name</span></span>||  
|<span data-ttu-id="bd019-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="bd019-113">Message Text</span></span>|<span data-ttu-id="bd019-114">Les dépendances signalées pour l'entité "%.\*ls" n'incluent pas de références aux colonnes.</span><span class="sxs-lookup"><span data-stu-id="bd019-114">The dependencies reported for entity "%.\*ls" do not include references to columns.</span></span> <span data-ttu-id="bd019-115">Cela est dû au fait que l'entité fait référence à un objet inexistant ou que l'une ou plusieurs instructions de l'entité comportent une erreur.</span><span class="sxs-lookup"><span data-stu-id="bd019-115">This is either because the entity references an object that does not exist or because of an error in one or more statements in the entity.</span></span>  <span data-ttu-id="bd019-116">Avant de réexécuter la requête, assurez-vous que l'entité ne comporte aucune erreur et que tous les objets référencés par l'entité existent.</span><span class="sxs-lookup"><span data-stu-id="bd019-116">Before rerunning the query, ensure that there are no errors in the entity and that all objects referenced by the entity exist.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bd019-117">Explication</span><span class="sxs-lookup"><span data-stu-id="bd019-117">Explanation</span></span>  
 <span data-ttu-id="bd019-118">La fonction système **sys.dm_sql_referenced_entities** signale toutes les dépendances au niveau des colonnes pour les références liées au schéma.</span><span class="sxs-lookup"><span data-stu-id="bd019-118">The **sys.dm_sql_referenced_entities** system function will report any column-level dependency for schema-bound references.</span></span> <span data-ttu-id="bd019-119">Par exemple, la fonction signale toutes les dépendances au niveau des colonnes pour une vue indexée car une vue indexée requiert une liaison de schéma.</span><span class="sxs-lookup"><span data-stu-id="bd019-119">For example, the function will report all column-level dependencies for an indexed view because an indexed view requires schema binding.</span></span> <span data-ttu-id="bd019-120">Toutefois, lorsque l'entité référencée n'est pas liée au schéma, les dépendances de colonne sont signalées uniquement lorsque toutes les instructions dans lesquelles les colonnes sont référencées peuvent être liées.</span><span class="sxs-lookup"><span data-stu-id="bd019-120">However, when the referenced entity is not schema-bound, column dependencies are reported only when all statements in which the columns are referenced can be bound.</span></span> <span data-ttu-id="bd019-121">Les instructions ne peuvent être correctement liées que si tous les objets existent au moment de l'analyse des instructions.</span><span class="sxs-lookup"><span data-stu-id="bd019-121">Statements can be successfully bound only if all objects exist at the time the statements are parsed.</span></span> <span data-ttu-id="bd019-122">Si la liaison échoue dans une instruction définie dans l’entité, les dépendances de colonnes ne sont pas signalées et la colonne **referenced_minor_id** retourne 0.</span><span class="sxs-lookup"><span data-stu-id="bd019-122">If any statement defined in the entity fails to bind, column dependencies will not be reported and the **referenced_minor_id** column will return 0.</span></span> <span data-ttu-id="bd019-123">Lorsque les dépendances de colonne ne peuvent pas être résolues, l'erreur 2020 est générée.</span><span class="sxs-lookup"><span data-stu-id="bd019-123">When column dependencies cannot be resolved, error 2020 is raised.</span></span> <span data-ttu-id="bd019-124">Cette erreur n'empêche pas la requête de retourner des dépendances au niveau objet.</span><span class="sxs-lookup"><span data-stu-id="bd019-124">This error does not prevent the query from returning object-level dependencies.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bd019-125">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="bd019-125">User Action</span></span>  
 <span data-ttu-id="bd019-126">Corrigez toutes les erreurs identifiées dans le message avant l'erreur 2020.</span><span class="sxs-lookup"><span data-stu-id="bd019-126">Correct any errors identified in the message before error 2020.</span></span> <span data-ttu-id="bd019-127">Par exemple, dans l'exemple de code suivant, la vue `Production.ApprovedDocuments` est définie dans les colonnes `Title`, `ChangeNumber` et `Status` de la table `Production.Document`.</span><span class="sxs-lookup"><span data-stu-id="bd019-127">For example, in the following code example the view `Production.ApprovedDocuments` is defined on the columns `Title`, `ChangeNumber`, and `Status` in the `Production.Document` table.</span></span> <span data-ttu-id="bd019-128">La fonction système **sys.dm_sql_referenced_entities** est interrogée pour les objets et les colonnes dont dépend la vue `ApprovedDocuments`.</span><span class="sxs-lookup"><span data-stu-id="bd019-128">The **sys.dm_sql_referenced_entities** system function is queried for the objects and columns on which the `ApprovedDocuments` view depends.</span></span> <span data-ttu-id="bd019-129">Étant donné que la vue n'est pas créée à l'aide de la clause WITH SCHEMA_BINDING, les colonnes référencées dans la vue peuvent être modifiées dans la table référencée.</span><span class="sxs-lookup"><span data-stu-id="bd019-129">Because the view is not created using the WITH SCHEMA_BINDING clause, the columns referenced in the view can be modified in the referenced table.</span></span> <span data-ttu-id="bd019-130">L'exemple modifie la colonne `ChangeNumber` de la table `Production.Document` en la renommant `TrackingNumber`.</span><span class="sxs-lookup"><span data-stu-id="bd019-130">The example alters the column `ChangeNumber` in the `Production.Document` table by renaming it to `TrackingNumber`.</span></span> <span data-ttu-id="bd019-131">L'affichage catalogue est interrogé de nouveau pour la vue `ApprovedDocuments` ; toutefois, il ne peut pas être lié à toutes les colonnes définies dans la vue.</span><span class="sxs-lookup"><span data-stu-id="bd019-131">The catalog view is queried again for the `ApprovedDocuments` view; however it cannot bind to all the columns defined in the view.</span></span> <span data-ttu-id="bd019-132">Les erreurs 207 et 2020 sont retournées pour identifier le problème.</span><span class="sxs-lookup"><span data-stu-id="bd019-132">Errors 207 and 2020 are returned identifying the problem.</span></span> <span data-ttu-id="bd019-133">Pour résoudre le problème, il est nécessaire de modifier la vue de façon à refléter le nouveau nom de la colonne.</span><span class="sxs-lookup"><span data-stu-id="bd019-133">To resolve the problem, the view must be altered to reflect the new name of the column.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 `CREATE VIEW Production.ApprovedDocuments`  
  
 `AS`  
  
 `SELECT Title, ChangeNumber, Status`  
  
 `FROM Production.Document`  
  
 `WHERE Status = 2;`  
  
 `GO`  
  
 `SELECT referenced_schema_name AS schema_name`  
  
 `,referenced_entity_name AS table_name`  
  
 `,referenced_minor_name AS referenced_column`  
  
 `FROM sys.dm_sql_referenced_entities ('Production.ApprovedDocuments', 'OBJECT');`  
  
 `GO`  
  
 `EXEC sp_rename 'Production.Document.ChangeNumber', 'TrackingNumber', 'COLUMN';`  
  
 `GO`  
  
 `SELECT referenced_schema_name AS schema_name`  
  
 `,referenced_entity_name AS table_name`  
  
 `,referenced_minor_name AS referenced_column`  
  
 `FROM sys.dm_sql_referenced_entities ('Production.ApprovedDocuments', 'OBJECT');`  
  
 `GO`  
  
 <span data-ttu-id="bd019-134">La requête retourne les messages d'erreur suivants.</span><span class="sxs-lookup"><span data-stu-id="bd019-134">The query returns the following error messages.</span></span>  
  
 `Msg 207, Level 16, State 1, Procedure ApprovedDocuments, Line 3`  
  
 `Invalid column name 'ChangeNumber'.`  
  
 `Msg 2020, Level 16, State 1, Line 1`  
  
 `The dependencies reported for entity`  
  
 `"Production.ApprovedDocuments" do not include references to`  
  
 `columns. This is either because the entity references an`  
  
 `object that does not exist or because of an error in one or`  
  
 `more statements in the entity. Before rerunning the query,`  
  
 `ensure that there are no errors in the entity and that all`  
  
 `objects referenced by the entity exist.`  
  
 <span data-ttu-id="bd019-135">L'exemple suivant corrige le nom de colonne dans la vue.</span><span class="sxs-lookup"><span data-stu-id="bd019-135">The following example corrects the column name in the view.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 `ALTER VIEW Production.ApprovedDocuments`  
  
 `AS`  
  
 `SELECT Title,TrackingNumber, Status`  
  
 `FROM Production.Document`  
  
 `WHERE Status = 2;`  
  
 `GO`  
  
## <a name="see-also"></a><span data-ttu-id="bd019-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bd019-136">See Also</span></span>  
 [<span data-ttu-id="bd019-137">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bd019-137">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
  
