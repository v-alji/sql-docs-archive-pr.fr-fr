---
title: Ajouter, déplacer ou supprimer une zone de texte (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f042cf81-d933-4ac7-9287-c074a46bde98
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cd85415fd2f0bac2a37b3fbda06795e10f351b19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707143"
---
# <a name="add-move-or-delete-a-text-box-report-builder-and-ssrs"></a><span data-ttu-id="643a0-102">Ajouter, déplacer ou supprimer une zone de texte (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="643a0-102">Add, Move, or Delete a Text Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="643a0-103">Les zones de texte sont les éléments de rapport les plus couramment utilisés dans les rapports.</span><span class="sxs-lookup"><span data-stu-id="643a0-103">Text boxes are the most commonly used report item in reports.</span></span> <span data-ttu-id="643a0-104">Vous pouvez ajouter une zone de texte au corps du rapport pour afficher des informations telles que les titres, les choix de paramètres, les champs prédéfinis et les dates.</span><span class="sxs-lookup"><span data-stu-id="643a0-104">You can add a text box to the report body to display information such as titles, parameter choices, built-in fields, and dates.</span></span>  
  
 <span data-ttu-id="643a0-105">Chaque cellule dans une table ou une matrice est réellement une zone de texte.</span><span class="sxs-lookup"><span data-stu-id="643a0-105">Every cell in a table or matrix is really a text box.</span></span> <span data-ttu-id="643a0-106">Les données affichées dans un rapport avec des tables et des matrices sont presque toutes le fruit de l'évaluation par le processeur de rapports du contenu de chaque zone de texte du rapport.</span><span class="sxs-lookup"><span data-stu-id="643a0-106">Almost all report data displayed in a report with tables and matrices is the result of the report processor evaluating the contents of each text box in the report.</span></span> <span data-ttu-id="643a0-107">De ce fait, vous pouvez mettre en forme des cellules de la même façon que d'autres zones de texte en dehors de la région de données.</span><span class="sxs-lookup"><span data-stu-id="643a0-107">As such, you can format cells in the same way you would format other text boxes outside the data region.</span></span>  
  
 <span data-ttu-id="643a0-108">Pour ajouter une zone de texte à une région de données de liste, vous devez d'abord ajouter la zone de texte, puis la faire glisser vers la liste.</span><span class="sxs-lookup"><span data-stu-id="643a0-108">To add a text box to a list data region, you must first add the text box and then drag it into the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="643a0-109">Lorsque vous cliquez sur une zone de texte, vous modifiez immédiatement le texte contenu dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="643a0-109">When you click a text box, you're immediately editing the text in the text box.</span></span> <span data-ttu-id="643a0-110">Pour sélectionner la zone de texte en elle-même et non le texte contenue dans celle-ci, appuyez sur Échap.</span><span class="sxs-lookup"><span data-stu-id="643a0-110">To select the text box itself, not the text in it, press ESC.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-text-box"></a><span data-ttu-id="643a0-111">Pour ajouter une zone de texte</span><span class="sxs-lookup"><span data-stu-id="643a0-111">To add a text box</span></span>  
  
1.  <span data-ttu-id="643a0-112">Sous l'onglet **Insérer** en mode Conception, cliquez sur **Zone de texte**.</span><span class="sxs-lookup"><span data-stu-id="643a0-112">On the **Insert** tab in Design view, click **Text Box**.</span></span>  
  
2.  <span data-ttu-id="643a0-113">Cliquez sur l'aire de conception, puis faites glisser la souris pour créer une zone de la taille voulue pour la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="643a0-113">On the design surface, click and then drag a box to the desired size of the text box.</span></span> <span data-ttu-id="643a0-114">Une autre solution consiste à cliquer sur l'aire de conception pour créer une zone de texte de taille par défaut.</span><span class="sxs-lookup"><span data-stu-id="643a0-114">Alternatively, click the design surface to create a text box of default size.</span></span>  
  
### <a name="to-add-a-text-box-in-a-list"></a><span data-ttu-id="643a0-115">Pour ajouter une zone de texte dans une liste</span><span class="sxs-lookup"><span data-stu-id="643a0-115">To add a text box in a list</span></span>  
  
1.  <span data-ttu-id="643a0-116">Sous l'onglet **Insérer** en mode création de rapport, cliquez sur **Liste**.</span><span class="sxs-lookup"><span data-stu-id="643a0-116">On the **Insert** tab in report design view, click **List**.</span></span>  
  
2.  <span data-ttu-id="643a0-117">Cliquez sur l'aire de conception, puis faites glisser la souris pour créer une zone de la taille voulue pour la liste.</span><span class="sxs-lookup"><span data-stu-id="643a0-117">On the design surface, click and then drag a box to the desired size of the list.</span></span> <span data-ttu-id="643a0-118">Une autre solution consiste à cliquer sur l'aire de conception pour créer une liste de taille par défaut.</span><span class="sxs-lookup"><span data-stu-id="643a0-118">Alternatively, click the design surface to create a list of default size.</span></span>  
  
3.  <span data-ttu-id="643a0-119">Sous l'onglet **Insérer** , cliquez sur **Zone de texte**.</span><span class="sxs-lookup"><span data-stu-id="643a0-119">On the **Insert** tab, click **Text Box**.</span></span>  
  
4.  <span data-ttu-id="643a0-120">Sur l'aire de conception, cliquez et faites glisser la souris pour créer une zone de la taille voulue pour la zone de texte dans la liste ajoutée à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="643a0-120">On the design surface, click and then drag a box to the desired size of the text box inside the list you added in step 1.</span></span> <span data-ttu-id="643a0-121">Une autre solution consiste à cliquer sur l'aire de conception dans la liste pour créer une zone de texte de taille par défaut.</span><span class="sxs-lookup"><span data-stu-id="643a0-121">Alternatively, click the design surface inside the list to create a text box of default size.</span></span>  
  
5.  <span data-ttu-id="643a0-122">Pour vérifier que la zone de texte est correctement imbriquée dans la liste, sélectionnez la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="643a0-122">To confirm the text box is correctly nested inside the list, select the text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="643a0-123">Si vous cliquez dans la zone de texte en mode édition, appuyez sur Échap pour sélectionner la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="643a0-123">If you click in the text box and are in edit mode, press ESC to select the text box.</span></span>  
  
6.  <span data-ttu-id="643a0-124">Dans le volet Propriétés, vérifiez que la propriété **Parent** est le rectangle qui été automatiquement ajouté à la région de données de la liste.</span><span class="sxs-lookup"><span data-stu-id="643a0-124">In the Properties pane, verify that the **Parent** property is the rectangle that was automatically added to the list data region.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="643a0-125">Si le volet Propriétés n’est pas visible, cochez **Propriétés** sous l’onglet **Affichage** .</span><span class="sxs-lookup"><span data-stu-id="643a0-125">If the Properties pane is not visible, check **Properties** on the **View** tab.</span></span>  
  
### <a name="to-move-a-text-box"></a><span data-ttu-id="643a0-126">Pour déplacer une zone de texte</span><span class="sxs-lookup"><span data-stu-id="643a0-126">To move a text box</span></span>  
  
1.  <span data-ttu-id="643a0-127">En mode création de rapport, cliquez sur un espace vide à l'intérieur de la zone de texte pour la sélectionner.</span><span class="sxs-lookup"><span data-stu-id="643a0-127">In report design view, click any empty space within the text box to select the text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="643a0-128">Si vous cliquez dans la zone de texte en mode édition, appuyez sur Échap pour sélectionner la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="643a0-128">If you click in the text box and are in edit mode, press ESC to select the text box.</span></span>  
  
2.  <span data-ttu-id="643a0-129">Cliquez sur la poignée de la zone de texte et faites glisser la zone de texte vers le nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="643a0-129">Click the text box handle and drag the text box to the new location.</span></span> <span data-ttu-id="643a0-130">Vous pouvez également utiliser les touches de direction pour déplacer une zone de texte sélectionnée horizontalement ou verticalement.</span><span class="sxs-lookup"><span data-stu-id="643a0-130">Alternatively, you can use the arrow keys to move a selected text box horizontally or vertically.</span></span> <span data-ttu-id="643a0-131">Pour déplacer la zone de texte par incréments plus petits sur l'aire de conception, maintenez la touche CTRL enfoncée et utilisez les touches de direction.</span><span class="sxs-lookup"><span data-stu-id="643a0-131">To move the text box in smaller increments on the design surface, hold down CTRL plus the arrow keys.</span></span>  
  
### <a name="to-delete-a-text-box"></a><span data-ttu-id="643a0-132">Pour supprimer une zone de texte</span><span class="sxs-lookup"><span data-stu-id="643a0-132">To delete a text box</span></span>  
  
1.  <span data-ttu-id="643a0-133">En mode création de rapport, cliquez avec le bouton droit sur un espace vide à l’intérieur de la zone de texte pour la sélectionner, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="643a0-133">In report design view, right-click any empty space within the text box to select it, and then click **Delete**.</span></span> <span data-ttu-id="643a0-134">Une autre solution consiste à cliquer sur un espace vide à l'intérieur de la zone de texte, puis à appuyer sur Suppr.</span><span class="sxs-lookup"><span data-stu-id="643a0-134">Alternatively, click any empty space within the text box, and then press DELETE.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="643a0-135">Si vous cliquez dans la zone de texte en mode édition, appuyez sur Échap pour sélectionner la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="643a0-135">If you click in the text box and are in edit mode, press ESC to select the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="643a0-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="643a0-136">See Also</span></span>  
 <span data-ttu-id="643a0-137">[Zones de texte &#40;Générateur de rapports et SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="643a0-137">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="643a0-138">[Expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="643a0-138">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="643a0-139">Raccourcis clavier &#40;Générateur de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="643a0-139">Keyboard Shortcuts &#40;Report Builder&#41;</span></span>](../report-builder/keyboard-shortcuts-report-builder.md)  
  
  
