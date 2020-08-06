---
title: Bonnes pratiques pour appeler des procédures stockées compilées en mode natif | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f39fc1c7-cfec-4a95-97f6-6b95954694bb
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d07d0e290d1fbd9b324235e64734a399bf7801d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601453"
---
# <a name="best-practices-for-calling-natively-compiled-stored-procedures"></a><span data-ttu-id="41322-102">Meilleures pratiques pour appeler des procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="41322-102">Best Practices for Calling Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="41322-103">Les procédures stockées compilées en mode natif sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="41322-103">Natively compiled stored procedures are:</span></span>  
  
-   <span data-ttu-id="41322-104">utilisées en général dans les parties ayant un impact sur les performances d'une application ;</span><span class="sxs-lookup"><span data-stu-id="41322-104">Used typically in performance-critical parts of an application.</span></span>  
  
-   <span data-ttu-id="41322-105">exécutées fréquemment ;</span><span class="sxs-lookup"><span data-stu-id="41322-105">Frequently executed.</span></span>  
  
-   <span data-ttu-id="41322-106">réputées très rapides.</span><span class="sxs-lookup"><span data-stu-id="41322-106">Expected to be very fast.</span></span>  
  
 <span data-ttu-id="41322-107">L'avantage lié à l'utilisation d'une procédure stockée compilée en mode natif augmente avec le nombre de lignes et la quantité de logique qui est traitée par la procédure.</span><span class="sxs-lookup"><span data-stu-id="41322-107">The performance benefit of using a natively compiled stored procedure increases with the number of rows and the amount of logic that is processed by the procedure.</span></span> <span data-ttu-id="41322-108">Par exemple, une procédure stockée compilée en mode natif présentera de meilleures performances si elle utilise un ou plusieurs des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="41322-108">For example, a natively compiled stored procedure will exhibit better performance if it uses one or more of the following:</span></span>  
  
-   <span data-ttu-id="41322-109">Agrégation.</span><span class="sxs-lookup"><span data-stu-id="41322-109">Aggregation.</span></span>  
  
-   <span data-ttu-id="41322-110">jointures de boucles imbriquées ;</span><span class="sxs-lookup"><span data-stu-id="41322-110">Nested-loops joins.</span></span>  
  
-   <span data-ttu-id="41322-111">opérations de sélection, insertion, mise à jour et suppression en plusieurs instructions ;</span><span class="sxs-lookup"><span data-stu-id="41322-111">Multi-statement select, insert, update, and delete operations.</span></span>  
  
-   <span data-ttu-id="41322-112">expressions complexes ;</span><span class="sxs-lookup"><span data-stu-id="41322-112">Complex expressions.</span></span>  
  
-   <span data-ttu-id="41322-113">logique procédurale, par exemple des instructions conditionnelles et des boucles.</span><span class="sxs-lookup"><span data-stu-id="41322-113">Procedural logic, such as conditional statements and loops.</span></span>  
  
 <span data-ttu-id="41322-114">Si vous devez traiter une seule ligne, l'utilisation d'une procédure stockée compilée en mode natif peut ne pas fournir un avantage en matière de performances.</span><span class="sxs-lookup"><span data-stu-id="41322-114">If you need to process only a single row, using a natively compiled stored procedure may not provide a performance benefit.</span></span>  
  
 <span data-ttu-id="41322-115">Pour éviter que le serveur soit contraint de mettre en correspondance les noms des paramètres et les types de conversion :</span><span class="sxs-lookup"><span data-stu-id="41322-115">To avoid the server having to map parameter names and convert types:</span></span>  
  
-   <span data-ttu-id="41322-116">Faites correspondre les types de paramètres transmis à la procédure avec les types dans la définition de la procédure.</span><span class="sxs-lookup"><span data-stu-id="41322-116">Match the types of the parameters passed to the procedure with the types in the procedure definition.</span></span>  
  
-   <span data-ttu-id="41322-117">Utilisez des paramètres (sans nom) ordinaux lorsque vous appelez des procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="41322-117">Use ordinal (nameless) parameters when calling natively compiled stored procedures.</span></span> <span data-ttu-id="41322-118">Pour une exécution optimale, n'utilisez pas de paramètres nommés.</span><span class="sxs-lookup"><span data-stu-id="41322-118">For the most efficient execution, do not use named parameters.</span></span>  
  
 <span data-ttu-id="41322-119">L'utilisation de paramètres nommés (inefficaces) avec des procédures stockées compilées en mode natif peut être détectée par le XEvent `hekaton_slow_parameter_passing`, avec `reason=named_parameters`.</span><span class="sxs-lookup"><span data-stu-id="41322-119">Use of (inefficient) named parameters with natively compiled stored procedures can be detected through the XEvent `hekaton_slow_parameter_passing`, with `reason=named_parameters`.</span></span>  
  
 <span data-ttu-id="41322-120">De même, vous pouvez détecter l'utilisation de types incompatibles dans le même XEvent `hekaton_slow_parameter_passing`, avec `reason=parameter_conversion`.</span><span class="sxs-lookup"><span data-stu-id="41322-120">Similarly, you can detect use of mismatched types through the same XEvent `hekaton_slow_parameter_passing`, with `reason=parameter_conversion`.</span></span>  
  
 <span data-ttu-id="41322-121">Étant donné que vous devez implémenter la logique de nouvelle tentative lors de l'utilisation des tables mémoire optimisées (dans de nombreux scénarios), et que vous devrez contourner certaines limitations de fonctionnalités, vous pouvez créer une procédure stockée [!INCLUDE[tsql](../../includes/tsql-md.md)] interprétée par wrapper.</span><span class="sxs-lookup"><span data-stu-id="41322-121">Because you will need to implement retry logic when using memory-optimized tables (in many scenarios), and because you will need to work around certain feature limitations, you may want to create a wrapper interpreted [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure.</span></span> <span data-ttu-id="41322-122">Pour obtenir un exemple, consultez [instructions pour la logique de nouvelle tentative pour les transactions sur les tables optimisées en mémoire](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="41322-122">For an example, see [Guidelines for Retry Logic for Transactions on Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41322-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="41322-123">See Also</span></span>  
 [<span data-ttu-id="41322-124">Procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="41322-124">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
