---
title: SQLSpecialColumns | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLSpecialColumns function
ms.assetid: dffe02ed-8f79-4c9a-af34-98130bbe5462
author: rothja
ms.author: jroth
ms.openlocfilehash: c36ff73606e95ed7ee5e713b81acf7c177a42563
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605408"
---
# <a name="sqlspecialcolumns"></a><span data-ttu-id="c5e29-102">SQLSpecialColumns</span><span class="sxs-lookup"><span data-stu-id="c5e29-102">SQLSpecialColumns</span></span>
  <span data-ttu-id="c5e29-103">Lors de la demande d’identificateurs de ligne (*IdentifierType* SQL_BEST_ROWID), **SQLSpecialColumns** retourne un jeu de résultats vide (aucune ligne de données) pour toute étendue demandée autre que SQL_SCOPE_CURROW.</span><span class="sxs-lookup"><span data-stu-id="c5e29-103">When requesting row identifiers (*IdentifierType* SQL_BEST_ROWID), **SQLSpecialColumns** returns an empty result set (no data rows) for any requested scope other than SQL_SCOPE_CURROW.</span></span> <span data-ttu-id="c5e29-104">Le jeu de résultats généré indique que les colonnes ne sont valides que dans cette étendue.</span><span class="sxs-lookup"><span data-stu-id="c5e29-104">The generated result set indicates that the columns are only valid within this scope.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c5e29-105">ne prend pas en charge les pseudo-colonnes pour les identificateurs.</span><span class="sxs-lookup"><span data-stu-id="c5e29-105">does not support pseudocolumns for identifiers.</span></span> <span data-ttu-id="c5e29-106">Le jeu de résultats **SQLSpecialColumns** identifie toutes les colonnes comme SQL_PC_NOT_PSEUDO.</span><span class="sxs-lookup"><span data-stu-id="c5e29-106">The **SQLSpecialColumns** result set will identify all columns as SQL_PC_NOT_PSEUDO.</span></span>  
  
 <span data-ttu-id="c5e29-107">**SQLSpecialColumns** peut être exécuté sur un curseur statique.</span><span class="sxs-lookup"><span data-stu-id="c5e29-107">**SQLSpecialColumns** can be executed on a static cursor.</span></span> <span data-ttu-id="c5e29-108">Une tentative d’exécution de **SQLSpecialColumns** sur un qui peut être mis à jour (KEYSET ou Dynamic) retourne SQL_SUCCESS_WITH_INFO indiquant que le type de curseur a été modifié.</span><span class="sxs-lookup"><span data-stu-id="c5e29-108">An attempt to execute **SQLSpecialColumns** on an updatable (keyset-driven or dynamic) returns SQL_SUCCESS_WITH_INFO indicating the cursor type has been changed.</span></span>  
  
## <a name="sqlspecialcolumns-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="c5e29-109">Prise en charge par SQLSpecialColumns des fonctionnalités de date et heure améliorées</span><span class="sxs-lookup"><span data-stu-id="c5e29-109">SQLSpecialColumns Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="c5e29-110">Pour plus d’informations sur les valeurs retournées pour les colonnes DATA_TYPE, TYPE_NAME, COLUMN_SIZE, BUFFER_LENGTH et DECIMAL_DIGTS pour les types date/heure, consultez [métadonnées de catalogue](../native-client-odbc-date-time/metadata-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="c5e29-110">For information about the values returned for the columns DATA_TYPE, TYPE_NAME, COLUMN_SIZE, BUFFER_LENGTH, and DECIMAL_DIGTS for date/time types, see [Catalog Metadata](../native-client-odbc-date-time/metadata-catalog.md).</span></span>  
  
 <span data-ttu-id="c5e29-111">Pour plus d’informations générales, consultez améliorations de la [date et de l’heure &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="c5e29-111">For more general information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlspecialcolumns-support-for-large-clr-udts"></a><span data-ttu-id="c5e29-112">Prise en charge par SQLSpecialColumns des grands types CLR définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="c5e29-112">SQLSpecialColumns Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="c5e29-113">**SQLSpecialColumns** prend en charge les types CLR volumineux définis par l’utilisateur (UDT).</span><span class="sxs-lookup"><span data-stu-id="c5e29-113">**SQLSpecialColumns** supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="c5e29-114">Pour plus d’informations, consultez [types CLR volumineux définis par l’utilisateur &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="c5e29-114">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5e29-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c5e29-115">See Also</span></span>  
 <span data-ttu-id="c5e29-116">[SQLSpecialColumns fonction)](https://go.microsoft.com/fwlink/?LinkId=59371) </span><span class="sxs-lookup"><span data-stu-id="c5e29-116">[SQLSpecialColumns Function](https://go.microsoft.com/fwlink/?LinkId=59371) </span></span>  
 [<span data-ttu-id="c5e29-117">Détails de l’implémentation d’API ODBC</span><span class="sxs-lookup"><span data-stu-id="c5e29-117">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
