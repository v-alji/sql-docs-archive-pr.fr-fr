---
title: Applications multithread | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- threads [SQL Server], multithreaded applications
- ODBC applications, multithreaded applications
- asynchronous operations [SQL Server Native Client]
- SQL Server Native Client ODBC driver, multithreaded applications
- multithreaded applications [SQL Server Native Client]
ms.assetid: d352c91a-6e08-4e50-9f3e-a37892d9c2cc
author: rothja
ms.author: jroth
ms.openlocfilehash: b680086f76e0c1a1e8c8cfc2f4ef82099957b3fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612256"
---
# <a name="multithreaded-applications"></a><span data-ttu-id="35b7e-102">Applications multithread</span><span class="sxs-lookup"><span data-stu-id="35b7e-102">Multithreaded Applications</span></span>
  <span data-ttu-id="35b7e-103">Le pilote ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client est un pilote multithread.</span><span class="sxs-lookup"><span data-stu-id="35b7e-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver is a multithreaded driver.</span></span> <span data-ttu-id="35b7e-104">L'écriture d'une application multithread est une alternative à l'utilisation d'appels asynchrones pour traiter plusieurs appels ODBC.</span><span class="sxs-lookup"><span data-stu-id="35b7e-104">Writing a multithreaded application is an alternative to using asynchronous calls to process multiple ODBC calls.</span></span> <span data-ttu-id="35b7e-105">Un thread peut effectuer un appel ODBC synchrone et d'autres threads peuvent être traités pendant que le premier thread est bloqué dans l'attente d'une réponse à son appel.</span><span class="sxs-lookup"><span data-stu-id="35b7e-105">A thread can make a synchronous ODBC call, and other threads can process while the first thread is blocked waiting for the response to its call.</span></span> <span data-ttu-id="35b7e-106">Ce modèle est plus efficace qu'effectuer des appels asynchrones, car il élimine les surcharges telles que le trafic réseau, et qu'effectuer des appels de fonctions ODBC répétés en testant SQL_STILL_EXECUTING.</span><span class="sxs-lookup"><span data-stu-id="35b7e-106">This model is more efficient than making asynchronous calls because it eliminates overhead such as network traffic and making repeated ODBC function calls testing for SQL_STILL_EXECUTING.</span></span>  
  
 <span data-ttu-id="35b7e-107">Le mode asynchrone est encore une méthode de traitement efficace.</span><span class="sxs-lookup"><span data-stu-id="35b7e-107">Asynchronous mode is still an effective method of processing.</span></span> <span data-ttu-id="35b7e-108">Les améliorations des performances d'un modèle multithread ne sont pas suffisantes pour justifier la réécriture d'applications asynchrones.</span><span class="sxs-lookup"><span data-stu-id="35b7e-108">The performance improvements of a multithreaded model are not enough to justify rewriting asynchronous applications.</span></span> <span data-ttu-id="35b7e-109">Si les utilisateurs convertissent des applications DB-Library qui utilisent le modèle asynchrone DB-Library, il est plus facile de les convertir au modèle asynchrone ODBC.</span><span class="sxs-lookup"><span data-stu-id="35b7e-109">If users are converting DB-Library applications that use the DB-Library asynchronous model, it is easier to convert them to the ODBC asynchronous model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35b7e-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="35b7e-110">See Also</span></span>  
 [<span data-ttu-id="35b7e-111">Création d’une application de pilote ODBC SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="35b7e-111">Creating a SQL Server Native Client ODBC Driver Application</span></span>](creating-a-driver-application.md)  
  
  
