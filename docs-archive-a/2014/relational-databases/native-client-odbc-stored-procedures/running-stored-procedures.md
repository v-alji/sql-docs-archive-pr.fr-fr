---
title: Exécution de procédures stockées | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, stored procedures
- stored procedures [ODBC], running
- SQL Server Native Client ODBC driver, stored procedures
- stored procedures [ODBC], executing
ms.assetid: 866b6dd3-2acd-4dfb-aeca-a0352b2d4c6a
author: rothja
ms.author: jroth
ms.openlocfilehash: 8e5de6a9a13c95b417657a1d108403fa27abe34b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709307"
---
# <a name="running-stored-procedures"></a><span data-ttu-id="91d3b-102">Exécution des procédures stockées</span><span class="sxs-lookup"><span data-stu-id="91d3b-102">Running Stored Procedures</span></span>
  <span data-ttu-id="91d3b-103">Une procédure stockée est un objet exécutable stocké dans une base de données.</span><span class="sxs-lookup"><span data-stu-id="91d3b-103">A stored procedure is an executable object stored in a database.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="91d3b-104">prend en charge :</span><span class="sxs-lookup"><span data-stu-id="91d3b-104">supports:</span></span>  
  
-   <span data-ttu-id="91d3b-105">Procédures stockées :</span><span class="sxs-lookup"><span data-stu-id="91d3b-105">Stored procedures:</span></span>  
  
     <span data-ttu-id="91d3b-106">une ou plusieurs instructions SQL précompilées en une seule procédure exécutable.</span><span class="sxs-lookup"><span data-stu-id="91d3b-106">One or more SQL statements precompiled into a single executable procedure.</span></span>  
  
-   <span data-ttu-id="91d3b-107">Les procédures stockées étendues :</span><span class="sxs-lookup"><span data-stu-id="91d3b-107">Extended stored procedures:</span></span>  
  
     <span data-ttu-id="91d3b-108">Les DLL C ou C++ écrites dans l'API SQL Server Open Data Services pour les procédures stockées étendues.</span><span class="sxs-lookup"><span data-stu-id="91d3b-108">C or C++ dynamic-link libraries (DLL) written to the SQL Server Open Data Services API for extended stored procedures.</span></span> <span data-ttu-id="91d3b-109">L'API Open Data Services étend les fonctions des procédures stockées pour inclure un code C ou C++.</span><span class="sxs-lookup"><span data-stu-id="91d3b-109">The Open Data Services API extends the capabilities of stored procedures to include C or C++ code.</span></span>  
  
 <span data-ttu-id="91d3b-110">Lorsque vous exécutez des instructions, l'appel d'une procédure stockée sur la source de données (au lieu d'exécuter ou de préparer directement une instruction dans l'application cliente) peut fournir les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="91d3b-110">When executing statements, calling a stored procedure on the data source (instead of directly executing or preparing a statement in the client application) can provide:</span></span>  
  
-   <span data-ttu-id="91d3b-111">Performances accrues</span><span class="sxs-lookup"><span data-stu-id="91d3b-111">Higher performance</span></span>  
  
     <span data-ttu-id="91d3b-112">Les instructions SQL sont analysées et compilées lorsque les procédures sont créées.</span><span class="sxs-lookup"><span data-stu-id="91d3b-112">SQL statements are parsed and compiled when procedures are created.</span></span> <span data-ttu-id="91d3b-113">Cette charge est ensuite enregistrée lorsque les procédures sont exécutées.</span><span class="sxs-lookup"><span data-stu-id="91d3b-113">This overhead is then saved when the procedures are executed.</span></span>  
  
-   <span data-ttu-id="91d3b-114">Charge réseau réduite</span><span class="sxs-lookup"><span data-stu-id="91d3b-114">Reduced network overhead</span></span>  
  
     <span data-ttu-id="91d3b-115">L'exécution d'une procédure au lieu d'envoyer des requêtes complexes à travers le réseau peut réduire le trafic réseau.</span><span class="sxs-lookup"><span data-stu-id="91d3b-115">Executing a procedure instead of sending complex queries across the network can reduce network traffic.</span></span> <span data-ttu-id="91d3b-116">Si une application ODBC utilise la syntaxe ODBC {CALL} pour exécuter une procédure stockée, le pilote ODBC procède à des optimisations supplémentaires qui éliminent le besoin de convertir les données des paramètres.</span><span class="sxs-lookup"><span data-stu-id="91d3b-116">If an ODBC application uses the ODBC { CALL } syntax to execute a stored procedure, the ODBC driver makes additional optimizations that eliminate the need to convert parameter data.</span></span>  
  
-   <span data-ttu-id="91d3b-117">Cohérence supérieure</span><span class="sxs-lookup"><span data-stu-id="91d3b-117">Greater consistency</span></span>  
  
     <span data-ttu-id="91d3b-118">Si les règles d'une organisation sont implémentées dans une ressource centrale, telle qu'une procédure stockée, elles peuvent être codées, testées et déboguées une fois.</span><span class="sxs-lookup"><span data-stu-id="91d3b-118">If an organization's rules are implemented in a central resource, such as a stored procedure, they can be coded, tested, and debugged once.</span></span> <span data-ttu-id="91d3b-119">Les programmeurs individuels peuvent utiliser ensuite les procédures stockées testées au lieu de développer leurs propres implémentations.</span><span class="sxs-lookup"><span data-stu-id="91d3b-119">Individual programmers can then use the tested stored procedures instead of developing their own implementations.</span></span>  
  
-   <span data-ttu-id="91d3b-120">Exactitude supérieure</span><span class="sxs-lookup"><span data-stu-id="91d3b-120">Greater accuracy</span></span>  
  
     <span data-ttu-id="91d3b-121">Comme les procédures stockées sont développées habituellement par des programmeurs expérimentés, elles tendent à être plus efficaces et à comporter moins d'erreurs qu'un code développé plusieurs fois par des programmeurs aux niveaux de compétence variables.</span><span class="sxs-lookup"><span data-stu-id="91d3b-121">Because stored procedures are usually developed by experienced programmers, they tend to be more efficient and have fewer errors than code developed multiple times by programmers of varying skill levels.</span></span>  
  
-   <span data-ttu-id="91d3b-122">Fonctionnalités supplémentaires</span><span class="sxs-lookup"><span data-stu-id="91d3b-122">Added functionality</span></span>  
  
     <span data-ttu-id="91d3b-123">Les procédures stockées étendues peuvent utiliser les fonctionnalités C et C++ non disponibles dans les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91d3b-123">Extended stored procedures can use C and C++ features not available in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
     <span data-ttu-id="91d3b-124">Pour obtenir un exemple d’appel d’une procédure stockée, consultez [traiter les codes de retour et les paramètres de sortie &#40;ODBC&#41;](../native-client-odbc-how-to/running-stored-procedures-process-return-codes-and-output-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="91d3b-124">For an example of how to call a stored procedure, see [Process Return Codes and Output Parameters &#40;ODBC&#41;](../native-client-odbc-how-to/running-stored-procedures-process-return-codes-and-output-parameters.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="91d3b-125">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="91d3b-125">In This Section</span></span>  
  
-   [<span data-ttu-id="91d3b-126">Appel d’une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="91d3b-126">Calling a Stored Procedure</span></span>](calling-a-stored-procedure.md)  
  
-   [<span data-ttu-id="91d3b-127">Traitement par lot des appels de procédures stockées</span><span class="sxs-lookup"><span data-stu-id="91d3b-127">Batching Stored Procedure Calls</span></span>](batching-stored-procedure-calls.md)  
  
-   [<span data-ttu-id="91d3b-128">Traitement des résultats des procédures stockées</span><span class="sxs-lookup"><span data-stu-id="91d3b-128">Processing Stored Procedure Results</span></span>](processing-stored-procedure-results.md)  
  
## <a name="see-also"></a><span data-ttu-id="91d3b-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="91d3b-129">See Also</span></span>  
 <span data-ttu-id="91d3b-130">[SQL Server Native Client &#40;&#41;ODBC](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="91d3b-130">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="91d3b-131">Rubriques de procédures relatives à l’exécution de procédures stockées &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="91d3b-131">Running Stored Procedures How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md)  
  
  
