---
title: IBCPSession (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- IBCPSession interface
ms.assetid: 00d0311f-8b71-4ad6-824d-0e89119347a3
author: rothja
ms.author: jroth
ms.openlocfilehash: 0d32da9c06a200d5924dbae18d6b7513f46c88ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707448"
---
# <a name="ibcpsession-ole-db"></a><span data-ttu-id="3994d-102">IBCPSession (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="3994d-102">IBCPSession (OLE DB)</span></span>
  <span data-ttu-id="3994d-103">L’interface **IBCPSession** expose la prise en charge des opérations de copie en bloc basées sur des fichiers [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3994d-103">The **IBCPSession** interface exposes support for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] file-based bulk copy operations.</span></span> <span data-ttu-id="3994d-104">L'interface **IBCPSession** est exposée dans le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sous le même niveau que Sessions.</span><span class="sxs-lookup"><span data-stu-id="3994d-104">The **IBCPSession** interface is exposed in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider under the same level as Sessions.</span></span> <span data-ttu-id="3994d-105">Dans le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, les objets sources de données sont des fabriques pour les objets Session et les opérations de copie en bloc sont spécifiées dans la propriété de connexion SSPROP_ENABLEBULKCOPY.</span><span class="sxs-lookup"><span data-stu-id="3994d-105">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, data source objects are factories for Session objects, and bulk copy operations are specified in the connection property SSPROP_ENABLEBULKCOPY.</span></span> <span data-ttu-id="3994d-106">De plus, la propriété SSPROP_ENABLEFASTLOAD doit avoir la valeur vrai.</span><span class="sxs-lookup"><span data-stu-id="3994d-106">In addition, the SSPROP_ENABLEFASTLOAD property should be set to true.</span></span>  
  
 <span data-ttu-id="3994d-107">L'appel de la méthode **IDBCreateSession::CreateSession** provoquera alors la création d'un objet **BulkCopySession** .</span><span class="sxs-lookup"><span data-stu-id="3994d-107">Calling the **IDBCreateSession::CreateSession** method will then result in the creation of a **BulkCopySession** object.</span></span> <span data-ttu-id="3994d-108">Toutes les méthodes de copie en bloc basées sur des fichiers exposées par le biais de l'objet **IBCPSession** peuvent ensuite être appelées avec des signatures presque semblables sur l'interface **IBCPSession** de cet objet **IBCPSession** .</span><span class="sxs-lookup"><span data-stu-id="3994d-108">All the file-based bulk copy methods exposed through the **IBCPSession** object are then callable with nearly similar signatures on this **IBCPSession** object's **IBCPSession** interface.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3994d-109">Le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client prend en charge les opérations de copie en bloc basées sur mémoire par le biais de l'interface [IRowsetFastLoad](irowsetfastload-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="3994d-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports memory-based bulk copy operations through the [IRowsetFastLoad](irowsetfastload-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="3994d-110">Pour plus d’informations sur l’utilisation du [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client pour les opérations de copie en bloc, consultez [exécution d’opérations de copie en bloc](../native-client/features/performing-bulk-copy-operations.md).</span><span class="sxs-lookup"><span data-stu-id="3994d-110">For more information about using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider for bulk copy operations, see [Performing Bulk Copy Operations](../native-client/features/performing-bulk-copy-operations.md).</span></span>  
  
 <span data-ttu-id="3994d-111">Pour obtenir un exemple qui indique comment utiliser l'interface **IBCPSession**, consultez [IBCPSession::BCPDone &#40;OLE DB&#41;](ibcpsession-bcpdone-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="3994d-111">For a sample showing how to use the **IBCPSession** interface, see [IBCPSession::BCPDone &#40;OLE DB&#41;](ibcpsession-bcpdone-ole-db.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3994d-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="3994d-112">In This Section</span></span>  
  
|<span data-ttu-id="3994d-113">Méthode</span><span class="sxs-lookup"><span data-stu-id="3994d-113">Method</span></span>|<span data-ttu-id="3994d-114">Description</span><span class="sxs-lookup"><span data-stu-id="3994d-114">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3994d-115">IBCPSession::BCPColFmt &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="3994d-115">IBCPSession::BCPColFmt &#40;OLE DB&#41;</span></span>](ibcpsession-bcpcolfmt-ole-db.md)|<span data-ttu-id="3994d-116">Crée une liaison entre des variables de programme et des colonnes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3994d-116">Creates a binding between program variables and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] columns.</span></span>|  
|[<span data-ttu-id="3994d-117">IBCPSession::BCPColumns &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="3994d-117">IBCPSession::BCPColumns &#40;OLE DB&#41;</span></span>](ibcpsession-bcpcolumns-ole-db.md)|<span data-ttu-id="3994d-118">Définit le nombre de champs qui doivent être liés aux colonnes dans une table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3994d-118">Sets the number of fields that are to be bound to the columns in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>|  
|[<span data-ttu-id="3994d-119">IBCPSession::BCPControl &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="3994d-119">IBCPSession::BCPControl &#40;OLE DB&#41;</span></span>](ibcpsession-bcpcontrol-ole-db.md)|<span data-ttu-id="3994d-120">Définit les options pour une opération de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="3994d-120">Sets the options for a bulk copy operation.</span></span>|  
|[<span data-ttu-id="3994d-121">IBCPSession::BCPDone &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="3994d-121">IBCPSession::BCPDone &#40;OLE DB&#41;</span></span>](ibcpsession-bcpdone-ole-db.md)|<span data-ttu-id="3994d-122">Valide les lignes restantes à envoyer à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3994d-122">Commits the remaining rows to be sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="3994d-123">IBCPSession::BCPExec &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="3994d-123">IBCPSession::BCPExec &#40;OLE DB&#41;</span></span>](ibcpsession-bcpexec-ole-db.md)|<span data-ttu-id="3994d-124">Effectue l'opération de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="3994d-124">Performs the bulk copy operation.</span></span>|  
|[<span data-ttu-id="3994d-125">IBCPSession::BCPInit &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="3994d-125">IBCPSession::BCPInit &#40;OLE DB&#41;</span></span>](ibcpsession-bcpinit-ole-db.md)|<span data-ttu-id="3994d-126">Initialise la structure de copie en bloc, effectue une vérification des erreurs, vérifie que les données et les noms de fichiers de format sont corrects, puis les ouvre.</span><span class="sxs-lookup"><span data-stu-id="3994d-126">Initializes the bulk copy structure, performs some error checking, verifies that the data and format file names are correct, and then opens them.</span></span>|  
|[<span data-ttu-id="3994d-127">IBCPSession::BCPReadFmt &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="3994d-127">IBCPSession::BCPReadFmt &#40;OLE DB&#41;</span></span>](ibcpsession-bcpreadfmt-ole-db.md)|<span data-ttu-id="3994d-128">Lit les informations de format pour chaque colonne à partir du fichier de format.</span><span class="sxs-lookup"><span data-stu-id="3994d-128">Reads format information for each column from the format file.</span></span>|  
|[<span data-ttu-id="3994d-129">IBCPSession::BCPWriteFmt &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="3994d-129">IBCPSession::BCPWriteFmt &#40;OLE DB&#41;</span></span>](ibcpsession-bcpwritefmt-ole-db.md)|<span data-ttu-id="3994d-130">Écrit les informations de format pour chaque colonne dans le fichier de format.</span><span class="sxs-lookup"><span data-stu-id="3994d-130">Writes format information for each column to the format file.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3994d-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3994d-131">See Also</span></span>  
 [<span data-ttu-id="3994d-132">Interfaces &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="3994d-132">Interfaces &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/interfaces-ole-db.md)  
  
  
