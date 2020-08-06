---
title: Annuler l’inscription d’un serveur cible dans un serveur maître | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- target servers [SQL Server], defecting
- SQL Server Agent jobs, master servers
- master servers [SQL Server], defecting target servers
- defecting target servers
ms.assetid: a6da262b-7b38-4ce4-bfd6-6a557c6e8a84
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2b17703fa87f5c0d3e7146a1660ac1ca7c7c1d81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699239"
---
# <a name="defect-a-target-server-from-a-master-server"></a><span data-ttu-id="e6d4f-102">Annuler l'inscription d'un serveur cible dans un serveur maître</span><span class="sxs-lookup"><span data-stu-id="e6d4f-102">Defect a Target Server from a Master Server</span></span>
  <span data-ttu-id="e6d4f-103">Cette rubrique décrit comment désinscrire un serveur cible d'un serveur maître dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../includes/tsql-md.md)] ou d'objets SMO (SQL Server Management Objects).</span><span class="sxs-lookup"><span data-stu-id="e6d4f-103">This topic describes how to defect a target server from a master server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="e6d4f-104">Exécutez cette procédure à partir du serveur cible.</span><span class="sxs-lookup"><span data-stu-id="e6d4f-104">Run this procedure from the target server.</span></span>  
  
 <span data-ttu-id="e6d4f-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="e6d4f-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e6d4f-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="e6d4f-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e6d4f-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="e6d4f-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e6d4f-108">**Pour annuler l'inscription d'un serveur cible à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="e6d4f-108">**To defect a target server, using:**</span></span>  
  
     [<span data-ttu-id="e6d4f-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e6d4f-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e6d4f-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e6d4f-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="e6d4f-111">SMO</span><span class="sxs-lookup"><span data-stu-id="e6d4f-111">SMO</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e6d4f-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="e6d4f-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e6d4f-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="e6d4f-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e6d4f-114">Autorisations</span><span class="sxs-lookup"><span data-stu-id="e6d4f-114">Permissions</span></span>  
 <span data-ttu-id="e6d4f-115">Pour exécuter cette procédure stockée, l'utilisateur doit être membre du rôle de serveur fixe `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="e6d4f-115">To execute this stored procedure, a user must be a member of the `sysadmin` fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e6d4f-116">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e6d4f-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-defect-a-target-server-from-a-master-server"></a><span data-ttu-id="e6d4f-117">Pour annuler l'inscription d'un serveur cible dans un serveur maître</span><span class="sxs-lookup"><span data-stu-id="e6d4f-117">To defect a target server from a master server</span></span>  
  
1.  <span data-ttu-id="e6d4f-118">Dans l' **Explorateur d'objets**, développez un serveur qui est configuré comme serveur cible.</span><span class="sxs-lookup"><span data-stu-id="e6d4f-118">In **Object Explorer**, expand a server that is configured as a target server.</span></span>  
  
2.  <span data-ttu-id="e6d4f-119">Cliquez avec le bouton droit sur **Agent SQL Server**, pointez sur **Administration multiserveur**, puis cliquez sur **Désinscrire**.</span><span class="sxs-lookup"><span data-stu-id="e6d4f-119">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Defect**.</span></span>  
  
3.  <span data-ttu-id="e6d4f-120">Cliquez sur **Oui** pour confirmer que vous voulez désinscrire ce serveur cible d'un serveur maître.</span><span class="sxs-lookup"><span data-stu-id="e6d4f-120">Click **Yes** to confirm that you want to defect this target server from a master server.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e6d4f-121">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e6d4f-121">Using Transact-SQL</span></span>  
  
#### <a name="to-defect-a-target-server-from-a-master-server"></a><span data-ttu-id="e6d4f-122">Pour annuler l'inscription d'un serveur cible dans un serveur maître</span><span class="sxs-lookup"><span data-stu-id="e6d4f-122">To defect a target server from a master server</span></span>  
  
1.  <span data-ttu-id="e6d4f-123">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6d4f-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e6d4f-124">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="e6d4f-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e6d4f-125">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="e6d4f-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
```sql
sp_msx_defect ;  
```  
  
 <span data-ttu-id="e6d4f-126">Pour plus d’informations, consultez [sp_msx_defect &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-defect-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e6d4f-126">For more information, see [sp_msx_defect &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-defect-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects-smo"></a><a name="PowerShellProcedure"></a><span data-ttu-id="e6d4f-127">Utilisation de SQL Server Management Objects (SMO)</span><span class="sxs-lookup"><span data-stu-id="e6d4f-127">Using SQL Server Management Objects (SMO)</span></span>  
 <span data-ttu-id="e6d4f-128">Utilisez la méthode `MsxDefect Method`.</span><span class="sxs-lookup"><span data-stu-id="e6d4f-128">Use the `MsxDefect Method`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d4f-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e6d4f-129">See Also</span></span>  
 <span data-ttu-id="e6d4f-130">[Créer un environnement multiserveur](create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="e6d4f-130">[Create a Multiserver Environment](create-a-multiserver-environment.md) </span></span>  
 <span data-ttu-id="e6d4f-131">[Administration automatisée à l'échelle d'une entreprise](automated-administration-across-an-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="e6d4f-131">[Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md) </span></span>  
 [<span data-ttu-id="e6d4f-132">Annuler l’inscription de plusieurs serveurs cibles dans un serveur maître</span><span class="sxs-lookup"><span data-stu-id="e6d4f-132">Defect Multiple Target Servers from a Master Server</span></span>](defect-multiple-target-servers-from-a-master-server.md)  
