---
title: Mode asynchrone et SQLCancel | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- asynchronous operations [SQL Server Native Client]
- SQLCancel function
- SQLSetConnectAttr function
- SQL Server Native Client, asynchronous operations
- ODBC functions
- ODBC applications, asynchronous operations
- SQL Server Native Client ODBC driver, asynchronous mode
ms.assetid: f31702a2-df76-4589-ac3b-da5412c03dc2
author: rothja
ms.author: jroth
ms.openlocfilehash: 9071c6821e6edeb577b639223e42899d2927bced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612255"
---
# <a name="asynchronous-mode-and-sqlcancel"></a><span data-ttu-id="0514c-102">Mode asynchrone et SQLCancel</span><span class="sxs-lookup"><span data-stu-id="0514c-102">Asynchronous Mode and SQLCancel</span></span>
  <span data-ttu-id="0514c-103">Certaines fonctions ODBC peuvent fonctionner en mode synchrone ou asynchrone.</span><span class="sxs-lookup"><span data-stu-id="0514c-103">Some ODBC functions can operate either synchronously or asynchronously.</span></span> <span data-ttu-id="0514c-104">L'application peut activer les opérations asynchrones pour un descripteur d'instruction ou un handle de connexion.</span><span class="sxs-lookup"><span data-stu-id="0514c-104">The application can enable asynchronous operations for either a statement handle or a connection handle.</span></span> <span data-ttu-id="0514c-105">Si l'option est définie pour un handle de connexion, tous les descripteurs d'instruction sur le handle de connexion sont affectés.</span><span class="sxs-lookup"><span data-stu-id="0514c-105">If the option is set for a connection handle, it affects all statement handles on the connection handle.</span></span> <span data-ttu-id="0514c-106">L'application utilise les instructions suivantes pour activer ou désactiver les opérations asynchrones :</span><span class="sxs-lookup"><span data-stu-id="0514c-106">The application uses the following statements to enable or disable asynchronous operations:</span></span>  
  
```  
SQLSetConnectAttr(hdbc, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_ON, SQL_IS_INTEGER);  
SQLSetConnectAttr(hdbc, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_OFF, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_ON, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_OFF, SQL_IS_INTEGER);  
```  
  
 <span data-ttu-id="0514c-107">Lorsqu'une application appelle une fonction ODBC en mode synchrone, le pilote ne rend pas le contrôle à l'application jusqu'à ce qu'il soit averti que le serveur a terminé la commande.</span><span class="sxs-lookup"><span data-stu-id="0514c-107">When an application calls an ODBC function in synchronous mode, the driver does not return control to the application until it is notified that the server has completed the command.</span></span>  
  
 <span data-ttu-id="0514c-108">En mode asynchrone, le pilote rend immédiatement le contrôle à l'application, avant même d'envoyer la commande au serveur.</span><span class="sxs-lookup"><span data-stu-id="0514c-108">When operating asynchronously, the driver immediately returns control to the application, even before sending the command to the server.</span></span> <span data-ttu-id="0514c-109">Le pilote définit le code de retour sur SQL_STILL_EXECUTING.</span><span class="sxs-lookup"><span data-stu-id="0514c-109">The driver sets the return code to SQL_STILL_EXECUTING.</span></span> <span data-ttu-id="0514c-110">L'application peut ensuite effectuer un autre travail.</span><span class="sxs-lookup"><span data-stu-id="0514c-110">The application can then perform other work.</span></span>  
  
 <span data-ttu-id="0514c-111">Lorsque l'application teste l'achèvement de la commande, il effectue le même appel de fonction avec les mêmes paramètres sur le pilote.</span><span class="sxs-lookup"><span data-stu-id="0514c-111">When the application tests for completion of the command, it makes the same function call with the same parameters to the driver.</span></span> <span data-ttu-id="0514c-112">Si le pilote n'a pas encore reçu de réponse du serveur, il retourne de nouveau SQL_STILL_EXECUTING.</span><span class="sxs-lookup"><span data-stu-id="0514c-112">If the driver has not yet received an answer from the server, it will again return SQL_STILL_EXECUTING.</span></span> <span data-ttu-id="0514c-113">L'application doit tester régulièrement la commande jusqu'à ce que le code de retour soit différent de SQL_STILL_EXECUTING.</span><span class="sxs-lookup"><span data-stu-id="0514c-113">The application must test the command periodically until the return code is something other than SQL_STILL_EXECUTING.</span></span> <span data-ttu-id="0514c-114">Lorsque l'application obtient un autre code de retour, même SQL_ERROR, elle peut déterminer que la commande est terminée.</span><span class="sxs-lookup"><span data-stu-id="0514c-114">When the application gets some other return code, even SQL_ERROR, it can determine that the command has completed.</span></span>  
  
 <span data-ttu-id="0514c-115">Une commande peut parfois rester longtemps en attente.</span><span class="sxs-lookup"><span data-stu-id="0514c-115">Sometimes a command is outstanding for a long time.</span></span> <span data-ttu-id="0514c-116">Si l’application doit annuler la commande sans attendre de réponse, elle peut le faire en appelant **SQLCancel** avec le même descripteur d’instruction que la commande en suspens.</span><span class="sxs-lookup"><span data-stu-id="0514c-116">If the application needs to cancel the command without waiting for a reply, it can do so by calling **SQLCancel** with the same statement handle as the outstanding command.</span></span> <span data-ttu-id="0514c-117">Il s’agit de la seule fois où **SQLCancel** doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="0514c-117">This is the only time **SQLCancel** should be used.</span></span> <span data-ttu-id="0514c-118">Certains programmeurs utilisent **SQLCancel** lorsqu’ils ont traité des éléments dans un jeu de résultats et veulent annuler le reste du jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="0514c-118">Some programmers use **SQLCancel** when they have processed part way through a result set and want to cancel the rest of the result set.</span></span> <span data-ttu-id="0514c-119">[SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) ou [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) doit être utilisé pour annuler le reste d’un jeu de résultats en suspens, et non **SQLCancel**.</span><span class="sxs-lookup"><span data-stu-id="0514c-119">[SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) or [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) should be used to cancel the remainder of an outstanding result set, not **SQLCancel**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0514c-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0514c-120">See Also</span></span>  
 [<span data-ttu-id="0514c-121">Création d’une application de pilote ODBC SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="0514c-121">Creating a SQL Server Native Client ODBC Driver Application</span></span>](creating-a-driver-application.md)  
  
  
