---
title: Renommer un journal d’erreurs de l’Agent SQL Server (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- renaming SQL Server Agent error log
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: dee2b199-48af-44cb-9177-d029a5edb169
author: stevestein
ms.author: sstein
ms.openlocfilehash: c1c85550a29bfff316ffc275ba2d4e4df10686d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614302"
---
# <a name="rename-a-sql-server-agent-error-log-sql-server-management-studio"></a><span data-ttu-id="4fbc2-102">Rename a SQL Server Agent Error Log (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="4fbc2-102">Rename a SQL Server Agent Error Log (SQL Server Management Studio)</span></span>
  <span data-ttu-id="4fbc2-103">Cette rubrique explique comment renommer le fichier dans lequel les [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Erreurs de l’agent sont écrites à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4fbc2-103">This topic describes how to rename the file where [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent errors are written in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="4fbc2-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="4fbc2-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4fbc2-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="4fbc2-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4fbc2-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="4fbc2-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4fbc2-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="4fbc2-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="4fbc2-108">Pour renommer le journal des erreurs de l'Agent SQL Server à l'aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4fbc2-108">To rename a SQL Server Agent error log using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4fbc2-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="4fbc2-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4fbc2-110">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="4fbc2-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="4fbc2-111">Cependant, l'Explorateur d'objets affiche le nœud de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent uniquement si vous avez l'autorisation de l'utiliser.</span><span class="sxs-lookup"><span data-stu-id="4fbc2-111">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4fbc2-112">Agent n'écrira pas dans le nouveau fichier journal tant que le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent n'est pas redémarré.</span><span class="sxs-lookup"><span data-stu-id="4fbc2-112">Agent will not write to the new log file until the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is restarted.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4fbc2-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="4fbc2-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4fbc2-114">Autorisations</span><span class="sxs-lookup"><span data-stu-id="4fbc2-114">Permissions</span></span>  
 <span data-ttu-id="4fbc2-115">Pour exécuter ses fonctions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent doit être configuré pour utiliser les informations d'identification d'un compte qui est membre du rôle serveur fixe **sysadmin** dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4fbc2-115">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4fbc2-116">Le compte doit avoir les autorisations Windows suivantes :</span><span class="sxs-lookup"><span data-stu-id="4fbc2-116">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="4fbc2-117">Ouvrir une session en tant que service (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="4fbc2-117">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="4fbc2-118">Remplacer un jeton de niveau processus (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="4fbc2-118">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="4fbc2-119">Outrepasser le contrôle de parcours (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="4fbc2-119">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="4fbc2-120">Changer les quotas de mémoire d'un processus (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="4fbc2-120">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="4fbc2-121">Pour plus d’informations sur les autorisations Windows requises pour le compte de service de l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent, consultez [Sélectionner un compte pour le service SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) et configurer les [comptes de service Windows et les autorisations](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="4fbc2-121">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4fbc2-122">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4fbc2-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-sql-server-agent-error-log"></a><span data-ttu-id="4fbc2-123">Pour renommer le journal des erreurs de SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="4fbc2-123">To rename a SQL Server Agent error log</span></span>  
  
1.  <span data-ttu-id="4fbc2-124">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur qui contient le journal des erreurs de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vous souhaitez renommer.</span><span class="sxs-lookup"><span data-stu-id="4fbc2-124">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log that you want to rename.</span></span>  
  
2.  <span data-ttu-id="4fbc2-125">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="4fbc2-125">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="4fbc2-126">Cliquez avec le bouton droit sur le dossier **Journaux d’erreurs** , puis sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="4fbc2-126">Right-click the **Error Logs** folder and select **Configure**.</span></span>  
  
4.  <span data-ttu-id="4fbc2-127">Dans la boîte de dialogue **Configurer les journaux d'erreurs de l'Agent SQL Server** , dans la zone **Fichier journal des erreurs** , entrez le nouveau chemin d'accès et le nom de fichier du journal des erreurs.</span><span class="sxs-lookup"><span data-stu-id="4fbc2-127">In the **Configure SQL Server Agent Error Logs** dialog box, in the **Error log file** box, enter the new file path and file name for the error log.</span></span> <span data-ttu-id="4fbc2-128">Vous pouvez également cliquer sur les points de suspension **(...)** pour ouvrir la boîte de dialogue **Spécifier l’emplacement du journal d’erreurs de l’agent** .</span><span class="sxs-lookup"><span data-stu-id="4fbc2-128">Alternately, click the ellipsis **(...)** to open the **Specify agent error log location** dialog box.</span></span>  
  
5.  <span data-ttu-id="4fbc2-129">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4fbc2-129">When finished, click **OK**.</span></span>  
  
  
