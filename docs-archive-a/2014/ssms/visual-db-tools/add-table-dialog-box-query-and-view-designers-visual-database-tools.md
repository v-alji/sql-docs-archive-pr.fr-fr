---
title: Boîte de dialogue Ajouter une table (concepteurs de requêtes et de vues) (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.query.addtable
- vdtsql.chm:65565
ms.assetid: fce7adcc-4cf5-4a52-9203-11c13d1ecf08
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8d7bf30cbdd37927735c36f184208a1ded957763
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603204"
---
# <a name="add-table-dialog-box-query-and-view-designers-visual-database-tools"></a><span data-ttu-id="c3ff0-102">Boîte de dialogue Ajouter une table (Concepteurs de requêtes et de vues)</span><span class="sxs-lookup"><span data-stu-id="c3ff0-102">Add Table Dialog Box (Query and View Designers) (Visual Database Tools)</span></span>
  <span data-ttu-id="c3ff0-103">Cette boîte de dialogue permet d'ajouter à une requête ou à une vue, des tables, des vues, des fonctions définies par l'utilisateur ou des synonymes.</span><span class="sxs-lookup"><span data-stu-id="c3ff0-103">This dialog box lets you add tables, views, user-defined functions, or synonyms to a query or view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3ff0-104">Si la table est publiée pour réplication, vous devez apporter vos modifications au schéma à l’aide de l’instruction Transact-SQL [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) ou de SMO (SQL Server Management Objects).</span><span class="sxs-lookup"><span data-stu-id="c3ff0-104">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="c3ff0-105">Lorsque les modifications sont apportées au diagramme à l’aide du Concepteur de tables ou du Concepteur de diagrammes de base de données, celui-ci tente d’abandonner la table et de la recréer.</span><span class="sxs-lookup"><span data-stu-id="c3ff0-105">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="c3ff0-106">Toutefois, il est impossible d'abandonner les objets publiés, par conséquent les modifications du schéma échoueront.</span><span class="sxs-lookup"><span data-stu-id="c3ff0-106">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c3ff0-107">Options</span><span class="sxs-lookup"><span data-stu-id="c3ff0-107">Options</span></span>  
 <span data-ttu-id="c3ff0-108">**Tables**</span><span class="sxs-lookup"><span data-stu-id="c3ff0-108">**Tables**</span></span>  
 <span data-ttu-id="c3ff0-109">Énumère les tables que vous pouvez ajouter au volet **Schéma** .</span><span class="sxs-lookup"><span data-stu-id="c3ff0-109">Lists the tables you can add to the **Diagram** pane.</span></span> <span data-ttu-id="c3ff0-110">Pour ajouter une table, sélectionnez-la et cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c3ff0-110">To add a table, select it and click **Add**.</span></span> <span data-ttu-id="c3ff0-111">Pour ajouter plusieurs tables à la fois, sélectionnez-les et cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c3ff0-111">To add several tables at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="c3ff0-112">**Views**</span><span class="sxs-lookup"><span data-stu-id="c3ff0-112">**Views**</span></span>  
 <span data-ttu-id="c3ff0-113">Énumère les vues que vous pouvez ajouter au volet **Schéma** .</span><span class="sxs-lookup"><span data-stu-id="c3ff0-113">Lists the views you can add to the **Diagram** pane.</span></span> <span data-ttu-id="c3ff0-114">Pour ajouter une vue, sélectionnez-la et cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c3ff0-114">To add a view, select it and click **Add**.</span></span> <span data-ttu-id="c3ff0-115">Pour ajouter plusieurs vues à la fois, sélectionnez-les et cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c3ff0-115">To add several views at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="c3ff0-116">**Fonctions**</span><span class="sxs-lookup"><span data-stu-id="c3ff0-116">**Functions**</span></span>  
 <span data-ttu-id="c3ff0-117">Énumère les fonctions définies par l’utilisateur que vous pouvez ajouter au volet **Schéma** .</span><span class="sxs-lookup"><span data-stu-id="c3ff0-117">Lists the user-defined functions you can add to the **Diagram** pane.</span></span> <span data-ttu-id="c3ff0-118">Pour ajouter une fonction, sélectionnez-la et cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c3ff0-118">To add a function, select it and click **Add**.</span></span> <span data-ttu-id="c3ff0-119">Pour ajouter plusieurs fonctions à la fois, sélectionnez-les et cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c3ff0-119">To add several functions at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="c3ff0-120">**Synonymes**</span><span class="sxs-lookup"><span data-stu-id="c3ff0-120">**Synonyms**</span></span>  
 <span data-ttu-id="c3ff0-121">Énumère les synonymes que vous pouvez ajouter au volet **Schéma** .</span><span class="sxs-lookup"><span data-stu-id="c3ff0-121">Lists the synonyms you can add to the **Diagram** pane.</span></span> <span data-ttu-id="c3ff0-122">Pour ajouter un synonyme, sélectionnez-le et cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c3ff0-122">To add a synonym, select it and click **Add**.</span></span> <span data-ttu-id="c3ff0-123">Pour ajouter plusieurs synonymes à la fois, sélectionnez-les et cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c3ff0-123">To add several synonyms at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="c3ff0-124">**Actualiser**</span><span class="sxs-lookup"><span data-stu-id="c3ff0-124">**Refresh**</span></span>  
 <span data-ttu-id="c3ff0-125">Met à jour la liste pour ajouter toutes les modifications apportées à la base de données depuis la dernière récupération de la liste.</span><span class="sxs-lookup"><span data-stu-id="c3ff0-125">Update the list to include any changes made to the database since the list was last retrieved.</span></span>  
  
 <span data-ttu-id="c3ff0-126">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="c3ff0-126">**Add**</span></span>  
 <span data-ttu-id="c3ff0-127">Ajoute chaque élément sélectionné.</span><span class="sxs-lookup"><span data-stu-id="c3ff0-127">Add the selected item or items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3ff0-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c3ff0-128">See Also</span></span>  
 [<span data-ttu-id="c3ff0-129">Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ff0-129">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
