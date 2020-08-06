---
title: Utilisation des fonctions de catalogue | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, functions
- SQLLinkedCatalogs function
- SQL Server Native Client ODBC driver, catalog functions
- SQLLinkedServers function
- catalog functions [ODBC]
- functions [ODBC]
ms.assetid: 7773fb2e-06b5-4c4b-88e9-0ad9132ad273
author: rothja
ms.author: jroth
ms.openlocfilehash: 6cac35e658343f606c1953f265c752335c70d81f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613433"
---
# <a name="using-catalog-functions"></a><span data-ttu-id="9259e-102">Utilisation des fonctions de catalogue</span><span class="sxs-lookup"><span data-stu-id="9259e-102">Using Catalog Functions</span></span>
  <span data-ttu-id="9259e-103">Toutes les bases de données ont une structure contenant les données stockée dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="9259e-103">All databases have a structure containing the data stored in the database.</span></span> <span data-ttu-id="9259e-104">Une définition de cette structure, ainsi que d'autres informations comme les autorisations, est stockée dans un catalogue (implémenté comme ensemble de tables système), également appelé dictionnaire de données.</span><span class="sxs-lookup"><span data-stu-id="9259e-104">A definition of this structure, along with other information such as permissions, is stored in a catalog (implemented as a set of system tables), also known as a data dictionary.</span></span>  
  
 <span data-ttu-id="9259e-105">Le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pilote ODBC Native Client permet à une application de déterminer la structure de la base de données par le biais d’appels aux fonctions de catalogue ODBC.</span><span class="sxs-lookup"><span data-stu-id="9259e-105">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver enables an application to determine the database structure through calls to ODBC catalog functions.</span></span> <span data-ttu-id="9259e-106">Les fonctions de catalogue retournent les informations dans les jeux de résultats et sont implémentées à l'aide de procédures stockées de catalogue pour interroger les tables système du catalogue.</span><span class="sxs-lookup"><span data-stu-id="9259e-106">Catalog functions return information in result sets and are implemented using catalog stored procedures to query the system tables in the catalog.</span></span> <span data-ttu-id="9259e-107">Par exemple, une application peut demander un jeu de résultats contenant des informations sur toutes les tables du système ou sur toutes les colonnes d'une table particulière.</span><span class="sxs-lookup"><span data-stu-id="9259e-107">For example, an application might request a result set containing information about all the tables on the system or all the columns in a particular table.</span></span> <span data-ttu-id="9259e-108">Les fonctions de catalogue ODBC standard sont utilisées pour obtenir des informations de catalogue à partir du serveur [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] auquel l'application est connectée.</span><span class="sxs-lookup"><span data-stu-id="9259e-108">The standard ODBC catalog functions are used to get catalog information from the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to which the application connected.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="9259e-109">prend en charge les requêtes distribuées dans lesquelles l'accès aux données de plusieurs sources de données OLE DB hétérogènes s'effectue via une requête unique.</span><span class="sxs-lookup"><span data-stu-id="9259e-109">supports distributed queries in which data from multiple, heterogeneous OLE DB data sources is accessed in a single query.</span></span> <span data-ttu-id="9259e-110">L'une des méthodes d'accès à une source de données OLE DB distante consiste à définir la source de données comme serveur lié.</span><span class="sxs-lookup"><span data-stu-id="9259e-110">One of the methods of accessing a remote OLE DB data source is to define the data source as a linked server.</span></span> <span data-ttu-id="9259e-111">Pour ce faire, vous pouvez utiliser [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9259e-111">This can be done by using [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span></span> <span data-ttu-id="9259e-112">Une fois que le serveur lié a été défini, les objets de ce serveur peuvent être référencés dans les instructions Transact-SQL en utilisant un nom en quatre parties :</span><span class="sxs-lookup"><span data-stu-id="9259e-112">After the linked server has been defined, objects in that server can be referenced in Transact-SQL statements by using a four-part name:</span></span>  
  
 <span data-ttu-id="9259e-113">*linked_server_name. Catalog. Schema. object_name*.</span><span class="sxs-lookup"><span data-stu-id="9259e-113">*linked_server_name.catalog.schema.object_name*.</span></span>  
  
 <span data-ttu-id="9259e-114">Le pilote ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client prend en charge deux fonctions spécifiques au pilote qui aident à obtenir les informations de catalogue des serveurs liés :</span><span class="sxs-lookup"><span data-stu-id="9259e-114">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports two driver-specific functions that help get catalog information from linked servers:</span></span>  
  
-   <span data-ttu-id="9259e-115">**SQLLinkedServers**</span><span class="sxs-lookup"><span data-stu-id="9259e-115">**SQLLinkedServers**</span></span>  
  
     <span data-ttu-id="9259e-116">Retourne la liste des serveurs liés définis au serveur local.</span><span class="sxs-lookup"><span data-stu-id="9259e-116">Returns a list of the linked servers defined to the local server.</span></span>  
  
-   <span data-ttu-id="9259e-117">**SQLLinkedCatalogs**</span><span class="sxs-lookup"><span data-stu-id="9259e-117">**SQLLinkedCatalogs**</span></span>  
  
     <span data-ttu-id="9259e-118">Retourne la liste des catalogues contenus dans un serveur lié.</span><span class="sxs-lookup"><span data-stu-id="9259e-118">Returns a list of the catalogs contained in a linked server.</span></span>  
  
 <span data-ttu-id="9259e-119">Une fois que vous avez un nom de serveur lié et un nom de catalogue, le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pilote ODBC Native Client prend en charge l’obtention d’informations à partir du catalogue en utilisant un nom en deux parties de _linked_server_name_**.** _catalogue_ pour *nomcatalogue* sur les fonctions de catalogue ODBC suivantes :</span><span class="sxs-lookup"><span data-stu-id="9259e-119">After you have a linked server name and a catalog name, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports getting information from the catalog by using a two-part name of _linked_server_name_**.**_catalog_ for *CatalogName* on the following ODBC catalog functions:</span></span>  
  
-   <span data-ttu-id="9259e-120">**SQLColumnPrivileges**</span><span class="sxs-lookup"><span data-stu-id="9259e-120">**SQLColumnPrivileges**</span></span>  
  
-   <span data-ttu-id="9259e-121">**SQLColumns**</span><span class="sxs-lookup"><span data-stu-id="9259e-121">**SQLColumns**</span></span>  
  
-   <span data-ttu-id="9259e-122">**SQLPrimaryKeys**</span><span class="sxs-lookup"><span data-stu-id="9259e-122">**SQLPrimaryKeys**</span></span>  
  
-   <span data-ttu-id="9259e-123">**SQLStatistics**</span><span class="sxs-lookup"><span data-stu-id="9259e-123">**SQLStatistics**</span></span>  
  
-   <span data-ttu-id="9259e-124">**SQLTablePrivileges**</span><span class="sxs-lookup"><span data-stu-id="9259e-124">**SQLTablePrivileges**</span></span>  
  
-   <span data-ttu-id="9259e-125">**SQLTables**</span><span class="sxs-lookup"><span data-stu-id="9259e-125">**SQLTables**</span></span>  
  
 <span data-ttu-id="9259e-126">Linked_server_name en deux parties _linked_server_name_**.** le _catalogue_ est également pris en charge pour *FKCatalogName* et *PKCatalogName* sur [SQLForeignKeys](../../native-client-odbc-api/sqlforeignkeys.md).</span><span class="sxs-lookup"><span data-stu-id="9259e-126">The two-part _linked_server_name_**.**_catalog_ is also supported for *FKCatalogName* and *PKCatalogName* on [SQLForeignKeys](../../native-client-odbc-api/sqlforeignkeys.md).</span></span>  
  
 <span data-ttu-id="9259e-127">L'utilisation de SQLLinkedServers et SQLLinkedCatalogs requiert les fichiers suivants :</span><span class="sxs-lookup"><span data-stu-id="9259e-127">Using SQLLinkedServers and SQLLinkedCatalogs requires the following files:</span></span>  
  
-   <span data-ttu-id="9259e-128">sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="9259e-128">sqlncli.h</span></span>  
  
     <span data-ttu-id="9259e-129">Inclut les prototypes de fonctions et les définitions de constantes pour les fonctions de catalogue du serveur lié.</span><span class="sxs-lookup"><span data-stu-id="9259e-129">Includes function prototypes and constant definitions for the linked server catalog functions.</span></span> <span data-ttu-id="9259e-130">sqlncli.h doit être inclus dans l'application ODBC, ainsi que dans le chemin d'accès Include lorsque l'application est compilée.</span><span class="sxs-lookup"><span data-stu-id="9259e-130">sqlncli.h must be included in the ODBC application and must be in the include path when the application is compiled.</span></span>  
  
-   <span data-ttu-id="9259e-131">sqlncli11.lib</span><span class="sxs-lookup"><span data-stu-id="9259e-131">sqlncli11.lib</span></span>  
  
     <span data-ttu-id="9259e-132">Doit être dans le chemin d'accès de la bibliothèque de l'éditeur de liens et spécifié comme fichier à lier.</span><span class="sxs-lookup"><span data-stu-id="9259e-132">Must be in the library path of the linker and specified as a file to be linked.</span></span> <span data-ttu-id="9259e-133">sqlncli11.lib est distribué avec le pilote ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="9259e-133">sqlncli11.lib is distributed with the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
-   <span data-ttu-id="9259e-134">sqlncli11.dll</span><span class="sxs-lookup"><span data-stu-id="9259e-134">sqlncli11.dll</span></span>  
  
     <span data-ttu-id="9259e-135">Doit être présent lors de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="9259e-135">Must be present at execution time.</span></span> <span data-ttu-id="9259e-136">sqlncli11.dll est distribué avec le pilote ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="9259e-136">sqlncli11.dll is distributed with the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9259e-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9259e-137">See Also</span></span>  
 <span data-ttu-id="9259e-138">[SQL Server Native Client &#40;&#41;ODBC](sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="9259e-138">[SQL Server Native Client &#40;ODBC&#41;](sql-server-native-client-odbc.md) </span></span>  
 <span data-ttu-id="9259e-139">[SQLColumnPrivileges](../../native-client-odbc-api/sqlcolumnprivileges.md) </span><span class="sxs-lookup"><span data-stu-id="9259e-139">[SQLColumnPrivileges](../../native-client-odbc-api/sqlcolumnprivileges.md) </span></span>  
 <span data-ttu-id="9259e-140">[SQLColumns](../../native-client-odbc-api/sqlcolumns.md) </span><span class="sxs-lookup"><span data-stu-id="9259e-140">[SQLColumns](../../native-client-odbc-api/sqlcolumns.md) </span></span>  
 <span data-ttu-id="9259e-141">[SQLPrimaryKeys](../../native-client-odbc-api/sqlprimarykeys.md) </span><span class="sxs-lookup"><span data-stu-id="9259e-141">[SQLPrimaryKeys](../../native-client-odbc-api/sqlprimarykeys.md) </span></span>  
 <span data-ttu-id="9259e-142">[SQLTablePrivileges](../../native-client-odbc-api/sqltableprivileges.md) </span><span class="sxs-lookup"><span data-stu-id="9259e-142">[SQLTablePrivileges](../../native-client-odbc-api/sqltableprivileges.md) </span></span>  
 <span data-ttu-id="9259e-143">[SQLTables](../../native-client-odbc-api/sqltables.md) </span><span class="sxs-lookup"><span data-stu-id="9259e-143">[SQLTables](../../native-client-odbc-api/sqltables.md) </span></span>  
 [<span data-ttu-id="9259e-144">SQLStatistics</span><span class="sxs-lookup"><span data-stu-id="9259e-144">SQLStatistics</span></span>](../../statistics/statistics.md)  
  
  
