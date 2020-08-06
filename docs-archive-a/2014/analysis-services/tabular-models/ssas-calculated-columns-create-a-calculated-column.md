---
title: Créer une colonne calculée (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.as.daxref.CreataCalculatedColumn.f1
ms.assetid: 59440510-2d76-41dc-9b55-edc15259f9da
author: minewiskan
ms.author: owend
ms.openlocfilehash: cdb56ffb2b42aa8225b7eff76b11315ea511fd81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694715"
---
# <a name="create-a-calculated-column-ssas-tabular"></a><span data-ttu-id="dae98-102">Créer une colonne calculée (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="dae98-102">Create a Calculated Column (SSAS Tabular)</span></span>
  <span data-ttu-id="dae98-103">Les colonnes calculées permettent d'ajouter de nouvelles données à votre modèle.</span><span class="sxs-lookup"><span data-stu-id="dae98-103">Calculated columns allow you to add new data to your model.</span></span> <span data-ttu-id="dae98-104">Au lieu de coller ou d’importer des valeurs dans la colonne, vous créez une formule DAX qui définit les valeurs de niveau de ligne de la colonne.</span><span class="sxs-lookup"><span data-stu-id="dae98-104">Instead of pasting or importing values into the column, you create a DAX formula that defines the column's row level values.</span></span> <span data-ttu-id="dae98-105">Les valeurs de chaque ligne d'une colonne calculée sont calculées et remplies lorsque vous créez une formule non valide puis cliquez sur ENTRÉE.</span><span class="sxs-lookup"><span data-stu-id="dae98-105">The values in each row of a calculated column are calculated and populated when you create a valid formula and then click ENTER.</span></span> <span data-ttu-id="dae98-106">La colonne calculée peut ensuite être ajoutée à une application de création de rapports ou d'analyse, comme toute autre colonne de données.</span><span class="sxs-lookup"><span data-stu-id="dae98-106">The calculated column can then be added to a reporting or analysis application just as would any other column of data.</span></span> <span data-ttu-id="dae98-107">Cette rubrique décrit comment créer une nouvelle colonne calculée à l'aide de la barre de formule DAX dans le générateur de modèles.</span><span class="sxs-lookup"><span data-stu-id="dae98-107">This topic describes how to create a new calculated column by using the DAX formula bar in the model designer.</span></span>  
  
#### <a name="to-create-a-new-calculated-column"></a><span data-ttu-id="dae98-108">Pour créer une nouvelle colonne calculée</span><span class="sxs-lookup"><span data-stu-id="dae98-108">To create a new calculated column</span></span>  
  
1.  <span data-ttu-id="dae98-109">Dans le générateur de modèles, dans la vue de données, sélectionnez la table à laquelle vous souhaitez ajouter une colonne calculée, cliquez sur le menu **Colonne** , puis sur **Ajouter une colonne**.</span><span class="sxs-lookup"><span data-stu-id="dae98-109">In the model designer, in Data View, select the table to which you want to add a calculated column, then click the **Column** menu, and then click **Add Column**.</span></span>  
  
     <span data-ttu-id="dae98-110">**Ajouter une colonne** est mis en surbrillance dans la colonne la plus à droite vide, et le curseur se place dans la barre de formule.</span><span class="sxs-lookup"><span data-stu-id="dae98-110">**Add Column** is highlighted over the empty rightmost column, and the cursor moves to the formula bar.</span></span>  
  
     <span data-ttu-id="dae98-111">Pour intercaler une colonne entre deux colonnes existantes, cliquez avec le bouton droit sur une colonne existante, puis sélectionnez **Insérer une colonne**.</span><span class="sxs-lookup"><span data-stu-id="dae98-111">To create a new column between two existing columns, right-click an existing column, and then click **Insert Column**.</span></span>  
  
2.  <span data-ttu-id="dae98-112">Dans la barre de formule, effectuez l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="dae98-112">In the formula bar, do one of the following:</span></span>  
  
    -   <span data-ttu-id="dae98-113">Tapez un signe égal suivi d'une formule.</span><span class="sxs-lookup"><span data-stu-id="dae98-113">Type an equal sign followed by a formula.</span></span>  
  
    -   <span data-ttu-id="dae98-114">Tapez un signe égal, suivi d'une fonction DAX, d'arguments et de paramètres, comme requis par la fonction.</span><span class="sxs-lookup"><span data-stu-id="dae98-114">Type an equal sign, followed by a DAX function, followed by arguments and parameters as required by the function.</span></span>  
  
    -   <span data-ttu-id="dae98-115">Cliquez sur le bouton de fonction (**fx**) puis, dans la boîte de dialogue **Insérer une fonction** , sélectionnez une catégorie et une fonction, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dae98-115">Click the function button (**fx**), then in the **Insert Function** dialog box, select a category and function, and then click **OK**.</span></span> <span data-ttu-id="dae98-116">Dans la barre de formule, tapez les arguments et les paramètres restants, comme requis par la fonction.</span><span class="sxs-lookup"><span data-stu-id="dae98-116">In the formula bar, type the remaining arguments and parameters as required by the function.</span></span>  
  
3.  <span data-ttu-id="dae98-117">Appuyez sur Entrée pour accepter la formule.</span><span class="sxs-lookup"><span data-stu-id="dae98-117">Press ENTER to accept the formula.</span></span>  
  
     <span data-ttu-id="dae98-118">La formule remplit la colonne tout entière et une valeur est calculée pour chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="dae98-118">The entire column is populated with the formula, and a value is calculated for each row.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="dae98-119">Vous pouvez utiliser la saisie semi-automatique des formules DAX au milieu d'une formule existante avec les fonctions imbriquées.</span><span class="sxs-lookup"><span data-stu-id="dae98-119">You can use DAX Formula AutoComplete in the middle of an existing formula with nested functions.</span></span> <span data-ttu-id="dae98-120">Le texte immédiatement avant le point d'insertion est utilisé pour afficher des valeurs dans la liste déroulante, et tout le texte après le point d'insertion reste inchangé.</span><span class="sxs-lookup"><span data-stu-id="dae98-120">The text immediately before the insertion point is used to display values in the drop-down list, and all of the text after the insertion point remains unchanged.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dae98-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dae98-121">See Also</span></span>  
 <span data-ttu-id="dae98-122">[Colonnes calculées &#40;&#41;tabulaires SSAS](ssas-calculated-columns.md) </span><span class="sxs-lookup"><span data-stu-id="dae98-122">[Calculated Columns &#40;SSAS Tabular&#41;](ssas-calculated-columns.md) </span></span>  
 [<span data-ttu-id="dae98-123">Mesures &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="dae98-123">Measures &#40;SSAS Tabular&#41;</span></span>](measures-ssas-tabular.md)  
  
  
