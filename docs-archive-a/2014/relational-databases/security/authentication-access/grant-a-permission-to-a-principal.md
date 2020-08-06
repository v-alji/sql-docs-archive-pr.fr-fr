---
title: Accorder une autorisation à un principal | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Grant permission to a principal
ms.assetid: 4107389d-05b6-4aa3-9fa8-95b40cdf05dc
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 4256d62bdeac2d79c51e5f3792c991e0e3b15096
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709095"
---
# <a name="grant-a-permission-to-a-principal"></a><span data-ttu-id="014e4-102">Accorder une autorisation à un principal</span><span class="sxs-lookup"><span data-stu-id="014e4-102">Grant a Permission to a Principal</span></span>
  <span data-ttu-id="014e4-103">Cette rubrique explique comment accorder une autorisation à un principal dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="014e4-103">This topic describes how to grant permission to a principal in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="014e4-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="014e4-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="014e4-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="014e4-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="014e4-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="014e4-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="014e4-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="014e4-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="014e4-108">**Pour accorder une autorisation à un principal, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="014e4-108">**To grant permission to a principal, using:**</span></span>  
  
     [<span data-ttu-id="014e4-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="014e4-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="014e4-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="014e4-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="014e4-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="014e4-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="014e4-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="014e4-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="014e4-113">Tenez compte des recommandations suivantes qui peuvent faciliter la gestion des autorisations.</span><span class="sxs-lookup"><span data-stu-id="014e4-113">Consider the following best practices that can make managing permissions easier.</span></span>  
  
-   <span data-ttu-id="014e4-114">Accorder des autorisations à des rôles plutôt qu'à des connexions ou des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="014e4-114">Grant permission to roles, instead of individual logins or users.</span></span> <span data-ttu-id="014e4-115">Lorsqu'un individu est remplacé par un autre, supprimez celui qui quitte le rôle et ajoutez le nouvel arrivant au rôle.</span><span class="sxs-lookup"><span data-stu-id="014e4-115">When one individual is replaced by another, remove the departing individual from the role and add the new individual to the role.</span></span> <span data-ttu-id="014e4-116">Les nombreuses autorisations qui peuvent être associées au rôle seront automatiquement disponibles pour ce dernier.</span><span class="sxs-lookup"><span data-stu-id="014e4-116">The many permissions that might be associated with the role will automatically be available to the new individual.</span></span> <span data-ttu-id="014e4-117">Si, dans une entreprise, plusieurs personnes ont besoin des mêmes autorisations, l'ajout de chacune d'entre elles au rôle leur accordera les mêmes autorisations.</span><span class="sxs-lookup"><span data-stu-id="014e4-117">If several people in an organization require the same permissions, adding each of them to the role will grant them the same permissions.</span></span>  
  
-   <span data-ttu-id="014e4-118">Configurez des éléments sécurisables similaires (tables, vues et procédures) qui seront détenus par un schéma, puis octroyez des autorisations au schéma.</span><span class="sxs-lookup"><span data-stu-id="014e4-118">Configure similar securables (tables, views, and procedures) to be owned by a schema, then grant permissions to the schema.</span></span> <span data-ttu-id="014e4-119">Par exemple, le schéma de registre du personnel peut détenir plusieurs tables, vues et procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="014e4-119">For example, the payroll schema might own several tables, views, and stored procedures.</span></span> <span data-ttu-id="014e4-120">En accordant l'accès au schéma, toutes les autorisations nécessaires pour effectuer la fonction de gestion du personnel peuvent être accordées en même temps.</span><span class="sxs-lookup"><span data-stu-id="014e4-120">By granting access to the schema, all the necessary permissions to perform the payroll function can be granted at the same time.</span></span> <span data-ttu-id="014e4-121">Pour en savoir plus sur les éléments sécurisables auxquels accorder des autorisations, consultez [Securables](../securables.md).</span><span class="sxs-lookup"><span data-stu-id="014e4-121">For more information about what securables can be granted permissions, see [Securables](../securables.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="014e4-122">Sécurité</span><span class="sxs-lookup"><span data-stu-id="014e4-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="014e4-123">Autorisations</span><span class="sxs-lookup"><span data-stu-id="014e4-123">Permissions</span></span>  
 <span data-ttu-id="014e4-124">Le fournisseur d'autorisations (ou le principal spécifié avec l'option AS) doit posséder l'autorisation elle-même avec l'option GRANT OPTION ou une autorisation plus élevée qui implique l'autorisation accordée.</span><span class="sxs-lookup"><span data-stu-id="014e4-124">The grantor (or the principal specified with the AS option) must have either the permission itself with GRANT OPTION or a higher permission that implies the permission being granted.</span></span> <span data-ttu-id="014e4-125">Les membres du rôle serveur fixe **sysadmin** peuvent accorder toutes les autorisations.</span><span class="sxs-lookup"><span data-stu-id="014e4-125">Members of the **sysadmin** fixed server role can grant any permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="014e4-126">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="014e4-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-grant-permission-to-a-principal"></a><span data-ttu-id="014e4-127">Pour accorder une autorisation à un principal</span><span class="sxs-lookup"><span data-stu-id="014e4-127">To grant permission to a principal</span></span>  
  
1.  <span data-ttu-id="014e4-128">Dans l'Explorateur d'objets, développez la base de données qui contient l'objet auquel vous souhaitez octroyer des autorisations.</span><span class="sxs-lookup"><span data-stu-id="014e4-128">In Object Explorer, expand the database that contains the object to which you want to grant permissions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="014e4-129">Ces étapes traitent spécifiquement de l'octroi d'autorisations à une procédure stockée, mais vous pouvez utiliser des étapes similaires pour ajouter des autorisations aux tables, aux vues, aux fonctions et aux assemblys, ainsi qu'à d'autres éléments sécurisables.</span><span class="sxs-lookup"><span data-stu-id="014e4-129">These steps deal specifically with granting permissions to a stored procedure, but you can use similar steps to add permissions to tables, views, functions, and assemblies, as well as other securables.</span></span> <span data-ttu-id="014e4-130">Pour plus d’informations, consultez [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="014e4-130">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql)</span></span>  
  
2.  <span data-ttu-id="014e4-131">Développez le dossier **Programmabilité** .</span><span class="sxs-lookup"><span data-stu-id="014e4-131">Expand the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="014e4-132">Développez le dossier **Procédures stockées** .</span><span class="sxs-lookup"><span data-stu-id="014e4-132">Expand the **Stored Procedures** folder.</span></span>  
  
4.  <span data-ttu-id="014e4-133">Cliquez avec le bouton droit sur une procédure stockée, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="014e4-133">Right-click a stored procedure and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="014e4-134">Dans la boîte de dialogue Propriétés de la **procédure stockée-**_stored_procedure_name_ , sous sélectionner une page, sélectionnez **autorisations**.</span><span class="sxs-lookup"><span data-stu-id="014e4-134">In the **Stored Procedure Properties -**_stored_procedure_name_ dialog box, under select a page, select **Permissions**.</span></span> <span data-ttu-id="014e4-135">Utilisez cette page pour ajouter des utilisateurs ou des rôles à la procédure stockée et spécifier les autorisations dont disposeront ces utilisateurs ou rôles.</span><span class="sxs-lookup"><span data-stu-id="014e4-135">Use this page to add users or roles to the stored procedure and specify the permissions those users or roles have.</span></span>  
  
6.  <span data-ttu-id="014e4-136">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="014e4-136">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="014e4-137">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="014e4-137">Using Transact-SQL</span></span>  
  
#### <a name="to-grant-permission-to-a-principal"></a><span data-ttu-id="014e4-138">Pour accorder une autorisation à un principal</span><span class="sxs-lookup"><span data-stu-id="014e4-138">To grant permission to a principal</span></span>  
  
1.  <span data-ttu-id="014e4-139">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="014e4-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="014e4-140">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="014e4-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="014e4-141">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="014e4-141">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Grants EXECUTE permission on stored procedure HumanResources.uspUpdateEmployeeHireInfo to an application role called Recruiting11.   
    USE AdventureWorks2012;  
    GO  
    GRANT EXECUTE ON OBJECT::HumanResources.uspUpdateEmployeeHireInfo  
        TO Recruiting11;  
    GO  
    ```  
  
 <span data-ttu-id="014e4-142">Pour plus d’informations, consultez [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) et [Octroi d’autorisations d’objet &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="014e4-142">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) and [GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="014e4-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="014e4-143">See Also</span></span>  
 [<span data-ttu-id="014e4-144">Principaux &#40;moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="014e4-144">Principals &#40;Database Engine&#41;</span></span>](principals-database-engine.md)  
  
  
