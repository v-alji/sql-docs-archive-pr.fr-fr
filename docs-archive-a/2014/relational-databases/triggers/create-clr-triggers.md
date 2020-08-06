---
title: Créer des déclencheurs CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- CRL triggers
- DML triggers, CLR triggers
- DDL triggers, CLR triggers
ms.assetid: 31f41703-134d-49fc-9850-76c297351c2c
author: rothja
ms.author: jroth
ms.openlocfilehash: 3afd841b4f1f9ca567a93c0a20c0a7609a5b45e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613904"
---
# <a name="create-clr-triggers"></a><span data-ttu-id="c3f13-102">Créer des déclencheurs CLR</span><span class="sxs-lookup"><span data-stu-id="c3f13-102">Create CLR Triggers</span></span>
  <span data-ttu-id="c3f13-103">Dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vous pouvez créer un objet de base de données programmée en fonction d’un assembly créé dans le CLR (Common Language Runtime) [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3f13-103">You can create a database object inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is programmed in an assembly created in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] common language runtime (CLR).</span></span> <span data-ttu-id="c3f13-104">Les objets de base de données qui peuvent tirer parti du modèle de programmation puissant qu'offre le CLR sont les déclencheurs DML, les déclencheurs DDL, les procédures stockées, les fonctions, les fonctions d'agrégation et les types.</span><span class="sxs-lookup"><span data-stu-id="c3f13-104">Database objects that can leverage the rich programming model provided by the CLR include DML triggers, DDL triggers, stored procedures, functions, aggregate functions, and types.</span></span>  
  
 <span data-ttu-id="c3f13-105">La création d'un déclencheur CLR (DML ou DDL) dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] implique les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="c3f13-105">Creating a CLR trigger (DML or DDL) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] involves the following steps:</span></span>  
  
-   <span data-ttu-id="c3f13-106">Définissez le déclencheur en tant que classe dans un langage .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c3f13-106">Define the trigger as a class in a .NET Framework-supported language.</span></span> <span data-ttu-id="c3f13-107">Pour plus d’informations sur la programmation de déclencheurs dans le CLR, consultez [Déclencheurs CLR](../../database-engine/dev-guide/clr-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="c3f13-107">For more information about how to program triggers in the CLR, see [CLR Triggers](../../database-engine/dev-guide/clr-triggers.md).</span></span> <span data-ttu-id="c3f13-108">Ensuite, compilez la classe pour créer un assembly dans le [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] à l'aide du compilateur du langage approprié.</span><span class="sxs-lookup"><span data-stu-id="c3f13-108">Then, compile the class to build an assembly in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] using the appropriate language compiler.</span></span>  
  
-   <span data-ttu-id="c3f13-109">Inscrivez l'assembly dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide de l'instruction CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="c3f13-109">Register the assembly in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the CREATE ASSEMBLY statement.</span></span> <span data-ttu-id="c3f13-110">Pour plus d’informations sur les assemblys dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez [Assemblys &#40;moteur de base de données&#41;](../clr-integration/assemblies-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="c3f13-110">For more information about assemblies in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Assemblies &#40;Database Engine&#41;](../clr-integration/assemblies-database-engine.md).</span></span>  
  
-   <span data-ttu-id="c3f13-111">Créez le déclencheur qui fait référence à l'assembly inscrit.</span><span class="sxs-lookup"><span data-stu-id="c3f13-111">Create the trigger that references the registered assembly.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3f13-112">Le déploiement d’un projet SQL Server dans [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] a pour effet d’inscrire un assembly dans la base de données qui a été spécifiée pour le projet.</span><span class="sxs-lookup"><span data-stu-id="c3f13-112">Deploying a SQL Server Project in [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] registers an assembly in the database that was specified for the project.</span></span> <span data-ttu-id="c3f13-113">Le déploiement du projet crée aussi les déclencheurs CLR dans la base de données pour toutes les méthodes annotées par l'attribut `SqlTrigger`.</span><span class="sxs-lookup"><span data-stu-id="c3f13-113">Deploying the project also creates CLR triggers in the database for all methods annotated with the `SqlTrigger` attribute.</span></span> <span data-ttu-id="c3f13-114">Pour plus d’informations, consultez [Déploiement d’objets de base de données CLR](../clr-integration/deploying-clr-database-objects.md).</span><span class="sxs-lookup"><span data-stu-id="c3f13-114">For more information, see [Deploying CLR Database Objects](../clr-integration/deploying-clr-database-objects.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3f13-115">La fonctionnalité d'exécution du code CLR par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="c3f13-115">The ability of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to execute CLR code is off by default.</span></span> <span data-ttu-id="c3f13-116">Vous pouvez créer, modifier et supprimer des objets de base de données qui font référence à des modules de code managé, mais ces références ne s’exécutent pas dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si l’option [CLR activé](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) n’est pas activée à l’aide de [sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c3f13-116">You can create, alter, and drop database objects that reference managed code modules, but these references will not execute in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unless the [clr enabled Option](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) is enabled using [sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql).</span></span>  
  
 <span data-ttu-id="c3f13-117">**Pour créer, modifier ou supprimer un assembly**</span><span class="sxs-lookup"><span data-stu-id="c3f13-117">**To create, modify, or drop an assembly**</span></span>  
  
-   [<span data-ttu-id="c3f13-118">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c3f13-118">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-assembly-transact-sql)  
  
-   [<span data-ttu-id="c3f13-119">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c3f13-119">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-assembly-transact-sql)  
  
-   [<span data-ttu-id="c3f13-120">DROP ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c3f13-120">DROP ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-assembly-transact-sql)  
  
 <span data-ttu-id="c3f13-121">**Pour créer un déclencheur CLR**</span><span class="sxs-lookup"><span data-stu-id="c3f13-121">**To create a CLR trigger**</span></span>  
  
-   [<span data-ttu-id="c3f13-122">CREATE TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c3f13-122">CREATE TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-trigger-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="c3f13-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c3f13-123">See Also</span></span>  
 <span data-ttu-id="c3f13-124">[Déclencheurs DML](dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="c3f13-124">[DML Triggers](dml-triggers.md) </span></span>  
 <span data-ttu-id="c3f13-125">[Concepts de programmation pour l’intégration du CLR &#40;Common Language Runtime&#41;](../clr-integration/common-language-runtime-clr-integration-programming-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="c3f13-125">[Common Language Runtime &#40;CLR&#41; Integration Programming Concepts](../clr-integration/common-language-runtime-clr-integration-programming-concepts.md) </span></span>  
 [<span data-ttu-id="c3f13-126">Accès aux données à partir d'objets de base de données CLR</span><span class="sxs-lookup"><span data-stu-id="c3f13-126">Data Access from CLR Database Objects</span></span>](../clr-integration/data-access/data-access-from-clr-database-objects.md)  
  
  
