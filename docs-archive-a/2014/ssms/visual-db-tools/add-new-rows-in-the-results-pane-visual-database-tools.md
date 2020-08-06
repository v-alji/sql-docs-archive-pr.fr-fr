---
title: Ajouter des lignes dans le volet de résultats (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- View Designer, Results pane
- inserting rows
- Query Designer [SQL Server], Results pane
- Results pane
- adding rows
- row additions [SQL Server], Results pane
ms.assetid: 59891c84-3f54-4ab9-8b86-72c59627b480
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3137da106279e09305261c6c7cb7fd06d254b4fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603213"
---
# <a name="add-new-rows-in-the-results-pane-visual-database-tools"></a><span data-ttu-id="f2f5a-102">Ajouter des lignes dans le volet de résultats (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="f2f5a-102">Add New Rows in the Results Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="f2f5a-103">Pour ajouter de nouvelles données, vous pouvez soit les taper, soit les coller à partir d'un autre programme, tel que le Bloc-notes ou Excel.</span><span class="sxs-lookup"><span data-stu-id="f2f5a-103">You can add new data either by typing it in or by pasting it from another program such as Notepad or Excel.</span></span> <span data-ttu-id="f2f5a-104">Une ligne collée doit avoir exactement le même nombre et les mêmes types de colonnes que la table dans laquelle vous effectuez le collage.</span><span class="sxs-lookup"><span data-stu-id="f2f5a-104">A row to be pasted must have exactly the same number and types of columns as the table into which you are pasting.</span></span> <span data-ttu-id="f2f5a-105">Vous pouvez coller plusieurs lignes à la fois dans le volet Résultats.</span><span class="sxs-lookup"><span data-stu-id="f2f5a-105">You can paste multiple rows into the Results pane at once.</span></span>  
  
 <span data-ttu-id="f2f5a-106">Pour plus d’informations sur la façon d’entrer des données, consultez [Règles relatives à la mise à jour des résultats &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f2f5a-106">For information about how to enter data see [Rules for Updating Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
### <a name="to-add-a-new-data-row"></a><span data-ttu-id="f2f5a-107">Pour ajouter une nouvelle ligne de données</span><span class="sxs-lookup"><span data-stu-id="f2f5a-107">To add a new data row</span></span>  
  
1.  <span data-ttu-id="f2f5a-108">Allez en bas du volet Résultats, où vous trouverez une ligne blanche pour ajouter une nouvelle ligne de données.</span><span class="sxs-lookup"><span data-stu-id="f2f5a-108">Navigate to the bottom of the Results pane, where a blank row is available for adding a new data row.</span></span>  
  
     <span data-ttu-id="f2f5a-109">Les valeurs initiales de toutes les colonnes sont *NULL*.</span><span class="sxs-lookup"><span data-stu-id="f2f5a-109">The initial values for all columns will be *NULL*.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="f2f5a-110">Pour accéder directement à la première ligne vide, utilisez la barre de navigation située au bas du volet Résultats.</span><span class="sxs-lookup"><span data-stu-id="f2f5a-110">To go directly to the first empty row use the navigation bar at the bottom of the Results pane.</span></span>  
  
2.  <span data-ttu-id="f2f5a-111">Si vous collez des lignes depuis le Presse-papiers, pour sélectionner la nouvelle ligne, cliquez sur le bouton situé à sa gauche.</span><span class="sxs-lookup"><span data-stu-id="f2f5a-111">If you are pasting rows from the Clipboard, select the new row by clicking the button to its left.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f2f5a-112">Si une ou plusieurs lignes que vous collez ne peuvent pas être validées dans la base de données, un message indiquant la ou les lignes qui n'ont pas pu être validées s'affiche.</span><span class="sxs-lookup"><span data-stu-id="f2f5a-112">If one or more of the rows you're pasting can't be committed to the database you will receive a message telling you which row(s) couldn't be committed.</span></span>  
  
3.  <span data-ttu-id="f2f5a-113">Entrez les données de la nouvelle ligne.</span><span class="sxs-lookup"><span data-stu-id="f2f5a-113">Enter the data for the new row.</span></span> <span data-ttu-id="f2f5a-114">Si vous effectuez un collage, choisissez **Coller** dans le menu **Edition** .</span><span class="sxs-lookup"><span data-stu-id="f2f5a-114">If you are pasting, choose **Paste** from the **Edit** menu.</span></span>  
  
4.  <span data-ttu-id="f2f5a-115">Laissez cette ligne pour la valider dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="f2f5a-115">Leave that row to commit it to the database.</span></span>  
  
 <span data-ttu-id="f2f5a-116">Si une erreur se produit lorsque vous enregistrez la ligne, le Concepteur de requêtes et de vues affiche un message, puis vous ramène à la ligne que vous avez modifiée.</span><span class="sxs-lookup"><span data-stu-id="f2f5a-116">If an error occurs when you save the row the Query and View Designer displays a message and then returns you to the row you were editing.</span></span> <span data-ttu-id="f2f5a-117">Ensuite, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="f2f5a-117">You can then:</span></span>  
  
-   <span data-ttu-id="f2f5a-118">Résoudre l'erreur par de nouvelles modifications de la ligne.</span><span class="sxs-lookup"><span data-stu-id="f2f5a-118">Resolve the error by making further edits in the row.</span></span>  
  
-   <span data-ttu-id="f2f5a-119">Annuler la modification en appuyant sur ÉCHAP.</span><span class="sxs-lookup"><span data-stu-id="f2f5a-119">Cancel the edit by pressing ESC.</span></span> <span data-ttu-id="f2f5a-120">Si vous appuyez sur ÉCHAP alors que vous êtes dans une cellule que vous avez modifiée, seules les modifications apportées à cette cellule sont annulées.</span><span class="sxs-lookup"><span data-stu-id="f2f5a-120">If you press ESC while in a cell that you changed, the changes for that cell are canceled.</span></span> <span data-ttu-id="f2f5a-121">Si vous appuyez sur ÉCHAP alors que vous êtes dans une cellule que vous n'avez pas modifiée, toutes les modifications de la ligne sont annulées.</span><span class="sxs-lookup"><span data-stu-id="f2f5a-121">If you press ESC while in a cell you have not changed, the changes for the entire row are canceled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2f5a-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f2f5a-122">See Also</span></span>  
 <span data-ttu-id="f2f5a-123">[Utiliser des données dans le volet de résultats &#40;Visual Database Tools&#41;](results-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="f2f5a-123">[Work with Data in the Results Pane &#40;Visual Database Tools&#41;](results-pane-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="f2f5a-124">Effectuer des opérations de base concernant les requêtes &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="f2f5a-124">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
