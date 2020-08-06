---
title: Prochaine position de récupération (fetch) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- fetching rows
- OLE DB rowsets, fetching
- next fetch position
- rowsets [OLE DB], fetching
ms.assetid: 9ef74b3f-c9c0-492f-9b93-d65738a61abd
author: rothja
ms.author: jroth
ms.openlocfilehash: fcc771eef4acf603148bc4b4318e810b1bd72302
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696787"
---
# <a name="next-fetch-position"></a><span data-ttu-id="3fc6e-102">Prochaine position d'extraction</span><span class="sxs-lookup"><span data-stu-id="3fc6e-102">Next Fetch Position</span></span>
  <span data-ttu-id="3fc6e-103">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client effectue le suivi de la position d’extraction suivante afin qu’une séquence d’appels à la méthode **GetNextRows** (sans sauts, modifications de direction ou appels intermédiaires aux méthodes **FindNextRow**, **Seek**ou **RestartPosition** ) Lise l’ensemble de lignes entier sans ignorer ou répéter une ligne.</span><span class="sxs-lookup"><span data-stu-id="3fc6e-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider keeps track of the next fetch position so that a sequence of calls to the **GetNextRows** method (without skips, changes of direction, or intervening calls to the **FindNextRow**, **Seek**, or **RestartPosition** methods) reads the whole rowset without skipping or repeating any row.</span></span> <span data-ttu-id="3fc6e-104">La prochaine position de récupération (fetch) est modifiée en appelant **IRowset::GetNextRows**, **IRowset::RestartPosition**, **IRowsetIndex::Seek** ou **FindNextRow** avec une valeur *pBookmark* Null.</span><span class="sxs-lookup"><span data-stu-id="3fc6e-104">The next fetch position is changed either by calling **IRowset::GetNextRows**, **IRowset::RestartPosition**, or **IRowsetIndex::Seek**, or by calling **FindNextRow** with a null *pBookmark* value.</span></span> <span data-ttu-id="3fc6e-105">L’appel de **FindNextRow** avec une valeur *pBookmark* non Null n’affecte pas la prochaine position de récupération.</span><span class="sxs-lookup"><span data-stu-id="3fc6e-105">Calling **FindNextRow** with a nonnull *pBookmark* value does not affect the next fetch position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fc6e-106">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3fc6e-106">See Also</span></span>  
 [<span data-ttu-id="3fc6e-107">Extraction de lignes</span><span class="sxs-lookup"><span data-stu-id="3fc6e-107">Fetching Rows</span></span>](fetching-rows.md)  
  
  
