---
title: Extraire et mettre à jour des ensembles de lignes (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- rowsets [ODBC]
ms.assetid: cf0eb3b4-8b72-49fc-a845-95edc360cf93
author: rothja
ms.author: jroth
ms.openlocfilehash: e09a3033e0883452ecd69b82c9375ed28c920da0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599981"
---
# <a name="fetch-and-update-rowsets-odbc"></a><span data-ttu-id="837dc-102">Extraire et mettre à jour des ensembles de lignes (ODBC)</span><span class="sxs-lookup"><span data-stu-id="837dc-102">Fetch and Update Rowsets (ODBC)</span></span>
    
### <a name="to-fetch-and-update-rowsets"></a><span data-ttu-id="837dc-103">Extraire et mettre à jour des ensembles de lignes</span><span class="sxs-lookup"><span data-stu-id="837dc-103">To fetch and update rowsets</span></span>  
  
1.  <span data-ttu-id="837dc-104">Si vous le souhaitez, appelez [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) avec SQL_ROW_ARRAY_SIZE pour modifier le nombre de lignes (R) dans l’ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="837dc-104">Optionally, call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) with SQL_ROW_ARRAY_SIZE to change the number of rows (R) in the rowset.</span></span>  
  
2.  <span data-ttu-id="837dc-105">Appelez [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) ou [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) pour obtenir un ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="837dc-105">Call [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) to get a rowset.</span></span>  
  
3.  <span data-ttu-id="837dc-106">Si des colonnes dépendantes sont utilisées, utilisez les valeurs de données et les longueurs de données à présent disponibles dans les tampons de colonnes dépendantes pour l'ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="837dc-106">If bound columns are used, use the data values and data lengths now available in the bound column buffers for the rowset.</span></span>  
  
     <span data-ttu-id="837dc-107">Si des colonnes indépendantes sont utilisées, pour chaque ligne, appelez [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) avec SQL_POSITION pour définir la position du curseur ; ensuite, pour chaque colonne indépendante :</span><span class="sxs-lookup"><span data-stu-id="837dc-107">If unbound columns are used, for each row call [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) with SQL_POSITION to set the cursor position; then, for each unbound column:</span></span>  
  
    -   <span data-ttu-id="837dc-108">Appelez [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) une ou plusieurs fois pour obtenir les données pour les colonnes indépendantes après la dernière colonne dépendante de l'ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="837dc-108">Call [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) one or more times to get the data for unbound columns after the last bound column of the rowset.</span></span> <span data-ttu-id="837dc-109">Les appels à [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) doivent être dans l'ordre croissant des numéros de colonnes.</span><span class="sxs-lookup"><span data-stu-id="837dc-109">Calls to [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) should be in order of increasing column number.</span></span>  
  
    -   <span data-ttu-id="837dc-110">Appelez plusieurs fois [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) pour obtenir des données à partir d'une colonne text ou image.</span><span class="sxs-lookup"><span data-stu-id="837dc-110">Call [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) multiple times to get data from a text or image column.</span></span>  
  
4.  <span data-ttu-id="837dc-111">Configurez toutes les colonnes image ou text de données en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="837dc-111">Set up any data-at-execution text or image columns.</span></span>  
  
5.  <span data-ttu-id="837dc-112">Appelez [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) ou [SQLBulkOperations](https://go.microsoft.com/fwlink/?LinkId=58398) pour définir la position du curseur, actualiser, mettre à jour, supprimer ou ajouter une ou des lignes dans l'ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="837dc-112">Call [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) or [SQLBulkOperations](https://go.microsoft.com/fwlink/?LinkId=58398) to set the cursor position, refresh, update, delete, or add row(s) within the rowset.</span></span>  
  
     <span data-ttu-id="837dc-113">Si des colonnes image ou text de données en cours d'exécution sont utilisées pour une opération de mise à jour ou d'ajout, gérez-les.</span><span class="sxs-lookup"><span data-stu-id="837dc-113">If data-at-execution text or image columns are used for an update or add operation, handle them.</span></span>  
  
6.  <span data-ttu-id="837dc-114">Vous pouvez éventuellement exécuter une instruction UPDATE ou DELETE positionnée, en spécifiant le nom de curseur (disponible à partir de [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md)) et en utilisant un descripteur d'instruction différent sur la même connexion.</span><span class="sxs-lookup"><span data-stu-id="837dc-114">Optionally, execute a positioned UPDATE or DELETE statement, specifying the cursor name (available from [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md)) and using a different statement handle on the same connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="837dc-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="837dc-115">See Also</span></span>  
 [<span data-ttu-id="837dc-116">Rubriques de procédures relatives à l’utilisation des curseurs &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="837dc-116">Using Cursors How-to Topics &#40;ODBC&#41;</span></span>](using-cursors-how-to-topics-odbc.md)  
  
  
