---
title: Définir une base de données en mode mono-utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- single-user mode [SQL Server], database option
ms.assetid: fb5254eb-b635-4b39-8361-136fd36f2b1f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 16281b5fa7d4f6698bb6c498915bfa84779b3e14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695695"
---
# <a name="set-a-database-to-single-user-mode"></a><span data-ttu-id="cccbe-102">Définir une base de données en mode mono-utilisateur</span><span class="sxs-lookup"><span data-stu-id="cccbe-102">Set a Database to Single-user Mode</span></span>
  <span data-ttu-id="cccbe-103">Cette rubrique explique comment configurer une base de données définie par l'utilisateur en mode mono-utilisateur dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cccbe-103">This topic describes how to set a user-defined database to single-user mode in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="cccbe-104">Le mode mono-utilisateur signifie que seul un utilisateur à la fois peut avoir accès à la base de données. Il est généralement destiné à des opérations de maintenance.</span><span class="sxs-lookup"><span data-stu-id="cccbe-104">Single-user mode specifies that only one user at a time can access the database and is generally used for maintenance actions.</span></span>  
  
 <span data-ttu-id="cccbe-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="cccbe-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="cccbe-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="cccbe-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="cccbe-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="cccbe-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="cccbe-108">Prérequis</span><span class="sxs-lookup"><span data-stu-id="cccbe-108">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="cccbe-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="cccbe-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="cccbe-110">**Pour définir une base de données en mode mono-utilisateur, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="cccbe-110">**To set a database to single-user mode, using:**</span></span>  
  
     [<span data-ttu-id="cccbe-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cccbe-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="cccbe-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cccbe-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cccbe-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="cccbe-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="cccbe-114">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="cccbe-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="cccbe-115">Si d'autres utilisateurs sont connectés à la base de données au moment où vous définissez la base de données en mode mono-utilisateur, leurs connexions à la base de données sont fermées sans avertissement.</span><span class="sxs-lookup"><span data-stu-id="cccbe-115">If other users are connected to the database at the time that you set the database to single-user mode, their connections to the database will be closed without warning.</span></span>  
  
-   <span data-ttu-id="cccbe-116">La base de données reste en mode mono-utilisateur même si l'utilisateur qui a défini l'option se déconnecte.</span><span class="sxs-lookup"><span data-stu-id="cccbe-116">The database remains in single-user mode even if the user that set the option logs off.</span></span> <span data-ttu-id="cccbe-117">À ce stade, un autre utilisateur (et un seul) peut se connecter à la base de données.</span><span class="sxs-lookup"><span data-stu-id="cccbe-117">At that point, a different user, but only one, can connect to the database.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="cccbe-118">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="cccbe-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="cccbe-119">Avant d'affecter la valeur SINGLE_USER à la base de données, vérifiez que l'option AUTO_UPDATE_STATISTICS_ASYNC a la valeur OFF.</span><span class="sxs-lookup"><span data-stu-id="cccbe-119">Before you set the database to SINGLE_USER, verify that the AUTO_UPDATE_STATISTICS_ASYNC option is set to OFF.</span></span> <span data-ttu-id="cccbe-120">Si la valeur de cette option est ON, le thread d'arrière-plan utilisé pour mettre à jour les statistiques se connecte à la base de données et vous ne pourrez pas accéder à celle-ci en mode mono-utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cccbe-120">When this option is set to ON, the background thread that is used to update statistics takes a connection against the database, and you will be unable to access the database in single-user mode.</span></span> <span data-ttu-id="cccbe-121">Pour plus d’informations, consultez [Options ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="cccbe-121">For more information, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cccbe-122">Sécurité</span><span class="sxs-lookup"><span data-stu-id="cccbe-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cccbe-123">Autorisations</span><span class="sxs-lookup"><span data-stu-id="cccbe-123">Permissions</span></span>  
 <span data-ttu-id="cccbe-124">Nécessite l'autorisation ALTER sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="cccbe-124">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cccbe-125">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cccbe-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-a-database-to-single-user-mode"></a><span data-ttu-id="cccbe-126">Pour définir une base de données en mode mono-utilisateur</span><span class="sxs-lookup"><span data-stu-id="cccbe-126">To set a database to single-user mode</span></span>  
  
1.  <span data-ttu-id="cccbe-127">Dans **l’Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], puis développez-la.</span><span class="sxs-lookup"><span data-stu-id="cccbe-127">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="cccbe-128">Cliquez avec le bouton droit sur la base de données à modifier, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="cccbe-128">Right-click the database to change, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="cccbe-129">Dans la boîte de dialogue **Propriétés de la base de données** , cliquez sur la page **Options** .</span><span class="sxs-lookup"><span data-stu-id="cccbe-129">In the **Database Properties** dialog box, click the **Options** page.</span></span>  
  
4.  <span data-ttu-id="cccbe-130">Dans l'option **Restreindre l'accès** , sélectionnez **Utilisateur unique**.</span><span class="sxs-lookup"><span data-stu-id="cccbe-130">From the **Restrict Access** option, select **Single**.</span></span>  
  
5.  <span data-ttu-id="cccbe-131">Si d'autres utilisateurs sont connectés à la base de données, un message **Ouvrir les connexions** apparaît.</span><span class="sxs-lookup"><span data-stu-id="cccbe-131">If other users are connected to the database, an **Open Connections** message will appear.</span></span> <span data-ttu-id="cccbe-132">Pour modifier la propriété et fermer toutes les autres connexions, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="cccbe-132">To change the property and close all other connections, click **Yes**.</span></span>  
  
 <span data-ttu-id="cccbe-133">Vous pouvez également définir la base de données pour un accès Multiple ou Restreint à l'aide de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="cccbe-133">You can also set the database to Multiple or Restricted access by using this procedure.</span></span> <span data-ttu-id="cccbe-134">Pour plus d’informations sur les options de restriction d’accès, consultez [Propriétés de la base de données &#40;page Options&#41;](database-properties-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="cccbe-134">For more information about the Restrict Access options, see [Database Properties &#40;Options Page&#41;](database-properties-options-page.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cccbe-135">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cccbe-135">Using Transact-SQL</span></span>  
  
#### <a name="to-set-a-database-to-single-user-mode"></a><span data-ttu-id="cccbe-136">Pour définir une base de données en mode mono-utilisateur</span><span class="sxs-lookup"><span data-stu-id="cccbe-136">To set a database to single-user mode</span></span>  
  
1.  <span data-ttu-id="cccbe-137">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cccbe-137">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cccbe-138">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="cccbe-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cccbe-139">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="cccbe-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="cccbe-140">Cet exemple attribue à la base de données la valeur `SINGLE_USER` pour obtenir l'accès exclusif.</span><span class="sxs-lookup"><span data-stu-id="cccbe-140">This example sets the database to `SINGLE_USER` mode to obtain exclusive access.</span></span> <span data-ttu-id="cccbe-141">L'exemple attribue ensuite à l'état de la base de données [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] la valeur `READ_ONLY` et octroie l'accès à la base de données à tous les utilisateurs. L'option d'arrêt `WITH ROLLBACK IMMEDIATE` est spécifiée dans la première instruction `ALTER DATABASE` .</span><span class="sxs-lookup"><span data-stu-id="cccbe-141">The example then sets the state of the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database to `READ_ONLY` and returns access to the database to all users.The termination option `WITH ROLLBACK IMMEDIATE` is specified in the first `ALTER DATABASE` statement.</span></span> <span data-ttu-id="cccbe-142">Suite à celà, toutes les transactions incomplètes sont restaurées et les autres connexions à la base de données [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] sont immédiatement déconnectées.</span><span class="sxs-lookup"><span data-stu-id="cccbe-142">This will cause all incomplete transactions to be rolled back and any other connections to the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database to be immediately disconnected.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase8](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase8)]  
  
## <a name="see-also"></a><span data-ttu-id="cccbe-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cccbe-143">See Also</span></span>  
 [<span data-ttu-id="cccbe-144">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cccbe-144">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
