---
title: Afficher les propriétés du repère de plan | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.planguideprop.general.f1
helpviewer_keywords:
- plan guides [SQL Server], view plan guide properties
- viewing plan guide properties
ms.assetid: 8c0d2f39-59c1-4168-a649-65473f6a771b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: af29c66690a43f89106c1f77aca8c3a02eff2ba9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699515"
---
# <a name="view-plan-guide-properties"></a><span data-ttu-id="64413-102">Afficher les propriétés du repère de plan</span><span class="sxs-lookup"><span data-stu-id="64413-102">View Plan Guide Properties</span></span>
  <span data-ttu-id="64413-103">Vous pouvez afficher les propriétés des repères de plan dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64413-103">You can view the properties of plan guides in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="64413-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="64413-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="64413-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="64413-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="64413-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="64413-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="64413-107">**Pour afficher les propriétés des repères de plan, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="64413-107">**To view the properties of plan guides, using:**</span></span>  
  
     [<span data-ttu-id="64413-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="64413-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="64413-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="64413-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="64413-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="64413-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="64413-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="64413-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="64413-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="64413-112">Permissions</span></span>  
 <span data-ttu-id="64413-113">La visibilité des métadonnées dans les affichages catalogue est limitée aux éléments sécurisables qu'un utilisateur détient ou pour lesquels des autorisations lui ont été accordées.</span><span class="sxs-lookup"><span data-stu-id="64413-113">The visibility of the metadata in catalog views is limited to securables that either a user owns or on which the user has been granted some permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="64413-114">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="64413-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-of-a-plan-guide"></a><span data-ttu-id="64413-115">Pour afficher les propriétés d'un repère de plan</span><span class="sxs-lookup"><span data-stu-id="64413-115">To view the properties of a plan guide</span></span>  
  
1.  <span data-ttu-id="64413-116">Cliquez sur le signe plus (+) pour développer la base de données dans laquelle vous souhaitez afficher les propriétés d'un repère de plan, puis cliquez sur le signe plus (+) pour développer le dossier **Programmabilité** .</span><span class="sxs-lookup"><span data-stu-id="64413-116">Click the plus sign to expand the database in which you want to view the properties of a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="64413-117">Cliquez sur le signe plus (+) pour développer le dossier **Repères de plan** .</span><span class="sxs-lookup"><span data-stu-id="64413-117">Click the plus sign to expand the **Plan Guides** folder.</span></span>  
  
3.  <span data-ttu-id="64413-118">Cliquez avec le bouton droit sur le repère de plan dont vous voulez afficher les propriétés, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="64413-118">Right-click the plan guide of which you want to view the properties and select **Properties**.</span></span>  
  
     <span data-ttu-id="64413-119">Les propriétés suivantes s'affichent dans la boîte de dialogue **Propriétés du repère de plan** .</span><span class="sxs-lookup"><span data-stu-id="64413-119">The following properties show in the **Plan Guide Properties** dialog box.</span></span>  
  
     <span data-ttu-id="64413-120">**Indicateurs**</span><span class="sxs-lookup"><span data-stu-id="64413-120">**Hints**</span></span>  
     <span data-ttu-id="64413-121">Affiche les indicateurs de requête ou le plan de requête à appliquer à l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64413-121">Displays the query hints or query plan to be applied to the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="64413-122">Lorsqu'un plan de requête est spécifié en tant qu'indicateur, la sortie du plan d'exécution XML s'affiche.</span><span class="sxs-lookup"><span data-stu-id="64413-122">When a query plan is specified as a hint, the XML Showplan output for the plan is displayed.</span></span>  
  
     <span data-ttu-id="64413-123">**Est désactivé**</span><span class="sxs-lookup"><span data-stu-id="64413-123">**Is disabled**</span></span>  
     <span data-ttu-id="64413-124">Affiche l'état du repère de plan.</span><span class="sxs-lookup"><span data-stu-id="64413-124">Displays the status of the plan guide.</span></span> <span data-ttu-id="64413-125">Les valeurs possibles sont **True** et **False**.</span><span class="sxs-lookup"><span data-stu-id="64413-125">Possible values are **True** and **False**.</span></span>  
  
     <span data-ttu-id="64413-126">**Nom**</span><span class="sxs-lookup"><span data-stu-id="64413-126">**Name**</span></span>  
     <span data-ttu-id="64413-127">Affiche le nom du repère de plan.</span><span class="sxs-lookup"><span data-stu-id="64413-127">Displays the name of the plan guide.</span></span>  
  
     <span data-ttu-id="64413-128">**Paramètres**</span><span class="sxs-lookup"><span data-stu-id="64413-128">**Parameters**</span></span>  
     <span data-ttu-id="64413-129">Lorsque le type de portée est SQL ou TEMPLATE, affiche le nom et le type de données de tous les paramètres incorporés dans l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64413-129">When the scope type is SQL or TEMPLATE, displays the name and data type of all parameters that are embedded in the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
     <span data-ttu-id="64413-130">**Lot de la portée**</span><span class="sxs-lookup"><span data-stu-id="64413-130">**Scope batch**</span></span>  
     <span data-ttu-id="64413-131">Affiche le texte du lot dans lequel l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] apparaît.</span><span class="sxs-lookup"><span data-stu-id="64413-131">Displays the batch text in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span>  
  
     <span data-ttu-id="64413-132">**Nom d'objet de la portée**</span><span class="sxs-lookup"><span data-stu-id="64413-132">**Scope object name**</span></span>  
     <span data-ttu-id="64413-133">Lorsque le type de portée est OBJECT, affiche le nom de la procédure stockée [!INCLUDE[tsql](../../includes/tsql-md.md)] , la fonction scalaire définie par l'utilisateur, la fonction table à instructions multiples ou le déclencheur DML dans lequel l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] apparaît.</span><span class="sxs-lookup"><span data-stu-id="64413-133">When the scope type is OBJECT, displays the name of the [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, user-defined scalar function, multistatement table-valued function, or DML trigger in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span>  
  
     <span data-ttu-id="64413-134">**Nom de schéma de la portée**</span><span class="sxs-lookup"><span data-stu-id="64413-134">**Scope schema name**</span></span>  
     <span data-ttu-id="64413-135">Lorsque le type de portée est OBJECT, affiche le nom du schéma dans lequel l'objet est contenu.</span><span class="sxs-lookup"><span data-stu-id="64413-135">When the scope type is OBJECT, displays the name of the schema in which the object is contained.</span></span>  
  
     <span data-ttu-id="64413-136">**Type d'étendue**</span><span class="sxs-lookup"><span data-stu-id="64413-136">**Scope type**</span></span>  
     <span data-ttu-id="64413-137">Affiche le type de l'entité dans laquelle l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] apparaît.</span><span class="sxs-lookup"><span data-stu-id="64413-137">Displays the type of entity in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="64413-138">Ce type spécifie le contexte pour la mise en correspondance de l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] avec le repère de plan.</span><span class="sxs-lookup"><span data-stu-id="64413-138">This specifies the context for matching the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to the plan guide.</span></span> <span data-ttu-id="64413-139">Les valeurs possibles sont **OBJECT**, **SQL**et **TEMPLATE**.</span><span class="sxs-lookup"><span data-stu-id="64413-139">Possible values are **OBJECT**, **SQL**, and **TEMPLATE**.</span></span>  
  
     <span data-ttu-id="64413-140">**Instruction**</span><span class="sxs-lookup"><span data-stu-id="64413-140">**Statement**</span></span>  
     <span data-ttu-id="64413-141">Affiche l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] par rapport à laquelle le repère de plan est appliqué.</span><span class="sxs-lookup"><span data-stu-id="64413-141">Displays the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement against which the plan guide is applied.</span></span>  
  
4.  <span data-ttu-id="64413-142">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="64413-142">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="64413-143">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="64413-143">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-properties-of-a-plan-guide"></a><span data-ttu-id="64413-144">Pour afficher les propriétés d'un repère de plan</span><span class="sxs-lookup"><span data-stu-id="64413-144">To view the properties of a plan guide</span></span>  
  
1.  <span data-ttu-id="64413-145">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64413-145">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="64413-146">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="64413-146">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="64413-147">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="64413-147">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- If a plan guide named "Guide1" already exists in the AdventureWorks2012 database, delete it.  
    USE AdventureWorks2012;  
    GO  
    IF OBJECT_ID(N'Guide1') IS NOT NULL  
       EXEC sp_control_plan_guide N'DROP', N'Guide1';  
    GO  
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
    GO  
    -- Gets the name, created date, and all other relevant property information on the plan guide created above.   
    SELECT name AS plan_guide_name,  
       create_date,  
       query_text,  
       scope_type_desc,  
       OBJECT_NAME(scope_object_id) AS scope_object_name,  
       scope_batch,  
       parameters,  
       hints,  
       is_disabled  
    FROM sys.plan_guides  
    WHERE name = N'Guide1';  
    GO  
    ```  
  
 <span data-ttu-id="64413-148">Pour plus d’informations, consultez [sys.plan_guides &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-plan-guides-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="64413-148">For more information, see [sys.plan_guides &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-plan-guides-transact-sql).</span></span>  
  
  
