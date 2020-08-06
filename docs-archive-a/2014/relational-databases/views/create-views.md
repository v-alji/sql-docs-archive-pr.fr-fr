---
title: Créer des vues | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], creating
ms.assetid: 0b7bd2a1-544c-42ba-8e7b-4822f34d7b64
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8280f6d65d7252cad423abef849207111492c044
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600716"
---
# <a name="create-views"></a><span data-ttu-id="51342-102">Créer des vues</span><span class="sxs-lookup"><span data-stu-id="51342-102">Create Views</span></span>
  <span data-ttu-id="51342-103">Vous pouvez créer des vues dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="51342-103">You can create views in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="51342-104">Une vue peut être utilisée aux fins suivantes :</span><span class="sxs-lookup"><span data-stu-id="51342-104">A view can be used for the following purposes:</span></span>  
  
-   <span data-ttu-id="51342-105">pour affiner, simplifier et personnaliser la perception de la base de données par chaque utilisateur ;</span><span class="sxs-lookup"><span data-stu-id="51342-105">To focus, simplify, and customize the perception each user has of the database.</span></span>  
  
-   <span data-ttu-id="51342-106">comme mécanisme de sécurité en permettant aux utilisateurs d'accéder aux données par le biais de la vue, sans leur accorder d'autorisations qui leur permettraient d'accéder directement aux tables de base sous-jacentes de la vue ;</span><span class="sxs-lookup"><span data-stu-id="51342-106">As a security mechanism by allowing users to access data through the view, without granting the users permissions to directly access the underlying base tables.</span></span>  
  
-   <span data-ttu-id="51342-107">pour fournir une interface à compatibilité descendante pour émuler une table dont le schéma a été modifié.</span><span class="sxs-lookup"><span data-stu-id="51342-107">To provide a backward compatible interface to emulate a table whose schema has changed.</span></span>  
  
 <span data-ttu-id="51342-108">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="51342-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="51342-109">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="51342-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="51342-110">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="51342-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="51342-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="51342-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="51342-112">**Pour créer une vue, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="51342-112">**To create a view, using:**</span></span>  
  
     [<span data-ttu-id="51342-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="51342-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="51342-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="51342-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="51342-115">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="51342-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="51342-116">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="51342-116">Limitations and Restrictions</span></span>  
 <span data-ttu-id="51342-117">Vous ne pouvez créer des vues que dans la base de données actuelle.</span><span class="sxs-lookup"><span data-stu-id="51342-117">A view can be created only in the current database.</span></span>  
  
 <span data-ttu-id="51342-118">Une vue ne peut faire référence qu'à un maximum de 1 024 colonnes.</span><span class="sxs-lookup"><span data-stu-id="51342-118">A view can have a maximum of 1,024 columns.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="51342-119">Sécurité</span><span class="sxs-lookup"><span data-stu-id="51342-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="51342-120">Autorisations</span><span class="sxs-lookup"><span data-stu-id="51342-120">Permissions</span></span>  
 <span data-ttu-id="51342-121">Nécessite l'autorisation CREATE VIEW dans la base de données et l'autorisation ALTER sur le schéma dans lequel la vue est créée.</span><span class="sxs-lookup"><span data-stu-id="51342-121">Requires CREATE VIEW permission in the database and ALTER permission on the schema in which the view is being created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="51342-122">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="51342-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-view-by-using-the-query-and-view-designer"></a><span data-ttu-id="51342-123">Pour créer une vue à l'aide du Concepteur de requêtes et de vues</span><span class="sxs-lookup"><span data-stu-id="51342-123">To create a view by using the Query and View Designer</span></span>  
  
1.  <span data-ttu-id="51342-124">Dans l' **Explorateur d'objets**, développez la base de données dans laquelle vous souhaitez créer votre nouvelle vue.</span><span class="sxs-lookup"><span data-stu-id="51342-124">In **Object Explorer**, expand the database where you want to create your new view.</span></span>  
  
2.  <span data-ttu-id="51342-125">Cliquez avec le bouton droit sur le dossier **Vues**, puis cliquez sur **Nouvelle vue...** .</span><span class="sxs-lookup"><span data-stu-id="51342-125">Right-click the **Views** folder, then click **New View...**.</span></span>  
  
3.  <span data-ttu-id="51342-126">Dans la boîte de dialogue **Ajouter une table** , sélectionnez le ou les éléments que vous souhaitez inclure dans votre nouvelle vue dans l'un des onglets suivants : Tables, Vues, Fonctions et Synonymes.</span><span class="sxs-lookup"><span data-stu-id="51342-126">In the **Add Table** dialog box, select the element or elements that you want to include in your new view from one of the following tabs: Tables, Views, Functions, and Synonyms.</span></span>  
  
4.  <span data-ttu-id="51342-127">Cliquez sur **Ajouter**, puis sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="51342-127">Click **Add**, then click **Close**.</span></span>  
  
5.  <span data-ttu-id="51342-128">Dans le **volet Schéma**, sélectionnez les colonnes ou d'autres éléments à inclure dans la nouvelle vue.</span><span class="sxs-lookup"><span data-stu-id="51342-128">In the **Diagram Pane**, select the columns or other elements to include in the new view.</span></span>  
  
6.  <span data-ttu-id="51342-129">Dans le **volet Critères**, sélectionnez les critères de tri ou de filtre supplémentaires pour les colonnes.</span><span class="sxs-lookup"><span data-stu-id="51342-129">In the **Criteria Pane**, select additional sort or filter criteria for the columns.</span></span>  
  
7.  <span data-ttu-id="51342-130">Dans le menu **Fichier** , cliquez sur **Enregistrer**_nom_vue_.</span><span class="sxs-lookup"><span data-stu-id="51342-130">On the **File** menu, click **Save**_view name_.</span></span>  
  
8.  <span data-ttu-id="51342-131">Dans la boîte de dialogue **Choisir un nom** , entrez un nom pour la nouvelle vue et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="51342-131">In the **Choose Name** dialog box, enter a name for the new view and click **OK**.</span></span>  
  
     <span data-ttu-id="51342-132">Pour plus d’informations sur le Concepteur de requêtes et de vues, consultez [Outils du concepteur de requêtes et de vues &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="51342-132">For more information about the query and view designer, see [Query and View Designer Tools &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="51342-133">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="51342-133">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-view"></a><span data-ttu-id="51342-134">Pour créer une vue</span><span class="sxs-lookup"><span data-stu-id="51342-134">To create a view</span></span>  
  
1.  <span data-ttu-id="51342-135">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="51342-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="51342-136">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="51342-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="51342-137">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="51342-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;   
    GO  
    CREATE VIEW HumanResources.EmployeeHireDate  
    AS  
    SELECT p.FirstName, p.LastName, e.HireDate  
    FROM HumanResources.Employee AS e JOIN Person.Person AS  p  
    ON e.BusinessEntityID = p.BusinessEntityID ;   
    GO  
    -- Query the view  
    SELECT FirstName, LastName, HireDate  
    FROM HumanResources.EmployeeHireDate  
    ORDER BY LastName;  
  
    ```  
  
 <span data-ttu-id="51342-138">Pour plus d’informations, consultez [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="51342-138">For more information, see [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span></span>  
  
  
