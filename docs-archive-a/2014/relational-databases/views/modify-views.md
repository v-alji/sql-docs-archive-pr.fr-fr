---
title: Modifier des vues | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], renaming
- views [SQL Server], modifying
- modifying views
- renaming views
ms.assetid: 2d3c14dc-43e5-4324-b8fb-f2692d330b16
author: stevestein
ms.author: sstein
ms.openlocfilehash: 10cf9ecc860d8f9b46a06ac679b0f1a8241000bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605308"
---
# <a name="modify-views"></a><span data-ttu-id="2cfd0-102">Modifier des vues</span><span class="sxs-lookup"><span data-stu-id="2cfd0-102">Modify Views</span></span>
  <span data-ttu-id="2cfd0-103">Après avoir défini une vue, vous pouvez modifier sa définition dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] sans la supprimer ni être obligé de la recréer à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2cfd0-103">After you define a view, you can modify its definition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] without dropping and re-creating the view by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2cfd0-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="2cfd0-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2cfd0-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="2cfd0-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2cfd0-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="2cfd0-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="2cfd0-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2cfd0-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2cfd0-108">**Pour modifier une vue, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="2cfd0-108">**To modify a view, using:**</span></span>  
  
     [<span data-ttu-id="2cfd0-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2cfd0-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2cfd0-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2cfd0-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2cfd0-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="2cfd0-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="2cfd0-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="2cfd0-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="2cfd0-113">Modifier une vue n'affecte aucun des objets qui en dépendent, tels que les procédures stockées ou les déclencheurs, à moins que la définition de la vue ne change de telle manière qu'un objet sous-jacent ne soit plus valide.</span><span class="sxs-lookup"><span data-stu-id="2cfd0-113">Modifying a view does not affect any dependent objects, such as stored procedures or triggers, unless the definition of the view changes in such a way that the dependent object is no longer valid.</span></span>  
  
-   <span data-ttu-id="2cfd0-114">Si la vue actuellement utilisée est modifiée en utilisant ALTER VIEW, le [!INCLUDE[ssDE](../../includes/ssde-md.md)] pose un verrou de schéma exclusif sur la vue.</span><span class="sxs-lookup"><span data-stu-id="2cfd0-114">If a view currently used is modified by using ALTER VIEW, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] takes an exclusive schema lock on the view.</span></span> <span data-ttu-id="2cfd0-115">Lorsque le verrou est attribué (et qu'il n'y a aucun utilisateur actif de la vue), le [!INCLUDE[ssDE](../../includes/ssde-md.md)] supprime toutes les copies de la vue du cache de procédure.</span><span class="sxs-lookup"><span data-stu-id="2cfd0-115">When the lock is granted, and there are no active users of the view, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] deletes all copies of the view from the procedure cache.</span></span> <span data-ttu-id="2cfd0-116">Les plans existants qui font référence à la vue restent dans le cache, mais ils sont recompilés lorsqu'ils sont invoqués.</span><span class="sxs-lookup"><span data-stu-id="2cfd0-116">Existing plans referencing the view remain in the cache but are recompiled when invoked.</span></span>  
  
-   <span data-ttu-id="2cfd0-117">L"instruction ALTER VIEW peut être appliquée à des vues indexées, mais elle supprime de manière inconditionnelle tous les index de la vue.</span><span class="sxs-lookup"><span data-stu-id="2cfd0-117">ALTER VIEW can be applied to indexed views; however, ALTER VIEW unconditionally drops all indexes on the view.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2cfd0-118">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2cfd0-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2cfd0-119">Autorisations</span><span class="sxs-lookup"><span data-stu-id="2cfd0-119">Permissions</span></span>  
 <span data-ttu-id="2cfd0-120">Pour exécuter l'instruction ALTER VIEW, il est nécessaire de disposer au minimum de l'autorisation ALTER sur OBJECT.</span><span class="sxs-lookup"><span data-stu-id="2cfd0-120">To execute ALTER VIEW, at a minimum, ALTER permission on OBJECT is required.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2cfd0-121">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2cfd0-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-view"></a><span data-ttu-id="2cfd0-122">Pour modifier une vue</span><span class="sxs-lookup"><span data-stu-id="2cfd0-122">To modify a view</span></span>  
  
1.  <span data-ttu-id="2cfd0-123">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) en regard de la base de données dans laquelle votre vue se trouve, puis cliquez sur le signe plus (+) en regard du dossier **Vues** .</span><span class="sxs-lookup"><span data-stu-id="2cfd0-123">In **Object Explorer**, click the plus sign next to the database where your view is located and then click the plus sign next to the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="2cfd0-124">Cliquez avec le bouton droit sur la vue à modifier, puis sélectionnez **Conception**.</span><span class="sxs-lookup"><span data-stu-id="2cfd0-124">Right-click on the view you wish to modify and select **Design**.</span></span>  
  
3.  <span data-ttu-id="2cfd0-125">Dans le volet Diagramme du Concepteur de requêtes, apportez les modifications à la vue à l'aide d'une ou de plusieurs des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="2cfd0-125">In the diagram pane of the query designer, make changes to the view in one or more of the following ways:</span></span>  
  
    1.  <span data-ttu-id="2cfd0-126">Activez ou désactivez les cases à cocher des éléments à ajouter ou supprimer.</span><span class="sxs-lookup"><span data-stu-id="2cfd0-126">Select or clear the check boxes of any elements you wish to add or remove.</span></span>  
  
    2.  <span data-ttu-id="2cfd0-127">Cliquez avec le bouton droit dans le volet Diagramme, sélectionnez **Ajouter une table...** , puis les colonnes supplémentaires à ajouter à la vue dans la boîte de dialogue **Ajouter une table**.</span><span class="sxs-lookup"><span data-stu-id="2cfd0-127">Right-click within the diagram pane, select **Add Table...**, and then select the additional columns you want to add to the view from the **Add Table** dialog box.</span></span>  
  
    3.  <span data-ttu-id="2cfd0-128">Cliquez avec le bouton droit sur la barre de titre de la table que vous souhaitez supprimer et sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="2cfd0-128">Right-click the title bar of the table you wish to remove and select **Remove**.</span></span>  
  
4.  <span data-ttu-id="2cfd0-129">Dans le menu **Fichier** , cliquez sur **Enregistrer**_nom_vue_.</span><span class="sxs-lookup"><span data-stu-id="2cfd0-129">On the **File** menu, click **Save**_view name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2cfd0-130">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2cfd0-130">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-view"></a><span data-ttu-id="2cfd0-131">Pour modifier une vue</span><span class="sxs-lookup"><span data-stu-id="2cfd0-131">To modify a view</span></span>  
  
1.  <span data-ttu-id="2cfd0-132">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2cfd0-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2cfd0-133">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="2cfd0-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2cfd0-134">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="2cfd0-134">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="2cfd0-135">L'exemple commence par créer une vue, puis la modifie à l'aide de ALTER VIEW.</span><span class="sxs-lookup"><span data-stu-id="2cfd0-135">The example first creates a view and then modifies the view by using ALTER VIEW.</span></span> <span data-ttu-id="2cfd0-136">Une clause WHERE est ajoutée à la définition de la vue.</span><span class="sxs-lookup"><span data-stu-id="2cfd0-136">A WHERE clause is added to the view definition.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    -- Create a view.  
    CREATE VIEW HumanResources.EmployeeHireDate  
    AS  
    SELECT p.FirstName, p.LastName, e.HireDate  
    FROM HumanResources.Employee AS e JOIN Person.Person AS  p  
    ON e.BusinessEntityID = p.BusinessEntityID ;   
  
    -- Modify the view by adding a WHERE clause to limit the rows returned.  
    ALTER VIEW HumanResources.EmployeeHireDate  
    AS  
    SELECT p.FirstName, p.LastName, e.HireDate  
    FROM HumanResources.Employee AS e JOIN Person.Person AS  p  
    ON e.BusinessEntityID = p.BusinessEntityID  
    WHERE HireDate < CONVERT(DATETIME,'20020101',101) ;   
    GO  
    ```  
  
 <span data-ttu-id="2cfd0-137">Pour plus d’informations, consultez [ALTER VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2cfd0-137">For more information, see [ALTER VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-view-transact-sql).</span></span>  
  
  
