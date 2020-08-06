---
title: Obtenir des informations au sujet d’une vue | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.viewproperties.general.f1
helpviewer_keywords:
- views [SQL Server], status information
- metadata [SQL Server], views
- dependencies [SQL Server], views
- displaying view information
- views [SQL Server], metadata
- viewing view information
- status information [SQL Server], views
- view dependencies
ms.assetid: 05a73e33-8f85-4fb6-80c1-1b659e753403
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4277aad4c1de0140606575c7ba437408518b3c8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600713"
---
# <a name="get-information-about-a-view"></a><span data-ttu-id="a05a1-102">Obtenir des informations au sujet d'une vue</span><span class="sxs-lookup"><span data-stu-id="a05a1-102">Get Information About a View</span></span>
  <span data-ttu-id="a05a1-103">Vous pouvez obtenir des informations sur la définition ou les propriétés d’une vue dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] en utilisant [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a05a1-103">You can gain information about a view's definition or properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a05a1-104">Vous devrez peut-être examiner la définition de la vue pour comprendre comment les données de celle-ci sont issues des tables source ou pour connaître les données définies par la vue.</span><span class="sxs-lookup"><span data-stu-id="a05a1-104">You may need to see the definition of the view to understand how its data is derived from the source tables or to see the data defined by the view.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a05a1-105">Si vous modifiez le nom d'un objet auquel une vue fait référence, vous devez modifier la vue pour que son texte reflète le nouveau nom de l'objet.</span><span class="sxs-lookup"><span data-stu-id="a05a1-105">If you change the name of an object referenced by a view, you must modify the view so that its text reflects the new name.</span></span> <span data-ttu-id="a05a1-106">Dès lors, avant de renommer un objet, affichez ses dépendances afin de déterminer si les vues sont affectées par la modification envisagée.</span><span class="sxs-lookup"><span data-stu-id="a05a1-106">Therefore, before renaming an object, display the dependencies of the object first to determine if any views are affected by the proposed change.</span></span>  
  
 <span data-ttu-id="a05a1-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="a05a1-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a05a1-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="a05a1-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a05a1-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a05a1-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a05a1-110">**Pour obtenir des informations sur une vue, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="a05a1-110">**To get information about a view, using:**</span></span>  
  
     [<span data-ttu-id="a05a1-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a05a1-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a05a1-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a05a1-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a05a1-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="a05a1-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a05a1-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a05a1-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a05a1-115">Autorisations</span><span class="sxs-lookup"><span data-stu-id="a05a1-115">Permissions</span></span>  
 <span data-ttu-id="a05a1-116">L'utilisation de `sp_helptext` pour retourner la définition d'une vue nécessite l'appartenance au rôle **public** .</span><span class="sxs-lookup"><span data-stu-id="a05a1-116">Using `sp_helptext` to return the definition of a view requires membership in the **public** role.</span></span> <span data-ttu-id="a05a1-117">L'utilisation de `sys.sql_expression_dependencies` pour rechercher toutes les dépendances d'une vue nécessite l'autorisation VIEW DEFINITION sur la base de données et l'autorisation SELECT sur `sys.sql_expression_dependencies` pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="a05a1-117">Using `sys.sql_expression_dependencies` to find all the dependencies on a view requires VIEW DEFINITION permission on the database and SELECT permission on `sys.sql_expression_dependencies` for the database.</span></span> <span data-ttu-id="a05a1-118">Les définitions d'objets système, telles que celles retournées dans SELECT OBJECT_DEFINITION, sont visibles publiquement.</span><span class="sxs-lookup"><span data-stu-id="a05a1-118">System object definitions, like the ones returned in SELECT OBJECT_DEFINITION, are publicly visible.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a05a1-119">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a05a1-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="get-view-properties-by-using-object-explorer"></a><span data-ttu-id="a05a1-120">Obtenir les propriétés de vue à l'aide de l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="a05a1-120">Get view properties by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="a05a1-121">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) en regard de la base de données qui contient la vue dont vous souhaitez afficher les propriétés, puis cliquez sur le signe plus (+) pour développer le dossier **Vues** .</span><span class="sxs-lookup"><span data-stu-id="a05a1-121">In **Object Explorer**, click the plus sign next to the database that contains the view to which you want to view the properties, and then click the plus sign to expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="a05a1-122">Cliquez avec le bouton droit sur la vue dont vous voulez afficher les propriétés, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a05a1-122">Right-click the view of which you want to view the properties and select **Properties**.</span></span>  
  
     <span data-ttu-id="a05a1-123">Les propriétés suivantes s'affichent dans la boîte de dialogue **Propriétés de la vue** .</span><span class="sxs-lookup"><span data-stu-id="a05a1-123">The following properties show in the **View Properties** dialog box.</span></span>  
  
     <span data-ttu-id="a05a1-124">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="a05a1-124">**Database**</span></span>  
     <span data-ttu-id="a05a1-125">Nom de la base de données contenant cette vue.</span><span class="sxs-lookup"><span data-stu-id="a05a1-125">The name of the database containing this view.</span></span>  
  
     <span data-ttu-id="a05a1-126">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="a05a1-126">**Server**</span></span>  
     <span data-ttu-id="a05a1-127">Nom de l'instance actuelle du serveur.</span><span class="sxs-lookup"><span data-stu-id="a05a1-127">The name of the current server instance.</span></span>  
  
     <span data-ttu-id="a05a1-128">**Utilisateur**</span><span class="sxs-lookup"><span data-stu-id="a05a1-128">**User**</span></span>  
     <span data-ttu-id="a05a1-129">Nom de l'utilisateur de cette connexion.</span><span class="sxs-lookup"><span data-stu-id="a05a1-129">The name of the user of this connection.</span></span>  
  
     <span data-ttu-id="a05a1-130">**Date de création**</span><span class="sxs-lookup"><span data-stu-id="a05a1-130">**Created date**</span></span>  
     <span data-ttu-id="a05a1-131">Affiche la date de création de la vue.</span><span class="sxs-lookup"><span data-stu-id="a05a1-131">Displays the date the view was created.</span></span>  
  
     <span data-ttu-id="a05a1-132">**Nom**</span><span class="sxs-lookup"><span data-stu-id="a05a1-132">**Name**</span></span>  
     <span data-ttu-id="a05a1-133">Nom de la vue actuelle.</span><span class="sxs-lookup"><span data-stu-id="a05a1-133">The name of the current view.</span></span>  
  
     <span data-ttu-id="a05a1-134">**Schéma**</span><span class="sxs-lookup"><span data-stu-id="a05a1-134">**Schema**</span></span>  
     <span data-ttu-id="a05a1-135">Affiche le schéma propriétaire de la vue.</span><span class="sxs-lookup"><span data-stu-id="a05a1-135">Displays the schema that owns the view.</span></span>  
  
     <span data-ttu-id="a05a1-136">**Objet système**</span><span class="sxs-lookup"><span data-stu-id="a05a1-136">**System object**</span></span>  
     <span data-ttu-id="a05a1-137">Indique si la vue est un objet système.</span><span class="sxs-lookup"><span data-stu-id="a05a1-137">Indicates whether the view is a system object.</span></span> <span data-ttu-id="a05a1-138">Les valeurs sont True et False.</span><span class="sxs-lookup"><span data-stu-id="a05a1-138">Values are True and False.</span></span>  
  
     <span data-ttu-id="a05a1-139">**Valeurs ANSI NULL**</span><span class="sxs-lookup"><span data-stu-id="a05a1-139">**ANSI NULLs**</span></span>  
     <span data-ttu-id="a05a1-140">Indique si l'objet a été créé avec l'option Valeurs ANSI NULL.</span><span class="sxs-lookup"><span data-stu-id="a05a1-140">Indicates if the object was created with the ANSI NULLs option.</span></span>  
  
     <span data-ttu-id="a05a1-141">**Chiffré**</span><span class="sxs-lookup"><span data-stu-id="a05a1-141">**Encrypted**</span></span>  
     <span data-ttu-id="a05a1-142">Indique si la vue est chiffrée.</span><span class="sxs-lookup"><span data-stu-id="a05a1-142">Indicates whether the view is encrypted.</span></span> <span data-ttu-id="a05a1-143">Les valeurs sont True et False.</span><span class="sxs-lookup"><span data-stu-id="a05a1-143">Values are True and False.</span></span>  
  
     <span data-ttu-id="a05a1-144">**Identificateur entre guillemets**</span><span class="sxs-lookup"><span data-stu-id="a05a1-144">**Quoted identifier**</span></span>  
     <span data-ttu-id="a05a1-145">Indique si l'objet a été créé avec l'option Identificateurs entre guillemets.</span><span class="sxs-lookup"><span data-stu-id="a05a1-145">Indicates if the object was created with the quoted identifier option.</span></span>  
  
     <span data-ttu-id="a05a1-146">**Lié(e) au schéma**</span><span class="sxs-lookup"><span data-stu-id="a05a1-146">**Schema bound**</span></span>  
     <span data-ttu-id="a05a1-147">Indique si la vue est liée au schéma.</span><span class="sxs-lookup"><span data-stu-id="a05a1-147">Indicates whether the view is schema-bound.</span></span> <span data-ttu-id="a05a1-148">Les valeurs sont True et False.</span><span class="sxs-lookup"><span data-stu-id="a05a1-148">Values are True and False.</span></span> <span data-ttu-id="a05a1-149">Pour plus d’informations sur les vues liées au schéma, consultez la partie SCHEMABINDING de [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a05a1-149">For information about schema-bound views, see the SCHEMABINDING portion of [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span></span>  
  
#### <a name="getting-view-properties-by-using-the-view-designer-tool"></a><span data-ttu-id="a05a1-150">Obtention des propriétés d'une vue à l'aide de l'outil Concepteur de vues</span><span class="sxs-lookup"><span data-stu-id="a05a1-150">Getting view properties by using the View Designer tool</span></span>  
  
1.  <span data-ttu-id="a05a1-151">Dans l' **Explorateur d'objets**, développez la base de données qui contient la vue dont vous souhaitez afficher les propriétés, puis développez le dossier **Vues** .</span><span class="sxs-lookup"><span data-stu-id="a05a1-151">In **Object Explorer**, expand the database that contains the view to which you want to view the properties, and then expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="a05a1-152">Cliquez avec le bouton droit sur la vue dont vous voulez afficher les propriétés, puis sélectionnez **Conception**.</span><span class="sxs-lookup"><span data-stu-id="a05a1-152">Right-click the view of which you want to view the properties and select **Design**.</span></span>  
  
3.  <span data-ttu-id="a05a1-153">Cliquez avec le bouton droit dans l’espace du volet Schéma et cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a05a1-153">Right-click in the blank space of the Diagram pane and click **Properties**.</span></span>  
  
     <span data-ttu-id="a05a1-154">Les propriétés suivantes sont affichées dans le volet **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="a05a1-154">The following properties show in the **Properties** pane.</span></span>  
  
     <span data-ttu-id="a05a1-155">**(Nom)**</span><span class="sxs-lookup"><span data-stu-id="a05a1-155">**(Name)**</span></span>  
     <span data-ttu-id="a05a1-156">Nom de la vue actuelle.</span><span class="sxs-lookup"><span data-stu-id="a05a1-156">The name of the current view.</span></span>  
  
     <span data-ttu-id="a05a1-157">**Database Name**</span><span class="sxs-lookup"><span data-stu-id="a05a1-157">**Database Name**</span></span>  
     <span data-ttu-id="a05a1-158">Nom de la base de données contenant cette vue.</span><span class="sxs-lookup"><span data-stu-id="a05a1-158">The name of the database containing this view.</span></span>  
  
     <span data-ttu-id="a05a1-159">**Description**</span><span class="sxs-lookup"><span data-stu-id="a05a1-159">**Description**</span></span>  
     <span data-ttu-id="a05a1-160">Brève description de la vue actuelle.</span><span class="sxs-lookup"><span data-stu-id="a05a1-160">A brief description of the current view.</span></span>  
  
     <span data-ttu-id="a05a1-161">**Schéma**</span><span class="sxs-lookup"><span data-stu-id="a05a1-161">**Schema**</span></span>  
     <span data-ttu-id="a05a1-162">Affiche le schéma propriétaire de la vue.</span><span class="sxs-lookup"><span data-stu-id="a05a1-162">Displays the schema that owns the view.</span></span>  
  
     <span data-ttu-id="a05a1-163">**Nom de serveur**</span><span class="sxs-lookup"><span data-stu-id="a05a1-163">**Server Name**</span></span>  
     <span data-ttu-id="a05a1-164">Nom de l'instance actuelle du serveur.</span><span class="sxs-lookup"><span data-stu-id="a05a1-164">The name of the current server instance.</span></span>  
  
     <span data-ttu-id="a05a1-165">**Lier au schéma**</span><span class="sxs-lookup"><span data-stu-id="a05a1-165">**Bind to Schema**</span></span>  
     <span data-ttu-id="a05a1-166">Empêche les utilisateurs de modifier les objets sous-jacents qui contribuent à cette vue de quelque manière qui invaliderait la définition de la vue.</span><span class="sxs-lookup"><span data-stu-id="a05a1-166">Prevents users from modifying the underlying objects that contribute to this view in any way that would invalidate the view definition.</span></span>  
  
     <span data-ttu-id="a05a1-167">**Déterministe**</span><span class="sxs-lookup"><span data-stu-id="a05a1-167">**Deterministic**</span></span>  
     <span data-ttu-id="a05a1-168">Indique si le type de données de la colonne sélectionnée peut être déterminé avec certitude</span><span class="sxs-lookup"><span data-stu-id="a05a1-168">Shows whether the data type of the selected column can be determined with certainty</span></span>  
  
     <span data-ttu-id="a05a1-169">**Valeurs distinctes**</span><span class="sxs-lookup"><span data-stu-id="a05a1-169">**Distinct Values**</span></span>  
     <span data-ttu-id="a05a1-170">Spécifie que la requête filtrera les doublons dans la vue.</span><span class="sxs-lookup"><span data-stu-id="a05a1-170">Specifies that the query will filter out duplicates in the view.</span></span> <span data-ttu-id="a05a1-171">Cette option est utile lorsque vous utilisez uniquement certaines colonnes d'une table et que ces colonnes peuvent contenir des valeurs dupliquées, ou encore lorsque le processus de jointure de plusieurs tables crée des lignes en double dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="a05a1-171">This option is useful when you are using only some of the columns from a table and those columns might contain duplicate values, or when the process of joining two or more tables produces duplicate rows in the result set.</span></span> <span data-ttu-id="a05a1-172">Choisir cette option équivaut à insérer le mot-clé DISTINCT dans l’instruction à l’intérieur du volet SQL.</span><span class="sxs-lookup"><span data-stu-id="a05a1-172">Choosing this option is equivalent to inserting the keyword DISTINCT into the statement in the SQL pane.</span></span>  
  
     <span data-ttu-id="a05a1-173">**Extension GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="a05a1-173">**GROUP BY Extension**</span></span>  
     <span data-ttu-id="a05a1-174">Spécifie que d'autres options sont disponibles pour les vues basées sur des requêtes d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="a05a1-174">Specifies that additional options for views based on aggregate queries are available.</span></span>  
  
     <span data-ttu-id="a05a1-175">**Sélectionne toutes les colonnes**</span><span class="sxs-lookup"><span data-stu-id="a05a1-175">**Output All Columns**</span></span>  
     <span data-ttu-id="a05a1-176">Indique si toutes les colonnes sont retournées par la vue sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a05a1-176">Shows whether all columns are returned by the selected view.</span></span> <span data-ttu-id="a05a1-177">Ce comportement est défini lorsque la vue est créée.</span><span class="sxs-lookup"><span data-stu-id="a05a1-177">This is set at the time the view is created.</span></span>  
  
     <span data-ttu-id="a05a1-178">**Commentaire SQL**</span><span class="sxs-lookup"><span data-stu-id="a05a1-178">**SQL Comment**</span></span>  
     <span data-ttu-id="a05a1-179">Affiche une description des instructions SQL.</span><span class="sxs-lookup"><span data-stu-id="a05a1-179">Shows a description of the SQL statements.</span></span> <span data-ttu-id="a05a1-180">Pour afficher l’intégralité de la description ou la modifier, cliquez sur la description, puis sur le bouton de sélection **(...)** situé à droite de la propriété.</span><span class="sxs-lookup"><span data-stu-id="a05a1-180">To see the entire description, or to edit it, click the description and then click the ellipses **(...)** to the right of the property.</span></span> <span data-ttu-id="a05a1-181">Vos commentaires peuvent contenir les noms des utilisateurs de la vue et le moment d'utilisation.</span><span class="sxs-lookup"><span data-stu-id="a05a1-181">Your comments might include information such as who uses the view and when they use it.</span></span>  
  
     <span data-ttu-id="a05a1-182">**Spécification Top**</span><span class="sxs-lookup"><span data-stu-id="a05a1-182">**Top Specification**</span></span>  
     <span data-ttu-id="a05a1-183">Se développe pour afficher les propriétés **Top**, **Expression**, **Pourcentage**et **With Ties** .</span><span class="sxs-lookup"><span data-stu-id="a05a1-183">Expands to show properties for the **Top**, **Expression**, **Percent**, and **With Ties** properties.</span></span>  
  
     <span data-ttu-id="a05a1-184">**(Top)**</span><span class="sxs-lookup"><span data-stu-id="a05a1-184">**(Top)**</span></span>  
     <span data-ttu-id="a05a1-185">Indique que la vue doit contenir une clause TOP, qui ne retourne que les n premières lignes ou n premiers pour cent des lignes du jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="a05a1-185">Specifies that the view will include a TOP clause, which returns only the first n rows or first n percentage of rows in the result set.</span></span> <span data-ttu-id="a05a1-186">Par défaut, la vue retourne les 10 premières lignes dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="a05a1-186">The default is that the view returns the first 10 rows in the result set.</span></span> <span data-ttu-id="a05a1-187">Utilisez cette option pour modifier le nombre de lignes à retourner ou pour spécifier un autre pourcentage.</span><span class="sxs-lookup"><span data-stu-id="a05a1-187">Use this to change the number of rows to return or to specify a different percentage</span></span>  
  
     <span data-ttu-id="a05a1-188">**Expression**</span><span class="sxs-lookup"><span data-stu-id="a05a1-188">**Expression**</span></span>  
     <span data-ttu-id="a05a1-189">Affiche le pourcentage (si **Pourcentage** a la valeur **Oui**) ou les enregistrements (si **Pourcentage** a la valeur **Non**) que la vue retourne.</span><span class="sxs-lookup"><span data-stu-id="a05a1-189">Shows what percent (if **Percent** is set to **Yes**) or records (if **Percent** is set to **No**) that the view will return.</span></span>  
  
     <span data-ttu-id="a05a1-190">**Pourcentage**</span><span class="sxs-lookup"><span data-stu-id="a05a1-190">**Percent**</span></span>  
     <span data-ttu-id="a05a1-191">Indique que la requête doit contenir une clause **TOP** , qui ne retourne que les n premiers pour cent des lignes du jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="a05a1-191">Specifies that the query will include a **TOP** clause, returning only the first n percentage of rows in the result set</span></span>  
  
     <span data-ttu-id="a05a1-192">**Avec liens**</span><span class="sxs-lookup"><span data-stu-id="a05a1-192">**With Ties**</span></span>  
     <span data-ttu-id="a05a1-193">Spécifie que la vue inclura une clause **WITH TIES** .</span><span class="sxs-lookup"><span data-stu-id="a05a1-193">Specifies that the view will include a **WITH TIES** clause.</span></span> <span data-ttu-id="a05a1-194">**WITH TIES** est utile si une vue inclut une clause **ORDER BY** et une clause **TOP** basée sur un pourcentage.</span><span class="sxs-lookup"><span data-stu-id="a05a1-194">**WITH TIES** is useful if a view includes an **ORDER BY** clause and a **TOP** clause based on percentage.</span></span> <span data-ttu-id="a05a1-195">Si cette option est activée et si le pourcentage s'arrête au milieu d'un groupe de lignes auxquelles correspondent des valeurs identiques dans la clause **ORDER BY** , la vue est agrandie de façon à inclure ces lignes.</span><span class="sxs-lookup"><span data-stu-id="a05a1-195">If this option is set, and if the percentage cutoff falls in the middle of a set of rows with identical values in the **ORDER BY** clause, the view is extended to include all such rows.</span></span>  
  
     <span data-ttu-id="a05a1-196">**Spécification de mise à jour**</span><span class="sxs-lookup"><span data-stu-id="a05a1-196">**Update Specification**</span></span>  
     <span data-ttu-id="a05a1-197">Se développe pour afficher les propriétés des propriétés **Mettre à jour en utilisant les règles de vue** et **Option Vérifier** .</span><span class="sxs-lookup"><span data-stu-id="a05a1-197">Expands to show properties for the **Update Using View Rules** and **Check Option** properties.</span></span>  
  
     <span data-ttu-id="a05a1-198">**(Mettre à jour en utilisant les règles de vue)**</span><span class="sxs-lookup"><span data-stu-id="a05a1-198">**(Update Using View Rules)**</span></span>  
     <span data-ttu-id="a05a1-199">Indique que toutes les mises à jour et insertions apportées à la vue seront traduites par Microsoft Data Access Components (MDAC) en instructions SQL qui font référence à la vue, plutôt qu'en instructions SQL qui font directement référence aux tables de base de la vue.</span><span class="sxs-lookup"><span data-stu-id="a05a1-199">Indicates that all updates and insertions to the view will be translated by Microsoft Data Access Components (MDAC) into SQL statements that refer to the view, rather than into SQL statements that refer directly to the view's base tables.</span></span>  
  
     <span data-ttu-id="a05a1-200">Dans certains cas, les manifestes MDAC considèrent les opérations de mise à jour et d'insertion dans une vue comme des mises à jour et des insertions dans les tables de base sous-jacentes de la vue.</span><span class="sxs-lookup"><span data-stu-id="a05a1-200">In some cases, MDAC manifests view update and view insert operations as updates and inserts against the view's underlying base tables.</span></span> <span data-ttu-id="a05a1-201">En sélectionnant **Mettre à jour en utilisant les règles de vue**, vous pouvez vous assurer que MDAC génère les opérations de mise à jour et d'insertion sur la vue proprement dite.</span><span class="sxs-lookup"><span data-stu-id="a05a1-201">By selecting **Update Using View Rules**, you can ensure that MDAC generates update and insert operations against the view itself.</span></span>  
  
     <span data-ttu-id="a05a1-202">**Option Vérifier**</span><span class="sxs-lookup"><span data-stu-id="a05a1-202">**Check Option**</span></span>  
     <span data-ttu-id="a05a1-203">Indique que quand vous ouvrez cette vue et modifiez le volet de **Résultats** , la source de données vérifie si les données ajoutées ou modifiées respectent la clause **WHERE** de la définition de la vue.</span><span class="sxs-lookup"><span data-stu-id="a05a1-203">Indicates that when you open this view and modify the **Results** pane, the data source checks whether the added or modified data satisfies the **WHERE** clause of the view definition.</span></span> <span data-ttu-id="a05a1-204">Si votre modification ne respecte pas la clause **WHERE** , un message d'erreur contenant des informations supplémentaires s'affiche.</span><span class="sxs-lookup"><span data-stu-id="a05a1-204">If your modification do not satisfy the **WHERE** clause, you will see an error with more information.</span></span>  
  
#### <a name="to-get-dependencies-on-the-view"></a><span data-ttu-id="a05a1-205">Pour obtenir les dépendances de la vue</span><span class="sxs-lookup"><span data-stu-id="a05a1-205">To get dependencies on the view</span></span>  
  
1.  <span data-ttu-id="a05a1-206">Dans l' **Explorateur d'objets**, développez la base de données qui contient la vue dont vous souhaitez afficher les propriétés, puis développez le dossier **Vues** .</span><span class="sxs-lookup"><span data-stu-id="a05a1-206">In **Object Explorer**, expand the database that contains the view to which you want to view the properties, and then expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="a05a1-207">Cliquez avec le bouton droit sur la vue dont vous voulez afficher les propriétés, puis sélectionnez **Afficher les dépendances**.</span><span class="sxs-lookup"><span data-stu-id="a05a1-207">Right-click the view of which you want to view the properties and select **View Dependencies**.</span></span>  
  
3.  <span data-ttu-id="a05a1-208">Sélectionnez **Objets dépendant de [nom de la vue]** pour afficher les objets qui font référence à la vue.</span><span class="sxs-lookup"><span data-stu-id="a05a1-208">Select **Objects that depend on [view name]** to display the objects that refer to the view.</span></span>  
  
4.  <span data-ttu-id="a05a1-209">Sélectionnez **Objets dont dépend [nom de la vue]** pour afficher les objets référencés par la vue.</span><span class="sxs-lookup"><span data-stu-id="a05a1-209">Select **Objects on which [view name] depends** to display the objects that are referenced by the view.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a05a1-210">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a05a1-210">Using Transact-SQL</span></span>  
  
#### <a name="to-get-the-definition-and-properties-of-a-view"></a><span data-ttu-id="a05a1-211">Pour obtenir la définition et les propriétés d'une vue</span><span class="sxs-lookup"><span data-stu-id="a05a1-211">To get the definition and properties of a view</span></span>  
  
1.  <span data-ttu-id="a05a1-212">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a05a1-212">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a05a1-213">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="a05a1-213">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a05a1-214">Copiez et collez l'un des exemples suivants dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="a05a1-214">Copy and paste one of the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT definition, uses_ansi_nulls, uses_quoted_identifier, is_schema_bound  
    FROM sys.sql_modules  
    WHERE object_id = OBJECT_ID('HumanResources.vEmployee');   
    GO  
    ```  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    SELECT OBJECT_DEFINITION (OBJECT_ID('HumanResources.vEmployee')) AS ObjectDefinition;   
    GO  
    ```  
  
    ```  
    EXEC sp_helptext 'HumanResources.vEmployee';  
    ```  
  
 <span data-ttu-id="a05a1-215">Pour plus d’informations, consultez [sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql), [OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql) et [sp_helptext &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a05a1-215">For more information, see [sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql), [OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql) and [sp_helptext &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql).</span></span>  
  
#### <a name="to-get-the-dependencies-of-a-view"></a><span data-ttu-id="a05a1-216">Pour obtenir les dépendances d'une vue</span><span class="sxs-lookup"><span data-stu-id="a05a1-216">To get the dependencies of a view</span></span>  
  
1.  <span data-ttu-id="a05a1-217">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a05a1-217">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a05a1-218">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="a05a1-218">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a05a1-219">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="a05a1-219">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT OBJECT_NAME(referencing_id) AS referencing_entity_name,   
        o.type_desc AS referencing_desciption,   
        COALESCE(COL_NAME(referencing_id, referencing_minor_id), '(n/a)') AS referencing_minor_id,   
        referencing_class_desc, referenced_class_desc,  
        referenced_server_name, referenced_database_name, referenced_schema_name,  
        referenced_entity_name,   
        COALESCE(COL_NAME(referenced_id, referenced_minor_id), '(n/a)') AS referenced_column_name,  
        is_caller_dependent, is_ambiguous  
    FROM sys.sql_expression_dependencies AS sed  
    INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
    WHERE referencing_id = OBJECT_ID(N'Production.vProductAndDescription');  
    GO  
    ```  
  
 <span data-ttu-id="a05a1-220">Pour plus d’informations, consultez [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) et [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a05a1-220">For more information, see [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) and [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span></span>  
  
  
