---
title: Mise à jour des données dans les ensembles de lignes | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- updating data [SQL Server]
- rowsets [OLE DB], updating data
- SQL Server Native Client OLE DB provider, rowsets
- OLE DB rowsets, updating data
- SQL Server Native Client OLE DB provider, data updates
- data updates [SQL Server], OLE DB
ms.assetid: 37769b1c-c480-419a-8c54-5cc420bf73db
author: rothja
ms.author: jroth
ms.openlocfilehash: 993cfb67d4e6b72eec7cc0537e9b47371e94af10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702867"
---
# <a name="updating-data-in-rowsets"></a><span data-ttu-id="89ab9-102">Mise à jour des données dans les ensembles de lignes</span><span class="sxs-lookup"><span data-stu-id="89ab9-102">Updating Data in Rowsets</span></span>
  <span data-ttu-id="89ab9-103">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client met à jour les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] données lorsqu’un consommateur met à jour un ensemble de lignes modifiable qui contient ces données.</span><span class="sxs-lookup"><span data-stu-id="89ab9-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider updates [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data when a consumer updates a modifiable rowset that contains that data.</span></span> <span data-ttu-id="89ab9-104">Un ensemble de lignes modifiable est créé lorsque le consommateur demande la prise en charge de l’interface **IRowsetChange** ou **IRowsetUpdate**.</span><span class="sxs-lookup"><span data-stu-id="89ab9-104">A modifiable rowset is created when the consumer requests support for either the **IRowsetChange** or **IRowsetUpdate** interface.</span></span>  
  
 <span data-ttu-id="89ab9-105">Tous les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ensembles de lignes de OLE DB fournisseur-modifiables Native Client utilisent des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] curseurs pour prendre en charge l’ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="89ab9-105">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider-modifiable rowsets use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursors to support the rowset.</span></span> <span data-ttu-id="89ab9-106">La propriété d'ensemble de lignes DBPROP_LOCKMODE modifie le comportement du contrôle concurrentiel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] des curseurs et détermine le comportement de l'extraction de lignes d'un ensemble de lignes et la génération d'erreurs d'intégrité des données dans les ensembles de lignes pouvant être mis à jour.</span><span class="sxs-lookup"><span data-stu-id="89ab9-106">The rowset property DBPROP_LOCKMODE alters [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] concurrency control behavior in cursors and determines the behavior of rowset row fetching and data integrity error generation in updatable rowsets.</span></span>  
  
 <span data-ttu-id="89ab9-107">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client prend en charge la synchronisation de ligne avant ou après une mise à jour.</span><span class="sxs-lookup"><span data-stu-id="89ab9-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports row synchronization before or after an update.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89ab9-108">IRowChange::SetColumns permet de définir les valeurs d'une ou de plusieurs colonnes nommées d'un objet ligne.</span><span class="sxs-lookup"><span data-stu-id="89ab9-108">IRowChange::SetColumns is available to set the values of one or more named columns of a row object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="89ab9-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="89ab9-109">In This Section</span></span>  
  
-   [<span data-ttu-id="89ab9-110">Mise à jour des données dans les curseurs SQL Server</span><span class="sxs-lookup"><span data-stu-id="89ab9-110">Updating Data in SQL Server Cursors</span></span>](updating-data-in-sql-server-cursors.md)  
  
-   [<span data-ttu-id="89ab9-111">Resynchronisation des lignes</span><span class="sxs-lookup"><span data-stu-id="89ab9-111">Resynchronizing Rows</span></span>](updating-data-in-rowsets-resynchronizing-rows.md)  
  
## <a name="see-also"></a><span data-ttu-id="89ab9-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="89ab9-112">See Also</span></span>  
 [<span data-ttu-id="89ab9-113">Ensembles de lignes</span><span class="sxs-lookup"><span data-stu-id="89ab9-113">Rowsets</span></span>](rowsets.md)  
  
  
