---
title: Procédures | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [ODBC]
- stored procedures [ODBC], about ODBC stored procedures
- ODBC applications, statements
- statements [ODBC], stored procedures
- ODBC applications, stored procedures
ms.assetid: c64d5f3a-376b-48ef-84f3-b6148ac8600a
author: rothja
ms.author: jroth
ms.openlocfilehash: a7ae4678d324ba7d07ae429793b1f75b57bb15e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600853"
---
# <a name="procedures"></a><span data-ttu-id="b2ac7-102">Procédures</span><span class="sxs-lookup"><span data-stu-id="b2ac7-102">Procedures</span></span>
  <span data-ttu-id="b2ac7-103">Une procédure stockée est un objet exécutable précompilé qui contient une ou plusieurs instructions [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2ac7-103">A stored procedure is a precompiled executable object that contains one or more [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="b2ac7-104">Les procédures stockées peuvent posséder des paramètres d'entrée et de sortie et peuvent également émettre un code de retour de type entier.</span><span class="sxs-lookup"><span data-stu-id="b2ac7-104">Stored procedures can have input and output parameters and can also put out an integer return code.</span></span> <span data-ttu-id="b2ac7-105">Une application peut énumérer les procédures stockées disponibles en utilisant des fonctions de catalogue.</span><span class="sxs-lookup"><span data-stu-id="b2ac7-105">An application can enumerate available stored procedures by using catalog functions.</span></span>  
  
 <span data-ttu-id="b2ac7-106">Les applications ODBC qui ciblent [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] doivent utiliser uniquement l'exécution directe pour appeler une procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="b2ac7-106">ODBC applications that target [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] should only use direct execution to call a stored procedure.</span></span> <span data-ttu-id="b2ac7-107">Lorsqu’il est connecté à des versions antérieures de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pilote ODBC Native Client implémente la [fonction SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360) en créant une procédure stockée temporaire, qui est ensuite appelée sur **SQLExecute**.</span><span class="sxs-lookup"><span data-stu-id="b2ac7-107">When connected to earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver implements [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) by creating a temporary stored procedure, which is then called on **SQLExecute**.</span></span> <span data-ttu-id="b2ac7-108">Il ajoute une surcharge pour que **SQLPrepare** crée une procédure stockée temporaire qui appelle uniquement la procédure stockée cible plutôt que d’exécuter directement la procédure stockée cible.</span><span class="sxs-lookup"><span data-stu-id="b2ac7-108">It adds overhead to have **SQLPrepare** create a temporary stored procedure that only calls the target stored procedure versus directly executing the target stored procedure.</span></span> <span data-ttu-id="b2ac7-109">Même lors d'une connexion à une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], la préparation d'un appel requiert une boucle réseau supplémentaire et l'établissement d'un plan d'exécution qui appelle simplement le plan d'exécution de procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="b2ac7-109">Even when connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], preparing a call requires an extra round trip across the network and the building of an execution plan that just calls the stored procedure execution plan.</span></span>  
  
 <span data-ttu-id="b2ac7-110">Les applications ODBC doivent utiliser la syntaxe ODBC CALL lors de l'exécution d'une procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="b2ac7-110">ODBC applications should use the ODBC CALL syntax when executing a stored procedure.</span></span> <span data-ttu-id="b2ac7-111">Le pilote est optimisé pour utiliser un mécanisme d'appel de procédure distante pour appeler la procédure lorsque la syntaxe ODBC CALL est utilisée.</span><span class="sxs-lookup"><span data-stu-id="b2ac7-111">The driver is optimized to use a remote procedure call mechanism to call the procedure when the ODBC CALL syntax is used.</span></span> <span data-ttu-id="b2ac7-112">Ce mécanisme est plus efficace que celui utilisé pour envoyer une instruction [!INCLUDE[tsql](../../../includes/tsql-md.md)] EXECUTE au serveur.</span><span class="sxs-lookup"><span data-stu-id="b2ac7-112">This is more efficient than the mechanism used to send a [!INCLUDE[tsql](../../../includes/tsql-md.md)] EXECUTE statement to the server.</span></span>  
  
 <span data-ttu-id="b2ac7-113">Pour plus d’informations, consultez [exécution de procédures stockées](../../native-client-odbc-stored-procedures/running-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b2ac7-113">For more information, see [Running Stored Procedures](../../native-client-odbc-stored-procedures/running-stored-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2ac7-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b2ac7-114">See Also</span></span>  
 [<span data-ttu-id="b2ac7-115">Exécution d’instructions &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="b2ac7-115">Executing Statements &#40;ODBC&#41;</span></span>](executing-statements-odbc.md)  
  
  
