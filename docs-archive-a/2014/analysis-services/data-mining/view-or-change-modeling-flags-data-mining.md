---
title: Afficher ou modifier les indicateurs de modélisation (exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d1169735-fb18-417b-b8d6-9a161e444020
author: minewiskan
ms.author: owend
ms.openlocfilehash: bf0edd827321685a2d6a9041759328a7ac6e7cbd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702156"
---
# <a name="view-or-change-modeling-flags-data-mining"></a><span data-ttu-id="8b5ce-102">Afficher ou modifier les indicateurs de modélisation (Exploration de données)</span><span class="sxs-lookup"><span data-stu-id="8b5ce-102">View or Change Modeling Flags (Data Mining)</span></span>
  <span data-ttu-id="8b5ce-103">Les indicateurs de modélisation sont des propriétés que vous définissez sur une colonne de structure d'exploration de données ou des colonnes du modèle d'exploration de données afin de contrôler la façon dont l'algorithme traite les données pendant l'analyse.</span><span class="sxs-lookup"><span data-stu-id="8b5ce-103">Modeling flags are properties that you set on a mining structure column or mining model columns to control how the algorithm processes the data during analysis.</span></span>  
  
 <span data-ttu-id="8b5ce-104">Dans le Concepteur d'exploration de données, vous pouvez afficher et modifier les indicateurs de modélisation associés à une structure d'exploration de données ou une colonne d'exploration de données en affichant les propriétés de la structure ou du modèle.</span><span class="sxs-lookup"><span data-stu-id="8b5ce-104">In Data Mining Designer, you can view and modify the modeling flags associated with a mining structure or mining column by viewing the properties of the structure or model.</span></span> <span data-ttu-id="8b5ce-105">Vous pouvez également définir des indicateurs de modélisation à l'aide de DMX, AMO ou XMLA.</span><span class="sxs-lookup"><span data-stu-id="8b5ce-105">You can also set modeling flags by using DMX, AMO, or XMLA.</span></span>  
  
 <span data-ttu-id="8b5ce-106">Cette procédure décrit comment modifier les indicateurs de modélisation dans le concepteur.</span><span class="sxs-lookup"><span data-stu-id="8b5ce-106">This procedure describes how to change the modeling flags in the designer.</span></span>  
  
### <a name="view-or-change-the-modeling-flag-for-a-structure-column-or-model-column"></a><span data-ttu-id="8b5ce-107">Afficher ou modifier l'indicateur de modélisation pour une colonne de structure ou une colonne de modèle</span><span class="sxs-lookup"><span data-stu-id="8b5ce-107">View or change the modeling flag for a structure column or model column</span></span>  
  
1.  <span data-ttu-id="8b5ce-108">Dans SQL Server Design Studio, ouvrez l'explorateur de solutions, puis double-cliquez sur la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="8b5ce-108">In SQL Server Design Studio, open Solution Explorer, and then double-click the mining structure.</span></span>  
  
2.  <span data-ttu-id="8b5ce-109">Pour définir l’indicateur de modélisation NOT NULL, cliquez sur l’onglet **structure d’exploration de données** . Pour définir les indicateurs de régression ou de MODEL_EXISTENCE_ONLY, cliquez sur l’onglet **modèle d’exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="8b5ce-109">To set the NOT NULL modeling flag, click the **Mining Structure** tab. To set the REGRESSOR or MODEL_EXISTENCE_ONLY flags, click the **Mining Model** tab.</span></span>  
  
3.  <span data-ttu-id="8b5ce-110">Cliquez avec le bouton droit sur la colonne à afficher ou à modifier, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="8b5ce-110">Right-click the column you want to view or change, and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="8b5ce-111">Pour ajouter un nouvel indicateur de modélisation, cliquez sur la zone de texte en regard de la propriété **ModelingFlags** , puis activez la ou les cases à cocher en regard des indicateurs de modélisation à utiliser.</span><span class="sxs-lookup"><span data-stu-id="8b5ce-111">To add a new modeling flag, click the text box next to the **ModelingFlags** property, and select the check box or check boxes for the modeling flags you want to use.</span></span>  
  
     <span data-ttu-id="8b5ce-112">Les indicateurs de modélisation sont affichés uniquement s'ils sont appropriés pour le type de données de colonne.</span><span class="sxs-lookup"><span data-stu-id="8b5ce-112">Modeling flags are displayed only if they are appropriate for the column data type.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8b5ce-113">Après avoir modifié un indicateur de modélisation, vous devez retraiter le modèle.</span><span class="sxs-lookup"><span data-stu-id="8b5ce-113">After you change a modeling flag, you must reprocess the model.</span></span>  
  
### <a name="get-the-modeling-flags-used-in-the-model"></a><span data-ttu-id="8b5ce-114">Obtenir les indicateurs de modélisation utilisés dans le modèle</span><span class="sxs-lookup"><span data-stu-id="8b5ce-114">Get the modeling flags used in the model</span></span>  
  
-   <span data-ttu-id="8b5ce-115">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], ouvrez une fenêtre de requête DMX et tapez une requête comme celle qui suit :</span><span class="sxs-lookup"><span data-stu-id="8b5ce-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open a DMX Query window, and type a query like the following:</span></span>  
  
    ```  
    SELECT COLUMN_NAME, CONTENT_TYPE, MODELING_FLAG  
    FROM $system.DMSCHEMA_MINING_COLUMNS  
    WHERE MODEL_NAME = 'Forecasting'  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8b5ce-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8b5ce-116">See Also</span></span>  
 <span data-ttu-id="8b5ce-117">[Tâches du modèle d’exploration de données et procédures](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="8b5ce-117">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="8b5ce-118">Indicateurs de modélisation &#40;exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="8b5ce-118">Modeling Flags &#40;Data Mining&#41;</span></span>](modeling-flags-data-mining.md)  
  
  
