---
title: Définition des tables et des colonnes UDT | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- user-defined types [CLR integration], columns
- UDTs [CLR integration], columns
- columns [CLR integration]
- user-defined types [CLR integration], tables
- tables [CLR integration]
- UDTs [CLR integration], tables
- UDTs [CLR integration], indexes
- user-defined types [CLR integration], indexes
- indexes [CLR integration]
ms.assetid: aea495f4-ce26-4952-b019-38f012625f3f
author: rothja
ms.author: jroth
ms.openlocfilehash: aa9596629ed8b4877b1793fa0c56956c52989499
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615166"
---
# <a name="defining-udt-tables-and-columns"></a><span data-ttu-id="2ef30-102">Définition de tables et de colonnes UDT</span><span class="sxs-lookup"><span data-stu-id="2ef30-102">Defining UDT Tables and Columns</span></span>
  <span data-ttu-id="2ef30-103">Une fois que l’assembly contenant la définition de type défini par l’utilisateur (UDT) a été enregistré dans une [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] base de données, il peut être utilisé dans une définition de colonne.</span><span class="sxs-lookup"><span data-stu-id="2ef30-103">Once the assembly containing the user-defined type (UDT) definition has been registered in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, it can be used in a column definition.</span></span>  
  
## <a name="creating-tables-with-udts"></a><span data-ttu-id="2ef30-104">Création de tables avec UDT</span><span class="sxs-lookup"><span data-stu-id="2ef30-104">Creating Tables with UDTs</span></span>  
 <span data-ttu-id="2ef30-105">Il n'existe aucune syntaxe particulière pour la création d'une colonne UDT dans une table.</span><span class="sxs-lookup"><span data-stu-id="2ef30-105">There is no special syntax for creating a UDT column in a table.</span></span> <span data-ttu-id="2ef30-106">Vous pouvez utiliser le nom de l'UDT dans une définition de colonne comme s'il correspondait à l'un des types de données intrinsèques de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ef30-106">You can use the name of the UDT in a column definition as though it were one of the intrinsic [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="2ef30-107">L’instruction CREATE TABLE suivante [!INCLUDE[tsql](../../includes/tsql-md.md)] crée une table nommée **points**, avec une colonne nommée **ID,** qui est définie comme une `int` colonne d’identité et la clé primaire de la table.</span><span class="sxs-lookup"><span data-stu-id="2ef30-107">The following CREATE TABLE [!INCLUDE[tsql](../../includes/tsql-md.md)] statement creates a table named **Points**, with a column named **ID,** which is defined as an `int` identity column and \ the primary key for the table.</span></span> <span data-ttu-id="2ef30-108">La deuxième colonne est nommée **PointValue**, avec un type de données **point**.</span><span class="sxs-lookup"><span data-stu-id="2ef30-108">The second column is named **PointValue**, with a data type of **Point**.</span></span> <span data-ttu-id="2ef30-109">Le nom de schéma utilisé dans cet exemple est **dbo**.</span><span class="sxs-lookup"><span data-stu-id="2ef30-109">The schema name used in this example is **dbo**.</span></span> <span data-ttu-id="2ef30-110">Notez que vous devez disposer des autorisations nécessaires pour spécifier un nom de schéma.</span><span class="sxs-lookup"><span data-stu-id="2ef30-110">Note that you must have the necessary permissions to specify a schema name.</span></span> <span data-ttu-id="2ef30-111">Si vous omettez le nom de schéma, le schéma par défaut de l'utilisateur de base de données est utilisé.</span><span class="sxs-lookup"><span data-stu-id="2ef30-111">If you omit the schema name, the default schema for the database user is used.</span></span>  
  
```  
CREATE TABLE dbo.Points   
(ID int IDENTITY(1,1) PRIMARY KEY, PointValue Point)  
```  
  
## <a name="creating-indexes-on-udt-columns"></a><span data-ttu-id="2ef30-112">Création d'index sur des colonnes UDT</span><span class="sxs-lookup"><span data-stu-id="2ef30-112">Creating Indexes on UDT Columns</span></span>  
 <span data-ttu-id="2ef30-113">Il existe deux options pour indexer une colonne UDT :</span><span class="sxs-lookup"><span data-stu-id="2ef30-113">There are two options for indexing a UDT column:</span></span>  
  
-   <span data-ttu-id="2ef30-114">Indexez la valeur complète.</span><span class="sxs-lookup"><span data-stu-id="2ef30-114">Index the full value.</span></span> <span data-ttu-id="2ef30-115">Dans ce cas, si le type défini par l'utilisateur est ordonné binaire, vous pouvez créer un index sur la colonne UDT tout entière en utilisant l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE INDEX.</span><span class="sxs-lookup"><span data-stu-id="2ef30-115">In this case, if the UDT is binary ordered, you can create an index over the entire UDT column by using the CREATE INDEX [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
-   <span data-ttu-id="2ef30-116">Indexez des expressions UDT.</span><span class="sxs-lookup"><span data-stu-id="2ef30-116">Index UDT expressions.</span></span> <span data-ttu-id="2ef30-117">Vous pouvez créer des index dans des colonnes calculées persistantes sur des expressions UDT.</span><span class="sxs-lookup"><span data-stu-id="2ef30-117">You can create indexes on persisted computed columns over UDT expressions.</span></span> <span data-ttu-id="2ef30-118">L'expression UDT peut être un champ, une méthode ou une propriété d'un UDT.</span><span class="sxs-lookup"><span data-stu-id="2ef30-118">The UDT expression can be a field, method, or property of a UDT.</span></span> <span data-ttu-id="2ef30-119">L'expression doit être déterministe et ne doit pas accéder aux données.</span><span class="sxs-lookup"><span data-stu-id="2ef30-119">The expression must be deterministic and must not perform data access.</span></span>  
  
 <span data-ttu-id="2ef30-120">Pour plus d’informations, consultez [types CLR définis par l’utilisateur](clr-user-defined-types.md) et [create index &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2ef30-120">For more information, see [CLR User-Defined Types](clr-user-defined-types.md) and [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ef30-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2ef30-121">See Also</span></span>  
 [<span data-ttu-id="2ef30-122">Utilisation de types définis par l’utilisateur dans SQL Server</span><span class="sxs-lookup"><span data-stu-id="2ef30-122">Working with User-Defined Types in SQL Server</span></span>](working-with-user-defined-types-in-sql-server.md)  
  
  
