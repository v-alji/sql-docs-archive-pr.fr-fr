---
title: Modifier les propriétés d’une structure d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], properties
ms.assetid: 03b16897-2e36-42b8-9f7d-db1b9b898401
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2c1e63ad5fada770394e2fc283e0e592319281b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694843"
---
# <a name="change-the-properties-of-a-mining-structure"></a><span data-ttu-id="32928-102">Modifier les propriétés d'une structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="32928-102">Change the Properties of a Mining Structure</span></span>
  <span data-ttu-id="32928-103">Il existe deux types de propriétés sur une structure d'exploration de données, qui peuvent être modifiées :</span><span class="sxs-lookup"><span data-stu-id="32928-103">There are two kinds of properties on a mining structure, both of which can be modified:</span></span>  
  
-   <span data-ttu-id="32928-104">Propriétés de la structure d'exploration de données qui affectent la structure entière</span><span class="sxs-lookup"><span data-stu-id="32928-104">Properties of the mining structure that affect the entire structure</span></span>  
  
-   <span data-ttu-id="32928-105">Propriétés sur des colonnes individuelles de la structure</span><span class="sxs-lookup"><span data-stu-id="32928-105">Properties on individual columns in the structure</span></span>  
  
 <span data-ttu-id="32928-106">Notez que certaines propriétés dépendent d'autres paramètres de propriété.</span><span class="sxs-lookup"><span data-stu-id="32928-106">Note that some properties are dependent on other property settings.</span></span> <span data-ttu-id="32928-107">Par exemple, vous ne pouvez pas définir les propriétés qui contrôlent le comportement de placement dans un conteneur (notamment <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> ou <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A>) jusqu'à ce que vous ayez défini le type de données de la colonne à `Discretized`.</span><span class="sxs-lookup"><span data-stu-id="32928-107">For example, you cannot set properties that control binning behavior (such as <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> or <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A>) until you have set the data type of the column to `Discretized`.</span></span>  
  
 <span data-ttu-id="32928-108">Pour plus d’informations sur les propriétés de structure d’exploration de données, consultez [Structure d’exploration de données](mining-structure-columns.md).</span><span class="sxs-lookup"><span data-stu-id="32928-108">For more information about mining structure properties, see [Mining Structure Columns](mining-structure-columns.md).</span></span>  
  
### <a name="to-change-the-properties-of-a-mining-structure"></a><span data-ttu-id="32928-109">Pour modifier les propriétés d'une structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="32928-109">To change the properties of a mining structure</span></span>  
  
1.  <span data-ttu-id="32928-110">Sous l’onglet **Structure d’exploration de données** du Concepteur d’exploration de données, cliquez avec le bouton droit de la souris sur la structure d’exploration de données ou sur une colonne de la structure d’exploration de données, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="32928-110">On the **Mining Structure** tab in Data Mining Designer, right-click either the mining structure or a column in the mining structure, and then select **Properties**.</span></span>  
  
     <span data-ttu-id="32928-111">La fenêtre **Propriétés** s’ouvre dans la partie droite de l’écran si elle n’était pas affichée.</span><span class="sxs-lookup"><span data-stu-id="32928-111">The **Properties** window opens on the right side of the screen, if it was not already visible.</span></span>  
  
2.  <span data-ttu-id="32928-112">Dans la fenêtre **Propriétés** , sélectionnez la valeur qui correspond à la propriété à modifier, puis entrez la nouvelle valeur.</span><span class="sxs-lookup"><span data-stu-id="32928-112">In the **Properties** window, select the value that corresponds to the property that you want to change, and then enter the new value.</span></span>  
  
     <span data-ttu-id="32928-113">La nouvelle valeur est appliquée lorsque vous sélectionnez un élément différent dans le concepteur.</span><span class="sxs-lookup"><span data-stu-id="32928-113">The new value will take effect when you select a different element in the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32928-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="32928-114">See Also</span></span>  
 [<span data-ttu-id="32928-115">Tâches de la structure d'exploration de données et procédures</span><span class="sxs-lookup"><span data-stu-id="32928-115">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
