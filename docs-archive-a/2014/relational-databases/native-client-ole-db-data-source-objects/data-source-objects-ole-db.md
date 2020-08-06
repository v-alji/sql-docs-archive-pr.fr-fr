---
title: Objets de la source de données (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data access [SQL Server Native Client], data source objects
- SQL Server Native Client, data source objects
- SQLNCLI, data source objects
- SQL Server Native Client OLE DB provider, data source objects
- OLE DB data source objects [SQL Server Native Client]
- data source objects [OLE DB]
- CLSID
ms.assetid: c1d4ed20-ad3b-4e33-a26b-38d7517237b7
author: rothja
ms.author: jroth
ms.openlocfilehash: 9cf3f0b0308d655b50149c174547c19966f550ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695588"
---
# <a name="data-source-objects-ole-db"></a><span data-ttu-id="2d7d0-102">Objets source de données (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="2d7d0-102">Data Source Objects (OLE DB)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="2d7d0-103">Native Client utilise le terme source de données pour l’ensemble des interfaces de OLE DB utilisées pour établir un lien vers un magasin de données, tel que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2d7d0-103">Native Client uses the term data source for the set of OLE DB interfaces used to establish a link to a data store, such as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2d7d0-104">La création d’une instance de l’objet source de données du fournisseur est la première tâche d’un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consommateur Native Client.</span><span class="sxs-lookup"><span data-stu-id="2d7d0-104">Creating an instance of the data source object of the provider is the first task of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client consumer.</span></span>  
  
 <span data-ttu-id="2d7d0-105">Chaque fournisseur OLE DB déclare un identificateur de classe (CLSID) pour lui-même.</span><span class="sxs-lookup"><span data-stu-id="2d7d0-105">Every OLE DB provider declares a class identifier (CLSID) for itself.</span></span> <span data-ttu-id="2d7d0-106">Le CLSID du [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client est le GUID C/C++ CLSID_SQLNCLI10 (le symbole SQLNCLI_CLSID sera résolu en ProgID correct dans le fichier sqlncli. h que vous référencez).</span><span class="sxs-lookup"><span data-stu-id="2d7d0-106">The CLSID for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider is the C/C++ GUID CLSID_SQLNCLI10 (the symbol SQLNCLI_CLSID will resolve to the correct progid in the sqlncli.h file that you reference).</span></span> <span data-ttu-id="2d7d0-107">Avec le CLSID, le consommateur utilise la fonction OLE **CoCreateInstance** pour fabriquer une instance de l’objet source de données.</span><span class="sxs-lookup"><span data-stu-id="2d7d0-107">With the CLSID, the consumer uses the OLE **CoCreateInstance** function to manufacture an instance of the data source object.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="2d7d0-108">Native Client est un serveur in-process.</span><span class="sxs-lookup"><span data-stu-id="2d7d0-108">Native Client is an in-process server.</span></span> <span data-ttu-id="2d7d0-109">Les instances des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objets Native Client OLE DB fournisseur sont créées à l’aide de la macro CLSCTX_INPROC_SERVER pour indiquer le contexte de l’exécutable.</span><span class="sxs-lookup"><span data-stu-id="2d7d0-109">Instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider objects are created using the CLSCTX_INPROC_SERVER macro to indicate the executable context.</span></span>  
  
 <span data-ttu-id="2d7d0-110">L' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objet de source de données du fournisseur OLE DB Native Client expose les interfaces d’initialisation OLE DB qui permettent au consommateur de se connecter aux [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bases de données existantes.</span><span class="sxs-lookup"><span data-stu-id="2d7d0-110">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source object exposes the OLE DB initialization interfaces that allow the consumer to connect to existing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span>  
  
 <span data-ttu-id="2d7d0-111">Chaque connexion effectuée via le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client définit automatiquement ces options :</span><span class="sxs-lookup"><span data-stu-id="2d7d0-111">Every connection made through the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider sets these options automatically:</span></span>  
  
-   <span data-ttu-id="2d7d0-112">SET ANSI_WARNINGS ON</span><span class="sxs-lookup"><span data-stu-id="2d7d0-112">SET ANSI_WARNINGS ON</span></span>  
  
-   <span data-ttu-id="2d7d0-113">SET ANSI_NULLS ON</span><span class="sxs-lookup"><span data-stu-id="2d7d0-113">SET ANSI_NULLS ON</span></span>  
  
-   <span data-ttu-id="2d7d0-114">SET ANSI_PADDING ON</span><span class="sxs-lookup"><span data-stu-id="2d7d0-114">SET ANSI_PADDING ON</span></span>  
  
-   <span data-ttu-id="2d7d0-115">SET ANSI_NULL_DFLT_ON ON</span><span class="sxs-lookup"><span data-stu-id="2d7d0-115">SET ANSI_NULL_DFLT_ON ON</span></span>  
  
-   <span data-ttu-id="2d7d0-116">SET QUOTED_IDENTIFIER ON</span><span class="sxs-lookup"><span data-stu-id="2d7d0-116">SET QUOTED_IDENTIFIER ON</span></span>  
  
-   <span data-ttu-id="2d7d0-117">SET CONCAT_OF_NULL_YIELDS_NULL ON</span><span class="sxs-lookup"><span data-stu-id="2d7d0-117">SET CONCAT_OF_NULL_YIELDS_NULL ON</span></span>  
  
 <span data-ttu-id="2d7d0-118">Cet exemple utilise la macro d’identificateur de classe pour créer un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objet Native Client OLE DB fournisseur de source de données et obtenir une référence à son interface **IDBInitialize** .</span><span class="sxs-lookup"><span data-stu-id="2d7d0-118">This example uses the class identifier macro to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source object and get a reference to its **IDBInitialize** interface.</span></span>  
  
```  
IDBInitialize*   pIDBInitialize;  
HRESULT          hr;  
  
hr = CoCreateInstance(CLSID_SQLNCLI10, NULL, CLSCTX_INPROC_SERVER,  
    IID_IDBInitialize, (void**) &pIDBInitialize);  
  
if (SUCCEEDED(hr))  
{  
    //  Perform necessary processing with the interface.  
    pIDBInitialize->Uninitialize();  
    pIDBInitialize->Release();  
}  
else  
{  
    // Display error from CoCreateInstance.  
}  
```  
  
 <span data-ttu-id="2d7d0-119">Avec la réussite de la création d’une instance d’un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objet Native Client OLE DB fournisseur de source de données, l’application consommateur peut continuer en initialisant la source de données et en créant des sessions.</span><span class="sxs-lookup"><span data-stu-id="2d7d0-119">With successful creation of an instance of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source object, the consumer application can continue by initializing the data source and creating sessions.</span></span> <span data-ttu-id="2d7d0-120">Les sessions OLE DB présentent des interfaces qui permettent d'accéder à des données et de les manipuler.</span><span class="sxs-lookup"><span data-stu-id="2d7d0-120">OLE DB sessions present the interfaces that allow data access and manipulation.</span></span>  
  
 <span data-ttu-id="2d7d0-121">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client établit sa première connexion à une instance spécifiée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans le cadre de l’initialisation réussie de la source de données.</span><span class="sxs-lookup"><span data-stu-id="2d7d0-121">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider makes its first connection to a specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as part of a successful data source initialization.</span></span> <span data-ttu-id="2d7d0-122">La connexion est maintenue tant qu’une référence est conservée dans toutes les interfaces d’initialisation de source de données, ou jusqu’à l’appel de la méthode **IDBInitialize::Uninitialize**.</span><span class="sxs-lookup"><span data-stu-id="2d7d0-122">The connection is maintained as long as a reference is maintained on any data source initialization interface, or until the **IDBInitialize::Uninitialize** method is called.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2d7d0-123">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="2d7d0-123">In This Section</span></span>  
  
-   [<span data-ttu-id="2d7d0-124">Propriétés de la source de données &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="2d7d0-124">Data Source Properties &#40;OLE DB&#41;</span></span>](data-source-properties-ole-db.md)  
  
-   [<span data-ttu-id="2d7d0-125">Propriétés des informations de la source de données</span><span class="sxs-lookup"><span data-stu-id="2d7d0-125">Data Source Information Properties</span></span>](data-source-information-properties.md)  
  
-   [<span data-ttu-id="2d7d0-126">Propriétés d’initialisation et d’autorisation</span><span class="sxs-lookup"><span data-stu-id="2d7d0-126">Initialization and Authorization Properties</span></span>](initialization-and-authorization-properties.md)  
  
-   [<span data-ttu-id="2d7d0-127">Sessions</span><span class="sxs-lookup"><span data-stu-id="2d7d0-127">Sessions</span></span>](sessions.md)  
  
-   [<span data-ttu-id="2d7d0-128">Propriétés de session</span><span class="sxs-lookup"><span data-stu-id="2d7d0-128">Session Properties</span></span>](session-properties-sql-server-native-client-ole-db-provider.md)  
  
-   [<span data-ttu-id="2d7d0-129">Objets source de données persistants</span><span class="sxs-lookup"><span data-stu-id="2d7d0-129">Persisted Data Source Objects</span></span>](persisted-data-source-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="2d7d0-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2d7d0-130">See Also</span></span>  
 [<span data-ttu-id="2d7d0-131">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="2d7d0-131">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
