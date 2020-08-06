---
title: Liaison de paramètres | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, parameters
- parameters [SQL Server Native Client], ODBC
- statements [ODBC], parameters
- binding parameters [SQL Server Native Client]
- parameter markers [ODBC]
- unbound parameter markers
- SQLBindParameter function
- ODBC applications, parameters
- bound parameter markers [SQL Server Native Client]
ms.assetid: d6c69739-8f89-475f-a60a-b2f6c06576e2
author: rothja
ms.author: jroth
ms.openlocfilehash: 3402a7efce43d0ce94a20c93504ac1dcb2c7b48f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600848"
---
# <a name="binding-parameters"></a><span data-ttu-id="23c6c-102">Liaison de paramètres</span><span class="sxs-lookup"><span data-stu-id="23c6c-102">Binding Parameters</span></span>
  <span data-ttu-id="23c6c-103">Chaque marqueur de paramètre dans une instruction SQL doit être associé, ou lié, à une variable dans l'application avant que l'instruction puisse être exécutée.</span><span class="sxs-lookup"><span data-stu-id="23c6c-103">Each parameter marker in an SQL statement must be associated, or bound, to a variable in the application before the statement can be executed.</span></span> <span data-ttu-id="23c6c-104">Pour ce faire, appelez la fonction [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) .</span><span class="sxs-lookup"><span data-stu-id="23c6c-104">This is done by calling the [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) function.</span></span> <span data-ttu-id="23c6c-105">**SQLBindParameter** décrit la variable de programme (adresse, type de données C, etc.) au pilote.</span><span class="sxs-lookup"><span data-stu-id="23c6c-105">**SQLBindParameter** describes the program variable (address, C data type, and so on) to the driver.</span></span> <span data-ttu-id="23c6c-106">Cette fonction identifie également le marqueur de paramètre en indiquant sa valeur ordinale puis décrit les caractéristiques de l'objet SQL qu'il représente (type de données SQL, précision, etc.).</span><span class="sxs-lookup"><span data-stu-id="23c6c-106">It also identifies the parameter marker by indicating its ordinal value and then describes the characteristics of the SQL object it represents (SQL data type, precision, and so on).</span></span>

 <span data-ttu-id="23c6c-107">Les marqueurs de paramètre peuvent être liés ou liés une nouvelle fois à tout moment avant l'exécution d'une instruction.</span><span class="sxs-lookup"><span data-stu-id="23c6c-107">Parameter markers can be bound or rebound at any time before a statement is executed.</span></span> <span data-ttu-id="23c6c-108">Une liaison de paramètre reste en vigueur jusqu'à ce que l'un des événements suivants se produise :</span><span class="sxs-lookup"><span data-stu-id="23c6c-108">A parameter binding remains in effect until one of the following occurs:</span></span>

-   <span data-ttu-id="23c6c-109">Un appel à [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) avec le paramètre *Option* défini sur SQL_RESET_PARAMS libère tous les paramètres liés au descripteur d’instruction.</span><span class="sxs-lookup"><span data-stu-id="23c6c-109">A call to [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) with the *Option* parameter set to SQL_RESET_PARAMS frees all parameters bound to the statement handle.</span></span>

-   <span data-ttu-id="23c6c-110">Un appel à **SQLBindParameter** avec *ParameterNumber* défini sur l’ordinal d’un marqueur de paramètre lié libère automatiquement la liaison précédente.</span><span class="sxs-lookup"><span data-stu-id="23c6c-110">A call to **SQLBindParameter** with *ParameterNumber* set to the ordinal of a bound parameter marker automatically releases the previous binding.</span></span>

 <span data-ttu-id="23c6c-111">Une application peut également lier des paramètres à des tableaux de variables de programme pour traiter une instruction SQL par lots.</span><span class="sxs-lookup"><span data-stu-id="23c6c-111">An application can also bind parameters to arrays of program variables to process an SQL statement in batches.</span></span> <span data-ttu-id="23c6c-112">Il existe deux types de liaison de tableau :</span><span class="sxs-lookup"><span data-stu-id="23c6c-112">There are two types of array binding:</span></span>

-   <span data-ttu-id="23c6c-113">Une liaison selon les colonnes est effectuée lorsque chaque paramètre individuel est lié à son propre tableau de variables.</span><span class="sxs-lookup"><span data-stu-id="23c6c-113">Column-wise binding is done when each individual parameter is bound to its own array of variables.</span></span>

     <span data-ttu-id="23c6c-114">La liaison selon les colonnes est spécifiée en appelant [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) avec l' *attribut* défini sur SQL_ATTR_PARAM_BIND_TYPE et *ValuePtr* défini sur SQL_PARAM_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="23c6c-114">Column-wise binding is specified by calling [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) with *Attribute* set to SQL_ATTR_PARAM_BIND_TYPE and *ValuePtr* set to SQL_PARAM_BIND_BY_COLUMN.</span></span>

-   <span data-ttu-id="23c6c-115">Une liaison selon les lignes est effectuée lorsque tous les paramètres dans l'instruction SQL sont liés en tant qu'unité à un tableau de structures qui contiennent les variables individuelles pour les paramètres.</span><span class="sxs-lookup"><span data-stu-id="23c6c-115">Row-wise binding is done when all of the parameters in the SQL statement are bound as a unit to an array of structures that contain the individual variables for the parameters.</span></span>

     <span data-ttu-id="23c6c-116">La liaison selon les lignes est spécifiée en appelant **SQLSetStmtAttr** avec l' *attribut* défini sur SQL_ATTR_PARAM_BIND_TYPE et *ValuePtr* défini sur la taille de la structure contenant les variables de programme.</span><span class="sxs-lookup"><span data-stu-id="23c6c-116">Row-wise binding is specified by calling **SQLSetStmtAttr** with *Attribute* set to SQL_ATTR_PARAM_BIND_TYPE and *ValuePtr* set to the size of the structure holding the program variables.</span></span>

 <span data-ttu-id="23c6c-117">Lorsque le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC native client envoie des paramètres de chaîne de caractères ou binaires au serveur, il remplit les valeurs à la longueur spécifiée dans le paramètre **SQLBindParameter** *Columns* .</span><span class="sxs-lookup"><span data-stu-id="23c6c-117">When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver sends character or binary string parameters to the server, it pads the values to the length specified in **SQLBindParameter** *ColumnSize* parameter.</span></span> <span data-ttu-id="23c6c-118">Si une application ODBC 2. x spécifie 0 pour *Column*, le pilote remplit la valeur de paramètre avec la précision du type de données.</span><span class="sxs-lookup"><span data-stu-id="23c6c-118">If an ODBC 2.x application specifies 0 for *ColumnSize*, the driver pads the parameter value to the precision of the data type.</span></span> <span data-ttu-id="23c6c-119">La précision est 8000 lors d'une connexion à des serveurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], 255 lors d'une connexion à des versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23c6c-119">The precision is 8000 when connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servers, 255 when connected to earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="23c6c-120">La *colonne Columns* est en octets pour les colonnes de type Variant.</span><span class="sxs-lookup"><span data-stu-id="23c6c-120">*ColumnSize* is in bytes for variant columns.</span></span>

 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="23c6c-121">prend en charge la définition de noms pour les paramètres de procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="23c6c-121">supports defining names for stored procedure parameters.</span></span> <span data-ttu-id="23c6c-122">ODBC 3.5 a également introduit la prise en charge des paramètres nommés utilisés lors de l'appel de procédures stockées [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23c6c-122">ODBC 3.5 also introduced support for named parameters used when calling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures.</span></span> <span data-ttu-id="23c6c-123">Cette prise en charge peut être utilisée pour :</span><span class="sxs-lookup"><span data-stu-id="23c6c-123">This support can be used to:</span></span>

-   <span data-ttu-id="23c6c-124">appeler une procédure stockée et fournir des valeurs pour un sous-ensemble des paramètres définis pour la procédure stockée ;</span><span class="sxs-lookup"><span data-stu-id="23c6c-124">Call a stored procedure and provide values for a subset of the parameters defined for the stored procedure.</span></span>

-   <span data-ttu-id="23c6c-125">spécifier les paramètres dans un ordre différent dans l'application de l'ordre spécifié quand la procédure stockée a été créée.</span><span class="sxs-lookup"><span data-stu-id="23c6c-125">Specify the parameters in a different order in the application than the order specified when the stored procedure was created.</span></span>

 <span data-ttu-id="23c6c-126">Les paramètres nommés sont pris en charge uniquement lors de l’utilisation de l' [!INCLUDE[tsql](../../includes/tsql-md.md)] `EXECUTE` instruction ou de la séquence d’échappement ODBC Call pour exécuter une procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="23c6c-126">Named parameters are only supported when using the [!INCLUDE[tsql](../../includes/tsql-md.md)] `EXECUTE` statement or the ODBC CALL escape sequence to execute a stored procedure.</span></span>

 <span data-ttu-id="23c6c-127">Si `SQL_DESC_NAME` est défini pour un paramètre de procédure stockée, tous les paramètres de procédure stockée dans la requête doivent également définir `SQL_DESC_NAME`.</span><span class="sxs-lookup"><span data-stu-id="23c6c-127">If `SQL_DESC_NAME` is set for a stored procedure parameter, all stored procedure parameters in the query should also set `SQL_DESC_NAME`.</span></span>  <span data-ttu-id="23c6c-128">Si des littéraux sont utilisés dans les appels de procédure stockée, où les paramètres ont `SQL_DESC_NAME` défini, les littéraux doivent utiliser le format *'Name* = *value*', où *Name* est le nom du paramètre de procédure stockée (par exemple, @p1 ).</span><span class="sxs-lookup"><span data-stu-id="23c6c-128">If literals are used in stored procedure calls, where parameters have `SQL_DESC_NAME` set, the literals should use the format *'name*=*value*', where *name* is the stored procedure parameter name (for example, @p1).</span></span> <span data-ttu-id="23c6c-129">Pour plus d’informations, consultez [liaison de paramètres par nom (paramètres nommés)](https://go.microsoft.com/fwlink/?LinkId=167215).</span><span class="sxs-lookup"><span data-stu-id="23c6c-129">For more information, see [Binding Parameters by Name (Named Parameters)](https://go.microsoft.com/fwlink/?LinkId=167215).</span></span>

## <a name="see-also"></a><span data-ttu-id="23c6c-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="23c6c-130">See Also</span></span>
 [<span data-ttu-id="23c6c-131">Utilisation de paramètres d'instruction</span><span class="sxs-lookup"><span data-stu-id="23c6c-131">Using Statement Parameters</span></span>](using-statement-parameters.md)


