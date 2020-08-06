---
title: Supprimer des fichiers de données ou des fichiers journaux d’une base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], files
- deleting files
- removing files
- removing data
- data deletions [SQL Server]
- file deletion [SQL Server]
- deleting data
ms.assetid: 0db4018c-ce2c-4ba1-bb29-1e4f3791c925
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6f7bd170e085e9bc94b00446545850e905efaa34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709556"
---
# <a name="delete-data-or-log-files-from-a-database"></a><span data-ttu-id="12dc5-102">Supprimer des fichiers de données ou des fichiers journaux d'une base de données</span><span class="sxs-lookup"><span data-stu-id="12dc5-102">Delete Data or Log Files from a Database</span></span>
  <span data-ttu-id="12dc5-103">Cette rubrique explique comment supprimer des données ou des fichiers journaux dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12dc5-103">This topic describes how to delete data or log files in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="12dc5-104">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="12dc5-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="12dc5-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="12dc5-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="12dc5-106">Un fichier doit être vide avant de pouvoir être supprimé.</span><span class="sxs-lookup"><span data-stu-id="12dc5-106">A file must be empty before it can be deleted.</span></span> <span data-ttu-id="12dc5-107">Pour plus d’informations, consultez [Réduire un fichier](shrink-a-file.md).</span><span class="sxs-lookup"><span data-stu-id="12dc5-107">For more information, see [Shrink a File](shrink-a-file.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="12dc5-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="12dc5-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="12dc5-109">Autorisations</span><span class="sxs-lookup"><span data-stu-id="12dc5-109">Permissions</span></span>  
 <span data-ttu-id="12dc5-110">Nécessite l'autorisation ALTER sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="12dc5-110">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="12dc5-111">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="12dc5-111">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-data-or-log-files-from-a-database"></a><span data-ttu-id="12dc5-112">Pour supprimer des fichiers de données ou des fichiers journaux d'une base de données</span><span class="sxs-lookup"><span data-stu-id="12dc5-112">To delete data or log files from a database</span></span>  
  
1.  <span data-ttu-id="12dc5-113">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="12dc5-113">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="12dc5-114">Développez le dossier **Bases de données**, cliquez avec le bouton droit sur la base de données de laquelle vous souhaitez supprimer le fichier, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="12dc5-114">Expand **Databases**, right-click the database from which to delete the file, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="12dc5-115">Sélectionnez la page **Fichiers** .</span><span class="sxs-lookup"><span data-stu-id="12dc5-115">Select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="12dc5-116">Dans la grille **Fichiers de la base de données** , sélectionnez le fichier à supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="12dc5-116">In the **Database files** grid, select the file to delete and then click **Remove**.</span></span>  
  
5.  <span data-ttu-id="12dc5-117">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="12dc5-117">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="12dc5-118">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="12dc5-118">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-data-or-log-files-from-a-database"></a><span data-ttu-id="12dc5-119">Pour supprimer des fichiers de données ou des fichiers journaux d'une base de données</span><span class="sxs-lookup"><span data-stu-id="12dc5-119">To delete data or log files from a database</span></span>  
  
1.  <span data-ttu-id="12dc5-120">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12dc5-120">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="12dc5-121">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="12dc5-121">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="12dc5-122">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="12dc5-122">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="12dc5-123">Cet exemple supprime le fichier `test1dat4`.</span><span class="sxs-lookup"><span data-stu-id="12dc5-123">This example removes the file `test1dat4`.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase4](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase4)]  
  
 <span data-ttu-id="12dc5-124">Pour plus d’exemples, consultez [Options de fichiers et de groupes de fichiers ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span><span class="sxs-lookup"><span data-stu-id="12dc5-124">For more examples, see [ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12dc5-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="12dc5-125">See Also</span></span>  
 <span data-ttu-id="12dc5-126">[Réduire une base de données](shrink-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="12dc5-126">[Shrink a Database](shrink-a-database.md) </span></span>  
 [<span data-ttu-id="12dc5-127">Ajouter des fichiers de données ou journaux à une base de données</span><span class="sxs-lookup"><span data-stu-id="12dc5-127">Add Data or Log Files to a Database</span></span>](add-data-or-log-files-to-a-database.md)  
  
  
