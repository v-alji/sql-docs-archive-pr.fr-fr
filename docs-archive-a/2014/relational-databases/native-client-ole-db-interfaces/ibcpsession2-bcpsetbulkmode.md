---
title: IBCPSession2::BCPSetBulkMode | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- BCPSetBulkMode function
ms.assetid: babba19f-e67b-450c-b0e6-523a0f9d23ab
author: rothja
ms.author: jroth
ms.openlocfilehash: 9605ff9b8effde1b4a77ba0d8554c719a8a8d1e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613453"
---
# <a name="ibcpsession2bcpsetbulkmode"></a><span data-ttu-id="e59b7-102">IBCPSession2::BCPSetBulkMode</span><span class="sxs-lookup"><span data-stu-id="e59b7-102">IBCPSession2::BCPSetBulkMode</span></span>
  <span data-ttu-id="e59b7-103">IBCPSession2::BCPSetBulkMode fournit une alternative à [IBCPSession::BCPColFmt &#40;OLE DB&#41;](ibcpsession-bcpcolfmt-ole-db.md) pour spécifier le format de colonne.</span><span class="sxs-lookup"><span data-stu-id="e59b7-103">IBCPSession2::BCPSetBulkMode provides an alternative to [IBCPSession::BCPColFmt &#40;OLE DB&#41;](ibcpsession-bcpcolfmt-ole-db.md) for specifying the column format.</span></span> <span data-ttu-id="e59b7-104">Contrairement à IBCPSession::BCPColFmt, qui définit des attributs de format de colonne individuels, IBCPSession2::BCPSetBulkMode définit tous les attributs.</span><span class="sxs-lookup"><span data-stu-id="e59b7-104">Unlike IBCPSession::BCPColFmt, which sets individual column format attributes, IBCPSession2::BCPSetBulkMode sets all attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e59b7-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e59b7-105">Syntax</span></span>  
  
```  
  
HRESULT BCPSetBulkMode (  
      int property,  
   void * pField,  
   int cbField,  
   void * pRow,  
   int cbRow  
);  
```  
  
## <a name="arguments"></a><span data-ttu-id="e59b7-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="e59b7-106">Arguments</span></span>  
 <span data-ttu-id="e59b7-107">*property*</span><span class="sxs-lookup"><span data-stu-id="e59b7-107">*property*</span></span>  
 <span data-ttu-id="e59b7-108">Constante de type BYTE.</span><span class="sxs-lookup"><span data-stu-id="e59b7-108">A constant of type BYTE.</span></span> <span data-ttu-id="e59b7-109">Consultez le tableau dans la section Notes pour obtenir une liste des constantes.</span><span class="sxs-lookup"><span data-stu-id="e59b7-109">See the table in the Remarks section for a list of the constants.</span></span>  
  
 <span data-ttu-id="e59b7-110">*pField*</span><span class="sxs-lookup"><span data-stu-id="e59b7-110">*pField*</span></span>  
 <span data-ttu-id="e59b7-111">Pointeur vers la valeur de marque de fin de champ.</span><span class="sxs-lookup"><span data-stu-id="e59b7-111">The pointer to the field terminator value.</span></span>  
  
 <span data-ttu-id="e59b7-112">cbField</span><span class="sxs-lookup"><span data-stu-id="e59b7-112">cbField</span></span>  
 <span data-ttu-id="e59b7-113">Longueur, en octets, de la valeur de marque de fin de champ.</span><span class="sxs-lookup"><span data-stu-id="e59b7-113">The length in bytes of the field terminator value.</span></span>  
  
 <span data-ttu-id="e59b7-114">pRow</span><span class="sxs-lookup"><span data-stu-id="e59b7-114">pRow</span></span>  
 <span data-ttu-id="e59b7-115">Pointeur vers la valeur de marque de fin de ligne.</span><span class="sxs-lookup"><span data-stu-id="e59b7-115">The pointer to the row terminator value.</span></span>  
  
 <span data-ttu-id="e59b7-116">cbRow</span><span class="sxs-lookup"><span data-stu-id="e59b7-116">cbRow</span></span>  
 <span data-ttu-id="e59b7-117">Longueur, en octets, de la valeur de marque de fin de ligne.</span><span class="sxs-lookup"><span data-stu-id="e59b7-117">The length in bytes of the row terminator value.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="e59b7-118">Retours</span><span class="sxs-lookup"><span data-stu-id="e59b7-118">Returns</span></span>  
 <span data-ttu-id="e59b7-119">IBCPSession2::BCPSetBulkMode peut retourner l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="e59b7-119">IBCPSession2::BCPSetBulkMode can return one of the following:</span></span>  
  
|||  
|-|-|  
|`S_OK`|<span data-ttu-id="e59b7-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="e59b7-120">The method succeeded.</span></span>|  
|`E_FAIL`|<span data-ttu-id="e59b7-121">Une erreur spécifique au fournisseur s’est produite. Pour obtenir des informations détaillées, utilisez l’interface ISQLServerErrorInfo.</span><span class="sxs-lookup"><span data-stu-id="e59b7-121">A provider specific error occurred, for detailed information use the ISQLServerErrorInfo interface.</span></span>|  
|`E_UNEXPECTED`|<span data-ttu-id="e59b7-122">L'appel à la méthode était inattendu.</span><span class="sxs-lookup"><span data-stu-id="e59b7-122">The call to the method was unexpected.</span></span> <span data-ttu-id="e59b7-123">Par exemple, la `IBCPSession2::BCPInit` méthode n’a pas été appelée avant d’appeler IBCPSession2 :: BCPSetBulkMode.</span><span class="sxs-lookup"><span data-stu-id="e59b7-123">For example, the `IBCPSession2::BCPInit` method was not called before calling IBCPSession2::BCPSetBulkMode.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="e59b7-124">L'argument n'était pas valide.</span><span class="sxs-lookup"><span data-stu-id="e59b7-124">The argument was invalid.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="e59b7-125">Erreur de mémoire insuffisante.</span><span class="sxs-lookup"><span data-stu-id="e59b7-125">Out of memory error.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e59b7-126">Notes</span><span class="sxs-lookup"><span data-stu-id="e59b7-126">Remarks</span></span>  
 <span data-ttu-id="e59b7-127">IBCPSession2::BCPSetBulkMode peut être utilisé pour créer une copie en bloc à partir d’une requête ou d’une table.</span><span class="sxs-lookup"><span data-stu-id="e59b7-127">IBCPSession2::BCPSetBulkMode can be used to bulk copy out of either a query or a table.</span></span> <span data-ttu-id="e59b7-128">Lorsque IBCPSession2::BCPSetBulkMode est utilisé pour copier en bloc une instruction de requête, il doit être appelé avant d’appeler `IBCPSession::BCPControl(BCP_OPTIONS_HINTS, ...)` pour spécifier l’instruction de requête.</span><span class="sxs-lookup"><span data-stu-id="e59b7-128">When IBCPSession2::BCPSetBulkMode is used to bulk copy out of a query statement, it must be called before calling `IBCPSession::BCPControl(BCP_OPTIONS_HINTS, ...)` to specify the query statement.</span></span>  
  
 <span data-ttu-id="e59b7-129">Vous devez éviter de combiner la syntaxe d'appel RPC avec la syntaxe de requête de lot (`{rpc func};SELECT * from Tbl`, par exemple) dans un texte de commande simple.</span><span class="sxs-lookup"><span data-stu-id="e59b7-129">You should avoid combining RPC call syntax with batch query syntax (`{rpc func};SELECT * from Tbl`, for example) in a single command text.</span></span>  <span data-ttu-id="e59b7-130">Cela entraînera le retour par ICommandPrepare::Prepare d'une erreur et vous empêchera de récupérer des métadonnées.</span><span class="sxs-lookup"><span data-stu-id="e59b7-130">This will cause ICommandPrepare::Prepare to return an error and prevent you from retrieving metadata.</span></span> <span data-ttu-id="e59b7-131">Utilisez la syntaxe ODBC CALL (`{call func}; SELECT * from Tbl`, par exemple) si vous devez combiner l'exécution d'une procédure stockée et une requête de lot dans un texte de commande simple.</span><span class="sxs-lookup"><span data-stu-id="e59b7-131">Use ODBC CALL syntax (`{call func}; SELECT * from Tbl`, for example) if you need to combine stored procedure execution and batch query in a single command text.</span></span>  
  
 <span data-ttu-id="e59b7-132">Le tableau suivant répertorie les constantes du paramètre *property* .</span><span class="sxs-lookup"><span data-stu-id="e59b7-132">The following table lists the constants for the *property* parameter.</span></span>  
  
|<span data-ttu-id="e59b7-133">Propriété</span><span class="sxs-lookup"><span data-stu-id="e59b7-133">Property</span></span>|<span data-ttu-id="e59b7-134">Description</span><span class="sxs-lookup"><span data-stu-id="e59b7-134">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="e59b7-135">BCP_OUT_CHARACTER_MODE</span><span class="sxs-lookup"><span data-stu-id="e59b7-135">BCP_OUT_CHARACTER_MODE</span></span>|<span data-ttu-id="e59b7-136">Spécifie le mode de sortie de caractères.</span><span class="sxs-lookup"><span data-stu-id="e59b7-136">Specifies character output mode.</span></span><br /><br /> <span data-ttu-id="e59b7-137">Correspond à l’option-c dans BCP.EXE, et à IBCPSession :: BCPColFmt avec la propriété *eUserDataType* définie sur `BCP_TYPE_SQLCHARACTER` .</span><span class="sxs-lookup"><span data-stu-id="e59b7-137">Corresponds to the -c option in BCP.EXE, and to IBCPSession::BCPColFmt with *eUserDataType* property set to `BCP_TYPE_SQLCHARACTER`.</span></span>|  
|<span data-ttu-id="e59b7-138">BCP_OUT_WIDE_CHARACTER_MODE</span><span class="sxs-lookup"><span data-stu-id="e59b7-138">BCP_OUT_WIDE_CHARACTER_MODE</span></span>|<span data-ttu-id="e59b7-139">Spécifie le mode de sortie Unicode.</span><span class="sxs-lookup"><span data-stu-id="e59b7-139">Specifies Unicode output mode.</span></span><br /><br /> <span data-ttu-id="e59b7-140">Correspond à l’option-w dans BCP.EXE et IBCPSession :: BCPColFmt avec la propriété *eUserDataType* définie sur `BCP_TYPE_SQLNCHAR` .</span><span class="sxs-lookup"><span data-stu-id="e59b7-140">Corresponds to the -w option in BCP.EXE and IBCPSession::BCPColFmt with *eUserDataType* property set to `BCP_TYPE_SQLNCHAR`.</span></span>|  
|<span data-ttu-id="e59b7-141">BCP_OUT_NATIVE_TEXT_MODE</span><span class="sxs-lookup"><span data-stu-id="e59b7-141">BCP_OUT_NATIVE_TEXT_MODE</span></span>|<span data-ttu-id="e59b7-142">Spécifie des types natifs pour les types de non-caractères et Unicode pour les types de caractères.</span><span class="sxs-lookup"><span data-stu-id="e59b7-142">Specifies native types for non-character types and Unicode for character types.</span></span><br /><br /> <span data-ttu-id="e59b7-143">Correspond à l’option-N dans BCP.EXE et IBCPSession :: BCPColFmt avec la propriété *eUserDataType* définie sur `BCP_TYPE_SQLNCHAR` si le type de colonne est une chaîne ou `BCP_TYPE_DEFAULT` s’il ne s’agit pas d’une chaîne.</span><span class="sxs-lookup"><span data-stu-id="e59b7-143">Corresponds to the -N option in BCP.EXE and IBCPSession::BCPColFmt with *eUserDataType* property set to `BCP_TYPE_SQLNCHAR` if the column type is a string or `BCP_TYPE_DEFAULT` if not a string.</span></span>|  
|<span data-ttu-id="e59b7-144">BCP_OUT_NATIVE_MODE</span><span class="sxs-lookup"><span data-stu-id="e59b7-144">BCP_OUT_NATIVE_MODE</span></span>|<span data-ttu-id="e59b7-145">Spécifie les types de base de données natifs.</span><span class="sxs-lookup"><span data-stu-id="e59b7-145">Specifies native database types.</span></span><br /><br /> <span data-ttu-id="e59b7-146">Correspond à l’option-n dans BCP.EXE et IBCPSession :: BCPColFmt avec la propriété *eUserDataType* définie sur `BCP_TYPE_DEFAULT` .</span><span class="sxs-lookup"><span data-stu-id="e59b7-146">Corresponds to the -n option in BCP.EXE and IBCPSession::BCPColFmt with *eUserDataType* property set to `BCP_TYPE_DEFAULT`.</span></span>|  
  
 <span data-ttu-id="e59b7-147">Vous pouvez appeler IBCPSession::BCPControl et IBCPSession2::BCPSetBulkMode pour les options IBCPSession::BCPControl qui ne sont pas en conflit avec IBCPSession2::BCPSetBulkMode.</span><span class="sxs-lookup"><span data-stu-id="e59b7-147">You can call IBCPSession::BCPControl and IBCPSession2::BCPSetBulkMode for IBCPSession::BCPControl options that do not conflict with IBCPSession2::BCPSetBulkMode.</span></span> <span data-ttu-id="e59b7-148">Par exemple, vous pouvez appeler IBCPSession :: BCPControl avec `BCP_OPTION_FIRST` et IBCPSession2 :: BCPSetBulkMode.</span><span class="sxs-lookup"><span data-stu-id="e59b7-148">For example, you can call IBCPSession::BCPControl with `BCP_OPTION_FIRST` and IBCPSession2::BCPSetBulkMode.</span></span>  
  
 <span data-ttu-id="e59b7-149">Vous ne pouvez pas appeler IBCPSession :: BCPControl avec `BCP_OPTION_TEXTFILE` et IBCPSession2 :: BCPSetBulkMode.</span><span class="sxs-lookup"><span data-stu-id="e59b7-149">You cannot call IBCPSession::BCPControl with `BCP_OPTION_TEXTFILE` and IBCPSession2::BCPSetBulkMode.</span></span>  
  
 <span data-ttu-id="e59b7-150">Si vous tentez d’appeler IBCPSession2::BCPSetBulkMode avec une séquence d’appels de fonction qui comprend IBCPSession::BCPColFmt, IBCPSession::BCPControl et IBCPSession::BCPReadFmt, l’un des appels de fonction retourne un échec d’erreur de séquence.</span><span class="sxs-lookup"><span data-stu-id="e59b7-150">If you attempt to call IBCPSession2::BCPSetBulkMode with a sequence of function calls that includes IBCPSession::BCPColFmt, IBCPSession::BCPControl, and IBCPSession::BCPReadFmt, one of the function calls will return a sequence error failure.</span></span> <span data-ttu-id="e59b7-151">Si vous choisissez de corriger l’échec, appelez IBCPSession::BCPInit pour réinitialiser les paramètres et recommencer.</span><span class="sxs-lookup"><span data-stu-id="e59b7-151">If you choose to correct the failure, call IBCPSession::BCPInit to reset the settings and start over.</span></span>  
  
 <span data-ttu-id="e59b7-152">Le tableau suivant présente quelques exemples d'appels de fonction qui provoquent une erreur de séquence de fonction :</span><span class="sxs-lookup"><span data-stu-id="e59b7-152">The following table presents some examples of function calls that result in a function sequence error:</span></span>  
  
 <span data-ttu-id="e59b7-153">Séquence d'appels</span><span class="sxs-lookup"><span data-stu-id="e59b7-153">Call sequence</span></span>  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_IN);  
BCPSetBulkMode();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPSetBulkMode();  
BCPReadFmt();  
```  
  
```  
BCPInit(NULL, "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_HINTS, "select ...");  
BCPSetBulkMode();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPSetBulkMode();  
BCPColFmt();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_DELAYREADFMT, true);  
BCPReadFmt();  
BCPColFmt();  
```  
  
```  
BCPInit(NULL, "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_DELAYREADFMT, true);  
BCPSetBulkMode();  
BCPControl(BCP_OPTION_HINTS, "select ...");  
BCPReadFmt();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_DELAYREADFMT, true);  
BCPColumns();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_DELAYREADFMT, true);  
BCPSetColFmt();  
```  
  
## <a name="example"></a><span data-ttu-id="e59b7-154">Exemple</span><span class="sxs-lookup"><span data-stu-id="e59b7-154">Example</span></span>  
 <span data-ttu-id="e59b7-155">L'exemple suivant crée quatre fichiers à l'aide de paramètres différents d'IBCPSession2::BCPSetBulkMode.</span><span class="sxs-lookup"><span data-stu-id="e59b7-155">The following sample creates four files using different settings of IBCPSession2::BCPSetBulkMode.</span></span>  
  
```  
  
// compile with: sqlncli11.lib oleaut32.lib ole32.lib  
  
#include <stdio.h>  
#include "sqlncli.h"  
  
IDBInitialize*  g_pIDBInitialize = NULL;  
IBCPSession2 * g_pIBcpSession = NULL;  
class COLEDBPropSet : public DBPROPSET {  
public:  
   COLEDBPropSet() {  
      rgProperties = NULL;  
      cProperties = 0;  
   };  
   COLEDBPropSet(const GUID& guid) {  
      rgProperties = NULL;  
      cProperties = 0;  
      guidPropertySet = guid;  
   };  
   ~COLEDBPropSet() {  
      for ( ULONG i = 0 ; i < cProperties ; i++ )  
         VariantClear(&rgProperties[i].vValue);  
      CoTaskMemFree(rgProperties);  
   }  
   void SetGUID(const GUID& guid) {  
      guidPropertySet = guid;  
   };  
   bool AddProperty(DWORD dwPropertyID, bool bValue) {  
      if (!Add())  
         return false;  
      rgProperties[cProperties].dwPropertyID = dwPropertyID;  
      rgProperties[cProperties].vValue.vt = VT_BOOL;  
      rgProperties[cProperties].vValue.boolVal = (bValue) ? VARIANT_TRUE : VARIANT_FALSE;  
      cProperties++;  
      return true;  
   };  
   bool AddProperty(DWORD dwPropertyID, long nValue) {  
      if (!Add())  
         return false;  
      rgProperties[cProperties].dwPropertyID  = dwPropertyID;  
      rgProperties[cProperties].vValue.vt     = VT_I4;  
      rgProperties[cProperties].vValue.lVal   = nValue;  
      cProperties++;  
      return true;  
   };  
   bool AddProperty(DWORD dwPropertyID,LPCWSTR szValue) {  
      if (!Add())  
         return false;  
      rgProperties[cProperties].dwPropertyID = dwPropertyID;  
      rgProperties[cProperties].vValue.vt = VT_BSTR;  
      rgProperties[cProperties].vValue.bstrVal = SysAllocString(szValue);  
      cProperties++;  
      return true;  
   };  
   bool Add() {  
      DBPROP* p = (DBPROP*)CoTaskMemRealloc(rgProperties, (cProperties + 1) * sizeof(DBPROP));  
      if (p != NULL) {  
         rgProperties = p;  
         rgProperties[cProperties].dwOptions = DBPROPOPTIONS_REQUIRED;  
         rgProperties[cProperties].colid = DB_NULLID;  
         rgProperties[cProperties].vValue.vt = VT_EMPTY;  
         return true;  
      }  
      else  
         return false;  
   };  
};  
  
void OLEDBCleanUp() {  
   if (g_pIDBInitialize) {  
      g_pIDBInitialize->Release();  
      g_pIDBInitialize = NULL;  
   }  
   if (g_pIBcpSession) {  
      g_pIBcpSession->Release();  
      g_pIBcpSession = NULL;  
   }  
}  
  
BOOL MakeOLEDBConnect(LPWSTR  pServer) {  
   BOOL ret = true;  
   IDBProperties * pIDBProperties = NULL;  
   IDBCreateSession * pIDBCreateSession = NULL;  
   COLEDBPropSet PropSet(DBPROPSET_DBINIT);  
   COLEDBPropSet BcpProperty(DBPROPSET_SQLSERVERDATASOURCE);  
   try {  
      HRESULT hr = CoInitializeEx(NULL,COINIT_MULTITHREADED);   
      hr = CoCreateInstance(SQLNCLI_CLSID, NULL, CLSCTX_INPROC_SERVER, IID_IDBInitialize, (LPVOID *)&g_pIDBInitialize);  
      if (FAILED(hr)) {  
         printf("CoCreateInstance failed\n");  
         return false;  
      }  
      PropSet.AddProperty(DBPROP_INIT_DATASOURCE, (LPWSTR)pServer);  
      PropSet.AddProperty(DBPROP_AUTH_INTEGRATED, L"SSPI");  
      hr = g_pIDBInitialize->QueryInterface(IID_IDBProperties, (void**) &pIDBProperties);  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->->QueryInterface(IID_IDBProperties...) failed\n");  
         throw false;  
      }  
      hr = pIDBProperties->SetProperties(1, &PropSet);  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->->SetProperties(...) failed\n");  
         throw false;  
      }  
      hr = g_pIDBInitialize->Initialize();  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->->Initialize() failed\n");  
         throw false;  
      }  
      BcpProperty.AddProperty(SSPROP_ENABLEFASTLOAD, true);  
      BcpProperty.AddProperty(SSPROP_ENABLEBULKCOPY, true);  
      hr = pIDBProperties->SetProperties(1, &BcpProperty);  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->->SetProperties() for bcp failed\n");  
         throw false;  
      }  
      hr = g_pIDBInitialize->QueryInterface(IID_IDBCreateSession, (void**) &pIDBCreateSession);  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->QueryInterface(IID_IDBCreateSession..) failed\n");  
         throw false;  
      }  
  
      hr = pIDBCreateSession->CreateSession(NULL, IID_IBCPSession2, (IUnknown**) &g_pIBcpSession);  
      if (FAILED(hr)) {  
         printf("g_pIDBCreateSession->CreateSession() failed\n");  
         throw false;  
      }  
   }  
   catch(...) {  
      ret = false;  
   }  
   if (pIDBProperties)  
      pIDBProperties->Release();  
   if (pIDBCreateSession)  
      pIDBCreateSession->Release();  
   return ret;  
}  
  
BOOL BCPSetBulkMode(LPWSTR pszServer, LPTSTR pszQureryOut, char BCPType, LPWSTR pszDataFile) {  
   HRESULThr;  
   if (!MakeOLEDBConnect(pszServer))  
      return false;  
   hr = g_pIBcpSession->BCPInit(NULL, pszDataFile, NULL, BCP_DIRECTION_OUT );   // bcp init for queryout  
   if (FAILED(hr)) {  
      printf("BCP init failed\n");  
      OLEDBCleanUp();  
      return false;  
   }  
   // setbulkmode  
   char ColTerm[] = "\t";  
   char RowTerm[] = "\r\n";  
   wchar_t wColTerm[] = L"\t";  
   wchar_t wRowTerm[] = L"\r\n";  
   BYTE * pColTerm = NULL;  
   int cbColTerm = NULL;  
   BYTE * pRowTerm = 0;  
   int cbRowTerm = 0;  
   int bulkmode = -1;  
  
   if(BCPType == 'c') {   // bcp -c  
      pColTerm = (BYTE*)ColTerm;  
      pRowTerm = (BYTE*)RowTerm;  
      cbColTerm = 1;  
      cbRowTerm = 2;  
      bulkmode = BCP_OUT_CHARACTER_MODE;  
   }  
   else  
      if(BCPType == 'w') {   // bcp -w  
         pColTerm = (BYTE*)wColTerm;  
         pRowTerm = (BYTE*)wRowTerm;  
         cbColTerm = 2;  
         cbRowTerm = 4;  
         bulkmode = BCP_OUT_WIDE_CHARACTER_MODE;  
      }  
      else  
         if (BCPType == 'n')   // bcp -n  
            bulkmode = BCP_OUT_NATIVE_MODE;  
         else  
            if (BCPType == 'N')   // bcp -n  
               bulkmode = BCP_OUT_NATIVE_TEXT_MODE;  
            else {  
               printf("unknown bcp mode\n");  
               OLEDBCleanUp();  
               return false;  
            }  
            hr = g_pIBcpSession->BCPSetBulkMode(bulkmode, pColTerm, cbColTerm, pRowTerm, cbRowTerm);  
            if (FAILED(hr)) {  
               printf("BCPSetBulkMode failed\n");  
               OLEDBCleanUp();  
               return false;  
            }  
  
            // set queryout TSQL statement  
            hr = g_pIBcpSession->BCPControl(BCP_OPTION_HINTS, pszQureryOut);  
            if (FAILED(hr)) {  
               printf("BCPControl failed\n");  
               OLEDBCleanUp();  
               return false;  
            }  
            // bcp copy  
            DBROWCOUNT nRowsInserted = 0;  
            hr = g_pIBcpSession->BCPExec(&nRowsInserted);  
            if (FAILED(hr)) {  
               printf("BCPExec failed\n");  
               OLEDBCleanUp();  
               return false;  
            }  
            printf("bcp done\n");  
            OLEDBCleanUp();  
            return true;  
}  
  
int main() {  
   BCPSetBulkMode(L"localhost", TEXT("SELECT 'this is a bcp -c test', 1,2") , 'c', L"bcpc.dat");  
   BCPSetBulkMode(L"localhost", TEXT("SELECT 'this is a bcp -w test', 1,2") , 'w', L"bcpw.dat");  
   BCPSetBulkMode(L"localhost", TEXT("SELECT 'this is a bcp -c test', 1,2") , 'n', L"bcpn.dat");  
   BCPSetBulkMode(L"localhost", TEXT("SELECT 'this is a bcp -w test', 1,2") , 'N', L"bcp_N.dat");  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e59b7-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e59b7-156">See Also</span></span>  
 [<span data-ttu-id="e59b7-157">IBCPSession2 &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="e59b7-157">IBCPSession2 &#40;OLE DB&#41;</span></span>](ibcpsession2-ole-db.md)  
  
  
