---
title: Ajouter des fichiers de données ou des fichiers journaux à une base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], files
- adding data files
- adding files
- adding log files
- file additions [SQL Server], steps
- files [SQL Server], adding
- data additions [SQL Server]
ms.assetid: 8ead516a-1334-4f40-84b2-509d0a8ffa45
author: stevestein
ms.author: sstein
ms.openlocfilehash: f72e00f9dab422652237b4b85579c544d0cda9fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709599"
---
# <a name="add-data-or-log-files-to-a-database"></a><span data-ttu-id="488f7-102">Ajouter des fichiers de données ou journaux à une base de données</span><span class="sxs-lookup"><span data-stu-id="488f7-102">Add Data or Log Files to a Database</span></span>
  <span data-ttu-id="488f7-103">Cette rubrique explique comment ajouter des fichiers de données ou des fichiers journaux à une base de données dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="488f7-103">This topic describes how to add data or log files to a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="488f7-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="488f7-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="488f7-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="488f7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="488f7-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="488f7-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="488f7-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="488f7-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="488f7-108">**Pour ajouter des fichiers de données ou des fichiers journaux à une base de données, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="488f7-108">**To add data or log files to a database, using:**</span></span>  
  
     [<span data-ttu-id="488f7-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="488f7-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="488f7-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="488f7-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="488f7-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="488f7-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="488f7-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="488f7-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="488f7-113">Vous ne pouvez pas ajouter ou supprimer de fichier tant qu'une instruction BACKUP est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="488f7-113">You cannot add or remove a file while a BACKUP statement is running.</span></span>  
  
-   <span data-ttu-id="488f7-114">Un maximum de 32 767 fichiers et 32 767 groupes de fichiers peut être spécifié pour chaque base de données.</span><span class="sxs-lookup"><span data-stu-id="488f7-114">A maximum of 32,767 files and 32,767 filegroups can be specified for each database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="488f7-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="488f7-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="488f7-116">Autorisations</span><span class="sxs-lookup"><span data-stu-id="488f7-116">Permissions</span></span>  
 <span data-ttu-id="488f7-117">Nécessite l'autorisation ALTER sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="488f7-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="488f7-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="488f7-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-data-or-log-files-to-a-database"></a><span data-ttu-id="488f7-119">Pour ajouter des fichiers de données ou journaux à une base de données</span><span class="sxs-lookup"><span data-stu-id="488f7-119">To add data or log files to a database</span></span>  
  
1.  <span data-ttu-id="488f7-120">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="488f7-120">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="488f7-121">Développez **Bases de données**, cliquez avec le bouton droit sur la base de données d’où viennent les fichiers à ajouter, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="488f7-121">Expand **Databases**, right-click the database from which to add the files, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="488f7-122">Dans la boîte de dialogue **Propriétés de la base de données** , sélectionnez la page **Fichiers** .</span><span class="sxs-lookup"><span data-stu-id="488f7-122">In the **Database Properties** dialog box, select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="488f7-123">Pour ajouter un fichier de données ou un fichier de journal des transactions, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="488f7-123">To add a data or transaction log file, click **Add**.</span></span>  
  
5.  <span data-ttu-id="488f7-124">Dans la grille **Fichiers de la base de données** , tapez le nom logique du fichier.</span><span class="sxs-lookup"><span data-stu-id="488f7-124">In the **Database files** grid, enter a logical name for the file.</span></span> <span data-ttu-id="488f7-125">Ce nom doit être unique dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="488f7-125">The file name must be unique within the database.</span></span>  
  
6.  <span data-ttu-id="488f7-126">Sélectionnez le type de fichier : données ou journal.</span><span class="sxs-lookup"><span data-stu-id="488f7-126">Select the file type, data or log.</span></span>  
  
7.  <span data-ttu-id="488f7-127">Pour un fichier de données, sélectionnez le groupe de fichiers dans lequel le fichier doit être inclus, ou sélectionnez **\<new filegroup>** pour créer un nouveau groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="488f7-127">For a data file, select the filegroup in which the file should be included from the list, or select **\<new filegroup>** to create a new filegroup.</span></span> <span data-ttu-id="488f7-128">Les journaux des transactions ne peuvent pas être placés dans des groupes de fichiers.</span><span class="sxs-lookup"><span data-stu-id="488f7-128">Transaction logs cannot be put in filegroups.</span></span>  
  
8.  <span data-ttu-id="488f7-129">Spécifiez la taille initiale du fichier.</span><span class="sxs-lookup"><span data-stu-id="488f7-129">Specify the initial size of the file.</span></span> <span data-ttu-id="488f7-130">Attribuez aux fichiers de données un maximum d'espace en tenant compte du volume maximal de données qu'est censée contenir la base de données.</span><span class="sxs-lookup"><span data-stu-id="488f7-130">Make the data file as large as possible, based on the maximum amount of data you expect in the database.</span></span>  
  
9. <span data-ttu-id="488f7-131">Pour spécifier la manière dont la taille du fichier doit augmenter, cliquez sur ( **...** ) dans la colonne **Croissance automatique**.</span><span class="sxs-lookup"><span data-stu-id="488f7-131">To specify how the file should grow, click (**...**) in the **Autogrowth** column.</span></span> <span data-ttu-id="488f7-132">Choisissez parmi les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="488f7-132">Select from the following options:</span></span>  
  
    1.  <span data-ttu-id="488f7-133">Pour autoriser la croissance du fichier sélectionné au fur et à mesure que l'espace requis pour les données augmente, activez la case à cocher **Activer la croissance automatique** , puis sélectionnez l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="488f7-133">To allow for the currently selected file to grow as more data space is required, select the **Enable Autogrowth** check box and then select from the following options:</span></span>  
  
    2.  <span data-ttu-id="488f7-134">Pour spécifier que le fichier doit augmenter de taille par incréments fixes, cliquez sur **En mégaoctets** et spécifiez une valeur.</span><span class="sxs-lookup"><span data-stu-id="488f7-134">To specify that the file should grow by fixed increments, select **In Megabytes** and specify a value.</span></span>  
  
    3.  <span data-ttu-id="488f7-135">Pour spécifier que le fichier doit grandir d'un pourcentage de sa taille actuelle, cliquez sur **En pourcentage** et spécifiez une valeur.</span><span class="sxs-lookup"><span data-stu-id="488f7-135">To specify that the file should grow by a percentage of the current file size, select **In Percent** and specify a value.</span></span>  
  
10. <span data-ttu-id="488f7-136">Pour spécifier la taille limite du fichier, choisissez l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="488f7-136">To specify the maximum file size limit, select from the following options:</span></span>  
  
    1.  <span data-ttu-id="488f7-137">Pour spécifier la taille maximale que le fichier peut atteindre, cliquez sur **Restreindre la croissance des fichiers (Mo)** et spécifiez une valeur.</span><span class="sxs-lookup"><span data-stu-id="488f7-137">To specify the maximum size the file should be able to grow to, select **Restricted File Growth (MB)** and specify a value.</span></span>  
  
    2.  <span data-ttu-id="488f7-138">Pour permettre au fichier d'augmenter de taille en fonction des besoins, cliquez sur **Croissance des fichiers illimitée**.</span><span class="sxs-lookup"><span data-stu-id="488f7-138">To allow for the file to grow as much as needed, select **Unrestricted File Growth**.</span></span>  
  
    3.  <span data-ttu-id="488f7-139">Pour empêcher toute croissance du fichier, désactivez la case à cocher **Activer la croissance automatique** .</span><span class="sxs-lookup"><span data-stu-id="488f7-139">To prevent the file from growing, clear the **Enable Autogrowth** check box.</span></span> <span data-ttu-id="488f7-140">La taille du fichier ne dépassera jamais la valeur spécifiée dans la colonne **Taille initiale (Mo)** .</span><span class="sxs-lookup"><span data-stu-id="488f7-140">The size of the file will not grow beyond the value specified in the **Initial Size (MB)** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="488f7-141">La taille maximale de la base de données est déterminée par la quantité d'espace disponible sur le disque et par les limites de licences fixées par la version de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="488f7-141">The maximum database size is determined by the amount of disk space available and the licensing limits determined by the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you are using.</span></span>  
  
11. <span data-ttu-id="488f7-142">Spécifiez le chemin d'accès de l'emplacement du fichier.</span><span class="sxs-lookup"><span data-stu-id="488f7-142">Specify the path for the file location.</span></span> <span data-ttu-id="488f7-143">Le chemin d'accès spécifié doit exister avant l'ajout du fichier.</span><span class="sxs-lookup"><span data-stu-id="488f7-143">The specified path must exist before adding the file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="488f7-144">Par défaut, les fichiers de données et les journaux des transactions sont placés au même endroit sur le même lecteur pour des raisons de compatibilité avec les systèmes à disque unique, ce qui n'est parfois pas idéal pour les environnements de production.</span><span class="sxs-lookup"><span data-stu-id="488f7-144">By default, the data and transaction logs are put on the same drive and path to accommodate single-disk systems, but may not be optimal for production environments.</span></span> <span data-ttu-id="488f7-145">Pour plus d'informations, consultez [Database Files and Filegroups](database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="488f7-145">For more information, see [Database Files and Filegroups](database-files-and-filegroups.md).</span></span>  
  
12. <span data-ttu-id="488f7-146">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="488f7-146">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="488f7-147">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="488f7-147">Using Transact-SQL</span></span>  
  
#### <a name="to-add-data-or-log-files-to-a-database"></a><span data-ttu-id="488f7-148">Pour ajouter des fichiers de données ou journaux à une base de données</span><span class="sxs-lookup"><span data-stu-id="488f7-148">To add data or log files to a database</span></span>  
  
1.  <span data-ttu-id="488f7-149">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="488f7-149">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="488f7-150">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="488f7-150">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="488f7-151">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="488f7-151">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="488f7-152">L'exemple ajoute un groupe de deux fichiers à une base de données.</span><span class="sxs-lookup"><span data-stu-id="488f7-152">The example adds a filegroup with two files to a database.</span></span> <span data-ttu-id="488f7-153">L'exemple crée le groupe de fichiers `Test1FG1` dans la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] et ajoute deux fichiers de 5 Mo au groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="488f7-153">The example creates the filegroup `Test1FG1` in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database and adds two 5-MB files to the filegroup.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase2](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase2)]  
  
 <span data-ttu-id="488f7-154">Pour plus d’exemples, consultez [Options de fichiers et de groupes de fichiers ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span><span class="sxs-lookup"><span data-stu-id="488f7-154">For more examples, see [ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="488f7-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="488f7-155">See Also</span></span>  
 <span data-ttu-id="488f7-156">[Database Files and Filegroups](database-files-and-filegroups.md) </span><span class="sxs-lookup"><span data-stu-id="488f7-156">[Database Files and Filegroups](database-files-and-filegroups.md) </span></span>  
 <span data-ttu-id="488f7-157">[Supprimer des fichiers de données ou des fichiers journaux d'une base de données](delete-data-or-log-files-from-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="488f7-157">[Delete Data or Log Files from a Database](delete-data-or-log-files-from-a-database.md) </span></span>  
 [<span data-ttu-id="488f7-158">Augmenter la taille d’une base de données</span><span class="sxs-lookup"><span data-stu-id="488f7-158">Increase the Size of a Database</span></span>](increase-the-size-of-a-database.md)  
  
  
