---
title: Configurer l’option de configuration de serveur fill factor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- fill factor option [SQL Server]
ms.assetid: b920ec34-ba8b-4bb8-af53-a3ffd06bafa6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 02258c92b4a09277d371e605fd4729ba9fda3461
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610858"
---
# <a name="configure-the-fill-factor-server-configuration-option"></a><span data-ttu-id="d18eb-102">Configurer l'option de configuration de serveur fill factor</span><span class="sxs-lookup"><span data-stu-id="d18eb-102">Configure the fill factor Server Configuration Option</span></span>
  <span data-ttu-id="d18eb-103">Cette rubrique explique comment configurer l'option de configuration de serveur **fill factor** dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d18eb-103">This topic describes how to configure the **fill factor** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="d18eb-104">Le facteur de remplissage permet de paramétrer précisément les performances et le stockage des données d'index.</span><span class="sxs-lookup"><span data-stu-id="d18eb-104">Fill factor is provided for fine-tuning index data storage and performance.</span></span> <span data-ttu-id="d18eb-105">Lorsqu'un index est créé ou régénéré, la valeur du facteur de remplissage détermine le pourcentage d'espace sur chaque page de niveau feuille à remplir de données, réservant ainsi le reste comme espace disponible pour une croissance future.</span><span class="sxs-lookup"><span data-stu-id="d18eb-105">When an index is created or rebuilt, the fill-factor value determines the percentage of space on each leaf-level page to be filled with data, reserving the rest as free space for future growth.</span></span> <span data-ttu-id="d18eb-106">Pour plus d’informations, consultez [Spécifier un facteur de remplissage pour un index](../../relational-databases/indexes/specify-fill-factor-for-an-index.md).</span><span class="sxs-lookup"><span data-stu-id="d18eb-106">For more information, see [Specify Fill Factor for an Index](../../relational-databases/indexes/specify-fill-factor-for-an-index.md).</span></span>  
  
 <span data-ttu-id="d18eb-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="d18eb-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d18eb-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="d18eb-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d18eb-109">Recommandations</span><span class="sxs-lookup"><span data-stu-id="d18eb-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="d18eb-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d18eb-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d18eb-111">**Pour configurer l'option fill factor, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="d18eb-111">**To configure the fill factor option, using:**</span></span>  
  
     [<span data-ttu-id="d18eb-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d18eb-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d18eb-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d18eb-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="d18eb-114">**Suivi :**  [Après avoir configuré l’option fill factor](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="d18eb-114">**Follow Up:**  [After you configure the fill factor option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d18eb-115">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="d18eb-115">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="d18eb-116">Recommandations</span><span class="sxs-lookup"><span data-stu-id="d18eb-116">Recommendations</span></span>  
  
-   <span data-ttu-id="d18eb-117">Cette option avancée ne doit être modifiée que par un administrateur de base de données qualifié ou un technicien agréé [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d18eb-117">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d18eb-118">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d18eb-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d18eb-119">Autorisations</span><span class="sxs-lookup"><span data-stu-id="d18eb-119">Permissions</span></span>  
 <span data-ttu-id="d18eb-120">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d18eb-120">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="d18eb-121">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="d18eb-121">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="d18eb-122">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="d18eb-122">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d18eb-123">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d18eb-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-fill-factor-option"></a><span data-ttu-id="d18eb-124">Pour configurer l'option fill factor</span><span class="sxs-lookup"><span data-stu-id="d18eb-124">To configure the fill factor option</span></span>  
  
1.  <span data-ttu-id="d18eb-125">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d18eb-125">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="d18eb-126">Cliquez sur le nœud **Paramètres de base de données** .</span><span class="sxs-lookup"><span data-stu-id="d18eb-126">Click the **Database Settings** node.</span></span>  
  
3.  <span data-ttu-id="d18eb-127">Dans la zone **Facteur de remplissage par défaut de l'index** , tapez ou sélectionnez le facteur de remplissage d'index de votre choix.</span><span class="sxs-lookup"><span data-stu-id="d18eb-127">In the **Default index fill factor** box, type or select the index fill factor that you want.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d18eb-128">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d18eb-128">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-fill-factor-option"></a><span data-ttu-id="d18eb-129">Pour configurer l'option fill factor</span><span class="sxs-lookup"><span data-stu-id="d18eb-129">To configure the fill factor option</span></span>  
  
1.  <span data-ttu-id="d18eb-130">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d18eb-130">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d18eb-131">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="d18eb-131">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d18eb-132">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="d18eb-132">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d18eb-133">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `fill factor` la valeur `100`.</span><span class="sxs-lookup"><span data-stu-id="d18eb-133">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `fill factor` option to `100`.</span></span>  
  
```sql  
Use AdventureWorks2012;  
GO  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'fill factor', 100;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="d18eb-134">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d18eb-134">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-fill-factor-option"></a><a name="FollowUp"></a> <span data-ttu-id="d18eb-135">Suivi : Après avoir configuré l’option fill factor</span><span class="sxs-lookup"><span data-stu-id="d18eb-135">Follow Up: After you configure the fill factor option</span></span>  
 <span data-ttu-id="d18eb-136">Le serveur doit être redémarré pour que le paramètre puisse être effet.</span><span class="sxs-lookup"><span data-stu-id="d18eb-136">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d18eb-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d18eb-137">See Also</span></span>  
 <span data-ttu-id="d18eb-138">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d18eb-138">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="d18eb-139">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d18eb-139">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="d18eb-140">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d18eb-140">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="d18eb-141">[Spécifier un facteur de remplissage pour un index](../../relational-databases/indexes/specify-fill-factor-for-an-index.md) </span><span class="sxs-lookup"><span data-stu-id="d18eb-141">[Specify Fill Factor for an Index](../../relational-databases/indexes/specify-fill-factor-for-an-index.md) </span></span>  
 <span data-ttu-id="d18eb-142">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d18eb-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="d18eb-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d18eb-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="d18eb-144">sys.indexes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d18eb-144">sys.indexes &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql)  
  
  
