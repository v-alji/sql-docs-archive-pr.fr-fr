---
title: SQLPrimaryKeys | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLPrimaryKeys function
ms.assetid: bc61cd5b-d2f4-4f87-abc7-743cf9ea772d
author: rothja
ms.author: jroth
ms.openlocfilehash: 67a932996ccbf52f5ab21fd6aa62381184ebc510
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614015"
---
# <a name="sqlprimarykeys"></a><span data-ttu-id="2d5e8-102">SQLPrimaryKeys</span><span class="sxs-lookup"><span data-stu-id="2d5e8-102">SQLPrimaryKeys</span></span>
  <span data-ttu-id="2d5e8-103">Une table peut avoir une ou plusieurs colonnes pouvant servir d’identificateurs de ligne uniques, et les tables créées sans contrainte de clé primaire renvoient un jeu de résultats vide à SQLPrimaryKeys.</span><span class="sxs-lookup"><span data-stu-id="2d5e8-103">A table might have a column or columns that can serve as unique row identifiers, and tables created without a PRIMARY KEY constraint return an empty result set to SQLPrimaryKeys.</span></span> <span data-ttu-id="2d5e8-104">La fonction ODBC [SQLSpecialColumns](sqlspecialcolumns.md) signale les candidats aux identificateurs de ligne pour les tables sans clés primaires.</span><span class="sxs-lookup"><span data-stu-id="2d5e8-104">The ODBC function [SQLSpecialColumns](sqlspecialcolumns.md) reports row identifier candidates for tables without primary keys.</span></span>  
  
 <span data-ttu-id="2d5e8-105">SQLPrimaryKeys retourne SQL_SUCCESS si des valeurs existent pour les paramètres *nomcatalogue*, *SchemaName*ou *TableName* .</span><span class="sxs-lookup"><span data-stu-id="2d5e8-105">SQLPrimaryKeys returns SQL_SUCCESS whether or not values exist for *CatalogName*, *SchemaName*, or *TableName* parameters.</span></span> <span data-ttu-id="2d5e8-106">SQLFetch retourne SQL_NO_DATA lorsque des valeurs non valides sont utilisées dans ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="2d5e8-106">SQLFetch returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="2d5e8-107">SQLPrimaryKeys peut être exécuté sur un curseur côté serveur statique.</span><span class="sxs-lookup"><span data-stu-id="2d5e8-107">SQLPrimaryKeys can be executed on a static server cursor.</span></span> <span data-ttu-id="2d5e8-108">Une tentative d’exécution de SQLPrimaryKeys sur un curseur pouvant être mis à jour (dynamique ou de jeu de clés) retourne SQL_SUCCESS_WITH_INFO indiquant que le type de curseur a été modifié.</span><span class="sxs-lookup"><span data-stu-id="2d5e8-108">An attempt to execute SQLPrimaryKeys on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="2d5e8-109">Le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client prend en charge les informations de création de rapport pour les tables des serveurs liés en acceptant un nom en deux parties pour le paramètre *CatalogName* : *Linked_Server_Name.Catalog_Name*.</span><span class="sxs-lookup"><span data-stu-id="2d5e8-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *CatalogName* parameter: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
## <a name="sqlprimarykeys-and-table-valued-parameters"></a><span data-ttu-id="2d5e8-110">SQLPrimaryKeys et paramètres table</span><span class="sxs-lookup"><span data-stu-id="2d5e8-110">SQLPrimaryKeys and Table-Valued Parameters</span></span>  
 <span data-ttu-id="2d5e8-111">Si l’attribut d’instruction SQL_SOPT_SS_NAME_SCOPE a la valeur SQL_SS_NAME_SCOPE_TABLE_TYPE, plutôt que sa valeur par défaut de SQL_SS_NAME_SCOPE_TABLE, SQLPrimaryKeys renvoie des informations sur les colonnes de clé primaire des types de table.</span><span class="sxs-lookup"><span data-stu-id="2d5e8-111">If the statement attribute SQL_SOPT_SS_NAME_SCOPE has the value SQL_SS_NAME_SCOPE_TABLE_TYPE, rather than its default value of SQL_SS_NAME_SCOPE_TABLE, SQLPrimaryKeys will return information about primary key columns of table types.</span></span> <span data-ttu-id="2d5e8-112">Pour plus d'informations sur SQL_SOPT_SS_NAME_SCOPE, consultez [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="2d5e8-112">For more information on SQL_SOPT_SS_NAME_SCOPE, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="2d5e8-113">Pour plus d’informations sur les paramètres table, consultez [paramètres table &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="2d5e8-113">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d5e8-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2d5e8-114">See Also</span></span>  
 <span data-ttu-id="2d5e8-115">[SQLPrimaryKeys fonction)](https://go.microsoft.com/fwlink/?LinkId=59361) </span><span class="sxs-lookup"><span data-stu-id="2d5e8-115">[SQLPrimaryKeys Function](https://go.microsoft.com/fwlink/?LinkId=59361) </span></span>  
 [<span data-ttu-id="2d5e8-116">Détails de l’implémentation d’API ODBC</span><span class="sxs-lookup"><span data-stu-id="2d5e8-116">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
