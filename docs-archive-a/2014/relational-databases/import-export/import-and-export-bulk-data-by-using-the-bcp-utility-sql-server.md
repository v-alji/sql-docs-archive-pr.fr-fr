---
title: Importer et exporter des données en bloc à l’aide de l’utilitaire bcp (SQL Server) | Microsoft Docs
ms.prod: sql-server-2014
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk exporting [SQL Server], bcp utility
- bulk importing [SQL Server], bcp utility
- bcp utility [SQL Server], about bcp utility
ms.assetid: 73e949de-67a3-4c84-9735-7da1ad4ba34a
author: markingmyname
ms.author: maghan
ms.reviewer: ''
ms.custom: ''
ms.date: 06/14/2017
ms.openlocfilehash: 7d1892b26f3c638a696d8ed15e739f56ac2e682f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612333"
---
# <a name="import-and-export-bulk-data-by-using-the-bcp-utility-sql-server"></a><span data-ttu-id="e254d-102">Importer et exporter des données en bloc à l'aide de l'utilitaire bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e254d-102">Import and Export Bulk Data by Using the bcp Utility (SQL Server)</span></span>

<span data-ttu-id="e254d-103">Cette rubrique est une présentation générale de l'utilisation de l' [utilitaire bcp](../../tools/bcp-utility.md) pour exporter des données à partir de n'importe quel emplacement d'une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contenant une instruction SELECT, vues partitionnées comprises.</span><span class="sxs-lookup"><span data-stu-id="e254d-103">This topic provides an overview for using the [bcp utility](../../tools/bcp-utility.md) to export data from anywhere in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database where a SELECT statement works, including partitioned views.</span></span>  
  
 <span data-ttu-id="e254d-104">L'utilitaire bcp (Bcp.exe) est un outil de ligne de commande qui fait appel à l'API BCP (Bulk Copy Program).</span><span class="sxs-lookup"><span data-stu-id="e254d-104">The bcp utility (Bcp.exe) is a command-line tool that uses the Bulk Copy Program (BCP) API.</span></span> <span data-ttu-id="e254d-105">L'utilitaire exécute les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="e254d-105">The bcp utility performs the following tasks:</span></span>  
  
-   <span data-ttu-id="e254d-106">Exportations en bloc des données à partir d'une table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans un fichier de données.</span><span class="sxs-lookup"><span data-stu-id="e254d-106">Bulk exports data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table into a data file.</span></span>  
  
-   <span data-ttu-id="e254d-107">Exportations en bloc des données à partir d'une requête.</span><span class="sxs-lookup"><span data-stu-id="e254d-107">Bulk exports data from a query.</span></span>  
  
-   <span data-ttu-id="e254d-108">Importations en bloc des données à partir d'un fichier de données dans une table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e254d-108">Bulk imports data from a data file into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
-   <span data-ttu-id="e254d-109">Génération des fichiers de format.</span><span class="sxs-lookup"><span data-stu-id="e254d-109">Generates format files.</span></span>  
  
 <span data-ttu-id="e254d-110">L’utilitaire bcp est accessible via la commande **bcp** .</span><span class="sxs-lookup"><span data-stu-id="e254d-110">The bcp utility is accessed by the **bcp** command.</span></span> <span data-ttu-id="e254d-111">Pour utiliser la commande **bcp** afin d’importer des données en bloc, vous devez comprendre le schéma de la table et les types de données de ses colonnes, à moins que vous n’utilisiez un fichier de format pré-existant.</span><span class="sxs-lookup"><span data-stu-id="e254d-111">To use the **bcp** command to bulk import data, you must understand the schema of the table and the data types of its columns, unless you are using a pre-existing format file.</span></span>  
  
 <span data-ttu-id="e254d-112">L'utilitaire bcp peut exporter des données à partir d'une table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans un fichier de données qui sera utilisé dans d'autres programmes.</span><span class="sxs-lookup"><span data-stu-id="e254d-112">The bcp utility can export data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table to a data file for use in other programs.</span></span> <span data-ttu-id="e254d-113">L'utilitaire permet également d'importer des données dans une table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à partir d'un autre programme, généralement un autre système de gestion de base de données (SGBD).</span><span class="sxs-lookup"><span data-stu-id="e254d-113">The utility can also import data into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table from another program, usually another database management system (DBMS).</span></span> <span data-ttu-id="e254d-114">Les données sont d'abord exportées à partir du programme source dans un fichier de données, puis copiées, au cours d'une opération séparée, à partir du fichier de données dans une table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e254d-114">The data is first exported from the source program to a data file and then, in a separate operation, copied from the data file into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="e254d-115">La commande **bcp** fournit des commutateurs qui vous permettent de spécifier le type de données du fichier de données ainsi que d’autres informations.</span><span class="sxs-lookup"><span data-stu-id="e254d-115">The **bcp** command provides switches that you use to specify the data type of the data file and other information.</span></span> <span data-ttu-id="e254d-116">Si ces commutateurs ne sont pas spécifiés, une commande bcp demande des informations de mise en forme, comme le type de champs de données dans un fichier de données.</span><span class="sxs-lookup"><span data-stu-id="e254d-116">If these switches are not specified, the command prompts for formatting information, such as the type of data fields in a data file.</span></span> <span data-ttu-id="e254d-117">La commande vous propose ensuite de créer un fichier de format contenant vos réponses interactives.</span><span class="sxs-lookup"><span data-stu-id="e254d-117">The command then asks whether you want to create a format file that contains your interactive responses.</span></span> <span data-ttu-id="e254d-118">Ce fichier est le plus souvent utile si vous avez besoin de flexibilité pour de futures opérations d'importation-exportation en bloc.</span><span class="sxs-lookup"><span data-stu-id="e254d-118">If you want flexibility for future bulk-import or bulk-export operations, a format file is often useful.</span></span> <span data-ttu-id="e254d-119">Vous pouvez spécifier le fichier de format lors de l’exécution ultérieure de commandes **bcp** pour des fichiers de données équivalents.</span><span class="sxs-lookup"><span data-stu-id="e254d-119">You can specify the format file on later **bcp** commands for equivalent data files.</span></span> <span data-ttu-id="e254d-120">Pour plus d’informations, consultez [Spécifier des formats de données pour la compatibilité lors de l’utilisation de bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e254d-120">For more information, see [Specify Data Formats for Compatibility when Using bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e254d-121">L'utilitaire bcp est écrit à l'aide de la copie en bloc ODBC</span><span class="sxs-lookup"><span data-stu-id="e254d-121">The bcp utility is written by using the ODBC bulk-copy</span></span>  
  
 <span data-ttu-id="e254d-122">Pour obtenir une description de la syntaxe de la commande **bcp** , consultez [bcp Utility](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="e254d-122">For a description of the **bcp** command syntax, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e254d-123">Exemples</span><span class="sxs-lookup"><span data-stu-id="e254d-123">Examples</span></span>

 <span data-ttu-id="e254d-124">Pour obtenir des exemples de commande **bcp** , consultez :</span><span class="sxs-lookup"><span data-stu-id="e254d-124">For **bcp** examples, see:</span></span>  
  
-   [<span data-ttu-id="e254d-125">Utilitaire bcp</span><span class="sxs-lookup"><span data-stu-id="e254d-125">bcp Utility</span></span>](../../tools/bcp-utility.md)  
  
-   [<span data-ttu-id="e254d-126">Créer un fichier de format &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e254d-126">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="e254d-127">Exemples d’importation et d’exportation en bloc de documents XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e254d-127">Examples of Bulk Import and Export of XML Documents &#40;SQL Server&#41;</span></span>](examples-of-bulk-import-and-export-of-xml-documents-sql-server.md)  
  
-   [<span data-ttu-id="e254d-128">Conserver des valeurs d’identité lors de l’importation de données en bloc &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e254d-128">Keep Identity Values When Bulk Importing Data &#40;SQL Server&#41;</span></span>](keep-identity-values-when-bulk-importing-data-sql-server.md)  
  
-   [<span data-ttu-id="e254d-129">Conserver les valeurs NULL ou utiliser la valeur par défaut lors de l’importation en bloc &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e254d-129">Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;</span></span>](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md)  
  
-   [<span data-ttu-id="e254d-130">Spécifier des indicateurs de fin de champ et de fin de ligne &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e254d-130">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
-   [<span data-ttu-id="e254d-131">Utiliser un fichier de format pour importer des données en bloc &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e254d-131">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="e254d-132">Utiliser le format caractère pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e254d-132">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="e254d-133">Utiliser le format natif pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e254d-133">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="e254d-134">Utiliser le format caractère Unicode pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e254d-134">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="e254d-135">Utiliser le format natif Unicode pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e254d-135">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  

## <a name="see-also"></a><span data-ttu-id="e254d-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e254d-136">See Also</span></span>

<span data-ttu-id="e254d-137">[Insérer &#40;&#41;](/sql/t-sql/statements/insert-transact-sql) 
 Transact-SQL [Clause SELECT &#40;&#41;](/sql/t-sql/queries/select-clause-transact-sql) 
 Transact-SQL [utilitaire bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="e254d-137">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql)
[SELECT Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-clause-transact-sql)
[bcp Utility](../../tools/bcp-utility.md) </span></span>  
<span data-ttu-id="e254d-138">[Préparer l’importation en bloc de données &#40;SQL Server&#41;](prepare-to-bulk-import-data-sql-server.md) 
 [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) 
 [Importation et exportation en bloc de données &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) 
 [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) 
 [Créer un fichier de Format &#40;SQL Server&#41;](create-a-format-file-sql-server.md)</span><span class="sxs-lookup"><span data-stu-id="e254d-138">[Prepare to Bulk Import Data &#40;SQL Server&#41;](prepare-to-bulk-import-data-sql-server.md)
[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql)
[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md)
[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql)
[Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md)</span></span>