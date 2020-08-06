---
title: Définir les options de curseur (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], options
ms.assetid: 0e72b48a-fc5a-4656-8cf5-39f57d8c1565
author: rothja
ms.author: jroth
ms.openlocfilehash: 877c2596c87ce50295a15912493661c6dd4e0305
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707487"
---
# <a name="set-cursor-options-odbc"></a><span data-ttu-id="2c05e-102">Définir des options de curseur (ODBC)</span><span class="sxs-lookup"><span data-stu-id="2c05e-102">Set Cursor Options (ODBC)</span></span>
  <span data-ttu-id="2c05e-103">Pour définir des options de curseur, appelez [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) pour définir ou [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md) afin d’afficher les options d’instruction qui contrôlent le comportement du curseur.</span><span class="sxs-lookup"><span data-stu-id="2c05e-103">To set cursor options, Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set or [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md) to get the statement options that control cursor behavior.</span></span>  
  
|<span data-ttu-id="2c05e-104">*Attribut*</span><span class="sxs-lookup"><span data-stu-id="2c05e-104">*Attribute*</span></span>|<span data-ttu-id="2c05e-105">Spécifie</span><span class="sxs-lookup"><span data-stu-id="2c05e-105">Specifies</span></span>|  
|-----------------|---------------|  
|<span data-ttu-id="2c05e-106">SQL_ATTR_CURSOR_TYPE</span><span class="sxs-lookup"><span data-stu-id="2c05e-106">SQL_ATTR_CURSOR_TYPE</span></span>|<span data-ttu-id="2c05e-107">Type de curseur avant uniquement, statique, dynamique ou de jeu de clés</span><span class="sxs-lookup"><span data-stu-id="2c05e-107">Cursor type of forward-only, static, dynamic, or keyset-driven</span></span>|  
|<span data-ttu-id="2c05e-108">SQL_ATTR_CONCURRENCY</span><span class="sxs-lookup"><span data-stu-id="2c05e-108">SQL_ATTR_CONCURRENCY</span></span>|<span data-ttu-id="2c05e-109">Option de contrôle concurrentiel de lecture seule, verrouillage, optimiste avec horodateurs ou optimiste avec valeurs</span><span class="sxs-lookup"><span data-stu-id="2c05e-109">Concurrency control option of read-only, locking, optimistic using timestamps, or optimistic using values</span></span>|  
|<span data-ttu-id="2c05e-110">SQL_ATTR_ROW_ARRAY_SIZE</span><span class="sxs-lookup"><span data-stu-id="2c05e-110">SQL_ATTR_ROW_ARRAY_SIZE</span></span>|<span data-ttu-id="2c05e-111">Nombre de lignes extraites à chaque extraction</span><span class="sxs-lookup"><span data-stu-id="2c05e-111">Number of rows retrieved in each fetch</span></span>|  
|<span data-ttu-id="2c05e-112">SQL_ATTR_CURSOR_SENSITIVITY</span><span class="sxs-lookup"><span data-stu-id="2c05e-112">SQL_ATTR_CURSOR_SENSITIVITY</span></span>|<span data-ttu-id="2c05e-113">Curseur qui affiche ou masque les mises à jour des lignes de curseur effectuées par d'autres connexions</span><span class="sxs-lookup"><span data-stu-id="2c05e-113">Cursor that does or does not show updates to cursor rows made by other connections</span></span>|  
|<span data-ttu-id="2c05e-114">SQL_ATTR_CURSOR_SCROLLABLE</span><span class="sxs-lookup"><span data-stu-id="2c05e-114">SQL_ATTR_CURSOR_SCROLLABLE</span></span>|<span data-ttu-id="2c05e-115">Curseur qu'il est possible de faire défiler vers l'avant et vers l'arrière</span><span class="sxs-lookup"><span data-stu-id="2c05e-115">Cursor that can be scrolled forward and backward</span></span>|  
  
 <span data-ttu-id="2c05e-116">Les valeurs par défaut de ces attributs (avant uniquement, lecture seule, taille d'ensemble de lignes de 1) n'utilisent pas de curseurs côté serveur.</span><span class="sxs-lookup"><span data-stu-id="2c05e-116">The default values for these attributes (forward-only, read-only, rowset size of 1) do not use server cursors.</span></span> <span data-ttu-id="2c05e-117">Pour utiliser des curseurs côté serveur, au moins l'un de ces attributs doit être défini à une valeur autre que la valeur par défaut et l'instruction qui est exécutée doit être une instruction SELECT unique ou une procédure stockée qui contient une instruction SELECT unique.</span><span class="sxs-lookup"><span data-stu-id="2c05e-117">To use server cursors, at least one of these attributes must be set to a value other than the default, and the statement being executed must be a single SELECT statement or a stored procedure that contains a single SELECT statement.</span></span> <span data-ttu-id="2c05e-118">Lors de l'utilisation de curseurs côté serveur, les instructions SELECT ne peuvent pas utiliser de clauses non prises en charge par les curseurs côté serveur : COMPUTE, COMPUTE BY, FOR BROWSE et INTO.</span><span class="sxs-lookup"><span data-stu-id="2c05e-118">When using server cursors, SELECT statements cannot use clauses not supported by server cursors: COMPUTE, COMPUTE BY, FOR BROWSE, and INTO.</span></span>  
  
 <span data-ttu-id="2c05e-119">Vous pouvez contrôler le type de curseur utilisé en définissant SQL_ATTR_CURSOR_TYPE et SQL_ATTR_CONCURRENCY, ou en définissant SQL_ATTR_CURSOR_SENSITIVITY et SQL_ATTR_CURSOR_SCROLLABLE.</span><span class="sxs-lookup"><span data-stu-id="2c05e-119">You can control the type of cursor used either by setting SQL_ATTR_CURSOR_TYPE and SQL_ATTR_CONCURRENCY, or by setting SQL_ATTR_CURSOR_SENSITIVITY and SQL_ATTR_CURSOR_SCROLLABLE.</span></span> <span data-ttu-id="2c05e-120">Vous ne devez pas combiner les deux méthodes de spécification de comportement du curseur.</span><span class="sxs-lookup"><span data-stu-id="2c05e-120">You should not mix the two methods of specifying cursor behavior.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c05e-121">Exemple</span><span class="sxs-lookup"><span data-stu-id="2c05e-121">Example</span></span>  
 <span data-ttu-id="2c05e-122">L'exemple suivant alloue un descripteur d'instruction, définit un type de curseur dynamique avec accès concurrentiel optimiste de contrôle de version de ligne, puis exécute une instruction SELECT.</span><span class="sxs-lookup"><span data-stu-id="2c05e-122">The following sample allocates a statement handle, sets a dynamic cursor type with row versioning optimistic concurrency, and then executes a SELECT.</span></span>  
  
```  
retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CURSOR_TYPE, (SQLPOINTER)SQL_CURSOR_DYNAMIC, SQL_IS_INTEGER);  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CONCURRENCY, SQLPOINTER)SQL_CONCUR_ROWVER, SQL_IS_INTEGER);  
retcode = SQLExecDirect(hstmt1, SELECT au_lname FROM authors", SQL_NTS);  
```  
  
## <a name="example"></a><span data-ttu-id="2c05e-123">Exemple</span><span class="sxs-lookup"><span data-stu-id="2c05e-123">Example</span></span>  
 <span data-ttu-id="2c05e-124">L'exemple suivant alloue un descripteur d'instruction, définit un curseur déroulant SENSITIVE, puis exécute une instruction SELECT.</span><span class="sxs-lookup"><span data-stu-id="2c05e-124">The following sample allocates a statement handle, sets a scrollable, sensitive cursor, and then executes a SELECT</span></span>  
  
```  
retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
  
// Set the cursor options and execute the statement.  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CURSOR_SCROLLABLE, SQLPOINTER)SQL_SCROLLABLE, SQL_IS_INTEGER);  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CURSOR_SENSITIVITY, SQLPOINTER)SQL_INSENSITIVE, SQL_IS_INTEGER);  
retcode = SQLExecDirect(hstmt1, select au_lname from authors", SQL_NTS);  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c05e-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2c05e-125">See Also</span></span>  
 [<span data-ttu-id="2c05e-126">Rubriques de procédures relatives à l’exécution de requêtes &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="2c05e-126">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
