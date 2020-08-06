---
title: Tables et index | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, indexes
- OLE DB, tables
- ITableDefinition interface
- tables [OLE DB]
- IIndexDefinition interface
- SQL Server Native Client OLE DB provider, tables
- SQL Server Native Client OLE DB provider, indexes
- indexes [OLE DB]
ms.assetid: 4217c6d8-8cd2-43dc-b36f-3cfd8a58fabc
author: rothja
ms.author: jroth
ms.openlocfilehash: abc7c314e433eb9f107bd191738d951706f1b50d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611035"
---
# <a name="tables-and-indexes"></a><span data-ttu-id="d4dae-102">Tables et index</span><span class="sxs-lookup"><span data-stu-id="d4dae-102">Tables and Indexes</span></span>
  <span data-ttu-id="d4dae-103">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client expose les interfaces **IIndexDefinition** et **ITableDefinition** , ce qui permet aux consommateurs de créer, modifier et supprimer des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables et des index.</span><span class="sxs-lookup"><span data-stu-id="d4dae-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **IIndexDefinition** and **ITableDefinition** interfaces, allowing consumers to create, alter, and drop [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables and indexes.</span></span> <span data-ttu-id="d4dae-104">Les définitions de table et d'index valides dépendent de la version de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4dae-104">Valid table and index definitions depend on the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d4dae-105">La possibilité de créer ou de supprimer des tables et des index dépend des droits d'accès [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de l'utilisateur de l'application consommateur.</span><span class="sxs-lookup"><span data-stu-id="d4dae-105">The ability to create or drop tables and indexes depends on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] access rights of the consumer-application user.</span></span> <span data-ttu-id="d4dae-106">La suppression d'une table peut être également limitée par la présence de contraintes d'intégrité référentielle déclarative ou d'autres facteurs.</span><span class="sxs-lookup"><span data-stu-id="d4dae-106">Dropping a table can be further constrained by the presence of declarative referential integrity constraints or other factors.</span></span>  
  
 <span data-ttu-id="d4dae-107">La plupart des applications ciblant [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilisent SQL-DMO au lieu de ces [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interfaces de fournisseur Native Client OLE DB.</span><span class="sxs-lookup"><span data-stu-id="d4dae-107">Most applications targeting [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] use SQL-DMO instead of these [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider interfaces.</span></span> <span data-ttu-id="d4dae-108">SQL-DMO est une collection d'objets OLE Automation qui prennent en charge toutes les fonctions d'administration de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4dae-108">SQL-DMO is a collection of OLE Automation objects that support all the administrative functions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d4dae-109">Les applications ciblant plusieurs fournisseurs OLE DB utilisent ces interfaces OLE DB génériques qui sont prises en charge par les différents fournisseurs OLE DB.</span><span class="sxs-lookup"><span data-stu-id="d4dae-109">Applications targeting multiple OLE DB providers use these generic OLE DB interfaces that are supported by the various OLE DB providers.</span></span>  
  
 <span data-ttu-id="d4dae-110">Dans le jeu de propriétés spécifique au fournisseur DBPROPSET_SQLSERVERCOLUMN, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] définit la propriété suivante.</span><span class="sxs-lookup"><span data-stu-id="d4dae-110">In the provider-specific property set DBPROPSET_SQLSERVERCOLUMN, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] defines the following property.</span></span>  
  
|<span data-ttu-id="d4dae-111">ID de propriété</span><span class="sxs-lookup"><span data-stu-id="d4dae-111">Property ID</span></span>|<span data-ttu-id="d4dae-112">Description</span><span class="sxs-lookup"><span data-stu-id="d4dae-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="d4dae-113">SSPROP_COL_COLLATIONNAME</span><span class="sxs-lookup"><span data-stu-id="d4dae-113">SSPROP_COL_COLLATIONNAME</span></span>|<span data-ttu-id="d4dae-114">Tapez : VT_BSTR</span><span class="sxs-lookup"><span data-stu-id="d4dae-114">Type: VT_BSTR</span></span><br /><br /> <span data-ttu-id="d4dae-115">L/E (Lecture/Écriture) : écriture</span><span class="sxs-lookup"><span data-stu-id="d4dae-115">R/W: Write</span></span><br /><br /> <span data-ttu-id="d4dae-116">Valeur par défaut : Null</span><span class="sxs-lookup"><span data-stu-id="d4dae-116">Default: Null</span></span><br /><br /> <span data-ttu-id="d4dae-117">Description : cette propriété est utilisée uniquement dans **ITableDefinition**.</span><span class="sxs-lookup"><span data-stu-id="d4dae-117">Description: This property is used only in **ITableDefinition**.</span></span> <span data-ttu-id="d4dae-118">La chaîne spécifiée dans cette propriété est utilisée lors de la création d’une instruction [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d4dae-118">The string specified in this property is used when creating a [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql)</span></span><br /><br /> <span data-ttu-id="d4dae-119">.</span><span class="sxs-lookup"><span data-stu-id="d4dae-119">statement.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="d4dae-120">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="d4dae-120">In This Section</span></span>  
  
-   [<span data-ttu-id="d4dae-121">Création de tables SQL Server</span><span class="sxs-lookup"><span data-stu-id="d4dae-121">Creating SQL Server Tables</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/creating-sql-server-tables.md)  
  
-   [<span data-ttu-id="d4dae-122">Ajout d'une colonne à une table SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d4dae-122">Adding a Column to a SQL Server Table</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/adding-a-column-to-a-sql-server-table.md)  
  
-   [<span data-ttu-id="d4dae-123">Suppression d'une colonne d'une table SQL Server</span><span class="sxs-lookup"><span data-stu-id="d4dae-123">Removing a Column from a SQL Server Table</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/removing-a-column-from-a-sql-server-table.md)  
  
-   [<span data-ttu-id="d4dae-124">Suppression d'une table SQL Server</span><span class="sxs-lookup"><span data-stu-id="d4dae-124">Dropping a SQL Server Table</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/dropping-a-sql-server-table.md)  
  
-   [<span data-ttu-id="d4dae-125">Création d'index SQL Server</span><span class="sxs-lookup"><span data-stu-id="d4dae-125">Creating SQL Server Indexes</span></span>](../../relational-databases/indexes/indexes.md)  
  
-   [<span data-ttu-id="d4dae-126">Suppression d'un index SQL Server</span><span class="sxs-lookup"><span data-stu-id="d4dae-126">Dropping a SQL Server Index</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/dropping-a-sql-server-index.md)  
  
## <a name="see-also"></a><span data-ttu-id="d4dae-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d4dae-127">See Also</span></span>  
 <span data-ttu-id="d4dae-128">[SQL Server Native Client &#40;OLE DB&#41;](../../relational-databases/native-client/ole-db/sql-server-native-client-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="d4dae-128">[SQL Server Native Client &#40;OLE DB&#41;](../../relational-databases/native-client/ole-db/sql-server-native-client-ole-db.md) </span></span>  
 <span data-ttu-id="d4dae-129">[DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d4dae-129">[DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) </span></span>  
 <span data-ttu-id="d4dae-130">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d4dae-130">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 [<span data-ttu-id="d4dae-131">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d4dae-131">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
  
