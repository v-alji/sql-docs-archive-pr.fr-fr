---
title: Avertissements (Concepteur de bases de données) (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.databasedesigner.warnings.f1
ms.assetid: 13f58b4d-f345-4fbc-ae2d-b3c8290a797d
author: minewiskan
ms.author: owend
ms.openlocfilehash: bf635460187fe56f4811de5090cada002ea8ca3b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603641"
---
# <a name="warnings-database-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="7d8a8-102">Avertissements (Concepteur de bases de données) (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="7d8a8-102">Warnings (Database Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="7d8a8-103">L’onglet **Avertissements** permet d’afficher et d’ignorer des règles globalement, et d’afficher et de réactiver des instances spécifiques d’avertissements ignorés.</span><span class="sxs-lookup"><span data-stu-id="7d8a8-103">Use the **Warnings** tab to view and dismiss rules globally, and to view and re-enable specific instances of dismissed warnings.</span></span> <span data-ttu-id="7d8a8-104">L'onglet **Avertissements** affiche deux grilles : **Règles d'avertissements de conception** et **Avertissements ignorés**.</span><span class="sxs-lookup"><span data-stu-id="7d8a8-104">The **Warnings** tab displays two grids: **Design Warning Rules** and **Dismissed Warnings**.</span></span>  
  
 <span data-ttu-id="7d8a8-105">**Pour afficher l'onglet Avertissements**</span><span class="sxs-lookup"><span data-stu-id="7d8a8-105">**To display the Warnings tab**</span></span>  
  
1.  <span data-ttu-id="7d8a8-106">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez un projet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7d8a8-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="7d8a8-107">Dans **l’Explorateur de solutions**, cliquez avec le bouton droit sur le projet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , puis cliquez sur **Modifier la base de données**, puis sur l’onglet **Avertissements** .</span><span class="sxs-lookup"><span data-stu-id="7d8a8-107">In **Solution Explorer**, right-click the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, click **Edit Database**, and then click the **Warnings** tab.</span></span>  
  
## <a name="design-warning-rules-grid"></a><span data-ttu-id="7d8a8-108">Grille Règles d'avertissements de conception</span><span class="sxs-lookup"><span data-stu-id="7d8a8-108">Design Warning Rules Grid</span></span>  
 <span data-ttu-id="7d8a8-109">La grille **Règles d'avertissements de conception** affiche toutes les règles d'avertissements de conception.</span><span class="sxs-lookup"><span data-stu-id="7d8a8-109">The **Design Warning Rules** grid displays all the design warning rules.</span></span> <span data-ttu-id="7d8a8-110">Cette grille contrôle également les règles activées pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="7d8a8-110">This grid also controls which rules are enabled for the database.</span></span> <span data-ttu-id="7d8a8-111">Pour activer ou désactiver une règle d'avertissement, activez ou désactivez la case à cocher correspondante.</span><span class="sxs-lookup"><span data-stu-id="7d8a8-111">To enable or disable a warning rule, select or clear its check box.</span></span>  
  
 <span data-ttu-id="7d8a8-112">Les colonnes de la grille **Règles d'avertissements de conception** sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="7d8a8-112">The **Design Warning Rules** grid has the following columns:</span></span>  
  
 <span data-ttu-id="7d8a8-113">**Description**</span><span class="sxs-lookup"><span data-stu-id="7d8a8-113">**Description**</span></span>  
 <span data-ttu-id="7d8a8-114">Affiche le nom de la règle.</span><span class="sxs-lookup"><span data-stu-id="7d8a8-114">Displays the name of the rule.</span></span> <span data-ttu-id="7d8a8-115">Les règles sont regroupées par catégorie.</span><span class="sxs-lookup"><span data-stu-id="7d8a8-115">Rules are grouped by category.</span></span>  
  
 <span data-ttu-id="7d8a8-116">**Importance**</span><span class="sxs-lookup"><span data-stu-id="7d8a8-116">**Importance**</span></span>  
 <span data-ttu-id="7d8a8-117">Affiche l'importance affectée à la règle.</span><span class="sxs-lookup"><span data-stu-id="7d8a8-117">Displays the importance assigned to the rule.</span></span>  
  
 <span data-ttu-id="7d8a8-118">**Commentaires**</span><span class="sxs-lookup"><span data-stu-id="7d8a8-118">**Comments**</span></span>  
 <span data-ttu-id="7d8a8-119">(Facultatif) Permet à l'utilisateur de taper un commentaire qui explique pourquoi vous ignorez l'avertissement.</span><span class="sxs-lookup"><span data-stu-id="7d8a8-119">(Optional) Allows the user to type a comment that explains why you are dismissing the warning.</span></span>  
  
## <a name="dismissed-warnings-grid"></a><span data-ttu-id="7d8a8-120">Grille Avertissements ignorés</span><span class="sxs-lookup"><span data-stu-id="7d8a8-120">Dismissed Warnings Grid</span></span>  
 <span data-ttu-id="7d8a8-121">La grille **Avertissements ignorés** affiche toutes les occurrences d'avertissements spécifiques qui ont été ignorées à partir de la **Liste d'erreurs**.</span><span class="sxs-lookup"><span data-stu-id="7d8a8-121">The **Dismissed Warnings** grid displays all specific warning occurrences that have been dismissed from the **Error List**.</span></span> <span data-ttu-id="7d8a8-122">Pour réactiver un avertissement, sélectionnez-le dans la grille, puis cliquez sur **Réactiver**.</span><span class="sxs-lookup"><span data-stu-id="7d8a8-122">To re-enable a warning, select it in the grid, and then click **Re-enable**.</span></span>  
  
 <span data-ttu-id="7d8a8-123">Les colonnes de la grille **Avertissements ignorés** sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="7d8a8-123">The **Dismissed Warnings** grid has the following :</span></span>  
  
 <span data-ttu-id="7d8a8-124">**Object**</span><span class="sxs-lookup"><span data-stu-id="7d8a8-124">**Object**</span></span>  
 <span data-ttu-id="7d8a8-125">Affiche une icône qui représente le type d'objet et le nom d'objet.</span><span class="sxs-lookup"><span data-stu-id="7d8a8-125">Displays an icon that represents the object type and the object name.</span></span>  
  
 <span data-ttu-id="7d8a8-126">**Type**</span><span class="sxs-lookup"><span data-stu-id="7d8a8-126">**Type**</span></span>  
 <span data-ttu-id="7d8a8-127">Affiche le type d'objet.</span><span class="sxs-lookup"><span data-stu-id="7d8a8-127">Displays the object type.</span></span>  
  
 <span data-ttu-id="7d8a8-128">**Description**</span><span class="sxs-lookup"><span data-stu-id="7d8a8-128">**Description**</span></span>  
 <span data-ttu-id="7d8a8-129">Affiche le nom de la règle.</span><span class="sxs-lookup"><span data-stu-id="7d8a8-129">Displays the name of the rule.</span></span>  
  
 <span data-ttu-id="7d8a8-130">**Importance**</span><span class="sxs-lookup"><span data-stu-id="7d8a8-130">**Importance**</span></span>  
 <span data-ttu-id="7d8a8-131">Affiche l'importance affectée à la règle.</span><span class="sxs-lookup"><span data-stu-id="7d8a8-131">Displays the importance assigned to the rule.</span></span>  
  
 <span data-ttu-id="7d8a8-132">**Commentaires**</span><span class="sxs-lookup"><span data-stu-id="7d8a8-132">**Comments**</span></span>  
 <span data-ttu-id="7d8a8-133">Affiche le commentaire qui a été entré lorsque l'avertissement a été ignoré.</span><span class="sxs-lookup"><span data-stu-id="7d8a8-133">Displays the comment that was entered when the warning was dismissed.</span></span> <span data-ttu-id="7d8a8-134">Vous pouvez ajouter ou modifier un commentaire ici.</span><span class="sxs-lookup"><span data-stu-id="7d8a8-134">You can add or modify a comment here.</span></span>  
  
 <span data-ttu-id="7d8a8-135">**Réactiver**</span><span class="sxs-lookup"><span data-stu-id="7d8a8-135">**Re-enable**</span></span>  
 <span data-ttu-id="7d8a8-136">Réactive les avertissements sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="7d8a8-136">Re-enables the selected warnings.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7d8a8-137">Si un objet a un avertissement mais que son état est non valide ou que cet objet a été supprimé manuellement du projet, une icône d'erreur apparaît à côté de l'avertissement dans la liste.</span><span class="sxs-lookup"><span data-stu-id="7d8a8-137">If an object has a warning, but the object is in an invalid state or was manually removed from the project, an error icon appears next to the warning in the list.</span></span> <span data-ttu-id="7d8a8-138">Pour ignorer l’avertissement, sélectionnez-le, puis cliquez sur **Ignorer**.</span><span class="sxs-lookup"><span data-stu-id="7d8a8-138">To dismiss the warning, select it and then click **Re-enable**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d8a8-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7d8a8-139">See Also</span></span>  
 <span data-ttu-id="7d8a8-140">[Boîte de dialogue ignorer l’avertissement &#40;Analysis Services-données multidimensionnelles&#41;](dismiss-warning-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="7d8a8-140">[Dismiss Warning Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](dismiss-warning-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="7d8a8-141">Concepteur de base de données &#40;général&#41; &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="7d8a8-141">General &#40;Database Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](general-database-designer-analysis-services-multidimensional-data.md)  
  
  
