---
title: Spécifier la clause TOP dans des requêtes (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- TOP clause, queries
- percentage of rows returned [SQL Server]
- number of rows
- search conditions [SQL Server], TOP clause
- restricting rows returned
- search criteria [SQL Server], limiting rows returned
- inspecting portion of results
- limiting rows returned
- search criteria [SQL Server], TOP clause
ms.assetid: ba7d7c10-9bb3-4d9b-90b0-5fa94ecae59b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8228779703b1bbe3753f1e2728e83b4b5c3a3d17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708008"
---
# <a name="specify-the-top-clause-in-queries-visual-database-tools"></a><span data-ttu-id="2f7d8-102">Spécifier la clause TOP dans des requêtes (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="2f7d8-102">Specify the TOP Clause in Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="2f7d8-103">La clause TOP retourne uniquement les *n premières* lignes ou *n premiers pourcents* des lignes d’une requête.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-103">The TOP clause returns only the first *n* or *n percent* rows from a query.</span></span> <span data-ttu-id="2f7d8-104">La clause TOP peut être utile si vous souhaitez inspecter une partie de vos résultats afin de déterminer si votre requête se comporte de la manière escomptée, sans devoir utiliser les ressources nécessaires pour retourner tous les résultats de la requête.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-104">The TOP clause is useful when you want to inspect a portion of your results to find out if your query does what you expect it to do, without taking the resources necessary to return all of the query results.</span></span>  
  
### <a name="to-specify-the-top-clause-in-queries"></a><span data-ttu-id="2f7d8-105">Pour spécifier la clause TOP dans des requêtes</span><span class="sxs-lookup"><span data-stu-id="2f7d8-105">To specify the TOP clause in queries</span></span>  
  
1.  <span data-ttu-id="2f7d8-106">Ouvrez une requête dans l'Explorateur de solutions ou créez-en une nouvelle.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-106">Open a query from Solution Explorer or create a new one.</span></span>  
  
2.  <span data-ttu-id="2f7d8-107">Dans le menu **Affichage** , cliquez sur **Fenêtre Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-107">From the **View** menu, click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="2f7d8-108">Dans la **Fenêtre Propriétés**, recherchez et développez la propriété **Spécification Top** .</span><span class="sxs-lookup"><span data-stu-id="2f7d8-108">In the **Properties Window**, locate and expand the **Top Specification** property.</span></span>  
  
4.  <span data-ttu-id="2f7d8-109">Cliquez sur la propriété enfant **(Haut)** et affectez-lui la valeur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-109">Click the **(Top)** child property and set it to **Yes**.</span></span>  
  
5.  <span data-ttu-id="2f7d8-110">Dans la propriété enfant **Expression** , tapez une expression qui a un résultat numérique (par exemple, « 10 » ou « 2\*5 »).</span><span class="sxs-lookup"><span data-stu-id="2f7d8-110">In the **Expression** child property, type an expression that has a numeric result (for example, "10" or "2\*5").</span></span>  
  
6.  <span data-ttu-id="2f7d8-111">Cliquez sur la propriété enfant **Pourcentage** et indiquez si la propriété **Expression** doit être traitée comme un pourcentage de toutes les lignes retournées (Oui) ou comme le nombre absolu de lignes retournées (Non).</span><span class="sxs-lookup"><span data-stu-id="2f7d8-111">Click the **Percent** child property and indicate whether or not to treat the **Expression** property as a percentage of all rows returned (Yes) or as the absolute number of rows returned (No).</span></span>  
  
7.  <span data-ttu-id="2f7d8-112">Si votre requête utilise la clause ORDER BY, cliquez sur la propriété enfant **With Ties** et sélectionnez **Oui** pour afficher toutes les lignes d’un groupe si seule une partie du groupe est incluse ou **Non** pour les tronquer.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-112">If your query uses the ORDER BY clause, click the **With Ties** child property and choose **Yes** to display all rows in a group if only part of the group is included or **No** to truncate them.</span></span>  
  
 <span data-ttu-id="2f7d8-113">Au fur et à mesure que vous exécutez la procédure précédente, remarquez que la clause TOP, affichée dans le volet SQL, se modifie pour refléter les valeurs actuelles des propriétés.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-113">As you work through the preceding procedure, notice that the TOP clause, displayed in the SQL pane, changes to reflect the current settings of the properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f7d8-114">Vous pouvez également modifier les valeurs des propriétés enfants de la propriété **Spécification Top** en modifiant la clause TOP dans le volet SQL.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-114">You can also change the values of the child properties of the **Top Specification** by editing the TOP clause in the SQL pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f7d8-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2f7d8-115">See Also</span></span>  
 <span data-ttu-id="2f7d8-116">[Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2f7d8-116">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="2f7d8-117">Propriétés de la requête &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="2f7d8-117">Query Properties &#40;Visual Database Tools&#41;</span></span>](query-properties-visual-database-tools.md)  
  
  
