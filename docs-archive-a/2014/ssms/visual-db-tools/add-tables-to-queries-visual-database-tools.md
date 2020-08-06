---
title: Ajouter des tables à des requêtes (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting tables
- adding tables
- queries [SQL Server], tables
ms.assetid: 6551aa7e-31a1-4636-852a-819bc53d658b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 572002bc913cc9916a75ce2b16c12064452d250f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605883"
---
# <a name="add-tables-to-queries-visual-database-tools"></a><span data-ttu-id="eec4d-102">Ajouter des tables à des requêtes (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="eec4d-102">Add Tables to Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="eec4d-103">Quand vous créez une requête, vous récupérez des données d’une table ou d’autres objets structurés comme des tables (vues et certaines fonctions définies par l’utilisateur).</span><span class="sxs-lookup"><span data-stu-id="eec4d-103">When you create a query, you are retrieving data from a table or other objects structured like tables - views and certain user-defined functions.</span></span> <span data-ttu-id="eec4d-104">Pour utiliser l'un de ces objets dans votre requête, vous pouvez les ajouter au **volet Schéma**.</span><span class="sxs-lookup"><span data-stu-id="eec4d-104">To work with any of these objects in your query, you add them to the **Diagram Pane**.</span></span>  
  
### <a name="to-add-a-table-or-table-valued-object-to-a-query"></a><span data-ttu-id="eec4d-105">Pour ajouter une table ou objet table à une requête</span><span class="sxs-lookup"><span data-stu-id="eec4d-105">To add a table or table-valued object to a query</span></span>  
  
1.  <span data-ttu-id="eec4d-106">Dans le **volet Schéma** du Concepteur de requêtes et de vues, cliquez avec le bouton droit sur l'arrière-plan et choisissez **Ajouter une table** dans le menu contextuel qui s'affiche.</span><span class="sxs-lookup"><span data-stu-id="eec4d-106">In the **Diagram pane** of the Query and View Designer, right-click the background and choose **Add Table** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="eec4d-107">Dans la boîte de dialogue **Ajouter une table** , sélectionnez l'onglet qui correspond au type d'objet que vous souhaitez ajouter à la requête.</span><span class="sxs-lookup"><span data-stu-id="eec4d-107">In the **Add Table** dialog box, select the tab for the type of object you want to add to the query.</span></span>  
  
3.  <span data-ttu-id="eec4d-108">Dans la liste affichée, double-cliquez sur chacun des éléments que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="eec4d-108">In the list of items, double-click each item you want to add.</span></span>  
  
4.  <span data-ttu-id="eec4d-109">Une fois que vous avez ajouté tous les éléments choisi, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="eec4d-109">When you finish adding items, click **Close**.</span></span>  
  
     <span data-ttu-id="eec4d-110">Le Concepteur de requêtes et de vue met à jour le **volet Schéma**, le **volet Critères**et le **volet SQL** d'après vos sélections.</span><span class="sxs-lookup"><span data-stu-id="eec4d-110">The Query and View Designer updates the **Diagram Pane**, **Criteria Pane**, and **SQL Pane** accordingly.</span></span>  
  
 <span data-ttu-id="eec4d-111">Les tables et les vues sont automatiquement ajoutées à la requête lorsque vous les référencez dans l'instruction du volet SQL.</span><span class="sxs-lookup"><span data-stu-id="eec4d-111">Tables and views are automatically added to the query when you reference them in the statement in the SQL pane.</span></span>  
  
 <span data-ttu-id="eec4d-112">Le Concepteur de requêtes et de vues n'affiche pas les colonnes de données d'une table ou d'un objet table si vous ne disposez pas des droits d'accès correspondants ou si le fournisseur ne parvient pas à retourner des informations le concernant.</span><span class="sxs-lookup"><span data-stu-id="eec4d-112">The Query and View Designer will not display data columns for a table or table-structured object if you do not have sufficient access rights to it or if the provider cannot return information about it.</span></span> <span data-ttu-id="eec4d-113">Dans ce cas, seules une barre de titre et la case à cocher \* (Toutes les colonnes) sont disponibles pour la table ou l'objet table.</span><span class="sxs-lookup"><span data-stu-id="eec4d-113">In such cases, only a title bar and the \* (All Columns) check box are displayed for the table or table-valued object.</span></span>  
  
### <a name="to-add-an-existing-query-to-a-new-query"></a><span data-ttu-id="eec4d-114">Pour ajouter une requête existante à une nouvelle requête</span><span class="sxs-lookup"><span data-stu-id="eec4d-114">To add an existing query to a new query</span></span>  
  
1.  <span data-ttu-id="eec4d-115">Vérifiez que le **volet SQL** figure dans la nouvelle requête que vous êtes en train de créer.</span><span class="sxs-lookup"><span data-stu-id="eec4d-115">Make sure the **SQL Pane** is displayed in the new query you are creating.</span></span>  
  
2.  <span data-ttu-id="eec4d-116">Dans le **volet SQL**, tapez des parenthèses ouvrante et fermante () à la suite du mot FROM.</span><span class="sxs-lookup"><span data-stu-id="eec4d-116">In the **SQL Pane**, type a right and left parentheses () after the word FROM.</span></span>  
  
3.  <span data-ttu-id="eec4d-117">Ouvrez le Concepteur de requêtes et de vues pour la requête existante.</span><span class="sxs-lookup"><span data-stu-id="eec4d-117">Open the Query Designer for the existing query.</span></span> <span data-ttu-id="eec4d-118">Deux Concepteurs de requêtes et de vues sont désormais ouverts.</span><span class="sxs-lookup"><span data-stu-id="eec4d-118">(You now have two Query Designers open.)</span></span>  
  
4.  <span data-ttu-id="eec4d-119">Affichez le **volet SQL** pour la requête interne (la requête existante que vous ajoutez à la nouvelle requête externe).</span><span class="sxs-lookup"><span data-stu-id="eec4d-119">Display the **SQL Pane** for the inner query - the existing query you are including in the new, outer query.</span></span>  
  
5.  <span data-ttu-id="eec4d-120">Sélectionnez l'ensemble du texte figurant dans le **volet SQL**et copiez-le dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="eec4d-120">Select all the text in the **SQL Pane**, and copy it to the Clipboard.</span></span>  
  
6.  <span data-ttu-id="eec4d-121">Cliquez sur le **volet SQL** de la nouvelle requête, placez le curseur entre les parenthèses que vous avez ajoutées et collez-y le contenu du Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="eec4d-121">Click in the **SQL Pane** of the new query, situate the cursor between the parentheses you added, and paste the contents of the Clipboard.</span></span>  
  
7.  <span data-ttu-id="eec4d-122">Toujours dans le **volet SQL**, ajoutez un alias à la suite de la parenthèse fermante.</span><span class="sxs-lookup"><span data-stu-id="eec4d-122">Still in the **SQL Pane**, add an alias after the right parenthesis.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eec4d-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eec4d-123">See Also</span></span>  
 <span data-ttu-id="eec4d-124">[Créer des alias de table &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="eec4d-124">[Create Table Aliases &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="eec4d-125">[Supprimer des tables des requêtes &#40;Visual Database Tools&#41;](remove-tables-from-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="eec4d-125">[Remove Tables from Queries &#40;Visual Database Tools&#41;](remove-tables-from-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="eec4d-126">[Spécifier les critères de recherche &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="eec4d-126">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="eec4d-127">[Résumer les résultats de la requête &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="eec4d-127">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="eec4d-128">Effectuer des opérations de base concernant les requêtes &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="eec4d-128">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
