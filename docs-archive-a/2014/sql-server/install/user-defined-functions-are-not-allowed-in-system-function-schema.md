---
title: Les fonctions définies par l’utilisateur ne sont pas autorisées dans system_function_schema | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- system functions [SQL Server]
- user-defined functions [SQL Server], system
ms.assetid: 3cb54053-ef65-4558-ae96-8686b6b22f4f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7242f9fda74288a2b7354ac0550ff4966e05c555
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710120"
---
# <a name="user-defined-functions-are-not-allowed-in-system_function_schema"></a><span data-ttu-id="a09a0-102">Les fonctions définies par l'utilisateur ne sont pas autorisées dans system_function_schema</span><span class="sxs-lookup"><span data-stu-id="a09a0-102">User-defined functions are not allowed in system_function_schema</span></span>
  <span data-ttu-id="a09a0-103">Le conseiller de mise à niveau a détecté des fonctions définies par l’utilisateur qui sont détenues par l’utilisateur **system_function_schema**non documenté.</span><span class="sxs-lookup"><span data-stu-id="a09a0-103">The Upgrade Advisor detected user-defined functions that are owned by the undocumented user **system_function_schema**.</span></span> <span data-ttu-id="a09a0-104">Vous ne pouvez pas créer une fonction système définie par l'utilisateur en spécifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a09a0-104">You cannot create a user-defined system function by specifying this user.</span></span> <span data-ttu-id="a09a0-105">Le nom d’utilisateur **system_function_schema** n’existe pas et l’ID d’utilisateur associé à ce nom (UID = 4) est réservé au schéma **sys** et est réservé à un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="a09a0-105">The **system_function_schema** user name does not exist, and the user ID that is associated with this name (UID = 4) is reserved for the **sys** schema and is restricted to internal use only.</span></span>  
  
## <a name="component"></a><span data-ttu-id="a09a0-106">Composant</span><span class="sxs-lookup"><span data-stu-id="a09a0-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="a09a0-107">Description</span><span class="sxs-lookup"><span data-stu-id="a09a0-107">Description</span></span>  
 <span data-ttu-id="a09a0-108">Le stockage et l'accès des objets système ont été modifiés comme suit :</span><span class="sxs-lookup"><span data-stu-id="a09a0-108">System object storage and access has changed in the following ways:</span></span>  
  
-   <span data-ttu-id="a09a0-109">Les objets système sont stockés dans la base de données de **ressources** en lecture seule et les mises à jour directes des objets système ne sont pas autorisées.</span><span class="sxs-lookup"><span data-stu-id="a09a0-109">System objects are stored in the read-only **Resource** database, and direct system object updates are not permitted.</span></span>  
  
     <span data-ttu-id="a09a0-110">Les objets système apparaissent logiquement dans le schéma **sys** de chaque base de données.</span><span class="sxs-lookup"><span data-stu-id="a09a0-110">System objects logically appear in the **sys** schema of every database.</span></span> <span data-ttu-id="a09a0-111">Il est donc toujours possible d'appeler des fonctions système à partir de n'importe quelle base de données en spécifiant un nom de fonction en une seule partie.</span><span class="sxs-lookup"><span data-stu-id="a09a0-111">This maintains the ability to invoke system functions from any database by specifying a one-part function name.</span></span> <span data-ttu-id="a09a0-112">Par exemple, l'instruction `SELECT * FROM fn_helpcollations()` peut être exécutée à partir de n'importe quelle base de données.</span><span class="sxs-lookup"><span data-stu-id="a09a0-112">For example, the statement `SELECT * FROM fn_helpcollations()` can be run from any database.</span></span>  
  
-   <span data-ttu-id="a09a0-113">L’utilisateur **system_function_schema** non documenté a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="a09a0-113">The undocumented user **system_function_schema** has been removed.</span></span>  
  
-   <span data-ttu-id="a09a0-114">L’ID d’utilisateur associé à **system_function_schema** (UID = 4) est réservé au schéma **sys** et est limité à un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="a09a0-114">The user ID associated with **system_function_schema** (UID = 4) is reserved for the **sys** schema and is restricted to internal use only.</span></span>  
  
 <span data-ttu-id="a09a0-115">Ces modifications ont l'effet suivant sur les fonctions système définies par l'utilisateur :</span><span class="sxs-lookup"><span data-stu-id="a09a0-115">These changes have the following effect on user-defined system functions:</span></span>  
  
-   <span data-ttu-id="a09a0-116">Les instructions DDL (Data Definition Language) qui référencent **system_function_schema** échouent.</span><span class="sxs-lookup"><span data-stu-id="a09a0-116">Data Definition Language (DDL) statements that reference **system_function_schema** will fail.</span></span> <span data-ttu-id="a09a0-117">Par exemple, l’instruction `CREATE FUNCTION system` _ `function` \_ `schema.fn` \_ `MySystemFunction` ... ne fonctionnera pas.</span><span class="sxs-lookup"><span data-stu-id="a09a0-117">For example, the statement `CREATE FUNCTION system`_`function`\_`schema.fn`\_`MySystemFunction` ... will not succeed.</span></span>  
  
-   <span data-ttu-id="a09a0-118">Après la mise à niveau vers [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] , les objets existants appartenant à **system_function_schema** sont contenus uniquement dans le schéma **sys** de la base de données **Master** .</span><span class="sxs-lookup"><span data-stu-id="a09a0-118">After you upgrade to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], existing objects that are owned by **system_function_schema** are contained only in the **sys** schema of the **master** database.</span></span> <span data-ttu-id="a09a0-119">Étant donné que les objets système ne peuvent pas être modifiés, ces fonctions ne peuvent jamais être modifiées ou supprimées de la base de données **Master** .</span><span class="sxs-lookup"><span data-stu-id="a09a0-119">Because system objects cannot be modified, these functions can never be changed or dropped from the **master** database.</span></span> <span data-ttu-id="a09a0-120">En outre, il est impossible d'appeler ces fonctions à partir d'autres bases de données en spécifiant uniquement un nom de fonction en une seule partie.</span><span class="sxs-lookup"><span data-stu-id="a09a0-120">Additionally, these functions cannot be invoked from other databases by specifying only a one-part function name.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="a09a0-121">Action corrective</span><span class="sxs-lookup"><span data-stu-id="a09a0-121">Corrective Action</span></span>  
 <span data-ttu-id="a09a0-122">Avant de procéder à la mise à niveau, effectuez les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="a09a0-122">Before you upgrade , complete the following tasks:</span></span>  
  
1.  <span data-ttu-id="a09a0-123">Modifiez la propriété des fonctions définies par l’utilisateur existantes en **dbo** à l’aide de la procédure stockée système **sp_changeobjectowner** .</span><span class="sxs-lookup"><span data-stu-id="a09a0-123">Change the ownership of existing user-defined functions to **dbo** by using the **sp_changeobjectowner** system stored procedure.</span></span>  
  
2.  <span data-ttu-id="a09a0-124">Vous pouvez renommer la fonction de manière à ce que son nom ne comporte pas le préfixe 'fn_'.</span><span class="sxs-lookup"><span data-stu-id="a09a0-124">Consider renaming the function so that is does not use the prefix 'fn_'.</span></span> <span data-ttu-id="a09a0-125">Cela évitera d'éventuels conflits de noms avec des fonctions système actuelles ou futures.</span><span class="sxs-lookup"><span data-stu-id="a09a0-125">This will avoid potential name conflicts with current or future system functions.</span></span>  
  
3.  <span data-ttu-id="a09a0-126">Ajoutez une copie des fonctions modifiées dans chaque base de données qui les utilise.</span><span class="sxs-lookup"><span data-stu-id="a09a0-126">Add a copy of the modified functions in every database that uses them.</span></span>  
  
4.  <span data-ttu-id="a09a0-127">Remplacez les références à **system_function_schema** par **dbo** dans tous les scripts qui contiennent des instructions DDL de fonction définie par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a09a0-127">Replace references to **system_function_schema** with **dbo** in all scripts that contain user-defined function DDL statements.</span></span>  
  
5.  <span data-ttu-id="a09a0-128">Modifiez les scripts qui appellent ces fonctions pour utiliser le nom en deux parties dbo **.** _function_name_, ou le nom en trois parties _database_name_**.** dbo. *function_name*.</span><span class="sxs-lookup"><span data-stu-id="a09a0-128">Modify scripts that invoke these functions to use either the two-part name dbo **.**_function_name_, or the three-part name _database_name_**.** dbo.*function_name*.</span></span>  
  
 <span data-ttu-id="a09a0-129">Pour plus d'informations, consultez les rubriques suivantes dans la documentation en ligne de SQL Server :</span><span class="sxs-lookup"><span data-stu-id="a09a0-129">For more information, see the following topics in SQL Server Books Online:</span></span>  
  
-   <span data-ttu-id="a09a0-130">« sp_changeobjectowner »</span><span class="sxs-lookup"><span data-stu-id="a09a0-130">"sp_changeobjectowner"</span></span>  
  
-   <span data-ttu-id="a09a0-131">« Séparation du schéma et de l'utilisateur »</span><span class="sxs-lookup"><span data-stu-id="a09a0-131">"User-schema Separation"</span></span>  
  
-   <span data-ttu-id="a09a0-132">« Base de données Resource »</span><span class="sxs-lookup"><span data-stu-id="a09a0-132">"Resource Database"</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a09a0-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a09a0-133">See Also</span></span>  
 <span data-ttu-id="a09a0-134">[Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;](sql-server-2014-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="a09a0-134">[SQL Server 2014 Upgrade Advisor &#91;new&#93;](sql-server-2014-upgrade-advisor.md) </span></span>  
 <span data-ttu-id="a09a0-135">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="a09a0-135">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 <span data-ttu-id="a09a0-136">[Supprimer les instructions qui modifient les objets système](../../../2014/sql-server/install/remove-statements-that-modify-system-objects.md) </span><span class="sxs-lookup"><span data-stu-id="a09a0-136">[Remove statements that modify system objects](../../../2014/sql-server/install/remove-statements-that-modify-system-objects.md) </span></span>  
 [<span data-ttu-id="a09a0-137">Supprimer les instructions qui suppriment des objets système</span><span class="sxs-lookup"><span data-stu-id="a09a0-137">Remove statements that drop system objects</span></span>](../../../2014/sql-server/install/remove-statements-that-drop-system-objects.md)  
  
  
