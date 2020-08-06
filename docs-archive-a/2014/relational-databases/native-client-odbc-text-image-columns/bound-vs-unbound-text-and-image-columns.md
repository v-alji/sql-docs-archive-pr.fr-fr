---
title: Colonnes de texte et d’image liées et non liées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- text columns [ODBC]
- SQL Server Native Client ODBC driver, image columns
- SQL Server Native Client ODBC driver, text columns
- data types [ODBC], image
- data types [ODBC], text
- columns [ODBC]
- ODBC data types, image columns
- ODBC data types, text columns
- image columns [ODBC]
ms.assetid: ffd3442e-d880-46e9-b848-2365a09a2406
author: rothja
ms.author: jroth
ms.openlocfilehash: 20a91d26ac8c2d1201386cb19bde13b49a3dbada
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709308"
---
# <a name="bound-vs-unbound-text-and-image-columns"></a><span data-ttu-id="d9a2f-102">Colonnes de texte et d'image liées et non liées</span><span class="sxs-lookup"><span data-stu-id="d9a2f-102">Bound vs. Unbound Text and Image Columns</span></span>
  <span data-ttu-id="d9a2f-103">Lors de l’utilisation de curseurs côté serveur, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client est optimisé pour ne pas transmettre les données des colonnes de **texte**, **ntext**ou **image** non liées au moment où **SQLFetch** est exécutée.</span><span class="sxs-lookup"><span data-stu-id="d9a2f-103">When using server cursors, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver is optimized to not transmit the data for unbound **text**, **ntext**, or **image** columns at the time **SQLFetch** is performed.</span></span> <span data-ttu-id="d9a2f-104">Les données **Text**, **ntext**ou **image** ne sont pas réellement récupérées à partir du serveur tant que l’application n’émet pas [SQLGetData](../native-client-odbc-api/sqlgetdata.md) pour la colonne.</span><span class="sxs-lookup"><span data-stu-id="d9a2f-104">The **text**, **ntext**, or **image** data is not actually retrieved from the server until the application issues [SQLGetData](../native-client-odbc-api/sqlgetdata.md) for the column.</span></span>  
  
 <span data-ttu-id="d9a2f-105">De nombreuses applications peuvent être écrites de sorte qu’aucune donnée **Text**, **ntext**ou **image** ne soit affichée alors qu’un utilisateur fait simplement défiler la liste vers le haut et vers le haut dans un curseur.</span><span class="sxs-lookup"><span data-stu-id="d9a2f-105">Many applications can be written so that no **text**, **ntext**, or **image** data is displayed while a user is simply scrolling up and down in a cursor.</span></span> <span data-ttu-id="d9a2f-106">Lorsqu’un utilisateur sélectionne une ligne pour obtenir plus de détails, l’application peut ensuite appeler **SQLGetData** pour extraire les données **Text**, **ntext**ou **image** .</span><span class="sxs-lookup"><span data-stu-id="d9a2f-106">When a user selects a row to get more detail, the application can then call **SQLGetData** to retrieve the **text**, **ntext**, or **image** data.</span></span> <span data-ttu-id="d9a2f-107">Cela empêchera la transmission des données **Text**, **ntext**ou **image** pour les lignes que l’utilisateur ne sélectionne pas et peut donc empêcher la transmission de très grandes quantités de données.</span><span class="sxs-lookup"><span data-stu-id="d9a2f-107">This will prevent transmitting the **text**, **ntext**, or **image** data for any of the rows the user does not select, and can therefore prevent the transmission of very large amounts of data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9a2f-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d9a2f-108">See Also</span></span>  
 <span data-ttu-id="d9a2f-109">[Gestion des colonnes texte et image](managing-text-and-image-columns.md) </span><span class="sxs-lookup"><span data-stu-id="d9a2f-109">[Managing Text and Image Columns](managing-text-and-image-columns.md) </span></span>  
 [<span data-ttu-id="d9a2f-110">Comportements des curseurs</span><span class="sxs-lookup"><span data-stu-id="d9a2f-110">Cursor Behaviors</span></span>](../native-client-odbc-cursors/cursor-behaviors.md)  
  
  
