---
title: Détail des erreurs SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- errors [OLE DB], error details
- IErrorRecords interface
- IErrorInfo interface
- OLE DB error handling, error details
- ISQLServerErrorInfo interface
ms.assetid: 51500ee3-3d78-47ec-b90f-ebfc55642e06
author: rothja
ms.author: jroth
ms.openlocfilehash: 4c03cf62dd274f9bcca213d33fb8969b26c9d980
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612793"
---
# <a name="sql-server-error-detail"></a><span data-ttu-id="4b9e7-102">Détail des erreurs SQL Server</span><span class="sxs-lookup"><span data-stu-id="4b9e7-102">SQL Server Error Detail</span></span>
  <span data-ttu-id="4b9e7-103">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client définit l’interface d’erreur spécifique au fournisseur [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="4b9e7-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the provider-specific error interface [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span></span> <span data-ttu-id="4b9e7-104">L'interface retourne davantage de détails sur une erreur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et s'avère utile en cas d'échec de l'exécution d'une commande ou d'opérations d'ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="4b9e7-104">The interface returns more detail about a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error and is valuable when command execution or rowset operations fail.</span></span>  
  
 <span data-ttu-id="4b9e7-105">Vous pouvez accéder à l’interface **ISQLServerErrorInfo** de deux manières.</span><span class="sxs-lookup"><span data-stu-id="4b9e7-105">There are two ways to obtain access to **ISQLServerErrorInfo** interface.</span></span>  
  
 <span data-ttu-id="4b9e7-106">Le consommateur peut appeler **IErrorRecords::GetCustomerErrorObject** pour obtenir un pointeur **ISQLServerErrorInfo**, comme illustré dans l’exemple de code suivant.</span><span class="sxs-lookup"><span data-stu-id="4b9e7-106">The consumer may call **IErrorRecords::GetCustomerErrorObject** to obtain an **ISQLServerErrorInfo** pointer, as shown in the following code sample.</span></span> <span data-ttu-id="4b9e7-107">(Il n’est pas nécessaire d’obtenir **ISQLErrorInfo**). **ISQLErrorInfo** et **ISQLServerErrorInfo** sont tous deux des objets d’erreur OLE DB personnalisés, **ISQLServerErrorInfo** étant l’interface à utiliser pour obtenir des informations sur les erreurs de serveur, notamment des détails sur le nom de la procédure et les numéros de ligne.</span><span class="sxs-lookup"><span data-stu-id="4b9e7-107">(There is no need to obtain **ISQLErrorInfo.**) Both **ISQLErrorInfo** and **ISQLServerErrorInfo** are custom OLE DB error objects, with **ISQLServerErrorInfo** being the interface to use to obtain information of server errors, including such details as procedure name and line numbers.</span></span>  
  
```  
// Get the SQL Server custom error object.  
if(FAILED(hr=pIErrorRecords->GetCustomErrorObject(  
   nRec, IID_ISQLServerErrorInfo,  
   (IUnknown**)&pISQLServerErrorErrorInfo)))  
```  
  
 <span data-ttu-id="4b9e7-108">L’autre méthode permettant d’obtenir un pointeur **ISQLServerErrorInfo** consiste à appeler la méthode **QueryInterface** sur un pointeur **ISQLErrorInfo** qui a déjà été obtenu.</span><span class="sxs-lookup"><span data-stu-id="4b9e7-108">Another way to get an **ISQLServerErrorInfo** pointer is to call the **QueryInterface** method on an already-obtained **ISQLErrorInfo** pointer.</span></span> <span data-ttu-id="4b9e7-109">Notez que comme **ISQLServerErrorInfo** contient un surensemble des informations disponibles auprès de **ISQLErrorInfo**, il est logique d’accéder directement à **ISQLServerErrorInfo** via **GetCustomerErrorObject**.</span><span class="sxs-lookup"><span data-stu-id="4b9e7-109">Note that because **ISQLServerErrorInfo** contains a superset of the information available from **ISQLErrorInfo**, it makes sense to go directly to **ISQLServerErrorInfo** through **GetCustomerErrorObject**.</span></span>  
  
 <span data-ttu-id="4b9e7-110">L’interface **ISQLServerErrorInfo** expose une fonction membre, [ISQLServerErrorInfo::GetErrorInfo](../native-client-ole-db-interfaces/isqlservererrorinfo-geterrorinfo-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="4b9e7-110">The **ISQLServerErrorInfo** interface exposes one member function, [ISQLServerErrorInfo::GetErrorInfo](../native-client-ole-db-interfaces/isqlservererrorinfo-geterrorinfo-ole-db.md).</span></span> <span data-ttu-id="4b9e7-111">La fonction retourne un pointeur à une structure SSERRORINFO et un pointeur à une mémoire tampon de chaîne.</span><span class="sxs-lookup"><span data-stu-id="4b9e7-111">The function returns a pointer to an SSERRORINFO structure and a pointer to a string buffer.</span></span> <span data-ttu-id="4b9e7-112">Les deux pointeurs référencent la mémoire que le consommateur doit libérer avec méthode **IMalloc::Free**.</span><span class="sxs-lookup"><span data-stu-id="4b9e7-112">Both pointers reference memory the consumer must deallocate by using the **IMalloc::Free** method.</span></span>  
  
 <span data-ttu-id="4b9e7-113">Les membres de la structure SSERRORINFO sont interprétés par le consommateur comme suit.</span><span class="sxs-lookup"><span data-stu-id="4b9e7-113">SSERRORINFO structure members are interpreted by the consumer as follows.</span></span>  
  
|<span data-ttu-id="4b9e7-114">Membre</span><span class="sxs-lookup"><span data-stu-id="4b9e7-114">Member</span></span>|<span data-ttu-id="4b9e7-115">Description</span><span class="sxs-lookup"><span data-stu-id="4b9e7-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="4b9e7-116">*pwszMessage*</span><span class="sxs-lookup"><span data-stu-id="4b9e7-116">*pwszMessage*</span></span>|<span data-ttu-id="4b9e7-117">Message d'erreur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b9e7-117">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message.</span></span> <span data-ttu-id="4b9e7-118">Identique à la chaîne retournée dans **IErrorInfo::GetDescription**.</span><span class="sxs-lookup"><span data-stu-id="4b9e7-118">Identical to the string returned in **IErrorInfo::GetDescription**.</span></span>|  
|<span data-ttu-id="4b9e7-119">*pwszServer*</span><span class="sxs-lookup"><span data-stu-id="4b9e7-119">*pwszServer*</span></span>|<span data-ttu-id="4b9e7-120">Nom de l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour la session.</span><span class="sxs-lookup"><span data-stu-id="4b9e7-120">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the session.</span></span>|  
|<span data-ttu-id="4b9e7-121">*pwszProcedure*</span><span class="sxs-lookup"><span data-stu-id="4b9e7-121">*pwszProcedure*</span></span>|<span data-ttu-id="4b9e7-122">S'il y a lieu, nom de la procédure d'où provient l'erreur.</span><span class="sxs-lookup"><span data-stu-id="4b9e7-122">If appropriate, the name of the procedure in which the error originated.</span></span> <span data-ttu-id="4b9e7-123">Sinon, une chaîne vide.</span><span class="sxs-lookup"><span data-stu-id="4b9e7-123">An empty string otherwise.</span></span>|  
|<span data-ttu-id="4b9e7-124">*lNative*</span><span class="sxs-lookup"><span data-stu-id="4b9e7-124">*lNative*</span></span>|<span data-ttu-id="4b9e7-125">Numéro d'erreur natif [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b9e7-125">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native error number.</span></span> <span data-ttu-id="4b9e7-126">Identique à la valeur retournée dans le paramètre *plNativeError* de **ISQLErrorInfo::GetSQLInfo**.</span><span class="sxs-lookup"><span data-stu-id="4b9e7-126">Identical to the value returned in the *plNativeError* parameter of **ISQLErrorInfo::GetSQLInfo**.</span></span>|  
|<span data-ttu-id="4b9e7-127">*bState*</span><span class="sxs-lookup"><span data-stu-id="4b9e7-127">*bState*</span></span>|<span data-ttu-id="4b9e7-128">État d'un message d'erreur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b9e7-128">State of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message.</span></span>|  
|<span data-ttu-id="4b9e7-129">*bClass*</span><span class="sxs-lookup"><span data-stu-id="4b9e7-129">*bClass*</span></span>|<span data-ttu-id="4b9e7-130">Gravité d'un message d'erreur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b9e7-130">Severity of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message.</span></span>|  
|<span data-ttu-id="4b9e7-131">*wLineNumber*</span><span class="sxs-lookup"><span data-stu-id="4b9e7-131">*wLineNumber*</span></span>|<span data-ttu-id="4b9e7-132">S'il y a lieu, numéro de ligne d'une procédure stockée sur laquelle s'est produite l'erreur.</span><span class="sxs-lookup"><span data-stu-id="4b9e7-132">When applicable, the line number of a stored procedure on which the error occurred.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4b9e7-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4b9e7-133">See Also</span></span>  
 <span data-ttu-id="4b9e7-134">[Sont](errors.md) </span><span class="sxs-lookup"><span data-stu-id="4b9e7-134">[Errors](errors.md) </span></span>  
 [<span data-ttu-id="4b9e7-135">RAISERROR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4b9e7-135">RAISERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/raiserror-transact-sql)  
  
  
