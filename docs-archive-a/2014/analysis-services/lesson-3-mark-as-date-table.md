---
title: 'Leçon 4 : marquer en tant que table de dates | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c32cc336-b7d8-4122-9d62-4936344d2315
author: minewiskan
ms.author: owend
ms.openlocfilehash: c3ccc57d770d954e9523196d2393fa9dc2ada5b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611384"
---
# <a name="lesson-4-mark-as-date-table"></a><span data-ttu-id="447ee-102">Leçon 4 : Marquer en tant que table de dates</span><span class="sxs-lookup"><span data-stu-id="447ee-102">Lesson 4: Mark as Date Table</span></span>
  <span data-ttu-id="447ee-103">Dans la lecon 2 : Ajouter des données, vous avez importé une table de dimension nommée DimDate.</span><span class="sxs-lookup"><span data-stu-id="447ee-103">In Lesson 2: Add Data, you imported a dimension table named DimDate.</span></span> <span data-ttu-id="447ee-104">Vous avez ensuite renommé la table DimDate dans la lecon 3 : Renommer des colonnes, en lui attribuant le nom Date.</span><span class="sxs-lookup"><span data-stu-id="447ee-104">You then renamed the DimDate table, in Lesson 3: Rename Columns, to simply, Date.</span></span> <span data-ttu-id="447ee-105">Alors que dans votre modèle cette table s’appelle désormais Date, elle peut également être désignée par *Table de Date*, car elle contient des données de date et d’heure.</span><span class="sxs-lookup"><span data-stu-id="447ee-105">While in your model this table is now named Date, it can also be known as a *Date table*, in that it contains date and time data.</span></span>  
  
 <span data-ttu-id="447ee-106">Quand vous utilisez des fonctions Time Intelligence dans les calculs, par exemple, quand vous créez des mesures, vous devez spécifier les propriétés de la table de date, notamment une *table Date* et une *colonne Date* (identificateur unique) dans cette table.</span><span class="sxs-lookup"><span data-stu-id="447ee-106">Whenever you use Time Intelligence functions in calculations, as you will do when you create measures a little later, you must specify date table properties, which include a *Date table* and a unique identifier *Date column* in that table.</span></span> <span data-ttu-id="447ee-107">Vous pouvez ensuite créer des relations valides entre d'autres tables et la table de dates, nécessaires pour les calculs qui utilisent les fonctions Time Intelligence DAX.</span><span class="sxs-lookup"><span data-stu-id="447ee-107">You can then create valid relationships between other tables and the Date table; necessary for calculations using DAX time intelligence functions.</span></span>  
  
 <span data-ttu-id="447ee-108">Dans cette leçon, vous marquez la table Date importée et renommée comme *Table de Date* et la colonne Date (dans la table de date) comme *Colonne de date* (identificateur unique).</span><span class="sxs-lookup"><span data-stu-id="447ee-108">In this lesson, you will mark the imported and renamed Date table as the *Date table* and the Date column (in the Date table) as the *Date column* (unique identifier).</span></span> <span data-ttu-id="447ee-109">Toute utilisation de la date de nom peut devenir confuse, mais vous obtiendrez bientôt l’idée.</span><span class="sxs-lookup"><span data-stu-id="447ee-109">All the use of the name Date can get kind of confusing, but you'll soon get the idea.</span></span>  
  
 <span data-ttu-id="447ee-110">Durée estimée pour effectuer cette leçon : **3 minutes**</span><span class="sxs-lookup"><span data-stu-id="447ee-110">Estimated time to complete this lesson: **3 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="447ee-111">Prérequis</span><span class="sxs-lookup"><span data-stu-id="447ee-111">Prerequisites</span></span>  
 <span data-ttu-id="447ee-112">Cette rubrique fait partie d’un didacticiel de modélisation tabulaire, qui doit être suivi dans l’ordre prévu.</span><span class="sxs-lookup"><span data-stu-id="447ee-112">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="447ee-113">Avant d’effectuer les tâches de cette leçon, vous devez avoir terminé la [Leçon 3 : Renommer des colonnes](rename-columns.md).</span><span class="sxs-lookup"><span data-stu-id="447ee-113">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 3: Rename Columns](rename-columns.md).</span></span>  
  
### <a name="to-set-mark-as-date-table"></a><span data-ttu-id="447ee-114">Pour marquer en tant que table de dates</span><span class="sxs-lookup"><span data-stu-id="447ee-114">To set Mark as Date Table</span></span>  
  
1.  <span data-ttu-id="447ee-115">Dans le concepteur de modèles, cliquez sur la table **Date** (onglet).</span><span class="sxs-lookup"><span data-stu-id="447ee-115">In the model designer, click the **Date** table (tab).</span></span>  
  
2.  <span data-ttu-id="447ee-116">Cliquez sur le menu **table** , sur **Date**, puis sur **marquer en tant que table de dates**.</span><span class="sxs-lookup"><span data-stu-id="447ee-116">Click the **Table** menu, then click **Date**, and then click **Mark as Date Table**.</span></span>  
  
3.  <span data-ttu-id="447ee-117">Dans la boîte de dialogue **Marquer comme Table de Date** , dans la zone de liste **Date** , sélectionnez la colonne **Date** comme identificateur unique.</span><span class="sxs-lookup"><span data-stu-id="447ee-117">In the **Mark as Date Table** dialog box, in the **Date** listbox, select the **Date** column as the unique identifier.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="447ee-118">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="447ee-118">Next Steps</span></span>  
 <span data-ttu-id="447ee-119">Pour continuer ce didacticiel, passez à la [Leçon 5 : Créer des relations](lesson-4-create-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="447ee-119">To continue this tutorial, go to the next lesson: [Lesson 5: Create Relationships](lesson-4-create-relationships.md).</span></span>  
  
  
