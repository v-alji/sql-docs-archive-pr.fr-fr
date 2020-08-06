---
title: Augmenter la taille d’une base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], size
- increasing database size
- database size [SQL Server], increasing
- size [SQL Server], databases
ms.assetid: 14f4206d-3afa-4ba9-9849-23e81d63306d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 71dcb00b3f5525f7059fc54911baed929f763008
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709548"
---
# <a name="increase-the-size-of-a-database"></a><span data-ttu-id="af4c1-102">Augmenter la taille d'une base de données</span><span class="sxs-lookup"><span data-stu-id="af4c1-102">Increase the Size of a Database</span></span>
  <span data-ttu-id="af4c1-103">Cette rubrique explique comment augmenter la taille d'une base de données dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af4c1-103">This topic describes how to increase the size of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="af4c1-104">Cette base de données peut être étendue de deux manières : en augmentant la taille d'un fichier de données ou d'un fichier journal existant ou en ajoutant un fichier à la base de données.</span><span class="sxs-lookup"><span data-stu-id="af4c1-104">The database is expanded by either increasing the size of an existing data or log file or by adding a new file to the database.</span></span>  
  
 <span data-ttu-id="af4c1-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="af4c1-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="af4c1-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="af4c1-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="af4c1-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="af4c1-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="af4c1-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="af4c1-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="af4c1-109">**Pour augmenter la taille d'une base de données, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="af4c1-109">**To increase the size of a database, using:**</span></span>  
  
     [<span data-ttu-id="af4c1-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="af4c1-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="af4c1-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="af4c1-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="af4c1-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="af4c1-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="af4c1-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="af4c1-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="af4c1-114">Vous ne pouvez pas ajouter ou supprimer de fichier tant qu'une instruction BACKUP est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="af4c1-114">You cannot add or remove a file while a BACKUP statement is running.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="af4c1-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="af4c1-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="af4c1-116">Autorisations</span><span class="sxs-lookup"><span data-stu-id="af4c1-116">Permissions</span></span>  
 <span data-ttu-id="af4c1-117">Nécessite l'autorisation ALTER sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="af4c1-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="af4c1-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="af4c1-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-increase-the-size-of-a-database"></a><span data-ttu-id="af4c1-119">Pour augmenter la taille d'une base de données</span><span class="sxs-lookup"><span data-stu-id="af4c1-119">To increase the size of a database</span></span>  
  
1.  <span data-ttu-id="af4c1-120">Dans **l’Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], puis développez-la.</span><span class="sxs-lookup"><span data-stu-id="af4c1-120">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="af4c1-121">Développez le dossier **Bases de données**, cliquez avec le bouton droit sur la base de données dont vous souhaitez augmenter la taille, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="af4c1-121">Expand **Databases**, right-click the database to increase, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="af4c1-122">Dans **Propriétés de la base de données**, sélectionnez la page **Fichiers** .</span><span class="sxs-lookup"><span data-stu-id="af4c1-122">In **Database Properties**, select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="af4c1-123">Pour augmenter la taille d’un fichier existant, entrez une valeur plus grande dans la colonne **Taille initiale (Mo)** correspondant au fichier.</span><span class="sxs-lookup"><span data-stu-id="af4c1-123">To increase the size of an existing file, increase the value in the **Initial Size (MB)** column for the file.</span></span> <span data-ttu-id="af4c1-124">Vous devez augmenter la taille de la base de données d'au moins 1 mégaoctet (Mo).</span><span class="sxs-lookup"><span data-stu-id="af4c1-124">You must increase the size of the database by at least 1 megabyte.</span></span>  
  
5.  <span data-ttu-id="af4c1-125">Pour augmenter la taille de la base de données en ajoutant un fichier, cliquez sur **Ajouter** et entrez les valeurs correspondant au nouveau fichier.</span><span class="sxs-lookup"><span data-stu-id="af4c1-125">To increase the size of the database by adding a new file, click **Add** and then enter the values for the new file.</span></span> <span data-ttu-id="af4c1-126">Pour plus d’informations, consultez [Ajouter des fichiers de données ou journaux à une base de données](add-data-or-log-files-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="af4c1-126">For more information, see [Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md).</span></span>  
  
6.  <span data-ttu-id="af4c1-127">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="af4c1-127">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="af4c1-128">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="af4c1-128">Using Transact-SQL</span></span>  
  
#### <a name="to-increase-the-size-of-a-database"></a><span data-ttu-id="af4c1-129">Pour augmenter la taille d'une base de données</span><span class="sxs-lookup"><span data-stu-id="af4c1-129">To increase the size of a database</span></span>  
  
1.  <span data-ttu-id="af4c1-130">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af4c1-130">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="af4c1-131">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="af4c1-131">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="af4c1-132">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="af4c1-132">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="af4c1-133">Cet exemple augmente la taille du fichier `test1dat3`.</span><span class="sxs-lookup"><span data-stu-id="af4c1-133">This example increases the size of the file `test1dat3`.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase5](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase5)]  
  
 <span data-ttu-id="af4c1-134">Pour plus d’exemples, consultez [Options de fichiers et de groupes de fichiers ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span><span class="sxs-lookup"><span data-stu-id="af4c1-134">For more examples, see [ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af4c1-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="af4c1-135">See Also</span></span>  
 <span data-ttu-id="af4c1-136">[Ajouter des fichiers de données ou journaux à une base de données](add-data-or-log-files-to-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="af4c1-136">[Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md) </span></span>  
 [<span data-ttu-id="af4c1-137">Réduire une base de données</span><span class="sxs-lookup"><span data-stu-id="af4c1-137">Shrink a Database</span></span>](shrink-a-database.md)  
  
  
