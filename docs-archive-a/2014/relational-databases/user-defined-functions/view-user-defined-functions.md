---
title: Afficher les fonctions définies par l’utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.udfproperties.general.f1
- sql12.swb.functionproperties.general.f1
helpviewer_keywords:
- displaying user-defined functions
- viewing user-defined functions
- user-defined functions [SQL Server], viewing
- status information [SQL Server], user-defined functions
ms.assetid: a45dfab5-6384-4311-b935-2e23a70c5c10
author: rothja
ms.author: jroth
ms.openlocfilehash: 5248f75540b72b489a7605b2cca34144dfcfedbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599839"
---
# <a name="view-user-defined-functions"></a><span data-ttu-id="84a47-102">Afficher les fonctions définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="84a47-102">View User-defined Functions</span></span>
  <span data-ttu-id="84a47-103">Vous pouvez obtenir des informations sur la définition ou les propriétés d'une fonction définie par l'utilisateur dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84a47-103">You can gain information about the definition or properties of a user-defined function in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="84a47-104">Vous devrez peut-être examiner la définition de la fonction pour comprendre comment les données de celle-ci sont issues des tables source ou pour connaître les données définies par la fonction.</span><span class="sxs-lookup"><span data-stu-id="84a47-104">You may need to see the definition of the function to understand how its data is derived from the source tables or to see the data defined by the function.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="84a47-105">Si vous modifiez le nom d'un objet auquel une fonction fait référence, vous devez modifier la fonction pour que son texte reflète le nouveau nom de l'objet.</span><span class="sxs-lookup"><span data-stu-id="84a47-105">If you change the name of an object referenced by a function, you must modify that function so that its text reflects the new name.</span></span> <span data-ttu-id="84a47-106">Par conséquent, avant de renommer un objet, affichez les dépendances de l'objet pour savoir si des fonctions peuvent être concernées par la modification projetée.</span><span class="sxs-lookup"><span data-stu-id="84a47-106">Therefore, before renaming an object, display the dependencies of the object first to determine if any functions are affected by the proposed change.</span></span>  
  
 <span data-ttu-id="84a47-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="84a47-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="84a47-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="84a47-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="84a47-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="84a47-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="84a47-110">**Pour obtenir des informations sur une fonction, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="84a47-110">**To get information about a function, using:**</span></span>  
  
     [<span data-ttu-id="84a47-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="84a47-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="84a47-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="84a47-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="84a47-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="84a47-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="84a47-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="84a47-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="84a47-115">Autorisations</span><span class="sxs-lookup"><span data-stu-id="84a47-115">Permissions</span></span>  
 <span data-ttu-id="84a47-116">L’utilisation de **sys.sql_expression_dependencies** pour rechercher toutes les dépendances sur une fonction nécessite l’autorisation VIEW DEFINITION sur la base de données et l’autorisation SELECT sur **sys.sql_expression_dependencies** pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="84a47-116">Using **sys.sql_expression_dependencies** to find all the dependencies on a function requires VIEW DEFINITION permission on the database and SELECT permission on **sys.sql_expression_dependencies** for the database.</span></span> <span data-ttu-id="84a47-117">Les définitions d'objets système, telles que celles retournées dans OBJECT_DEFINITION, sont visibles publiquement.</span><span class="sxs-lookup"><span data-stu-id="84a47-117">System object definitions, like the ones returned in OBJECT_DEFINITION, are publicly visible.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="84a47-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="84a47-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-show-a-user-defined-functions-properties"></a><span data-ttu-id="84a47-119">Pour afficher les propriétés d’une fonction définie par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="84a47-119">To show a user-defined function's properties</span></span>  
  
1.  <span data-ttu-id="84a47-120">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) en regard de la base de données qui contient la fonction dont vous souhaitez afficher les propriétés, puis cliquez sur le signe plus (+) pour développer le dossier **Programmabilité** .</span><span class="sxs-lookup"><span data-stu-id="84a47-120">In **Object Explorer**, click the plus sign next to the database that contains the function to which you want to view the properties, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="84a47-121">Cliquez sur le signe plus (+) pour développer le dossier **Fonctions** .</span><span class="sxs-lookup"><span data-stu-id="84a47-121">Click the plus sign to expand the **Functions** folder.</span></span>  
  
3.  <span data-ttu-id="84a47-122">Cliquez sur le signe plus (+) pour développer le dossier qui contient la fonction dont vous souhaitez afficher les propriétés :</span><span class="sxs-lookup"><span data-stu-id="84a47-122">Click the plus sign to expand the folder that contains the function to which you want to view the properties:</span></span>  
  
    -   <span data-ttu-id="84a47-123">Fonction table</span><span class="sxs-lookup"><span data-stu-id="84a47-123">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="84a47-124">Fonction scalaire</span><span class="sxs-lookup"><span data-stu-id="84a47-124">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="84a47-125">Fonction d'agrégation</span><span class="sxs-lookup"><span data-stu-id="84a47-125">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="84a47-126">Cliquez avec le bouton droit sur la fonction dont vous voulez afficher les propriétés, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="84a47-126">Right-click the function of which you want to view the properties and select **Properties**.</span></span>  
  
     <span data-ttu-id="84a47-127">Les propriétés suivantes s’affichent dans la boîte de dialogue **Propriétés de la fonction -** _nom_fonction_.</span><span class="sxs-lookup"><span data-stu-id="84a47-127">The following properties appear in the **Function Properties -** _function_name_ dialog box.</span></span>  
  
     <span data-ttu-id="84a47-128">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="84a47-128">**Database**</span></span>  
     <span data-ttu-id="84a47-129">Nom de la base de données contenant cette fonction.</span><span class="sxs-lookup"><span data-stu-id="84a47-129">The name of the database containing this function.</span></span>  
  
     <span data-ttu-id="84a47-130">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="84a47-130">**Server**</span></span>  
     <span data-ttu-id="84a47-131">Nom de l'instance actuelle du serveur.</span><span class="sxs-lookup"><span data-stu-id="84a47-131">The name of the current server instance.</span></span>  
  
     <span data-ttu-id="84a47-132">**Utilisateur**</span><span class="sxs-lookup"><span data-stu-id="84a47-132">**User**</span></span>  
     <span data-ttu-id="84a47-133">Nom de l'utilisateur de cette connexion.</span><span class="sxs-lookup"><span data-stu-id="84a47-133">The name of the user of this connection.</span></span>  
  
     <span data-ttu-id="84a47-134">**Date de création**</span><span class="sxs-lookup"><span data-stu-id="84a47-134">**Created date**</span></span>  
     <span data-ttu-id="84a47-135">Affiche la date à laquelle la fonction a été créée.</span><span class="sxs-lookup"><span data-stu-id="84a47-135">Displays the date the function was created.</span></span>  
  
     <span data-ttu-id="84a47-136">**Exécuter en tant que**</span><span class="sxs-lookup"><span data-stu-id="84a47-136">**Execute As**</span></span>  
     <span data-ttu-id="84a47-137">Contexte d'exécution de la fonction.</span><span class="sxs-lookup"><span data-stu-id="84a47-137">Execution context for the function.</span></span>  
  
     <span data-ttu-id="84a47-138">**Nom**</span><span class="sxs-lookup"><span data-stu-id="84a47-138">**Name**</span></span>  
     <span data-ttu-id="84a47-139">Nom de la fonction actuelle.</span><span class="sxs-lookup"><span data-stu-id="84a47-139">The name of the current function.</span></span>  
  
     <span data-ttu-id="84a47-140">**Schéma**</span><span class="sxs-lookup"><span data-stu-id="84a47-140">**Schema**</span></span>  
     <span data-ttu-id="84a47-141">Affiche le schéma auquel appartient la fonction.</span><span class="sxs-lookup"><span data-stu-id="84a47-141">Displays the schema that owns the function.</span></span>  
  
     <span data-ttu-id="84a47-142">**Objet système**</span><span class="sxs-lookup"><span data-stu-id="84a47-142">**System object**</span></span>  
     <span data-ttu-id="84a47-143">Indique si la fonction est un objet système.</span><span class="sxs-lookup"><span data-stu-id="84a47-143">Indicates whether the function is a system object.</span></span> <span data-ttu-id="84a47-144">Les valeurs sont True et False.</span><span class="sxs-lookup"><span data-stu-id="84a47-144">Values are True and False.</span></span>  
  
     <span data-ttu-id="84a47-145">**Valeurs ANSI NULL**</span><span class="sxs-lookup"><span data-stu-id="84a47-145">**ANSI NULLs**</span></span>  
     <span data-ttu-id="84a47-146">Indique si l'objet a été créé avec l'option Valeurs ANSI NULL.</span><span class="sxs-lookup"><span data-stu-id="84a47-146">Indicates if the object was created with the ANSI NULLs option.</span></span>  
  
     <span data-ttu-id="84a47-147">**Chiffré**</span><span class="sxs-lookup"><span data-stu-id="84a47-147">**Encrypted**</span></span>  
     <span data-ttu-id="84a47-148">Indique si la fonction est chiffrée.</span><span class="sxs-lookup"><span data-stu-id="84a47-148">Indicates whether the function is encrypted.</span></span> <span data-ttu-id="84a47-149">Les valeurs sont True et False.</span><span class="sxs-lookup"><span data-stu-id="84a47-149">Values are True and False.</span></span>  
  
     <span data-ttu-id="84a47-150">**Type de fonction**</span><span class="sxs-lookup"><span data-stu-id="84a47-150">**Function Type**</span></span>  
     <span data-ttu-id="84a47-151">Type de la fonction définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="84a47-151">The type of user defined function.</span></span>  
  
     <span data-ttu-id="84a47-152">**Identificateur entre guillemets**</span><span class="sxs-lookup"><span data-stu-id="84a47-152">**Quoted identifier**</span></span>  
     <span data-ttu-id="84a47-153">Indique si l'objet a été créé avec l'option Identificateurs entre guillemets.</span><span class="sxs-lookup"><span data-stu-id="84a47-153">Indicates if the object was created with the quoted identifier option.</span></span>  
  
     <span data-ttu-id="84a47-154">**Lié(e) au schéma**</span><span class="sxs-lookup"><span data-stu-id="84a47-154">**Schema bound**</span></span>  
     <span data-ttu-id="84a47-155">Indique si la fonction est liée au schéma.</span><span class="sxs-lookup"><span data-stu-id="84a47-155">Indicates whether the function is schema-bound.</span></span> <span data-ttu-id="84a47-156">Les valeurs sont True et False.</span><span class="sxs-lookup"><span data-stu-id="84a47-156">Values are True and False.</span></span> <span data-ttu-id="84a47-157">Pour plus d’informations sur les fonctions liées à un schéma, consultez la section SCHEMABINDING de [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="84a47-157">For information about schema-bound functions, see the SCHEMABINDING section of [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="84a47-158">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="84a47-158">Using Transact-SQL</span></span>  
  
#### <a name="to-get-the-definition-and-properties-of-a-function"></a><span data-ttu-id="84a47-159">Pour obtenir la définition et les propriétés d'une fonction</span><span class="sxs-lookup"><span data-stu-id="84a47-159">To get the definition and properties of a function</span></span>  
  
1.  <span data-ttu-id="84a47-160">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84a47-160">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="84a47-161">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="84a47-161">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="84a47-162">Copiez et collez l'un des exemples suivants dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="84a47-162">Copy and paste one of the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Get the function name, definition, and relevant properties  
    SELECT sm.object_id,   
       OBJECT_NAME(sm.object_id) AS object_name,   
       o.type,   
       o.type_desc,   
       sm.definition,  
       sm.uses_ansi_nulls,  
       sm.uses_quoted_identifier,  
       sm.is_schema_bound,  
       sm.execute_as_principal_id  
    -- using the two system tables sys.sql_modules and sys.objects  
    FROM sys.sql_modules AS sm  
    JOIN sys.objects AS o ON sm.object_id = o.object_id  
    -- from the function 'dbo.ufnGetProductDealerPrice'  
    WHERE sm.object_id = OBJECT_ID('dbo.ufnGetProductDealerPrice')  
    ORDER BY o.type;  
    GO  
  
    ```  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Get the definition of the function dbo.ufnGetProductDealerPrice  
    SELECT OBJECT_DEFINITION (OBJECT_ID('dbo.ufnGetProductDealerPrice')) AS ObjectDefinition;  
    GO  
    ```  
  
 <span data-ttu-id="84a47-163">Pour plus d’informations, consultez [sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) et [OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="84a47-163">For more information, see [sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) and [OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql).</span></span>  
  
#### <a name="to-get-the-dependencies-of-a-function"></a><span data-ttu-id="84a47-164">Pour obtenir les dépendances d'une fonction</span><span class="sxs-lookup"><span data-stu-id="84a47-164">To get the dependencies of a function</span></span>  
  
1.  <span data-ttu-id="84a47-165">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84a47-165">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="84a47-166">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="84a47-166">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="84a47-167">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="84a47-167">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Get all of the dependency information  
    SELECT OBJECT_NAME(sed.referencing_id) AS referencing_entity_name,   
        o.type_desc AS referencing_desciption,   
        COALESCE(COL_NAME(sed.referencing_id, sed.referencing_minor_id), '(n/a)') AS referencing_minor_id,   
        sed.referencing_class_desc, sed.referenced_class_desc,  
        sed.referenced_server_name, sed.referenced_database_name, sed.referenced_schema_name,  
        sed.referenced_entity_name,   
        COALESCE(COL_NAME(sed.referenced_id, sed.referenced_minor_id), '(n/a)') AS referenced_column_name,  
        sed.is_caller_dependent, sed.is_ambiguous  
    -- from the two system tables sys.sql_expression_dependencies and sys.object  
    FROM sys.sql_expression_dependencies AS sed  
    INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
    -- on the function dbo.ufnGetProductDealerPrice  
    WHERE sed.referencing_id = OBJECT_ID('dbo.ufnGetProductDealerPrice');  
    GO  
    ```  
  
 <span data-ttu-id="84a47-168">Pour plus d’informations, consultez [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) et [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="84a47-168">For more information, see [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) and [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span></span>  
  
  
