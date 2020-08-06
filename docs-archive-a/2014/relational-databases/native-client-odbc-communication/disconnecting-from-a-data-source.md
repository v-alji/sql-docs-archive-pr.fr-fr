---
title: Déconnexion d’une source de données | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC data sources, connections
- data sources [SQL Server Native Client]
- disconnecting [ODBC]
- ODBC applications, disconnecting
- SQLDisconnect function
- ODBC applications, data sources
- connections [SQL Server Native Client]
- SQLFreeHandle function
- ODBC data sources, disconnecting
- SQL Server Native Client ODBC driver, data sources
- ODBC functions
- SQL Server Native Client ODBC driver, connections
ms.assetid: 65b0267d-b2ab-4a59-83f2-436d90cfbf79
author: rothja
ms.author: jroth
ms.openlocfilehash: 5db3b83ab65d854f3a4d2182d9a4a1314e097681
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605395"
---
# <a name="disconnecting-from-a-data-source"></a><span data-ttu-id="f8f56-102">Déconnexion d'une source de données</span><span class="sxs-lookup"><span data-stu-id="f8f56-102">Disconnecting from a Data Source</span></span>
  <span data-ttu-id="f8f56-103">Lorsqu’une application a fini d’utiliser une source de données, elle appelle **SQLDisconnect**.</span><span class="sxs-lookup"><span data-stu-id="f8f56-103">When an application has finished using a data source, it calls **SQLDisconnect**.</span></span> <span data-ttu-id="f8f56-104">**SQLDisconnect** libère toutes les instructions qui sont allouées sur la connexion et déconnecte le pilote de la source de données.</span><span class="sxs-lookup"><span data-stu-id="f8f56-104">**SQLDisconnect** frees any statements that are allocated on the connection and disconnects the driver from the data source.</span></span> <span data-ttu-id="f8f56-105">Après la déconnexion, l’application peut appeler [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) pour libérer le handle de connexion.</span><span class="sxs-lookup"><span data-stu-id="f8f56-105">After disconnecting, the application can call [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) to free the connection handle.</span></span> <span data-ttu-id="f8f56-106">Avant de quitter, une application appelle également **SQLFreeHandle** pour libérer le handle d’environnement.</span><span class="sxs-lookup"><span data-stu-id="f8f56-106">Before exiting, an application also calls **SQLFreeHandle** to free the environment handle.</span></span>  
  
 <span data-ttu-id="f8f56-107">Après la déconnexion, une application peut réutiliser le handle de connexion alloué, se connecter à une autre source de données ou se reconnecter à la même source de données.</span><span class="sxs-lookup"><span data-stu-id="f8f56-107">After disconnecting, an application can reuse the allocated connection handle, either to connect to a different data source or reconnect to the same data source.</span></span> <span data-ttu-id="f8f56-108">La décision de rester connecté au lieu de se déconnecter et de se reconnecter ultérieurement requiert que le writer d'application considère les coûts relatifs de chaque option.</span><span class="sxs-lookup"><span data-stu-id="f8f56-108">The decision to remain connected instead of disconnecting and reconnecting later requires that the application writer consider the relative costs of each option.</span></span> <span data-ttu-id="f8f56-109">La connexion à une source de données et le fait de demeurer connecté peut être relativement coûteux, selon le moyen de connexion.</span><span class="sxs-lookup"><span data-stu-id="f8f56-109">Connecting to a data source and remaining connected can be relatively costly, depending on the connection medium.</span></span> <span data-ttu-id="f8f56-110">En faisant un compromis, l'application doit aussi faire des hypothèses sur la probabilité et le minutage d'opérations supplémentaires sur la même source de données.</span><span class="sxs-lookup"><span data-stu-id="f8f56-110">In making a trade-off, the application must also make assumptions about the probability and timing of additional operations on the same data source.</span></span> <span data-ttu-id="f8f56-111">Une application peut devoir utiliser également plusieurs connexions.</span><span class="sxs-lookup"><span data-stu-id="f8f56-111">An application may also have to use more than one connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8f56-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f8f56-112">See Also</span></span>  
 [<span data-ttu-id="f8f56-113">Communication avec SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="f8f56-113">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  
