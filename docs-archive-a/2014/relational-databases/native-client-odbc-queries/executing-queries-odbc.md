---
title: Exécution de requêtes (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC applications, executing queries
- SQL Server Native Client ODBC driver, statements
- ODBC applications, statements
- SQL Server Native Client ODBC driver, queries
- queries [ODBC]
ms.assetid: d935bcba-8ce6-4159-8395-6c86431602ad
author: rothja
ms.author: jroth
ms.openlocfilehash: adc51186803148056401f58f1207d3e9a7abf9c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600865"
---
# <a name="executing-queries-odbc"></a><span data-ttu-id="214f5-102">Exécution de requêtes (ODBC)</span><span class="sxs-lookup"><span data-stu-id="214f5-102">Executing Queries (ODBC)</span></span>
  <span data-ttu-id="214f5-103">Après qu'une application ODBC a initialisé un handle de connexion et s'est connectée avec une source de données, elle alloue un ou plusieurs descripteurs d'instruction sur le handle de connexion.</span><span class="sxs-lookup"><span data-stu-id="214f5-103">After an ODBC application initializes a connection handle and connects with a data source, it allocates one or more statement handles on the connection handle.</span></span> <span data-ttu-id="214f5-104">L’application peut ensuite exécuter [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] des instructions sur le descripteur d’instruction.</span><span class="sxs-lookup"><span data-stu-id="214f5-104">The application can then execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statements on the statement handle.</span></span> <span data-ttu-id="214f5-105">La séquence générale des événements lors de l'exécution d'une instruction SQL est :</span><span class="sxs-lookup"><span data-stu-id="214f5-105">The general sequence of events in executing an SQL statement is:</span></span>  
  
1.  <span data-ttu-id="214f5-106">Définition des attributs de l'instruction requis.</span><span class="sxs-lookup"><span data-stu-id="214f5-106">Set any required statement attributes.</span></span>  
  
2.  <span data-ttu-id="214f5-107">Construction de l'instruction.</span><span class="sxs-lookup"><span data-stu-id="214f5-107">Construct the statement.</span></span>  
  
3.  <span data-ttu-id="214f5-108">Exécution de l'instruction.</span><span class="sxs-lookup"><span data-stu-id="214f5-108">Execute the statement.</span></span>  
  
4.  <span data-ttu-id="214f5-109">Extraction des jeux de résultats éventuels.</span><span class="sxs-lookup"><span data-stu-id="214f5-109">Retrieve any result sets.</span></span>  
  
 <span data-ttu-id="214f5-110">Après qu'une application a extrait toutes les lignes dans tous les jeux de résultats retournés par l'instruction SQL, elle peut exécuter une autre requête sur le même descripteur d'instruction.</span><span class="sxs-lookup"><span data-stu-id="214f5-110">After an application retrieves all the rows in all of the result sets returned by the SQL statement, it can execute another query on the same statement handle.</span></span> <span data-ttu-id="214f5-111">Si une application détermine qu’il n’est pas nécessaire d’extraire toutes les lignes d’un jeu de résultats particulier, elle peut annuler le reste du jeu de résultats en appelant [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) ou [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).</span><span class="sxs-lookup"><span data-stu-id="214f5-111">If an application determines that it is not required to retrieve all the rows in a particular result set, it can cancel the rest of the result set by calling either [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) or [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).</span></span>  
  
 <span data-ttu-id="214f5-112">Si, dans une application ODBC, vous devez exécuter plusieurs fois la même instruction SQL avec des données différentes, utilisez un marqueur de paramètre dénoté par un point d'interrogation (?) dans la construction d'une instruction SQL :</span><span class="sxs-lookup"><span data-stu-id="214f5-112">If, in an ODBC application, you must execute the same SQL statement multiple times with different data, use a parameter marker denoted by a question mark (?) in the construction of an SQL statement:</span></span>  
  
```  
INSERT INTO MyTable VALUES (?, ?, ?)  
```  
  
 <span data-ttu-id="214f5-113">Chaque marqueur de paramètre peut ensuite être lié à une variable de programme en appelant [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md).</span><span class="sxs-lookup"><span data-stu-id="214f5-113">Each parameter marker can then be bound to a program variable by calling [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md).</span></span>  
  
 <span data-ttu-id="214f5-114">Après l'exécution de toutes les instructions SQL et le traitement de leurs jeux de résultats, l'application libère le descripteur d'instruction.</span><span class="sxs-lookup"><span data-stu-id="214f5-114">After all SQL statements execute and their result sets process, the application frees the statement handle.</span></span>  
  
 <span data-ttu-id="214f5-115">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client prend en charge plusieurs descripteurs d’instruction par handle de connexion.</span><span class="sxs-lookup"><span data-stu-id="214f5-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports multiple statement handles per connection handle.</span></span> <span data-ttu-id="214f5-116">Les transactions sont gérées au niveau de la connexion, afin que tout le travail effectué sur tous les descripteurs d'instruction sur un handle de connexion unique soit géré dans le cadre de la même transaction.</span><span class="sxs-lookup"><span data-stu-id="214f5-116">Transactions are managed at the connection level, so that all work performed on all statement handles on a single connection handle are managed as part of the same transaction.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="214f5-117">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="214f5-117">In This Section</span></span>  
  
-   [<span data-ttu-id="214f5-118">Allocation d'un descripteur d'instruction</span><span class="sxs-lookup"><span data-stu-id="214f5-118">Allocating a Statement Handle</span></span>](allocating-a-statement-handle.md)  
  
-   [<span data-ttu-id="214f5-119">Construction d’une instruction SQL &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="214f5-119">Constructing an SQL Statement &#40;ODBC&#41;</span></span>](constructing-an-sql-statement-odbc.md)  
  
-   [<span data-ttu-id="214f5-120">Construction d'instructions SQL pour les curseurs</span><span class="sxs-lookup"><span data-stu-id="214f5-120">Constructing SQL Statements for Cursors</span></span>](constructing-sql-statements-for-cursors.md)  
  
-   [<span data-ttu-id="214f5-121">Utilisation de paramètres d'instruction</span><span class="sxs-lookup"><span data-stu-id="214f5-121">Using Statement Parameters</span></span>](using-statement-parameters.md)  
  
-   [<span data-ttu-id="214f5-122">Exécution d’instructions &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="214f5-122">Executing Statements &#40;ODBC&#41;</span></span>](executing-statements/executing-statements-odbc.md)  
  
-   [<span data-ttu-id="214f5-123">Libération d'un descripteur d'instruction</span><span class="sxs-lookup"><span data-stu-id="214f5-123">Freeing a Statement Handle</span></span>](freeing-a-statement-handle.md)  
  
## <a name="see-also"></a><span data-ttu-id="214f5-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="214f5-124">See Also</span></span>  
 [<span data-ttu-id="214f5-125">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="214f5-125">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
