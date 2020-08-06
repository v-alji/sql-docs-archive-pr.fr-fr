---
title: SQLTables | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLTables function
ms.assetid: 77b6c15c-9cf7-4019-b3f0-3d27d23ef656
author: rothja
ms.author: jroth
ms.openlocfilehash: bad60aa102a7771935e37ac963e6fa0d3cb2fd57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605399"
---
# <a name="sqltables"></a><span data-ttu-id="fe5b3-102">SQLTables</span><span class="sxs-lookup"><span data-stu-id="fe5b3-102">SQLTables</span></span>
  <span data-ttu-id="fe5b3-103">SQLTables peut être exécuté sur un curseur côté serveur statique.</span><span class="sxs-lookup"><span data-stu-id="fe5b3-103">SQLTables can be executed on a static server cursor.</span></span> <span data-ttu-id="fe5b3-104">Une tentative d’exécution de SQLTables sur un curseur pouvant être mis à jour (dynamique ou de jeu de clés) retourne SQL_SUCCESS_WITH_INFO indiquant que le type de curseur a été modifié.</span><span class="sxs-lookup"><span data-stu-id="fe5b3-104">An attempt to execute SQLTables on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="fe5b3-105">SQLTables signale les tables de toutes les bases de données lorsque le paramètre *nomcatalogue* est SQL_ALL_CATALOGS et que tous les autres paramètres contiennent des valeurs par défaut (pointeurs null).</span><span class="sxs-lookup"><span data-stu-id="fe5b3-105">SQLTables reports tables from all databases when the *CatalogName* parameter is SQL_ALL_CATALOGS and all other parameters contain default values (NULL pointers).</span></span>  
  
 <span data-ttu-id="fe5b3-106">Pour signaler les catalogues disponibles, les schémas et les types de tables, SQLTables utilise des chaînes vides (pointeurs d’octets de longueur nulle).</span><span class="sxs-lookup"><span data-stu-id="fe5b3-106">To report available catalogs, schemas, and table types, SQLTables makes special use of empty strings (zero-length byte pointers).</span></span> <span data-ttu-id="fe5b3-107">Les chaînes vides ne sont pas des valeurs par défaut (pointeurs NULL).</span><span class="sxs-lookup"><span data-stu-id="fe5b3-107">Empty strings are not default values (NULL pointers).</span></span>  
  
 <span data-ttu-id="fe5b3-108">Le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client prend en charge les informations de création de rapport pour les tables des serveurs liés en acceptant un nom en deux parties pour le paramètre *CatalogName* : *Linked_Server_Name.Catalog_Name*.</span><span class="sxs-lookup"><span data-stu-id="fe5b3-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *CatalogName* parameter: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
 <span data-ttu-id="fe5b3-109">SQLTables retourne des informations sur toutes les tables dont les noms correspondent à *TableName* et qui sont détenus par l’utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="fe5b3-109">SQLTables returns information about any tables whose names match *TableName* and are owned by the current user.</span></span>  
  
## <a name="sqltables-and-table-valued-parameters"></a><span data-ttu-id="fe5b3-110">SQLTables et paramètres table</span><span class="sxs-lookup"><span data-stu-id="fe5b3-110">SQLTables and Table-Valued Parameters</span></span>  
 <span data-ttu-id="fe5b3-111">Lorsque l’attribut d’instruction SQL_SOPT_SS_NAME_SCOPE a la valeur SQL_SS_NAME_SCOPE_TABLE_TYPE, plutôt que sa valeur par défaut SQL_SS_NAME_SCOPE_TABLE, SQLTables retourne des informations sur les types de table.</span><span class="sxs-lookup"><span data-stu-id="fe5b3-111">When the statement attribute SQL_SOPT_SS_NAME_SCOPE has the value SQL_SS_NAME_SCOPE_TABLE_TYPE, rather than its default value of SQL_SS_NAME_SCOPE_TABLE, SQLTables returns information about table types.</span></span> <span data-ttu-id="fe5b3-112">La valeur TABLE_TYPE retournée pour un type de table dans la colonne 4 du jeu de résultats retourné par SQLTables est le TYPE de TABLE.</span><span class="sxs-lookup"><span data-stu-id="fe5b3-112">The TABLE_TYPE value returned for a table type in column 4 of the result set returned by SQLTables is TABLE TYPE.</span></span> <span data-ttu-id="fe5b3-113">Pour plus d'informations sur SQL_SOPT_SS_NAME_SCOPE, consultez [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="fe5b3-113">For more information on SQL_SOPT_SS_NAME_SCOPE, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="fe5b3-114">Les tables, les vues et les synonymes partagent un espace de noms commun, distinct de l'espace de noms utilisé par les types de table.</span><span class="sxs-lookup"><span data-stu-id="fe5b3-114">Tables, views, and synonyms share a common namespace that is distinct from the namespace used by table types.</span></span> <span data-ttu-id="fe5b3-115">Bien qu'il ne soit pas possible d'avoir une table et une vue ayant le même nom, vous pouvez avoir une table et un type de table avec le même nom dans le même catalogue et le même schéma.</span><span class="sxs-lookup"><span data-stu-id="fe5b3-115">Although it is not possible to have a table and a view with the same name, it is possible to have a table and a table type with the same in the same catalog and schema.</span></span>  
  
 <span data-ttu-id="fe5b3-116">Pour plus d’informations sur les paramètres table, consultez [paramètres table &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="fe5b3-116">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe5b3-117"> Exemple</span><span class="sxs-lookup"><span data-stu-id="fe5b3-117">Example</span></span>  
  
```  
// Get a list of all tables in the current database.  
SQLTables(hstmt, NULL, 0, NULL, 0, NULL, 0, NULL,0);  
  
// Get a list of all tables in all databases.  
SQLTables(hstmt, (SQLCHAR*) "%", SQL_NTS, NULL, 0, NULL, 0, NULL,0);  
  
// Get a list of databases on the current connection's server.  
SQLTables(hstmt, (SQLCHAR*) "%", SQL_NTS, (SQLCHAR*)"", 0, (SQLCHAR*)"",  
    0, NULL, 0);  
```  
  
## <a name="see-also"></a><span data-ttu-id="fe5b3-118"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fe5b3-118">See Also</span></span>  
 <span data-ttu-id="fe5b3-119">[SQLTables, fonction](https://go.microsoft.com/fwlink/?LinkId=59374) </span><span class="sxs-lookup"><span data-stu-id="fe5b3-119">[SQLTables Function](https://go.microsoft.com/fwlink/?LinkId=59374) </span></span>  
 [<span data-ttu-id="fe5b3-120">Détails de l’implémentation d’API ODBC</span><span class="sxs-lookup"><span data-stu-id="fe5b3-120">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
