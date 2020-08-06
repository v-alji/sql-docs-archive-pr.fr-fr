---
title: SQLGetDescField | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetDescField function
ms.assetid: 3e59a37a-28ee-4c91-8968-7fe3b966739d
author: rothja
ms.author: jroth
ms.openlocfilehash: 4538396dbfb5406d0464c4730c1f6f3bd5882799
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611059"
---
# <a name="sqlgetdescfield"></a><span data-ttu-id="85d39-102">SQLGetDescField</span><span class="sxs-lookup"><span data-stu-id="85d39-102">SQLGetDescField</span></span>
  <span data-ttu-id="85d39-103">Le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client expose uniquement les champs de descripteur spécifiques au pilote pour le descripteur de ligne d'implémentation (IRD).</span><span class="sxs-lookup"><span data-stu-id="85d39-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver exposes driver-specific descriptor fields for the implementation row descriptor (IRD) only.</span></span> <span data-ttu-id="85d39-104">Dans le descripteur IRD, les champs de descripteur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont référencés par le biais d'attributs de colonne spécifiques aux pilotes.</span><span class="sxs-lookup"><span data-stu-id="85d39-104">Within the IRD, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] descriptor fields are referenced through driver-specific column attributes.</span></span> <span data-ttu-id="85d39-105">Pour obtenir une liste complète des champs de descripteur spécifiques au pilote disponibles, consultez [SQLColAttribute](sqlcolattribute.md).</span><span class="sxs-lookup"><span data-stu-id="85d39-105">For information about a complete list of available driver-specific descriptor fields, see [SQLColAttribute](sqlcolattribute.md).</span></span>  
  
 <span data-ttu-id="85d39-106">Les champs de descripteur qui contiennent des chaînes d'identificateur de colonne sont souvent des chaînes de longueur nulle.</span><span class="sxs-lookup"><span data-stu-id="85d39-106">Descriptor fields that contain column identifier strings are often zero-length strings.</span></span> <span data-ttu-id="85d39-107">Toutes les valeurs des champs de descripteur spécifiques à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="85d39-107">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific descriptor field values are read-only.</span></span>  
  
 <span data-ttu-id="85d39-108">À l’instar des attributs récupérés avec SQLColAttribute, les champs de descripteur qui signalent des attributs au niveau de la ligne (par exemple SQL_CA_SS_COMPUTE_ID) sont signalés pour toutes les colonnes du jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="85d39-108">Like attributes retrieved with SQLColAttribute, descriptor fields that report row-level attributes (such as SQL_CA_SS_COMPUTE_ID) are reported for all columns in the result set.</span></span>  
  
## <a name="sqlgetdescfield-and-table-valued-parameters"></a><span data-ttu-id="85d39-109">SQLGetDescField et paramètres table</span><span class="sxs-lookup"><span data-stu-id="85d39-109">SQLGetDescField and Table-Valued Parameters</span></span>  
 <span data-ttu-id="85d39-110">SQLGetDescField peut être utilisé pour obtenir des valeurs pour les attributs étendus de paramètres table et les colonnes de paramètre table.</span><span class="sxs-lookup"><span data-stu-id="85d39-110">SQLGetDescField can be used to get values for extended attributes of table-valued parameters and table-valued parameter columns.</span></span> <span data-ttu-id="85d39-111">Pour plus d’informations sur les paramètres table, consultez [paramètres table &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="85d39-111">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlgetdescfield-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="85d39-112">Prise en charge par SQLGetDescField des fonctionnalités de date et heure améliorées</span><span class="sxs-lookup"><span data-stu-id="85d39-112">SQLGetDescField Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="85d39-113">Pour plus d'informations sur les champs de descripteur disponibles avec les nouveaux types date/heure, consultez [Parameter and Result Metadata](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span><span class="sxs-lookup"><span data-stu-id="85d39-113">For information about the descriptor fields available with the new date/time types, see [Parameter and Result Metadata](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span></span>  
  
 <span data-ttu-id="85d39-114">Pour plus d’informations, consultez améliorations de la [date et de l’heure &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="85d39-114">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
 <span data-ttu-id="85d39-115">À compter de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , SQLGetDescField peut retourner `SQL_C_SS_TIME2` (pour les `time` types) ou `SQL_C_SS_TIMESTAMPOFFSET` (pour `datetimeoffset` ) au lieu de `SQL_C_BINARY` , si votre application utilise ODBC 3,8.</span><span class="sxs-lookup"><span data-stu-id="85d39-115">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], SQLGetDescField can return `SQL_C_SS_TIME2` (for `time` types) or `SQL_C_SS_TIMESTAMPOFFSET` (for `datetimeoffset`) instead of `SQL_C_BINARY`, if your application uses ODBC 3.8.</span></span>  
  
## <a name="sqlgetdescfield-support-for-large-clr-udts"></a><span data-ttu-id="85d39-116">Prise en charge par SQLGetDescField des types CLR volumineux définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="85d39-116">SQLGetDescField Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="85d39-117">`SQLGetDescField` prend en charge les grands types CLR définis par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="85d39-117">`SQLGetDescField` supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="85d39-118">Pour plus d’informations, consultez [types CLR volumineux définis par l’utilisateur &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="85d39-118">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="sqlgetdescfield-support-for-sparse-columns"></a><span data-ttu-id="85d39-119">Prise en charge par SQLGetDescField des colonnes éparses</span><span class="sxs-lookup"><span data-stu-id="85d39-119">SQLGetDescField Support for Sparse Columns</span></span>  
 <span data-ttu-id="85d39-120">SQLGetDescField peut être utilisé pour interroger le nouveau champ IRD SQL_CA_SS_IS_COLUMN_SET pour déterminer si une colonne est une `column_set` colonne.</span><span class="sxs-lookup"><span data-stu-id="85d39-120">SQLGetDescField can be used to query the new IRD field SQL_CA_SS_IS_COLUMN_SET to determine if a column is a `column_set` column.</span></span>  
  
 <span data-ttu-id="85d39-121">Pour plus d’informations, consultez la rubrique [prise en charge des colonnes éparses &#40;ODBC&#41;](../native-client/odbc/sparse-columns-support-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="85d39-121">For more information, see [Sparse Columns Support &#40;ODBC&#41;](../native-client/odbc/sparse-columns-support-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="85d39-122"> Exemple</span><span class="sxs-lookup"><span data-stu-id="85d39-122">Example</span></span>  
  
```  
typedef struct tagCOMPUTEBYLIST  
    {  
    SQLSMALLINT nBys;  
    SQLSMALLINT aByList[1];  
    } COMPUTEBYLIST;  
typedef COMPUTEBYLIST* PCOMPUTEBYLIST;   
  
SQLHDESC    hIRD;   
SQLINTEGER  cbIRD;   
SQLINTEGER  nSet = 0;   
  
// . . .  
// Execute a statement that contains a COMPUTE clause,  
//  then get the descriptor handle of the IRD and  
//  get some IRD values.  
  
SQLGetStmtAttr(g_hStmt, SQL_ATTR_IMP_ROW_DESC,  
    (SQLPOINTER) &hIRD, sizeof(SQLHDESC), &cbIRD);  
  
// For statement-wide column attributes, any  
//  descriptor record will do. You know that 1 exists,  
//  so use it.  
SQLGetDescField(hIRD, 1, SQL_CA_SS_NUM_COMPUTES,  
    (SQLPOINTER) &nComputes, SQL_IS_INTEGER, &cbIRD);  
  
if (nSet == 0)  
    {  
    SQLINTEGER      nOrderID;  
  
    printf_s("Normal result set.\n");  
  
    for (nCol = 0; nCol < nCols; nCol++)  
        {  
        SQLGetDescField(hIRD, nCol+1,  
            SQL_CA_SS_COLUMN_ORDER,  
            (SQLPOINTER) &nOrderID, SQL_IS_INTEGER,  
            &cbIRD);  
  
        if (nOrderID != 0)  
            {  
            printf_s("Col in ORDER BY, pos: %ld",  
                nOrderID);  
            }  
            printf_s("\n");  
        }  
  
    printf_s("\n");  
    }  
else  
    {  
    PCOMPUTEBYLIST  pByList;  
    SQLSMALLINT     nBy;  
    SQLINTEGER      nColID;  
  
    printf_s("Computed result set number: %lu\n",  
        nSet);  
  
    SQLGetDescField(hIRD, 1, SQL_CA_SS_COMPUTE_BYLIST,  
        (SQLPOINTER) &pByList, SQL_IS_INTEGER,  
        &cbIRD);  
  
    if (pByList != NULL)  
        {  
        printf_s("Clause ordered by columns: ");  
        for (nBy = 0; nBy < pByList->nBys; )  
            {  
            printf_s("%u", pByList->aByList[nBy]);  
            nBy++;  
  
            if (nBy == pByList->nBys)  
                {  
                printf_s("\n");  
                }  
            else  
                {  
                printf_s(", ");  
                }  
            }  
        }  
    else  
        {  
        printf_s("Compute clause set not ordered.\n");  
        }  
  
    for (nCol = 0; nCol < nCols; nCol++)  
        {  
        SQLGetDescField(hIRD, nCol+1,  
            SQL_CA_SS_COLUMN_ID, (SQLPOINTER) &nColID,  
            SQL_IS_INTEGER, &cbIRD);  
        printf_s("ColumnID: %lu, nColID);  
        }  
    printf_s("\n");  
    }  
  
if (SQLMoreResults(g_hStmt) == SQL_SUCCESS)  
    {  
    // Determine the result set indicator.  
    SQLGetDescField(hIRD, 1, SQL_CA_SS_COMPUTE_ID,  
        (SQLPOINTER) &nSet, SQL_IS_INTEGER, &cbIRD);  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="85d39-123"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="85d39-123">See Also</span></span>  
 <span data-ttu-id="85d39-124">[SQLGetDescField fonction)](https://go.microsoft.com/fwlink/?LinkId=59351) </span><span class="sxs-lookup"><span data-stu-id="85d39-124">[SQLGetDescField Function](https://go.microsoft.com/fwlink/?LinkId=59351) </span></span>  
 [<span data-ttu-id="85d39-125">Détails de l’implémentation d’API ODBC</span><span class="sxs-lookup"><span data-stu-id="85d39-125">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
