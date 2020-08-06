---
title: Détacher une base de données | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.detachdatabase.f1
helpviewer_keywords:
- database detaching [SQL Server]
- detaching databases [SQL Server]
ms.assetid: f63d4107-13e4-4bfe-922d-5e4f712e472d
author: stevestein
ms.author: sstein
ms.openlocfilehash: b8acc809b881012d18f78995bb8e521337fb02ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614623"
---
# <a name="detach-a-database"></a><span data-ttu-id="9b0de-102">Détacher une base de données</span><span class="sxs-lookup"><span data-stu-id="9b0de-102">Detach a Database</span></span>
  <span data-ttu-id="9b0de-103">Cette rubrique explique comment détacher une base de données dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b0de-103">This topic describes how to detach a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="9b0de-104">Les fichiers détachés restent et peuvent être rattachés à l'aide de CREATE DATABASE avec l'option FOR ATTACH ou FOR ATTACH_REBUILD_LOG.</span><span class="sxs-lookup"><span data-stu-id="9b0de-104">The detached files remain and can be reattached by using CREATE DATABASE with the FOR ATTACH or FOR ATTACH_REBUILD_LOG option.</span></span> <span data-ttu-id="9b0de-105">Vous pouvez les déplacer sur un autre serveur et les y attacher.</span><span class="sxs-lookup"><span data-stu-id="9b0de-105">The files can be moved to another server and attached there.</span></span>  
  
 <span data-ttu-id="9b0de-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="9b0de-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9b0de-107">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="9b0de-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9b0de-108">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="9b0de-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="9b0de-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="9b0de-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9b0de-110">**Pour détacher une base de données, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="9b0de-110">**To detach a database, using:**</span></span>  
  
     [<span data-ttu-id="9b0de-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9b0de-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9b0de-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9b0de-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9b0de-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="9b0de-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9b0de-114">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="9b0de-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="9b0de-115">Pour obtenir la liste des limitations et restrictions, consultez [Attacher et détacher une base de données &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9b0de-115">For a list of limitations and restrictions, see [Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9b0de-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="9b0de-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9b0de-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="9b0de-117">Permissions</span></span>  
 <span data-ttu-id="9b0de-118">Nécessite l'appartenance au rôle de base de données fixe db_owner.</span><span class="sxs-lookup"><span data-stu-id="9b0de-118">Requires membership in the db_owner fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9b0de-119">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9b0de-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-detach-a-database"></a><span data-ttu-id="9b0de-120">Pour détacher une base de données</span><span class="sxs-lookup"><span data-stu-id="9b0de-120">To detach a database</span></span>  
  
1.  <span data-ttu-id="9b0de-121">Dans l'Explorateur d'objets de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , connectez-vous à une instance de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] et développez cette dernière.</span><span class="sxs-lookup"><span data-stu-id="9b0de-121">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, connect to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand the instance.</span></span>  
  
2.  <span data-ttu-id="9b0de-122">Développez **Bases de données**, puis sélectionnez le nom de la base de données utilisateur que vous souhaitez détacher.</span><span class="sxs-lookup"><span data-stu-id="9b0de-122">Expand **Databases**, and select the name of the user database you want to detach.</span></span>  
  
3.  <span data-ttu-id="9b0de-123">Cliquez avec le bouton droit sur le nom de la base de données, pointez sur **Tâches**, puis cliquez sur **Détacher**.</span><span class="sxs-lookup"><span data-stu-id="9b0de-123">Right-click the database name, point to **Tasks**, and then click **Detach**.</span></span> <span data-ttu-id="9b0de-124">La boîte de dialogue **Détacher la base de données** apparaît.</span><span class="sxs-lookup"><span data-stu-id="9b0de-124">The **Detach Database** dialog box appears.</span></span>  
  
     <span data-ttu-id="9b0de-125">**Bases de données à détacher**</span><span class="sxs-lookup"><span data-stu-id="9b0de-125">**Databases to detach**</span></span>  
     <span data-ttu-id="9b0de-126">Répertorie les bases de données à détacher.</span><span class="sxs-lookup"><span data-stu-id="9b0de-126">Lists the databases to detach.</span></span>  
  
     <span data-ttu-id="9b0de-127">**Database Name**</span><span class="sxs-lookup"><span data-stu-id="9b0de-127">**Database Name**</span></span>  
     <span data-ttu-id="9b0de-128">Spécifie le nom de la base de données à détacher.</span><span class="sxs-lookup"><span data-stu-id="9b0de-128">Displays the name of the database to be detached.</span></span>  
  
     <span data-ttu-id="9b0de-129">**Supprimer les connexions**</span><span class="sxs-lookup"><span data-stu-id="9b0de-129">**Drop Connections**</span></span>  
     <span data-ttu-id="9b0de-130">Permet de déconnecter les connexions à la base de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="9b0de-130">Disconnect connections to the specified database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9b0de-131">Vous ne pouvez pas détacher une base de données avec des connexions actives.</span><span class="sxs-lookup"><span data-stu-id="9b0de-131">You cannot detach a database with active connections.</span></span>  
  
     <span data-ttu-id="9b0de-132">**Mettre à jour les statistiques**</span><span class="sxs-lookup"><span data-stu-id="9b0de-132">**Update Statistics**</span></span>  
     <span data-ttu-id="9b0de-133">Par défaut, l'opération de détachement conserve toutes les statistiques d'optimisation obsolètes avant de procéder au détachement ; pour actualiser les statistiques existantes, activez cette case à cocher.</span><span class="sxs-lookup"><span data-stu-id="9b0de-133">By default, the detach operation retains any out-of-date optimization statistics when detaching the database; to update the existing optimization statistics, click this check box.</span></span>  
  
     <span data-ttu-id="9b0de-134">**Conserver les catalogues de texte intégral**</span><span class="sxs-lookup"><span data-stu-id="9b0de-134">**Keep Full-Text Catalogs**</span></span>  
     <span data-ttu-id="9b0de-135">Par défaut, l'opération de détachement conserve tous les catalogues de texte intégral associés à la base de données.</span><span class="sxs-lookup"><span data-stu-id="9b0de-135">By default, the detach operation keeps any full-text catalogs that are associated with the database.</span></span> <span data-ttu-id="9b0de-136">Pour les supprimer, décochez la case **Conserver les catalogues de texte intégral** .</span><span class="sxs-lookup"><span data-stu-id="9b0de-136">To remove them, clear the **Keep Full-Text Catalogs** check box.</span></span> <span data-ttu-id="9b0de-137">Cette option s'affiche uniquement lors de la mise à niveau d'une base de données à partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b0de-137">This option appears only when you are upgrading a database from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
     <span data-ttu-id="9b0de-138">**État**</span><span class="sxs-lookup"><span data-stu-id="9b0de-138">**Status**</span></span>  
     <span data-ttu-id="9b0de-139">Affiche un des états suivants : **Prêt** ou **Non prêt**.</span><span class="sxs-lookup"><span data-stu-id="9b0de-139">Displays one of the following states: **Ready** or **Not ready**.</span></span>  
  
     <span data-ttu-id="9b0de-140">**Message**</span><span class="sxs-lookup"><span data-stu-id="9b0de-140">**Message**</span></span>  
     <span data-ttu-id="9b0de-141">La colonne **Message** peut indiquer des informations sur la base de données, comme suit :</span><span class="sxs-lookup"><span data-stu-id="9b0de-141">The **Message** column may display information about the database, as follows:</span></span>  
  
    -   <span data-ttu-id="9b0de-142">Lorsqu'une base de données est impliquée dans la réplication, l' **État** est **Non prêt** et la colonne **Message** indique **Base de données répliquée**.</span><span class="sxs-lookup"><span data-stu-id="9b0de-142">When a database is involved with replication, the **Status** is **Not ready** and the **Message** column displays **Database replicated**.</span></span>  
  
    -   <span data-ttu-id="9b0de-143">Quand une base de données a une ou plusieurs connexions actives, l’**État** est **Non prêt** et la colonne **Message** indique _<nombre_de_connexions_actives>_ **Connexion(s) active(s)**  ; par exemple : **1 connexion(s) active(s)** .</span><span class="sxs-lookup"><span data-stu-id="9b0de-143">When a database has one or more active connections, the **Status** is **Not ready** and the **Message** column displays _<number_of_active_connections>_**Active connection(s)** - for example: **1 Active connection(s)**.</span></span> <span data-ttu-id="9b0de-144">Avant de détacher la base de données, vous devez déconnecter toutes les connexions actives en cliquant sur **Supprimer les connexions**.</span><span class="sxs-lookup"><span data-stu-id="9b0de-144">Before you can detach the database, you need to disconnect any active connections by selecting **Drop Connections**.</span></span>  
  
     <span data-ttu-id="9b0de-145">Pour obtenir plus d'informations sur un message, cliquez sur le texte du lien hypertexte pour ouvrir le Moniteur d'activité.</span><span class="sxs-lookup"><span data-stu-id="9b0de-145">To obtain more information about a message, click the hyperlinked text to open Activity Monitor.</span></span>  
  
4.  <span data-ttu-id="9b0de-146">Lorsque vous avez prêt à lancer le processus, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b0de-146">When you are ready to detach the database, click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b0de-147">La base de données ainsi détachée reste toujours visible dans le nœud **Bases de données** de l'explorateur d'objets jusqu'à ce que la vue soit actualisée.</span><span class="sxs-lookup"><span data-stu-id="9b0de-147">The newly detached database will remain visible in the **Databases** node of Object Explorer until the view is refreshed.</span></span> <span data-ttu-id="9b0de-148">Vous pouvez le faire à tout moment en cliquant dans le volet de l’Explorateur d’objets et en sélectionnant, dans la barre de menus, les éléments **Affichage**, puis **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="9b0de-148">You can refresh the view at any time: Click in the Object Explorer pane, and from the menu bar select **View** and then **Refresh**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9b0de-149">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9b0de-149">Using Transact-SQL</span></span>  
  
#### <a name="to-detach-a-database"></a><span data-ttu-id="9b0de-150">Pour détacher une base de données</span><span class="sxs-lookup"><span data-stu-id="9b0de-150">To detach a database</span></span>  
  
1.  <span data-ttu-id="9b0de-151">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b0de-151">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9b0de-152">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="9b0de-152">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9b0de-153">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="9b0de-153">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="9b0de-154">Cet exemple détache la base de données AdventureWorks2012 avec l'option skipchecks définie sur la valeur True.</span><span class="sxs-lookup"><span data-stu-id="9b0de-154">This example detaches the AdventureWorks2012 database with skipchecks set to true.</span></span>  
  
```  
EXEC sp_detach_db 'AdventureWorks2012', 'true';  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b0de-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9b0de-155">See Also</span></span>  
 <span data-ttu-id="9b0de-156">[Attacher et détacher une base de données &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9b0de-156">[Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span></span>  
 [<span data-ttu-id="9b0de-157">sp_detach_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9b0de-157">sp_detach_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql)  
  
  
