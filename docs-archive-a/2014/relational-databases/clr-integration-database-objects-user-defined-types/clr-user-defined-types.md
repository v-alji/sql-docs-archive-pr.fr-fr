---
title: Types CLR définis par l’utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- validation [CLR integration]
- types [CLR integration]
- UserDefined serialization format [CLR integration]
- null values [CLR integration]
- serialization
- Native serialization format [CLR integration]
- databases [CLR integration]
- building database objects [CLR integration], user-defined types
- user-defined types [CLR integration]
- common language runtime [SQL Server], user-defined types
- UDTs [CLR integration]
- database objects [CLR integration], user-defined types
- turning on CLR functionality
- customizing UDT expression return types [CLR integration]
- UDTs [CLR integration], about UDTs
- comparing UDT values
- annotations [CLR integration]
- user-defined types [CLR integration], about UDTs
- variables [CLR integration]
- invoking UDT methods
- indexes [CLR integration]
ms.assetid: 27c4889b-c543-47a8-a630-ad06804f92df
author: rothja
ms.author: jroth
ms.openlocfilehash: e4e19323eeac9e0a1148924543f71aa7de5619b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614661"
---
# <a name="clr-user-defined-types"></a><span data-ttu-id="94ae2-102">Types CLR définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="94ae2-102">CLR User-Defined Types</span></span>
  <span data-ttu-id="94ae2-103">Dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vous pouvez créer des objets de base de données programmés à partir d'un assembly créé dans le CLR (Common Language Runtime) .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="94ae2-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gives you the ability to create database objects that are programmed against an assembly created in the.NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="94ae2-104">Les objets de base de données pouvant tirer parti du modèle de programmation évolué fourni par le CLR comprennent les déclencheurs, les procédures stockées, les fonctions, les fonctions d'agrégation et les types.</span><span class="sxs-lookup"><span data-stu-id="94ae2-104">Database objects that can take advantage of the rich programming model provided by the CLR include triggers, stored procedures, functions, aggregate functions, and types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="94ae2-105">La possibilité d’exécuter du code CLR est désactivée (OFF) par défaut dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="94ae2-105">The ability to execute CLR code is set to OFF by default in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="94ae2-106">Le CLR peut être activé à l’aide de la procédure stockée système **sp_configure** .</span><span class="sxs-lookup"><span data-stu-id="94ae2-106">The CLR can be enabled by using the **sp_configure** system stored procedure.</span></span>  
  
 <span data-ttu-id="94ae2-107">À partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , vous pouvez utiliser des types définis par l’utilisateur (UDT) pour étendre le système de type scalaire du serveur, permettant ainsi le stockage d’objets CLR dans une [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] base de données.</span><span class="sxs-lookup"><span data-stu-id="94ae2-107">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], you can use user-defined types (UDTs) to extend the scalar type system of the server, enabling storage of CLR objects in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="94ae2-108">Les types UDT peuvent contenir plusieurs éléments et avoir des comportements, ce qui les différencie des types de données alias traditionnels qui se composent d'un seul type de données système [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94ae2-108">UDTs can contain multiple elements and can have behaviors, differentiating them from the traditional alias data types which consist of a single [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system data type.</span></span>  
  
 <span data-ttu-id="94ae2-109">Les types UDT étant accessibles au système dans son ensemble, leur utilisation pour des types de données complexes peut nuire aux performances.</span><span class="sxs-lookup"><span data-stu-id="94ae2-109">Because UDTs are accessed by the system as a whole, their use for complex data types may negatively impact performance.</span></span> <span data-ttu-id="94ae2-110">Les données complexes sont généralement mieux modélisées au moyen de lignes et de tables traditionnelles.</span><span class="sxs-lookup"><span data-stu-id="94ae2-110">Complex data is generally best modeled using traditional rows and tables.</span></span> <span data-ttu-id="94ae2-111">Les types UDT dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont bien adaptés aux éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="94ae2-111">UDTs in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are well suited to the following:</span></span>  
  
-   <span data-ttu-id="94ae2-112">Date, heure, devise et types numériques étendus</span><span class="sxs-lookup"><span data-stu-id="94ae2-112">Date, time, currency, and extended numeric types</span></span>  
  
-   <span data-ttu-id="94ae2-113">Applications géographiques</span><span class="sxs-lookup"><span data-stu-id="94ae2-113">Geospatial applications</span></span>  
  
-   <span data-ttu-id="94ae2-114">Données encodées ou chiffrées</span><span class="sxs-lookup"><span data-stu-id="94ae2-114">Encoded or encrypted data</span></span>  
  
 <span data-ttu-id="94ae2-115">Le processus de développement de types UDT dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] comprend les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="94ae2-115">The process of developing UDTs in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consists of the following steps:</span></span>  
  
1.  <span data-ttu-id="94ae2-116">**Coder et générer l'assembly définissant le type UDT.**</span><span class="sxs-lookup"><span data-stu-id="94ae2-116">**Code and build the assembly that defines the UDT.**</span></span> <span data-ttu-id="94ae2-117">Les UDT sont définis à l’aide de l’un des langages pris en charge par the.NET Framework common language runtime (CLR) qui produisent du code vérifiable.</span><span class="sxs-lookup"><span data-stu-id="94ae2-117">UDTs are defined using any of the languages supported by the.NET Framework common language runtime (CLR) that produce verifiable code.</span></span> <span data-ttu-id="94ae2-118">notamment Visual C# et Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="94ae2-118">This includes Visual C# and Visual Basic .NET.</span></span> <span data-ttu-id="94ae2-119">Les données sont exposées en tant que champs et propriétés d'une classe ou d'une structure .NET Framework, et les comportements sont définis par des méthodes de la classe ou de la structure.</span><span class="sxs-lookup"><span data-stu-id="94ae2-119">The data is exposed as fields and properties of a .NET Framework class or structure, and behaviors are defined by methods of the class or structure.</span></span>  
  
2.  <span data-ttu-id="94ae2-120">**Inscrire l'assembly.**</span><span class="sxs-lookup"><span data-stu-id="94ae2-120">**Register the assembly.**</span></span> <span data-ttu-id="94ae2-121">Les types UDT peuvent être déployés par l'intermédiaire de l'interface utilisateur Visual Studio dans un projet de base de données, ou à l'aide de l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE ASSEMBLY, qui copie l'assembly contenant la classe ou la structure dans une base de données.</span><span class="sxs-lookup"><span data-stu-id="94ae2-121">UDTs can be deployed through the Visual Studio user interface in a database project, or by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE ASSEMBLY statement, which copies the assembly containing the class or structure into a database.</span></span>  
  
3.  <span data-ttu-id="94ae2-122">**Créer le type UDT dans SQL Server.**</span><span class="sxs-lookup"><span data-stu-id="94ae2-122">**Create the UDT in SQL Server.**</span></span> <span data-ttu-id="94ae2-123">Une fois qu'un assembly est chargé dans une base de données hôte, vous utilisez l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TYPE pour créer un type UDT et exposer les membres de la classe ou de la structure en tant que membres du type UDT.</span><span class="sxs-lookup"><span data-stu-id="94ae2-123">Once an assembly is loaded into a host database, you use the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TYPE statement to create a UDT and expose the members of the class or structure as members of the UDT.</span></span> <span data-ttu-id="94ae2-124">Les types UDT existent uniquement dans le contexte d'une base de données unique et, une fois inscrits, n'ont pas de dépendances vis-à-vis des fichiers externes à partir desquels ils ont été créés.</span><span class="sxs-lookup"><span data-stu-id="94ae2-124">UDTs exist only in the context of a single database, and, once registered, have no dependencies on the external files from which they were created.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="94ae2-125">Dans les versions antérieures à [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], les types UDT créés à partir d'assemblys .NET Framework n'étaient pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="94ae2-125">Before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], UDTs created from .NET Framework assemblies were not supported.</span></span> <span data-ttu-id="94ae2-126">Toutefois, vous pouvez toujours utiliser les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types de données d’alias à l’aide de **sp_addtype**.</span><span class="sxs-lookup"><span data-stu-id="94ae2-126">However, you can still use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alias data types by using **sp_addtype**.</span></span> <span data-ttu-id="94ae2-127">La syntaxe CREATE TYPE peut être utilisée pour créer à la fois des types de données définis par l'utilisateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] natifs et des types UDT.</span><span class="sxs-lookup"><span data-stu-id="94ae2-127">The CREATE TYPE syntax can be used for creating both native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user-defined data types and UDTs.</span></span>  
  
4.  <span data-ttu-id="94ae2-128">**Créer des tables, des variables ou des paramètres à l’aide de l’UDT** À partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , un type défini par l’utilisateur peut être utilisé comme définition de colonne d’une table, en tant que variable dans un [!INCLUDE[tsql](../../includes/tsql-md.md)] lot ou en tant qu’argument d’une [!INCLUDE[tsql](../../includes/tsql-md.md)] fonction ou d’une procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="94ae2-128">**Create tables, variables, or parameters using the UDT** Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], a user-defined type can be used as the column definition of a table, as a variable in a [!INCLUDE[tsql](../../includes/tsql-md.md)] batch, or as an argument of a [!INCLUDE[tsql](../../includes/tsql-md.md)] function or stored procedure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="94ae2-129">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="94ae2-129">In This Section</span></span>  
 [<span data-ttu-id="94ae2-130">Création d’un type défini par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="94ae2-130">Creating a User-Defined Type</span></span>](creating-user-defined-types.md)  
 <span data-ttu-id="94ae2-131">Décrit comment créer des types UDT.</span><span class="sxs-lookup"><span data-stu-id="94ae2-131">Describes how to create UDTs.</span></span>  
  
 [<span data-ttu-id="94ae2-132">Inscription des types définis par l'utilisateur dans SQL Server</span><span class="sxs-lookup"><span data-stu-id="94ae2-132">Registering User-Defined Types in SQL Server</span></span>](registering-user-defined-types-in-sql-server.md)  
 <span data-ttu-id="94ae2-133">Décrit comment inscrire et gérer des types UDT dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94ae2-133">Describes how to register and manage UDTs in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="94ae2-134">Utilisation de types définis par l’utilisateur dans SQL Server</span><span class="sxs-lookup"><span data-stu-id="94ae2-134">Working with User-Defined Types in SQL Server</span></span>](working-with-user-defined-types-in-sql-server.md)  
 <span data-ttu-id="94ae2-135">Décrit comment créer des requêtes à l'aide de types UDT.</span><span class="sxs-lookup"><span data-stu-id="94ae2-135">Describes how to create queries using UDTs.</span></span>  
  
 [<span data-ttu-id="94ae2-136">Accès aux types définis par l'utilisateur dans ADO.NET</span><span class="sxs-lookup"><span data-stu-id="94ae2-136">Accessing User-Defined Types in ADO.NET</span></span>](accessing-user-defined-types-in-ado-net.md)  
 <span data-ttu-id="94ae2-137">Décrit comment utiliser des types UDT à l'aide du fournisseur de données .NET Framework pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="94ae2-137">Describes how to work with UDTs using the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in ADO.NET.</span></span>  
  
  
