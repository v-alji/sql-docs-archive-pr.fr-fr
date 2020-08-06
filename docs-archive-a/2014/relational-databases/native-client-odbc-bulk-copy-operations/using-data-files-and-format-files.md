---
title: Utilisation de fichiers de données et de fichiers de format | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC], file formats
- ODBC, functions
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [SQL Server Native Client]
- ODBC, bulk copy operations
- bulk copy [ODBC], data files
ms.assetid: c01b7155-3f0a-473d-90b7-87a97bc56ca5
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e0ee92f79e2c8cab9605db0188e01898df8c23e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709388"
---
# <a name="using-data-files-and-format-files"></a><span data-ttu-id="79c0b-102">Utilisation de fichiers de données et de format</span><span class="sxs-lookup"><span data-stu-id="79c0b-102">Using Data Files and Format Files</span></span>
  <span data-ttu-id="79c0b-103">Le programme de copie en bloc le plus simple permet d'effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="79c0b-103">The simplest bulk copy program does the following:</span></span>  
  
1.  <span data-ttu-id="79c0b-104">Appelle [bcp_init](../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) pour spécifier la copie en bloc (Set BCP_OUT) à partir d’une table ou d’une vue vers un fichier de données.</span><span class="sxs-lookup"><span data-stu-id="79c0b-104">Calls [bcp_init](../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) to specify bulk copying out (set BCP_OUT) from a table or view to a data file.</span></span>  
  
2.  <span data-ttu-id="79c0b-105">Appelle [bcp_exec](../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) pour exécuter l’opération de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="79c0b-105">Calls [bcp_exec](../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) to execute the bulk copy operation.</span></span>  
  
 <span data-ttu-id="79c0b-106">Le fichier de données est créé en mode natif ; les données de toutes les colonnes dans une table ou une vue sont stockées dans le fichier de données sous le même format que celui de la base de données.</span><span class="sxs-lookup"><span data-stu-id="79c0b-106">The data file is created in native mode; therefore, data from all columns in the table or view are stored in the data file in the same format as in the database.</span></span> <span data-ttu-id="79c0b-107">Le fichier peut ensuite être copié en bloc vers un serveur en suivant la même procédure et en définissant DB_IN au lieu de DB_OUT.</span><span class="sxs-lookup"><span data-stu-id="79c0b-107">The file can then be bulk copied into a server by using these same steps and setting DB_IN instead of DB_OUT.</span></span> <span data-ttu-id="79c0b-108">Cela ne fonctionne que si les tables source et cible ont exactement la même structure.</span><span class="sxs-lookup"><span data-stu-id="79c0b-108">This works only if both the source and target tables have exactly the same structure.</span></span> <span data-ttu-id="79c0b-109">Le fichier de données résultant peut également être entré dans l’utilitaire **BCP** à l’aide du commutateur **/n** (mode natif).</span><span class="sxs-lookup"><span data-stu-id="79c0b-109">The resulting data file can also be input to the **bcp** utility by using the **/n** (native mode) switch.</span></span>  
  
 <span data-ttu-id="79c0b-110">Pour copier en bloc le jeu de résultats d'une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] plutôt que directement depuis une table ou une vue :</span><span class="sxs-lookup"><span data-stu-id="79c0b-110">To bulk copy out the result set of a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement instead of directly from a table or view:</span></span>  
  
1.  <span data-ttu-id="79c0b-111">Appelez **bcp_init** pour spécifier la copie en bloc, mais spécifiez NULL pour le nom de la table.</span><span class="sxs-lookup"><span data-stu-id="79c0b-111">Call **bcp_init** to specify bulk copying out, but specify NULL for the table name.</span></span>  
  
2.  <span data-ttu-id="79c0b-112">Appelez [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) avec *EOPTION* défini sur valeur BCPHINTS et *iValue* défini sur un pointeur vers une chaîne SQLTCHAR contenant l’instruction Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="79c0b-112">Call [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) with *eOption* set to BCPHINTS and *iValue* set to a pointer to a SQLTCHAR string containing the Transact-SQL statement.</span></span>  
  
3.  <span data-ttu-id="79c0b-113">Appelez **bcp_exec** pour exécuter l’opération de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="79c0b-113">Call **bcp_exec** to execute the bulk copy operation.</span></span>  
  
 <span data-ttu-id="79c0b-114">L'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] peut être n'importe quelle instruction qui génère un jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="79c0b-114">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statement can be any statement that generates a result set.</span></span> <span data-ttu-id="79c0b-115">Le fichier de données contenant le premier jeu de résultats de l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] est créé.</span><span class="sxs-lookup"><span data-stu-id="79c0b-115">The data file is created containing the first result set of the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="79c0b-116">La copie en bloc ignore tous les jeux de résultats après le premier si l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] génère plusieurs jeux de résultats.</span><span class="sxs-lookup"><span data-stu-id="79c0b-116">Bulk copy ignores any result set after the first if the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement generates multiple result sets.</span></span>  
  
 <span data-ttu-id="79c0b-117">Pour créer un fichier de données dans lequel les données de la colonne sont stockées dans un format différent de celui de la table, appelez [bcp_columns](../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md) pour spécifier le nombre de colonnes qui seront modifiées, puis appelez [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md) pour chaque colonne dont vous souhaitez modifier le format.</span><span class="sxs-lookup"><span data-stu-id="79c0b-117">To create a data file in which column data is stored in a different format than in the table, call [bcp_columns](../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md) to specify how many columns will be changed, then call [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md) for each column whose format you want to change.</span></span> <span data-ttu-id="79c0b-118">Cette opération est effectuée après l’appel de **bcp_init** mais avant l’appel de **bcp_exec**.</span><span class="sxs-lookup"><span data-stu-id="79c0b-118">This is done after calling **bcp_init** but before calling **bcp_exec**.</span></span> <span data-ttu-id="79c0b-119">**bcp_colfmt** spécifie le format dans lequel les données de la colonne sont stockées dans le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="79c0b-119">**bcp_colfmt** specifies the format in which the column's data is stored in the data file.</span></span> <span data-ttu-id="79c0b-120">Il peut être utilisé lors de la copie en bloc dans ou vers l’extérieur. Vous pouvez également utiliser **bcp_colfmt** pour définir les indicateurs de fin de ligne et de colonne.</span><span class="sxs-lookup"><span data-stu-id="79c0b-120">It can be used when bulk copying in or out. You can also use **bcp_colfmt** to set the row and column terminators.</span></span> <span data-ttu-id="79c0b-121">Par exemple, si vos données ne contiennent pas de caractères de tabulation, vous pouvez créer un fichier délimité par des tabulations à l’aide de **bcp_colfmt** pour définir la tabulation comme marque de fin de chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="79c0b-121">For example, if your data contains no tab characters, you can create a tab-delimited file by using **bcp_colfmt** to set the tab character as the terminator for each column.</span></span>  
  
 <span data-ttu-id="79c0b-122">Lors de la copie en bloc à partir de **bcp_colfmt**, vous pouvez facilement créer un fichier de format décrivant le fichier de données que vous avez créé en appelant [bcp_writefmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-writefmt.md) après le dernier appel à **bcp_colfmt**.</span><span class="sxs-lookup"><span data-stu-id="79c0b-122">When bulk copying out and using **bcp_colfmt**, you can easily create a format file describing the data file you have created by calling [bcp_writefmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-writefmt.md) after the last call to **bcp_colfmt**.</span></span>  
  
 <span data-ttu-id="79c0b-123">Lors d’une copie en bloc à partir d’un fichier de données décrit par un fichier de format, lisez le fichier de format en appelant [bcp_readfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) après **bcp_init** mais avant d' **bcp_exec**.</span><span class="sxs-lookup"><span data-stu-id="79c0b-123">When bulk copying in from a data file described by a format file, read the format file by calling [bcp_readfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) after **bcp_init** but before **bcp_exec**.</span></span>  
  
 <span data-ttu-id="79c0b-124">La fonction **bcp_control** contrôle plusieurs options lors de la copie en bloc dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à partir d’un fichier de données.</span><span class="sxs-lookup"><span data-stu-id="79c0b-124">The **bcp_control** function controls several options when bulk copying into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a data file.</span></span> <span data-ttu-id="79c0b-125">**bcp_control** définit des options, telles que le nombre maximal d’erreurs avant l’arrêt, la ligne du fichier sur laquelle démarrer la copie en bloc, la ligne sur laquelle s’arrêter et la taille du lot.</span><span class="sxs-lookup"><span data-stu-id="79c0b-125">**bcp_control** sets options, such as the maximum number of errors before termination, the row in the file on which to start the bulk copy, the row to stop on, and the batch size.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79c0b-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="79c0b-126">See Also</span></span>  
 [<span data-ttu-id="79c0b-127">Exécution d’opérations de copie en bloc &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="79c0b-127">Performing Bulk Copy Operations &#40;ODBC&#41;</span></span>](performing-bulk-copy-operations-odbc.md)  
  
  
