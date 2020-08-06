---
title: Prise en charge de FILESTREAM (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- FILESTREAM [SQL Server], ODBC
- ODBC, FILESTREAM support
ms.assetid: 87982955-1542-4551-9c06-447ffe8193b9
author: rothja
ms.author: jroth
ms.openlocfilehash: e9b77a6a893c1c7c12e5fc14f23bf9fd719c689f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602809"
---
# <a name="filestream-support-odbc"></a><span data-ttu-id="75af8-102">Prise en charge de FILESTREAM (ODBC)</span><span class="sxs-lookup"><span data-stu-id="75af8-102">FILESTREAM Support (ODBC)</span></span>
  <span data-ttu-id="75af8-103">ODBC dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client prend en charge la fonctionnalité FILESTREAM améliorée.</span><span class="sxs-lookup"><span data-stu-id="75af8-103">ODBC in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports the enhanced FILESTREAM feature.</span></span> <span data-ttu-id="75af8-104">Pour plus d’informations sur cette fonctionnalité, consultez [prise en charge de FileStream](../features/filestream-support.md).</span><span class="sxs-lookup"><span data-stu-id="75af8-104">For more information about this feature, see [FILESTREAM Support](../features/filestream-support.md).</span></span> <span data-ttu-id="75af8-105">Pour obtenir un exemple illustrant la prise en charge d’ODB pour FILESTREAM, consultez [Envoyer et recevoir des données de façon incrémentielle avec filestream &#40;ODBC&#41;](../../native-client-odbc-how-to/send-and-receive-data-incrementally-with-filestream-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="75af8-105">For a sample demonstrating ODB support for FILESTREAM, see [Send and Receive Data Incrementally with FILESTREAM &#40;ODBC&#41;](../../native-client-odbc-how-to/send-and-receive-data-incrementally-with-filestream-odbc.md).</span></span>  
  
 <span data-ttu-id="75af8-106">Pour envoyer et recevoir des `varbinary(max)` valeurs supérieures à 2 Go, une application doit lier des paramètres à l’aide de SQLBindParameter avec l’ensemble de *colonnes* défini sur `SQL_SS_LENGTH_UNLIMITED` et définir le contenu de *StrLen_or_IndPtr* sur `SQL_DATA_AT_EXEC` avant SQLExecDirect ou SQLExecute.</span><span class="sxs-lookup"><span data-stu-id="75af8-106">To send and receive `varbinary(max)` values greater than 2 GB, an application must bind parameters by using SQLBindParameter with *ColumnSize* set to `SQL_SS_LENGTH_UNLIMITED`, and set the contents of *StrLen_or_IndPtr* to `SQL_DATA_AT_EXEC` before SQLExecDirect or SQLExecute.</span></span>  
  
 <span data-ttu-id="75af8-107">Comme pour tout paramètre de données en cours d’exécution, les données sont fournies avec SQLParamData et SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="75af8-107">As with any data-at-execution parameter, the data will be supplied with SQLParamData and SQLPutData.</span></span>  
  
 <span data-ttu-id="75af8-108">Vous pouvez appeler SQLGetData pour extraire des données en segments pour une colonne FILESTREAM si la colonne n’est pas liée à SQLBindCol.</span><span class="sxs-lookup"><span data-stu-id="75af8-108">You can call SQLGetData to fetch data in chunks for a FILESTREAM column if the column is not bound with SQLBindCol.</span></span>  
  
 <span data-ttu-id="75af8-109">Vous pouvez mettre à jour les données FILESTREAM si elles sont liées à SQLBindCol.</span><span class="sxs-lookup"><span data-stu-id="75af8-109">You can update FILESTREAM data if it is bound with SQLBindCol.</span></span>  
  
 <span data-ttu-id="75af8-110">Si vous appelez SQLFetch sur une colonne liée, vous recevrez un avertissement « données tronquées » si la mémoire tampon n’est pas assez grande pour contenir la valeur entière.</span><span class="sxs-lookup"><span data-stu-id="75af8-110">If you call SQLFetch on a bound column, you will receive a "data truncated" warning if the buffer is not large enough to hold the entire value.</span></span> <span data-ttu-id="75af8-111">Ignorez cet avertissement et mettez à jour les données de cette colonne liée avec les appels SQLParamData et SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="75af8-111">Ignore this warning and update the data in this bound column with SQLParamData and SQLPutData calls.</span></span> <span data-ttu-id="75af8-112">Vous pouvez mettre à jour les données FILESTREAM à l’aide de SQLSetPos si elles sont liées à SQLBindCol.</span><span class="sxs-lookup"><span data-stu-id="75af8-112">You can update FILESTREAM data by using SQLSetPos if it is bound with SQLBindCol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75af8-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="75af8-113">Example</span></span>  
 <span data-ttu-id="75af8-114">Les colonnes FILESTREAM se comportent exactement comme les colonnes `varbinary(max)`, mais sans limite de taille.</span><span class="sxs-lookup"><span data-stu-id="75af8-114">FILESTREAM columns behave exactly like `varbinary(max)` columns, but without a size limit.</span></span> <span data-ttu-id="75af8-115">Elles sont liées en tant que SQL_VARBINARY.</span><span class="sxs-lookup"><span data-stu-id="75af8-115">They are bound as SQL_VARBINARY.</span></span> <span data-ttu-id="75af8-116">(SQL_LONGVARBINARY est utilisé avec les colonnes image et ce type comporte un certain nombre de restrictions.</span><span class="sxs-lookup"><span data-stu-id="75af8-116">(SQL_LONGVARBINARY is used with image columns, and there are restrictions on this type.</span></span> <span data-ttu-id="75af8-117">Par exemple, SQL_LONGVARBINARY connot être utilisé comme paramètre de sortie.) Les exemples suivants montrent un accès direct au NTFS pour les colonnes FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="75af8-117">For example, SQL_LONGVARBINARY connot be used as an output parameter.) The following examples show direct NTFS access for FILESTREAM columns.</span></span> <span data-ttu-id="75af8-118">Ces exemples supposent que le code [!INCLUDE[tsql](../../../includes/tsql-md.md)] suivant a été exécuté dans la base de données :</span><span class="sxs-lookup"><span data-stu-id="75af8-118">These examples assume that the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] code has been executed in the database:</span></span>  
  
```  
CREATE TABLE fileStreamDocs(  
id uniqueidentifier ROWGUIDCOL NOT NULL UNIQUE,  
author varchar(64),  
document VARBINARY(MAX) FILESTREAM NULL)  
```  
  
### <a name="read"></a><span data-ttu-id="75af8-119">Lire</span><span class="sxs-lookup"><span data-stu-id="75af8-119">Read</span></span>  
  
```  
void selectFilestream (LPCWSTR dstFilePath) {  
SQLRETURN r;  
SQLCHAR transactionToken[1024];  
SQLWCHAR srcFilePath[1024];  
SQLINTEGER cbTransactionToken, cbsrcFilePath;  
  
// The GUID columns must be visible to the query,   
// even if it is not used  
r = SQLExecDirect(hstmt, (SQLTCHAR *)   
_T("select GET_FILESTREAM_TRANSACTION_CONTEXT(); \  
select TOP(1) id, document.PathName() \  
from fileStreamDocs WHERE author = 'Chris Lee'"),   
SQL_NTS);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLFetch(hstmt);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLGetData(hstmt, 1, SQL_C_BINARY,   
transactionToken, sizeof(transactionToken), &cbTransactionToken);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLMoreResults(hstmt);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLFetch(hstmt);  
r = SQLGetData(hstmt, 2, SQL_C_TCHAR,   
srcFilePath, sizeof(srcFilePath), &cbsrcFilePath);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
if (!copyFileFromSql(srcFilePath, dstFilePath, transactionToken, cbTransactionToken)) {  
DeleteFile(dstFilePath);  
}  
r = SQLTransact(henv, hdbc, SQL_ROLLBACK);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
}  
```  
  
### <a name="insert"></a><span data-ttu-id="75af8-120">Insert</span><span class="sxs-lookup"><span data-stu-id="75af8-120">Insert</span></span>  
  
```  
void insertFilestream(LPCWSTR srcFilePath) {  
SQLRETURN r;  
SQLCHAR transactionToken[64];  
SQLWCHAR dstFilePath[1024];  
SQLINTEGER cbTransactionToken, cbDstFilePath;  
SQLUSMALLINT mode;  
  
r = SQLExecDirect(hstmt, (SQLTCHAR *)   
_T("insert into fileStreamDocs (id, author, document)\  
    output Get_Filestream_Transaction_Context(), inserted.document.PathName() \  
        values (newid(), 'Chris Lee', convert(varbinary, '**Temp**')) "), SQL_NTS);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLFetch(hstmt);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLGetData(hstmt, 1, SQL_C_BINARY,  
transactionToken, sizeof(transactionToken), &cbTransactionToken);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLGetData(hstmt, 2, SQL_C_TCHAR,  
dstFilePath, sizeof(dstFilePath), &cbDstFilePath);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLCloseCursor(hstmt);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
if (copyFileToSql(  
srcFilePath, dstFilePath,   
transactionToken, cbTransactionToken)) {  
mode = SQL_COMMIT;  
}  
else {  
mode = SQL_ROLLBACK;  
}  
  
r = SQLTransact(henv, hdbc, mode);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
}  
```  
  
### <a name="helper-routines"></a><span data-ttu-id="75af8-121">Routines d'assistance</span><span class="sxs-lookup"><span data-stu-id="75af8-121">Helper Routines</span></span>  
  
```  
#define COPYBUFFERSIZE 4096  
BOOL copyFileContents (HANDLE srcHandle, HANDLE dstHandle) {  
  
BYTE buffer[COPYBUFFERSIZE];  
DWORD bytesRead, bytesWritten;  
BOOL r;  
  
do {  
r = ReadFile(srcHandle, buffer, COPYBUFFERSIZE, &bytesRead,NULL);  
if (bytesRead == 0) {  
return r;  
}  
r = WriteFile(dstHandle, buffer, bytesRead, &bytesWritten, NULL);  
if (bytesWritten == 0) {  
return r;  
}  
} while (TRUE);  
}  
  
BOOL copyFileToSql(LPCWSTR srcFilePath, LPCWSTR dstFilePath, LPBYTE transactionToken, SQLINTEGER cbTransactionToken) {  
  
BOOL r;  
  
HANDLE srcHandle, dstHandle;  
unsigned int NtStatus;  
  
srcHandle =  CreateFile(  
                         srcFilePath,  
                         GENERIC_READ,  
                         FILE_SHARE_READ,  
                         NULL,  
                         OPEN_EXISTING,  
                         FILE_FLAG_SEQUENTIAL_SCAN,  
 NULL);  
  
if (srcHandle == INVALID_HANDLE_VALUE) {  
return FALSE;  
}  
  
dstHandle =  OpenSqlFilestream(  
                         dstFilePath,  
                         Write,  
                         0,  
                         transactionToken,  
                         cbTransactionToken,  
                         0);  
  
if (dstHandle == INVALID_HANDLE_VALUE) {  
NtStatus = GetLastError();  
r = CloseHandle(srcHandle);  
return FALSE;  
}  
  
//copy file  
r = copyFileContents(srcHandle, dstHandle);  
  
CloseHandle(srcHandle);  
  
CloseHandle(dstHandle);  
  
return r;  
}  
  
BOOL copyFileFromSql(LPCWSTR srcFilePath, LPCWSTR dstFilePath, LPBYTE transactionToken, SQLINTEGER cbTransactionToken) {  
  
BOOL r;  
  
HANDLE srcHandle, dstHandle;  
unsigned int NtStatus;  
  
srcHandle =  OpenSqlFilestream(  
                         srcFilePath,  
                         Read,  
                         0,  
                         transactionToken,  
                         cbTransactionToken,  
                         0);  
  
if (srcHandle == INVALID_HANDLE_VALUE) {  
return FALSE;  
}  
  
dstHandle =  CreateFile(  
                         dstFilePath,  
                         GENERIC_WRITE,  
                         0,  
                         NULL,  
                         OPEN_ALWAYS,  
                         FILE_ATTRIBUTE_NORMAL,  
 NULL);  
  
if (dstHandle == INVALID_HANDLE_VALUE) {  
CloseHandle(srcHandle);  
return FALSE;  
}  
  
r = copyFileContents(srcHandle, dstHandle);  
  
CloseHandle(srcHandle);  
  
CloseHandle(dstHandle);  
  
return r;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="75af8-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="75af8-122">See Also</span></span>  
 [<span data-ttu-id="75af8-123">Programmation de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="75af8-123">SQL Server Native Client Programming</span></span>](../sql-server-native-client-programming.md)  
  
  
