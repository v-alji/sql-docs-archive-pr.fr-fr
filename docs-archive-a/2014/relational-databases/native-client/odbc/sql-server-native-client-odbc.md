---
title: SQL Server Native Client (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLNCLI, ODBC
- SQL Server Native Client ODBC driver, about SQL Server Native Client ODBC driver
- data access [SQL Server Native Client], ODBC
- SQL Server Native Client ODBC driver
- ODBC
- SQL Server Native Client, ODBC
- ODBC, about SQL Server Native Client ODBC driver
ms.assetid: 811d5ba3-a2b8-48c0-adbc-8c91f041f458
author: rothja
ms.author: jroth
ms.openlocfilehash: 16c73966e318ed1e7d326fa77f56195ebbd830df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702859"
---
# <a name="sql-server-native-client-odbc"></a><span data-ttu-id="612b8-102">SQL Server Native Client (ODBC)</span><span class="sxs-lookup"><span data-stu-id="612b8-102">SQL Server Native Client (ODBC)</span></span>
  <span data-ttu-id="612b8-103">ODBC est la définition standard d'une interface de programmation d'applications (API) utilisée pour accéder aux données des bases de données relationnelles ou à accès séquentiel indexé (Indexed Sequential Access Method).</span><span class="sxs-lookup"><span data-stu-id="612b8-103">ODBC is a standard definition of an application programming interface (API) used to access data in relational or indexed sequential access method (ISAM) databases.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="612b8-104">prend en charge ODBC, via le pilote ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, comme l'une des API natives pour écrire des applications C et C++ qui communiquent avec [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="612b8-104">supports ODBC, via the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver, as one of the native APIs for writing C and C++ applications that communicate with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="612b8-105">Les programmes [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] écrits à l'aide du pilote ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client communiquent avec [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] via les appels de fonctions C.</span><span class="sxs-lookup"><span data-stu-id="612b8-105">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] programs that are written using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver communicate with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] through C function calls.</span></span> <span data-ttu-id="612b8-106">Les versions propres à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] des fonctions ODBC sont implémentées dans le pilote ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="612b8-106">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific versions of the ODBC functions are implemented in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="612b8-107">Le pilote passe les instructions SQL à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] et retourne les résultats des instructions à l'application.</span><span class="sxs-lookup"><span data-stu-id="612b8-107">The driver passes SQL statements to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and returns the results of the statements to the application.</span></span>  
  
 <span data-ttu-id="612b8-108">Le pilote ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client est conforme à la spécification Microsoft Win32 ODBC 3.51.</span><span class="sxs-lookup"><span data-stu-id="612b8-108">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver complies with the Microsoft Win32 ODBC 3.51 specification.</span></span> <span data-ttu-id="612b8-109">Le pilote prend en charge les applications écrites à l'aide de versions antérieures d'ODBC selon la manière définie dans la spécification ODBC 3.51.</span><span class="sxs-lookup"><span data-stu-id="612b8-109">The driver supports applications written using earlier versions of ODBC in the manner defined in the ODBC 3.51 specification.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="612b8-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="612b8-110">In This Section</span></span>  
  
-   [<span data-ttu-id="612b8-111">Noms des sources de données et systèmes d'exploitation 64 bits</span><span class="sxs-lookup"><span data-stu-id="612b8-111">Data Source Names and 64-Bit Operating Systems</span></span>](data-source-names-and-64-bit-operating-systems.md)  
  
-   [<span data-ttu-id="612b8-112">Création d’une application de pilote ODBC SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="612b8-112">Creating a SQL Server Native Client ODBC Driver Application</span></span>](creating-a-driver-application.md)  
  
-   [<span data-ttu-id="612b8-113">Communication avec SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="612b8-113">Communicating with SQL Server &#40;ODBC&#41;</span></span>](../../native-client-odbc-communication/communicating-with-sql-server-odbc.md)  
  
-   [<span data-ttu-id="612b8-114">Exécution de requêtes &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="612b8-114">Executing Queries &#40;ODBC&#41;</span></span>](../../native-client-odbc-queries/executing-queries-odbc.md)  
  
-   [<span data-ttu-id="612b8-115">Traitement des résultats &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="612b8-115">Processing Results &#40;ODBC&#41;</span></span>](../../native-client-odbc-results/processing-results-odbc.md)  
  
-   [<span data-ttu-id="612b8-116">Utilisation de curseurs &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="612b8-116">Using Cursors &#40;ODBC&#41;</span></span>](../../native-client-odbc-cursors/using-cursors-odbc.md)  
  
-   [<span data-ttu-id="612b8-117">Exécution de transactions &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="612b8-117">Performing Transactions &#40;ODBC&#41;</span></span>](../../../database-engine/dev-guide/performing-transactions-odbc.md)  
  
-   [<span data-ttu-id="612b8-118">Gestion des erreurs et des messages</span><span class="sxs-lookup"><span data-stu-id="612b8-118">Handling Errors and Messages</span></span>](../../native-client-odbc-error-messages/handling-errors-and-messages.md)  
  
-   [<span data-ttu-id="612b8-119">Exécution de procédures stockées</span><span class="sxs-lookup"><span data-stu-id="612b8-119">Running Stored Procedures</span></span>](../../native-client-odbc-stored-procedures/running-stored-procedures.md)  
  
-   [<span data-ttu-id="612b8-120">Utilisation des fonctions de catalogue</span><span class="sxs-lookup"><span data-stu-id="612b8-120">Using Catalog Functions</span></span>](using-catalog-functions.md)  
  
-   [<span data-ttu-id="612b8-121">Exécution d’opérations de copie en bloc &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="612b8-121">Performing Bulk Copy Operations &#40;ODBC&#41;</span></span>](../../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md)  
  
-   [<span data-ttu-id="612b8-122">Gestion des colonnes texte et image</span><span class="sxs-lookup"><span data-stu-id="612b8-122">Managing Text and Image Columns</span></span>](../../native-client-odbc-text-image-columns/managing-text-and-image-columns.md)  
  
-   [<span data-ttu-id="612b8-123">Profilage des performances du pilote ODBC</span><span class="sxs-lookup"><span data-stu-id="612b8-123">Profiling ODBC Driver Performance</span></span>](profiling-odbc-driver-performance.md)  
  
-   [<span data-ttu-id="612b8-124">Paramètres table &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="612b8-124">Table-Valued Parameters &#40;ODBC&#41;</span></span>](../../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md)  
  
-   [<span data-ttu-id="612b8-125">Améliorations de la date et de l’heure &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="612b8-125">Date and Time Improvements &#40;ODBC&#41;</span></span>](../../native-client-odbc-date-time/date-and-time-improvements-odbc.md)  
  
-   [<span data-ttu-id="612b8-126">Types CLR volumineux définis par l’utilisateur &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="612b8-126">Large CLR User-Defined Types &#40;ODBC&#41;</span></span>](large-clr-user-defined-types-odbc.md)  
  
-   [<span data-ttu-id="612b8-127">Prise en charge de FILESTREAM &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="612b8-127">FILESTREAM Support &#40;ODBC&#41;</span></span>](filestream-support-odbc.md)  
  
-   [<span data-ttu-id="612b8-128">Noms de principaux du service &#40;noms SPN&#41; dans les connexions clientes &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="612b8-128">Service Principal Names &#40;SPNs&#41; in Client Connections &#40;ODBC&#41;</span></span>](service-principal-names-spns-in-client-connections-odbc.md)  
  
-   [<span data-ttu-id="612b8-129">Les colonnes éparses prennent en charge &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="612b8-129">Sparse Columns Support &#40;ODBC&#41;</span></span>](sparse-columns-support-odbc.md)  
  
-   [<span data-ttu-id="612b8-130">Référence de&#41; ODBC SQL Server Native Client &#40;</span><span class="sxs-lookup"><span data-stu-id="612b8-130">SQL Server Native Client &#40;ODBC&#41; Reference</span></span>](../../../database-engine/dev-guide/sql-server-native-client-odbc-reference.md)  
  
-   [<span data-ttu-id="612b8-131">Rubriques de procédures liées à ODBC</span><span class="sxs-lookup"><span data-stu-id="612b8-131">ODBC How-to Topics</span></span>](../../native-client-odbc-how-to/odbc-how-to-topics.md)  
  
## <a name="see-also"></a><span data-ttu-id="612b8-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="612b8-132">See Also</span></span>  
 <span data-ttu-id="612b8-133">[Programmation SQL Server Native Client](../sql-server-native-client-programming.md) </span><span class="sxs-lookup"><span data-stu-id="612b8-133">[SQL Server Native Client Programming](../sql-server-native-client-programming.md) </span></span>  
 [<span data-ttu-id="612b8-134">Installation de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="612b8-134">Installing SQL Server Native Client</span></span>](../applications/installing-sql-server-native-client.md)  
  
  
