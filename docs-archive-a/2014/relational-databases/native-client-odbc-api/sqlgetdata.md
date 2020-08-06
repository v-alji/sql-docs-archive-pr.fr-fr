---
title: SQLGetData | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetData function
ms.assetid: 204848be-8787-45b4-816f-a60ac9d56fcf
author: rothja
ms.author: jroth
ms.openlocfilehash: c351cf7340bc7b0afeb76b139bd75aa429f56e10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599993"
---
# <a name="sqlgetdata"></a><span data-ttu-id="84367-102">SQLGetData</span><span class="sxs-lookup"><span data-stu-id="84367-102">SQLGetData</span></span>
  <span data-ttu-id="84367-103">**SQLGetData** est utilisé pour récupérer les données du jeu de résultats sans les valeurs de colonne de liaison.</span><span class="sxs-lookup"><span data-stu-id="84367-103">**SQLGetData** is used to retrieve result set data without binding column values.</span></span> <span data-ttu-id="84367-104">**SQLGetData** peut être appelé successivement sur la même colonne pour récupérer de grandes quantités de données à partir d’une colonne avec un type de données **Text**, **ntext**ou **image** .</span><span class="sxs-lookup"><span data-stu-id="84367-104">**SQLGetData** can be called successively on the same column to retrieve large amounts of data from a column with a **text**, **ntext**, or **image** data type.</span></span>  
  
 <span data-ttu-id="84367-105">Il n'y a aucune spécification exigeant qu'une application lie des variables pour extraire des données de jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="84367-105">There is no requirement that an application bind variables to fetch result set data.</span></span> <span data-ttu-id="84367-106">Les données de n’importe quelle colonne peuvent être récupérées à partir du [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client à l’aide de **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="84367-106">The data of any column can be retrieved from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver by using **SQLGetData**.</span></span>  
  
 <span data-ttu-id="84367-107">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client ne prend pas en charge l’utilisation de **SQLGetData** pour récupérer des données dans l’ordre aléatoire des colonnes.</span><span class="sxs-lookup"><span data-stu-id="84367-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support using **SQLGetData** to retrieve data in random column order.</span></span> <span data-ttu-id="84367-108">Toutes les colonnes indépendantes traitées avec **SQLGetData** doivent avoir des ordinaux de colonne plus élevés que les colonnes liées dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="84367-108">All unbound columns processed with **SQLGetData** must have higher column ordinals than the bound columns in the result set.</span></span> <span data-ttu-id="84367-109">L'application doit traiter les données de la valeur d'ordinal de colonne indépendante la plus basse à la plus élevée.</span><span class="sxs-lookup"><span data-stu-id="84367-109">The application must process data from the lowest unbound ordinal column value to the highest.</span></span> <span data-ttu-id="84367-110">Toute tentative d'extraction de données d'une colonne d'ordinal inférieur provoque une erreur.</span><span class="sxs-lookup"><span data-stu-id="84367-110">Attempting to retrieve data from a lower ordinally numbered column results in an error.</span></span> <span data-ttu-id="84367-111">Si l'application utilise des curseurs côté serveur pour signaler les lignes de jeu de résultats, l'application peut réextraire la ligne actuelle, puis extraire la valeur d'une colonne.</span><span class="sxs-lookup"><span data-stu-id="84367-111">If the application is using server cursors to report result set rows, the application can refetch the current row and then fetch the value of a column.</span></span> <span data-ttu-id="84367-112">Si une instruction est exécutée sur le curseur par défaut en lecture seule et avant uniquement, vous devez exécuter à nouveau l’instruction pour sauvegarder **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="84367-112">If a statement is executed on the default read-only, forward-only cursor, you must re-execute the statement to back up **SQLGetData**.</span></span>  
  
 <span data-ttu-id="84367-113">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC native client signale avec précision la longueur des données **Text**, **ntext**et **image** extraites à l’aide de **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="84367-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver accurately reports the length of **text**, **ntext**, and **image** data retrieved using **SQLGetData**.</span></span> <span data-ttu-id="84367-114">L’application peut utiliser le retour du paramètre *StrLen_or_IndPtr* pour récupérer rapidement des données de type long.</span><span class="sxs-lookup"><span data-stu-id="84367-114">The application can make good use of the *StrLen_or_IndPtr* parameter return to retrieve long data rapidly.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="84367-115">Pour les types de valeur élevée, *StrLen_or_IndPtr* retourne SQL_NO_TOTAL en cas de troncation des données.</span><span class="sxs-lookup"><span data-stu-id="84367-115">For large value types, *StrLen_or_IndPtr* will return SQL_NO_TOTAL in cases of data truncation.</span></span>  
  
## <a name="sqlgetdata-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="84367-116">Prise en charge de SQLGetData pour les fonctionnalités Date et Heure améliorées</span><span class="sxs-lookup"><span data-stu-id="84367-116">SQLGetData Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="84367-117">Les valeurs de colonne de résultats de types date/heure sont converties comme décrit dans [conversions de SQL en C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md).</span><span class="sxs-lookup"><span data-stu-id="84367-117">Result column values of date/time types are converted as described in [Conversions from SQL to C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md).</span></span>  
  
 <span data-ttu-id="84367-118">Pour plus d’informations, consultez améliorations de la [date et de l’heure &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="84367-118">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlgetdata-support-for-large-clr-udts"></a><span data-ttu-id="84367-119">Prise en charge SQLGetData pour les types CLR volumineux définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="84367-119">SQLGetData Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="84367-120">**SQLGetData** prend en charge les grands types CLR définis par l’utilisateur (UDT).</span><span class="sxs-lookup"><span data-stu-id="84367-120">**SQLGetData** supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="84367-121">Pour plus d’informations, consultez [types CLR volumineux définis par l’utilisateur &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="84367-121">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="84367-122"> Exemple</span><span class="sxs-lookup"><span data-stu-id="84367-122">Example</span></span>  
  
```  
SQLHDBC     hDbc = NULL;  
SQLHSTMT    hStmt = NULL;  
long        lEmpID;  
PBYTE       pPicture;  
SQLINTEGER  pIndicators[2];  
  
// Get an environment, connection, and so on.  
...  
  
// Get a statement handle and execute a command.  
SQLAllocHandle(SQL_HANDLE_STMT, hDbc, &hStmt);  
  
if (SQLExecDirect(hStmt,  
    (SQLCHAR*) "SELECT EmployeeID, Photo FROM Employees",  
    SQL_NTS) == SQL_ERROR)  
    {  
    // Handle error and return.  
    }  
  
// Retrieve data from row set.  
SQLBindCol(hStmt, 1, SQL_C_LONG, (SQLPOINTER) &lEmpID, sizeof(long),  
    &pIndicators[0]);  
  
while (SQLFetch(hStmt) == SQL_SUCCESS)  
    {  
    cout << "EmployeeID: " << lEmpID << "\n";  
  
    // Call SQLGetData to determine the amount of data that's waiting.  
    if (SQLGetData(hStmt, 2, SQL_C_BINARY, pPicture, 0, &pIndicators[1])  
        == SQL_SUCCESS_WITH_INFO)  
        {  
        cout << "Photo size: " pIndicators[1] << "\n\n";  
  
        // Get all the data at once.  
        pPicture = new BYTE[pIndicators[1]];  
        if (SQLGetData(hStmt, 2, SQL_C_DEFAULT, pPicture,  
            pIndicators[1], &pIndicators[1]) != SQL_SUCCESS)  
            {  
            // Handle error and continue.  
            }  
  
        delete [] pPicture;  
        }  
    else  
        {  
        // Handle error on attempt to get data length.  
        }  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="84367-123"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="84367-123">See Also</span></span>  
 <span data-ttu-id="84367-124">[Fonction SQLGetData](https://go.microsoft.com/fwlink/?LinkId=59350) </span><span class="sxs-lookup"><span data-stu-id="84367-124">[SQLGetData Function](https://go.microsoft.com/fwlink/?LinkId=59350) </span></span>  
 [<span data-ttu-id="84367-125">Détails de l’implémentation d’API ODBC</span><span class="sxs-lookup"><span data-stu-id="84367-125">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
