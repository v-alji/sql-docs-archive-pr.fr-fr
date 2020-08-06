---
title: Configurer l’option de configuration de serveur two digit year cutoff | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- two digit year cutoff option
- four-digit years [SQL Server]
ms.assetid: d94e81b6-f2e6-47ef-b497-ec3d827a1646
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c31c1d87c8b743132dd90d495f73ef711dc1f813
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603615"
---
# <a name="configure-the-two-digit-year-cutoff-server-configuration-option"></a><span data-ttu-id="75160-102">Configurer l'option de configuration de serveur two digit year cutoff</span><span class="sxs-lookup"><span data-stu-id="75160-102">Configure the two digit year cutoff Server Configuration Option</span></span>
  <span data-ttu-id="75160-103">Cette rubrique explique comment configurer l'option de configuration de serveur **two digit year cutoff** dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75160-103">This topic describes how to configure the **two digit year cutoff** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="75160-104">L’option **two digit year cutoff** spécifie un entier compris entre 1753 et 9999 qui représente l’année de troncature permettant d’interpréter les années sur deux chiffres comme des années sur quatre chiffres.</span><span class="sxs-lookup"><span data-stu-id="75160-104">The **two digit year cutoff** option specifies an integer from 1753 to 9999 that represents the cutoff year for interpreting two-digit years as four-digit years.</span></span> <span data-ttu-id="75160-105">L'intervalle de temps par défaut pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est 1950-2049, qui correspond à 2049 comme année de troncature.</span><span class="sxs-lookup"><span data-stu-id="75160-105">The default time span for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is 1950-2049, which represents a cutoff year of 2049.</span></span> <span data-ttu-id="75160-106">Cela signifie que l'année 49 est interprétée par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] comme étant 2 049, et l'année 50 comme étant 1 950. L'année 99 est interprétée comme étant 1 999.</span><span class="sxs-lookup"><span data-stu-id="75160-106">This means that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interprets a two-digit year of 49 as 2049, a two-digit year of 50 as 1950, and a two-digit year of 99 as 1999.</span></span> <span data-ttu-id="75160-107">Pour maintenir une compatibilité ascendante, laissez ce paramètre avec sa valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="75160-107">To maintain backward compatibility, leave the setting at the default value.</span></span>  
  
 <span data-ttu-id="75160-108">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="75160-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="75160-109">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="75160-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="75160-110">Recommandations</span><span class="sxs-lookup"><span data-stu-id="75160-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="75160-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="75160-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="75160-112">**Pour configurer l'option two digit year cutoff, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="75160-112">**To configure the two digit year cutoff option, using:**</span></span>  
  
     [<span data-ttu-id="75160-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="75160-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="75160-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="75160-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="75160-115">**Suivi :**  [Après avoir configuré l’option two digit year cutoff](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="75160-115">**Follow Up:**  [After you configure the two digit year cutoff option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="75160-116">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="75160-116">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="75160-117">Recommandations</span><span class="sxs-lookup"><span data-stu-id="75160-117">Recommendations</span></span>  
  
-   <span data-ttu-id="75160-118">Cette option avancée ne doit être modifiée que par un administrateur de base de données qualifié ou un technicien agréé [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="75160-118">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="75160-119">Les objets OLE Automation utilisent 2030 comme année de coupure à deux chiffres.</span><span class="sxs-lookup"><span data-stu-id="75160-119">OLE Automation objects use 2030 as the two-digit cutoff year.</span></span> <span data-ttu-id="75160-120">Vous pouvez utiliser l'option **Année de coupure à deux chiffres** pour assurer la cohérence des dates entre [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et les applications clientes.</span><span class="sxs-lookup"><span data-stu-id="75160-120">You can use the **two digit year cutoff** option to provide consistency in date values between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and client applications.</span></span> <span data-ttu-id="75160-121">Cependant, pour éviter toute ambiguïté sur les dates, utilisez des années sur quatre chiffres dans vos données.</span><span class="sxs-lookup"><span data-stu-id="75160-121">However, to avoid ambiguity with dates, use four-digit years in your data.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="75160-122">Sécurité</span><span class="sxs-lookup"><span data-stu-id="75160-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="75160-123">Autorisations</span><span class="sxs-lookup"><span data-stu-id="75160-123">Permissions</span></span>  
 <span data-ttu-id="75160-124">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="75160-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="75160-125">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="75160-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="75160-126">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="75160-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="75160-127">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="75160-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-two-digit-year-cutoff-option"></a><span data-ttu-id="75160-128">Pour configurer l'option two digit year cutoff</span><span class="sxs-lookup"><span data-stu-id="75160-128">To configure the two digit year cutoff option</span></span>  
  
1.  <span data-ttu-id="75160-129">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="75160-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="75160-130">Cliquez sur le nœud **Paramètres divers du serveur** .</span><span class="sxs-lookup"><span data-stu-id="75160-130">Click the **Misc server settings** node.</span></span>  
  
3.  <span data-ttu-id="75160-131">Sous **Prise en charge de l'année (à deux chiffres)** , dans la zone **Lors de l'entrée d'une année sur deux chiffres**, **l'interpréter comme une année entre** , entrez ou sélectionnez une valeur correspondant à la dernière année de la période.</span><span class="sxs-lookup"><span data-stu-id="75160-131">Under **Two digit year support**, in the **When a two digit year is entered**, **interpret it as a year between** box, type or select a value that is the ending year of the time span.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="75160-132">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="75160-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-two-digit-year-cutoff-option"></a><span data-ttu-id="75160-133">Pour configurer l'option two digit year cutoff</span><span class="sxs-lookup"><span data-stu-id="75160-133">To configure the two digit year cutoff option</span></span>  
  
1.  <span data-ttu-id="75160-134">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75160-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="75160-135">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="75160-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="75160-136">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="75160-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="75160-137">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `two digit year cutoff` la valeur `2030`.</span><span class="sxs-lookup"><span data-stu-id="75160-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `two digit year cutoff` option to `2030`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'two digit year cutoff', 2030 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="75160-138">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="75160-138">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-two-digit-year-cutoff-option"></a><a name="FollowUp"></a> <span data-ttu-id="75160-139">Suivi : Après avoir configuré l’option two digit year cutoff</span><span class="sxs-lookup"><span data-stu-id="75160-139">Follow Up: After you configure the two digit year cutoff option</span></span>  
 <span data-ttu-id="75160-140">Le paramètre prend effet immédiatement sans redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="75160-140">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75160-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="75160-141">See Also</span></span>  
 <span data-ttu-id="75160-142">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="75160-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="75160-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="75160-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="75160-144">RECONFIGURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="75160-144">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  
