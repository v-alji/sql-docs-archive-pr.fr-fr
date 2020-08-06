---
title: Extraire des colonnes avec IRow::GetColumns (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- IRow interface
ms.assetid: a4f79906-da0e-42f2-b0e9-812c29f39e48
author: rothja
ms.author: jroth
ms.openlocfilehash: 1e3eb9e2b55ad03ae4b5739850557836589649d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696835"
---
# <a name="fetch-columns-using-irowgetcolumns-ole-db"></a><span data-ttu-id="2ac06-102">Extraire des colonnes avec IRow::GetColumns (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="2ac06-102">Fetch Columns Using IRow::GetColumns (OLE DB)</span></span>
  <span data-ttu-id="2ac06-103">L'interface `IRow` autorise un accès direct aux colonnes d'une ligne unique dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="2ac06-103">The `IRow` interface allows direct access to columns of a single row in the result set.</span></span> <span data-ttu-id="2ac06-104">`IRow` est donc une méthode efficace pour extraire des colonnes d'un jeu de résultats avec une seule ligne.</span><span class="sxs-lookup"><span data-stu-id="2ac06-104">Thus, `IRow` is an efficient way to retrieve columns from a result set with one row.</span></span>  
  
 <span data-ttu-id="2ac06-105">Un exemple de code démontrant comment extraire une ligne unique à l'aide de `IRow` est disponible.</span><span class="sxs-lookup"><span data-stu-id="2ac06-105">A code sample is available that showshow to fetch a single row using `IRow`.</span></span> <span data-ttu-id="2ac06-106">Dans cet exemple, une colonne est extraite à la fois de la ligne.</span><span class="sxs-lookup"><span data-stu-id="2ac06-106">In this sample, one column at a time is retrieved from the row.</span></span> <span data-ttu-id="2ac06-107">L’exemple montre :</span><span class="sxs-lookup"><span data-stu-id="2ac06-107">The sample shows:</span></span>  
  
-   <span data-ttu-id="2ac06-108">comment extraire un groupe de colonnes (de manière consécutive) ;</span><span class="sxs-lookup"><span data-stu-id="2ac06-108">How to fetch a group of columns (in sequence).</span></span>  
  
-   <span data-ttu-id="2ac06-109">comment accéder deux fois à une colonne</span><span class="sxs-lookup"><span data-stu-id="2ac06-109">How to access a column twice.</span></span> <span data-ttu-id="2ac06-110">avec extraction de la largeur réelle de la colonne la première fois, puis accès aux données concernées par la suite.</span><span class="sxs-lookup"><span data-stu-id="2ac06-110">The first time the actual column width is obtained, and later the actual data is accessed.</span></span> <span data-ttu-id="2ac06-111">Dans la structure DBCOLUMNACCESS, si **pData** a la valeur null et que **cbMaxLen** est égal à 0, l’appel à `IRow` - `>GetColumns()` retourne uniquement la longueur de colonne réelle.</span><span class="sxs-lookup"><span data-stu-id="2ac06-111">In the DBCOLUMNACCESS structure, if **pData** is NULL and **cbMaxLen** is 0, the call to `IRow`-`>GetColumns()` returns only the actual column length.</span></span> <span data-ttu-id="2ac06-112">Dans ce cas, vous pouvez rappeler `IRow->GetColumns()` sur la même colonne pour récupérer les données réelles.</span><span class="sxs-lookup"><span data-stu-id="2ac06-112">In this case, `IRow->GetColumns()` can be called again on the same column to retrieve the actual data.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2ac06-113">Lorsque c'est possible, utilisez l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="2ac06-113">When possible, use Windows Authentication.</span></span> <span data-ttu-id="2ac06-114">Si l'authentification Windows n'est pas disponible, invitez les utilisateurs à entrer leurs informations d'identification au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="2ac06-114">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="2ac06-115">Évitez de stocker ces informations dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="2ac06-115">Avoid storing credentials in a file.</span></span> <span data-ttu-id="2ac06-116">Si vous devez conserver des informations d’identification, vous devez les chiffrer avec l' [API de chiffrement Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="2ac06-116">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-fetch-columns-using-irowgetcolumns"></a><span data-ttu-id="2ac06-117">Pour extraire des colonnes avec IRow::GetColumns</span><span class="sxs-lookup"><span data-stu-id="2ac06-117">To fetch columns using IRow::GetColumns</span></span>  
  
1.  <span data-ttu-id="2ac06-118">Établissez une connexion à la source de données.</span><span class="sxs-lookup"><span data-stu-id="2ac06-118">Establish a connection to the data source.</span></span>  
  
2.  <span data-ttu-id="2ac06-119">Exécutez la commande (dans l'exemple suivant, ICommandExecute::Execute() est appelée avec IID_IRow).</span><span class="sxs-lookup"><span data-stu-id="2ac06-119">Execute the command (in the following example, ICommandExecute::Execute() is called with IID_IRow).</span></span>  
  
3.  <span data-ttu-id="2ac06-120">Exécutez IRow::GetColumns() pour extraire une ou plusieurs colonnes dans la ligne obtenue.</span><span class="sxs-lookup"><span data-stu-id="2ac06-120">Execute IRow::GetColumns() to fetch one or more columns in the resulting row.</span></span> <span data-ttu-id="2ac06-121">Si vous souhaitez rechercher la taille de colonne réelle avant d'extraire des données, définissez pData dans DBCOLUMNACCESS sur NULL.</span><span class="sxs-lookup"><span data-stu-id="2ac06-121">If you want to find the actual column size before fetching data, set the pData in DBCOLUMNACCESS to NULL.</span></span> <span data-ttu-id="2ac06-122">L'appel à IRow::GetColumns() retourne uniquement la largeur de la colonne.</span><span class="sxs-lookup"><span data-stu-id="2ac06-122">The call to IRow::GetColumns() returns only the column width.</span></span> <span data-ttu-id="2ac06-123">Un autre appel à IRow::GetColumns() permet d'extraire les données.</span><span class="sxs-lookup"><span data-stu-id="2ac06-123">Another call the IRow::GetColumns() will fetch the data.</span></span>  
  
4.  <span data-ttu-id="2ac06-124">Exécutez IRow::GetColumns() jusqu'à ce que vous accédiez à toutes les colonnes dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="2ac06-124">Execute IRow::GetColumns() until all the columns you need are accessed.</span></span> <span data-ttu-id="2ac06-125">Vous devez accéder aux colonnes de manière consécutive.</span><span class="sxs-lookup"><span data-stu-id="2ac06-125">The columns must be accessed in sequence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ac06-126">Exemple</span><span class="sxs-lookup"><span data-stu-id="2ac06-126">Example</span></span>  
 <span data-ttu-id="2ac06-127">Cet exemple montre comment utiliser l'interface IRow pour permettre d'accéder directement aux colonnes d'une ligne unique dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="2ac06-127">This sample shows how to use the IRow interface to allow direct access to columns of a single row in the result set.</span></span> <span data-ttu-id="2ac06-128">L'exemple montre :</span><span class="sxs-lookup"><span data-stu-id="2ac06-128">The example shows:</span></span>  
  
-   <span data-ttu-id="2ac06-129">comment extraire un groupe de colonnes de manière consécutive.</span><span class="sxs-lookup"><span data-stu-id="2ac06-129">How to fetch a group of columns in sequence.</span></span>  
  
-   <span data-ttu-id="2ac06-130">Comment accéder deux fois à une colonne : la première fois au moment de l'obtention de la largeur de colonne réelle, puis ultérieurement, au moment de l'accès aux données effectives.</span><span class="sxs-lookup"><span data-stu-id="2ac06-130">How to access a column twice - the first time the actual column width is obtained and then later the actual data is accessed.</span></span>  
  
 <span data-ttu-id="2ac06-131">Dans la structure DBCOLUMNACCESS, si pData a la valeur NULL et que cbMaxLen est défini sur 0, l’appel à IRow>GetColumns retourne seulement la longueur de colonne réelle.</span><span class="sxs-lookup"><span data-stu-id="2ac06-131">In the DBCOLUMNACCESS structure, if pData is NULL and cbMaxLen is 0, the call to IRow->GetColumns returns only the actual column length.</span></span> <span data-ttu-id="2ac06-132">Dans ce cas, vous pouvez rappeler IRow->GetColumns sur la même colonne pour extraire les données réelles.</span><span class="sxs-lookup"><span data-stu-id="2ac06-132">In this case IRow->GetColumns can be called again on the same column to retrieve the actual data.</span></span> <span data-ttu-id="2ac06-133">Cet exemple n'est pas pris en charge sur la plateforme IA64.</span><span class="sxs-lookup"><span data-stu-id="2ac06-133">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="2ac06-134">Cet exemple requiert l'exemple de base de données AdventureWorks, que vous pouvez télécharger à partir de la page d'accueil des [exemples et projets de communautés Microsoft SQL Server](https://go.microsoft.com/fwlink/?LinkID=85384) .</span><span class="sxs-lookup"><span data-stu-id="2ac06-134">This sample requires the AdventureWorks sample database, which you can download from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.</span></span>  
  
 <span data-ttu-id="2ac06-135">La première liste de code ([!INCLUDE[tsql](../../includes/tsql-md.md)]) crée une table utilisée par l'exemple.</span><span class="sxs-lookup"><span data-stu-id="2ac06-135">The first ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing creates a table used by the sample.</span></span>  
  
 <span data-ttu-id="2ac06-136">Compilez avec ole32.lib oleaut32.lib et exécutez la deuxième liste de code (C++).</span><span class="sxs-lookup"><span data-stu-id="2ac06-136">Compile with ole32.lib oleaut32.lib and execute the second (C++) code listing.</span></span> <span data-ttu-id="2ac06-137">Cette application vous permet de vous connecter à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] par défaut de votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="2ac06-137">This application connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="2ac06-138">Sur certains systèmes d'exploitation Windows, vous devrez remplacer (localhost) ou (local) par le nom de votre instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2ac06-138">On some Windows operating systems, you will need to change (localhost) or (local) to the name of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="2ac06-139">Pour vous connecter à une instance nommée, changez la chaîne de connexion de L"(local)" en L"(local)\\\nom", où nom correspond à l’instance nommée.</span><span class="sxs-lookup"><span data-stu-id="2ac06-139">To connect to a named instance, change the connection string from L"(local)" to L"(local)\\\name" , where name is the named instance.</span></span> <span data-ttu-id="2ac06-140">Par défaut, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express est installé dans une instance nommée.</span><span class="sxs-lookup"><span data-stu-id="2ac06-140">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express installs to a named instance.</span></span> <span data-ttu-id="2ac06-141">Assurez-vous que votre variable d'environnement INCLUDE inclut le répertoire qui contient sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="2ac06-141">Make sure your INCLUDE environment variable includes the directory that contains sqlncli.h.</span></span>  
  
 <span data-ttu-id="2ac06-142">La troisième liste de code ([!INCLUDE[tsql](../../includes/tsql-md.md)]) supprime la table utilisée par l'exemple.</span><span class="sxs-lookup"><span data-stu-id="2ac06-142">The third ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing deletes the table used by the sample.</span></span>  
  
```  
use AdventureWorks  
go  
  
if exists (select name from sysobjects where name = 'MyTable')  
     drop table MyTable  
go  
  
create table MyTable  
(  
     col1  int,  
     col2  varchar(50),  
     col3  char(50),  
     col4  datetime,  
     col5  float,  
     col6  money,  
     col7  sql_variant,  
     col8  binary(50),  
     col9  text,  
     col10 image  
)  
go  
insert into MyTable  
values  
(  
     10,  
     'abcdefghijklmnopqrstuvwxyz',  
     'ABCDEFGHIJKLMNOPQRSTUVWXYZ',  
     '11/1/1999 11:52 AM',  
     3.14,  
     99.95,  
     convert(nchar(50), N'AbCdEfGhIjKlMnOpQrStUvWxYz'),  
     0x123456789,  
     replicate('AAAAABBBBB', 500),  
     replicate(0x123456789, 500)  
)  
Go  
```  
  
```  
// compile with: ole32.lib oleaut32.lib  
#define DBINITCONSTANTS  
#define OLEDBVER 0x0250   // to include correct interfaces  
  
#include <stdio.h>  
#include <windows.h>  
#include <iostream>  
#include <oledb.h>  
#include <sqlncli.h>  
  
using namespace std;  
  
int InitializeAndEstablishConnection();  
HRESULT GetColumnSize(IRow* pUnkRow, ULONG iCol);  
ULONG PrintData(ULONG iCols, ULONG iStart, DBCOLUMNINFO* prgInfo, DBCOLUMNACCESS* prgColumns);  
HRESULT GetColumns(IRow* pUnkRow, ULONG iStart, ULONG iEnd);  
  
IDBInitialize*       pIDBInitialize     = NULL;  
IDBProperties*       pIDBProperties     = NULL;  
IDBCreateSession*    pIDBCreateSession  = NULL;  
IDBCreateCommand*    pIDBCreateCommand  = NULL;  
ICommandText*        pICommandText      = NULL;  
IRow   *             pIRow              = NULL;  
DBCOLUMNINFO*        pDBColumnInfo      = NULL;  
IAccessor*           pIAccessor         = NULL;  
DBPROP               InitProperties[4];  
DBPROPSET            rgInitPropSet[1];  
ULONG                i, j;  
HRESULT              hresult;  
DBROWCOUNT           cNumRows = 0;  
ULONG                lNumCols;  
WCHAR*               pStringsBuffer;  
DBBINDING*           pBindings;  
ULONG                ConsumerBufColOffset = 0;  
HACCESSOR            hAccessor;  
ULONG                lNumRowsRetrieved;  
HROW                 hRows[10];  
HROW*                pRows = &hRows[0];  
  
int main() {  
   ULONG iidx = 0;  
   WCHAR* wCmdString = OLESTR(" SELECT * FROM MyTable");  
  
   // Call a function to initialize and establish connection.   
   if (InitializeAndEstablishConnection() == -1) {  
      cout << "Failed to initialize and establish connection.\n";  
      // Insert your code for cleanup and error handling.  
      return -1;  
   }  
  
   // Create a session object.  
   if (FAILED(pIDBInitialize->QueryInterface (   
      IID_IDBCreateSession, (void**) &pIDBCreateSession))) {  
      cout << "Failed to obtain IDBCreateSession interface.\n";  
      // Insert your code for cleanup and error handling.  
      return -1;  
   }  
  
   if (FAILED(pIDBCreateSession->CreateSession( NULL, IID_IDBCreateCommand, (IUnknown**) &pIDBCreateCommand))) {  
      cout << "pIDBCreateSession->CreateSession failed.\n";  
      // Insert your code for cleanup and error handling.  
      return -1;  
   }  
  
   // Access the ICommandText interface.  
   if (FAILED(pIDBCreateCommand->CreateCommand( NULL, IID_ICommandText, (IUnknown**) &pICommandText))) {  
      cout << "Failed to access ICommand interface.\n";  
      // Insert your code for cleanup and error handling.  
      return -1;  
   }  
  
   // Use SetCommandText() to specify the command text.  
   if (FAILED(pICommandText->SetCommandText(DBGUID_DBSQL, wCmdString))) {  
      cout << "Failed to set command text.\n";  
      // Insert your code for cleanup and error handling.  
      return -1;  
   }  
  
   // Fetch columns 1-5 and then 6-10 and display the contents  
   if (FAILED(hresult = pICommandText->Execute(NULL, IID_IRow, NULL, &cNumRows, (IUnknown **) &pIRow))) {  
      cout << "Failed to execute command.\n";  
      // Insert your code for cleanup and error handling.  
      return -1;  
   }  
  
   hresult = GetColumns(pIRow, 1, 5);  
   hresult = GetColumns(pIRow, 6, 10);  
  
   hresult = pIRow->Release();  
  
   // Execute the command.  
   if (FAILED(hresult = pICommandText->Execute(NULL, IID_IRow, NULL, &cNumRows, (IUnknown **) &pIRow))) {  
      cout << "Failed to execute command.\n";  
      // Insert your code for cleanup and error handling.  
      return -1;  
   }  
  
   // Get columns  
   for ( iidx = 1 ; iidx <= 10 ; iidx++ ) {  
      if (FAILED(hresult = GetColumnSize(pIRow, iidx))) {  
         cout << "Failed to get column size.\n";  
         // Insert your code for cleanup and error handling.     
         return -1;  
      }  
  
      hresult = GetColumns(pIRow, iidx, iidx);  
   }  
  
   pIRow->Release();  
  
   // Release memory.  
   pICommandText->Release();  
   pIDBCreateCommand->Release();  
   pIDBCreateSession->Release();  
  
   if (FAILED(pIDBInitialize->Uninitialize())) {  
      // Uninitialize not required, but fails if an interface has not been released.  Can be used for debugging.  
      cout << "Problem uninitializing.\n";  
   }  
  
   pIDBInitialize->Release();  
  
   // Release the COM library.  
   CoUninitialize();  
  
   return 0;  
};  
  
//--------------------------------------------------------------------  
BOOL InitColumn(DBCOLUMNACCESS* pCol, DBCOLUMNINFO* pInfo) {  
   // If text or image column is being read,in which case the max  possible length of a value is   
   // the column is hugh,we will limit that size to 512 bytes (for illustration purposes).  
   DBLENGTH ulSize = (pInfo->ulColumnSize < 0x7fffffff) ? pInfo->ulColumnSize : 512;  
  
   // Verify dta buffer is large enough.  
   if (pCol->cbMaxLen < (ulSize + 1)) {  
      if (pCol->pData) {  
         delete [] pCol->pData;  
         pCol->pData = NULL;  
      }  
  
      // Allocate data buffer  
      void * p = pCol->pData = new WCHAR[ulSize + 1];  
      if (!(p /* pCol->pData = new WCHAR[ulSize + 1] */ ))  
         return FALSE;  
  
      // set the max length of caller-initialized memory.  
      pCol->cbMaxLen = sizeof(WCHAR) * (ulSize + 1);  
  
      // In the above 2 steps, pData is pointing to memory (it is not NULL) and cbMaxLen has a value   
      // (not 0), so next call to IRow->GetData() will read the data from the column.  
   }  
  
   // Clear memory buffer  
   ZeroMemory((void*) pCol->pData, pCol->cbMaxLen);  
  
   // Set properties.  
   pCol->wType = DBTYPE_WSTR;  
   pCol->columnid = pInfo->columnid;  
   pCol->cbDataLen = 0;  
   pCol->dwStatus = 0;  
   pCol->dwReserved = 0;  
   pCol->bPrecision = 0;  
   pCol->bScale = 0;  
   return TRUE;  
}  
  
//--------------------------------------------------------------------  
HRESULT GetColumns(IRow* pUnkRow, ULONG iStart, ULONG iEnd) {  
// Start and end are same. Thus, get only one column.  
   HRESULT hr;  
   ULONG iidx;   // loop counter  
   DBORDINAL cColumns;   // Count of columns  
   ULONG cUserCols;   // Count of user columns  
  
   DBCOLUMNINFO* prgInfo;   // Column of info. array  
   OLECHAR* pColNames;   // Array of column names  
  
   DBCOLUMNACCESS* prgColumns;   // Ptr to column access structures array  
   DBCOLUMNINFO* pCurrInfo;  
   DBCOLUMNACCESS* pCurrCol;  
  
   IColumnsInfo* pIColumnsInfo = NULL;  
  
   // Initialize  
   cColumns = 0;  
   prgInfo = NULL;  
   pColNames = NULL;  
   prgColumns = NULL;  
  
   printf("Retrieving data\n");  
  
   // Get column info to build column access array  
   hr = pUnkRow->QueryInterface(IID_IColumnsInfo, (void**)&pIColumnsInfo);  
   if (FAILED(hr))  
      goto CLEANUP;  
   hr = pIColumnsInfo->GetColumnInfo(&cColumns, &prgInfo, &pColNames);  
   if (FAILED(hr))  
      goto CLEANUP;  
  
   printf("In GetColumns(), Columns= %d\n", cColumns);  
  
   // Determine no. of columns to retrieve. Since iEnd and iStart is same, this is redundent step.    
   // cUserCols will always be 1.  
   cUserCols = iEnd - iStart + 1;   
  
   // Walk list of columns and setup a DBCOLUMNACCESS structure  
   if (!(prgColumns= new DBCOLUMNACCESS[cUserCols])) {   // cUserCols is only 1  
      hr = E_FAIL;  
      goto CLEANUP;  
   }  
  
   ZeroMemory((void*) prgColumns, sizeof(DBCOLUMNACCESS) * cUserCols);  
  
   for ( iidx = 0 ; iidx < cUserCols ; iidx++ ) {  
      pCurrInfo = prgInfo + iidx + iStart - 1;  
      pCurrCol = prgColumns + iidx;  
  
      // Here the values of DBCOLUMNACCESS elements is set (pData and cbMaxLen)Thus IRow->GetColumns()   
      // will return actual data.  
      if (InitColumn(pCurrCol, pCurrInfo) == FALSE)  
         goto CLEANUP;  
   }  
  
   hr = pUnkRow->GetColumns(cUserCols, prgColumns);   // cUserCols = 1  
   if (FAILED(hr))  
      printf("Error occured\n");  
  
   // Show data.  
   PrintData(cUserCols, iStart, prgInfo, prgColumns);  
  
CLEANUP:  
   if (pIColumnsInfo)  
      pIColumnsInfo->Release();  
   if (prgColumns)  
      delete [] prgColumns;  
  
   return hr;  
}  
  
// This function returns the actual width of the data in the column (not the columnwidth in   
// DBCOLUMNFO structure which is the width of the column)  
HRESULT GetColumnSize(IRow* pUnkRow, ULONG iCol) {  
   HRESULT        hr = NOERROR;  
   DBORDINAL      cColumns = 0;   // Count the columns  
   DBCOLUMNINFO*  prgInfo;   // Column info array  
   OLECHAR*       pColNames;  
   DBCOLUMNACCESS column;  
   DBCOLUMNINFO*  pCurrInfo;  
   IColumnsInfo*  pIColumnsInfo = NULL;  
  
   // Initialize  
   prgInfo = NULL;  
   pColNames = NULL;  
  
   printf("Checking column size\n");  
  
   // Get column info to build column access array  
   hr = pUnkRow->QueryInterface(IID_IColumnsInfo, (void**) &pIColumnsInfo);  
   if (FAILED(hr))  
      goto CLEANUP;  
  
   hr = pIColumnsInfo->GetColumnInfo(&cColumns, &prgInfo, &pColNames);  
   if (FAILED(hr))  
      goto CLEANUP;  
   printf("Value of cColumns is %d\n", cColumns);  
  
   // Setup a DBCOLUMNACCESS structure: Here pData is set to NULL and cbMaxLen is set to 0. Thus   
   // IRow->GetColumns() returns only the actual column length in cbDataLen member of DBCOLUMNACCESS   
   // structure. In this case you can call IRow->GetColumns() again for the same  column to retrieve   
   // actual data in the second call.  
   ZeroMemory((void*) &column, sizeof(DBCOLUMNACCESS));  
   column.pData = NULL;  
  
   pCurrInfo = prgInfo + iCol - 1;  
  
   // Get the column id in DBCOLUMNACCESS structure. It is then used in GetColumn().  
   column.columnid = pCurrInfo->columnid;   
  
   printf("column.columnid value is %d\n", column.columnid);  
   // We know which column to get. The column.columnid gives the column no.  
   hr = pUnkRow->GetColumns(1, &column);   
   if (FAILED(hr))  
      printf("Errors occured\n");  
  
   // Show data  
   PrintData(1, iCol, prgInfo, &column);  
  
CLEANUP:  
   if (pIColumnsInfo)  
      pIColumnsInfo->Release();  
   return hr;  
}  
  
BOOL GetStatus(DWORD dwStatus, WCHAR* pwszStatus) {  
   switch (dwStatus) {  
   case DBSTATUS_S_OK:  
      wcscpy_s(pwszStatus, 255, L"DBSTATUS_S_OK");  
      break;  
   case DBSTATUS_E_UNAVAILABLE:  
      wcscpy_s(pwszStatus, 255, L"DBSTATUS_E_UNAVAILABLE");  
      break;  
   case DBSTATUS_S_TRUNCATED:  
      wcscpy_s(pwszStatus, 255, L"DBSTATUS_S_TRUNCATED");  
      break;  
   }  
   return TRUE;  
}  
  
ULONG PrintData(ULONG iCols, ULONG iStart, DBCOLUMNINFO* prgInfo, DBCOLUMNACCESS* prgColumns) {  
   WCHAR wszStatus[255];  
   DBCOLUMNINFO* pCurrInfo;  
   DBCOLUMNACCESS* pCurrCol;  
   ULONG iidx;  
  
   printf("No. Name       Status     Length  Max  Data\n");  
  
   for ( iidx = 0 ; iidx < iCols ; iidx++ ) {  
      pCurrInfo = prgInfo + iidx + iStart - 1;  
      pCurrCol = prgColumns + iidx;  
  
      GetStatus(pCurrCol->dwStatus, wszStatus);   
      // was the data successfully retrieved?  
      wprintf(L"%-3d %-*s %-20s %-3d %-3d %-20s\n", iStart+iidx,   
                                                    10,   
                                                    pCurrInfo->pwszName,   
                                                    wszStatus,  
                                                    pCurrCol->cbDataLen,  
                                                    pCurrCol->cbMaxLen,  
                                                    (WCHAR*) pCurrCol->pData);  
   }  
  
   wprintf(L"\n");  
   return iidx;  
}  
  
int InitializeAndEstablishConnection() {      
   // Initialize the COM library.  
   CoInitialize(NULL);  
  
   // Obtain access to the SQLNCLI provider.  
   hresult = CoCreateInstance(CLSID_SQLNCLI11,  
                              NULL,  
                              CLSCTX_INPROC_SERVER,  
                              IID_IDBInitialize,  
                              (void **) &pIDBInitialize);  
  
   if (FAILED(hresult)) {  
      printf("Failed to get IDBInitialize interface.\n");  
      // Insert your code for cleanup and error handling.  
      return -1;  
   }  
  
   // Initialize the property values needed to establish the connection.  
   for ( i = 0 ; i < 4 ; i++ )   
      VariantInit(&InitProperties[i].vValue);  
  
   // Server name.  
   InitProperties[0].dwPropertyID  = DBPROP_INIT_DATASOURCE;  
   InitProperties[0].vValue.vt     = VT_BSTR;  
  
   InitProperties[0].vValue.bstrVal= SysAllocString(L"(local)");  
   InitProperties[0].dwOptions     = DBPROPOPTIONS_REQUIRED;  
   InitProperties[0].colid         = DB_NULLID;  
  
   // Database.  
   InitProperties[1].dwPropertyID  = DBPROP_INIT_CATALOG;  
   InitProperties[1].vValue.vt     = VT_BSTR;  
   InitProperties[1].vValue.bstrVal= SysAllocString(L"AdventureWorks");  
   InitProperties[1].dwOptions     = DBPROPOPTIONS_REQUIRED;  
   InitProperties[1].colid         = DB_NULLID;  
  
   InitProperties[2].dwPropertyID  = DBPROP_AUTH_INTEGRATED;  
   InitProperties[2].vValue.vt     = VT_BSTR;  
   InitProperties[2].vValue.bstrVal= SysAllocString(L"SSPI");  
   InitProperties[2].dwOptions     = DBPROPOPTIONS_REQUIRED;  
   InitProperties[2].colid         = DB_NULLID;  
  
   // Now that the properties are set, construct the DBPROPSET structure (rgInitPropSet). The DBPROPSET   
   // structure is used to pass an array of DBPROP structures (InitProperties) to the SetProperties method.  
   rgInitPropSet[0].guidPropertySet= DBPROPSET_DBINIT;  
   rgInitPropSet[0].cProperties    = 4;  
   rgInitPropSet[0].rgProperties   = InitProperties;  
  
   // Set initialization properties.  
   hresult = pIDBInitialize->QueryInterface(IID_IDBProperties, (void **)&pIDBProperties);  
   if (FAILED(hresult)) {  
      cout << "Failed to get IDBProperties interface.\n";  
      // Insert your code for cleanup and error handling.  
      return -1;  
   }  
  
   hresult = pIDBProperties->SetProperties(1, rgInitPropSet);   
   if (FAILED(hresult)) {  
      cout << "Failed to set initialization properties.\n";  
      // Insert your code for cleanup and error handling.  
      return -1;  
   }  
  
   pIDBProperties->Release();  
  
   // Now establish the connection to the data source.  
   if (FAILED(pIDBInitialize->Initialize()))  
      cout << "Problem establishing connection to the data source.\n";  
  
   return 0;  
}  
```  
  
```  
use AdventureWorks  
go  
  
if exists (select name from sysobjects where name = 'MyTable')  
     drop table MyTable  
go  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ac06-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2ac06-143">See Also</span></span>  
 [<span data-ttu-id="2ac06-144">Rubriques de procédures liées à OLE DB</span><span class="sxs-lookup"><span data-stu-id="2ac06-144">OLE DB How-to Topics</span></span>](ole-db-how-to-topics.md)  
  
  
