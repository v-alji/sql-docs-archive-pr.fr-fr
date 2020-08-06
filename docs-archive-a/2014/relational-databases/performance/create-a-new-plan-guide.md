---
title: Créer un repère de plan | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.designer.newplanguide.f1
helpviewer_keywords:
- creating plan guides
- plan guides [SQL Server]. creating
ms.assetid: e1ad78bb-4857-40ea-a0c6-dcf5c28aef2f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 60ba31e2a63575a316db5befb397bea59c0ad1e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614570"
---
# <a name="create-a-new-plan-guide"></a><span data-ttu-id="0943b-102">Créer un repère de plan</span><span class="sxs-lookup"><span data-stu-id="0943b-102">Create a New Plan Guide</span></span>
  <span data-ttu-id="0943b-103">Vous pouvez créer un repère de plan dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0943b-103">You can create a plan guide in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="0943b-104">Les repères de plan influencent l'optimisation des requêtes en attachant des indicateurs de requête ou un plan fixe de requête à celles-ci.</span><span class="sxs-lookup"><span data-stu-id="0943b-104">Plan guides influence query optimization by attaching query hints or a fixed query plan to them.</span></span> <span data-ttu-id="0943b-105">Dans le repère de plan, vous spécifiez l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] que vous voulez optimiser et une clause OPTION contenant les indicateurs de requête ou un plan de requête spécifique à utiliser pour optimiser la requête.</span><span class="sxs-lookup"><span data-stu-id="0943b-105">In the plan guide, you specify the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that you want optimized and either an OPTION clause that contains the query hints you want to use or a specific query plan you want to use to optimize the query.</span></span> <span data-ttu-id="0943b-106">Lorsque la requête s'exécute, l'optimiseur de requête fait correspondre l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] au repère de plan et attache la clause OPTION à la requête au moment de l'exécution ou fait appel au plan de requête spécifié.</span><span class="sxs-lookup"><span data-stu-id="0943b-106">When the query executes, the query optimizer matches the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to the plan guide and either attaches the OPTION clause to the query at run time or uses the specified query plan.</span></span>  
  
 <span data-ttu-id="0943b-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="0943b-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0943b-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="0943b-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0943b-109">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="0943b-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="0943b-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="0943b-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0943b-111">**Pour créer un repère de plan, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="0943b-111">**To create a plan guide, using:**</span></span>  
  
     [<span data-ttu-id="0943b-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0943b-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0943b-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0943b-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0943b-114">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="0943b-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="0943b-115">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="0943b-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="0943b-116">Les arguments de sp_create_plan_guide doivent être indiqués dans l'ordre affiché.</span><span class="sxs-lookup"><span data-stu-id="0943b-116">The arguments to sp_create_plan_guide must be provided in the order that is shown.</span></span> <span data-ttu-id="0943b-117">Lorsque vous fournissez des valeurs pour les paramètres de `sp_create_plan_guide`, tous les noms de paramètres doivent être spécifiés explicitement, ou aucun nom ne doit être spécifié.</span><span class="sxs-lookup"><span data-stu-id="0943b-117">When you supply values for the parameters of `sp_create_plan_guide`, all parameter names must be specified explicitly, or none at all.</span></span> <span data-ttu-id="0943b-118">Par exemple, si `@name =` est spécifié, `@stmt =`, `@type =` (etc.) doit l'être aussi.</span><span class="sxs-lookup"><span data-stu-id="0943b-118">For example, if `@name =` is specified, then `@stmt =` , `@type =`, and so on, must also be specified.</span></span> <span data-ttu-id="0943b-119">De même, si `@name =` est omis et que seule la valeur du paramètre est indiquée, les noms de paramètres restants doivent également être omis, et seules leurs valeurs doivent être indiquées.</span><span class="sxs-lookup"><span data-stu-id="0943b-119">Likewise, if `@name =` is omitted and only the parameter value is provided, the remaining parameter names must also be omitted, and only their values provided.</span></span> <span data-ttu-id="0943b-120">Les noms d'arguments sont utilisés à des fins descriptives uniquement, pour une meilleure compréhension de la syntaxe.</span><span class="sxs-lookup"><span data-stu-id="0943b-120">Argument names are for descriptive purposes only, to help understand the syntax.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0943b-121">ne vérifie pas que le nom de paramètre spécifié correspond au nom du paramètre à l'emplacement où le nom est utilisé.</span><span class="sxs-lookup"><span data-stu-id="0943b-121">does not verify that the specified parameter name matches the name for the parameter in the position where the name is used.</span></span>  
  
-   <span data-ttu-id="0943b-122">Vous pouvez créer plusieurs repères de plan OBJECT ou SQL pour la même requête et le même lot ou module.</span><span class="sxs-lookup"><span data-stu-id="0943b-122">You can create more than one OBJECT or SQL plan guide for the same query and batch or module.</span></span> <span data-ttu-id="0943b-123">Toutefois, un seul repère de plan peut être activé à un moment donné.</span><span class="sxs-lookup"><span data-stu-id="0943b-123">However, only one plan guide can be enabled at any given time.</span></span>  
  
-   <span data-ttu-id="0943b-124">Vous ne pouvez pas créer de repère de plan de type OBJECT pour une valeur @module_or_batch qui fait référence à une procédure stockée, une fonction ou un déclencheur DML temporaire ou qui spécifie la clause WITH ENCRYPTION.</span><span class="sxs-lookup"><span data-stu-id="0943b-124">Plan guides of type OBJECT cannot be created for an @module_or_batch value that references a stored procedure, function, or DML trigger that specifies the WITH ENCRYPTION clause or that is temporary.</span></span>  
  
-   <span data-ttu-id="0943b-125">Si vous tentez de supprimer ou de modifier une fonction, une procédure stockée ou un déclencheur DML référencé par un repère de plan, qu'il soit activé ou désactivé, une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="0943b-125">Trying to drop or modify a function, stored procedure, or DML trigger that is referenced by a plan guide, either enabled or disabled, causes an error.</span></span> <span data-ttu-id="0943b-126">Une erreur se produit également si vous tentez de supprimer une table dont un des déclencheurs est référencé par un repère de plan.</span><span class="sxs-lookup"><span data-stu-id="0943b-126">Trying to drop a table that has a trigger defined on it that is referenced by a plan guide also causes an error.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0943b-127">Sécurité</span><span class="sxs-lookup"><span data-stu-id="0943b-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0943b-128">Autorisations</span><span class="sxs-lookup"><span data-stu-id="0943b-128">Permissions</span></span>  
 <span data-ttu-id="0943b-129">Pour créer un repère de plan de type OBJECT, il vous faut une autorisation ALTER sur l'objet référencé.</span><span class="sxs-lookup"><span data-stu-id="0943b-129">To create a plan guide of type OBJECT, requires ALTER permission on the referenced object.</span></span> <span data-ttu-id="0943b-130">Pour créer un repère de plan de type SQL ou TEMPLATE, il vous faut une autorisation ALTER pour la base de données active.</span><span class="sxs-lookup"><span data-stu-id="0943b-130">To create a plan guide of type SQL or TEMPLATE, requires ALTER permission on the current database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0943b-131">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0943b-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-plan-guide"></a><span data-ttu-id="0943b-132">Pour créer un repère de plan</span><span class="sxs-lookup"><span data-stu-id="0943b-132">To create a plan guide</span></span>  
  
1.  <span data-ttu-id="0943b-133">Cliquez sur le signe plus (+) pour développer la base de données dans laquelle vous souhaitez créer un repère de plan, puis cliquez sur le signe plus (+) pour développer le dossier **Programmabilité** .</span><span class="sxs-lookup"><span data-stu-id="0943b-133">Click the plus sign to expand the database in which you want to create a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="0943b-134">Cliquez avec le bouton droit sur le dossier **repères de plan** et sélectionnez **nouveau repère de plan.**...</span><span class="sxs-lookup"><span data-stu-id="0943b-134">Right-click the **Plan Guides** folder and select **New Plan Guide...**.</span></span>  
  
3.  <span data-ttu-id="0943b-135">Dans la boîte de dialogue **Nouveau repère de plan** , dans la zone **Nom** , entrez le nom du repère de plan.</span><span class="sxs-lookup"><span data-stu-id="0943b-135">In the **New Plan Guide** dialog box, in the **Name** box, enter the name of the plan guide.</span></span>  
  
4.  <span data-ttu-id="0943b-136">Dans la zone **Instruction** , entrez l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] en fonction de laquelle le repère de plan doit être appliqué.</span><span class="sxs-lookup"><span data-stu-id="0943b-136">In the **Statement** box, enter the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement against which the plan guide is to be applied.</span></span>  
  
5.  <span data-ttu-id="0943b-137">Dans la liste **Type d'étendue** , sélectionnez le type de l'entité dans laquelle l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] apparaît.</span><span class="sxs-lookup"><span data-stu-id="0943b-137">In the **Scope type** list, select the type of entity in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="0943b-138">Ce type spécifie le contexte pour la mise en correspondance de l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] avec le repère de plan.</span><span class="sxs-lookup"><span data-stu-id="0943b-138">This specifies the context for matching the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to the plan guide.</span></span> <span data-ttu-id="0943b-139">Les valeurs possibles sont **OBJECT**, **SQL**et **TEMPLATE**.</span><span class="sxs-lookup"><span data-stu-id="0943b-139">Possible values are **OBJECT**, **SQL**, and **TEMPLATE**.</span></span>  
  
6.  <span data-ttu-id="0943b-140">Dans la zone **Lot de l'étendue** , entrez le texte du lot dans lequel l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] apparaît.</span><span class="sxs-lookup"><span data-stu-id="0943b-140">In the **Scope batch** box, enter the batch text in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="0943b-141">Le texte du lot ne peut pas inclure d’instruction USE\`\`*database* .</span><span class="sxs-lookup"><span data-stu-id="0943b-141">The batch text cannot include a USE\`\`*database* statement.</span></span> <span data-ttu-id="0943b-142">La zone **Lot de l'étendue** est disponible uniquement lorsque **SQL** est sélectionné comme type d'étendue.</span><span class="sxs-lookup"><span data-stu-id="0943b-142">The **Scope batch** box is only available when **SQL** is selected as a scope type.</span></span> <span data-ttu-id="0943b-143">Si aucune valeur n'est entrée dans la zone Lot de l'étendue lorsque SQL est le type de portée, la valeur du texte du lot est la même que celle figurant dans la zone **Instruction** .</span><span class="sxs-lookup"><span data-stu-id="0943b-143">If nothing is entered in the scope batch box when SQL is the scope type, then the value of the batch text is set to the same value as is in the **Statement** box.</span></span>  
  
7.  <span data-ttu-id="0943b-144">Dans la liste **Nom de schéma de l'étendue** , entrez le nom du schéma dans lequel l'objet est contenu.</span><span class="sxs-lookup"><span data-stu-id="0943b-144">In the **Scope schema name** list, enter the name of the schema in which the object is contained.</span></span> <span data-ttu-id="0943b-145">La zone **Nom de schéma de l'étendue** est disponible uniquement lorsque **Objet** est sélectionné comme type d'étendue.</span><span class="sxs-lookup"><span data-stu-id="0943b-145">The **Scope schema name** box is only available when **Object** is selected as a scope type.</span></span>  
  
8.  <span data-ttu-id="0943b-146">Dans la zone **Nom d’objet de l’étendue** , entrez le nom de la procédure stockée [!INCLUDE[tsql](../../includes/tsql-md.md)] , la fonction scalaire définie par l’utilisateur, la fonction table à instructions multiples ou le déclencheur DML dans lequel l’instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] apparaît.</span><span class="sxs-lookup"><span data-stu-id="0943b-146">In the **Scope object name** box, enter the name of the [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, user-defined scalar function, multistatement table-valued function, or DML trigger in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="0943b-147">La zone **Nom d'objet de l'étendue** est disponible uniquement lorsque **Objet** est sélectionné comme type d'étendue.</span><span class="sxs-lookup"><span data-stu-id="0943b-147">The **Scope object name** box is only available when **Object** is selected as a scope type.</span></span>  
  
9. <span data-ttu-id="0943b-148">Dans la zone **Paramètres** , entrez le nom de paramètre et le type de données de tous les paramètres incorporés dans l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0943b-148">In the **Parameters** box, enter the parameter name and data type of all parameters that are embedded in the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
     <span data-ttu-id="0943b-149">Les paramètres s'appliquent uniquement lorsque l'une des conditions suivantes est remplie :</span><span class="sxs-lookup"><span data-stu-id="0943b-149">Parameters apply only when either of the following is true:</span></span>  
  
    -   <span data-ttu-id="0943b-150">Le type de portée est **SQL** ou **TEMPLATE**.</span><span class="sxs-lookup"><span data-stu-id="0943b-150">The scope type is **SQL** or **TEMPLATE**.</span></span> <span data-ttu-id="0943b-151">Si le type est **TEMPLATE**, les paramètres ne doivent pas avoir la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="0943b-151">If **TEMPLATE**, parameters must not be NULL.</span></span>  
  
    -   <span data-ttu-id="0943b-152">L'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] est soumise à l'aide de sp_executesql et une valeur est spécifiée pour le paramètre ou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] soumet une instruction en interne après l'avoir paramétrée.</span><span class="sxs-lookup"><span data-stu-id="0943b-152">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is submitted by using sp_executesql and a value for the parameter is specified, or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] internally submits a statement after parameterizing it.</span></span>  
  
10. <span data-ttu-id="0943b-153">Dans la zone **Indicateurs** , entrez les indicateurs de requête ou le plan de requête à appliquer à l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0943b-153">In the **Hints** box, enter the query hints or query plan to be applied to the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="0943b-154">Pour spécifier un ou plusieurs indicateurs de requête, entrez une clause OPTION valide.</span><span class="sxs-lookup"><span data-stu-id="0943b-154">To specify one or more query hints, enter a valid OPTION clause.</span></span>  
  
11. <span data-ttu-id="0943b-155">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0943b-155">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0943b-156">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0943b-156">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-plan-guide"></a><span data-ttu-id="0943b-157">Pour créer un repère de plan</span><span class="sxs-lookup"><span data-stu-id="0943b-157">To create a plan guide</span></span>  
  
1.  <span data-ttu-id="0943b-158">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0943b-158">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0943b-159">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="0943b-159">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0943b-160">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="0943b-160">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates a plan guide named Guide1 based on a SQL statement  
    EXEC sp_create_plan_guide   
        @name = N'Guide1',   
        @stmt = N'SELECT TOP 1 *   
                  FROM Sales.SalesOrderHeader   
                  ORDER BY OrderDate DESC',   
        @type = N'SQL',  
        @module_or_batch = NULL,   
        @params = NULL,   
        @hints = N'OPTION (MAXDOP 1)';  
  
    ```  
  
 <span data-ttu-id="0943b-161">Pour plus d’informations, consultez [sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0943b-161">For more information, see [sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql).</span></span>  
  
  
