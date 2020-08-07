---
title: Supprimer un proxy de SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- deleting SQL Server Agent proxies
- proxies [SQL Server Agent], deleting
- removing SQL Server Agent proxies
ms.assetid: 9248841d-7294-47d4-94f3-b34a0521fabc
author: stevestein
ms.author: sstein
ms.openlocfilehash: a672c6392e2ffed3ca2a7ed655b806d9d093b10c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612065"
---
# <a name="delete-a-sql-server-agent-proxy"></a><span data-ttu-id="03bc5-102">Delete a SQL Server Agent Proxy</span><span class="sxs-lookup"><span data-stu-id="03bc5-102">Delete a SQL Server Agent Proxy</span></span>
  <span data-ttu-id="03bc5-103">Cette rubrique explique comment supprimer un compte proxy de l'Agent dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03bc5-103">This topic describes how to delete a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="03bc5-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="03bc5-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="03bc5-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="03bc5-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="03bc5-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="03bc5-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="03bc5-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="03bc5-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="03bc5-108">**Pour supprimer un compte proxy de SQL Server Agent, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="03bc5-108">**To delete a SQL Server Agent proxy account, using:**</span></span>  
  
     [<span data-ttu-id="03bc5-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="03bc5-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="03bc5-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="03bc5-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="03bc5-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="03bc5-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="03bc5-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="03bc5-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="03bc5-113">Lorsque vous supprimez un compte proxy de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vérifiez que le proxy ne fait pas référence à des étapes de travail actives.</span><span class="sxs-lookup"><span data-stu-id="03bc5-113">When you delete a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account, make sure the proxy does not reference any active job steps.</span></span> <span data-ttu-id="03bc5-114">Pour vérifier si des étapes de travail font référence au proxy, cliquez avec le bouton droit sur le proxy, sélectionnez **Propriétés**, puis dans la boîte de dialogue _Propriétés du compte proxy_**nom_proxy** , sélectionnez la page **Références** .</span><span class="sxs-lookup"><span data-stu-id="03bc5-114">To check for any job steps that reference the proxy, right-click the proxy, select **Properties**, and then, in the _proxy_name_**Proxy Account Properties** dialog box, select the **References** page.</span></span> <span data-ttu-id="03bc5-115">Si vous supprimez un proxy, il vous est proposé de réaffecter toutes les étapes de travail qui utilisent ce proxy dans la boîte de dialogue **Supprimer un objet** .</span><span class="sxs-lookup"><span data-stu-id="03bc5-115">If you delete a proxy, you are given the option to reassign all job steps that use that proxy in the **Delete Object** dialog box.</span></span>  
  
-   <span data-ttu-id="03bc5-116">Les proxys de l'Agent[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilisent les informations d'identification pour stocker les informations relatives aux comptes d'utilisateur Windows.</span><span class="sxs-lookup"><span data-stu-id="03bc5-116">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxies use credentials to store information about Windows user accounts.</span></span> <span data-ttu-id="03bc5-117">L'utilisateur spécifié dans l'information d'identification doit être habilité à ouvrir une session en tant que programme de traitement par lots sur l'ordinateur sur lequel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="03bc5-117">The user specified in the credential must have "Log on as a batch job" permission on the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="03bc5-118">vérifie l'accès au sous-système pour un proxy et donne accès au proxy à chaque exécution de l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="03bc5-118">Agent checks subsystem access for a proxy and gives access to the proxy each time the job step runs.</span></span> <span data-ttu-id="03bc5-119">Si le proxy n'a plus accès au sous-système, l'étape de travail échoue.</span><span class="sxs-lookup"><span data-stu-id="03bc5-119">If the proxy no longer has access to the subsystem, the job step fails.</span></span> <span data-ttu-id="03bc5-120">Sinon, l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] emprunte l'identité de l'utilisateur spécifié dans le proxy et exécute l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="03bc5-120">Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent impersonates the user that is specified in the proxy and runs the job step.</span></span>  
  
-   <span data-ttu-id="03bc5-121">Si la connexion de l'utilisateur a accès au proxy ou que l'utilisateur appartient à un rôle qui y a accès, l'utilisateur peut recourir au proxy dans une étape de travail.</span><span class="sxs-lookup"><span data-stu-id="03bc5-121">If the login for the user has access to the proxy, or the user belongs to any role with access to the proxy, the user can use the proxy in a job step.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="03bc5-122">Sécurité</span><span class="sxs-lookup"><span data-stu-id="03bc5-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="03bc5-123">Autorisations</span><span class="sxs-lookup"><span data-stu-id="03bc5-123">Permissions</span></span>  
 <span data-ttu-id="03bc5-124">Seuls les membres du rôle serveur fixe **sysadmin** peuvent créer, modifier ou supprimer des comptes proxy.</span><span class="sxs-lookup"><span data-stu-id="03bc5-124">Only members of the **sysadmin** fixed server role can create, modify, or delete proxy accounts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="03bc5-125">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="03bc5-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-proxy-account"></a><span data-ttu-id="03bc5-126">Pour supprimer un compte proxy de SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="03bc5-126">To delete a SQL Server Agent proxy account</span></span>  
  
1.  <span data-ttu-id="03bc5-127">Dans l' **Explorateur d'objets**, cliquez sur le signe plus pour développer un serveur qui contient le compte proxy à supprimer.</span><span class="sxs-lookup"><span data-stu-id="03bc5-127">In **Object Explorer**, click the plus sign to expand a server that contains the proxy account that you want to delete.</span></span>  
  
2.  <span data-ttu-id="03bc5-128">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="03bc5-128">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="03bc5-129">Cliquez sur le signe plus (+) pour développer le dossier **Proxys** .</span><span class="sxs-lookup"><span data-stu-id="03bc5-129">Click the plus sign to expand the **Proxies** folder.</span></span>  
  
4.  <span data-ttu-id="03bc5-130">Cliquez sur le signe plus pour développer le sous-système qui contient le compte proxy à supprimer (par exemple, **Script ActiveX**).</span><span class="sxs-lookup"><span data-stu-id="03bc5-130">Click the plus sign to expand the subsystem that contains the proxy account you want to delete (for example, **ActiveX Script)**.</span></span>  
  
5.  <span data-ttu-id="03bc5-131">Cliquez avec le bouton droit sur le compte proxy à supprimer, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="03bc5-131">Right-click the proxy account that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="03bc5-132">Dans la boîte de dialogue **Supprimer un objet** , confirmez que le compte proxy correct est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="03bc5-132">In the **Delete Object** dialog box, confirm that the correct proxy account is selected.</span></span> <span data-ttu-id="03bc5-133">Activez la case à cocher **Réaffecter à** pour réaffecter les étapes de travail qui référencent ce compte proxy à un autre compte.</span><span class="sxs-lookup"><span data-stu-id="03bc5-133">Check the **Reassign to** check box to reassign the job steps that reference this proxy account to another account.</span></span>  
  
7.  <span data-ttu-id="03bc5-134">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="03bc5-134">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="03bc5-135">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="03bc5-135">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-proxy-account"></a><span data-ttu-id="03bc5-136">Pour supprimer un compte proxy de SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="03bc5-136">To delete a SQL Server Agent proxy account</span></span>  
  
1.  <span data-ttu-id="03bc5-137">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03bc5-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="03bc5-138">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="03bc5-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="03bc5-139">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="03bc5-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- deletes the proxy "Catalog application proxy"  
    USE msdb ;  
    GO  
    EXEC dbo.sp_delete_proxy  
        @proxy_name = N'Catalog application proxy' ;  
    GO  
    ```  
  
 <span data-ttu-id="03bc5-140">Pour plus d’informations, consultez [sp_delete_proxy &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-proxy-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="03bc5-140">For more information, see [sp_delete_proxy &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-proxy-transact-sql).</span></span>  
  
  
