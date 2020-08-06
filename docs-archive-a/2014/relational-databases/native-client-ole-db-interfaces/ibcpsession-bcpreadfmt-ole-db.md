---
title: IBCPSession::BCPReadFmt (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPReadFmt (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPReadFmt method
ms.assetid: e2a12050-94e4-48a3-8a48-b780d646f116
author: rothja
ms.author: jroth
ms.openlocfilehash: ca811dceb8ab6771e3bdd6689a8e11eca6a0e3ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707447"
---
# <a name="ibcpsessionbcpreadfmt-ole-db"></a><span data-ttu-id="79d4c-102">IBCPSession::BCPReadFmt (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="79d4c-102">IBCPSession::BCPReadFmt (OLE DB)</span></span>
  <span data-ttu-id="79d4c-103">Lit les informations de format pour chaque colonne à partir du fichier de format.</span><span class="sxs-lookup"><span data-stu-id="79d4c-103">Reads format information for each column from the format file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79d4c-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="79d4c-104">Syntax</span></span>  
  
```  
  
HRESULT BCPReadFmt(   
const wchar_t *pwszFormatFile);  
```  
  
## <a name="remarks"></a><span data-ttu-id="79d4c-105">Notes</span><span class="sxs-lookup"><span data-stu-id="79d4c-105">Remarks</span></span>  
 <span data-ttu-id="79d4c-106">La méthode **BCPReadFmt** est utilisée pour lire les données d'un fichier de format qui spécifie le format des données dans le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="79d4c-106">The **BCPReadFmt** method is used for reading data from a format file that specifies the format of data in the data file.</span></span> <span data-ttu-id="79d4c-107">Cette méthode est capable de détecter la version correcte du fichier de format.</span><span class="sxs-lookup"><span data-stu-id="79d4c-107">This method is capable of detecting the correct version of the format file.</span></span> <span data-ttu-id="79d4c-108">Elle peut détecter automatiquement si le fichier de format est au format xml ou dans un ancien format et qu'il se comporte en conséquence.</span><span class="sxs-lookup"><span data-stu-id="79d4c-108">It can automatically detect whether the format file is in xml or old style text format and behaves accordingly.</span></span> <span data-ttu-id="79d4c-109">Les fichiers de format versions 6.0 et supérieures sont prises en charge par l'utilitaire de copie en bloc (BCP) du fournisseur OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="79d4c-109">The format file versions supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider BCP are version 6.0 or newer.</span></span>  
  
 <span data-ttu-id="79d4c-110">Après avoir lu les valeurs de format, la méthode **BCPReadFmt** effectue les appels appropriés aux méthodes [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) et [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="79d4c-110">After the **BCPReadFmt** method reads the format values, it makes the appropriate calls to the [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) and [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) methods.</span></span> <span data-ttu-id="79d4c-111">L'utilisateur n'a pas besoin d'analyser un fichier de format et d'effectuer ces appels.</span><span class="sxs-lookup"><span data-stu-id="79d4c-111">There is no need for the user to parse a format file and make these calls.</span></span>  
  
 <span data-ttu-id="79d4c-112">Pour enregistrer un fichier de format, appelez la méthode [IBCPSession::BCPWriteFmt](ibcpsession-bcpwritefmt-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="79d4c-112">To save a format file, call the [IBCPSession::BCPWriteFmt](ibcpsession-bcpwritefmt-ole-db.md) method.</span></span> <span data-ttu-id="79d4c-113">Les appels à la méthode **BCPReadFmt** peuvent référencer des formats enregistrés.</span><span class="sxs-lookup"><span data-stu-id="79d4c-113">Calls to the **BCPReadFmt** method can reference saved formats.</span></span> <span data-ttu-id="79d4c-114">L'utilitaire**bcp**peut également enregistrer des formats de données définis par l'utilisateur dans des fichiers qui peuvent être référencés par la méthode **BCPReadFmt** .</span><span class="sxs-lookup"><span data-stu-id="79d4c-114">Alternatively, the bulk-copy utility (**bcp**) can save user-defined data formats in files that can be referenced by the **BCPReadFmt** method.</span></span>  
  
 <span data-ttu-id="79d4c-115">La `BCP_OPTION_DELAYREADFMT` valeur du paramètre *EOption* de [IBCPSession :: BCPControl](ibcpsession-bcpcontrol-ole-db.md) modifie le comportement de IBCPSession :: BCPReadFmt.</span><span class="sxs-lookup"><span data-stu-id="79d4c-115">The `BCP_OPTION_DELAYREADFMT` value of the *eOption* parameter of [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md) modifies the behavior of IBCPSession::BCPReadFmt.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="79d4c-116">Arguments</span><span class="sxs-lookup"><span data-stu-id="79d4c-116">Arguments</span></span>  
 <span data-ttu-id="79d4c-117">*pwszFormatFile*[in]</span><span class="sxs-lookup"><span data-stu-id="79d4c-117">*pwszFormatFile*[in]</span></span>  
 <span data-ttu-id="79d4c-118">Chemin d'accès et nom du fichier contenant les valeurs de format du fichier de données.</span><span class="sxs-lookup"><span data-stu-id="79d4c-118">The path and file name of the file containing the format values for the data file.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="79d4c-119">Codet de retour</span><span class="sxs-lookup"><span data-stu-id="79d4c-119">Return Code Values</span></span>  
 <span data-ttu-id="79d4c-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="79d4c-120">S_OK</span></span>  
 <span data-ttu-id="79d4c-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="79d4c-121">The method succeeded.</span></span>  
  
 <span data-ttu-id="79d4c-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="79d4c-122">E_FAIL</span></span>  
 <span data-ttu-id="79d4c-123">Une erreur spécifique au fournisseur s’est produite. Pour obtenir des informations détaillées, utilisez l’interface [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="79d4c-123">A provider-specific error occurred, for detailed information use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="79d4c-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="79d4c-124">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="79d4c-125">Erreur de mémoire insuffisante.</span><span class="sxs-lookup"><span data-stu-id="79d4c-125">Out of memory error.</span></span>  
  
 <span data-ttu-id="79d4c-126">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="79d4c-126">E_UNEXPECTED</span></span>  
 <span data-ttu-id="79d4c-127">L'appel à la méthode était inattendu.</span><span class="sxs-lookup"><span data-stu-id="79d4c-127">The call to the method was unexpected.</span></span> <span data-ttu-id="79d4c-128">Par exemple, la méthode [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) n’a pas été appelée avant d’appeler cette méthode.</span><span class="sxs-lookup"><span data-stu-id="79d4c-128">For example, the [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) method was not called before calling this method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79d4c-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="79d4c-129">See Also</span></span>  
 <span data-ttu-id="79d4c-130">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="79d4c-130">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="79d4c-131">Exécution d'opérations de copie en bloc</span><span class="sxs-lookup"><span data-stu-id="79d4c-131">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
