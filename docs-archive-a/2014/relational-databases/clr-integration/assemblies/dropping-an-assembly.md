---
title: Suppression d’un assembly | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- removing assemblies
- DROP ASSEMBLY statement
- assemblies [CLR integration], removing
- dropping assemblies
ms.assetid: 03481034-dc91-4488-ab24-ba44243e2690
author: rothja
ms.author: jroth
ms.openlocfilehash: 45d02cbb57459a4c1c11330446021c32dc897353
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704163"
---
# <a name="dropping-an-assembly"></a><span data-ttu-id="bd2ff-102">Suppression d'un assembly</span><span class="sxs-lookup"><span data-stu-id="bd2ff-102">Dropping an Assembly</span></span>
  <span data-ttu-id="bd2ff-103">Les assemblys inscrits dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à l'aide de l'instruction CREATE ASSEMBLY peuvent être supprimés lorsque les fonctionnalités qu'ils fournissent ne sont plus nécessaires.</span><span class="sxs-lookup"><span data-stu-id="bd2ff-103">Assemblies that have been registered in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] using the CREATE ASSEMBLY statement can be deleted, or dropped, when the functionality they provide is no longer needed.</span></span> <span data-ttu-id="bd2ff-104">La suppression d'un assembly supprime de la base de données l'assembly spécifié et tous les fichiers associés, tels que les fichiers de débogage.</span><span class="sxs-lookup"><span data-stu-id="bd2ff-104">Dropping an assembly removes the assembly and all of its associated files, such as debug files, from the database.</span></span> <span data-ttu-id="bd2ff-105">Pour supprimer un assembly, utilisez l'instruction DROP ASSEMBLY avec la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="bd2ff-105">To drop an assembly, use the DROP ASSEMBLY statement with the following syntax:</span></span>  
  
```  
DROP ASSEMBLY MyDotNETAssembly  
```  
  
 <span data-ttu-id="bd2ff-106">DROP ASSEMBLY n'interfère pas avec le code en cours d'exécution qui référence l'assembly, mais après l'exécution de DROP ASSEMBLY, toute tentative d'appel du code de l'assembly échoue.</span><span class="sxs-lookup"><span data-stu-id="bd2ff-106">DROP ASSEMBLY does not interfere with any code referencing the assembly that is currently running, but after DROP ASSEMBLY executes, any attempts to invoke the assembly code fail.</span></span>  
  
 <span data-ttu-id="bd2ff-107">DROP ASSEMBLY retourne une erreur si l'assembly est référencé par un assembly existant de la base de données ou s'il est utilisé par des fonctions CLR (Common Language Runtime), des procédures, des déclencheurs, des types définis par l'utilisateur (UDT) ou des agrégats définis par l'utilisateur (UDA) dans la base de données active.</span><span class="sxs-lookup"><span data-stu-id="bd2ff-107">DROP ASSEMBLY returns an error if the assembly is referenced by another assembly that exists in the database, or if it is used by common language runtime (CLR) functions, procedures, triggers, user-defined types (UDTs), or user-defined aggregates (UDAs) in the current database.</span></span> <span data-ttu-id="bd2ff-108">En premier lieu, utilisez les instructions DROP AGGREGATE, DROP FUNCTION, DROP PROCEDURE, DROP TRIGGER et DROP TYPE pour supprimer tout objet de base de données managé contenu dans l'assembly.</span><span class="sxs-lookup"><span data-stu-id="bd2ff-108">First use the DROP AGGREGATE, DROP FUNCTION, DROP PROCEDURE, DROP TRIGGER, and DROP TYPE statements to delete any managed database objects contained in the assembly.</span></span>  
  
## <a name="removing-a-udt-from-the-database"></a><span data-ttu-id="bd2ff-109">Suppression d'un UDT de la base de données</span><span class="sxs-lookup"><span data-stu-id="bd2ff-109">Removing a UDT from the Database</span></span>  
 <span data-ttu-id="bd2ff-110">L'instruction DROP TYPE supprime un UDT de la base de données active.</span><span class="sxs-lookup"><span data-stu-id="bd2ff-110">The DROP TYPE statement removes a UDT from the current database.</span></span> <span data-ttu-id="bd2ff-111">Une fois un UDT supprimé, vous pouvez utiliser l'instruction DROP ASSEMBLY pour supprimer l'assembly de la base de données.</span><span class="sxs-lookup"><span data-stu-id="bd2ff-111">Once a UDT is dropped, you can use the DROP ASSEMBLY statement to drop the assembly from the database.</span></span>  
  
 <span data-ttu-id="bd2ff-112">L'instruction DROP TYPE échoue si les objets dépendent du type UDT, comme dans les situations suivantes :</span><span class="sxs-lookup"><span data-stu-id="bd2ff-112">The DROP TYPE statement fails if objects depend on the UDT, as in the following situations:</span></span>  
  
-   <span data-ttu-id="bd2ff-113">Des tables de la base de données contiennent des colonnes définies à l'aide de l'UDT.</span><span class="sxs-lookup"><span data-stu-id="bd2ff-113">Tables in the database that contain columns defined using the UDT.</span></span>  
  
-   <span data-ttu-id="bd2ff-114">Des fonctions, procédures stockées ou déclencheurs créés dans la base de données avec la clause WITH SCHEMABINDING utilisent des variables ou des paramètres de l'UDT.</span><span class="sxs-lookup"><span data-stu-id="bd2ff-114">Functions, stored procedures, or triggers that use variables or parameters of the UDT, created in the database with the WITH SCHEMABINDING clause.</span></span>  
  
### <a name="finding-udt-dependencies"></a><span data-ttu-id="bd2ff-115">Recherche des dépendances d'un UDT</span><span class="sxs-lookup"><span data-stu-id="bd2ff-115">Finding UDT Dependencies</span></span>  
 <span data-ttu-id="bd2ff-116">Vous devez commencer par supprimer tous les objets dépendants, puis exécuter l'instruction DROP TYPE.</span><span class="sxs-lookup"><span data-stu-id="bd2ff-116">You must first drop all dependent objects, and then execute the DROP TYPE statement.</span></span> <span data-ttu-id="bd2ff-117">La [!INCLUDE[tsql](../../../includes/tsql-md.md)] requête suivante localise toutes les colonnes et tous les paramètres qui utilisent un UDT dans la base de données **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="bd2ff-117">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] query locates all of the columns and parameters that use a UDT in the **AdventureWorks** database.</span></span>  
  
```  
USE Adventureworks;  
SELECT o.name AS major_name, o.type_desc AS major_type_desc  
     , c.name AS minor_name, c.type_desc AS minor_type_desc  
     , at.assembly_class  
  FROM (  
        SELECT object_id, name, user_type_id, 'SQL_COLUMN' AS type_desc  
          FROM sys.columns  
     UNION ALL  
        SELECT object_id, name, user_type_id, 'SQL_PROCEDURE_PARAMETER'  
          FROM sys.parameters  
     ) AS c  
  JOIN sys.objects AS o  
    ON o.object_id = c.object_id  
  JOIN sys.assembly_types AS at  
    ON at.user_type_id = c.user_type_id;   
```  
  
## <a name="see-also"></a><span data-ttu-id="bd2ff-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bd2ff-118">See Also</span></span>  
 <span data-ttu-id="bd2ff-119">[Gestion des assemblys d’intégration du CLR](managing-clr-integration-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="bd2ff-119">[Managing CLR Integration Assemblies](managing-clr-integration-assemblies.md) </span></span>  
 <span data-ttu-id="bd2ff-120">[Modification d’un assembly](altering-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="bd2ff-120">[Altering an Assembly](altering-an-assembly.md) </span></span>  
 <span data-ttu-id="bd2ff-121">[Création d’un assembly](creating-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="bd2ff-121">[Creating an Assembly](creating-an-assembly.md) </span></span>  
 <span data-ttu-id="bd2ff-122">[DROP AGGREGATe &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-aggregate-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bd2ff-122">[DROP AGGREGATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-aggregate-transact-sql) </span></span>  
 <span data-ttu-id="bd2ff-123">[DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bd2ff-123">[DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql) </span></span>  
 <span data-ttu-id="bd2ff-124">[SUPPRIMER la procédure &#40;&#41;Transact-SQL](/sql/t-sql/statements/drop-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bd2ff-124">[DROP PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-procedure-transact-sql) </span></span>  
 <span data-ttu-id="bd2ff-125">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bd2ff-125">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 [<span data-ttu-id="bd2ff-126">DROP TYPE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bd2ff-126">DROP TYPE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-type-transact-sql)  
  
  
