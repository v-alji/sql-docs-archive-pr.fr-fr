---
title: Abonner une base de données ou annuler son abonnement à une catégorie de stratégie | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.groupsubscription.f1
ms.assetid: d2c31769-7098-428e-ad9c-ef56541b7c52
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2b4ca6f804352b57b30b42012da93e0d031be8d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699455"
---
# <a name="subscribe-or-unsubscribe-a-database--to-a-policy-category"></a><span data-ttu-id="8c8ce-102">Abonner une base de données ou annuler son abonnement à une catégorie de stratégie</span><span class="sxs-lookup"><span data-stu-id="8c8ce-102">Subscribe or Unsubscribe a Database  to a Policy Category</span></span>
  <span data-ttu-id="8c8ce-103">Cette rubrique explique comment abonner une base de données à une catégorie de stratégie dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ou annuler cet abonnement à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c8ce-103">This topic describes how to subscribe or unsubscribe a database to a policy category.in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8c8ce-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="8c8ce-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8c8ce-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="8c8ce-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8c8ce-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="8c8ce-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8c8ce-107">**Pour abonner ou annuler l'abonnement d'une base de données à une catégorie de stratégie à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="8c8ce-107">**To subscribe or unsubscribe a database to a policy category., using:**</span></span>  
  
     [<span data-ttu-id="8c8ce-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8c8ce-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8c8ce-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8c8ce-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8c8ce-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="8c8ce-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8c8ce-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="8c8ce-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8c8ce-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="8c8ce-112">Permissions</span></span>  
 <span data-ttu-id="8c8ce-113">Nécessite l'appartenance au rôle de base de données fixe db_owner.</span><span class="sxs-lookup"><span data-stu-id="8c8ce-113">Requires membership in the db_owner fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8c8ce-114">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8c8ce-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-subscribe-or-unsubscribe-a-database-to-a-policy-category"></a><span data-ttu-id="8c8ce-115">Pour abonner ou annuler l'abonnement d'une base de données à une catégorie de stratégie</span><span class="sxs-lookup"><span data-stu-id="8c8ce-115">To subscribe or unsubscribe a database to a policy category</span></span>  
  
1.  <span data-ttu-id="8c8ce-116">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur qui contient la base de données dont vous souhaitez gérer les abonnements aux catégories.</span><span class="sxs-lookup"><span data-stu-id="8c8ce-116">In **Object Explorer**, click the plus sign to expand the server that contains the database wherein you want to manage category subscriptions.</span></span>  
  
2.  <span data-ttu-id="8c8ce-117">Cliquez sur le signe plus (+) pour développer le dossier **Bases de données** .</span><span class="sxs-lookup"><span data-stu-id="8c8ce-117">Click the plus sign to expand the **Databases** folder.</span></span>  
  
3.  <span data-ttu-id="8c8ce-118">Cliquez avec le bouton droit sur la base de données dont vous souhaitez gérer les abonnements aux catégories, pointez sur **Stratégies**, puis sélectionnez **Catégories**.</span><span class="sxs-lookup"><span data-stu-id="8c8ce-118">Right-click the database wherein you want to manage category subscriptions, point to **Policies**, and select **Categories**</span></span>  
  
     <span data-ttu-id="8c8ce-119">Les options suivantes sont disponibles dans la boîte de dialogue **Catégories** :</span><span class="sxs-lookup"><span data-stu-id="8c8ce-119">The following options are available in the **Categories** dialog box:</span></span>  
  
     <span data-ttu-id="8c8ce-120">Développer la colonne</span><span class="sxs-lookup"><span data-stu-id="8c8ce-120">Expand column</span></span>  
     <span data-ttu-id="8c8ce-121">Cliquez sur cette option pour développer une catégorie de stratégie.</span><span class="sxs-lookup"><span data-stu-id="8c8ce-121">Click to expand a policy category.</span></span> <span data-ttu-id="8c8ce-122">Celle-ci répertorie toutes les stratégies incluses dans la catégorie.</span><span class="sxs-lookup"><span data-stu-id="8c8ce-122">This lists all the policies that are included in the category.</span></span>  
  
     <span data-ttu-id="8c8ce-123">**Nom**</span><span class="sxs-lookup"><span data-stu-id="8c8ce-123">**Name**</span></span>  
     <span data-ttu-id="8c8ce-124">Nom de la catégorie de stratégie.</span><span class="sxs-lookup"><span data-stu-id="8c8ce-124">The name of the policy category.</span></span>  
  
     <span data-ttu-id="8c8ce-125">**Abonné**</span><span class="sxs-lookup"><span data-stu-id="8c8ce-125">**Subscribed**</span></span>  
     <span data-ttu-id="8c8ce-126">Indique si la cible est abonnée à la catégorie de stratégie.</span><span class="sxs-lookup"><span data-stu-id="8c8ce-126">Indicates whether the target has subscribed to the policy category.</span></span> <span data-ttu-id="8c8ce-127">Si cette case à cocher est désactivée, la catégorie de stratégie est définie pour **Abonnements à la base de données autorisée**.</span><span class="sxs-lookup"><span data-stu-id="8c8ce-127">If this check box is disabled, the policy category is set for **Mandate Database Subscriptions**.</span></span> <span data-ttu-id="8c8ce-128">Cela signifie que la catégorie de stratégie s'applique à toutes les bases de données du serveur.</span><span class="sxs-lookup"><span data-stu-id="8c8ce-128">This means that the policy category applies to all databases on the server.</span></span>  
  
     <span data-ttu-id="8c8ce-129">**Stratégie**</span><span class="sxs-lookup"><span data-stu-id="8c8ce-129">**Policy**</span></span>  
     <span data-ttu-id="8c8ce-130">Lorsque des groupes de stratégies sont développés, affiche les stratégies appartenant à la catégorie de stratégie.</span><span class="sxs-lookup"><span data-stu-id="8c8ce-130">When policy groups are expanded, displays the policies in the policy category.</span></span>  
  
     <span data-ttu-id="8c8ce-131">**Activé**</span><span class="sxs-lookup"><span data-stu-id="8c8ce-131">**Enabled**</span></span>  
     <span data-ttu-id="8c8ce-132">Indique si les stratégies sont activées ou désactivées.</span><span class="sxs-lookup"><span data-stu-id="8c8ce-132">Indicates whether the policies are enabled or disabled.</span></span>  
  
     <span data-ttu-id="8c8ce-133">**Mode d'exécution**</span><span class="sxs-lookup"><span data-stu-id="8c8ce-133">**Execution Mode**</span></span>  
     <span data-ttu-id="8c8ce-134">Indique le mode d'exécution de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="8c8ce-134">Displays the execution mode of the policy.</span></span>  
  
     <span data-ttu-id="8c8ce-135">**History**</span><span class="sxs-lookup"><span data-stu-id="8c8ce-135">**History**</span></span>  
     <span data-ttu-id="8c8ce-136">Cliquez sur le lien hypertexte Afficher l'historique pour ouvrir la Visionneuse du fichier journal et consulter l'historique de stratégie.</span><span class="sxs-lookup"><span data-stu-id="8c8ce-136">Click the View History hyperlink to open the Log File Viewer to see the policy history.</span></span>  
  
4.  <span data-ttu-id="8c8ce-137">Pour l’abonnement à une catégorie de gestion basée sur des stratégies, cochez la case de la catégorie dans la colonne **Abonné** .</span><span class="sxs-lookup"><span data-stu-id="8c8ce-137">To subscribe to a Policy-Based Management category, select the category's check box under the **Subscribed** column.</span></span> <span data-ttu-id="8c8ce-138">Pour annuler l'abonnement à une catégorie, désactivez la case à cocher.</span><span class="sxs-lookup"><span data-stu-id="8c8ce-138">To unsubscribe from a category, clear the check box.</span></span>  
  
5.  <span data-ttu-id="8c8ce-139">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c8ce-139">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8c8ce-140">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8c8ce-140">Using Transact-SQL</span></span>  
  
#### <a name="to-subscribe-a-database-to-a-policy-category"></a><span data-ttu-id="8c8ce-141">Pour abonner une base de données à une catégorie de stratégie</span><span class="sxs-lookup"><span data-stu-id="8c8ce-141">To subscribe a database to a policy category</span></span>  
  
1.  <span data-ttu-id="8c8ce-142">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c8ce-142">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8c8ce-143">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="8c8ce-143">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8c8ce-144">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="8c8ce-144">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    -- Adds a subscription to the 'Finance' policy category for the AdventureWorks2012 database.  
    EXEC sys.sp_syspolicy_subscribe_to_policy_category @policy_category = N'Finance';  
    GO  
    ```  
  
 <span data-ttu-id="8c8ce-145">Pour plus d’informations, consultez [sp_syspolicy_subscribe_to_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-subscribe-to-policy-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8c8ce-145">For more information, see [sp_syspolicy_subscribe_to_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-subscribe-to-policy-category-transact-sql).</span></span>  
  
#### <a name="to-unsubscribe-a-database-to-a-policy-category"></a><span data-ttu-id="8c8ce-146">Pour annuler l'abonnement d'une base de données à une catégorie de stratégie</span><span class="sxs-lookup"><span data-stu-id="8c8ce-146">To unsubscribe a database to a policy category</span></span>  
  
1.  <span data-ttu-id="8c8ce-147">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c8ce-147">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8c8ce-148">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="8c8ce-148">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8c8ce-149">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="8c8ce-149">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    -- Deletes a subscription to the 'Finance' policy category for the AdventureWorks2012 database.  
    EXEC sys.sp_syspolicy_unsubscribe_from_policy_category @policy_category = N'Finance';  
    GO  
    ```  
  
 <span data-ttu-id="8c8ce-150">Pour plus d’informations, consultez [sp_syspolicy_unsubscribe_from_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-unsubscribe-from-policy-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8c8ce-150">For more information, see [sp_syspolicy_unsubscribe_from_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-unsubscribe-from-policy-category-transact-sql).</span></span>  
  
  
