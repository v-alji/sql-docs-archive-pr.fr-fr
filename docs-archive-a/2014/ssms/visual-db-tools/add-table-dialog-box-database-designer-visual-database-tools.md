---
title: Ajouter une table, boîte de dialogue (Concepteur de bases de données) (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:65555
- vdt.dlgbox.schema.addtable
ms.assetid: 3c0b1b30-795c-4240-91d6-890b8348014a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6ae9d3763ef66c0a7580cc516169c2f273f36528
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603205"
---
# <a name="add-table-dialog-box-database-designer-visual-database-tools"></a><span data-ttu-id="ebd81-102">Boîte de dialogue Ajouter une table (Concepteur de bases de données)</span><span class="sxs-lookup"><span data-stu-id="ebd81-102">Add Table Dialog Box (Database Designer) (Visual Database Tools)</span></span>
  <span data-ttu-id="ebd81-103">Vous permet d'ajouter des tables dans le Concepteur de bases de données.</span><span class="sxs-lookup"><span data-stu-id="ebd81-103">Lets you add tables in Database Designer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ebd81-104">Si la table est publiée pour réplication, vous devez apporter vos modifications au schéma à l’aide de l’instruction Transact-SQL [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) ou de SMO (SQL Server Management Objects).</span><span class="sxs-lookup"><span data-stu-id="ebd81-104">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="ebd81-105">Lorsque les modifications sont apportées au diagramme à l’aide du Concepteur de tables ou du Concepteur de diagrammes de base de données, celui-ci tente d’abandonner la table et de la recréer.</span><span class="sxs-lookup"><span data-stu-id="ebd81-105">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="ebd81-106">Toutefois, il est impossible d'abandonner les objets publiés, par conséquent les modifications du schéma échoueront.</span><span class="sxs-lookup"><span data-stu-id="ebd81-106">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="ebd81-107">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="ebd81-107">UI element list</span></span>  
 <span data-ttu-id="ebd81-108">**Actualiser**</span><span class="sxs-lookup"><span data-stu-id="ebd81-108">**Refresh**</span></span>  
 <span data-ttu-id="ebd81-109">Actualise la liste des tables afin de refléter l'état actuel de la base de données.</span><span class="sxs-lookup"><span data-stu-id="ebd81-109">Refreshed the list of tables to match the current state of the database.</span></span>  
  
 <span data-ttu-id="ebd81-110">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="ebd81-110">**Add**</span></span>  
 <span data-ttu-id="ebd81-111">Ajoute la ou les tables sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="ebd81-111">Adds the selected table or tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ebd81-112">Si vous souhaitez ajouter plusieurs tables au schéma, vous pouvez toutes les sélectionner avant de cliquer sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="ebd81-112">If you want to add several tables to the diagram, you can select them all before clicking **Add**.</span></span> <span data-ttu-id="ebd81-113">Vous pouvez aussi double-cliquer sur chaque table à ajouter, puis cliquer sur **Fermer** quand vous avez terminé.</span><span class="sxs-lookup"><span data-stu-id="ebd81-113">Alternatively, you can double-click each table you want to add, then click **Close** when you are finished.</span></span>  
  
 <span data-ttu-id="ebd81-114">**Close**</span><span class="sxs-lookup"><span data-stu-id="ebd81-114">**Close**</span></span>  
 <span data-ttu-id="ebd81-115">Ferme la boîte de dialogue sans ajouter de tables supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="ebd81-115">Closes the dialog box without adding further tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebd81-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ebd81-116">See Also</span></span>  
 [<span data-ttu-id="ebd81-117">Ajouter des tables à des schémas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="ebd81-117">Add Tables to Diagrams &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
