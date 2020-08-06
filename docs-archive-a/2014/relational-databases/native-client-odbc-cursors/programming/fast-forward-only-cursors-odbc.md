---
title: Curseurs avant uniquement rapides (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- fast forward-only cursors
- forward-only cursors
- cursors [ODBC], fast forward-only
- ODBC cursors, fast forward-only
ms.assetid: 0707d07e-fc95-42ed-9280-b7e508ac8c62
author: rothja
ms.author: jroth
ms.openlocfilehash: de8d82a0c72ad51741a3785fba2910f691028cba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612302"
---
# <a name="fast-forward-only-cursors-odbc"></a><span data-ttu-id="856da-102">Curseurs avant uniquement rapides (ODBC)</span><span class="sxs-lookup"><span data-stu-id="856da-102">Fast Forward-Only Cursors (ODBC)</span></span>
  <span data-ttu-id="856da-103">En cas de connexion à une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pilote ODBC Native Client prend en charge les optimisations de performances pour les curseurs avant uniquement et en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="856da-103">When connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports performance optimizations for forward-only, read-only cursors.</span></span> <span data-ttu-id="856da-104">Les curseurs avant uniquement rapides sont implémentés en interne par le pilote et le serveur d'une manière très semblable aux jeux de résultats par défaut.</span><span class="sxs-lookup"><span data-stu-id="856da-104">Fast forward-only cursors are implemented internally by the driver and server in a manner very similar to default result sets.</span></span> <span data-ttu-id="856da-105">Les curseurs avant uniquement rapides présentent d'autres caractéristiques, au-delà de leurs performances élevées :</span><span class="sxs-lookup"><span data-stu-id="856da-105">Besides having high performance, fast forward-only cursors also have these characteristics:</span></span>  
  
-   <span data-ttu-id="856da-106">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="856da-106">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) is not supported.</span></span> <span data-ttu-id="856da-107">Les colonnes de jeu de résultats doivent être liées à des variables de programme.</span><span class="sxs-lookup"><span data-stu-id="856da-107">The result set columns must be bound to program variables.</span></span>  
  
-   <span data-ttu-id="856da-108">Le serveur ferme automatiquement le curseur lorsque la fin de celui-ci est détectée.</span><span class="sxs-lookup"><span data-stu-id="856da-108">The server automatically closes the cursor when the end of the cursor is detected.</span></span> <span data-ttu-id="856da-109">L’application doit toujours appeler [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) ou [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md)(SQL_CLOSE), mais le pilote n’a pas besoin d’envoyer la demande de fermeture au serveur.</span><span class="sxs-lookup"><span data-stu-id="856da-109">The application must still call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) or [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md)(SQL_CLOSE), but the driver does not have to send the close request to the server.</span></span> <span data-ttu-id="856da-110">Cela permet d'économiser un aller-retour au serveur par le biais du réseau.</span><span class="sxs-lookup"><span data-stu-id="856da-110">This saves a roundtrip across the network to the server.</span></span>  
  
 <span data-ttu-id="856da-111">L'application demande des curseurs avant uniquement rapides à l'aide de l'attribut d'instruction SQL_SOPT_SS_CURSOR_OPTIONS spécifique au pilote.</span><span class="sxs-lookup"><span data-stu-id="856da-111">The application requests fast forward-only cursors using the driver-specific statement attribute SQL_SOPT_SS_CURSOR_OPTIONS.</span></span> <span data-ttu-id="856da-112">Lorsqu'ils sont définis avec la valeur SQL_CO_FFO, les curseurs avant uniquement rapides sont activés sans auto-extraction.</span><span class="sxs-lookup"><span data-stu-id="856da-112">When set to SQL_CO_FFO, fast forward-only cursors are enabled without autofetch.</span></span> <span data-ttu-id="856da-113">Lorsqu'ils sont définis sur SQL_CO_FFO_AF, l'option d'auto-extraction est également activée.</span><span class="sxs-lookup"><span data-stu-id="856da-113">When set to SQL_CO_FFO_AF, the autofetch option is also enabled.</span></span> <span data-ttu-id="856da-114">Pour plus d’informations sur l’auto-extraction, consultez [utilisation de l’auto-extraction avec les curseurs ODBC](using-autofetch-with-odbc-cursors.md).</span><span class="sxs-lookup"><span data-stu-id="856da-114">For more information about autofetch, see [Using Autofetch with ODBC Cursors](using-autofetch-with-odbc-cursors.md).</span></span>  
  
 <span data-ttu-id="856da-115">Les curseurs avant uniquement rapides avec auto-extraction peuvent être utilisés pour extraire un petit jeu de résultats avec un seul aller-retour au serveur.</span><span class="sxs-lookup"><span data-stu-id="856da-115">Fast forward-only cursors with autofetch can be used to retrieve a small result set with only one roundtrip to the server.</span></span> <span data-ttu-id="856da-116">Dans ces étapes, *n* est le nombre de lignes à retourner :</span><span class="sxs-lookup"><span data-stu-id="856da-116">In these steps, *n* is the number of rows to be returned:</span></span>  
  
1.  <span data-ttu-id="856da-117">Affectez la valeur SQL_CO_FFO_AF à SQL_SOPT_SS_CURSOR_OPTIONS.</span><span class="sxs-lookup"><span data-stu-id="856da-117">Set SQL_SOPT_SS_CURSOR_OPTIONS to SQL_CO_FFO_AF.</span></span>  
  
2.  <span data-ttu-id="856da-118">Affectez à SQL_ATTR_ROW_ARRAY_SIZE la valeur *n* + 1.</span><span class="sxs-lookup"><span data-stu-id="856da-118">Set SQL_ATTR_ROW_ARRAY_SIZE to *n* + 1.</span></span>  
  
3.  <span data-ttu-id="856da-119">Liez les colonnes de résultats à des tableaux de *n* + 1 éléments (pour être sécurisé, si *n* + 1 lignes sont réellement extraites).</span><span class="sxs-lookup"><span data-stu-id="856da-119">Bind the result columns to arrays of *n* + 1 elements (to be safe if *n* + 1 rows are actually fetched).</span></span>  
  
4.  <span data-ttu-id="856da-120">Ouvrez le curseur avec **SQLExecDirect** ou **SQLExecute**.</span><span class="sxs-lookup"><span data-stu-id="856da-120">Open the cursor with either **SQLExecDirect** or **SQLExecute**.</span></span>  
  
5.  <span data-ttu-id="856da-121">Si l’état de retour est SQL_SUCCESS, appelez **SQLFreeStmt** ou **SQLCloseCursor** pour fermer le curseur.</span><span class="sxs-lookup"><span data-stu-id="856da-121">If the return status is SQL_SUCCESS, then call **SQLFreeStmt** or **SQLCloseCursor** to close the cursor.</span></span> <span data-ttu-id="856da-122">Toutes les données des lignes seront dans les variables de programme liées.</span><span class="sxs-lookup"><span data-stu-id="856da-122">All data for the rows will be in the bound program variables.</span></span>  
  
 <span data-ttu-id="856da-123">Avec ces étapes, **SQLExecDirect** ou **SQLExecute** envoie une demande d’ouverture de curseur avec l’option d’auto-extraction activée.</span><span class="sxs-lookup"><span data-stu-id="856da-123">With these steps, the **SQLExecDirect** or **SQLExecute** sends a cursor open request with the autofetch option enabled.</span></span> <span data-ttu-id="856da-124">Lors de cette demande unique de la part du client, le serveur :</span><span class="sxs-lookup"><span data-stu-id="856da-124">On that single request from the client, the server:</span></span>  
  
-   <span data-ttu-id="856da-125">ouvre le curseur ;</span><span class="sxs-lookup"><span data-stu-id="856da-125">Opens the cursor.</span></span>  
  
-   <span data-ttu-id="856da-126">génère le jeu de résultats et envoie les lignes au client ;</span><span class="sxs-lookup"><span data-stu-id="856da-126">Builds the result set and sends the rows to the client.</span></span>  
  
-   <span data-ttu-id="856da-127">détecte la fin du curseur et le ferme, la taille de l'ensemble de lignes ayant été définie avec une unité de plus que le nombre de lignes dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="856da-127">Because the rowset size was set to 1 more than the number of rows in the result set, the server detects the end of the cursor and closes the cursor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="856da-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="856da-128">See Also</span></span>  
 [<span data-ttu-id="856da-129">Détails de programmation de curseur &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="856da-129">Cursor Programming Details &#40;ODBC&#41;</span></span>](cursor-programming-details-odbc.md)  
  
  
