---
title: Configurer l’option de configuration de serveur default full-text | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- languages [full-text search]
- default full-text language option
ms.assetid: 0fa8785b-0830-4a52-aff5-fcf8268b72fc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ec0736326a4da0708d125bfc480996d54bb86c8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601095"
---
# <a name="configure-the-default-full-text-language-server-configuration-option"></a><span data-ttu-id="d2360-102">Configurer l'option de configuration de serveur default full-text</span><span class="sxs-lookup"><span data-stu-id="d2360-102">Configure the default full-text language Server Configuration Option</span></span>
  <span data-ttu-id="d2360-103">Cette rubrique explique comment configurer l' `default full-text language` option de configuration de serveur dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d2360-103">This topic describes how to configure the `default full-text language` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="d2360-104">L' `default full-text language` option spécifie une valeur de langue par défaut pour les index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="d2360-104">The `default full-text language` option specifies a default language value for full-text indexes.</span></span> <span data-ttu-id="d2360-105">L’analyse linguistique est effectuée sur toutes les données de texte intégral indexées et elle dépend de la langue des données.</span><span class="sxs-lookup"><span data-stu-id="d2360-105">Linguistic analysis is performed on all data that is full-text indexed and is dependent on the language of the data.</span></span> <span data-ttu-id="d2360-106">La valeur par défaut de cette option est la langue du serveur.</span><span class="sxs-lookup"><span data-stu-id="d2360-106">The default value of this option is the language of the server.</span></span> <span data-ttu-id="d2360-107">Pour une version localisée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] programme d’installation de définit l' `default full-text language` option sur la langue du serveur s’il existe une correspondance appropriée.</span><span class="sxs-lookup"><span data-stu-id="d2360-107">For a localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup sets the `default full-text language` option to the language of the server if an appropriate match exists.</span></span> <span data-ttu-id="d2360-108">Pour une version non localisée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], l'anglais est la valeur affectée par défaut à l'option `default full-text language`.</span><span class="sxs-lookup"><span data-stu-id="d2360-108">For a non-localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the `default full-text language` option is English.</span></span>  
  
 <span data-ttu-id="d2360-109">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="d2360-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d2360-110">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="d2360-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d2360-111">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="d2360-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d2360-112">Recommandations</span><span class="sxs-lookup"><span data-stu-id="d2360-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="d2360-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d2360-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d2360-114">**Pour configurer l'option default full-text, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="d2360-114">**To configure the default full-text language option, using:**</span></span>  
  
     [<span data-ttu-id="d2360-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d2360-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d2360-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d2360-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="d2360-117">**Suivi :**  [Après avoir configuré l’option default full-text language](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="d2360-117">**Follow Up:**  [After you configure the default full-text language option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d2360-118">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="d2360-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d2360-119">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="d2360-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d2360-120">La valeur de l' `default full-text language` option est utilisée dans un index de recherche en texte intégral quand aucune langue n’est spécifiée pour une colonne par le biais de l’option language **language_term** dans les instructions CREATE FULLTEXT index ou ALTER FULLTEXT index.</span><span class="sxs-lookup"><span data-stu-id="d2360-120">The value of the `default full-text language` option is used in a full-text index when no language is specified for a column through the LANGUAGE **language_term** option in the CREATE FULLTEXT INDEX or ALTER FULLTEXT INDEX statements.</span></span> <span data-ttu-id="d2360-121">Si la langue de texte intégral par défaut n'est pas prise en charge ou si le package d'analyse linguistique n'est pas disponible, l'opération CREATE ou ALTER échouera et [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retournera un message d'erreur indiquant que la langue spécifiée n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="d2360-121">If the default full-text language is not supported or the linguistic analysis package is not available, the CREATE or ALTER operation will fail and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will return an error message stating that the language specified is not valid.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="d2360-122">Recommandations</span><span class="sxs-lookup"><span data-stu-id="d2360-122">Recommendations</span></span>  
  
-   <span data-ttu-id="d2360-123">Cette option avancée ne doit être modifiée que par un administrateur de base de données qualifié ou un technicien agréé [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d2360-123">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="d2360-124">L' `default full-text language` option requiert une valeur LCID.</span><span class="sxs-lookup"><span data-stu-id="d2360-124">The `default full-text language` option requires an LCID value.</span></span> <span data-ttu-id="d2360-125">Pour obtenir la liste des LCID pris en charge et des langues associées, consultez [sys.fulltext_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d2360-125">For a list of supported LCIDs and their related languages, see [sys.fulltext_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql).</span></span> <span data-ttu-id="d2360-126">D'autres langues peuvent aussi être proposées par d'autres éditeurs de logiciels.</span><span class="sxs-lookup"><span data-stu-id="d2360-126">Other languages may also be available from independent software vendors, for example.</span></span> <span data-ttu-id="d2360-127">Si aucun dialecte spécifique n'est détecté, le Moteur d'indexation et de recherche en texte intégral passe automatiquement à la langue principale.</span><span class="sxs-lookup"><span data-stu-id="d2360-127">If no specific language dialect is found, the Full-Text Engine will automatically switch to the primary language.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d2360-128">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d2360-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d2360-129">Autorisations</span><span class="sxs-lookup"><span data-stu-id="d2360-129">Permissions</span></span>  
 <span data-ttu-id="d2360-130">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d2360-130">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="d2360-131">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="d2360-131">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="d2360-132">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="d2360-132">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d2360-133">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d2360-133">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-default-full-text-language-option"></a><span data-ttu-id="d2360-134">Pour configurer l'option default full-text</span><span class="sxs-lookup"><span data-stu-id="d2360-134">To configure the default full-text language option</span></span>  
  
1.  <span data-ttu-id="d2360-135">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d2360-135">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="d2360-136">Cliquez sur le nœud **Avancé** .</span><span class="sxs-lookup"><span data-stu-id="d2360-136">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="d2360-137">Sous Divers, utilisez l’option **Langue de texte intégral par défaut** pour spécifier une valeur de langue par défaut pour les colonnes de texte intégral indexées.</span><span class="sxs-lookup"><span data-stu-id="d2360-137">Under Miscellaneous, use **Default Full Text Language** to specify a default language value for full-text indexed columns.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d2360-138">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d2360-138">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-default-full-text-language-option"></a><span data-ttu-id="d2360-139">Pour configurer l'option default full-text</span><span class="sxs-lookup"><span data-stu-id="d2360-139">To configure the default full-text language option</span></span>  
  
1.  <span data-ttu-id="d2360-140">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2360-140">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d2360-141">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="d2360-141">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d2360-142">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="d2360-142">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d2360-143">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `default full-text` la valeur Néerlandais (`1043`).</span><span class="sxs-lookup"><span data-stu-id="d2360-143">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `default full-text` option to Dutch (`1043`).</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'default full-text language', 1043 ;  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="d2360-144">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d2360-144">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-default-full-text-language-option"></a><a name="FollowUp"></a> <span data-ttu-id="d2360-145">Suivi : Après avoir configuré l’option default full-text language</span><span class="sxs-lookup"><span data-stu-id="d2360-145">Follow Up: After you configure the default full-text language option</span></span>  
 <span data-ttu-id="d2360-146">Le paramètre prend effet immédiatement sans redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="d2360-146">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2360-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d2360-147">See Also</span></span>  
 <span data-ttu-id="d2360-148">[sys.fulltext_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d2360-148">[sys.fulltext_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) </span></span>  
 <span data-ttu-id="d2360-149">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d2360-149">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="d2360-150">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d2360-150">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="d2360-151">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d2360-151">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="d2360-152">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d2360-152">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span></span>  
 [<span data-ttu-id="d2360-153">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d2360-153">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-index-transact-sql)  
  
  
