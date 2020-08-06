---
title: Ajouter, déplacer ou supprimer une table, une matrice ou une liste (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4b97c470-cde0-4bb1-a46e-5f5f5553feaa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 43941639a41c897a49cd34662b74de26a27e3f07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707144"
---
# <a name="add-move-or-delete-a-table-matrix-or-list-report-builder-and-ssrs"></a><span data-ttu-id="c2ce6-102">Ajouter, déplacer ou supprimer une table, une matrice ou une liste (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="c2ce6-102">Add, Move, or Delete a Table, Matrix, or List (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c2ce6-103">Une région de données affiche les données d'un dataset de rapport.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-103">A data region displays data from a report dataset.</span></span> <span data-ttu-id="c2ce6-104">Les tables, matrices, listes, graphiques et jauges sont des régions de données.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-104">Data regions include table, matrix, list, chart, and gauge.</span></span> <span data-ttu-id="c2ce6-105">Pour imbriquer une région de données dans une autre, ajoutez une à une chaque région de données, puis faites glisser la région de données enfant dans la région de données parente.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-105">To nest one data region inside another, add each data region separately, and then drag the child data region onto the parent data region.</span></span>  
  
 <span data-ttu-id="c2ce6-106">Le moyen le plus simple d'ajouter une région de données de type tableau ou matrice à votre rapport est d'exécuter l'Assistant Nouveau tableau ou nouvelle matrice.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-106">The simplest way to add a table or matrix data region to your report is to run the New Table or New Matrix Wizard.</span></span> <span data-ttu-id="c2ce6-107">Ces Assistants vous aideront à sélectionner une connexion à une source de données, à organiser les champs et à choisir une disposition et un style.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-107">These wizards will guide you through the process of choosing a connection to a data source, arranging fields, and choosing the layout and style.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c2ce6-108">L'Assistant est disponible uniquement dans le Générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-108">The wizard is available only in Report Builder.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-table-or-matrix-to-a-report-by-using-the-new-table-or-new-matrix-wizard"></a><span data-ttu-id="c2ce6-109">Pour ajouter une table ou une matrice à un rapport à l'aide de l'Assistant Table ou Matrice</span><span class="sxs-lookup"><span data-stu-id="c2ce6-109">To add a table or matrix to a report by using the New Table or New Matrix Wizard</span></span>  
  
1.  <span data-ttu-id="c2ce6-110">Sous l’onglet **Insérer** , cliquez sur **Tableau** ou **Matrice**, puis sur **Assistant Tableau** ou **Assistant Matrice**.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-110">On the **Insert** tab, click **Table** or **Matrix**, and then click **Table Wizard** or **Matrix Wizard**.</span></span>  
  
2.  <span data-ttu-id="c2ce6-111">Suivez les étapes de l’Assistant **newTable** ou **nouvelle matrice** .</span><span class="sxs-lookup"><span data-stu-id="c2ce6-111">Follow the steps in the **NewTable** or **New Matrix** wizard.</span></span>  
  
3.  <span data-ttu-id="c2ce6-112">Sous l’onglet **Accueil** , cliquez sur **Exécuter** pour visualiser le rapport rendu.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-112">On the **Home** tab, click **Run** to see the rendered report.</span></span>  
  
4.  <span data-ttu-id="c2ce6-113">Sous l’onglet **Exécuter** , cliquez sur **Conception** pour continuer à utiliser le rapport.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-113">On the **Run** tab, click **Design** to continue working on the report.</span></span>  
  
### <a name="to-add-a-data-region"></a><span data-ttu-id="c2ce6-114">Pour ajouter une région de données</span><span class="sxs-lookup"><span data-stu-id="c2ce6-114">To add a data region</span></span>  
  
1.  <span data-ttu-id="c2ce6-115">Sur le **ruban**, dans le groupe **Régions de données** , cliquez sur la région de données à ajouter.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-115">On the **Ribbon**, in the **Data Regions** group, click the data region to add.</span></span>  
  
2.  <span data-ttu-id="c2ce6-116">Cliquez sur l'aire de conception, puis faites glisser la souris pour créer une zone de la taille voulue pour la région de données.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-116">Click the design surface, and then drag to create a box that is the desired size of the data region.</span></span>  
  
3.  <span data-ttu-id="c2ce6-117">Faites glisser un champ de dataset de rapport à partir du volet des données de rapportvers une cellule de la région de données.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-117">Drag a report dataset field from the Report Data pane onto a data region cell.</span></span> <span data-ttu-id="c2ce6-118">La région de données est maintenant liée à des données du dataset de rapport.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-118">The data region is now bound to data from the report dataset.</span></span>  
  
### <a name="to-select-a-data-region"></a><span data-ttu-id="c2ce6-119">Pour sélectionner une région de données</span><span class="sxs-lookup"><span data-stu-id="c2ce6-119">To select a data region</span></span>  
  
-   <span data-ttu-id="c2ce6-120">Dans le cas d'une région de données de tableau matriciel, cliquez avec le bouton droit sur la poignée d'angle.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-120">For a tablix data region, right-click the corner handle.</span></span> <span data-ttu-id="c2ce6-121">Dans le cas d'une région de données de graphique ou jauge, cliquez dans la région de données.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-121">For a chart or gauge data region, click in the data region.</span></span>  
  
     <span data-ttu-id="c2ce6-122">Une poignée de sélection et huit poignées de redimensionnement apparaissent.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-122">A selection handle and eight resizing handles appear.</span></span>  
  
     <span data-ttu-id="c2ce6-123">Dans le cas d’une région de données imbriquée, cliquez dedans avec le bouton droit, cliquez sur **Sélectionner**, puis sélectionnez l’élément de rapport voulu.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-123">For nested data regions, right-click in the nested data region, click **Select**, and then select the report item you want.</span></span> <span data-ttu-id="c2ce6-124">Pour vérifier quel élément de rapport est sélectionné, utilisez le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-124">To verify which report item is selected, use the Properties pane.</span></span> <span data-ttu-id="c2ce6-125">Le nom de l'élément sélectionné dans l'aire de conception apparaît dans la barre d'outils du volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-125">The name of the selected item on the design surface appears in the toolbar of the Properties pane.</span></span>  
  
### <a name="to-move-a-data-region"></a><span data-ttu-id="c2ce6-126">Pour déplacer une région de données</span><span class="sxs-lookup"><span data-stu-id="c2ce6-126">To move a data region</span></span>  
  
-   <span data-ttu-id="c2ce6-127">Pour déplacer une région de données, cliquez sur la poignée de sélection de la région de données et faites-la glisser.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-127">To move a data region, click the selection handle of the data region and drag it.</span></span> <span data-ttu-id="c2ce6-128">Utilisez les lignes d'alignement pour l'aligner aux éléments de rapport existants.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-128">Use snaplines to align it to existing report items.</span></span>  
  
     <span data-ttu-id="c2ce6-129">Si la règle n’est pas visible, cliquez sur l’onglet Affichage et sélectionnez l’option **Règle** .</span><span class="sxs-lookup"><span data-stu-id="c2ce6-129">If the ruler is not visible, click the View tab and select the **Ruler** option.</span></span>  
  
     <span data-ttu-id="c2ce6-130">Vous pouvez aussi utiliser les touches de direction pour déplacer la région de données sélectionnée sur l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-130">Alternatively, use the arrow keys to move the selected data region on the design surface.</span></span>  
  
### <a name="to-delete-a-data-region"></a><span data-ttu-id="c2ce6-131">Pour supprimer une région de données</span><span class="sxs-lookup"><span data-stu-id="c2ce6-131">To delete a data region</span></span>  
  
-   <span data-ttu-id="c2ce6-132">Sélectionnez la région de données, cliquez dedans avec le bouton droit, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-132">Select the data region, right-click in the data region, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2ce6-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c2ce6-133">See Also</span></span>  
 <span data-ttu-id="c2ce6-134">[Région de données de tableau matriciel &#40;Générateur de rapports et SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c2ce6-134">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c2ce6-135">[Tables &#40;Générateur de rapports et SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c2ce6-135">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c2ce6-136">[Matrices &#40;Générateur de rapports et SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c2ce6-136">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c2ce6-137">[Répertorie &#40;Générateur de rapports et SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c2ce6-137">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c2ce6-138">Tables, matrices et listes &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c2ce6-138">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
