---
title: Renommer des vues | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], renaming
- renaming views
ms.assetid: 5eed0488-81d2-40e8-8fdf-b0a640a591d0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5cc76ced033a69788270c3fa9277bcca6972e080
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696680"
---
# <a name="rename-views"></a><span data-ttu-id="0a2ab-102">Renommer des vues</span><span class="sxs-lookup"><span data-stu-id="0a2ab-102">Rename Views</span></span>
  <span data-ttu-id="0a2ab-103">Vous pouvez renommer une vue dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a2ab-103">You can rename a view in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="0a2ab-104">Si vous renommez une vue, l'exécution du code et des applications qui en dépendent peut échouer.</span><span class="sxs-lookup"><span data-stu-id="0a2ab-104">If you rename a view, code and applications that depend on the view may fail.</span></span> <span data-ttu-id="0a2ab-105">Il peut s'agir d'autres vues, de requêtes, de procédures stockées, de fonctions définies par l'utilisateur et d'applications clientes.</span><span class="sxs-lookup"><span data-stu-id="0a2ab-105">These include other views, queries, stored procedures, user-defined functions, and client applications.</span></span> <span data-ttu-id="0a2ab-106">Notez que ces défaillances se produisent en cascade.</span><span class="sxs-lookup"><span data-stu-id="0a2ab-106">Note that these failures will cascade.</span></span>  
  
 <span data-ttu-id="0a2ab-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="0a2ab-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0a2ab-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="0a2ab-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0a2ab-109">Composants requis</span><span class="sxs-lookup"><span data-stu-id="0a2ab-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="0a2ab-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="0a2ab-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0a2ab-111">**Pour renommer une vue, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="0a2ab-111">**To rename a view, using:**</span></span>  
  
     [<span data-ttu-id="0a2ab-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0a2ab-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0a2ab-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0a2ab-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="0a2ab-114">**Suivi :**  [Après avoir renommé une vue](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="0a2ab-114">**Follow Up:**  [After renaming a view](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0a2ab-115">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="0a2ab-115">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="0a2ab-116">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="0a2ab-116">Prerequisites</span></span>  
 <span data-ttu-id="0a2ab-117">Obtenez une liste de toutes les dépendances sur la vue.</span><span class="sxs-lookup"><span data-stu-id="0a2ab-117">Obtain a list of all dependencies on the view.</span></span> <span data-ttu-id="0a2ab-118">Tous les objets, scripts ou applications qui font référence à la vue doivent être modifiés pour refléter le nouveau nom de la vue.</span><span class="sxs-lookup"><span data-stu-id="0a2ab-118">Any objects, scripts or applications that reference the view must be modified to reflect the new name of the view.</span></span> <span data-ttu-id="0a2ab-119">Pour plus d'informations, consultez [Get Information About a View](get-information-about-a-view.md).</span><span class="sxs-lookup"><span data-stu-id="0a2ab-119">For more information, see [Get Information About a View](get-information-about-a-view.md).</span></span> <span data-ttu-id="0a2ab-120">Nous vous recommandons de supprimer la vue et de la recréer sous un nouveau nom plutôt que de la renommer.</span><span class="sxs-lookup"><span data-stu-id="0a2ab-120">We recommend that you drop the view and recreate it with a new name instead of renaming the view.</span></span> <span data-ttu-id="0a2ab-121">En recréant la vue, vous mettez à jour les informations de dépendance pour les objets référencés dans la vue.</span><span class="sxs-lookup"><span data-stu-id="0a2ab-121">By recreating the view, you update the dependency information for the objects that are referenced in the view.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0a2ab-122">Sécurité</span><span class="sxs-lookup"><span data-stu-id="0a2ab-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0a2ab-123">Autorisations</span><span class="sxs-lookup"><span data-stu-id="0a2ab-123">Permissions</span></span>  
 <span data-ttu-id="0a2ab-124">Requiert l'autorisation ALTER sur SCHEMA, l'autorisation CONTROL sur OBJECT et l'autorisation CREATE VIEW sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="0a2ab-124">Requires ALTER permission on SCHEMA or CONTROL permission on OBJECT is required, and CREATE VIEW permission in the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0a2ab-125">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0a2ab-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-view"></a><span data-ttu-id="0a2ab-126">Pour renommer une vue</span><span class="sxs-lookup"><span data-stu-id="0a2ab-126">To rename a view</span></span>  
  
1.  <span data-ttu-id="0a2ab-127">Dans l' **Explorateur d'objets**, développez la base de données qui contient la vue que vous souhaitez renommer et le dossier **Vue** .</span><span class="sxs-lookup"><span data-stu-id="0a2ab-127">In **Object Explorer**, expand the database that contains the view you wish to rename and then expand the **View** folder.</span></span>  
  
2.  <span data-ttu-id="0a2ab-128">Cliquez avec le bouton droit sur la vue que vous souhaitez renommer et sélectionnez **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="0a2ab-128">Right-click the view you wish to rename and select **Rename**.</span></span>  
  
3.  <span data-ttu-id="0a2ab-129">Entrez le nouveau nom de la vue.</span><span class="sxs-lookup"><span data-stu-id="0a2ab-129">Enter the view's new name.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0a2ab-130">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0a2ab-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="0a2ab-131">**Pour renommer une vue**</span><span class="sxs-lookup"><span data-stu-id="0a2ab-131">**To rename a view**</span></span>  
  
 <span data-ttu-id="0a2ab-132">Même si vous pouvez utiliser **sp_rename** pour modifier le nom de la vue, nous vous recommandons de supprimer la vue existante puis de la recréer sous le nouveau nom.</span><span class="sxs-lookup"><span data-stu-id="0a2ab-132">While you can use **sp_rename** to change the name of the view, we recommend that you delete the existing view and then re-create it with the new name.</span></span>  
  
 <span data-ttu-id="0a2ab-133">Pour plus d’informations, consultez [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) et [DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0a2ab-133">For more information, see [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) and [DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql).</span></span>  
  
##  <a name="follow-up-after-renaming-a-view"></a><a name="FollowUp"></a> <span data-ttu-id="0a2ab-134">Suivi : Après avoir renommé une vue</span><span class="sxs-lookup"><span data-stu-id="0a2ab-134">Follow Up: After Renaming a View</span></span>  
 <span data-ttu-id="0a2ab-135">Vérifiez que tous les objets, scripts et applications qui font référence à l’ancien nom de la vue utilisent désormais le nouveau nom.</span><span class="sxs-lookup"><span data-stu-id="0a2ab-135">Ensure that all objects, scripts, and applications that reference the view's old name now use the new name.</span></span>  
  
  
