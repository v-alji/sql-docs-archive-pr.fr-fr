---
title: Créer un serveur maître | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.msxwiz.complete.f1
- sql12.ag.msxwiz.target.f1
- sql12.ag.msxwiz.login.f1
- sql12.ag.msxwiz.cover.f1
- sql12.ag.msxwiz.operator.f1
helpviewer_keywords:
- master servers [SQL Server], creating
- wizards [SQL Server Management Studio], Master Server Wizard
- SQL Server Agent jobs, master servers
- Master Server Wizard
ms.assetid: 05739a73-1fdf-4d9d-92a6-70f328380322
author: stevestein
ms.author: sstein
ms.openlocfilehash: ce8e7428aaf8ba459bcf6831988c61da3f192bac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604806"
---
# <a name="make-a-master-server"></a><span data-ttu-id="ccbc1-102">Créer un serveur maître</span><span class="sxs-lookup"><span data-stu-id="ccbc1-102">Make a Master Server</span></span>
  <span data-ttu-id="ccbc1-103">Cette rubrique décrit comment définir un serveur maître [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccbc1-103">This topic describes how to make a master server [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ccbc1-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="ccbc1-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ccbc1-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="ccbc1-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ccbc1-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ccbc1-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ccbc1-107">**Pour créer un serveur maître à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="ccbc1-107">**To make a master server, using:**</span></span>  
  
     [<span data-ttu-id="ccbc1-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ccbc1-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ccbc1-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ccbc1-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ccbc1-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="ccbc1-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ccbc1-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ccbc1-111">Security</span></span>  
 <span data-ttu-id="ccbc1-112">Les travaux distribués dont les étapes sont associées à un proxy sont exécutés dans le contexte du compte proxy du serveur cible.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-112">Distributed jobs that have steps which are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="ccbc1-113">Assurez-vous que les conditions suivantes sont remplies ou que les étapes de travail associées à un proxy ne seront pas téléchargées du serveur maître vers la cible :</span><span class="sxs-lookup"><span data-stu-id="ccbc1-113">Make sure that the following conditions are met or job steps that are associated with a proxy will not be downloaded from the master server to the target:</span></span>  
  
-   <span data-ttu-id="ccbc1-114">La sous-clé de Registre du serveur maître **\ HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Microsoft SQL Server \\ < *instance_name*> \SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) a la valeur 1 (true).</span><span class="sxs-lookup"><span data-stu-id="ccbc1-114">The master server registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<*instance_name*>\SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) is set to 1 (true).</span></span> <span data-ttu-id="ccbc1-115">Par défaut, la valeur de cette sous-clé est 0 (False).</span><span class="sxs-lookup"><span data-stu-id="ccbc1-115">By default, this subkey is set to 0 (false).</span></span>  
  
-   <span data-ttu-id="ccbc1-116">Il existe sur le serveur cible un compte proxy possédant le même nom que le compte proxy du serveur maître sur lequel l'étape du travail est exécutée.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-116">A proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
 <span data-ttu-id="ccbc1-117">Si les étapes du travail utilisant des comptes proxy échouent pendant leur téléchargement à partir du serveur maître vers le serveur cible, vous pouvez vérifier la colonne **error_message** dans la table **sysdownloadlist** de la base de données **msdb** pour les messages d’erreur suivants :</span><span class="sxs-lookup"><span data-stu-id="ccbc1-117">If job steps that use proxy accounts fail when downloading them from the master server to the target server, you can check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="ccbc1-118">« L'étape du travail nécessite un compte proxy, cependant la mise en correspondance de proxy est désactivée sur le serveur cible. »</span><span class="sxs-lookup"><span data-stu-id="ccbc1-118">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span>  
  
     <span data-ttu-id="ccbc1-119">Pour corriger ce problème, affectez à la sous-clé de Registre **AllowDownloadedJobsToMatchProxyName** la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-119">To resolve this error, set the **AllowDownloadedJobsToMatchProxyName** registry subkey to 1.</span></span>  
  
-   <span data-ttu-id="ccbc1-120">« Proxy introuvable. »</span><span class="sxs-lookup"><span data-stu-id="ccbc1-120">"Proxy not found."</span></span>  
  
     <span data-ttu-id="ccbc1-121">Pour résoudre ce problème, vérifiez qu'un compte proxy portant le même nom que le compte proxy du serveur maître sous lequel l'étape s'exécute existe sur le serveur cible.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-121">To resolve this error, make sure a proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ccbc1-122">Autorisations</span><span class="sxs-lookup"><span data-stu-id="ccbc1-122">Permissions</span></span>  
 <span data-ttu-id="ccbc1-123">Les autorisations d'exécution de cette procédure sont octroyées par défaut aux membres du rôle serveur fixe `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-123">Permissions to execute this procedure default to members of the `sysadmin` fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ccbc1-124">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ccbc1-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-make-a-master-server"></a><span data-ttu-id="ccbc1-125">Pour créer un serveur maître</span><span class="sxs-lookup"><span data-stu-id="ccbc1-125">To make a master server</span></span>  
  
1.  <span data-ttu-id="ccbc1-126">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-126">In **Object Explorer,** connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="ccbc1-127">Cliquez avec le bouton droit sur **Agent SQL Server**, pointez sur **Administration multiserveur**, puis cliquez sur **Transformer en serveur maître**.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-127">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Make this a Master**.</span></span> <span data-ttu-id="ccbc1-128">L' **Assistant Serveur maître** vous guide au sein du processus de définition d'un serveur maître et d'ajout de serveurs cibles.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-128">The **Master Server Wizard** guides you through the process of making a master server and adding target servers.</span></span>  
  
3.  <span data-ttu-id="ccbc1-129">Dans la page **Opérateur de serveur maître** , configurez un opérateur pour le serveur maître. Pour envoyer des notifications par e-mail ou par récepteur de radiomessagerie aux opérateurs, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent doit être configuré pour l’envoi d’e-mail.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-129">From the **Master Server Operator** page, configure an operator for the master server To send notifications to operators by using e-mail or pagers, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to send e-mail.</span></span> <span data-ttu-id="ccbc1-130">Pour envoyer des notifications aux opérateurs au moyen de **net send**, le service Messenger doit s’exécuter sur le serveur où réside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-130">To send notifications to operators by using **net send**, the Messenger service must be running on the server where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent resides.</span></span>  
  
     <span data-ttu-id="ccbc1-131">**Adresse de messagerie**</span><span class="sxs-lookup"><span data-stu-id="ccbc1-131">**E-mail address**</span></span>  
     <span data-ttu-id="ccbc1-132">Permet de spécifier l'adresse de messagerie de l'opérateur.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-132">Sets the e-mail address for the operator.</span></span>  
  
     <span data-ttu-id="ccbc1-133">**Adresse de radiomessagerie**</span><span class="sxs-lookup"><span data-stu-id="ccbc1-133">**Pager address**</span></span>  
     <span data-ttu-id="ccbc1-134">Permet de spécifier l'adresse de radiomessagerie de l'opérateur.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-134">Sets the pager e-mail address for the operator.</span></span>  
  
     <span data-ttu-id="ccbc1-135">**Adresse d'envoi réseau**</span><span class="sxs-lookup"><span data-stu-id="ccbc1-135">**Net send address**</span></span>  
     <span data-ttu-id="ccbc1-136">Permet de spécifier l’adresse **net send** de l’opérateur.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-136">Sets the **net send** address for the operator.</span></span>  
  
4.  <span data-ttu-id="ccbc1-137">Dans la page **Serveur cible** , sélectionnez les serveurs cibles pour le serveur maître.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-137">From the **Target Server** page, select target servers for the master server.</span></span>  
  
     <span data-ttu-id="ccbc1-138">**Serveurs inscrits**</span><span class="sxs-lookup"><span data-stu-id="ccbc1-138">**Registered Servers**</span></span>  
     <span data-ttu-id="ccbc1-139">Répertorie les serveurs inscrits dans Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] qui ne sont pas déjà des serveurs cibles.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-139">Lists the servers registered in Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] that are not already target servers.</span></span>  
  
     <span data-ttu-id="ccbc1-140">**Serveurs cibles**</span><span class="sxs-lookup"><span data-stu-id="ccbc1-140">**Target Servers**</span></span>  
     <span data-ttu-id="ccbc1-141">Répertorie les serveurs qui sont des serveurs cibles.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-141">Lists the servers that are target servers.</span></span>  
  
     **>**  
     <span data-ttu-id="ccbc1-142">Déplace le serveur sélectionné vers la liste des serveurs cibles.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-142">Move the selected server to the target server list.</span></span>  
  
     **>>**  
     <span data-ttu-id="ccbc1-143">Déplace tous les serveurs vers la liste des serveurs cibles.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-143">Move all servers to the target server list.</span></span>  
  
     **<**  
     <span data-ttu-id="ccbc1-144">Supprime le serveur sélectionné de la liste des serveurs cibles.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-144">Remove the selected server from the target server list.</span></span>  
  
     **<<**  
     <span data-ttu-id="ccbc1-145">Supprime tous les serveurs de la liste des serveurs cibles.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-145">Remove all servers from the target server list.</span></span>  
  
     <span data-ttu-id="ccbc1-146">**Ajouter une connexion**</span><span class="sxs-lookup"><span data-stu-id="ccbc1-146">**Add connection**</span></span>  
     <span data-ttu-id="ccbc1-147">Ajoute un serveur à la liste des serveurs cibles sans inscrire le serveur.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-147">Add a server to the target server list without registering the server.</span></span>  
  
     <span data-ttu-id="ccbc1-148">**Connection**</span><span class="sxs-lookup"><span data-stu-id="ccbc1-148">**Connection**</span></span>  
     <span data-ttu-id="ccbc1-149">Modifie les propriétés de connexion du serveur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-149">Change the connection properties for the selected server.</span></span>  
  
5.  <span data-ttu-id="ccbc1-150">Dans la page **Infos d'identification de connexion du serveur maître** , spécifiez si vous souhaitez créer une connexion pour le serveur cible, le cas échéant, et lui attribuer des droits sur le serveur maître.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-150">From the **Master Server Login Credentials** page to specify if you want to create a new login for the target server, if necessary, and assign it rights to the master server.</span></span>  
  
     <span data-ttu-id="ccbc1-151">**Créer une nouvelle connexion si nécessaire et lui attribuer des droits sur le serveur MSX**</span><span class="sxs-lookup"><span data-stu-id="ccbc1-151">**Create a new login if necessary and assign it rights to the MSX**</span></span>  
     <span data-ttu-id="ccbc1-152">Créez une nouvelle connexion sur le serveur cible si la connexion spécifiée n'existe pas encore.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-152">Create a new login on the target server if the login specified does not already exist.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ccbc1-153">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ccbc1-153">Using Transact-SQL</span></span>  
  
#### <a name="to-make-a-master-server"></a><span data-ttu-id="ccbc1-154">Pour créer un serveur maître</span><span class="sxs-lookup"><span data-stu-id="ccbc1-154">To make a master server</span></span>  
  
1.  <span data-ttu-id="ccbc1-155">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccbc1-155">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ccbc1-156">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-156">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ccbc1-157">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-157">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="ccbc1-158">Cet exemple inscrit le serveur actuel dans le serveur maître AdventureWorks1.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-158">This example enlists the current server into the AdventureWorks1 master server.</span></span> <span data-ttu-id="ccbc1-159">L'emplacement du serveur actuel est Building 21, Room 309, Rack 5.</span><span class="sxs-lookup"><span data-stu-id="ccbc1-159">The location for the current server is Building 21, Room 309, Rack 5.</span></span>  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_msx_enlist N'AdventureWorks1',   
    N'Building 21, Room 309, Rack 5' ;   
GO;  
```  
  
 <span data-ttu-id="ccbc1-160">Pour plus d’informations, consultez [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ccbc1-160">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccbc1-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ccbc1-161">See Also</span></span>  
 <span data-ttu-id="ccbc1-162">[Créer un environnement multiserveur](create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="ccbc1-162">[Create a Multiserver Environment](create-a-multiserver-environment.md) </span></span>  
 [<span data-ttu-id="ccbc1-163">Administration automatisée à l'échelle d'une entreprise</span><span class="sxs-lookup"><span data-stu-id="ccbc1-163">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
  
  
