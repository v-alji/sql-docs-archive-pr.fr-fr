---
title: IBCPSession::BCPWriteFmt (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPWriteFmt (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPWriteFmt method
ms.assetid: add50425-2ed6-411a-a391-4ce63c364892
author: rothja
ms.author: jroth
ms.openlocfilehash: ee4dcb5809c0f0fbb6d3f7aba6f4af5f6991e0e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613454"
---
# <a name="ibcpsessionbcpwritefmt-ole-db"></a><span data-ttu-id="918fd-102">IBCPSession::BCPWriteFmt (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="918fd-102">IBCPSession::BCPWriteFmt (OLE DB)</span></span>
  <span data-ttu-id="918fd-103">Écrit les informations de format pour chaque colonne dans le fichier de format.</span><span class="sxs-lookup"><span data-stu-id="918fd-103">Writes format information for each column to the format file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="918fd-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="918fd-104">Syntax</span></span>  
  
```  
  
HRESULT BCPWriteFmt(   
const wchar_t *pwszFormatFile);  
```  
  
## <a name="remarks"></a><span data-ttu-id="918fd-105">Notes</span><span class="sxs-lookup"><span data-stu-id="918fd-105">Remarks</span></span>  
 <span data-ttu-id="918fd-106">Le fichier de format spécifie le format de données d'un fichier de données créé par le biais d'une copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="918fd-106">The format file specifies the data format of a data file created by bulk copy.</span></span> <span data-ttu-id="918fd-107">Les appels aux méthodes [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) et [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) définissent le format du fichier de données.</span><span class="sxs-lookup"><span data-stu-id="918fd-107">Calls to the [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) and [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) methods define the format of the data file.</span></span> <span data-ttu-id="918fd-108">La méthode **BCPWriteFmt** enregistre cette définition dans le fichier référencé par l'argument pwszFormatFile.</span><span class="sxs-lookup"><span data-stu-id="918fd-108">The **BCPWriteFmt** method saves this definition in the file referenced by the pwszFormatFile argument.</span></span>  
  
 <span data-ttu-id="918fd-109">La méthode **BCPWriteFmt** peut enregistrer les fichiers de format dans un format XML ou texte.</span><span class="sxs-lookup"><span data-stu-id="918fd-109">The **BCPWriteFmt** method can save the format files in either xml or text format.</span></span> <span data-ttu-id="918fd-110">Vous devez l’indiquer au moyen de l’option de contrôle BCP_OPTION_XML avec la méthode [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="918fd-110">This must be indicated by using the BCP_OPTION_XML control option with the [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md) method.</span></span>  
  
 <span data-ttu-id="918fd-111">Pour charger un fichier de format enregistré, utilisez la méthode [IBCPSession::BCPReadFmt](ibcpsession-bcpreadfmt-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="918fd-111">To load a saved format file, use the [IBCPSession::BCPReadFmt](ibcpsession-bcpreadfmt-ole-db.md) method.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="918fd-112">Arguments</span><span class="sxs-lookup"><span data-stu-id="918fd-112">Arguments</span></span>  
 <span data-ttu-id="918fd-113">*pwszFormatFile*[in]</span><span class="sxs-lookup"><span data-stu-id="918fd-113">*pwszFormatFile*[in]</span></span>  
 <span data-ttu-id="918fd-114">Chemin d'accès et nom du fichier contenant les valeurs de format du fichier de données.</span><span class="sxs-lookup"><span data-stu-id="918fd-114">The path and file name of the file containing the format values for the data file.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="918fd-115">Codet de retour</span><span class="sxs-lookup"><span data-stu-id="918fd-115">Return Code Values</span></span>  
 <span data-ttu-id="918fd-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="918fd-116">S_OK</span></span>  
 <span data-ttu-id="918fd-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="918fd-117">The method succeeded.</span></span>  
  
 <span data-ttu-id="918fd-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="918fd-118">E_FAIL</span></span>  
 <span data-ttu-id="918fd-119">Une erreur spécifique au fournisseur s’est produite ; Pour plus d’informations, utilisez l’interface [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="918fd-119">A provider-specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="918fd-120">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="918fd-120">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="918fd-121">Erreur de mémoire insuffisante.</span><span class="sxs-lookup"><span data-stu-id="918fd-121">Out-of-memory error.</span></span>  
  
 <span data-ttu-id="918fd-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="918fd-122">E_UNEXPECTED</span></span>  
 <span data-ttu-id="918fd-123">L'appel à la méthode était inattendu.</span><span class="sxs-lookup"><span data-stu-id="918fd-123">The call to the method was unexpected.</span></span> <span data-ttu-id="918fd-124">Par exemple, la méthode [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) n’a pas été appelée avant d’appeler cette méthode.</span><span class="sxs-lookup"><span data-stu-id="918fd-124">For example, the [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) method was not called before calling this method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="918fd-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="918fd-125">See Also</span></span>  
 <span data-ttu-id="918fd-126">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="918fd-126">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="918fd-127">Exécution d'opérations de copie en bloc</span><span class="sxs-lookup"><span data-stu-id="918fd-127">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
