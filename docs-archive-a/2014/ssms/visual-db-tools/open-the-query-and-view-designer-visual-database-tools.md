---
title: Ouvrir le Concepteur de requêtes et de vues (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- opening View Designer
- View Designer, opening
- Query Designer [SQL Server], opening
- opening Query Designer
ms.assetid: b473f258-d53c-41c0-9ad9-528a2ff141f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3a36a0a9f014759269517a5774167f84c19b0b18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605870"
---
# <a name="open-the-query-and-view-designer-visual-database-tools"></a><span data-ttu-id="b05da-102">Ouvrir le Concepteur de requêtes et de vues (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="b05da-102">Open the Query and View Designer (Visual Database Tools)</span></span>
  <span data-ttu-id="b05da-103">Le Concepteur de requêtes et de vues s'affiche lorsque vous ouvrez la définition d'une vue, lorsque vous affichez les résultats d'une requête ou d'une vue, ou encore lorsque vous créez ou ouvrez une requête.</span><span class="sxs-lookup"><span data-stu-id="b05da-103">The Query and View Designer opens when you open the definition of a view, show the results for a query or view, or create or open a query.</span></span> <span data-ttu-id="b05da-104">Il se compose de quatre volets distincts :</span><span class="sxs-lookup"><span data-stu-id="b05da-104">It consists of four separate panes:</span></span>  
  
-   <span data-ttu-id="b05da-105">Ce volet donne une représentation graphique des tables ou des objets tables que vous avez sélectionnés dans la connexion de données.</span><span class="sxs-lookup"><span data-stu-id="b05da-105">The Diagram pane presents a graphic display of the tables or table-valued objects you have selected from the data connection.</span></span> <span data-ttu-id="b05da-106">Il montre également les jointures entre ces tables et/ou ces objets.</span><span class="sxs-lookup"><span data-stu-id="b05da-106">It also shows any join relationships among them.</span></span>  
  
-   <span data-ttu-id="b05da-107">Ce volet permet d’utiliser une grille similaire à une feuille de calcul pour spécifier des options de requêtes, telles que les colonnes de données à afficher, la façon de trier les résultats et les lignes à sélectionner.</span><span class="sxs-lookup"><span data-stu-id="b05da-107">The Criteria pane allows you to specify query options - such as which data columns to display, how to order the results, and what rows to select - by entering your choices into a spreadsheet-like grid.</span></span>  
  
-   <span data-ttu-id="b05da-108">Vous pouvez utiliser le volet SQL pour créer votre propre instruction SQL, ou utiliser le volet Critères et le volet Schéma pour créer l'instruction, auquel cas les instructions SQL sont créées dans le volet SQL.</span><span class="sxs-lookup"><span data-stu-id="b05da-108">You can use the SQL pane to create your own SQL statement, or you can use the Criteria pane and Diagram pane to create the statement, in which case the SQL statements will be created in the SQL pane.</span></span> <span data-ttu-id="b05da-109">Pendant la génération de la requête, le volet SQL se met automatiquement à jour et se reformate pour que sa lecture soit facile.</span><span class="sxs-lookup"><span data-stu-id="b05da-109">As you build your query, the SQL pane automatically updates and reformats to be easily read.</span></span>  
  
-   <span data-ttu-id="b05da-110">Le volet Résultats montre les résultats de la dernière requête Select exécutée.</span><span class="sxs-lookup"><span data-stu-id="b05da-110">The Results pane shows the results of the most recently executed Select query.</span></span> <span data-ttu-id="b05da-111">(Les résultats des autres types de requêtes sont affichés dans des boîtes de messages.)</span><span class="sxs-lookup"><span data-stu-id="b05da-111">(The results of other query types are displayed in message boxes.)</span></span>  
  
-   <span data-ttu-id="b05da-112">Ces volets sont utiles pour travailler à la fois avec des requêtes et avec des vues.</span><span class="sxs-lookup"><span data-stu-id="b05da-112">These panes are useful for working with both queries and views.</span></span>  
  
-   <span data-ttu-id="b05da-113">Lorsque vous ouvrez une vue ou une requête, une partie ou la totalité des volets s'affichent.</span><span class="sxs-lookup"><span data-stu-id="b05da-113">When you open a view or query some or all of the panes open with it.</span></span> <span data-ttu-id="b05da-114">Les volets qui s'ouvrent sont déterminés par les paramètres de la boîte de dialogue **Options** et du système de gestion de bases de données auquel vous êtes connecté.</span><span class="sxs-lookup"><span data-stu-id="b05da-114">Which ones open depend on the settings in the **Options** dialog box and what database management system you're connected to.</span></span> <span data-ttu-id="b05da-115">Par défaut, les quatre volets s'ouvrent.</span><span class="sxs-lookup"><span data-stu-id="b05da-115">The default is that all four open.</span></span>  
  
### <a name="to-open-the-query-and-view-designer-for-a-view"></a><span data-ttu-id="b05da-116">Pour ouvrir le Concepteur de requêtes et de vues pour une vue</span><span class="sxs-lookup"><span data-stu-id="b05da-116">To open the Query and View Designer for a view</span></span>  
  
1.  <span data-ttu-id="b05da-117">Dans l'Explorateur d'objets, cliquez avec le bouton droit sur la vue que vous souhaitez ouvrir et cliquez sur **Conception** ou sur **Ouvrir la vue**.</span><span class="sxs-lookup"><span data-stu-id="b05da-117">In Object Explorer, right-click the view you want to open and click **Design** or **Open View**.</span></span>  
  
     <span data-ttu-id="b05da-118">Si vous avez choisi **Conception**, les volets du Concepteur de requêtes et de vues s'ouvrent comme défini par les options sélectionnées dans la boîte de dialogue **Options** .</span><span class="sxs-lookup"><span data-stu-id="b05da-118">If you chose **Design**, the Query and View Designer panes open as dictated by the options selected in the **Options** dialog box.</span></span> <span data-ttu-id="b05da-119">Si vous avez choisi **Ouvrir la vue**, seul le volet Résultats s'ouvre par défaut.</span><span class="sxs-lookup"><span data-stu-id="b05da-119">If you chose **Open View**, only the Results pane opens by default.</span></span>  
  
### <a name="to-open-the-query-and-view-designer-for-an-existing-query"></a><span data-ttu-id="b05da-120">Pour ouvrir le Concepteur de requêtes et de vues pour une requête existante</span><span class="sxs-lookup"><span data-stu-id="b05da-120">To open the Query and View Designer for an existing query</span></span>  
  
1.  <span data-ttu-id="b05da-121">Dans l'Explorateur de solutions, développez le dossier **Requêtes** .</span><span class="sxs-lookup"><span data-stu-id="b05da-121">In Solution Explorer, expand the **Queries** folder.</span></span>  
  
2.  <span data-ttu-id="b05da-122">Double-cliquez sur la requête à ouvrir.</span><span class="sxs-lookup"><span data-stu-id="b05da-122">Double-click the query you want to open.</span></span>  
  
3.  <span data-ttu-id="b05da-123">Mettez en surbrillance les instructions de la requête, cliquez avec le bouton droit sur la zone en surbrillance puis cliquez sur **Concevoir une requête dans l'éditeur**.</span><span class="sxs-lookup"><span data-stu-id="b05da-123">Highlight the query statement(s), right-click the highlighted area and click **Design Query in Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b05da-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b05da-124">See Also</span></span>  
 <span data-ttu-id="b05da-125">[Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b05da-125">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="b05da-126">Outils du concepteur de requêtes et de vues &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="b05da-126">Query and View Designer Tools &#40;Visual Database Tools&#41;</span></span>](query-and-view-designer-tools-visual-database-tools.md)  
  
  
