---
title: Établissement d'une connexion à une source de données | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data sources [SQL Server Native Client]
- connections [SQL Server Native Client]
- SQL Server Native Client OLE DB provider, data source connections
- CoCreateInstance method
- OLE DB data sources [SQL Server Native Client]
ms.assetid: 7ebd1394-cc8d-4bcf-92f3-c374a26e7ba0
author: rothja
ms.author: jroth
ms.openlocfilehash: f88454339ee932c38655819cce475ab52d79975f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612789"
---
# <a name="establishing-a-connection-to-a-data-source"></a><span data-ttu-id="2ddf7-102">Établissement d'une connexion à une source de données</span><span class="sxs-lookup"><span data-stu-id="2ddf7-102">Establishing a Connection to a Data Source</span></span>
  <span data-ttu-id="2ddf7-103">Pour accéder au [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client, le consommateur doit d’abord créer une instance d’un objet source de données en appelant la méthode **CoCreateInstance** .</span><span class="sxs-lookup"><span data-stu-id="2ddf7-103">To access the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the consumer must first create an instance of a data source object by calling the **CoCreateInstance** method.</span></span> <span data-ttu-id="2ddf7-104">Un identificateur de classe unique (CLSID) identifie chaque fournisseur OLE DB.</span><span class="sxs-lookup"><span data-stu-id="2ddf7-104">A unique class identifier (CLSID) identifies each OLE DB provider.</span></span> <span data-ttu-id="2ddf7-105">Pour le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client, l’identificateur de classe est CLSID_SQLNCLI10.</span><span class="sxs-lookup"><span data-stu-id="2ddf7-105">For the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the class identifier is CLSID_SQLNCLI10.</span></span> <span data-ttu-id="2ddf7-106">Vous pouvez également utiliser le symbole SQLNCLI_CLSID qui sera résolu en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur Native Client OLE DB utilisé dans le sqlncli. h que vous référencez.</span><span class="sxs-lookup"><span data-stu-id="2ddf7-106">You can also use the symbol SQLNCLI_CLSID that will resolve to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider that is used in the sqlncli.h that you reference.</span></span>  
  
 <span data-ttu-id="2ddf7-107">L’objet de source de données expose l’interface **IDBProperties**, que le consommateur utilise pour fournir les informations d’authentification de base, comme le nom du serveur, le nom de la base de données, l’ID d’utilisateur et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="2ddf7-107">The data source object exposes the **IDBProperties** interface, which the consumer uses to provide basic authentication information such as server name, database name, user ID, and password.</span></span> <span data-ttu-id="2ddf7-108">La méthode **IDBProperties::SetProperties** est appelée pour définir ces propriétés.</span><span class="sxs-lookup"><span data-stu-id="2ddf7-108">The **IDBProperties::SetProperties** method is called to set these properties.</span></span>  
  
 <span data-ttu-id="2ddf7-109">S'il existe plusieurs instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui s'exécutent sur l'ordinateur, le nom du serveur est spécifié sous la forme NomServeur\NomInstance.</span><span class="sxs-lookup"><span data-stu-id="2ddf7-109">If there are multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the computer, the server name is specified as ServerName\InstanceName.</span></span>  
  
 <span data-ttu-id="2ddf7-110">L’objet de source de données expose également l’interface **IDBInitialize**.</span><span class="sxs-lookup"><span data-stu-id="2ddf7-110">The data source object also exposes the **IDBInitialize** interface.</span></span> <span data-ttu-id="2ddf7-111">Une fois les propriétés définies, la connexion à la source de données est établie en appelant la méthode **IDBInitialize::Initialize**.</span><span class="sxs-lookup"><span data-stu-id="2ddf7-111">After the properties are set, connection to the data source is established by calling the **IDBInitialize::Initialize** method.</span></span> <span data-ttu-id="2ddf7-112">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="2ddf7-112">For example:</span></span>  
  
```  
CoCreateInstance(CLSID_SQLNCLI10,   
                 NULL,   
                 CLSCTX_INPROC_SERVER,  
                 IID_IDBInitialize,   
                 (void **) &pIDBInitialize)  
```  
  
 <span data-ttu-id="2ddf7-113">Cet appel à **CoCreateInstance** crée un objet unique de la classe associée à CLSID_SQLNCLI10 (CSLID associé aux données et au code qui sera utilisé pour créer l’objet).</span><span class="sxs-lookup"><span data-stu-id="2ddf7-113">This call to **CoCreateInstance** creates a single object of the class associated with CLSID_SQLNCLI10 (CSLID associated with the data and code that will be used to create the object).</span></span> <span data-ttu-id="2ddf7-114">IID_IDBInitialize est une référence à l’identificateur de l’interface (**IDBInitialize**) à utiliser pour communiquer avec l’objet.</span><span class="sxs-lookup"><span data-stu-id="2ddf7-114">IID_IDBInitialize is a reference to the identifier of the interface (**IDBInitialize**) to be used to communicate with the object.</span></span>  
  
 <span data-ttu-id="2ddf7-115">Les éléments suivants sont un exemple de fonction qui initialise et établit une connexion à la source de données.</span><span class="sxs-lookup"><span data-stu-id="2ddf7-115">The following is a sample function that initializes and establishes a connection to the data source.</span></span>  
  
```  
void InitializeAndEstablishConnection() {  
   // Initialize the COM library.  
   CoInitialize(NULL);  
  
   // Obtain access to the SQL Server Native Client OLE DB provider.  
   hr = CoCreateInstance(CLSID_SQLNCLI10,   
                         NULL,   
                         CLSCTX_INPROC_SERVER,  
                         IID_IDBInitialize,   
                         (void **) &pIDBInitialize);  
   // Initialize property values needed to establish connection.  
   for (i = 0 ; i < 4 ; i++)   
      VariantInit(&InitProperties[i].vValue);  
  
   // Server name.  
   // See DBPROP structure for more information on InitProperties  
   InitProperties[0].dwPropertyID  = DBPROP_INIT_DATASOURCE;  
   InitProperties[0].vValue.vt    = VT_BSTR;  
   InitProperties[0].vValue.bstrVal=   
                     SysAllocString(L"Server");  
   InitProperties[0].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[0].colid       = DB_NULLID;  
  
   // Database.  
   InitProperties[1].dwPropertyID  = DBPROP_INIT_CATALOG;  
   InitProperties[1].vValue.vt    = VT_BSTR;  
   InitProperties[1].vValue.bstrVal= SysAllocString(L"database");  
   InitProperties[1].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[1].colid       = DB_NULLID;  
  
   // Username (login).  
   InitProperties[2].dwPropertyID  = DBPROP_AUTH_INTEGRATED;  
   InitProperties[2].vValue.vt    = VT_BSTR;  
   InitProperties[2].vValue.bstrVal= SysAllocString(L"SSPI");  
   InitProperties[2].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[2].colid       = DB_NULLID;  
   InitProperties[3].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[3].colid       = DB_NULLID;  
  
   // Construct the DBPROPSET structure(rgInitPropSet). The   
   // DBPROPSET structure is used to pass an array of DBPROP   
   // structures (InitProperties) to the SetProperties method.  
   rgInitPropSet[0].guidPropertySet = DBPROPSET_DBINIT;  
   rgInitPropSet[0].cProperties   = 4;  
   rgInitPropSet[0].rgProperties   = InitProperties;  
  
   // Set initialization properties.  
   hr = pIDBInitialize->QueryInterface(IID_IDBProperties,   
                           (void **)&pIDBProperties);  
   hr = pIDBProperties->SetProperties(1, rgInitPropSet);   
   pIDBProperties->Release();  
  
   // Now establish the connection to the data source.  
   pIDBInitialize->Initialize();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ddf7-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2ddf7-116">See Also</span></span>  
 [<span data-ttu-id="2ddf7-117">Création d'une application de fournisseur OLE DB de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="2ddf7-117">Creating a SQL Server Native Client OLE DB Provider Application</span></span>](creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
  
