---
title: Modifier manuellement une requête de prédiction | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying prediction queries
- Mining Model Prediction [Analysis Services], modifying prediction queries
- manual prediction query modification [Analysis Services]
ms.assetid: 9f6a9298-49d5-4675-ad49-977a47dff5a6
author: minewiskan
ms.author: owend
ms.openlocfilehash: e887e935dafcd2428859fd959cb7bc64650c660d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614908"
---
# <a name="manually-edit-a-prediction-query"></a><span data-ttu-id="093b5-102">Modifier manuellement une requête de prédiction</span><span class="sxs-lookup"><span data-stu-id="093b5-102">Manually Edit a Prediction Query</span></span>
  <span data-ttu-id="093b5-103">Après avoir créé une requête en utilisant le Générateur de requêtes de prédiction, vous pouvez modifier la requête en activant le mode Texte de la requête sous l’onglet **Prédiction de modèle d’exploration de données** du Concepteur d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="093b5-103">After you have designed a query by using the Prediction Query Builder, you can modify the query by switching to Query Text view on the **Mining Model Prediction** tab of Data Mining Designer.</span></span> <span data-ttu-id="093b5-104">Un éditeur de texte apparaît au bas de l'écran pour afficher la requête créée par le Générateur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="093b5-104">A text editor appears at the bottom of the screen to display the query that the query builder created.</span></span>  
  
 <span data-ttu-id="093b5-105">Le basculement vers le mode Texte de la requête est utile pour effectuer des ajouts à la requête.</span><span class="sxs-lookup"><span data-stu-id="093b5-105">Switching to Query Text view is useful for making additions to the query.</span></span> <span data-ttu-id="093b5-106">Par exemple, vous pouvez ajouter une clause WHERE ou une clause ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="093b5-106">For example, you can add a WHERE clause or ORDER BY clause.</span></span>  
  
 <span data-ttu-id="093b5-107">Utilisez la grille dans le Générateur de requêtes de prédiction pour insérer le nom des objets et des colonnes, ainsi que pour configurer la syntaxe de fonctions de prédiction individuelles, puis basculez vers le mode de modification manuelle pour modifier des valeurs de paramètres.</span><span class="sxs-lookup"><span data-stu-id="093b5-107">Use the grid in the Prediction Query Builder to insert the names of objects and columns and set up the syntax for individual prediction functions, and then switch to manual editing mode to change parameter values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="093b5-108">Si vous repassez du mode **Texte de la requête** au mode **Conception** , toutes les modifications apportées en mode **Texte de la requête** sont perdues.</span><span class="sxs-lookup"><span data-stu-id="093b5-108">If you switch back to **Design** view from **Query Text** view, any changes that you made in **Query Text** view will be lost.</span></span>  
  
### <a name="modify-a-query"></a><span data-ttu-id="093b5-109">Modifier une requête</span><span class="sxs-lookup"><span data-stu-id="093b5-109">Modify a query</span></span>  
  
1.  <span data-ttu-id="093b5-110">Sous l’onglet **Prédiction de modèle d’exploration de données** du Concepteur d’exploration de données de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], cliquez sur **SQL**.</span><span class="sxs-lookup"><span data-stu-id="093b5-110">On the **Mining Model Prediction** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click **SQL**.</span></span>  
  
     <span data-ttu-id="093b5-111">La grille au bas de l'écran est remplacée par un éditeur de texte qui contient la requête.</span><span class="sxs-lookup"><span data-stu-id="093b5-111">The grid at the bottom of the screen is replaced by a text editor that contains the query.</span></span> <span data-ttu-id="093b5-112">Vous pouvez modifier la requête dans cet éditeur.</span><span class="sxs-lookup"><span data-stu-id="093b5-112">You can type changes to the query in this editor.</span></span>  
  
2.  <span data-ttu-id="093b5-113">Pour exécuter la requête, dans le menu **Modèle d’exploration de données** , sélectionnez **Résultat**ou cliquez sur le bouton pour passer aux résultats de la requête.</span><span class="sxs-lookup"><span data-stu-id="093b5-113">To run the query, on the **Mining Model** menu, select **Result**, or click the button to switch to query results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="093b5-114">Si la requête que vous avez créée n'est pas valide, la fenêtre Résultats n'affiche ni erreur ni résultats.</span><span class="sxs-lookup"><span data-stu-id="093b5-114">If the query that you have created is invalid, the Results window does not display an error and does not display any results.</span></span> <span data-ttu-id="093b5-115">Cliquez sur le bouton **Conception** ou sélectionnez **Conception** ou **Requête** dans le menu **Modèle d’exploration de données** pour résoudre le problème et réexécuter la requête.</span><span class="sxs-lookup"><span data-stu-id="093b5-115">Click the **Design** button, or select **Design** or **Query** from the **Mining Model** menu to correct the problem and run the query again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="093b5-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="093b5-116">See Also</span></span>  
 <span data-ttu-id="093b5-117">[Requêtes d’exploration de données](data-mining-queries.md) </span><span class="sxs-lookup"><span data-stu-id="093b5-117">[Data Mining Queries](data-mining-queries.md) </span></span>  
 <span data-ttu-id="093b5-118">[Prédiction Générateur de requêtes &#40;l’exploration de données&#41;](../prediction-query-builder-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="093b5-118">[Prediction Query Builder &#40;Data Mining&#41;](../prediction-query-builder-data-mining.md) </span></span>  
 [<span data-ttu-id="093b5-119">Leçon 6 : création et utilisation de prédictions &#40;Didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="093b5-119">Lesson 6: Creating and Working with Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../tutorials/lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial.md)  
  
  
