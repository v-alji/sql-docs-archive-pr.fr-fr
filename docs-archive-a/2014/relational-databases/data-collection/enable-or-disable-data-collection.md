---
title: Activer ou désactiver la collecte de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collector [SQL Server], disabling
- data collector [SQL Server], enabling
ms.assetid: 0137971b-fb48-4a3e-822a-3df2b9bb09d7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: af5cc647a63d3a9451086fc9e2211dec809e88fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602154"
---
# <a name="enable-or-disable-data-collection"></a><span data-ttu-id="2c834-102">Activer ou désactiver la collecte de données</span><span class="sxs-lookup"><span data-stu-id="2c834-102">Enable or Disable Data Collection</span></span>
  <span data-ttu-id="2c834-103">Cette rubrique explique comment activer ou désactiver la collecte de données dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c834-103">This topic describes how to enable or disable data collection in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2c834-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="2c834-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2c834-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="2c834-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2c834-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2c834-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2c834-107">**Pour activer ou désactiver la collecte de données, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="2c834-107">**To enable or disable data collection, using:**</span></span>  
  
     [<span data-ttu-id="2c834-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2c834-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2c834-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2c834-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2c834-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="2c834-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2c834-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2c834-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2c834-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="2c834-112">Permissions</span></span>  
 <span data-ttu-id="2c834-113">Nécessite l’appartenance au rôle de base de données fixe **dc_admin** ou **dc_operator** (avec l’autorisation EXECUTE) pour exécuter cette procédure.</span><span class="sxs-lookup"><span data-stu-id="2c834-113">Requires membership in the **dc_admin** or **dc_operator** (with EXECUTE permission) fixed database role to execute this procedure.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2c834-114">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2c834-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enable-the-data-collector"></a><span data-ttu-id="2c834-115">Pour activer le collecteur de données</span><span class="sxs-lookup"><span data-stu-id="2c834-115">To enable the data collector</span></span>  
  
1.  <span data-ttu-id="2c834-116">Dans l'Explorateur d'objets, développez le nœud **Gestion** .</span><span class="sxs-lookup"><span data-stu-id="2c834-116">In Object Explorer, expand the **Management** node.</span></span>  
  
2.  <span data-ttu-id="2c834-117">Cliquez avec le bouton droit sur **Collecte de données**, puis cliquez sur **Activer la collecte de données**.</span><span class="sxs-lookup"><span data-stu-id="2c834-117">Right-click **Data Collection**, and then click **Enable Data Collection**.</span></span>  
  
#### <a name="to-disable-the-data-collector"></a><span data-ttu-id="2c834-118">Pour désactiver le collecteur de données</span><span class="sxs-lookup"><span data-stu-id="2c834-118">To disable the data collector</span></span>  
  
1.  <span data-ttu-id="2c834-119">Dans l'Explorateur d'objets, développez le nœud **Gestion** .</span><span class="sxs-lookup"><span data-stu-id="2c834-119">In Object Explorer, expand the **Management** node.</span></span>  
  
2.  <span data-ttu-id="2c834-120">Cliquez avec le bouton droit sur **Collecte de données**, puis sélectionnez **Désactiver la collecte de données**.</span><span class="sxs-lookup"><span data-stu-id="2c834-120">Right-click **Data Collection**, and then click **Disable Data Collection**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2c834-121">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2c834-121">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-the-data-collector"></a><span data-ttu-id="2c834-122">Pour activer le collecteur de données</span><span class="sxs-lookup"><span data-stu-id="2c834-122">To enable the data collector</span></span>  
  
1.  <span data-ttu-id="2c834-123">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c834-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2c834-124">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="2c834-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2c834-125">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="2c834-125">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="2c834-126">Cet exemple utilise [sp_syscollector_enable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) pour activer le collecteur de données.</span><span class="sxs-lookup"><span data-stu-id="2c834-126">This example uses [sp_syscollector_enable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) to enable the data collector.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC dbo.sp_syscollector_enable_collector ;  
```  
  
#### <a name="to-disable-the-data-collector"></a><span data-ttu-id="2c834-127">Pour désactiver le collecteur de données</span><span class="sxs-lookup"><span data-stu-id="2c834-127">To disable the data collector</span></span>  
  
1.  <span data-ttu-id="2c834-128">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c834-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2c834-129">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="2c834-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2c834-130">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="2c834-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="2c834-131">Cet exemple utilise [sp_syscollector_disable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) pour désactiver le collecteur de données.</span><span class="sxs-lookup"><span data-stu-id="2c834-131">This example uses [sp_syscollector_disable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) to disable the data collector.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC dbo.sp_syscollector_disable_collector;  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c834-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2c834-132">See Also</span></span>  
 <span data-ttu-id="2c834-133">[Collecte de données](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="2c834-133">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="2c834-134">Procédures stockées système &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2c834-134">System Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql)  
  
  
