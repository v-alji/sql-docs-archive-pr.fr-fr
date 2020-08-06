---
title: Créer un serveur cible | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.tsxwiz.msx.f1
- sql12.ag.tsxwiz.cover.f1
- sql12.ag.tsxwiz.credentials.f1
- sql12.ag.tsxwiz.complete.f1
helpviewer_keywords:
- Target Server Wizard
- SQL Server Agent jobs, target servers
- target servers [SQL Server], creating
ms.assetid: 13aabe2d-67fe-4c67-8d49-2928dd705b7a
author: stevestein
ms.author: sstein
ms.openlocfilehash: bd60a19234d186bb0912978589fa60fd8e8a8c22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695260"
---
# <a name="make-a-target-server"></a><span data-ttu-id="beaa1-102">Créer un serveur cible</span><span class="sxs-lookup"><span data-stu-id="beaa1-102">Make a Target Server</span></span>
  <span data-ttu-id="beaa1-103">Cette rubrique explique comment créer un serveur cible dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../includes/tsql-md.md)]ou d'objets SMO (SQL Server Management Objects).</span><span class="sxs-lookup"><span data-stu-id="beaa1-103">This topic describes how to make a target server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="beaa1-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="beaa1-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="beaa1-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="beaa1-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="beaa1-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="beaa1-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="beaa1-107">**Pour créer un serveur cible à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="beaa1-107">**To make a target server, using:**</span></span>  
  
     [<span data-ttu-id="beaa1-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="beaa1-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="beaa1-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="beaa1-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="beaa1-110">SMO</span><span class="sxs-lookup"><span data-stu-id="beaa1-110">SMO</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="beaa1-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="beaa1-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="beaa1-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="beaa1-112">Security</span></span>  
 <span data-ttu-id="beaa1-113">Les travaux distribués dont les étapes sont associées à un proxy sont exécutés dans le contexte du compte proxy du serveur cible.</span><span class="sxs-lookup"><span data-stu-id="beaa1-113">Distributed jobs that have steps which are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="beaa1-114">Assurez-vous que les conditions suivantes sont remplies ou que les étapes de travail associées à un proxy ne seront pas téléchargées du serveur maître vers la cible :</span><span class="sxs-lookup"><span data-stu-id="beaa1-114">Make sure that the following conditions are met or job steps that are associated with a proxy will not be downloaded from the master server to the target:</span></span>  
  
-   <span data-ttu-id="beaa1-115">La sous-clé de Registre du serveur maître **\ HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Microsoft SQL Server \\ < *instance_name*> \SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) a la valeur 1 (true).</span><span class="sxs-lookup"><span data-stu-id="beaa1-115">The master server registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<*instance_name*>\SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) is set to 1 (true).</span></span> <span data-ttu-id="beaa1-116">Par défaut, la valeur de cette sous-clé est 0 (False).</span><span class="sxs-lookup"><span data-stu-id="beaa1-116">By default, this subkey is set to 0 (false).</span></span>  
  
-   <span data-ttu-id="beaa1-117">Il existe sur le serveur cible un compte proxy possédant le même nom que le compte proxy du serveur maître sur lequel l'étape du travail est exécutée.</span><span class="sxs-lookup"><span data-stu-id="beaa1-117">A proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
 <span data-ttu-id="beaa1-118">Si les étapes du travail utilisant des comptes proxy échouent pendant leur téléchargement à partir du serveur maître vers le serveur cible, vous pouvez vérifier la colonne **error_message** dans la table **sysdownloadlist** de la base de données **msdb** pour les messages d’erreur suivants :</span><span class="sxs-lookup"><span data-stu-id="beaa1-118">If job steps that use proxy accounts fail when downloading them from the master server to the target server, you can check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="beaa1-119">« L'étape du travail nécessite un compte proxy, cependant la mise en correspondance de proxy est désactivée sur le serveur cible. »</span><span class="sxs-lookup"><span data-stu-id="beaa1-119">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span>  
  
     <span data-ttu-id="beaa1-120">Pour corriger ce problème, affectez à la sous-clé de Registre **AllowDownloadedJobsToMatchProxyName** la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="beaa1-120">To resolve this error, set the **AllowDownloadedJobsToMatchProxyName** registry subkey to 1.</span></span>  
  
-   <span data-ttu-id="beaa1-121">« Proxy introuvable. »</span><span class="sxs-lookup"><span data-stu-id="beaa1-121">"Proxy not found."</span></span>  
  
     <span data-ttu-id="beaa1-122">Pour résoudre ce problème, vérifiez qu'un compte proxy portant le même nom que le compte proxy du serveur maître sous lequel l'étape s'exécute existe sur le serveur cible.</span><span class="sxs-lookup"><span data-stu-id="beaa1-122">To resolve this error, make sure a proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="beaa1-123">Autorisations</span><span class="sxs-lookup"><span data-stu-id="beaa1-123">Permissions</span></span>  
 <span data-ttu-id="beaa1-124">Les autorisations d'exécution de cette procédure sont octroyées par défaut aux membres du rôle serveur fixe `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="beaa1-124">Permissions to execute this procedure default to members of the `sysadmin` fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="beaa1-125">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="beaa1-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-make-a-target-server"></a><span data-ttu-id="beaa1-126">Pour créer un serveur cible</span><span class="sxs-lookup"><span data-stu-id="beaa1-126">To make a target server</span></span>  
  
1.  <span data-ttu-id="beaa1-127">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="beaa1-127">In **Object Explorer,** connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="beaa1-128">Cliquez avec le bouton droit sur **Agent SQL Server**, pointez sur **Administration multiserveur**, puis cliquez sur **Transformer en serveur cible**.</span><span class="sxs-lookup"><span data-stu-id="beaa1-128">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Make this a Target**.</span></span> <span data-ttu-id="beaa1-129">L' **Assistant Création d'un serveur cible** vous aide à créer un serveur cible.</span><span class="sxs-lookup"><span data-stu-id="beaa1-129">The **Target Server Wizard** guides you through the process of making a target server.</span></span>  
  
3.  <span data-ttu-id="beaa1-130">Dans la page **Sélectionner un serveur maître** , sélectionnez le serveur maître à partir duquel ce serveur cible va recevoir des travaux.</span><span class="sxs-lookup"><span data-stu-id="beaa1-130">From the **Select a Master Server** page, select the master server that this target server will receive jobs from.</span></span>  
  
     <span data-ttu-id="beaa1-131">**Choisir le serveur**</span><span class="sxs-lookup"><span data-stu-id="beaa1-131">**Pick Server**</span></span>  
     <span data-ttu-id="beaa1-132">Connectez-vous au serveur maître.</span><span class="sxs-lookup"><span data-stu-id="beaa1-132">Connect to the master server.</span></span>  
  
     <span data-ttu-id="beaa1-133">**Description de ce serveur**</span><span class="sxs-lookup"><span data-stu-id="beaa1-133">**Description of this server**</span></span>  
     <span data-ttu-id="beaa1-134">Tapez une description de ce serveur cible.</span><span class="sxs-lookup"><span data-stu-id="beaa1-134">Type a description for this target server.</span></span> <span data-ttu-id="beaa1-135">Le serveur cible télécharge cette description sur le serveur maître.</span><span class="sxs-lookup"><span data-stu-id="beaa1-135">The target server uploads this description to the master server.</span></span>  
  
4.  <span data-ttu-id="beaa1-136">Dans la page **Infos d'identification de connexion du serveur maître** , créez une nouvelle connexion sur le serveur cible, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="beaa1-136">From the **Master Server Login Credentials** page, create a new login on the target server, if necessary.</span></span>  
  
     <span data-ttu-id="beaa1-137">**Créer une nouvelle connexion si nécessaire et lui attribuer des droits sur le serveur MSX**</span><span class="sxs-lookup"><span data-stu-id="beaa1-137">**Create a new login if necessary and assign it rights to the MSX**</span></span>  
     <span data-ttu-id="beaa1-138">Créez une nouvelle connexion sur le serveur cible si la connexion spécifiée n'existe pas encore.</span><span class="sxs-lookup"><span data-stu-id="beaa1-138">Create a new login on the target server if the login specified does not already exist.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="beaa1-139">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="beaa1-139">Using Transact-SQL</span></span>  
  
#### <a name="to-make-a-target-server"></a><span data-ttu-id="beaa1-140">Pour créer un serveur cible</span><span class="sxs-lookup"><span data-stu-id="beaa1-140">To make a target server</span></span>  
  
1.  <span data-ttu-id="beaa1-141">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="beaa1-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="beaa1-142">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="beaa1-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="beaa1-143">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="beaa1-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="beaa1-144">Cet exemple inscrit le serveur actuel dans le serveur maître AdventureWorks1.</span><span class="sxs-lookup"><span data-stu-id="beaa1-144">This example enlists the current server into the AdventureWorks1 master server.</span></span> <span data-ttu-id="beaa1-145">L'emplacement du serveur actuel est Building 21, Room 309, Rack 5.</span><span class="sxs-lookup"><span data-stu-id="beaa1-145">The location for the current server is Building 21, Room 309, Rack 5.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_msx_enlist N'AdventureWorks1',   
        N'Building 21, Room 309, Rack 5' ;   
    GO;  
    ```  
  
     <span data-ttu-id="beaa1-146">Pour plus d’informations, consultez [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="beaa1-146">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects-smo"></a><a name="PowerShellProcedure"></a><span data-ttu-id="beaa1-147">Utilisation de SQL Server Management Objects (SMO)</span><span class="sxs-lookup"><span data-stu-id="beaa1-147">Using SQL Server Management Objects (SMO)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beaa1-148"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="beaa1-148">See Also</span></span>  
 [<span data-ttu-id="beaa1-149">Administration automatisée à l'échelle d'une entreprise</span><span class="sxs-lookup"><span data-stu-id="beaa1-149">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
