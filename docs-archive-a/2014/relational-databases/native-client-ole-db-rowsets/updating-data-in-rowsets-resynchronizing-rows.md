---
title: Resynchronisation des lignes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- synchronization [OLE DB]
- IRowsetResynch interface
- resynchronizing rows
- data updates [SQL Server], OLE DB
ms.assetid: d2d30505-a878-4aa9-b821-53d8118a45a5
author: rothja
ms.author: jroth
ms.openlocfilehash: 47c628ae583f3e635f422d5146f64508372a1114
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602822"
---
# <a name="resynchronizing-rows"></a><span data-ttu-id="da9d1-102">Resynchronisation des lignes</span><span class="sxs-lookup"><span data-stu-id="da9d1-102">Resynchronizing Rows</span></span>
  <span data-ttu-id="da9d1-103">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client prend en charge **IRowsetResynch** [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uniquement sur les ensembles de lignes pris en charge par les curseurs.</span><span class="sxs-lookup"><span data-stu-id="da9d1-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **IRowsetResynch** on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursor-supported rowsets only.</span></span> <span data-ttu-id="da9d1-104">**IRowsetResynch** n’est pas disponible à la demande.</span><span class="sxs-lookup"><span data-stu-id="da9d1-104">**IRowsetResynch** is not available on demand.</span></span> <span data-ttu-id="da9d1-105">Le consommateur doit demander l'interface avant d'ouvrir l'ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="da9d1-105">The consumer must request the interface before opening the rowset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da9d1-106">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="da9d1-106">See Also</span></span>  
 [<span data-ttu-id="da9d1-107">Mise à jour des données dans les ensembles de lignes</span><span class="sxs-lookup"><span data-stu-id="da9d1-107">Updating Data in Rowsets</span></span>](updating-data-in-rowsets.md)  
  
  
