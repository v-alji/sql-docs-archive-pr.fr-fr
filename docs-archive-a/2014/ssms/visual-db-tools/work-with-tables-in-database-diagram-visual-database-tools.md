---
title: Utiliser des tables dans les diagrammes de base de données (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- database diagrams [SQL Server], tables
- Table Designer, database diagrams
- tables [SQL Server], database diagrams
- database diagrams [SQL Server], Table Designer
ms.assetid: ee2c5d84-22bf-4597-ac70-a27ed8cc94f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: f648cd5fd08ed47c6670491ad5b7f3d75b7ead47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611445"
---
# <a name="work-with-tables-in-database-diagram-visual-database-tools"></a><span data-ttu-id="8901c-102">Utiliser des tables dans les diagrammes de base de données (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="8901c-102">Work with Tables in Database Diagram (Visual Database Tools)</span></span>
  <span data-ttu-id="8901c-103">Vous pouvez modifier et créer des tables de base de données dans le Concepteur de tables ou dans le Concepteur de diagrammes de base de données.</span><span class="sxs-lookup"><span data-stu-id="8901c-103">You can modify and create database tables in either Table Designer or Database Diagram Designer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8901c-104">Si la table est publiée pour réplication, vous devez apporter vos modifications au schéma à l’aide de l’instruction Transact-SQL [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) ou de SMO (SQL Server Management Objects).</span><span class="sxs-lookup"><span data-stu-id="8901c-104">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="8901c-105">Lorsque les modifications sont apportées au diagramme à l’aide du Concepteur de tables ou du Concepteur de diagrammes de base de données, celui-ci tente d’abandonner la table et de la recréer.</span><span class="sxs-lookup"><span data-stu-id="8901c-105">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="8901c-106">Toutefois, il est impossible d'abandonner les objets publiés, par conséquent les modifications du schéma échoueront.</span><span class="sxs-lookup"><span data-stu-id="8901c-106">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8901c-107">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="8901c-107">In This Section</span></span>  
 [<span data-ttu-id="8901c-108">Ajouter des tables à des schémas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="8901c-108">Add Tables to Diagrams &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
 [<span data-ttu-id="8901c-109">Ajouter des tables connexes à des schémas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="8901c-109">Add Related Tables to Diagrams &#40;Visual Database Tools&#41;</span></span>](add-related-tables-to-diagrams-visual-database-tools.md)  
  
 [<span data-ttu-id="8901c-110">Enregistrer des tables sélectionnées dans un schéma &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="8901c-110">Save Selected Tables on a Diagram &#40;Visual Database Tools&#41;</span></span>](save-selected-tables-on-a-diagram-visual-database-tools.md)  
  
 [<span data-ttu-id="8901c-111">Copier des tables d’un diagramme de base de données vers un autre &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="8901c-111">Copy Tables from One Database Diagrams to Another &#40;Visual Database Tools&#41;</span></span>](copy-tables-from-one-database-diagrams-to-another-visual-database-tools.md)  
  
 [<span data-ttu-id="8901c-112">Supprimer des tables de diagrammes de base de données &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="8901c-112">Remove Tables from Database Diagrams &#40;Visual Database Tools&#41;</span></span>](remove-tables-from-database-diagrams-visual-database-tools.md)  
  
 [<span data-ttu-id="8901c-113">Mapper des relations plusieurs-à-plusieurs &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="8901c-113">Map Many-to-Many Relationships &#40;Visual Database Tools&#41;</span></span>](map-many-to-many-relationships-visual-database-tools.md)  
  
 [<span data-ttu-id="8901c-114">Établir des relations réflexives &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="8901c-114">Draw Reflexive Relationships &#40;Visual Database Tools&#41;</span></span>](draw-reflexive-relationships-visual-database-tools.md)  
  
## <a name="reference"></a><span data-ttu-id="8901c-115">Informations de référence</span><span class="sxs-lookup"><span data-stu-id="8901c-115">Reference</span></span>  
 [<span data-ttu-id="8901c-116">Boîte de dialogue Ajouter une table &#40;Concepteur de bases de données&#41; &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="8901c-116">Add Table Dialog Box &#40;Database Designer&#41; &#40;Visual Database Tools&#41;</span></span>](add-table-dialog-box-database-designer-visual-database-tools.md)  
  
## <a name="related-sections"></a><span data-ttu-id="8901c-117">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="8901c-117">Related Sections</span></span>  
  
