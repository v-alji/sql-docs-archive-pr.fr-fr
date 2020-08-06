---
title: Construction d’une instruction SQL (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, statements
- statements [ODBC], constructing
- ODBC applications, statements
ms.assetid: 0acc71e2-8004-4dd8-8592-05c022bdd692
author: rothja
ms.author: jroth
ms.openlocfilehash: 1c454f936c49335555ca09b190e4d604c9fbad64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600868"
---
# <a name="constructing-an-sql-statement-odbc"></a><span data-ttu-id="cbf0c-102">Construction d'une instruction SQL (ODBC)</span><span class="sxs-lookup"><span data-stu-id="cbf0c-102">Constructing an SQL Statement (ODBC)</span></span>
  <span data-ttu-id="cbf0c-103">Les applications ODBC effectuent la plus grande partie de leur accès aux bases de données en exécutant des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbf0c-103">ODBC applications perform almost all of their database access by executing [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="cbf0c-104">La forme de ces instructions dépend des spécifications d'application.</span><span class="sxs-lookup"><span data-stu-id="cbf0c-104">The form of these statements depends on the application requirements.</span></span> <span data-ttu-id="cbf0c-105">Les instructions SQL peuvent être construites des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbf0c-105">SQL statements can be constructed in the following ways:</span></span>  
  
-   <span data-ttu-id="cbf0c-106">Codées de manière irréversible</span><span class="sxs-lookup"><span data-stu-id="cbf0c-106">Hard-coded</span></span>  
  
     <span data-ttu-id="cbf0c-107">Instructions statiques exécutées par une application en tant que tâche fixe.</span><span class="sxs-lookup"><span data-stu-id="cbf0c-107">Static statements performed by an application as a fixed task.</span></span>  
  
-   <span data-ttu-id="cbf0c-108">Construction au moment de l'exécution</span><span class="sxs-lookup"><span data-stu-id="cbf0c-108">Constructed at run time</span></span>  
  
     <span data-ttu-id="cbf0c-109">Les instructions SQL construites au moment de l'exécution permettent à l'utilisateur de personnaliser l'instruction en utilisant des clauses courantes telles que SELECT, WHERE et ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="cbf0c-109">SQL statements constructed at run time that enable the user to tailor the statement by using common clauses, such as SELECT, WHERE, and ORDER BY.</span></span> <span data-ttu-id="cbf0c-110">Cela inclut les requêtes ad hoc entrées par les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="cbf0c-110">This includes ad hoc queries entered by users.</span></span>  
  
 <span data-ttu-id="cbf0c-111">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC du client analyse les instructions SQL uniquement pour la syntaxe ODBC et ISO non directement prise en charge par le [!INCLUDE[ssDE](../../includes/ssde-md.md)] , que le pilote transforme [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cbf0c-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client ODBC driver parses SQL statements only for ODBC and ISO syntax not directly supported by the [!INCLUDE[ssDE](../../includes/ssde-md.md)], which the driver transforms into [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="cbf0c-112">Toute autre syntaxe SQL est passée au [!INCLUDE[ssDE](../../includes/ssde-md.md)] inchangée, où [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] déterminera s'il s'agit de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] valide.</span><span class="sxs-lookup"><span data-stu-id="cbf0c-112">All other SQL syntax is passed to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] unchanged, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will determine if it is valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cbf0c-113">Cette approche fournit deux avantages :</span><span class="sxs-lookup"><span data-stu-id="cbf0c-113">This approach yields two benefits:</span></span>  
  
-   <span data-ttu-id="cbf0c-114">Réduction des coûts</span><span class="sxs-lookup"><span data-stu-id="cbf0c-114">Reduced overhead</span></span>  
  
     <span data-ttu-id="cbf0c-115">Les coûts de traitement pour le pilote sont réduits car il doit analyser seulement un petit ensemble de clauses ODBC et ISO.</span><span class="sxs-lookup"><span data-stu-id="cbf0c-115">Processing overhead for the driver is minimized because it only has to scan for a small set of ODBC and ISO clauses.</span></span>  
  
-   <span data-ttu-id="cbf0c-116">Souplesse</span><span class="sxs-lookup"><span data-stu-id="cbf0c-116">Flexibility</span></span>  
  
     <span data-ttu-id="cbf0c-117">Les programmeurs peuvent personnaliser la portabilité de leurs applications.</span><span class="sxs-lookup"><span data-stu-id="cbf0c-117">Programmers can tailor the portability of their applications.</span></span> <span data-ttu-id="cbf0c-118">Pour améliorer la portabilité contre plusieurs bases de données, utilisez principalement la syntaxe ODBC et ISO.</span><span class="sxs-lookup"><span data-stu-id="cbf0c-118">To enhance portability against multiple databases, use primarily ODBC and ISO syntax.</span></span> <span data-ttu-id="cbf0c-119">Pour utiliser des améliorations spécifiques à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], utilisez la syntaxe [!INCLUDE[tsql](../../includes/tsql-md.md)] appropriée.</span><span class="sxs-lookup"><span data-stu-id="cbf0c-119">To use enhancements specific to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use the appropriate [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax.</span></span> <span data-ttu-id="cbf0c-120">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client prend en charge la [!INCLUDE[tsql](../../includes/tsql-md.md)] syntaxe complète afin que les applications basées sur ODBC puissent tirer parti de toutes les fonctionnalités de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cbf0c-120">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports the complete [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax so ODBC-based applications can take advantage of all the features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="cbf0c-121">La liste de colonnes dans une instruction SELECT doit contenir uniquement les colonnes requises pour effectuer la tâche actuelle.</span><span class="sxs-lookup"><span data-stu-id="cbf0c-121">The column list in a SELECT statement should contain only the columns required to perform the current task.</span></span> <span data-ttu-id="cbf0c-122">Cela réduit non seulement la quantité de données envoyées sur le réseau, mais réduit également l'impact des modifications de base de données sur l'application.</span><span class="sxs-lookup"><span data-stu-id="cbf0c-122">Not only does this reduce the amount of data sent across the network, but also it reduces the effect of database changes on the application.</span></span> <span data-ttu-id="cbf0c-123">Si une application ne fait pas référence à une colonne d'une table, elle n'est pas affectée par les modifications apportées à cette colonne.</span><span class="sxs-lookup"><span data-stu-id="cbf0c-123">If an application does not reference a column from a table, then the application is not affected by any changes made to that column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbf0c-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cbf0c-124">See Also</span></span>  
 [<span data-ttu-id="cbf0c-125">Exécution de requêtes &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="cbf0c-125">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
