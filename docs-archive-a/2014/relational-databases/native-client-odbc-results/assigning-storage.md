---
title: Affectation du stockage | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- column-wise binding [ODBC]
- SQL Server Native Client ODBC driver, result sets
- ODBC applications, result sets
- SQLBindCol function
- storing data [ODBC]
- result sets [ODBC], storage
- SQL Server Native Client ODBC driver, data storage
- row-wise binding
- binding result sets [SQL Server Native Client]
- array binding
ms.assetid: 11c81955-5300-495f-925f-9256f2587b58
author: rothja
ms.author: jroth
ms.openlocfilehash: ada18c91493d91b36ced51bf84c32513a0c5f5df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612272"
---
# <a name="assigning-storage"></a><span data-ttu-id="c93de-102">Assignation du stockage</span><span class="sxs-lookup"><span data-stu-id="c93de-102">Assigning Storage</span></span>
  <span data-ttu-id="c93de-103">Une application peut assigner le stockage pour les résultats avant ou après avoir exécuté une instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="c93de-103">An application can assign storage for results before or after it executes a SQL statement.</span></span> <span data-ttu-id="c93de-104">Si une application prépare ou exécute en premier l'instruction SQL, elle peut se renseigner à propos du jeu de résultats avant d'assigner le stockage pour les résultats.</span><span class="sxs-lookup"><span data-stu-id="c93de-104">If an application prepares or executes the SQL statement first, it can inquire about the result set before it assigns storage for results.</span></span> <span data-ttu-id="c93de-105">Par exemple, si le jeu de résultats est inconnu, l'application doit extraire le nombre de colonnes avant de pouvoir lui assigner du stockage.</span><span class="sxs-lookup"><span data-stu-id="c93de-105">For example, if the result set is unknown, the application must retrieve the number of columns before it can assign storage for them.</span></span>  
  
 <span data-ttu-id="c93de-106">Pour associer le stockage pour une colonne de données, une application appelle [SQLBindCol](../native-client-odbc-api/sqlbindcol.md)et la transmet :</span><span class="sxs-lookup"><span data-stu-id="c93de-106">To associate storage for a column of data, an application calls [SQLBindCol](../native-client-odbc-api/sqlbindcol.md)and passes it:</span></span>  
  
-   <span data-ttu-id="c93de-107">Le type de données vers lequel les données doivent être converties.</span><span class="sxs-lookup"><span data-stu-id="c93de-107">The data type to which the data is to be converted.</span></span>  
  
-   <span data-ttu-id="c93de-108">L'adresse d'un tampon de sortie pour les données.</span><span class="sxs-lookup"><span data-stu-id="c93de-108">The address of an output buffer for the data.</span></span>  
  
     <span data-ttu-id="c93de-109">L'application doit allouer cette mémoire tampon, qui doit être suffisamment grande pour contenir les données au format dans lequel elles sont converties.</span><span class="sxs-lookup"><span data-stu-id="c93de-109">The application must allocate this buffer, and it must be large enough to hold the data in the form to which it is converted.</span></span>  
  
-   <span data-ttu-id="c93de-110">La longueur du tampon de sortie.</span><span class="sxs-lookup"><span data-stu-id="c93de-110">The length of the output buffer.</span></span>  
  
     <span data-ttu-id="c93de-111">Cette valeur est ignorée si les données retournées ont une largeur fixe dans C, tel qu'un entier, un nombre réel ou une structure de date.</span><span class="sxs-lookup"><span data-stu-id="c93de-111">This value is ignored if the returned data has a fixed width in C, such as an integer, real number, or date structure.</span></span>  
  
-   <span data-ttu-id="c93de-112">L'adresse d'un tampon mémoire dans lequel retourner le nombre d'octets de données disponibles.</span><span class="sxs-lookup"><span data-stu-id="c93de-112">The address of a storage buffer in which to return the number of bytes of available data.</span></span>  
  
 <span data-ttu-id="c93de-113">Une application peut également lier des colonnes de jeu de résultats à des tableaux de variables de programme afin de prendre en charge l'extraction de lignes de jeu de résultats en blocs.</span><span class="sxs-lookup"><span data-stu-id="c93de-113">An application can also bind result set columns to arrays of program variables to support fetching result set rows in blocks.</span></span> <span data-ttu-id="c93de-114">Il existe deux types différents de liaison de tableau :</span><span class="sxs-lookup"><span data-stu-id="c93de-114">There are two different types of array binding:</span></span>  
  
-   <span data-ttu-id="c93de-115">La liaison basée sur les colonnes est finie lorsque chaque colonne est liée à son propre tableau de variables.</span><span class="sxs-lookup"><span data-stu-id="c93de-115">Column-wise binding is finished when each column is bound to its own array of variables.</span></span>  
  
     <span data-ttu-id="c93de-116">La liaison selon les colonnes est spécifiée en appelant [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) avec l' *attribut* défini sur SQL_ATTR_ROW_BIND_TYPE et *ValuePtr* défini sur SQL_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="c93de-116">Column-wise binding is specified by calling [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) with *Attribute* set to SQL_ATTR_ROW_BIND_TYPE and *ValuePtr* set to SQL_BIND_BY_COLUMN.</span></span> <span data-ttu-id="c93de-117">Tous les tableaux doivent contenir le même nombre d'éléments.</span><span class="sxs-lookup"><span data-stu-id="c93de-117">All the arrays must have the same number of elements.</span></span>  
  
-   <span data-ttu-id="c93de-118">La liaison basée sur les lignes est finie lorsque tous les paramètres dans l'instruction SQL sont liés en tant qu'unité à un tableau de structures qui contiennent les variables individuelles pour les paramètres.</span><span class="sxs-lookup"><span data-stu-id="c93de-118">Row-wise binding is finished when all the parameters in the SQL statement are bound as a unit to an array of structures that contain the individual variables for the parameters.</span></span>  
  
     <span data-ttu-id="c93de-119">La liaison selon les lignes est spécifiée en appelant **SQLSetStmtAttr** avec l' *attribut* défini sur SQL_ATTR_ROW_BIND_TYPE et *ValuePtr* défini sur la taille de la structure contenant les variables qui recevront les colonnes du jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="c93de-119">Row-wise binding is specified by calling **SQLSetStmtAttr** with *Attribute* set to SQL_ATTR_ROW_BIND_TYPE and *ValuePtr* set to the size of the structure holding the variables that will receive the result set columns.</span></span>  
  
 <span data-ttu-id="c93de-120">L'application définit également SQL_ATTR_ROW_ARRAY_SIZE au nombre d'éléments dans les tableaux de colonnes ou de lignes et définit SQL_ATTR_ROW_STATUS_PTR et SQL_ATTR_ROWS_FETCHED_PTR.</span><span class="sxs-lookup"><span data-stu-id="c93de-120">The application also sets SQL_ATTR_ROW_ARRAY_SIZE to the number of elements in the column or row arrays and sets SQL_ATTR_ROW_STATUS_PTR and SQL_ATTR_ROWS_FETCHED_PTR.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c93de-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c93de-121">See Also</span></span>  
 [<span data-ttu-id="c93de-122">Traitement des résultats &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="c93de-122">Processing Results &#40;ODBC&#41;</span></span>](processing-results-odbc.md)  
  
  
