---
title: Construction d’instructions SQL pour les curseurs | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], statement construction
- ODBC applications, cursors
- SQL Server Native Client ODBC driver, statements
- statements [ODBC], constructing
- ODBC applications, statements
- statements [ODBC], cursors
ms.assetid: 134003fd-9c93-4f5c-a988-045990933b80
author: rothja
ms.author: jroth
ms.openlocfilehash: b0fe0831b97c13c5d20067386f4e9d8c97ee19ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600867"
---
# <a name="constructing-sql-statements-for-cursors"></a><span data-ttu-id="b8221-102">Construction d'instructions SQL pour les curseurs</span><span class="sxs-lookup"><span data-stu-id="b8221-102">Constructing SQL Statements for Cursors</span></span>
  <span data-ttu-id="b8221-103">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client utilise des curseurs de serveur pour implémenter la fonctionnalité de curseur définie dans la spécification ODBC.</span><span class="sxs-lookup"><span data-stu-id="b8221-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver uses server cursors to implement the cursor functionality defined in the ODBC specification.</span></span> <span data-ttu-id="b8221-104">Une application ODBC contrôle le comportement des curseurs à l’aide de [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) pour définir différents attributs d’instruction.</span><span class="sxs-lookup"><span data-stu-id="b8221-104">An ODBC application controls the cursor behavior by using [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) to set different statement attributes.</span></span> <span data-ttu-id="b8221-105">Voici les attributs et leurs valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="b8221-105">These are the attributes and their defaults.</span></span>  
  
|<span data-ttu-id="b8221-106">Attribut</span><span class="sxs-lookup"><span data-stu-id="b8221-106">Attribute</span></span>|<span data-ttu-id="b8221-107">Default</span><span class="sxs-lookup"><span data-stu-id="b8221-107">Default</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="b8221-108">SQL_ATTR_CONCURRENCY</span><span class="sxs-lookup"><span data-stu-id="b8221-108">SQL_ATTR_CONCURRENCY</span></span>|<span data-ttu-id="b8221-109">SQL_CONCUR_READ_ONLY</span><span class="sxs-lookup"><span data-stu-id="b8221-109">SQL_CONCUR_READ_ONLY</span></span>|  
|<span data-ttu-id="b8221-110">SQL_ATTR_CURSOR_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8221-110">SQL_ATTR_CURSOR_TYPE</span></span>|<span data-ttu-id="b8221-111">SQL_CURSOR_FORWARD_ONLY</span><span class="sxs-lookup"><span data-stu-id="b8221-111">SQL_CURSOR_FORWARD_ONLY</span></span>|  
|<span data-ttu-id="b8221-112">SQL_ATTR_CURSOR_SCROLLABLE</span><span class="sxs-lookup"><span data-stu-id="b8221-112">SQL_ATTR_CURSOR_SCROLLABLE</span></span>|<span data-ttu-id="b8221-113">SQL_NONSCROLLABLE</span><span class="sxs-lookup"><span data-stu-id="b8221-113">SQL_NONSCROLLABLE</span></span>|  
|<span data-ttu-id="b8221-114">SQL_ATTR_CURSOR_SENSITIVITY</span><span class="sxs-lookup"><span data-stu-id="b8221-114">SQL_ATTR_CURSOR_SENSITIVITY</span></span>|<span data-ttu-id="b8221-115">SQL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="b8221-115">SQL_UNSPECIFIED</span></span>|  
|<span data-ttu-id="b8221-116">SQL_ATTR_ROW_ARRAY_SIZE</span><span class="sxs-lookup"><span data-stu-id="b8221-116">SQL_ATTR_ROW_ARRAY_SIZE</span></span>|<span data-ttu-id="b8221-117">1</span><span class="sxs-lookup"><span data-stu-id="b8221-117">1</span></span>|  
  
 <span data-ttu-id="b8221-118">Lorsque ces options sont définies sur leurs valeurs par défaut au moment de l’exécution d’une instruction SQL, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client n’utilise pas de curseur côté serveur pour implémenter le jeu de résultats ; à la place, il utilise un jeu de résultats par défaut.</span><span class="sxs-lookup"><span data-stu-id="b8221-118">When these options are set to their defaults at the time an SQL statement is executed, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not use a server cursor to implement the result set; instead, it uses a default result set.</span></span> <span data-ttu-id="b8221-119">Si l’une de ces options est modifiée par rapport aux valeurs par défaut au moment de l’exécution d’une instruction SQL, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC de native client tente d’utiliser un curseur côté serveur pour implémenter le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="b8221-119">If any of these options are changed from their defaults at the time an SQL statement is executed, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver attempts to use a server cursor to implement the result set.</span></span>  
  
 <span data-ttu-id="b8221-120">Les jeux de résultats par défaut prennent en charge toutes les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8221-120">Default result sets support all of the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="b8221-121">Il n'y a pas de restrictions concernant les types d'instructions SQL qui peuvent être exécutés lors de l'utilisation d'un jeu de résultats par défaut.</span><span class="sxs-lookup"><span data-stu-id="b8221-121">There are no restrictions on the types of SQL statements that can be executed when using a default result set.</span></span>  
  
 <span data-ttu-id="b8221-122">Les curseurs côté serveur ne prennent pas en charge toutes les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8221-122">Server cursors do not support all [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="b8221-123">Les curseurs côté serveur ne prennent pas en charge les instructions SQL qui génèrent plusieurs jeux de résultats.</span><span class="sxs-lookup"><span data-stu-id="b8221-123">Server cursors do not support any SQL statement that generates multiple result sets.</span></span>  
  
 <span data-ttu-id="b8221-124">Les types d'instructions suivants ne sont pas pris en charge par les curseurs côté serveur :</span><span class="sxs-lookup"><span data-stu-id="b8221-124">The following types of statements are not supported by server cursors:</span></span>  
  
-   <span data-ttu-id="b8221-125">Lots</span><span class="sxs-lookup"><span data-stu-id="b8221-125">Batches</span></span>  
  
     <span data-ttu-id="b8221-126">Les instructions SQL construites à partir de plusieurs instructions SQL SELECT individuelles, par exemple :</span><span class="sxs-lookup"><span data-stu-id="b8221-126">SQL statements built from two or more individual SQL SELECT statements, for example:</span></span>  
  
    ```  
    SELECT * FROM Authors; SELECT * FROM Titles  
    ```  
  
-   <span data-ttu-id="b8221-127">Procédures stockées avec plusieurs instructions SELECT</span><span class="sxs-lookup"><span data-stu-id="b8221-127">Stored procedures with multiple SELECT statements</span></span>  
  
     <span data-ttu-id="b8221-128">Instructions SQL qui exécutent une procédure stockée contenant plusieurs instructions SELECT.</span><span class="sxs-lookup"><span data-stu-id="b8221-128">SQL statements that execute a stored procedure containing more than one SELECT statement.</span></span> <span data-ttu-id="b8221-129">Cela inclut les instructions SELECT qui remplissent des paramètres ou des variables.</span><span class="sxs-lookup"><span data-stu-id="b8221-129">This includes SELECT statements that fill parameters or variables.</span></span>  
  
-   <span data-ttu-id="b8221-130">Mots clés</span><span class="sxs-lookup"><span data-stu-id="b8221-130">Keywords</span></span>  
  
     <span data-ttu-id="b8221-131">Instructions SQL contenant les mots clés FOR BROWSE ou INTO.</span><span class="sxs-lookup"><span data-stu-id="b8221-131">SQL statements containing the keywords FOR BROWSE, or INTO.</span></span>  
  
 <span data-ttu-id="b8221-132">Dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], si une instruction SQL qui remplit l'une de ces conditions est exécutée avec un curseur côté serveur, celui-ci est converti implicitement en un jeu de résultats par défaut.</span><span class="sxs-lookup"><span data-stu-id="b8221-132">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], if an SQL statement that matches any of these conditions is executed with a server cursor, the server cursor is implicitly converted to a default result set.</span></span> <span data-ttu-id="b8221-133">Une fois que **SQLExecDirect** ou **SQLExecute** a renvoyé SQL_SUCCESS_WITH_INFO, les paramètres par défaut des attributs de curseur sont redéfinis.</span><span class="sxs-lookup"><span data-stu-id="b8221-133">After **SQLExecDirect** or **SQLExecute** returns SQL_SUCCESS_WITH_INFO, the cursor attributes will be set back to their default settings.</span></span>  
  
 <span data-ttu-id="b8221-134">Les instructions SQL qui n'appartiennent à aucune des catégories précitées peuvent être exécutées avec tout paramètre d'attribut d'instruction ; elles fonctionnent aussi bien avec un jeu de résultats par défaut qu'avec un curseur côté serveur.</span><span class="sxs-lookup"><span data-stu-id="b8221-134">SQL statements that do not fit the categories above can be executed with any statement attribute settings; they work equally well with either a default result set or a server cursor.</span></span>  
  
## <a name="errors"></a><span data-ttu-id="b8221-135">Erreurs</span><span class="sxs-lookup"><span data-stu-id="b8221-135">Errors</span></span>  
 <span data-ttu-id="b8221-136">Dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 et versions ultérieures, toute tentative d'exécution d'une instruction qui produit plusieurs jeux de résultats génère SQL_SUCCESS_WITH INFO et le message suivant :</span><span class="sxs-lookup"><span data-stu-id="b8221-136">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 and later, an attempt to execute a statement that produces multiple result sets generates SQL_SUCCESS_WITH INFO and the following message:</span></span>  
  
```  
SqlState: 01S02"  
pfNative: 0  
szErrorMsgString: "[Microsoft][SQL Server Native Client][SQL Server]  
               Cursor type changed."  
```  
  
 <span data-ttu-id="b8221-137">Les applications ODBC qui reçoivent ce message peuvent appeler [SQLGetStmtAttr](../native-client-odbc-api/sqlgetstmtattr.md) pour déterminer les paramètres de curseur actuels.</span><span class="sxs-lookup"><span data-stu-id="b8221-137">ODBC applications receiving this message can call [SQLGetStmtAttr](../native-client-odbc-api/sqlgetstmtattr.md) to determine the current cursor settings.</span></span>  
  
 <span data-ttu-id="b8221-138">Toute tentative d'exécution d'une procédure avec plusieurs instructions SELECT lors de l'utilisation de curseurs côté serveur génère l'erreur suivante :</span><span class="sxs-lookup"><span data-stu-id="b8221-138">An attempt to execute a procedure with multiple SELECT statements when using server cursors generates the following error:</span></span>  
  
```  
SqlState: 42000  
pfNative: 16937  
szErrorMsgString: [Microsoft][SQL Server Native Client][SQL Server]  
               A server cursor is not allowed on a stored procedure  
               with more than one SELECT statement in it. Use a  
               default result set or client cursor.  
```  
  
 <span data-ttu-id="b8221-139">Toute tentative d'exécution d'un lot avec plusieurs instructions SELECT lors de l'utilisation de curseurs côté serveur génère l'erreur suivante :</span><span class="sxs-lookup"><span data-stu-id="b8221-139">An attempt to execute a batch with multiple SELECT statements when using server cursors generates the following error:</span></span>  
  
```  
SqlState: 42000  
pfNative: 16938  
szErrorMsgString: [Microsoft][SQL Server Native Client][SQL Server]  
               sp_cursoropen. The statement parameter can only  
               be a single SELECT statement or a single stored   
               procedure.  
```  
  
 <span data-ttu-id="b8221-140">Les applications ODBC qui reçoivent ces erreurs doivent réinitialiser tous les attributs d'instructions de curseur à leurs valeurs par défaut avant d'essayer d'exécuter l'instruction.</span><span class="sxs-lookup"><span data-stu-id="b8221-140">ODBC applications receiving these errors must reset all the cursor statement attributes to their defaults before attempting to execute the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8221-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b8221-141">See Also</span></span>  
 [<span data-ttu-id="b8221-142">Exécution de requêtes &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="b8221-142">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
