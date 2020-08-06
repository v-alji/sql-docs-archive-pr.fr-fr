---
title: Définir le classement des bases de données définies par l’utilisateur pour qu’elles correspondent à celles des bases de données master et Model | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: c686446f-dae1-4b05-a3df-837b3422988d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b48696fb56c40062d62f04845715170887f84fda
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696024"
---
# <a name="set-the-collation-of-user-defined-databases-to-match-those-of-the-master-and-model-databases"></a><span data-ttu-id="b5c9d-102">Définir le même classement pour les bases de données définies par l'utilisateur que pour les bases de données MASTER ou model</span><span class="sxs-lookup"><span data-stu-id="b5c9d-102">Set the Collation of User-defined Databases to Match Those of the master and model Databases</span></span>
  <span data-ttu-id="b5c9d-103">Cette règle vérifie si les bases de données définies par l'utilisateur sont définies en utilisant un classement de base de données identique à celui de la base de données MASTER ou model.</span><span class="sxs-lookup"><span data-stu-id="b5c9d-103">This rule checks whether user-defined databases are defined by using a database collation that is the same as the collation for master or model.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="b5c9d-104">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="b5c9d-104">Best Practices Recommendations</span></span>  
 <span data-ttu-id="b5c9d-105">Nous recommandons d'utiliser pour les bases de données définies par l'utilisateur les même classements que ceux des bases de données MASTER ou model.</span><span class="sxs-lookup"><span data-stu-id="b5c9d-105">We recommend that the collations of user-defined databases match the collation of master or model.</span></span> <span data-ttu-id="b5c9d-106">Dans le cas contraire, des conflits de classement pouvant empêcher l'exécution du code risquent de se produire.</span><span class="sxs-lookup"><span data-stu-id="b5c9d-106">Otherwise, collation conflicts can occur that might prevent code from executing.</span></span> <span data-ttu-id="b5c9d-107">Par exemple, lorsqu'une procédure stockée joint une table à une table temporaire, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] peut terminer le lot et retourner une erreur de conflit de classement si les classements de la base de données définie par l'utilisateur et de la base de données model sont différents.</span><span class="sxs-lookup"><span data-stu-id="b5c9d-107">For example, when a stored procedure joins one table to a temporary table, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] might end the batch and return a collation conflict error if the collations of the user-defined database and the model database are different.</span></span> <span data-ttu-id="b5c9d-108">Cela se produit car les tables temporaires sont créées dans tempdb, dont le classement repose sur celui de la base de données model.</span><span class="sxs-lookup"><span data-stu-id="b5c9d-108">This occurs because temporary tables are created in tempdb, which bases its collation on that of model.</span></span>  
  
 <span data-ttu-id="b5c9d-109">Si vous rencontrez des erreurs de conflit de classement, considérez l'une des solutions suivantes :</span><span class="sxs-lookup"><span data-stu-id="b5c9d-109">If you experience collation conflict errors, consider one of the following solutions:</span></span>  
  
-   <span data-ttu-id="b5c9d-110">Exportez les données de la base de données utilisateur et importez-les dans de nouvelles tables ayant le même classement que les bases de données MASTER et model.</span><span class="sxs-lookup"><span data-stu-id="b5c9d-110">Export the data from the user database and import it into new tables that have the same collation as the master and model databases.</span></span>  
  
-   <span data-ttu-id="b5c9d-111">Reconstruisez les bases de données système pour utiliser un classement qui correspond à celui de la base de données utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b5c9d-111">Rebuild the system databases to use a collation that matches the user database collation.</span></span> <span data-ttu-id="b5c9d-112">Pour plus d’informations sur la régénération des bases de données système, consultez [reconstruire des bases de données système](../relational-databases/databases/system-databases.md).</span><span class="sxs-lookup"><span data-stu-id="b5c9d-112">For more information about how to rebuild the system databases, see [Rebuild System Databases](../relational-databases/databases/system-databases.md).</span></span>  
  
-   <span data-ttu-id="b5c9d-113">Modifiez toute procédure stockée qui joint des tables utilisateur à des tables de la base de données tempdb pour créer les tables dans tempdb en utilisant le classement de la base de données utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b5c9d-113">Modify any stored procedures that join user tables to tables in tempdb to create the tables in tempdb by using the collation of the user database.</span></span> <span data-ttu-id="b5c9d-114">Pour ce faire, ajoutez la clause `COLLATE database_default` aux définitions de colonnes de la table temporaire, comme indiqué dans l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="b5c9d-114">To do this, add the `COLLATE database_default` clause to the column definitions of the temporary table, as shown in the following example:</span></span>  
  
    ```  
    CREATE TABLE #temp1 ( c1 int, c2 varchar(30) COLLATE database_default )  
    ```  
  
## <a name="for-more-information"></a><span data-ttu-id="b5c9d-115">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="b5c9d-115">For More Information</span></span>  
 [<span data-ttu-id="b5c9d-116">Définir ou modifier le classement de la base de données</span><span class="sxs-lookup"><span data-stu-id="b5c9d-116">Set or Change the Database Collation</span></span>](../relational-databases/collations/set-or-change-the-database-collation.md)  
  
 [<span data-ttu-id="b5c9d-117">Définir ou modifier le classement des colonnes</span><span class="sxs-lookup"><span data-stu-id="b5c9d-117">Set or Change the Column Collation</span></span>](../relational-databases/collations/set-or-change-the-column-collation.md)  
  
 [<span data-ttu-id="b5c9d-118">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b5c9d-118">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
 [<span data-ttu-id="b5c9d-119">COLLATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b5c9d-119">COLLATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/collations)  
  
 [<span data-ttu-id="b5c9d-120">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b5c9d-120">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
 [<span data-ttu-id="b5c9d-121">Article 325335 de la base de connaissances Microsoft</span><span class="sxs-lookup"><span data-stu-id="b5c9d-121">Microsoft Knowledge Base article 325335</span></span>](https://go.microsoft.com/fwlink/?linkid=117751)  
  
 [<span data-ttu-id="b5c9d-122">Procédure : installer SQL Server 2008 à partir de l'invite de commandes</span><span class="sxs-lookup"><span data-stu-id="b5c9d-122">How to: Install SQL Server 2008 from the Command Prompt</span></span>](https://go.microsoft.com/fwlink/?LinkId=81585)  
  
## <a name="see-also"></a><span data-ttu-id="b5c9d-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b5c9d-123">See Also</span></span>  
 [<span data-ttu-id="b5c9d-124">Contrôler et appliquer les bonnes pratiques à l’aide de la gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="b5c9d-124">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
