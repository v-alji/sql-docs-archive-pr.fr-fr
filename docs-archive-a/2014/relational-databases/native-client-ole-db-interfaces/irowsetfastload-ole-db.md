---
title: IRowsetFastLoad (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- IRowsetFastLoad interface
ms.assetid: d19a7097-48d9-409a-aff9-277891b7aca7
author: rothja
ms.author: jroth
ms.openlocfilehash: 7ecf72f0015d9ed197b3b7a33d4f9bb3246134b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613437"
---
# <a name="irowsetfastload-ole-db"></a><span data-ttu-id="ca91c-102">IRowsetFastLoad (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="ca91c-102">IRowsetFastLoad (OLE DB)</span></span>
  <span data-ttu-id="ca91c-103">L' `IRowsetFastLoad` interface expose la prise en charge des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] opérations de copie en bloc basées sur la mémoire.</span><span class="sxs-lookup"><span data-stu-id="ca91c-103">The `IRowsetFastLoad` interface exposes support for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory-based bulk-copy operations.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="ca91c-104">Les consommateurs de fournisseurs OLE DB Native Client utilisent l’interface pour ajouter rapidement des données à une [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table existante.</span><span class="sxs-lookup"><span data-stu-id="ca91c-104">Native Client OLE DB provider consumers use the interface to rapidly add data to an existing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="ca91c-105">Si vous affectez la valeur VARIANT_TRUE à SSPROP_ENABLEFASTLOAD pour une session, vous ne pouvez pas lire les données des ensembles de lignes retournés ultérieurement à partir de cette session.</span><span class="sxs-lookup"><span data-stu-id="ca91c-105">If you set SSPROP_ENABLEFASTLOAD to VARIANT_TRUE for a session, you cannot read data from rowsets subsequently returned from that session.</span></span> <span data-ttu-id="ca91c-106">Lorsque SSPROP_ENABLEFASTLOAD a la valeur VARIANT_TRUE, tous les ensembles de lignes créés sur la session sont du type IRowsetFastLoad.</span><span class="sxs-lookup"><span data-stu-id="ca91c-106">When SSPROP_ENABLEFASTLOAD is set to VARIANT_TRUE, all rowsets created on the session will be of type IRowsetFastLoad.</span></span> <span data-ttu-id="ca91c-107">Les ensembles de lignes IRowsetFastLoad ne prennent pas en charge la fonctionnalité de récupération (fetch) des ensembles de lignes. Par conséquent, les données issues de ces ensembles de lignes ne peuvent pas être lues.</span><span class="sxs-lookup"><span data-stu-id="ca91c-107">IRowsetFastLoad rowsets do not support rowset fetch functionality; therefore, data from these rowsets cannot be read.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ca91c-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="ca91c-108">In This Section</span></span>  
  
|<span data-ttu-id="ca91c-109">Méthode</span><span class="sxs-lookup"><span data-stu-id="ca91c-109">Method</span></span>|<span data-ttu-id="ca91c-110">Description</span><span class="sxs-lookup"><span data-stu-id="ca91c-110">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ca91c-111">IRowsetFastLoad::Commit &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="ca91c-111">IRowsetFastLoad::Commit &#40;OLE DB&#41;</span></span>](irowsetfastload-commit-ole-db.md)|<span data-ttu-id="ca91c-112">Marque la fin d'un lot de lignes insérées et écrit les lignes dans la table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ca91c-112">Marks the end of a batch of inserted rows and writes the rows to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>|  
|[<span data-ttu-id="ca91c-113">IRowsetFastLoad::InsertRow &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="ca91c-113">IRowsetFastLoad::InsertRow &#40;OLE DB&#41;</span></span>](irowsetfastload-insertrow-ole-db.md)|<span data-ttu-id="ca91c-114">Ajoute une ligne à l'ensemble de lignes de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="ca91c-114">Adds a row to the bulk copy rowset.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca91c-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ca91c-115">See Also</span></span>  
 <span data-ttu-id="ca91c-116">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="ca91c-116">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span></span>  
 <span data-ttu-id="ca91c-117">[Copier des données en bloc à l’aide de IRowsetFastLoad &#40;OLE DB&#41;](../native-client-ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="ca91c-117">[Bulk Copy Data Using IRowsetFastLoad &#40;OLE DB&#41;](../native-client-ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md) </span></span>  
 [<span data-ttu-id="ca91c-118">Envoyer des données BLOB vers SQL SERVER en utilisant IROWSETFASTLOAD et ISEQUENTIALSTREAM &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="ca91c-118">Send BLOB Data to SQL SERVER Using IROWSETFASTLOAD and ISEQUENTIALSTREAM &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md)  
  
  
