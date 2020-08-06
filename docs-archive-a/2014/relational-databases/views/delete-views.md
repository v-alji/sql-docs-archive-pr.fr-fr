---
title: Supprimer des vues | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- dropping views
- deleting views
- views [SQL Server], deleting
- removing views
ms.assetid: 6823c7f8-06ca-4bda-8482-7092f03d52a0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3e05724f7d6384d0407e915207ad60a1cdfb01b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600715"
---
# <a name="delete-views"></a><span data-ttu-id="ce01e-102">Supprimer des vues</span><span class="sxs-lookup"><span data-stu-id="ce01e-102">Delete Views</span></span>
  <span data-ttu-id="ce01e-103">Vous pouvez supprimer (ignorer) des vues dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce01e-103">You can delete (drop) views in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ce01e-104">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="ce01e-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ce01e-105">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="ce01e-105">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="ce01e-106">Lorsque vous supprimez une vue, sa définition et d'autres informations la concernant sont supprimées du catalogue système.</span><span class="sxs-lookup"><span data-stu-id="ce01e-106">When you drop a view, the definition of the view and other information about the view is deleted from the system catalog.</span></span> <span data-ttu-id="ce01e-107">Toutes les autorisations pour la vue sont également supprimées.</span><span class="sxs-lookup"><span data-stu-id="ce01e-107">All permissions for the view are also deleted.</span></span>  
  
-   <span data-ttu-id="ce01e-108">Toute vue d'une table qui est supprimée au moyen de `DROP TABLE` doit être supprimée de manière explicite à l'aide de `DROP VIEW`.</span><span class="sxs-lookup"><span data-stu-id="ce01e-108">Any view on a table that is dropped by using `DROP TABLE` must be dropped explicitly by using `DROP VIEW`.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ce01e-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ce01e-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ce01e-110">Autorisations</span><span class="sxs-lookup"><span data-stu-id="ce01e-110">Permissions</span></span>  
 <span data-ttu-id="ce01e-111">Nécessite soit une autorisation ALTER sur SCHEMA, soit une autorisation CONTROL sur OBJECT.</span><span class="sxs-lookup"><span data-stu-id="ce01e-111">Requires ALTER permission on SCHEMA or CONTROL permission on OBJECT.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ce01e-112">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ce01e-112">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-view-from-a-database"></a><span data-ttu-id="ce01e-113">Pour supprimer une vue d'une base de données</span><span class="sxs-lookup"><span data-stu-id="ce01e-113">To delete a view from a database</span></span>  
  
1.  <span data-ttu-id="ce01e-114">Dans l' **Explorateur d'objets**, développez la base de données qui contient la vue que vous souhaitez supprimer, puis le dossier **Vues** .</span><span class="sxs-lookup"><span data-stu-id="ce01e-114">In **Object Explorer**, expand the database that contains the view you want to delete, and then expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="ce01e-115">Cliquez avec le bouton droit sur la vue à supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="ce01e-115">Right-click the view you want to delete and click **Delete**.</span></span>  
  
3.  <span data-ttu-id="ce01e-116">Dans la boîte de dialogue **Supprimer l'objet** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce01e-116">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="ce01e-117">Cliquez sur **Afficher les dépendances** dans la boîte de dialogue **Supprimer un objet** pour ouvrir la boîte de dialogue _Dépendances de_**nom_vue**.</span><span class="sxs-lookup"><span data-stu-id="ce01e-117">Click **Show Dependencies** in the **Delete Object** dialog box to open the _view_name_**Dependencies** dialog box.</span></span> <span data-ttu-id="ce01e-118">Cette opération affiche tous les objets qui dépendent de la vue et tous les objets dont la vue dépend.</span><span class="sxs-lookup"><span data-stu-id="ce01e-118">This will show all of the objects that depend on the view and all of the objects on which the view depends.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ce01e-119">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ce01e-119">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-view-from-a-database"></a><span data-ttu-id="ce01e-120">Pour supprimer une vue d'une base de données</span><span class="sxs-lookup"><span data-stu-id="ce01e-120">To delete a view from a database</span></span>  
  
1.  <span data-ttu-id="ce01e-121">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce01e-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ce01e-122">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="ce01e-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ce01e-123">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="ce01e-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="ce01e-124">L'exemple supprime la vue spécifiée uniquement si cette vue existe déjà.</span><span class="sxs-lookup"><span data-stu-id="ce01e-124">The example deletes the specified view only if the view already exists.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    IF OBJECT_ID ('HumanResources.EmployeeHireDate', 'V') IS NOT NULL  
    DROP VIEW HumanResources.EmployeeHireDate;  
    GO  
    ```  
  
 <span data-ttu-id="ce01e-125">Pour plus d’informations, consultez [DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ce01e-125">For more information, see [DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql).</span></span>  
  
  
