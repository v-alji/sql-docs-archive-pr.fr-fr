---
title: Démarrer ou arrêter un jeu d’éléments de collecte | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- collection sets [SQL Server], stopping
- collection sets [SQL Server], starting
ms.assetid: 48a7b2fe-6bc3-4278-a7ec-1babc1290345
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e37d4b2edcd7a6e048c405b072bcbf9b1fef78c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612975"
---
# <a name="start-or-stop-a-collection-set"></a><span data-ttu-id="2ac63-102">Démarrer ou arrêter un jeu d'éléments de collecte</span><span class="sxs-lookup"><span data-stu-id="2ac63-102">Start or Stop a Collection Set</span></span>
  <span data-ttu-id="2ac63-103">Cette rubrique explique comment démarrer ou arrêter un jeu d'éléments de collecte dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ac63-103">This topic describes how to start or stop a collection set in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2ac63-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="2ac63-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2ac63-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="2ac63-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2ac63-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="2ac63-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="2ac63-107">Prérequis</span><span class="sxs-lookup"><span data-stu-id="2ac63-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="2ac63-108">Recommandations</span><span class="sxs-lookup"><span data-stu-id="2ac63-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="2ac63-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2ac63-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2ac63-110">**Pour démarrer ou arrêter un jeu d'éléments de collecte, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="2ac63-110">**To start or stop a collection set, using:**</span></span>  
  
     [<span data-ttu-id="2ac63-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2ac63-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2ac63-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2ac63-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2ac63-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="2ac63-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="2ac63-114">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="2ac63-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="2ac63-115">Les procédures stockées et les affichages catalogue du collecteur de données sont stockés dans la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="2ac63-115">Data Collector stored procedures and catalog views are stored in the **msdb** database.</span></span>  
  
-   <span data-ttu-id="2ac63-116">Contrairement aux procédures stockées standard, les procédures stockées du collecteur de données utilisent des paramètres de type strict qui ne prennent pas en charge la conversion automatique de type de données.</span><span class="sxs-lookup"><span data-stu-id="2ac63-116">Unlike regular stored procedures, the parameters for data collector stored procedures are strictly typed and do not support automatic data type conversion.</span></span> <span data-ttu-id="2ac63-117">Si ces paramètres ne sont pas appelés à l'aide des types de données appropriés pour les paramètres d'entrée tels qu'ils sont spécifiés dans la description de l'argument, la procédure stockée retourne une erreur.</span><span class="sxs-lookup"><span data-stu-id="2ac63-117">If these parameters are not called with the correct input parameter data types, as specified in the argument description, the stored procedure returns an error.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="2ac63-118">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="2ac63-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="2ac63-119">L'Agent SQL Server doit être démarré.</span><span class="sxs-lookup"><span data-stu-id="2ac63-119">SQL Server Agent must be started.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="2ac63-120">Recommandations</span><span class="sxs-lookup"><span data-stu-id="2ac63-120">Recommendations</span></span>  
  
-   <span data-ttu-id="2ac63-121">Pour obtenir des informations sur les jeux d’éléments de collecte, interrogez l’affichage catalogue [syscollector_collection_sets](/sql/relational-databases/system-catalog-views/syscollector-collection-sets-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="2ac63-121">To obtain information about collection sets, query the [syscollector_collection_sets](/sql/relational-databases/system-catalog-views/syscollector-collection-sets-transact-sql) catalog view.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2ac63-122">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2ac63-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2ac63-123">Autorisations</span><span class="sxs-lookup"><span data-stu-id="2ac63-123">Permissions</span></span>  
 <span data-ttu-id="2ac63-124">Nécessite l’appartenance au rôle de base de données fixe **dc_operator** .</span><span class="sxs-lookup"><span data-stu-id="2ac63-124">Requires membership in the **dc_operator** fixed database role.</span></span> <span data-ttu-id="2ac63-125">Si le jeu d'éléments de collecte n'a pas de compte proxy, l'appartenance au rôle serveur fixe **sysadmin** est requise. Exemples</span><span class="sxs-lookup"><span data-stu-id="2ac63-125">If the collection set does not have a proxy account, membership in the **sysadmin** fixed server role is required.Examples</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2ac63-126">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2ac63-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-start-a-collection-set"></a><span data-ttu-id="2ac63-127">Pour démarrer un jeu d'éléments de collecte</span><span class="sxs-lookup"><span data-stu-id="2ac63-127">To start a collection set</span></span>  
  
1.  <span data-ttu-id="2ac63-128">Dans l'Explorateur d'objets, développez le nœud **Gestion** et développez **Collecte de données**, puis **Jeux d'éléments de collecte de données système**.</span><span class="sxs-lookup"><span data-stu-id="2ac63-128">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="2ac63-129">Cliquez avec le bouton droit sur le jeu d’éléments de collecte à démarrer, puis cliquez sur **Démarrer le jeu d’éléments de collecte de données**.</span><span class="sxs-lookup"><span data-stu-id="2ac63-129">Right-click the collection set that you want to start, and then click **Start Data Collection Set**.</span></span>  
  
     <span data-ttu-id="2ac63-130">Une zone de message affiche les résultats de cette action et une flèche verte sur l'icône du jeu d'éléments de collecte indique que celui-ci a démarré.</span><span class="sxs-lookup"><span data-stu-id="2ac63-130">A message box displays the results of this action, and a green arrow on the icon for the collection set indicates that the collection set has started.</span></span>  
  
#### <a name="to-stop-a-collection-set"></a><span data-ttu-id="2ac63-131">Pour arrêter un jeu d'éléments de collecte</span><span class="sxs-lookup"><span data-stu-id="2ac63-131">To stop a collection set</span></span>  
  
1.  <span data-ttu-id="2ac63-132">Dans l'Explorateur d'objets, développez le nœud **Gestion** et développez **Collecte de données**, puis **Jeux d'éléments de collecte de données système**.</span><span class="sxs-lookup"><span data-stu-id="2ac63-132">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="2ac63-133">Cliquez avec le bouton droit sur le jeu d’éléments de collecte à arrêter, puis cliquez sur **Arrêter le jeu d’éléments de collecte de données**.</span><span class="sxs-lookup"><span data-stu-id="2ac63-133">Right-click the collection set that you want to stop, and then click **Stop Data Collection Set**.</span></span>  
  
     <span data-ttu-id="2ac63-134">Une zone de message affiche les résultats de cette action et un cercle rouge sur l'icône du jeu d'éléments de collecte indique que celui-ci s'est arrêté.</span><span class="sxs-lookup"><span data-stu-id="2ac63-134">A message box displays the results of this action, and a red circle on the icon for the collection set indicates that the collection set has stopped.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2ac63-135">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2ac63-135">Using Transact-SQL</span></span>  
  
#### <a name="to-start-a-collection-set"></a><span data-ttu-id="2ac63-136">Pour démarrer un jeu d'éléments de collecte</span><span class="sxs-lookup"><span data-stu-id="2ac63-136">To start a collection set</span></span>  
  
1.  <span data-ttu-id="2ac63-137">Connectez-vous au [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ac63-137">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2ac63-138">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="2ac63-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2ac63-139">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="2ac63-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="2ac63-140">Cet exemple utilise [sp_syscollector_start_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-start-collection-set-transact-sql) pour démarrer le jeu d’éléments de collecte présentant l’ID `1`.</span><span class="sxs-lookup"><span data-stu-id="2ac63-140">This example uses [sp_syscollector_start_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-start-collection-set-transact-sql) to start the collection set that has the ID of `1`.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC sp_syscollector_start_collection_set @collection_set_id = 1;  
```  
  
#### <a name="to-stop-a-collection-set"></a><span data-ttu-id="2ac63-141">Pour arrêter un jeu d'éléments de collecte</span><span class="sxs-lookup"><span data-stu-id="2ac63-141">To stop a collection set</span></span>  
  
1.  <span data-ttu-id="2ac63-142">Connectez-vous au [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ac63-142">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2ac63-143">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="2ac63-143">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2ac63-144">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="2ac63-144">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="2ac63-145">Cet exemple utilise [sp_syscollector_stop_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-stop-collection-set-transact-sql) pour arrêter le jeu d’éléments de collecte présentant l’ID `1`.</span><span class="sxs-lookup"><span data-stu-id="2ac63-145">This example uses [sp_syscollector_stop_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-stop-collection-set-transact-sql) to stop the collection set that has the ID of `1`.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC sp_syscollector_stop_collection_set @collection_set_id = 1;  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ac63-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2ac63-146">See Also</span></span>  
 <span data-ttu-id="2ac63-147">[Vues du collecteur de données &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/data-collector-views-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2ac63-147">[Data Collector Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/data-collector-views-transact-sql) </span></span>  
 [<span data-ttu-id="2ac63-148">Collecte de données</span><span class="sxs-lookup"><span data-stu-id="2ac63-148">Data Collection</span></span>](data-collection.md)  
  
  
