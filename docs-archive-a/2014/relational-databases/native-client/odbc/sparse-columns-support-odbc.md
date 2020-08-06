---
title: Prise en charge des colonnes éparses (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 11ae959f-2fb6-4b85-ac5d-1476a82136d4
author: rothja
ms.author: jroth
ms.openlocfilehash: 076709f3f37e92492f7c3f8c20ee692416d9e867
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702856"
---
# <a name="sparse-columns-support-odbc"></a><span data-ttu-id="bb901-102">Prise en charge des colonnes éparses (ODBC)</span><span class="sxs-lookup"><span data-stu-id="bb901-102">Sparse Columns Support (ODBC)</span></span>
  <span data-ttu-id="bb901-103">Cette rubrique décrit la prise en charge ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client pour les colonnes éparses.</span><span class="sxs-lookup"><span data-stu-id="bb901-103">This topic describes [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC support for sparse columns.</span></span> <span data-ttu-id="bb901-104">Pour obtenir un exemple illustrant la prise en charge d’ODBC pour les colonnes éparses, consultez [appeler SQLColumns sur une table avec des colonnes éparses](../../native-client-odbc-how-to/call-sqlcolumns-on-a-table-with-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="bb901-104">For a sample demonstrating ODBC support for sparse columns, see [Call SQLColumns on a Table with Sparse Columns](../../native-client-odbc-how-to/call-sqlcolumns-on-a-table-with-sparse-columns.md).</span></span> <span data-ttu-id="bb901-105">Pour plus d’informations sur les colonnes éparses, consultez [prise en charge des colonnes éparses dans SQL Server Native Client](../features/sparse-columns-support-in-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="bb901-105">For more information about sparse columns, see [Sparse Columns Support in SQL Server Native Client](../features/sparse-columns-support-in-sql-server-native-client.md).</span></span>  
  
## <a name="statement-metadata"></a><span data-ttu-id="bb901-106">Métadonnées d'instruction</span><span class="sxs-lookup"><span data-stu-id="bb901-106">Statement Metadata</span></span>  
 <span data-ttu-id="bb901-107">Le champ de descripteur APD (Application Parameter Descriptor) et l'attribut d'instruction SQL_SOPT_SS_NAME_SCOPE acceptent les valeurs supplémentaires SQL_SS_NAME_SCOPE_EXTENDED et SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.</span><span class="sxs-lookup"><span data-stu-id="bb901-107">The application parameter descriptor (APD) descriptor field and SQL_SOPT_SS_NAME_SCOPE statement attribute accepts the additional values SQL_SS_NAME_SCOPE_EXTENDED and SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.</span></span> <span data-ttu-id="bb901-108">Ces valeurs spécifient les colonnes qui sont incluses dans le jeu de résultats retourné par [SQLColumns](../../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="bb901-108">These values specify which columns are included in the result set returned by [SQLColumns](../../native-client-odbc-api/sqlcolumns.md).</span></span> <span data-ttu-id="bb901-109">Pour plus d'informations sur SQL_SOPT_SS_NAME_SCOPE, consultez [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="bb901-109">For more information about SQL_SOPT_SS_NAME_SCOPE, see [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="bb901-110">Un nouveau descripteur de ligne d'implémentation (IRD, Implementation Row Descriptor), un champ SQLSMALLINT en lecture seule appelé SQL_CA_SS_IS_COLUMN_SET, peut être utilisé pour déterminer si une colonne est une valeur `column_set` XML.</span><span class="sxs-lookup"><span data-stu-id="bb901-110">A new implementation row descriptor (IRD), a read-only SQLSMALLINT field called SQL_CA_SS_IS_COLUMN_SET, can be used to determine if a column is an XML `column_set` value.</span></span> <span data-ttu-id="bb901-111">SQL_CA_SS_IS_COLUMN_SET prend les valeurs SQL_TRUE et SQL_FALSE.</span><span class="sxs-lookup"><span data-stu-id="bb901-111">SQL_CA_SS_IS_COLUMN_SET takes the values SQL_TRUE and SQL_FALSE.</span></span>  
  
## <a name="catalog-metadata"></a><span data-ttu-id="bb901-112">Métadonnées de catalogue</span><span class="sxs-lookup"><span data-stu-id="bb901-112">Catalog Metadata</span></span>  
 <span data-ttu-id="bb901-113">Deux colonnes spécifiques à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (SS_IS_SPARSE et SS_IS_COLUMN_SET) ont été ajoutées au jeu de résultats pour [SQLColumns](../../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="bb901-113">Two [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] specific columns (SS_IS_SPARSE and SS_IS_COLUMN_SET) have been added to the result set for [SQLColumns](../../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="odbc-function-support-for-sparse-columns"></a><span data-ttu-id="bb901-114">Prise en charge de fonction ODBC pour les colonnes éparses</span><span class="sxs-lookup"><span data-stu-id="bb901-114">ODBC Function Support for Sparse Columns</span></span>  
 <span data-ttu-id="bb901-115">Les fonctions ODBC suivantes ont été mises à jour pour prendre en charge les colonnes éparses dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client :</span><span class="sxs-lookup"><span data-stu-id="bb901-115">The following ODBC functions have been updated to support sparse columns in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client:</span></span>  
  
-   [<span data-ttu-id="bb901-116">SQLColAttribute</span><span class="sxs-lookup"><span data-stu-id="bb901-116">SQLColAttribute</span></span>](../../native-client-odbc-api/sqlcolattribute.md)  
  
-   [<span data-ttu-id="bb901-117">SQLColumns</span><span class="sxs-lookup"><span data-stu-id="bb901-117">SQLColumns</span></span>](../../native-client-odbc-api/sqlcolumns.md)  
  
-   [<span data-ttu-id="bb901-118">SQLGetDescField</span><span class="sxs-lookup"><span data-stu-id="bb901-118">SQLGetDescField</span></span>](../../native-client-odbc-api/sqlgetdescfield.md)  
  
-   [<span data-ttu-id="bb901-119">SQLSetDescField</span><span class="sxs-lookup"><span data-stu-id="bb901-119">SQLSetDescField</span></span>](../../native-client-odbc-api/sqlsetdescfield.md)  
  
-   [<span data-ttu-id="bb901-120">SQLSetStmtAttr</span><span class="sxs-lookup"><span data-stu-id="bb901-120">SQLSetStmtAttr</span></span>](../../native-client-odbc-api/sqlsetstmtattr.md)  
  
## <a name="see-also"></a><span data-ttu-id="bb901-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bb901-121">See Also</span></span>  
 [<span data-ttu-id="bb901-122">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="bb901-122">SQL Server Native Client &#40;ODBC&#41;</span></span>](sql-server-native-client-odbc.md)  
  
  
