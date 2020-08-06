---
title: Utilisation de IRow::GetColumns | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- fetching rows
- IRow interface
- single row fetching [SQL Server Native Client]
- OLE DB rowsets, fetching
- rowsets [OLE DB], fetching
- GetColumns method
ms.assetid: 1f5d2e03-e6fe-4ea1-b71d-55d02b5d59ae
author: rothja
ms.author: jroth
ms.openlocfilehash: f323dda790946565bc0dbd63c9e1f9d17ac7494b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602817"
---
# <a name="using-irowgetcolumns"></a><span data-ttu-id="ce13a-102">Utilisation d'IRow::GetColumns</span><span class="sxs-lookup"><span data-stu-id="ce13a-102">Using IRow::GetColumns</span></span>
  <span data-ttu-id="ce13a-103">L’implémentation **IRow** permet un accès séquentiel de type « avant uniquement » aux colonnes.</span><span class="sxs-lookup"><span data-stu-id="ce13a-103">The **IRow** implementation allows forward-only sequential access to the columns.</span></span> <span data-ttu-id="ce13a-104">Vous pouvez accéder à toutes les colonnes d’une ligne avec un appel unique à **IRow::GetColumns**, ou appeler **IRow::GetColumns** chaque fois que vous accédez à plusieurs colonnes de la ligne.</span><span class="sxs-lookup"><span data-stu-id="ce13a-104">You can either access all the columns in the row with a single call to **IRow::GetColumns** or call **IRow::GetColumns** multiple times every time that you access several columns in the row.</span></span>  
  
 <span data-ttu-id="ce13a-105">Les appels multiples à **IRow::GetColumns** ne doivent pas se chevaucher.</span><span class="sxs-lookup"><span data-stu-id="ce13a-105">The multiple calls to **IRow::GetColumns** should not overlap.</span></span> <span data-ttu-id="ce13a-106">Par exemple, si le premier appel à **IRow::GetColumns** récupère les données des colonnes 1, 2 et 3, le deuxième appel à **IRow::GetColumns** doit appeler les colonnes 4, 5 et 6.</span><span class="sxs-lookup"><span data-stu-id="ce13a-106">For example, if the first call to **IRow::GetColumns** retrieves columns 1, 2, and 3, the second call to **IRow::GetColumns** should call for columns 4, 5, and 6.</span></span> <span data-ttu-id="ce13a-107">Si des appels ultérieurs à **IRow::GetColumns** se chevauchent, l’indicateur d’état (champ dwstatus dans DBCOLUMNACCESS) a la valeur DBSTATUS_E_UNAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ce13a-107">If later calls to **IRow::GetColumns** overlap, the status flag (dwstatus field in DBCOLUMNACCESS) is set to DBSTATUS_E_UNAVAILABLE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce13a-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ce13a-108">See Also</span></span>  
 [<span data-ttu-id="ce13a-109">Extraction d'une ligne unique avec IRow</span><span class="sxs-lookup"><span data-stu-id="ce13a-109">Fetching a Single Row with IRow</span></span>](fetching-a-single-row-with-irow.md)  
  
  
