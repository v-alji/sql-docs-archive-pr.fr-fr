---
title: Énumérer des sources de données OLE DB (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data sources [OLE DB]
ms.assetid: ba240060-3237-4fb8-b2fb-b87fda2b1e7a
author: rothja
ms.author: jroth
ms.openlocfilehash: 1173feef8de657c43563b40bec763f81d630014e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707484"
---
# <a name="enumerate-ole-db-data-sources-ole-db"></a><span data-ttu-id="d6dd8-102">Énumérer des sources de données OLE DB (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="d6dd8-102">Enumerate OLE DB Data Sources (OLE DB)</span></span>
  <span data-ttu-id="d6dd8-103">Cet exemple montre comment utiliser l'objet énumérateur pour répertorier les sources de données disponibles.</span><span class="sxs-lookup"><span data-stu-id="d6dd8-103">This sample shows how to use the enumerator object to list the data sources available.</span></span>  
  
 <span data-ttu-id="d6dd8-104">Pour répertorier les sources de données visibles pour l'énumérateur SQLOLEDB, le consommateur appelle la méthode [ISourcesRowset::GetSourcesRowset](https://go.microsoft.com/fwlink/?LinkId=120312) .</span><span class="sxs-lookup"><span data-stu-id="d6dd8-104">To list the data sources visible to the SQLOLEDB enumerator, the consumer calls the [ISourcesRowset::GetSourcesRowset](https://go.microsoft.com/fwlink/?LinkId=120312) method.</span></span> <span data-ttu-id="d6dd8-105">Cette méthode retourne un ensemble de lignes dotées d'informations sur les sources de données actuellement visibles.</span><span class="sxs-lookup"><span data-stu-id="d6dd8-105">This method returns a rowset of information about the currently visible data sources.</span></span>  
  
 <span data-ttu-id="d6dd8-106">Selon la bibliothèque réseau utilisée, le système recherche les sources de données dans le domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="d6dd8-106">Depending on the network library used, the appropriate domain is searched for the data sources.</span></span> <span data-ttu-id="d6dd8-107">Pour les canaux nommés, il s'agit du domaine auquel le client est connecté.</span><span class="sxs-lookup"><span data-stu-id="d6dd8-107">For named pipes, it is the domain to which the client is logged on.</span></span> <span data-ttu-id="d6dd8-108">Pour AppleTalk, il s'agit de la zone par défaut.</span><span class="sxs-lookup"><span data-stu-id="d6dd8-108">For AppleTalk, it is the default zone.</span></span> <span data-ttu-id="d6dd8-109">Pour SPX/IPX, il s'agit de la liste des installations [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disponibles dans la base de données Bindery.</span><span class="sxs-lookup"><span data-stu-id="d6dd8-109">For SPX/IPX, it is the list of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installations found in the bindery.</span></span> <span data-ttu-id="d6dd8-110">Pour BANYAN VINES, il s'agit des installations [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disponibles dans le réseau local.</span><span class="sxs-lookup"><span data-stu-id="d6dd8-110">For Banyan VINES, it is the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installations found on the local network.</span></span> <span data-ttu-id="d6dd8-111">Les sockets Multiprotocol et TCP/IP ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="d6dd8-111">Multiprotocol and TCP/IP sockets are not supported.</span></span>  
  
 <span data-ttu-id="d6dd8-112">Lorsque le serveur est désactivé ou activé, la mise à jour des informations dans ces domaines peut prendre un moment.</span><span class="sxs-lookup"><span data-stu-id="d6dd8-112">When the server is turned off or on, it can take few minutes to update the information in these domains.</span></span>  
  
 <span data-ttu-id="d6dd8-113">Cet exemple requiert l'exemple de base de données AdventureWorks, que vous pouvez télécharger à partir de la page d'accueil des [exemples et projets de communautés Microsoft SQL Server](https://go.microsoft.com/fwlink/?LinkID=85384) .</span><span class="sxs-lookup"><span data-stu-id="d6dd8-113">This sample requires the AdventureWorks sample database, which you can download from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d6dd8-114">Lorsque c'est possible, utilisez l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="d6dd8-114">When possible, use Windows Authentication.</span></span> <span data-ttu-id="d6dd8-115">Si l'authentification Windows n'est pas disponible, invitez les utilisateurs à entrer leurs informations d'identification au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="d6dd8-115">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="d6dd8-116">Évitez de stocker ces informations dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="d6dd8-116">Avoid storing credentials in a file.</span></span> <span data-ttu-id="d6dd8-117">Si vous devez conserver des informations d’identification, vous devez les chiffrer avec l' [API de chiffrement Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="d6dd8-117">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-enumerate-ole-db-data-sources"></a><span data-ttu-id="d6dd8-118">Pour énumérer des sources de données OLE DB</span><span class="sxs-lookup"><span data-stu-id="d6dd8-118">To enumerate OLE DB data sources</span></span>  
  
1.  <span data-ttu-id="d6dd8-119">Appelez `ISourceRowset::GetSourcesRowset` pour extraire l'ensemble de lignes source.</span><span class="sxs-lookup"><span data-stu-id="d6dd8-119">Retrieve the source rowset by calling `ISourceRowset::GetSourcesRowset`.</span></span>  
  
2.  <span data-ttu-id="d6dd8-120">Appelez `GetColumnInfo::IColumnInfo` pour rechercher la description de l'ensemble de lignes des énumérateurs.</span><span class="sxs-lookup"><span data-stu-id="d6dd8-120">Find the description of the enumerators rowset by calling `GetColumnInfo::IColumnInfo`.</span></span>  
  
3.  <span data-ttu-id="d6dd8-121">Créez les structures de liaison à partir des informations sur les colonnes.</span><span class="sxs-lookup"><span data-stu-id="d6dd8-121">Create the binding structures from the column information.</span></span>  
  
4.  <span data-ttu-id="d6dd8-122">Appelez `IAccessor::CreateAccessor` pour créer l'accesseur de l'ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="d6dd8-122">Create the rowset accessor by calling `IAccessor::CreateAccessor`.</span></span>  
  
5.  <span data-ttu-id="d6dd8-123">Appelez `IRowset::GetNextRows` pour extraire les lignes.</span><span class="sxs-lookup"><span data-stu-id="d6dd8-123">Fetch the rows by calling `IRowset::GetNextRows`.</span></span>  
  
6.  <span data-ttu-id="d6dd8-124">Appelez `IRowset::GetData` pour récupérer les données de la copie de l'ensemble de lignes de la ligne et traiter ces données.</span><span class="sxs-lookup"><span data-stu-id="d6dd8-124">Retrieve data from the rowset's copy of the row by calling `IRowset::GetData`, and process it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6dd8-125">Exemple</span><span class="sxs-lookup"><span data-stu-id="d6dd8-125">Example</span></span>  
 <span data-ttu-id="d6dd8-126">Compilez avec ole32.lib et exécutez le code C++ suivant.</span><span class="sxs-lookup"><span data-stu-id="d6dd8-126">Compile with ole32.lib and execute the following C++ code listing.</span></span> <span data-ttu-id="d6dd8-127">Cette application vous permet de vous connecter à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] par défaut de votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="d6dd8-127">This application connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="d6dd8-128">Sur certains systèmes d'exploitation Windows, vous devrez remplacer (localhost) ou (local) par le nom de votre instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d6dd8-128">On some Windows operating systems, you will need to change (localhost) or (local) to the name of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="d6dd8-129">Pour vous connecter à une instance nommée, changez la chaîne de connexion de L"(local)" en L"(local)\\\nom", où nom correspond à l’instance nommée.</span><span class="sxs-lookup"><span data-stu-id="d6dd8-129">To connect to a named instance, change the connection string from L"(local)" to L"(local)\\\name" , where name is the named instance.</span></span> <span data-ttu-id="d6dd8-130">Par défaut, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express est installé dans une instance nommée.</span><span class="sxs-lookup"><span data-stu-id="d6dd8-130">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express installs to a named instance.</span></span> <span data-ttu-id="d6dd8-131">Assurez-vous que votre variable d'environnement INCLUDE inclut le répertoire qui contient sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="d6dd8-131">Make sure your INCLUDE environment variable includes the directory that contains sqlncli.h.</span></span>  
  
```  
// compile with: ole32.lib  
#define UNICODE  
#define _UNICODE  
#define DBINITCONSTANTS  
#define INITGUID  
#define OLEDBVER 0x0250   // to include correct interfaces  
  
#include <windows.h>  
#include <stddef.h>  
#include <oledb.h>  
#include <oledberr.h>  
#include <sqlncli.h>  
#include <stdio.h>  
  
#define NUMROWS_CHUNK  5  
  
// AdjustLen supports binding on four-byte boundaries.  
_inline DBLENGTH AdjustLen(DBLENGTH cb) {   
   return ( (cb + 3) & ~3 );  
}  
  
// Get the characteristics of the rowset (the IColumnsInfo interface).  
HRESULT GetColumnInfo ( IRowset* pIRowset,   
                        DBORDINAL* pnCols,   
                        DBCOLUMNINFO** ppColumnsInfo,  
                        OLECHAR** ppColumnStrings ) {  
   IColumnsInfo* pIColumnsInfo;  
   HRESULT hr;  
  
   *pnCols = 0;  
   if (FAILED(pIRowset->QueryInterface(IID_IColumnsInfo, (void**) &pIColumnsInfo)))  
      return (E_FAIL);  
  
   hr = pIColumnsInfo->GetColumnInfo(pnCols, ppColumnsInfo, ppColumnStrings);  
  
   if (FAILED(hr)) {}   /* Process error */   
  
   pIColumnsInfo->Release();  
   return (hr);  
}  
  
// Create binding structures from column information. Binding structures  
// will be used to create an accessor that allows row value retrieval.  
void CreateDBBindings ( DBORDINAL nCols,   
                        DBCOLUMNINFO* pColumnsInfo,   
                        DBBINDING** ppDBBindings,  
                        BYTE** ppRowValues ) {  
   ULONG nCol;  
   DBLENGTH cbRow = 0;  
   DBLENGTH cbCol;  
   DBBINDING* pDBBindings;  
   BYTE* pRowValues;  
  
   pDBBindings = new DBBINDING[nCols];  
   if (!(pDBBindings /* = new DBBINDING[nCols] */ ))  
      return;  
  
   for ( nCol = 0 ; nCol < nCols ; nCol++ ) {  
      pDBBindings[nCol].iOrdinal = nCol + 1;  
      pDBBindings[nCol].pTypeInfo = NULL;  
      pDBBindings[nCol].pObject = NULL;  
      pDBBindings[nCol].pBindExt = NULL;  
      pDBBindings[nCol].dwPart = DBPART_VALUE;  
      pDBBindings[nCol].dwMemOwner = DBMEMOWNER_CLIENTOWNED;  
      pDBBindings[nCol].eParamIO = DBPARAMIO_NOTPARAM;  
      pDBBindings[nCol].dwFlags = 0;  
      pDBBindings[nCol].wType = pColumnsInfo[nCol].wType;  
      pDBBindings[nCol].bPrecision = pColumnsInfo[nCol].bPrecision;  
      pDBBindings[nCol].bScale = pColumnsInfo[nCol].bScale;  
  
      cbCol = pColumnsInfo[nCol].ulColumnSize;  
  
      switch (pColumnsInfo[nCol].wType) {  
      case DBTYPE_STR: {  
            cbCol += 1;  
            break;  
         }  
  
      case DBTYPE_WSTR: {  
            cbCol = (cbCol + 1) * sizeof(WCHAR);  
            break;  
         }  
  
      default:  
         break;  
      }  
  
      pDBBindings[nCol].obValue = cbRow;  
      pDBBindings[nCol].cbMaxLen = cbCol;  
      cbRow += AdjustLen(cbCol);  
   }  
  
   pRowValues = new BYTE[cbRow];  
   *ppDBBindings = pDBBindings;  
   *ppRowValues = pRowValues;  
}  
  
int main() {  
   ISourcesRowset* pISourceRowset = NULL;      
   IRowset* pIRowset = NULL;          
   IAccessor* pIAccessor = NULL;  
   DBBINDING* pDBBindings = NULL;              
  
   HROW* pRows = new HROW[500];      
   HACCESSOR hAccessorRetrieve = NULL;          
   ULONG DSSeqNumber = 0;  
  
   HRESULT hr;  
   DBORDINAL nCols;  
   DBCOLUMNINFO* pColumnsInfo = NULL;  
   OLECHAR* pColumnStrings = NULL;  
   DBBINDSTATUS* pDBBindStatus = NULL;  
  
   BYTE* pRowValues = NULL;  
   DBCOUNTITEM cRowsObtained;  
   ULONG iRow;  
   char* pMultiByte = NULL;  
   short* psSourceType = NULL;  
   BYTE* pDatasource = NULL;  
  
   if (!pRows)  
      return (0);  
  
   // Initialize COM library.  
   CoInitialize(NULL);  
  
   // Initialize the enumerator.  
   if (FAILED(CoCreateInstance(CLSID_SQLNCLI11_ENUMERATOR,   
                               NULL,  
                               CLSCTX_INPROC_SERVER,   
                               IID_ISourcesRowset,   
                               (void**)&pISourceRowset))) {  
      // Process error.  
      return TRUE;  
   }  
  
   // Retrieve the source rowset.  
   hr = pISourceRowset->GetSourcesRowset(NULL, IID_IRowset, 0, NULL, (IUnknown**)&pIRowset);  
  
   pISourceRowset->Release();  
   if (FAILED(hr)) {  
      // Process error.  
      return TRUE;  
   }  
  
   // Get the description of the enumerator's rowset.  
   if (FAILED(hr = GetColumnInfo(pIRowset, &nCols, &pColumnsInfo, &pColumnStrings))) {  
      // Process error.  
      goto SAFE_EXIT;  
   }  
  
   // Create the binding structures.  
   CreateDBBindings(nCols, pColumnsInfo, &pDBBindings, &pRowValues);  
   pDBBindStatus = new DBBINDSTATUS[nCols];  
  
   if (sizeof(TCHAR) != sizeof(WCHAR))  
      pMultiByte = new char[pDBBindings[0].cbMaxLen];  
  
   if (FAILED(pIRowset->QueryInterface(IID_IAccessor, (void**)&pIAccessor))) {  
      // Process error.  
      goto SAFE_EXIT;  
   }  
  
   // Create the rowset accessor.  
   if (FAILED(hr = pIAccessor->CreateAccessor(DBACCESSOR_ROWDATA,   
                                              nCols,  
                                              pDBBindings,   
                                              0,   
                                              &hAccessorRetrieve,   
                                              pDBBindStatus))) {  
      // Process error.  
      goto SAFE_EXIT;  
   }  
  
   // Process all the rows, NUMROWS_CHUNK rows at a time.  
   while (SUCCEEDED(hr)) {  
      hr = pIRowset->GetNextRows(NULL, 0, NUMROWS_CHUNK, &cRowsObtained, &pRows);  
      if( FAILED(hr)) {  
         // process error  
      }  
      if (cRowsObtained == 0 || FAILED(hr))  
         break;  
  
      for (iRow = 0 ; iRow < cRowsObtained ; iRow++) {  
         // Get the rowset data.  
         if (SUCCEEDED(hr = pIRowset->GetData(pRows[iRow], hAccessorRetrieve, pRowValues))) {  
            psSourceType = (short *)(pRowValues + pDBBindings[3].obValue);  
  
            if (*psSourceType == DBSOURCETYPE_DATASOURCE) {  
               DSSeqNumber = DSSeqNumber + 1;   // Data source counter.  
               pDatasource = (pRowValues + pDBBindings[0].obValue);  
  
               if ( sizeof(TCHAR) != sizeof(WCHAR) ) {  
                  WideCharToMultiByte(CP_ACP,   
                                      0,  
                                      (WCHAR*)pDatasource,   
                                      -1,   
                                      pMultiByte,  
                                      static_cast<int>(pDBBindings[0].cbMaxLen),   
                                      NULL,   
                                      NULL);  
  
                  printf( "DataSource# %d\tName: %S\n",   
                          DSSeqNumber,   
                          (WCHAR *) pMultiByte );  
               }  
               else {  
                  printf( "DataSource# %d\tName: %S\n",   
                          DSSeqNumber,   
                          (WCHAR *) pDatasource );  
               }  
            }  
         }  
      }  
      pIRowset->ReleaseRows(cRowsObtained, pRows, NULL, NULL, NULL);  
   }  
  
   // Release COM library.  
   CoUninitialize();  
  
SAFE_EXIT:  
   // Do the clean-up.  
   return TRUE;  
}  
```  
  
  
