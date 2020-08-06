---
title: Gérer les catégories de stratégie | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.policycategories.f1
ms.assetid: d188a819-731f-4029-98aa-780d3299a0ce
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 168d05dd88286263da1dca5456a2c6072e946786
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603453"
---
# <a name="manage-policy-categories"></a><span data-ttu-id="658be-102">Gérer les catégories de stratégie</span><span class="sxs-lookup"><span data-stu-id="658be-102">Manage Policy Categories</span></span>
  <span data-ttu-id="658be-103">Cette rubrique explique comment appliquer une seule ou toutes les stratégies disponibles dans une catégorie à l'ensemble de l'instance de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="658be-103">This topic describes how to apply any or all available policies in a category to the whole instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="658be-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="658be-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="658be-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="658be-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="658be-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="658be-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="658be-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="658be-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="658be-108">**Pour appliquer des stratégies de catégorie à une instance SQL Server à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="658be-108">**To apply category policies to a SQL Server instance, using:**</span></span>  
  
     [<span data-ttu-id="658be-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="658be-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="658be-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="658be-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="658be-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="658be-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="658be-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="658be-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="658be-113">Lorsque vous utilisez [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], si la case **Abonnements à la base de données autorisée** n'est pas sélectionnée, la catégorie de stratégie doit être appliquée individuellement à chaque partie pertinente du serveur, telle qu'une ou plusieurs bases de données ou tables.</span><span class="sxs-lookup"><span data-stu-id="658be-113">When using [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], if the **Mandate Database Subscriptions** check box is not selected, the policy category must be individually applied to each relevant portion of the server, such as one or more databases or tables.</span></span>  
  
-   <span data-ttu-id="658be-114">Si vous spécifiez une catégorie de stratégie qui n'existe pas, une nouvelle catégorie de stratégie est créée et l'abonnement est autorisé pour toutes les bases de données lorsque vous exécutez la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="658be-114">If you specify a policy category that does not exist, a new policy category is created and the subscription is mandated for all databases when you execute the stored procedure.</span></span> <span data-ttu-id="658be-115">Si vous supprimez l’abonnement autorisé pour la nouvelle catégorie, il ne s’appliquera qu’à la base de données que vous avez spécifiée en tant que *target_object*.</span><span class="sxs-lookup"><span data-stu-id="658be-115">If you then clear the mandated subscription for the new category, the subscription will only apply for the database that you specified as the *target_object*.</span></span> <span data-ttu-id="658be-116">Pour plus d’informations sur la modification d’un paramètre d’abonnement autorisé, consultez [sp_syspolicy_update_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-update-policy-category-subscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="658be-116">For more information about how to change a mandated subscription setting, see [sp_syspolicy_update_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-update-policy-category-subscription-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="658be-117">Sécurité</span><span class="sxs-lookup"><span data-stu-id="658be-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="658be-118">Autorisations</span><span class="sxs-lookup"><span data-stu-id="658be-118">Permissions</span></span>  
 <span data-ttu-id="658be-119">Cette procédure stockée est exécutée dans le contexte du propriétaire actuel de la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="658be-119">This stored procedure runs in the context of the current owner of the stored procedure.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="658be-120">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="658be-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-apply-category-policies-to-a-sql-server-instance"></a><span data-ttu-id="658be-121">Pour appliquer des stratégies de catégorie à une instance SQL Server</span><span class="sxs-lookup"><span data-stu-id="658be-121">To apply category policies to a SQL Server instance</span></span>  
  
1.  <span data-ttu-id="658be-122">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur sur lequel vous souhaitez appliquer les stratégies de catégorie.</span><span class="sxs-lookup"><span data-stu-id="658be-122">In **Object Explorer**, click the plus sign to expand the server where you will apply category policies.</span></span>  
  
2.  <span data-ttu-id="658be-123">Cliquez sur le signe plus (+) pour développer le dossier **Gestion** .</span><span class="sxs-lookup"><span data-stu-id="658be-123">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="658be-124">Cliquez avec le bouton droit sur **Gestion de la stratégie** et sélectionnez **Gérer les catégories**.</span><span class="sxs-lookup"><span data-stu-id="658be-124">Right-click **Policy Management** and select **Manage Categories**.</span></span>  
  
     <span data-ttu-id="658be-125">les informations suivantes sont disponibles dans la boîte de dialogue **Administration des catégories de stratégie** :</span><span class="sxs-lookup"><span data-stu-id="658be-125">The following information is available in the **Manage Policy Categories** dialog box:</span></span>  
  
     <span data-ttu-id="658be-126">**Nom**</span><span class="sxs-lookup"><span data-stu-id="658be-126">**Name**</span></span>  
     <span data-ttu-id="658be-127">Nom de la catégorie de stratégie.</span><span class="sxs-lookup"><span data-stu-id="658be-127">The name of the policy category.</span></span>  
  
     <span data-ttu-id="658be-128">**Abonnements à la base de données autorisée**</span><span class="sxs-lookup"><span data-stu-id="658be-128">**Mandate Database Subscriptions**</span></span>  
     <span data-ttu-id="658be-129">Force toutes les bases de données sur l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à appliquer les stratégies de la catégorie de stratégie.</span><span class="sxs-lookup"><span data-stu-id="658be-129">Forces all databases on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to enforce policies in the policy category.</span></span>  
  
4.  <span data-ttu-id="658be-130">Activez ou désactivez toutes ou une partie des cases à cocher sous **Abonnements à la base de données autorisée** pour appliquer des catégories de stratégie à l'instance de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="658be-130">Select or clear any or all check boxes under **Mandate Database Subscriptions** to apply that policy category to the SQL Server instance.</span></span>  
  
5.  <span data-ttu-id="658be-131">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="658be-131">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="658be-132">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="658be-132">Using Transact-SQL</span></span>  
  
#### <a name="to-apply-category-policies-to-a-sql-server-instance"></a><span data-ttu-id="658be-133">Pour appliquer des stratégies de catégorie à une instance SQL Server</span><span class="sxs-lookup"><span data-stu-id="658be-133">To apply category policies to a SQL Server instance</span></span>  
  
1.  <span data-ttu-id="658be-134">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="658be-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="658be-135">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="658be-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="658be-136">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="658be-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb;  
    GO  
    -- configures the specified database to subscribe to a policy category that is named 'Table Naming Policies'.  
    EXEC dbo.sp_syspolicy_add_policy_category_subscription @target_type = N'DATABASE'  
    , @target_object = N'AdventureWorks2012'  
    , @policy_category = N'Table Naming Policies';  
    GO  
    ```  
  
 <span data-ttu-id="658be-137">Pour plus d’informations, consultez [sp_syspolicy_add_policy_category_subscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-add-policy-category-subscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="658be-137">For more information, see [sp_syspolicy_add_policy_category_subscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-add-policy-category-subscription-transact-sql).</span></span>  
  
  
