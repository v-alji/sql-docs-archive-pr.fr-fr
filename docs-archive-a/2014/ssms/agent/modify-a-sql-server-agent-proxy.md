---
title: Modifier un proxy de SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- proxies [SQL Server Agent], modifying
- modifying SQL Server Agent proxy
ms.assetid: 6e1dfbaa-8089-4813-940c-d5a2e13d8552
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2f86793a8ddcc6fe8f981d6b367d2178c5a794ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603790"
---
# <a name="modify-a-sql-server-agent-proxy"></a><span data-ttu-id="af2b2-102">Modify a SQL Server Agent Proxy</span><span class="sxs-lookup"><span data-stu-id="af2b2-102">Modify a SQL Server Agent Proxy</span></span>
  <span data-ttu-id="af2b2-103">Cette rubrique explique comment modifier un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proxy de l’agent dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="af2b2-103">This topic describes how to modify a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="af2b2-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="af2b2-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="af2b2-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="af2b2-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="af2b2-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="af2b2-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="af2b2-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="af2b2-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="af2b2-108">**Pour modifier un proxy de SQL Server Agent, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="af2b2-108">**To modify a SQL Server Agent proxy, using:**</span></span>  
  
     [<span data-ttu-id="af2b2-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="af2b2-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="af2b2-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="af2b2-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="af2b2-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="af2b2-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="af2b2-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="af2b2-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="af2b2-113">Les proxys de l'Agent[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilisent les informations d'identification pour stocker les informations relatives aux comptes d'utilisateur Windows.</span><span class="sxs-lookup"><span data-stu-id="af2b2-113">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxies use credentials to store information about Windows user accounts.</span></span> <span data-ttu-id="af2b2-114">L'utilisateur spécifié dans l'information d'identification doit être habilité à ouvrir une session en tant que programme de traitement par lots sur l'ordinateur sur lequel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="af2b2-114">The user specified in the credential must have "Log on as a batch job" permission on the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="af2b2-115">vérifie l'accès au sous-système pour un proxy et donne accès au proxy à chaque exécution de l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="af2b2-115">Agent checks subsystem access for a proxy and gives access to the proxy each time the job step runs.</span></span> <span data-ttu-id="af2b2-116">Si le proxy n'a plus accès au sous-système, l'étape de travail échoue.</span><span class="sxs-lookup"><span data-stu-id="af2b2-116">If the proxy no longer has access to the subsystem, the job step fails.</span></span> <span data-ttu-id="af2b2-117">Sinon, l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] emprunte l'identité de l'utilisateur spécifié dans le proxy et exécute l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="af2b2-117">Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent impersonates the user that is specified in the proxy and runs the job step.</span></span>  
  
-   <span data-ttu-id="af2b2-118">Si la connexion de l'utilisateur a accès au proxy ou que l'utilisateur appartient à un rôle qui y a accès, l'utilisateur peut recourir au proxy dans une étape de travail.</span><span class="sxs-lookup"><span data-stu-id="af2b2-118">If the login for the user has access to the proxy, or the user belongs to any role with access to the proxy, the user can use the proxy in a job step.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="af2b2-119">Sécurité</span><span class="sxs-lookup"><span data-stu-id="af2b2-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="af2b2-120">Autorisations</span><span class="sxs-lookup"><span data-stu-id="af2b2-120">Permissions</span></span>  
 <span data-ttu-id="af2b2-121">Seuls les membres du rôle serveur fixe **sysadmin** peuvent créer, modifier ou supprimer des comptes proxy.</span><span class="sxs-lookup"><span data-stu-id="af2b2-121">Only members of the **sysadmin** fixed server role can create, modify, or delete proxy accounts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="af2b2-122">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="af2b2-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-ssnoversion-agent-proxy"></a><span data-ttu-id="af2b2-123">Pour modifier un proxy de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af2b2-123">To modify a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy</span></span>  
  
1.  <span data-ttu-id="af2b2-124">Dans **Explorateur d'objets**, cliquez sur le signe plus pour développer le serveur qui contient le compte proxy de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="af2b2-124">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account that you want to modify.</span></span>  
  
2.  <span data-ttu-id="af2b2-125">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="af2b2-125">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="af2b2-126">Cliquez sur le signe plus (+) pour développer le dossier **Proxys** .</span><span class="sxs-lookup"><span data-stu-id="af2b2-126">Click the plus sign to expand the **Proxies** folder.</span></span>  
  
4.  <span data-ttu-id="af2b2-127">Cliquez sur le signe plus pour développer le nœud du sous-système du proxy ( **Script ActiveX**, par exemple).</span><span class="sxs-lookup"><span data-stu-id="af2b2-127">Click the plus sign to expand the subsystem node for the proxy (for example, **ActiveX Script**).</span></span>  
  
5.  <span data-ttu-id="af2b2-128">Cliquez avec le bouton droit sur le compte proxy que vous voulez modifier, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="af2b2-128">Right-click the proxy account you want to modify and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="af2b2-129">Dans la boîte de dialogue _Propriétés du compte proxy_**nom_proxy** , apportez des modifications au compte proxy selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="af2b2-129">In the _proxy_name_**Proxy Account Properties** dialog box, make changes to the proxy account as necessary.</span></span> <span data-ttu-id="af2b2-130">Pour plus d’informations sur les options de cette boîte de dialogue, consultez [Créer un proxy de SQL Server Agent](create-a-sql-server-agent-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="af2b2-130">For more information on the options in this dialog box, see [Create a SQL Server Agent Proxy](create-a-sql-server-agent-proxy.md).</span></span>  
  
7.  <span data-ttu-id="af2b2-131">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="af2b2-131">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="af2b2-132">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="af2b2-132">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-ssnoversion-agent-proxy"></a><span data-ttu-id="af2b2-133">Pour modifier un proxy de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af2b2-133">To modify a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy</span></span>  
  
1.  <span data-ttu-id="af2b2-134">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af2b2-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="af2b2-135">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="af2b2-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="af2b2-136">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="af2b2-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Disables the proxy named 'Catalog application proxy'.  
    USE msdb ;  
    GO  
    EXEC dbo.sp_update_proxy  
        @proxy_name = 'Catalog application proxy',  
        @enabled = 0;  
    GO  
    ```  
  
 <span data-ttu-id="af2b2-137">Pour plus d’informations, consultez [sp_update_proxy &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-proxy-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="af2b2-137">For more information, see [sp_update_proxy &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-proxy-transact-sql).</span></span>  
  
  
