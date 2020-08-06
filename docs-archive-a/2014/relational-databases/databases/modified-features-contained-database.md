---
title: Fonctionnalités modifiées (base de données autonome) | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- contained database, modifications to DBs
ms.assetid: a2942509-39a2-4903-b504-ae80a300a9de
author: stevestein
ms.author: sstein
ms.openlocfilehash: bc52821deeb879022881f838c61823b23c0c10c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709519"
---
# <a name="modified-features-contained-database"></a><span data-ttu-id="b5d57-102">Fonctionnalités modifiées (base de données autonome)</span><span class="sxs-lookup"><span data-stu-id="b5d57-102">Modified Features (Contained Database)</span></span>
  <span data-ttu-id="b5d57-103">Les fonctionnalités suivantes ont été modifiées pour être prises en charge par une base de données partiellement autonome.</span><span class="sxs-lookup"><span data-stu-id="b5d57-103">The following features have been modified to be supported by a partially contained database.</span></span> <span data-ttu-id="b5d57-104">Les fonctionnalités sont généralement modifiées de façon à ce qu'elles ne traversent pas la limite de base de données.</span><span class="sxs-lookup"><span data-stu-id="b5d57-104">Features are usually modified so they do not cross the database boundary.</span></span>  
  
 <span data-ttu-id="b5d57-105">Pour plus d’informations, consultez [Bases de données autonomes](contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="b5d57-105">For more information, see [Contained Databases](contained-databases.md).</span></span>  
  
## <a name="alter-database"></a><span data-ttu-id="b5d57-106">ALTER DATABASE</span><span class="sxs-lookup"><span data-stu-id="b5d57-106">ALTER DATABASE</span></span>  
  
### <a name="application-level"></a><span data-ttu-id="b5d57-107">Niveau de l'application</span><span class="sxs-lookup"><span data-stu-id="b5d57-107">Application Level</span></span>  
 <span data-ttu-id="b5d57-108">Lors de l'utilisation de l'instruction ALTER DATABASE à partir d'une base de données autonome, la syntaxe est différente de celle utilisée pour une base de données non autonome.</span><span class="sxs-lookup"><span data-stu-id="b5d57-108">When using the ALTER DATABASE statement from inside of a contained database, the syntax differs from that used for a non-contained database.</span></span> <span data-ttu-id="b5d57-109">Cette différence inclut des restrictions sur les éléments de l'instruction qui s'étendent au-delà de la base de données, au niveau de l'instance.</span><span class="sxs-lookup"><span data-stu-id="b5d57-109">This difference includes restrictions of elements of the statement that extend beyond the database to the instance.</span></span> <span data-ttu-id="b5d57-110">Pour plus d’informations, consultez [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b5d57-110">For more information, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
### <a name="instance-level"></a><span data-ttu-id="b5d57-111">Niveau de l'instance</span><span class="sxs-lookup"><span data-stu-id="b5d57-111">Instance Level</span></span>  
 <span data-ttu-id="b5d57-112">La syntaxe de l'instruction ALTER DATABASE en cas d'utilisation hors d'une base de données autonome diffère de celle utilisée pour les bases de données non autonomes.</span><span class="sxs-lookup"><span data-stu-id="b5d57-112">The syntax for the ALTER DATABASE when used outside of a contained database differs from that used for non-contained databases.</span></span> <span data-ttu-id="b5d57-113">Ces modifications empêchent de dépasser la limite de base de données.</span><span class="sxs-lookup"><span data-stu-id="b5d57-113">These changes prevent crossing the database boundary.</span></span> <span data-ttu-id="b5d57-114">Pour plus d’informations, consultez [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b5d57-114">For more information, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
## <a name="create-database"></a><span data-ttu-id="b5d57-115">CREATE DATABASE</span><span class="sxs-lookup"><span data-stu-id="b5d57-115">CREATE DATABASE</span></span>  
 <span data-ttu-id="b5d57-116">La syntaxe CREATE DATABASE pour une base de données autonome diffère de celle pour une base de données non autonome.</span><span class="sxs-lookup"><span data-stu-id="b5d57-116">The CREATE DATABASE syntax for a contained database differs from that for a non-contained database.</span></span> <span data-ttu-id="b5d57-117">Consultez [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) pour plus d’informations sur les nouvelles exigences et autorisations relatives à la syntaxe.</span><span class="sxs-lookup"><span data-stu-id="b5d57-117">See [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql)for information about new syntax requirements and allowances.</span></span>  
  
## <a name="temporary-tables"></a><span data-ttu-id="b5d57-118">Tables temporaires</span><span class="sxs-lookup"><span data-stu-id="b5d57-118">Temporary Tables</span></span>  
 <span data-ttu-id="b5d57-119">Les tables temporaires locales sont autorisées dans une base de données autonome, mais leur comportement est différent dans les bases de données non autonomes.</span><span class="sxs-lookup"><span data-stu-id="b5d57-119">Local temporary tables are permitted within a contained database, but their behavior differs from those in non-contained databases.</span></span> <span data-ttu-id="b5d57-120">Dans les bases de données sans relation contenant-contenu, les données de table temporaire sont classées selon le classement de **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="b5d57-120">In non-contained databases, temporary table data is collated in the collation of **tempdb**.</span></span> <span data-ttu-id="b5d57-121">Dans une base de données autonome, les données de la table temporaire sont classées selon le classement de cette base de données.</span><span class="sxs-lookup"><span data-stu-id="b5d57-121">In a contained database temporary table data is collated in the collation of the contained database.</span></span>  
  
 <span data-ttu-id="b5d57-122">Toutes les métadonnées associées aux tables temporaires (par exemple, les noms de table et de colonne, les index, etc.) figurent dans le classement de catalogue.</span><span class="sxs-lookup"><span data-stu-id="b5d57-122">All metadata associated with temporary tables (for example, table and column names, indexes, and so on) will be in the catalog collation.</span></span>  
  
 <span data-ttu-id="b5d57-123">Les contraintes nommées ne peuvent pas être utilisées dans les tables temporaires.</span><span class="sxs-lookup"><span data-stu-id="b5d57-123">Named constraints may not be used in temporary tables.</span></span>  
  
 <span data-ttu-id="b5d57-124">Les tables temporaires ne peuvent pas faire référence aux types définis par l'utilisateur, aux collections de schémas XML ou aux fonctions définies par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b5d57-124">Temporary tables may not refer to user-defined types, XML schema collections, or user-defined functions.</span></span>  
  
## <a name="collation"></a><span data-ttu-id="b5d57-125">Classement</span><span class="sxs-lookup"><span data-stu-id="b5d57-125">Collation</span></span>  
 <span data-ttu-id="b5d57-126">Dans le modèle de base de données non autonome, il existe trois types de classement distincts : classement de base de données, classement d’instance et classement tempdb.</span><span class="sxs-lookup"><span data-stu-id="b5d57-126">In the non-contained database model, there are three separate types of collation: Database collation, Instance collation, and tempdb collation.</span></span> <span data-ttu-id="b5d57-127">Les bases de données autonomes utilisent uniquement deux classements, le classement de base de données et le nouveau classement de catalogue.</span><span class="sxs-lookup"><span data-stu-id="b5d57-127">Contained databases use only two collations, database collation and the new catalog collation.</span></span> <span data-ttu-id="b5d57-128">Consultez [Classements de base de données autonome](contained-database-collations.md) pour plus d’informations sur le classement de bases de données autonomes.</span><span class="sxs-lookup"><span data-stu-id="b5d57-128">See [Contained Database Collations](contained-database-collations.md) for more details on contained database collation.</span></span>  
  
## <a name="user-options"></a><span data-ttu-id="b5d57-129">Options utilisateur</span><span class="sxs-lookup"><span data-stu-id="b5d57-129">User Options</span></span>  
 <span data-ttu-id="b5d57-130">Au moment d’activer les bases de données autonomes, l’option [user options](../../database-engine/configure-windows/configure-the-user-options-server-configuration-option.md) doit avoir la valeur 0 pour l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5d57-130">When enabling contained databases, the [user options Option](../../database-engine/configure-windows/configure-the-user-options-server-configuration-option.md) must be set to 0 for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5d57-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b5d57-131">See Also</span></span>  
 <span data-ttu-id="b5d57-132">[Classements de base de données autonome](contained-database-collations.md) </span><span class="sxs-lookup"><span data-stu-id="b5d57-132">[Contained Database Collations](contained-database-collations.md) </span></span>  
 [<span data-ttu-id="b5d57-133">Bases de données autonomes</span><span class="sxs-lookup"><span data-stu-id="b5d57-133">Contained Databases</span></span>](contained-databases.md)  
  
  
