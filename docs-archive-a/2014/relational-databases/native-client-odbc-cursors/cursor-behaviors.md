---
title: Comportements des curseurs | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- scrollable cursors [SQL Server]
- SQL Server Native Client ODBC driver, cursors
- version-based optimistic concurrency
- cursors [ODBC], cursor behaviors
- ODBC applications, cursors
- SQL_ATTR_CURSOR_SENSITIVITY option
- SQL_ATTR_CURSOR_SCROLLABLE option
- sensitivity behavior of cursor
- ODBC cursors, cursor behaviors
ms.assetid: 742ddcd2-232b-4aa1-9212-027df120ad35
author: rothja
ms.author: jroth
ms.openlocfilehash: 89c7c4e9a8dcffe03dd12f8013d5ed43810547f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605391"
---
# <a name="cursor-behaviors"></a><span data-ttu-id="fcbe8-102">Comportements des curseurs</span><span class="sxs-lookup"><span data-stu-id="fcbe8-102">Cursor Behaviors</span></span>
  <span data-ttu-id="fcbe8-103">ODBC prend en charge les options ISO pour spécifier le comportement des curseurs en termes de capacité de défilement et de sensibilité.</span><span class="sxs-lookup"><span data-stu-id="fcbe8-103">ODBC supports the ISO options for specifying the behavior of cursors by specifying their scrollability and sensitivity.</span></span> <span data-ttu-id="fcbe8-104">Ces comportements sont spécifiés en définissant les options SQL_ATTR_CURSOR_SCROLLABLE et SQL_ATTR_CURSOR_SENSITIVITY sur un appel à [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="fcbe8-104">These behaviors are specified by setting the SQL_ATTR_CURSOR_SCROLLABLE and SQL_ATTR_CURSOR_SENSITIVITY options on a call to [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md).</span></span> <span data-ttu-id="fcbe8-105">Le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client implémente ces options en demandant des curseurs côté serveur avec les caractéristiques suivantes.</span><span class="sxs-lookup"><span data-stu-id="fcbe8-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver implements these options by requesting server cursors with the following characteristics.</span></span>  
  
|<span data-ttu-id="fcbe8-106">Paramètres de comportement du curseur</span><span class="sxs-lookup"><span data-stu-id="fcbe8-106">Cursor behavior settings</span></span>|<span data-ttu-id="fcbe8-107">Caractéristiques du curseur côté serveur demandées</span><span class="sxs-lookup"><span data-stu-id="fcbe8-107">Server cursor characteristics requested</span></span>|  
|------------------------------|---------------------------------------------|  
|<span data-ttu-id="fcbe8-108">SQL_SCROLLABLE et SQL_SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="fcbe8-108">SQL_SCROLLABLE and SQL_SENSITIVE</span></span>|<span data-ttu-id="fcbe8-109">Curseur de jeu de clés et accès concurrentiel optimiste basé sur la version</span><span class="sxs-lookup"><span data-stu-id="fcbe8-109">Keyset-driven cursor and version-based optimistic concurrency</span></span>|  
|<span data-ttu-id="fcbe8-110">SQL_SCROLLABLE et SQL_INSENSITIVE</span><span class="sxs-lookup"><span data-stu-id="fcbe8-110">SQL_SCROLLABLE and SQL_INSENSITIVE</span></span>|<span data-ttu-id="fcbe8-111">Curseur statique et concurrence en lecture seule</span><span class="sxs-lookup"><span data-stu-id="fcbe8-111">Static cursor and read-only concurrency</span></span>|  
|<span data-ttu-id="fcbe8-112">SQL_SCROLLABLE et SQL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="fcbe8-112">SQL_SCROLLABLE and SQL_UNSPECIFIED</span></span>|<span data-ttu-id="fcbe8-113">Curseur statique et concurrence en lecture seule</span><span class="sxs-lookup"><span data-stu-id="fcbe8-113">Static cursor and read-only concurrency</span></span>|  
|<span data-ttu-id="fcbe8-114">SQL_NONSCROLLABLE et SQL_SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="fcbe8-114">SQL_NONSCROLLABLE and SQL_SENSITIVE</span></span>|<span data-ttu-id="fcbe8-115">Curseur avant uniquement et accès concurrentiel optimiste basé sur la version</span><span class="sxs-lookup"><span data-stu-id="fcbe8-115">Forward-only cursor and version-based optimistic concurrency</span></span>|  
|<span data-ttu-id="fcbe8-116">SQL_NONSCROLLABLE et SQL_INSENSITIVE</span><span class="sxs-lookup"><span data-stu-id="fcbe8-116">SQL_NONSCROLLABLE and SQL_INSENSITIVE</span></span>|<span data-ttu-id="fcbe8-117">Jeu de résultats par défaut (avant uniquement, en lecture seule)</span><span class="sxs-lookup"><span data-stu-id="fcbe8-117">Default result set (forward-only, read-only)</span></span>|  
|<span data-ttu-id="fcbe8-118">SQL_NONSCROLLABLE et SQL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="fcbe8-118">SQL_NONSCROLLABLE and SQL_UNSPECIFIED</span></span>|<span data-ttu-id="fcbe8-119">Jeu de résultats par défaut (avant uniquement, en lecture seule)</span><span class="sxs-lookup"><span data-stu-id="fcbe8-119">Default result set (forward-only, read-only)</span></span>|  
  
 <span data-ttu-id="fcbe8-120">L’accès concurrentiel optimiste basé sur la version nécessite une colonne **timestamp** dans la table sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="fcbe8-120">Version-based optimistic concurrency requires a **timestamp** column in the underlying table.</span></span> <span data-ttu-id="fcbe8-121">Si le contrôle d’accès concurrentiel optimiste basé sur la version est demandé sur une table qui n’a pas de colonne **timestamp** , le serveur utilise l’accès concurrentiel optimiste basé sur les valeurs.</span><span class="sxs-lookup"><span data-stu-id="fcbe8-121">If version-based optimistic concurrency control is requested on a table that does not have a **timestamp** column, the server uses values-based optimistic concurrency.</span></span>  
  
## <a name="scrollability"></a><span data-ttu-id="fcbe8-122">Capacité de défilement</span><span class="sxs-lookup"><span data-stu-id="fcbe8-122">Scrollability</span></span>  
 <span data-ttu-id="fcbe8-123">Lorsque SQL_ATTR_CURSOR_SCROLLABLE a la valeur SQL_SCROLLABLE, le curseur prend en charge toutes les valeurs différentes pour le paramètre *FetchOrientation* de [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span><span class="sxs-lookup"><span data-stu-id="fcbe8-123">When SQL_ATTR_CURSOR_SCROLLABLE is set to SQL_SCROLLABLE, the cursor supports all the different values for the *FetchOrientation* parameter of [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span></span> <span data-ttu-id="fcbe8-124">Lorsque SQL_ATTR_CURSOR_SCROLLABLE est défini sur SQL_NONSCROLLABLE, le curseur prend en charge uniquement la valeur *FetchOrientation* de SQL_FETCH_NEXT.</span><span class="sxs-lookup"><span data-stu-id="fcbe8-124">When SQL_ATTR_CURSOR_SCROLLABLE is set to SQL_NONSCROLLABLE, the cursor only supports a *FetchOrientation* value of SQL_FETCH_NEXT.</span></span>  
  
## <a name="sensitivity"></a><span data-ttu-id="fcbe8-125">Sensibilité</span><span class="sxs-lookup"><span data-stu-id="fcbe8-125">Sensitivity</span></span>  
 <span data-ttu-id="fcbe8-126">Quand SQL_ATTR_CURSOR_SENSITIVITY est défini avec la valeur SQL_SENSITIVE, le curseur reflète les modifications des données effectuées par l'utilisateur en cours ou validées par d'autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fcbe8-126">When SQL_ATTR_CURSOR_SENSITIVITY is set to SQL_SENSITIVE, the cursor reflects data modifications made by the current user or committed by other users.</span></span> <span data-ttu-id="fcbe8-127">Quand SQL_ATTR_CURSOR_SENSITIVITY est défini avec la valeur SQL_INSENSITIVE, le curseur ne reflète pas les modifications des données.</span><span class="sxs-lookup"><span data-stu-id="fcbe8-127">When SQL_ATTR_CURSOR_SENSITIVITY is set to SQL_INSENSITIVE, the cursor does not reflect data modifications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcbe8-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fcbe8-128">See Also</span></span>  
 [<span data-ttu-id="fcbe8-129">Utilisation de curseurs &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="fcbe8-129">Using Cursors &#40;ODBC&#41;</span></span>](using-cursors-odbc.md)  
  
  
