---
title: Démarrer automatiquement l’Agent SQL Server (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, starting
- autostart SQL Server Agent
ms.assetid: 2ea332da-0ede-4d2b-b122-c4c10eaca191
author: stevestein
ms.author: sstein
ms.openlocfilehash: a39c7c7a112370797a965cfa601bc07f983a7a37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611497"
---
# <a name="autostart-sql-server-agent-sql-server-management-studio"></a><span data-ttu-id="f292d-102">Démarrer automatiquement SQL Server Agent (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="f292d-102">Autostart SQL Server Agent (SQL Server Management Studio)</span></span>
  <span data-ttu-id="f292d-103">Cette rubrique explique comment configurer [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] l’agent pour qu’il redémarre automatiquement s’il doit s’arrêter de façon inattendue dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f292d-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to automatically restart if it should stop unexpectedly in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="f292d-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="f292d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f292d-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="f292d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f292d-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="f292d-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f292d-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f292d-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="f292d-108">Pour configurer SQL Server Agent en vue d'un redémarrage automatique, à l'aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f292d-108">To configure SQL Server Agent to automatically restart, using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f292d-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="f292d-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f292d-110">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="f292d-110">Limitations and Restrictions</span></span>  
 <span data-ttu-id="f292d-111">Cependant, l'Explorateur d'objets affiche le nœud de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent uniquement si vous avez l'autorisation de l'utiliser.</span><span class="sxs-lookup"><span data-stu-id="f292d-111">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f292d-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f292d-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f292d-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="f292d-113">Permissions</span></span>  
 <span data-ttu-id="f292d-114">Pour exécuter ses fonctions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent doit être configuré pour utiliser les informations d'identification d'un compte qui est membre du rôle serveur fixe **sysadmin** dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f292d-114">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f292d-115">Le compte doit avoir les autorisations Windows suivantes :</span><span class="sxs-lookup"><span data-stu-id="f292d-115">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="f292d-116">Ouvrir une session en tant que service (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="f292d-116">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="f292d-117">Remplacer un jeton de niveau processus (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="f292d-117">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="f292d-118">Outrepasser le contrôle de parcours (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="f292d-118">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="f292d-119">Changer les quotas de mémoire d'un processus (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="f292d-119">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="f292d-120">Pour plus d’informations sur les autorisations Windows requises pour le compte de service de l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent, consultez [Sélectionner un compte pour le service SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) et configurer les [comptes de service Windows et les autorisations](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f292d-120">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f292d-121">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f292d-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-sql-server-agent-to-automatically-restart"></a><span data-ttu-id="f292d-122">Pour configurer SQL Server Agent en vue d'un redémarrage automatique</span><span class="sxs-lookup"><span data-stu-id="f292d-122">To configure SQL Server Agent to automatically restart</span></span>  
  
1.  <span data-ttu-id="f292d-123">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur sur lequel vous souhaitez configurer SQL Server Agent afin qu'il redémarre automatiquement.</span><span class="sxs-lookup"><span data-stu-id="f292d-123">In **Object Explorer**, click the plus sign to expand the server where you want to configure SQL Server Agent to automatically restart.</span></span>  
  
2.  <span data-ttu-id="f292d-124">Cliquez avec le bouton droit sur **SQL Server Agent**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f292d-124">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="f292d-125">Dans la page **Général** , activez la case à cocher **Redémarrage automatique de SQL Server Agent après un arrêt inattendu**.</span><span class="sxs-lookup"><span data-stu-id="f292d-125">On the **General** page, check **Auto restart SQL Server Agent if it stops unexpectedly**.</span></span>  
  
  
