---
title: Erreurs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- OLE/COM errors
- errors [OLE DB]
- OLE DB error handling, about error handling
- OLE DB error handling
ms.assetid: bd0612f4-96ef-4919-b0f9-b5447210fe93
author: rothja
ms.author: jroth
ms.openlocfilehash: 0560a31b60a10e278f621aa53f1c7fa038fe8039
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612802"
---
# <a name="errors"></a><span data-ttu-id="68982-102">Erreurs</span><span class="sxs-lookup"><span data-stu-id="68982-102">Errors</span></span>
  <span data-ttu-id="68982-103">Les objets OLE/COM signalent les erreurs via le code de retour HRESULT des fonctions membres objets.</span><span class="sxs-lookup"><span data-stu-id="68982-103">OLE/COM objects report errors through the HRESULT return code of object member functions.</span></span> <span data-ttu-id="68982-104">Un valeur HRESULT OLE/COM est une structure de bits comprimée.</span><span class="sxs-lookup"><span data-stu-id="68982-104">An OLE/COM HRESULT is a bit-packed structure.</span></span> <span data-ttu-id="68982-105">OLE fournit des macros qui déréférencent les membres de la structure.</span><span class="sxs-lookup"><span data-stu-id="68982-105">OLE provides macros that dereference structure members.</span></span>  
  
 <span data-ttu-id="68982-106">OLE/COM spécifie l’interface **IErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="68982-106">OLE/COM specifies the **IErrorInfo** interface.</span></span> <span data-ttu-id="68982-107">L’interface propose des méthodes comme **GetDescription**.</span><span class="sxs-lookup"><span data-stu-id="68982-107">The interface exposes methods such as **GetDescription**.</span></span> <span data-ttu-id="68982-108">Ceci permet aux clients d'extraire des informations détaillées sur les erreurs à partir des serveurs OLE/COM.</span><span class="sxs-lookup"><span data-stu-id="68982-108">This allows clients to extract error details from OLE/COM servers.</span></span> <span data-ttu-id="68982-109">OLE DB étend **IErrorInfo** pour prendre en charge le retour de plusieurs paquets d’informations d’erreur lors de l’exécution d’une fonction à un seul membre.</span><span class="sxs-lookup"><span data-stu-id="68982-109">OLE DB extends **IErrorInfo** to support the return of multiple error information packets on a single-member function execution.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="68982-110">peut retourner plusieurs erreurs.</span><span class="sxs-lookup"><span data-stu-id="68982-110">can return multiple errors.</span></span> <span data-ttu-id="68982-111">Une application peut récupérer les erreurs de serveur une par une en appelant [IMultipleResults::GetResult](https://go.microsoft.com/fwlink/?LinkId=129630) en combinaison avec ISQLErrorInfo et IErrorRecords.</span><span class="sxs-lookup"><span data-stu-id="68982-111">An application can retrieve server errors one at a time by calling [IMultipleResults::GetResult](https://go.microsoft.com/fwlink/?LinkId=129630) combined with ISQLErrorInfo and IErrorRecords.</span></span>  
  
 <span data-ttu-id="68982-112">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client expose les OLE DB les interfaces **IErrorInfo**, personnalisées `ISQLErrorInfo` et spécifiques au fournisseur. [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md)</span><span class="sxs-lookup"><span data-stu-id="68982-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the OLE DB record-enhanced **IErrorInfo**, the custom `ISQLErrorInfo`, and the provider-specific [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) error object interfaces.</span></span>  
  
 <span data-ttu-id="68982-113">Pour plus d’informations sur le suivi des erreurs, consultez [Suivi de l’accès aux données](https://go.microsoft.com/fwlink/?LinkId=125805).</span><span class="sxs-lookup"><span data-stu-id="68982-113">For information about tracing errors, see [Data Access Tracing](https://go.microsoft.com/fwlink/?LinkId=125805).</span></span> <span data-ttu-id="68982-114">Pour plus d’informations sur les améliorations du suivi des erreurs ajoutées dans [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], consultez [Accès aux informations de diagnostic dans le journal des événements étendus](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span><span class="sxs-lookup"><span data-stu-id="68982-114">For information about enhancements to error tracing added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], see [Accessing Diagnostic Information in the Extended Events Log](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="68982-115">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="68982-115">In This Section</span></span>  
  
-   [<span data-ttu-id="68982-116">Codes de retour</span><span class="sxs-lookup"><span data-stu-id="68982-116">Return Codes</span></span>](return-codes.md)  
  
-   [<span data-ttu-id="68982-117">Informations dans les interfaces d’erreur</span><span class="sxs-lookup"><span data-stu-id="68982-117">Information in Error Interfaces</span></span>](information-in-error-interfaces.md)  
  
-   [<span data-ttu-id="68982-118">Détails des erreurs SQL Server</span><span class="sxs-lookup"><span data-stu-id="68982-118">SQL Server Error Detail</span></span>](sql-server-error-detail.md)  
  
-   [<span data-ttu-id="68982-119">Extraction des informations sur les erreurs</span><span class="sxs-lookup"><span data-stu-id="68982-119">Retrieving Error Information</span></span>](retrieving-error-information.md)  
  
-   [<span data-ttu-id="68982-120">Résultats des messages SQL Server</span><span class="sxs-lookup"><span data-stu-id="68982-120">SQL Server Message Results</span></span>](sql-server-message-results.md)  
  
## <a name="see-also"></a><span data-ttu-id="68982-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="68982-121">See Also</span></span>  
 [<span data-ttu-id="68982-122">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="68982-122">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
