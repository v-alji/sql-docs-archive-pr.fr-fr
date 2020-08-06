---
title: Comment les curseurs sont implémentés | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC cursors, about ODBC cursors
- ODBC applications, cursors
- cursors [ODBC], about ODBC cursors
ms.assetid: 2b1d7dd4-08a4-43fc-b3eb-70c183d0941f
author: rothja
ms.author: jroth
ms.openlocfilehash: 18995355b825d9cb1e62b4794429b5e98ef2b472
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603524"
---
# <a name="how-cursors-are-implemented"></a><span data-ttu-id="bb24d-102">Comment les curseurs sont implémentés</span><span class="sxs-lookup"><span data-stu-id="bb24d-102">How Cursors Are Implemented</span></span>
  <span data-ttu-id="bb24d-103">Les applications ODBC contrôlent le comportement d'un curseur en définissant un ou plusieurs attributs d'instruction avant d'exécuter une instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="bb24d-103">ODBC applications control the behavior of a cursor by setting one or more statement attributes before executing an SQL statement.</span></span> <span data-ttu-id="bb24d-104">ODBC permet de spécifier les caractéristiques d'un curseur de deux façons différentes :</span><span class="sxs-lookup"><span data-stu-id="bb24d-104">ODBC has two different ways to specify the characteristics of a cursor:</span></span>  
  
-   <span data-ttu-id="bb24d-105">Type de curseur</span><span class="sxs-lookup"><span data-stu-id="bb24d-105">Cursor type</span></span>  
  
     <span data-ttu-id="bb24d-106">Les types de curseurs sont définis à l’aide de l’attribut SQL_ATTR_CURSOR_TYPE de [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="bb24d-106">Cursor types are set using the SQL_ATTR_CURSOR_TYPE attribute of [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span> <span data-ttu-id="bb24d-107">Les types de curseurs ODBC sont les suivants : avant uniquement, statiques, de jeu de clés, mixtes et dynamiques.</span><span class="sxs-lookup"><span data-stu-id="bb24d-107">The ODBC cursor types are forward-only, static, keyset-driven, mixed, and dynamic.</span></span> <span data-ttu-id="bb24d-108">La définition du type de curseur était la méthode employée à l'origine pour spécifier des curseurs dans ODBC.</span><span class="sxs-lookup"><span data-stu-id="bb24d-108">Setting the cursor type was the original method of specifying cursors in ODBC.</span></span>  
  
-   <span data-ttu-id="bb24d-109">Comportements des curseurs</span><span class="sxs-lookup"><span data-stu-id="bb24d-109">Cursor behavior</span></span>  
  
     <span data-ttu-id="bb24d-110">Le comportement de curseur est défini à l’aide des attributs SQL_ATTR_CURSOR_SCROLLABLE et SQL_ATTR_CURSOR_SENSITIVITY de **SQLSetStmtAttr**.</span><span class="sxs-lookup"><span data-stu-id="bb24d-110">Cursor behavior is set using the SQL_ATTR_CURSOR_SCROLLABLE and SQL_ATTR_CURSOR_SENSITIVITY attributes of **SQLSetStmtAttr**.</span></span> <span data-ttu-id="bb24d-111">Ces attributs sont modélisés sur les mots clés SCROLL et SENSITIVE définis pour l'instruction DECLARE CURSOR dans les normes ISO.</span><span class="sxs-lookup"><span data-stu-id="bb24d-111">These attributes are modeled on the SCROLL and SENSITIVE keywords defined for the DECLARE CURSOR statement in ISO standards.</span></span> <span data-ttu-id="bb24d-112">Ces deux options ISO ont été introduites dans version 3.0 d'ODBC.</span><span class="sxs-lookup"><span data-stu-id="bb24d-112">These two ISO options were introduced in ODBC version 3.0.</span></span>  
  
 <span data-ttu-id="bb24d-113">Les caractéristiques d'un curseur ODBC doivent être spécifiées à l'aide de l'une de ces deux méthodes, avec pour recommandation d'utiliser les types de curseurs ODBC.</span><span class="sxs-lookup"><span data-stu-id="bb24d-113">The characteristics of an ODBC cursor should be specified using either one or the other of these two methods, with the preference being to use the ODBC cursor types.</span></span>  
  
 <span data-ttu-id="bb24d-114">Outre la définition du type d'un curseur, les applications ODBC définissent également d'autres options, telles que le nombre de lignes retournées sur chaque extraction, les options de concurrence et les niveaux d'isolation de la transaction.</span><span class="sxs-lookup"><span data-stu-id="bb24d-114">In addition to setting the type of a cursor, ODBC applications also set other options, such as the number of rows returned on each fetch, concurrency options, and transaction isolation levels.</span></span> <span data-ttu-id="bb24d-115">Ces options peuvent être définies pour des curseurs de style ODBC (avant uniquement, statiques, de eu de clés, mixtes et dynamiques) ou des curseurs de style ISO (capacité de défilement et sensibilité).</span><span class="sxs-lookup"><span data-stu-id="bb24d-115">These options can be set for either ODBC-style cursors (forward-only, static, keyset-driven, mixed, and dynamic) or ISO style cursors (scrollability and sensitivity).</span></span>  
  
 <span data-ttu-id="bb24d-116">Le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pilote ODBC Native Client prend en charge plusieurs méthodes pour implémenter physiquement les différents types de curseurs.</span><span class="sxs-lookup"><span data-stu-id="bb24d-116">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports several ways to physically implement the various types of cursors.</span></span> <span data-ttu-id="bb24d-117">Le pilote implémente certains types de curseurs à l'aide d'un jeu de résultats par défaut [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], et d'autres en tant que curseurs côté serveur ou à l'aide de la bibliothèque de curseurs ODBC.</span><span class="sxs-lookup"><span data-stu-id="bb24d-117">The driver implements some types of cursors using a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default result set; it implements others as server cursors or by using the ODBC Cursor Library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb24d-118">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="bb24d-118">In This Section</span></span>  
  
-   [<span data-ttu-id="bb24d-119">Utilisation de jeux de résultats SQL Server par défaut</span><span class="sxs-lookup"><span data-stu-id="bb24d-119">Using SQL Server Default Result Sets</span></span>](using-sql-server-default-result-sets.md)  
  
-   [<span data-ttu-id="bb24d-120">Utilisation des curseurs côté serveur</span><span class="sxs-lookup"><span data-stu-id="bb24d-120">Using Server Cursors</span></span>](using-server-cursors.md)  
  
-   [<span data-ttu-id="bb24d-121">Bibliothèque de curseurs ODBC</span><span class="sxs-lookup"><span data-stu-id="bb24d-121">ODBC Cursor Library</span></span>](odbc-cursor-library.md)  
  
## <a name="see-also"></a><span data-ttu-id="bb24d-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bb24d-122">See Also</span></span>  
 [<span data-ttu-id="bb24d-123">Utilisation de curseurs &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="bb24d-123">Using Cursors &#40;ODBC&#41;</span></span>](../using-cursors-odbc.md)  
  
  
