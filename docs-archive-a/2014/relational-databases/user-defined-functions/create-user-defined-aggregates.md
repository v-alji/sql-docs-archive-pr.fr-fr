---
title: Créer des agrégats définis par l’utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- aggregate functions [SQL Server], user-defined
- user-defined functions [CLR integration]
ms.assetid: c278b746-6323-4b32-b460-239915acc067
author: rothja
ms.author: jroth
ms.openlocfilehash: c91179cb194bbfb79e8e7a8476e9725877b88afa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708143"
---
# <a name="create-user-defined-aggregates"></a><span data-ttu-id="e353f-102">Créer des agrégats définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e353f-102">Create User-defined Aggregates</span></span>
  <span data-ttu-id="e353f-103">Vous pouvez créer un objet de base de données dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] programmé dans un assembly CLR.</span><span class="sxs-lookup"><span data-stu-id="e353f-103">You can create a database object inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is programmed in a CLR assembly.</span></span> <span data-ttu-id="e353f-104">Les objets de base de données qui peuvent tirer parti du modèle de programmation riche fourni par le CLR sont notamment les déclencheurs, les procédures stockées, les fonctions, les fonctions d'agrégation et les types.</span><span class="sxs-lookup"><span data-stu-id="e353f-104">Database objects that can leverage the rich programming model provided by the CLR include triggers, stored procedures, functions, aggregate functions, and types.</span></span>  
  
 <span data-ttu-id="e353f-105">Au même titre que les fonctions d'agrégation intégrées fournies dans [!INCLUDE[tsql](../../includes/tsql-md.md)], les fonctions d'agrégation définies par l'utilisateur réalisent un calcul sur un ensemble de valeurs et retournent une seule valeur.</span><span class="sxs-lookup"><span data-stu-id="e353f-105">Like the built-in aggregate functions provided in [!INCLUDE[tsql](../../includes/tsql-md.md)], user-defined aggregate functions perform a calculation on a set of values and return a single value.</span></span>  
  
 <span data-ttu-id="e353f-106">La création d'une fonction d'agrégation définie par l'utilisateur dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] suppose les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="e353f-106">Creating a user-defined aggregate function in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] involves the following steps:</span></span>  
  
-   <span data-ttu-id="e353f-107">Définissez la fonction d'agrégation définie par l'utilisateur en tant que classe dans un langage [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e353f-107">Define the user-defined aggregate function as a class in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework-supported language.</span></span> <span data-ttu-id="e353f-108">Pour plus d’informations sur la programmation d’agrégats définis par l’utilisateur dans le CLR, consultez [Agrégats CLR définis par l’utilisateur](../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md).</span><span class="sxs-lookup"><span data-stu-id="e353f-108">For more information about how to program user-defined aggregates in the CLR, see [CLR User-Defined Aggregates](../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md).</span></span> <span data-ttu-id="e353f-109">Compilez cette classe pour créer un assembly CLR à l'aide du compilateur de langage approprié.</span><span class="sxs-lookup"><span data-stu-id="e353f-109">Compile this class to build a CLR assembly using the appropriate language compiler.</span></span>  
  
-   <span data-ttu-id="e353f-110">Inscrivez l'assembly dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide de l'instruction CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="e353f-110">Register the assembly in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the CREATE ASSEMBLY statement.</span></span> <span data-ttu-id="e353f-111">Pour plus d’informations sur les assemblys dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez [Assemblys &#40;moteur de base de données&#41;](../clr-integration/assemblies-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="e353f-111">For more information about assemblies in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Assemblies &#40;Database Engine&#41;](../clr-integration/assemblies-database-engine.md).</span></span>  
  
-   <span data-ttu-id="e353f-112">Créez l'agrégat défini par l'utilisateur qui fait référence à l'assembly inscrit à l'aide de l'instruction CREATE AGGREGATE.</span><span class="sxs-lookup"><span data-stu-id="e353f-112">Create the user-defined aggregate that references the registered assembly using the CREATE AGGREGATE statement.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e353f-113">Le déploiement d’un projet SQL Server dans [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] a pour effet d’inscrire un assembly dans la base de données qui a été spécifiée pour le projet.</span><span class="sxs-lookup"><span data-stu-id="e353f-113">Deploying a SQL Server Project in [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] registers an assembly in the database that was specified for the project.</span></span> <span data-ttu-id="e353f-114">Le déploiement du projet crée aussi une agrégation définie par l'utilisateur dans la base de données pour toutes les définitions de classe annotées par l'attribut `SqlUserDefinedAggregate`.</span><span class="sxs-lookup"><span data-stu-id="e353f-114">Deploying the project also creates a user-defined aggregate in the database for all class definitions annotated with the `SqlUserDefinedAggregate` attribute.</span></span> <span data-ttu-id="e353f-115">Pour plus d’informations, consultez [Déploiement d’objets de base de données CLR](../clr-integration/deploying-clr-database-objects.md).</span><span class="sxs-lookup"><span data-stu-id="e353f-115">For more information, see [Deploying CLR Database Objects](../clr-integration/deploying-clr-database-objects.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e353f-116">La fonctionnalité d'exécution du code CLR par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="e353f-116">The ability of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to execute CLR code is off by default.</span></span> <span data-ttu-id="e353f-117">Vous pouvez créer, modifier et supprimer des objets de base de données qui font référence à des modules de code managé, mais ces références ne s’exécutent pas dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si l’option [clr enabled](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) n’est pas activée à l’aide de [sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e353f-117">You can create, alter and drop database objects that reference managed code modules, but these references will not execute in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unless the [clr enabled Option](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) is enabled using [sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql).</span></span>  
  
 <span data-ttu-id="e353f-118">**Pour créer, modifier ou supprimer un assembly**</span><span class="sxs-lookup"><span data-stu-id="e353f-118">**To create, modify, or drop an assembly**</span></span>  
  
-   [<span data-ttu-id="e353f-119">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e353f-119">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-assembly-transact-sql)  
  
-   [<span data-ttu-id="e353f-120">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e353f-120">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-assembly-transact-sql)  
  
-   [<span data-ttu-id="e353f-121">DROP ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e353f-121">DROP ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-assembly-transact-sql)  
  
 <span data-ttu-id="e353f-122">**Pour créer un agrégat défini par l'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="e353f-122">**To create a user-defined aggregate**</span></span>  
  
-   [<span data-ttu-id="e353f-123">CREATE AGGREGATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e353f-123">CREATE AGGREGATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-aggregate-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="e353f-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e353f-124">See Also</span></span>  
 [<span data-ttu-id="e353f-125">Concepts de programmation pour l’intégration du CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="e353f-125">Common Language Runtime &#40;CLR&#41; Integration Programming Concepts</span></span>](../clr-integration/common-language-runtime-clr-integration-programming-concepts.md)  
  
  
