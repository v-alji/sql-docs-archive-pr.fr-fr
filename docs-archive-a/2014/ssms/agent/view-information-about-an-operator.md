---
title: Afficher les informations relatives à un opérateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- viewing operators
- operators (users) [Database Engine], viewing with Management Studio
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
- displaying operators
ms.assetid: 92c82cdf-f704-444e-9539-82aea7fe6fb7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 680b90401f800a9c435bdae33b8e55385541cc4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603767"
---
# <a name="view-information-about-an-operator"></a><span data-ttu-id="03e34-102">Afficher des informations relatives à un opérateur</span><span class="sxs-lookup"><span data-stu-id="03e34-102">View Information About an Operator</span></span>
  <span data-ttu-id="03e34-103">Cette rubrique explique comment afficher des informations sur un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] opérateur de l’agent dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="03e34-103">This topic describes how to view information about a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operator in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="03e34-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="03e34-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="03e34-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="03e34-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="03e34-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="03e34-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="03e34-107">**Pour afficher des informations relatives à un opérateur, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="03e34-107">**To view information about an operator, using:**</span></span>  
  
     [<span data-ttu-id="03e34-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="03e34-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="03e34-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="03e34-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="03e34-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="03e34-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="03e34-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="03e34-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="03e34-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="03e34-112">Permissions</span></span>  
 <span data-ttu-id="03e34-113">Par défaut, les membres du rôle serveur fixe **sysadmin** peuvent exécuter cette procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="03e34-113">By default, members of the **sysadmin** fixed server role can execute this stored procedure.</span></span> <span data-ttu-id="03e34-114">Les autres utilisateurs doivent disposer de l'un des rôles de base de données fixes suivants de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent dans la base de données **msdb** :</span><span class="sxs-lookup"><span data-stu-id="03e34-114">Other users must be granted one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database:</span></span>  
  
-   <span data-ttu-id="03e34-115">**SQLAgentUserRole**</span><span class="sxs-lookup"><span data-stu-id="03e34-115">**SQLAgentUserRole**</span></span>  
  
-   <span data-ttu-id="03e34-116">**SQLAgentReaderRole**</span><span class="sxs-lookup"><span data-stu-id="03e34-116">**SQLAgentReaderRole**</span></span>  
  
-   <span data-ttu-id="03e34-117">**SQLAgentOperatorRole**</span><span class="sxs-lookup"><span data-stu-id="03e34-117">**SQLAgentOperatorRole**</span></span>  
  
 <span data-ttu-id="03e34-118">Pour en savoir plus sur les autorisations de ces rôles, consultez [Rôles de base de données fixes de l'Agent SQL Server](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="03e34-118">For details about the permissions of these roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="03e34-119">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="03e34-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-information-about-an-operator"></a><span data-ttu-id="03e34-120">Pour afficher des informations relatives à un opérateur</span><span class="sxs-lookup"><span data-stu-id="03e34-120">To view information about an operator</span></span>  
  
1.  <span data-ttu-id="03e34-121">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur qui contient l'opérateur que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="03e34-121">In **Object Explorer**, click the plus sign to expand the server that contains the operator you want to view.</span></span>  
  
2.  <span data-ttu-id="03e34-122">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="03e34-122">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="03e34-123">Cliquez sur le signe plus (+) pour développer le dossier **Opérateurs** .</span><span class="sxs-lookup"><span data-stu-id="03e34-123">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="03e34-124">Cliquez avec le bouton droit sur l’opérateur à afficher, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="03e34-124">Right-click the operator that you want to view and select **Properties**.</span></span>  
  
     <span data-ttu-id="03e34-125">Pour plus d’informations sur les options disponibles contenues dans la boîte de dialogue _Propriétés de_**nom_opérateur** , consultez :</span><span class="sxs-lookup"><span data-stu-id="03e34-125">For more information on the available options contained in the _operator_name_**Properties** dialog box, see:</span></span>  
  
    -   [<span data-ttu-id="03e34-126">Propriétés de l’opérateur et nouvel opérateur &#40;&#41;page général</span><span class="sxs-lookup"><span data-stu-id="03e34-126">Operator Properties and New Operator &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="03e34-127">Propriétés de l’opérateur : nouvel opérateur &#40;page notifications&#41;</span><span class="sxs-lookup"><span data-stu-id="03e34-127">Operator Properties: New Operator &#40;Notifications Page&#41;</span></span>](operator-properties-new-operator-notifications-page.md)  
  
    -   [<span data-ttu-id="03e34-128">Propriétés Opérateur &#40;page Historique&#41;</span><span class="sxs-lookup"><span data-stu-id="03e34-128">Operator Properties &#40;History Page&#41;</span></span>](operator-properties-history-page.md)  
  
5.  <span data-ttu-id="03e34-129">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="03e34-129">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="03e34-130">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="03e34-130">Using Transact-SQL</span></span>  
  
#### <a name="to-view-information-about-an-operator"></a><span data-ttu-id="03e34-131">Pour afficher des informations relatives à un opérateur</span><span class="sxs-lookup"><span data-stu-id="03e34-131">To view information about an operator</span></span>  
  
1.  <span data-ttu-id="03e34-132">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03e34-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="03e34-133">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="03e34-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="03e34-134">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="03e34-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- reports information about operator Fran??ois Ajenstat   
    -- This example assumes that the operator exists.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_operator  
        @operator_name = N'Fran??ois Ajenstat' ;  
    GO  
    ```  
  
 <span data-ttu-id="03e34-135">Pour plus d’informations, consultez [sp_help_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="03e34-135">For more information, see [sp_help_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-operator-transact-sql).</span></span>  
  
  
