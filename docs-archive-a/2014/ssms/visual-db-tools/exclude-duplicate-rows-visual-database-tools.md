---
title: Exclure les doublons de lignes (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], excluding rows
- row duplicates [SQL Server]
- duplicate rows
- row excluded in search [SQL Server]
- result sets [SQL Server], duplicate values
- excluding rows
ms.assetid: ab35a363-421d-4665-946b-ae3f6397af50
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3b396f2738f6895684d828884d4822ea9165e0a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613753"
---
# <a name="exclude-duplicate-rows-visual-database-tools"></a><span data-ttu-id="6532b-102">Exclure les doublons de lignes (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="6532b-102">Exclude Duplicate Rows (Visual Database Tools)</span></span>
  <span data-ttu-id="6532b-103">Si vous souhaitez afficher uniquement des valeurs uniques dans un jeu de résultats, vous pouvez spécifier qu'il faut exclure les doublons du jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="6532b-103">If you want to see only unique values in a result set, you can specify that you want to exclude duplicates from the result set.</span></span>  
  
### <a name="to-exclude-duplicate-rows-from-the-result-set"></a><span data-ttu-id="6532b-104">Pour exclure les doublons du jeu de résultats</span><span class="sxs-lookup"><span data-stu-id="6532b-104">To exclude duplicate rows from the result set</span></span>  
  
1.  <span data-ttu-id="6532b-105">Cliquez avec le bouton droit sur un point de l’arrière-plan du volet Schéma, puis choisissez **Propriétés** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="6532b-105">Right-click the background of the Diagram pane, then choose **Properties** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="6532b-106">Dans la fenêtre Propriétés, cliquez sur **Valeurs DISTINCT** et affectez-lui la valeur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="6532b-106">In the Property window, click **Distinct values** and set the value to **Yes**.</span></span>  
  
     <span data-ttu-id="6532b-107">Le Concepteur de requêtes et de vues insère le mot clé DISTINCT devant la liste des colonnes affichées dans l'instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="6532b-107">The Query and View Designer inserts the keyword DISTINCT in front of the list of display columns in the SQL statement.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6532b-108">Si vous utilisez le mot clé DISTINCT, il se peut que vous ne puissiez pas modifier le jeu de résultats dans le volet Résultats.</span><span class="sxs-lookup"><span data-stu-id="6532b-108">If you use the DISTINCT keyword you may not be able to modify the result set in the results pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6532b-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6532b-109">See Also</span></span>  
 <span data-ttu-id="6532b-110">[Spécifier les critères de recherche &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="6532b-110">[Specify Search Criteria &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="6532b-111">Trier et regrouper des résultats de requête &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="6532b-111">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  
