---
title: Procédures stockées compilées en mode natif | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
helpviewer_keywords:
- natively compiled stored procedures
ms.assetid: d5ed432c-10c5-4e4f-883c-ef4d1fa32366
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b8fb7a379c0c08ca357baa1042ebcf51c512c9ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706495"
---
# <a name="natively-compiled-stored-procedures"></a><span data-ttu-id="a4a67-102">procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="a4a67-102">Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="a4a67-103">Les procédures stockées compilées en mode natif sont des procédures stockées [!INCLUDE[tsql](../../includes/tsql-md.md)] compilées en code natif qui accèdent aux tables optimisées en mémoire.</span><span class="sxs-lookup"><span data-stu-id="a4a67-103">Natively compiled stored procedures are [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures compiled to native code that access memory-optimized tables.</span></span> <span data-ttu-id="a4a67-104">Elles permettent une exécution efficace des requêtes et de la logique métier des procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="a4a67-104">Natively compiled stored procedures allow for efficient execution of queries and business logic in the stored procedure.</span></span> <span data-ttu-id="a4a67-105">Pour plus d'informations sur le processus de compilation en mode natif, consultez [Native Compilation of Tables and Stored Procedures](native-compilation-of-tables-and-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a4a67-105">For more details about the native compilation process, see [Native Compilation of Tables and Stored Procedures](native-compilation-of-tables-and-stored-procedures.md).</span></span> <span data-ttu-id="a4a67-106">Pour plus d’informations sur la migration des procédures stockées sur disque vers des procédures stockées compilées en mode natif, consultez [Problèmes de migration pour les procédures stockées compilées en mode natif](migration-issues-for-natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a4a67-106">For more information about migrating disk-based stored procedures to natively compiled stored procedures, see [Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a4a67-107">La différence entre les procédures stockées (sur disque) interprétées et les procédures stockées compilées en mode natif réside dans le fait qu'une procédure stockée interprétée est compilée lors de la première exécution, tandis qu'une procédure stockée compilée en mode natif l'est au moment de sa création.</span><span class="sxs-lookup"><span data-stu-id="a4a67-107">One difference between interpreted (disk-based) stored procedures and natively compiled stored procedures is that an interpreted stored procedure is compiled at first execution whereas a natively compiled stored procedure is compiled when it is created.</span></span> <span data-ttu-id="a4a67-108">Avec des procédures stockées compilées en mode natif, de nombreuses conditions d'erreur (dépassement arithmétique, conversion de type, et certaines conditions de division par zéro) peuvent être détectées lors de la création et entraîner l'échec de la création de la procédure stockée compilée en mode natif.</span><span class="sxs-lookup"><span data-stu-id="a4a67-108">With natively compiled stored procedures, many error conditions (arithmetic overflow, type conversion, and some divide-by-zero conditions) can be detected at create time and will cause creation of the natively compiled stored procedure to fail.</span></span> <span data-ttu-id="a4a67-109">Avec des procédures stockées interprétées, ces conditions d'erreur ne provoquent généralement pas un échec lorsque la procédure stockée est créée, mais toutes les exécutions échoueront.</span><span class="sxs-lookup"><span data-stu-id="a4a67-109">With interpreted stored procedures, these error conditions will typically not cause a failure when the stored procedure is created, but all executions will fail.</span></span>  
  
 <span data-ttu-id="a4a67-110">Rubriques de cette section :</span><span class="sxs-lookup"><span data-stu-id="a4a67-110">Topics in this section:</span></span>  
  
-   [<span data-ttu-id="a4a67-111">Création de procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="a4a67-111">Creating Natively Compiled Stored Procedures</span></span>](creating-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="a4a67-112">Blocs Atomic</span><span class="sxs-lookup"><span data-stu-id="a4a67-112">Atomic Blocks</span></span>](atomic-blocks-in-native-procedures.md)  
  
-   [<span data-ttu-id="a4a67-113">Constructions prises en charge dans les procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="a4a67-113">Supported Constructs in Natively Compiled Stored Procedures</span></span>](supported-features-for-natively-compiled-t-sql-modules.md)  
  
-   [<span data-ttu-id="a4a67-114">Utilisation de Try..Catch dans des procédures stockées en mode natif</span><span class="sxs-lookup"><span data-stu-id="a4a67-114">Using Try..Catch in Natively Compiled Stored Procedures</span></span>](../../database-engine/using-try-catch-in-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="a4a67-115">Constructions prises en charge dans les procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="a4a67-115">Supported Constructs on Natively Compiled Stored Procedures</span></span>](supported-ddl-for-natively-compiled-t-sql-modules.md)  
  
-   [<span data-ttu-id="a4a67-116">Procédures stockées compilées en mode natif et options SET d'exécution</span><span class="sxs-lookup"><span data-stu-id="a4a67-116">Natively Compiled Stored Procedures and Execution Set Options</span></span>](natively-compiled-stored-procedures-and-execution-set-options.md)  
  
-   [<span data-ttu-id="a4a67-117">Meilleures pratiques pour appeler des procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="a4a67-117">Best Practices for Calling Natively Compiled Stored Procedures</span></span>](best-practices-for-calling-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="a4a67-118">Surveillance des performances des procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="a4a67-118">Monitoring Performance of Natively Compiled Stored Procedures</span></span>](monitoring-performance-of-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="a4a67-119">Appeler des procédures stockées compilées en mode natif à partir d'applications d'accès aux données</span><span class="sxs-lookup"><span data-stu-id="a4a67-119">Calling Natively Compiled Stored Procedures from Data Access Applications</span></span>](calling-natively-compiled-stored-procedures-from-data-access-applications.md)  
  
## <a name="see-also"></a><span data-ttu-id="a4a67-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a4a67-120">See Also</span></span>  
 [<span data-ttu-id="a4a67-121">Tables à mémoire optimisée</span><span class="sxs-lookup"><span data-stu-id="a4a67-121">Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
  
