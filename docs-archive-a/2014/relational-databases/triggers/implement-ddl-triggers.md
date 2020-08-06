---
title: Implémenter des déclencheurs DDL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- DDL triggers, implementing
ms.assetid: f44e5340-1d18-40e9-828e-0ffcca091ae3
author: rothja
ms.author: jroth
ms.openlocfilehash: 110e69aca31df75d4b4d7a732de5c58556bd3e24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613876"
---
# <a name="implement-ddl-triggers"></a><span data-ttu-id="4e614-102">Implémenter des déclencheurs DDL</span><span class="sxs-lookup"><span data-stu-id="4e614-102">Implement DDL Triggers</span></span>
  <span data-ttu-id="4e614-103">Cette rubrique fournit des informations pour vous aider à créer, modifier, désactiver ou supprimer des déclencheurs DDL.</span><span class="sxs-lookup"><span data-stu-id="4e614-103">This topic provides information to help you create DDL triggers, modify DDL triggers, and disable or drop DDL triggers.</span></span>  
  
## <a name="creating-ddl-triggers"></a><span data-ttu-id="4e614-104">Création de déclencheurs DDL</span><span class="sxs-lookup"><span data-stu-id="4e614-104">Creating DDL Triggers</span></span>  
 <span data-ttu-id="4e614-105">Les déclencheurs DDL sont créés à l'aide de l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TRIGGER pour les déclencheurs DDL.</span><span class="sxs-lookup"><span data-stu-id="4e614-105">DDL triggers are created by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TRIGGER statement for DDL triggers.</span></span>  
  
 <span data-ttu-id="4e614-106">**Pour créer un déclencheur DDL**</span><span class="sxs-lookup"><span data-stu-id="4e614-106">**To create a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="4e614-107">CREATE TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4e614-107">CREATE TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-trigger-transact-sql)  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4e614-108">La fonctionnalité de renvoi des jeux de résultats à partir de déclencheurs sera éliminée dans une version ultérieure de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e614-108">The ability to return result sets from triggers will be removed in a future version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4e614-109">Les déclencheurs qui renvoient des jeux de résultats peuvent provoquer un comportement inattendu des applications qui ne sont pas conçues pour interagir avec eux.</span><span class="sxs-lookup"><span data-stu-id="4e614-109">Triggers that return result sets may cause unexpected behavior in applications that are not designed to work with them.</span></span> <span data-ttu-id="4e614-110">Évitez de renvoyer des jeux de résultats provenant de déclencheurs dans un nouveau travail de développement et prévoyez la modification des applications qui y recourent actuellement.</span><span class="sxs-lookup"><span data-stu-id="4e614-110">Avoid returning result sets from triggers in new development work, and plan to modify applications that currently do this.</span></span> <span data-ttu-id="4e614-111">Pour empêcher les déclencheurs de retourner des jeux de résultats dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], définissez l’option d’ [interdiction des résultats des déclencheurs](../../database-engine/configure-windows/disallow-results-from-triggers-server-configuration-option.md) sur 1.</span><span class="sxs-lookup"><span data-stu-id="4e614-111">To prevent triggers from returning result sets in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], set the [disallow results from triggers Option](../../database-engine/configure-windows/disallow-results-from-triggers-server-configuration-option.md) to 1.</span></span> <span data-ttu-id="4e614-112">Le paramètre par défaut de cette option sera 1 dans une version ultérieure de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e614-112">The default setting of this option will be 1 in a future version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="modifying-ddl-triggers"></a><span data-ttu-id="4e614-113">Modification de déclencheurs DDL</span><span class="sxs-lookup"><span data-stu-id="4e614-113">Modifying DDL Triggers</span></span>  
 <span data-ttu-id="4e614-114">Si vous devez modifier la définition d'un déclencheur DDL, vous pouvez soit l'annuler, puis le recréer, soit redéfinir le déclencheur existant en une seule opération.</span><span class="sxs-lookup"><span data-stu-id="4e614-114">If you have to modify the definition of a DDL trigger, you can either drop and re-create the trigger or redefine the existing trigger in a single step.</span></span>  
  
 <span data-ttu-id="4e614-115">Si vous changez le nom d'un objet référencé par un déclencheur DDL, vous devez modifier le déclencheur pour que sa définition se réfère au nouveau nom de l'objet.</span><span class="sxs-lookup"><span data-stu-id="4e614-115">If you change the name of an object that is referenced by a DDL trigger, you must modify the trigger so that its text reflects the new name.</span></span> <span data-ttu-id="4e614-116">Par conséquent, avant de renommer un objet, affichez les dépendances de l'objet pour savoir si des déclencheurs peuvent être concernés par la modification projetée.</span><span class="sxs-lookup"><span data-stu-id="4e614-116">Therefore, before renaming an object, display the dependencies of the object first to determine whether any triggers are affected by the proposed change.</span></span>  
  
 <span data-ttu-id="4e614-117">Un déclencheur peut aussi être modifié pour en chiffrer la définition.</span><span class="sxs-lookup"><span data-stu-id="4e614-117">A trigger can also be modified to encrypt its definition.</span></span>  
  
 <span data-ttu-id="4e614-118">**Pour modifier un déclencheur**</span><span class="sxs-lookup"><span data-stu-id="4e614-118">**To modify a trigger**</span></span>  
  
-   [<span data-ttu-id="4e614-119">ALTER TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4e614-119">ALTER TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-trigger-transact-sql)  
  
 <span data-ttu-id="4e614-120">**Pour afficher les dépendances d'un déclencheur**</span><span class="sxs-lookup"><span data-stu-id="4e614-120">**To view the dependencies of a trigger**</span></span>  
  
-   [<span data-ttu-id="4e614-121">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4e614-121">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
-   [<span data-ttu-id="4e614-122">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4e614-122">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
-   [<span data-ttu-id="4e614-123">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4e614-123">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql)  
  
## <a name="disabling-and-dropping-ddl-triggers"></a><span data-ttu-id="4e614-124">Désactivation et suppression de déclencheurs DDL</span><span class="sxs-lookup"><span data-stu-id="4e614-124">Disabling and Dropping DDL Triggers</span></span>  
 <span data-ttu-id="4e614-125">Vous pouvez désactiver ou supprimer un déclencheur DDL s'il ne vous est plus utile.</span><span class="sxs-lookup"><span data-stu-id="4e614-125">When a DDL trigger is no longer needed, you can disable it or delete it.</span></span>  
  
 <span data-ttu-id="4e614-126">La désactivation d'un déclencheur DDL n'entraîne pas sa suppression.</span><span class="sxs-lookup"><span data-stu-id="4e614-126">Disabling a DDL trigger does not drop it.</span></span> <span data-ttu-id="4e614-127">Le déclencheur existe toujours en tant qu'objet dans la base de données actuelle.</span><span class="sxs-lookup"><span data-stu-id="4e614-127">The trigger still exists as an object in the current database.</span></span> <span data-ttu-id="4e614-128">Cependant, il ne se déclenchera pas lorsque des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] sur lesquelles il a été programmé seront exécutées.</span><span class="sxs-lookup"><span data-stu-id="4e614-128">However, the trigger will not fire when any [!INCLUDE[tsql](../../includes/tsql-md.md)] statements on which it was programmed are run.</span></span> <span data-ttu-id="4e614-129">Tout déclencheur DDL désactivé peut être réactivé.</span><span class="sxs-lookup"><span data-stu-id="4e614-129">DDL triggers that are disabled can be reenabled.</span></span> <span data-ttu-id="4e614-130">Quand un déclencheur est réactivé, il se déclenche de la même manière que lors de sa création.</span><span class="sxs-lookup"><span data-stu-id="4e614-130">Enabling a DDL trigger causes it to fire in the same way the trigger did when it was originally created.</span></span> <span data-ttu-id="4e614-131">Les déclencheurs sont activés par défaut au moment de leur création.</span><span class="sxs-lookup"><span data-stu-id="4e614-131">When DDL triggers are created, they are enabled by default.</span></span>  
  
 <span data-ttu-id="4e614-132">La suppression d'un déclencheur DDL entraîne sa suppression définitive de la base de données actuelle.</span><span class="sxs-lookup"><span data-stu-id="4e614-132">When a DDL trigger is deleted, it is dropped from the current database.</span></span> <span data-ttu-id="4e614-133">Les objets ou données faisant partie de la portée du déclencheur DDL ne sont pas affectés.</span><span class="sxs-lookup"><span data-stu-id="4e614-133">Any objects or data upon which the DDL trigger is scoped are not affected.</span></span>  
  
 <span data-ttu-id="4e614-134">**Pour désactiver un déclencheur DDL**</span><span class="sxs-lookup"><span data-stu-id="4e614-134">**To disable a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="4e614-135">DISABLE TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4e614-135">DISABLE TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/disable-trigger-transact-sql)  
  
-   [<span data-ttu-id="4e614-136">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4e614-136">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
 <span data-ttu-id="4e614-137">**Pour activer un déclencheur DDL**</span><span class="sxs-lookup"><span data-stu-id="4e614-137">**To enable a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="4e614-138">ENABLE TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4e614-138">ENABLE TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/enable-trigger-transact-sql)  
  
-   [<span data-ttu-id="4e614-139">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4e614-139">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
 <span data-ttu-id="4e614-140">**Pour supprimer un déclencheur DDL**</span><span class="sxs-lookup"><span data-stu-id="4e614-140">**To delete a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="4e614-141">DROP TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4e614-141">DROP TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-trigger-transact-sql)  
  
  
