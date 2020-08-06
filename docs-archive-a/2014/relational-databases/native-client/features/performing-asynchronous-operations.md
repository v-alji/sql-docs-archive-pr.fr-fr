---
title: Exécution d’opérations asynchrones Azure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- initialization [SQL Server Native Client]
- database connections [SQL Server Native Client]
- data access [SQL Server Native Client], asynchronous operations
- connections [SQL Server Native Client]
- asynchronous operations [SQL Server Native Client]
- rowsets [SQL Server], initializing
- SQLNCLI, asynchronous operations
- SQL Server Native Client, asynchronous operations
ms.assetid: 8fbd84b4-69cb-4708-9f0f-bbdf69029bcc
author: rothja
ms.author: jroth
ms.openlocfilehash: 4f7e8f4481923cd7da537f921248865d4fff7280
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698063"
---
# <a name="performing-asynchronous-operations"></a><span data-ttu-id="61248-102">Exécution d'opérations asynchrones</span><span class="sxs-lookup"><span data-stu-id="61248-102">Performing Asynchronous Operations</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="61248-103">permet aux applications d'effectuer des opérations de base de données asynchrones.</span><span class="sxs-lookup"><span data-stu-id="61248-103">allows applications to perform asynchronous database operations.</span></span> <span data-ttu-id="61248-104">Le traitement asynchrone permet aux méthodes d'être retournées immédiatement sans blocage du thread appelant.</span><span class="sxs-lookup"><span data-stu-id="61248-104">Asynchronous processing enables methods to return immediately without blocking on the calling thread.</span></span> <span data-ttu-id="61248-105">Cela rend le multithreading plus puissant et plus souple, sans obliger le développeur à créer explicitement des threads ou à gérer la synchronisation.</span><span class="sxs-lookup"><span data-stu-id="61248-105">This allows much of the power and flexibility of multithreading, without requiring the developer to explicitly create threads or handle synchronization.</span></span> <span data-ttu-id="61248-106">Les applications requièrent un traitement asynchrone lors de l'initialisation d'une connexion de base de données, ou lors de l'initialisation du résultat de l'exécution d'une commande.</span><span class="sxs-lookup"><span data-stu-id="61248-106">Applications request asynchronous processing when initializing a database connection, or when initializing the result from the execution of a command.</span></span>  
  
## <a name="opening-and-closing-a-database-connection"></a><span data-ttu-id="61248-107">Ouverture et fermeture d'une connexion de base de données</span><span class="sxs-lookup"><span data-stu-id="61248-107">Opening and Closing a Database Connection</span></span>  
 <span data-ttu-id="61248-108">Lorsque vous utilisez le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client, les applications conçues pour initialiser de manière asynchrone un objet source de données peuvent définir le bit DBPROPVAL_ASYNCH_INITIALIZE dans la propriété DBPROP_INIT_ASYNCH avant d’appeler **IDBInitialize :: Initialize**.</span><span class="sxs-lookup"><span data-stu-id="61248-108">When using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, applications designed to initialize a data source object asynchronously can set the DBPROPVAL_ASYNCH_INITIALIZE bit in the DBPROP_INIT_ASYNCH property prior to calling **IDBInitialize::Initialize**.</span></span> <span data-ttu-id="61248-109">Quand cette propriété est définie, le fournisseur est retourné immédiatement à partir de l’appel à **Initialize** avec la valeur S_OK si l’opération s’est effectuée immédiatement ou DB_S_ASYNCHRONOUS si l’initialisation se poursuit de façon asynchrone.</span><span class="sxs-lookup"><span data-stu-id="61248-109">When this property is set, the provider returns immediately from the call to **Initialize** with either S_OK, if the operation has completed immediately, or DB_S_ASYNCHRONOUS, if the initialization is continuing asynchronously.</span></span> <span data-ttu-id="61248-110">Les applications peuvent interroger l’interface **IDBAsynchStatus** ou [ISSAsynchStatus](../../native-client-ole-db-interfaces/issasynchstatus-ole-db.md)sur l’objet source de données, puis appeler **IDBAsynchStatus :: GetStatus** ou[ISSAsynchStatus :: WaitForAsynchCompletion](../../native-client-ole-db-interfaces/issasynchstatus-waitforasynchcompletion-ole-db.md) pour obtenir l’état de l’initialisation.</span><span class="sxs-lookup"><span data-stu-id="61248-110">Applications can query for the **IDBAsynchStatus** or [ISSAsynchStatus](../../native-client-ole-db-interfaces/issasynchstatus-ole-db.md)interface on the data source object, and then call **IDBAsynchStatus::GetStatus** or[ISSAsynchStatus::WaitForAsynchCompletion](../../native-client-ole-db-interfaces/issasynchstatus-waitforasynchcompletion-ole-db.md) to get the status of the initialization.</span></span>  
  
 <span data-ttu-id="61248-111">De plus, la propriété SSPROP_ISSAsynchStatus a été ajoutée au jeu de propriétés DBPROPSET_SQLSERVERROWSET.</span><span class="sxs-lookup"><span data-stu-id="61248-111">In addition, the SSPROP_ISSAsynchStatus property has been added to the DBPROPSET_SQLSERVERROWSET property set.</span></span> <span data-ttu-id="61248-112">Les fournisseurs qui prennent en charge l’interface **ISSAsynchStatus** doivent implémenter cette propriété avec la valeur VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="61248-112">Providers that support the **ISSAsynchStatus** interface must implement this property with a value of VARIANT_TRUE.</span></span>  
  
 <span data-ttu-id="61248-113">**IDBAsynchStatus::Abort** ou [ISSAsynchStatus::Abort](../../native-client-ole-db-interfaces/issasynchstatus-abort-ole-db.md) peut être appelée pour annuler l’appel asynchrone à **Initialize**.</span><span class="sxs-lookup"><span data-stu-id="61248-113">**IDBAsynchStatus::Abort** or [ISSAsynchStatus::Abort](../../native-client-ole-db-interfaces/issasynchstatus-abort-ole-db.md) can be called to cancel the asynchronous **Initialize** call.</span></span> <span data-ttu-id="61248-114">Le consommateur doit demander explicitement l'initialisation de la source de données asynchrone.</span><span class="sxs-lookup"><span data-stu-id="61248-114">The consumer must explicitly request Asynchronous Data Source Initialization.</span></span> <span data-ttu-id="61248-115">Sinon, **IDBInitialize::Initialize** n’est pas retournée tant que l’objet source de données n’est pas complètement initialisé.</span><span class="sxs-lookup"><span data-stu-id="61248-115">Otherwise, **IDBInitialize::Initialize** does not return until the data source object is completely initialized.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61248-116">Les objets de source de données utilisés pour le regroupement de connexions ne peuvent pas appeler l’interface **ISSAsynchStatus** dans le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client.</span><span class="sxs-lookup"><span data-stu-id="61248-116">Data source objects used for connection pooling cannot call the **ISSAsynchStatus** interface in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="61248-117">L’interface **ISSAsynchStatus** n’est pas exposée pour les objets sources de données regroupés.</span><span class="sxs-lookup"><span data-stu-id="61248-117">The **ISSAsynchStatus** interface is not exposed for pooled data source objects.</span></span>  
>   
>  <span data-ttu-id="61248-118">Si une application force explicitement l’utilisation du moteur de curseur, **IOpenRowset::OpenRowset** et **IMultipleResults::GetResult** ne prennent pas en charge le traitement asynchrone.</span><span class="sxs-lookup"><span data-stu-id="61248-118">If an application explicitly forces use of the cursor engine, **IOpenRowset::OpenRowset** and **IMultipleResults::GetResult** will not support asynchronous processing.</span></span>  
>   
>  <span data-ttu-id="61248-119">En outre, la dll proxy de communication à distance/stub (dans MDAC 2,8) ne peut pas appeler l’interface **ISSAsynchStatus** dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="61248-119">In addition, the remoting proxy/stub dll (in MDAC 2.8) cannot call the **ISSAsynchStatus** interface in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="61248-120">L’interface **ISSAsynchStatus** n’est pas exposée via la communication à distance.</span><span class="sxs-lookup"><span data-stu-id="61248-120">The **ISSAsynchStatus** interface is not exposed through remoting.</span></span>  
>   
>  <span data-ttu-id="61248-121">Les composants du service ne prennent pas en charge **ISSAsynchStatus**.</span><span class="sxs-lookup"><span data-stu-id="61248-121">Service Components do not support **ISSAsynchStatus**.</span></span>  
  
## <a name="execution-and-rowset-initialization"></a><span data-ttu-id="61248-122">Exécution et initialisation de l'ensemble de lignes</span><span class="sxs-lookup"><span data-stu-id="61248-122">Execution and Rowset Initialization</span></span>  
 <span data-ttu-id="61248-123">Les applications conçues pour ouvrir de façon asynchrone le résultat de l'exécution d'une commande peuvent définir DBPROPVAL_ASYNCH_INITIALIZE dans la propriété DBPROP_ROWSET_ASYNCH.</span><span class="sxs-lookup"><span data-stu-id="61248-123">Applications designed to asynchronously open the result from the execution of a command can set the DBPROPVAL_ASYNCH_INITIALIZE bit in the DBPROP_ROWSET_ASYNCH property.</span></span> <span data-ttu-id="61248-124">Lors de la définition de ce bit avant d’appeler **IDBInitialize::Initialize**, **ICommand::Execute**, **IOpenRowset::OpenRowset** ou **IMultipleResults::GetResult**, l’argument *riid* doit avoir pour valeur IID_IDBAsynchStatus, IID_ISSAsynchStatus ou IID_IUnknown.</span><span class="sxs-lookup"><span data-stu-id="61248-124">When setting this bit prior to calling **IDBInitialize::Initialize**, **ICommand::Execute**, **IOpenRowset::OpenRowset** or **IMultipleResults::GetResult**, the *riid* argument must be set to IID_IDBAsynchStatus, IID_ISSAsynchStatus, or IID_IUnknown.</span></span>  
  
 <span data-ttu-id="61248-125">La méthode est retournée immédiatement avec S_OK si l’initialisation de l’ensemble de lignes s’effectue immédiatement (ou avec DB_S_ASYNCHRONOUS si l’ensemble de lignes poursuit son initialisation de façon asynchrone) avec *ppRowset* défini en fonction de l’interface demandée sur l’ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="61248-125">The method returns immediately with S_OK if the rowset initialization completes immediately, or with DB_S_ASYNCHRONOUS if the rowset continues initializing asynchronously, with *ppRowset* set to the requested interface on the rowset.</span></span> <span data-ttu-id="61248-126">Pour le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client, cette interface peut uniquement être **IDBAsynchStatus** ou **ISSAsynchStatus**.</span><span class="sxs-lookup"><span data-stu-id="61248-126">For the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, this interface can only be **IDBAsynchStatus** or **ISSAsynchStatus**.</span></span> <span data-ttu-id="61248-127">Jusqu’à ce que l’ensemble de lignes soit entièrement initialisé, cette interface se comporte comme si elle était dans un état suspendu ; par ailleurs, l’appel de **QueryInterface** pour les interfaces autres **qu’IID_IDBAsynchStatus** ou **qu’IID_ISSAsynchStatus** peut retourner E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="61248-127">Until the rowset is fully initialized, this interface behaves as if it were in a suspended state, and calling **QueryInterface** for interfaces other than **IID_IDBAsynchStatus** or **IID_ISSAsynchStatus** may return E_NOINTERFACE.</span></span> <span data-ttu-id="61248-128">À moins que le consommateur ne demande explicitement un traitement asynchrone, l'ensemble de lignes est initialisé de façon synchrone.</span><span class="sxs-lookup"><span data-stu-id="61248-128">Unless the consumer explicitly requests asynchronous processing, the rowset is initialized synchronously.</span></span> <span data-ttu-id="61248-129">Toutes les interfaces demandées sont disponibles quand **IDBAsynchStaus::GetStatus** ou **ISSAsynchStatus::WaitForAsynchCompletion** est retournée avec l’indication que l’opération asynchrone a été effectuée.</span><span class="sxs-lookup"><span data-stu-id="61248-129">All requested interfaces are available when **IDBAsynchStaus::GetStatus** or **ISSAsynchStatus::WaitForAsynchCompletion** returns with the indication that asynchronous operation is complete.</span></span> <span data-ttu-id="61248-130">Cela ne signifie pas nécessairement que l'ensemble de lignes soit entièrement rempli, mais il est prêt et complètement fonctionnel.</span><span class="sxs-lookup"><span data-stu-id="61248-130">This does not necessarily mean that the rowset is fully populated, but it is complete and fully functional.</span></span>  
  
 <span data-ttu-id="61248-131">Si la commande exécutée ne retourne pas d’ensemble de lignes, elle est quand même retournée immédiatement avec un objet qui prend en charge **IDBAsynchStatus**.</span><span class="sxs-lookup"><span data-stu-id="61248-131">If the executed command does not return a rowset, it still returns immediately with an object that supports **IDBAsynchStatus**.</span></span>  
  
 <span data-ttu-id="61248-132">S'il vous faut obtenir plusieurs résultats à partir de l'exécution d'une commande asynchrone, vous devez :</span><span class="sxs-lookup"><span data-stu-id="61248-132">If you need to get multiple results from asynchronous command execution, you should:</span></span>  
  
-   <span data-ttu-id="61248-133">définir DBPROPVAL_ASYNCH_INITIALIZE dans la propriété DBPROP_ROWSET_ASYNCH, avant d'exécuter la commande ;</span><span class="sxs-lookup"><span data-stu-id="61248-133">Set the DBPROPVAL_ASYNCH_INITIALIZE bit of the DBPROP_ROWSET_ASYNCH property, before executing the command.</span></span>  
  
-   <span data-ttu-id="61248-134">appeler **ICommand::Execute** et demander **IMultipleResults**.</span><span class="sxs-lookup"><span data-stu-id="61248-134">Call **ICommand::Execute**, and request **IMultipleResults**.</span></span>  
  
 <span data-ttu-id="61248-135">Les interfaces **IDBAsynchStatus** et **ISSAsynchStatus** peuvent ensuite être obtenues en interrogeant l’interface de résultats multiples via **QueryInterface**.</span><span class="sxs-lookup"><span data-stu-id="61248-135">The **IDBAsynchStatus** and **ISSAsynchStatus** interfaces can then be obtained by querying the multiple results interface using **QueryInterface**.</span></span>  
  
 <span data-ttu-id="61248-136">Quand l’exécution de la commande est terminée, **IMultipleResults** peut être utilisé normalement à une exception près par rapport au traitement synchrone : DB_S_ASYNCHRONOUS peut être retourné, auquel cas **IDBAsynchStatus** ou **ISSAsynchStatus** peut être utilisée pour déterminer le moment où l’opération est achevée.</span><span class="sxs-lookup"><span data-stu-id="61248-136">When the command has finished executing, **IMultipleResults** can be used as normal, with one exception from the synchronous case: DB_S_ASYNCHRONOUS may be returned, in which case **IDBAsynchStatus** or **ISSAsynchStatus** can be used to determine when the operation is complete.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="61248-137">Exemples</span><span class="sxs-lookup"><span data-stu-id="61248-137">Examples</span></span>  
 <span data-ttu-id="61248-138">Dans l'exemple suivant, l'application appelle une méthode non bloquante, effectue d'autres traitements, puis retourne au traitement des résultats.</span><span class="sxs-lookup"><span data-stu-id="61248-138">In the following example, the application calls a non-blocking method, does some other processing, and then returns to process the results.</span></span> <span data-ttu-id="61248-139">**ISSAsynchStatus::WaitForAsynchCompletion** attend l’objet d’événement interne jusqu’à ce que l’opération s’exécutant de manière asynchrone soit terminée ou que le délai spécifié par *dwMilisecTimeOut* soit passé.</span><span class="sxs-lookup"><span data-stu-id="61248-139">**ISSAsynchStatus::WaitForAsynchCompletion** waits on the internal event object until the asynchronously executing operation is done or the amount of time specified by *dwMilisecTimeOut* is passed.</span></span>  
  
```  
// Set the DBPROPVAL_ASYNCH_INITIALIZE bit in the   
// DBPROP_ROWSET_ASYNCH property before calling Execute().  
  
DBPROPSET CmdPropset[1];  
DBPROP CmdProperties[1];  
  
CmdPropset[0].rgProperties = CmdProperties;  
CmdPropset[0].cProperties = 1;  
CmdPropset[0].guidPropertySet = DBPROPSET_ROWSET;  
  
// Set asynch mode for command.  
CmdProperties[0].dwPropertyID = DBPROP_ROWSET_ASYNCH;  
CmdProperties[0].vValue.vt = VT_I4;  
CmdProperties[0].vValue.lVal = DBPROPVAL_ASYNCH_INITIALIZE;  
CmdProperties[0].dwOptions = DBPROPOPTIONS_REQUIRED;  
  
hr = pICommandProps->SetProperties(1, CmdPropset);  
  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_ISSAsynchStatus,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pISSAsynchStatus);  
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   // Do some work here...  
  
   hr = pISSAsynchStatus->WaitForAsynchCompletion(dwMilisecTimeOut);  
   if ( hr == S_OK)  
   {  
      hr = pISSAsynchStatus->QueryInterface(IID_IRowset, (void**)&pRowset);  
      pISSAsynchStatus->Release();  
   }  
}  
```  
  
 <span data-ttu-id="61248-140">**ISSAsynchStatus::WaitForAsynchCompletion** attend l’objet d’événement interne jusqu’à ce que l’opération s’exécutant de manière asynchrone soit terminée ou que la valeur *dwMilisecTimeOut* soit passée.</span><span class="sxs-lookup"><span data-stu-id="61248-140">**ISSAsynchStatus::WaitForAsynchCompletion** waits on the internal event object until the asynchronously executing operation is done or the *dwMilisecTimeOut* value is passed.</span></span>  
  
 <span data-ttu-id="61248-141">L'exemple suivant illustre le traitement asynchrone avec plusieurs jeux de résultats :</span><span class="sxs-lookup"><span data-stu-id="61248-141">The following example shows asynchronous processing with multiple result sets:</span></span>  
  
```  
DBPROP CmdProperties[1];  
  
// Set asynch mode for command.  
CmdProperties[0].dwPropertyID = DBPROP_ROWSET_ASYNCH;  
CmdProperties[0].vValue.vt = VT_I4;  
CmdProperties[0].vValue.lVal = DBPROPVAL_ASYNCH_INITIALIZE;  
  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_IMultipleResults,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pIMultipleResults);  
  
// Use GetResults for ISSAsynchStatus.  
hr = pIMultipleResults->GetResult(IID_ISSAsynchStatus, (void **) &pISSAsynchStatus);  
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   // Do some work here...  
  
   hr = pISSAsynchStatus->WaitForAsynchCompletion(dwMilisecTimeOut);  
   if (hr == S_OK)  
   {  
      hr = pISSAsynchStatus->QueryInterface(IID_IRowset, (void**)&pRowset);  
      pISSAsynchStatus->Release();  
   }  
}  
```  
  
 <span data-ttu-id="61248-142">Pour empêcher tout blocage, le client peut vérifier l'état d'une opération asynchrone en cours d'exécution, comme le montre l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="61248-142">To prevent blocking, the client can check the status of a running asynchronous operation, as in the following example:</span></span>  
  
```  
// Set the DBPROPVAL_ASYNCH_INITIALIZE bit in the   
// DBPROP_ROWSET_ASYNCH property before calling Execute().  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_ISSAsynchStatus,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pISSAsynchStatus);   
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   do{  
      // Do some work...  
      hr = pISSAsynchStatus->GetStatus(DB_NULL_HCHAPTER, DBASYNCHOP_OPEN, NULL, NULL, &ulAsynchPhase, NULL);  
   }while (DBASYNCHPHASE_COMPLETE != ulAsynchPhase)  
   if SUCCEEDED(hr)  
   {  
      hr = pISSAsynchStatus->QueryInterface(IID_IRowset, (void**)&pRowset);  
   }  
   pIDBAsynchStatus->Release();  
}  
```  
  
 <span data-ttu-id="61248-143">L'exemple suivant montre comment vous pouvez annuler l'opération asynchrone en cours d'exécution :</span><span class="sxs-lookup"><span data-stu-id="61248-143">The following example demonstrates how you can cancel the currently running asynchronous operation:</span></span>  
  
```  
// Set the DBPROPVAL_ASYNCH_INITIALIZE bit in the   
// DBPROP_ROWSET_ASYNCH property before calling Execute().  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_ISSAsynchStatus,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pISSAsynchStatus);  
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   // Do some work...  
   hr = pISSAsynchStatus->Abort(DB_NULL_HCHAPTER, DBASYNCHOP_OPEN);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="61248-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="61248-144">See Also</span></span>  
 <span data-ttu-id="61248-145">[Fonctionnalités de SQL Server Native Client](sql-server-native-client-features.md) </span><span class="sxs-lookup"><span data-stu-id="61248-145">[SQL Server Native Client Features](sql-server-native-client-features.md) </span></span>  
 <span data-ttu-id="61248-146">[Propriétés et comportements de l’ensemble de lignes](../../native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span><span class="sxs-lookup"><span data-stu-id="61248-146">[Rowset Properties and Behaviors](../../native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span></span>  
 [<span data-ttu-id="61248-147">ISSAsynchStatus &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="61248-147">ISSAsynchStatus &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-interfaces/issasynchstatus-ole-db.md)  
  
  
