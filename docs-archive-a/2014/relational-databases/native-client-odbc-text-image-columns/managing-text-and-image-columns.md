---
title: Gestion des colonnes text et image | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- text columns [ODBC]
- SQL Server Native Client ODBC driver, image columns
- SQL Server Native Client ODBC driver, text columns
- data types [ODBC], text
- columns [ODBC]
- ODBC data types, image columns
- data types [ODBC], mapping
- ODBC data types, text columns
- image columns [ODBC]
ms.assetid: 7b543556-ff36-4d35-ac08-de96223d92cd
author: rothja
ms.author: jroth
ms.openlocfilehash: e9d7d5b0f48c68e8ac911f5e274c9afdb8cfe17d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709295"
---
# <a name="managing-text-and-image-columns"></a><span data-ttu-id="61b4d-102">Gestion des colonnes text et image</span><span class="sxs-lookup"><span data-stu-id="61b4d-102">Managing Text and Image Columns</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="61b4d-103">les données **Text**, **ntext**et **image** (également appelées données de type long) sont des types de données de chaîne de caractères ou binaires qui peuvent contenir des valeurs de données trop grandes pour tenir dans des colonnes **char**, **varchar**, **Binary**ou **varbinary** .</span><span class="sxs-lookup"><span data-stu-id="61b4d-103">**text**, **ntext**, and **image** data (also referred to as long data) are character or binary string data types that can hold data values too large to fit into **char**, **varchar**, **binary**, or **varbinary** columns.</span></span> <span data-ttu-id="61b4d-104">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type de données **Text** est mappé sur le type de données SQL_LONGVARCHAR ODBC ; **ntext** est mappé à SQL_WLONGVARCHAR ; et **images** est mappé à SQL_LONGVARBINARY.</span><span class="sxs-lookup"><span data-stu-id="61b4d-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **text** data type maps to the ODBC SQL_LONGVARCHAR data type; **ntext** maps to SQL_WLONGVARCHAR; and **image** maps to SQL_LONGVARBINARY.</span></span> <span data-ttu-id="61b4d-105">Certains éléments de données, tels que les longs documents ou les images bitmaps volumineuses, peuvent être trop grands pour pouvoir être stockés raisonnablement en mémoire.</span><span class="sxs-lookup"><span data-stu-id="61b4d-105">Some data items, such as long documents or large bitmaps, may be too large to store reasonably in memory.</span></span> <span data-ttu-id="61b4d-106">Pour récupérer des données de type long [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans des parties séquentielles, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client permet à une application d’appeler [SQLGetData](../native-client-odbc-api/sqlgetdata.md).</span><span class="sxs-lookup"><span data-stu-id="61b4d-106">To retrieve long data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in sequential parts, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver enables an application to call [SQLGetData](../native-client-odbc-api/sqlgetdata.md).</span></span> <span data-ttu-id="61b4d-107">Pour envoyer des données de type long dans des parties séquentielles, l’application peut appeler [SQLPutData](../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="61b4d-107">To send long data in sequential parts, the application can call [SQLPutData](../native-client-odbc-api/sqlputdata.md).</span></span> <span data-ttu-id="61b4d-108">Les paramètres pour lesquels les données sont envoyées au moment de l'exécution sont connus comme paramètres de données en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="61b4d-108">Parameters for which data is sent at execution time are known as data-at-execution parameters.</span></span>  
  
 <span data-ttu-id="61b4d-109">Une application peut en fait écrire ou récupérer n’importe quel type de données (pas seulement des données longues) avec **SQLPutData** ou **SQLGetData**, bien que seules les données de type **caractère** et **binaire** puissent être envoyées ou récupérées dans des parties.</span><span class="sxs-lookup"><span data-stu-id="61b4d-109">An application can actually write or retrieve any type of data (not just long data) with **SQLPutData** or **SQLGetData**, although only **character** and **binary** data can be sent or retrieved in parts.</span></span> <span data-ttu-id="61b4d-110">Toutefois, si les données sont suffisamment petites pour tenir dans une seule mémoire tampon, il n’y a généralement aucune raison d’utiliser **SQLPutData** ou **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="61b4d-110">However, if the data is small enough to fit in a single buffer, there is generally no reason to use **SQLPutData** or **SQLGetData**.</span></span> <span data-ttu-id="61b4d-111">Il est beaucoup plus facile de lier la mémoire tampon unique au paramètre ou à la colonne.</span><span class="sxs-lookup"><span data-stu-id="61b4d-111">It is much easier to bind the single buffer to the parameter or column.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="61b4d-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="61b4d-112">In This Section</span></span>  
  
-   [<span data-ttu-id="61b4d-113">Colonnes de texte et d'image liées et non liées</span><span class="sxs-lookup"><span data-stu-id="61b4d-113">Bound vs. Unbound Text and Image Columns</span></span>](bound-vs-unbound-text-and-image-columns.md)  
  
-   [<span data-ttu-id="61b4d-114">Modifications enregistrées ou non enregistrées</span><span class="sxs-lookup"><span data-stu-id="61b4d-114">Logged vs. Unlogged Modifications</span></span>](logged-vs-unlogged-modifications.md)  
  
-   [<span data-ttu-id="61b4d-115">Colonnes text, ntext ou image de données en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="61b4d-115">Data-at-Execution and Text, ntext, or Image Columns</span></span>](data-at-execution-and-text-ntext-or-image-columns.md)  
  
## <a name="see-also"></a><span data-ttu-id="61b4d-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="61b4d-116">See Also</span></span>  
 [<span data-ttu-id="61b4d-117">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="61b4d-117">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
