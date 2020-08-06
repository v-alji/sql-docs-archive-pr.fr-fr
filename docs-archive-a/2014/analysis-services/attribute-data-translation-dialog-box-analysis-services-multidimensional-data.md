---
title: Boîte de dialogue traduction de données d’attribut (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensiondesigner.dimensionstoragesettings.f1
helpviewer_keywords:
- Attribute Data Translation dialog box
ms.assetid: bed286de-1e9b-49de-b09e-3cd076aba152
author: minewiskan
ms.author: owend
ms.openlocfilehash: b61022ec2cb8726fc034e13a0d63e432df6ec151
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602623"
---
# <a name="attribute-data-translation-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="06c65-102">Boîte de dialogue Traduction de données d'attribut (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="06c65-102">Attribute Data Translation Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="06c65-103">Utilisez la boîte de dialogue **Traduction de données d’attribut** pour configurer la colonne qui contient les données de sous-titre de traduction, ainsi que l’ordre de classement et de tri à utiliser avec les données traduites.</span><span class="sxs-lookup"><span data-stu-id="06c65-103">Use the **Attribute Data Translation** dialog box to set the column that contains the translation caption data, as well as the collation and sort order to be used with the translated data.</span></span> <span data-ttu-id="06c65-104">Pour afficher la boîte de dialogue **Traduction de données d’attribut** , vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="06c65-104">You can display the **Attribute Data Translation** dialog box by:</span></span>  
  
-   <span data-ttu-id="06c65-105">soit cliquer sur **Nouvelle colonne de légende** ou **Modifier la colonne de légende** dans le volet **Barre d’outils** de l’onglet **Traductions** du **Concepteur de dimensions**;</span><span class="sxs-lookup"><span data-stu-id="06c65-105">Clicking **New caption column** or **Edit caption column** from the **Toolbar** pane on the **Translations** tab of **Dimension Designer**.</span></span>  
  
-   <span data-ttu-id="06c65-106">soit cliquer avec le bouton droit sur le volet des **détails des traductions** de l’onglet **Traductions** du **Concepteur de dimensions** et sélectionner **Nouvelle colonne de légende** ou **Modifier la colonne de légende**.</span><span class="sxs-lookup"><span data-stu-id="06c65-106">Right-clicking the **Translation Details** pane on the **Translations** tab of **Dimension Designer** and selecting **New caption column** or **Edit caption column**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="06c65-107">Options</span><span class="sxs-lookup"><span data-stu-id="06c65-107">Options</span></span>  
 <span data-ttu-id="06c65-108">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="06c65-108">**Attribute**</span></span>  
 <span data-ttu-id="06c65-109">Affiche l'attribut sélectionné.</span><span class="sxs-lookup"><span data-stu-id="06c65-109">Displays the selected attribute.</span></span>  
  
 <span data-ttu-id="06c65-110">**Langage**</span><span class="sxs-lookup"><span data-stu-id="06c65-110">**Language**</span></span>  
 <span data-ttu-id="06c65-111">Affiche la langue sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="06c65-111">Displays the selected language.</span></span>  
  
 <span data-ttu-id="06c65-112">**Légende traduite**</span><span class="sxs-lookup"><span data-stu-id="06c65-112">**Translated caption**</span></span>  
 <span data-ttu-id="06c65-113">Configure la légende traduite en cours pour l'attribut sélectionné.</span><span class="sxs-lookup"><span data-stu-id="06c65-113">Sets the current translated caption for the selected attribute.</span></span>  
  
 <span data-ttu-id="06c65-114">**Colonnes de traduction**</span><span class="sxs-lookup"><span data-stu-id="06c65-114">**Translation columns**</span></span>  
 <span data-ttu-id="06c65-115">Définit la colonne où les données de sous-titre de traduction sont enregistrées.</span><span class="sxs-lookup"><span data-stu-id="06c65-115">Sets the column where the translation caption data is stored.</span></span> <span data-ttu-id="06c65-116">Vous pouvez sélectionner une seule colonne.</span><span class="sxs-lookup"><span data-stu-id="06c65-116">Only one column can be selected.</span></span> <span data-ttu-id="06c65-117">Toutes les tables associées référencées par la table primaire de dimension sont affichées.</span><span class="sxs-lookup"><span data-stu-id="06c65-117">All related tables that are referred to by the primary dimension table will be displayed.</span></span>  
  
 <span data-ttu-id="06c65-118">**Indicateur de classement**</span><span class="sxs-lookup"><span data-stu-id="06c65-118">**Collation designator**</span></span>  
 <span data-ttu-id="06c65-119">Définit l'indicateur de classement pour l'attribut sélectionné.</span><span class="sxs-lookup"><span data-stu-id="06c65-119">Sets the collation designator for the selected attribute.</span></span> <span data-ttu-id="06c65-120">Le classement Windows est sélectionné par défaut.</span><span class="sxs-lookup"><span data-stu-id="06c65-120">By default, the current Windows collation is selected.</span></span> <span data-ttu-id="06c65-121">Cliquez sur la flèche vers le bas pour effectuer votre sélection parmi les classements disponibles.</span><span class="sxs-lookup"><span data-stu-id="06c65-121">Click the down arrow to select from the available collations.</span></span>  
  
 <span data-ttu-id="06c65-122">**Binaire**</span><span class="sxs-lookup"><span data-stu-id="06c65-122">**Binary**</span></span>  
 <span data-ttu-id="06c65-123">Sélectionnez cette option pour trier et comparer les données en fonction des modèles des bits définis pour chaque caractère.</span><span class="sxs-lookup"><span data-stu-id="06c65-123">Select this option to sort and compare data based on the bit patterns defined for each character.</span></span> <span data-ttu-id="06c65-124">L'ordre de tri binaire respecte la casse, c'est-à-dire que les minuscules précèdent les majuscules ; il respecte également les accents.</span><span class="sxs-lookup"><span data-stu-id="06c65-124">Binary sort order is case-sensitive, that is, lowercase precedes uppercase, and accent-sensitive.</span></span> <span data-ttu-id="06c65-125">Il s'agit de l'ordre de tri le plus rapide.</span><span class="sxs-lookup"><span data-stu-id="06c65-125">This is the fastest sorting order.</span></span>  
  
 <span data-ttu-id="06c65-126">Si cette option n'est pas activée, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] respecte les règles de tri et de comparaison définies dans les dictionnaires pour la langue ou l'alphabet associé.</span><span class="sxs-lookup"><span data-stu-id="06c65-126">If this option is not selected, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] follows sorting and comparison rules as defined in dictionaries for the associated language or alphabet.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="06c65-127">Si cette option est sélectionnée, les options **Respecter la casse**, **Respecter les accents**, **Respecter le jeu de caractères Kana**et **Respecter la largeur** sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="06c65-127">If this option is selected, the **Case sensitive**, **Accent sensitive**, **Kana sensitive**, and **Width sensitive** options are disabled.</span></span>  
  
 <span data-ttu-id="06c65-128">**Respecter la casse**</span><span class="sxs-lookup"><span data-stu-id="06c65-128">**Case sensitive**</span></span>  
 <span data-ttu-id="06c65-129">Sélectionnez cette option pour trier et comparer les données d'après les règles du dictionnaire de la langue ou de l'alphabet associé et pour faire la distinction entre les majuscules et les minuscules.</span><span class="sxs-lookup"><span data-stu-id="06c65-129">Select this option to sort and compare data based on the dictionary rules provided for the associated language or alphabet, and to distinguish between uppercase and lowercase letters.</span></span>  
  
 <span data-ttu-id="06c65-130">Si cette option n’est pas sélectionnée, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] considère qu’il n’y a pas de différences entre les lettres majuscules et minuscules.</span><span class="sxs-lookup"><span data-stu-id="06c65-130">If not selected, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] considers the uppercase and lowercase versions of letters to be equal.</span></span> [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]<span data-ttu-id="06c65-131">ne définit pas si les lettres minuscules sont triées en minuscules ou supérieures par rapport aux majuscules lorsque la **casse** n’est pas sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="06c65-131">does not define whether lowercase letters sort lower or higher in relation to uppercase letters when **Case-sensitive** is not selected.</span></span>  
  
 <span data-ttu-id="06c65-132">**Respecter les accents**</span><span class="sxs-lookup"><span data-stu-id="06c65-132">**Accent sensitive**</span></span>  
 <span data-ttu-id="06c65-133">Sélectionnez cette option pour trier et comparer les données d'après les règles du dictionnaire de la langue ou de l'alphabet associé et pour faire la distinction entre les lettres accentuées ou non.</span><span class="sxs-lookup"><span data-stu-id="06c65-133">Select this option to sort and compare data based on the dictionary rules provided for the associated language or alphabet, and to distinguish between accented and unaccented characters.</span></span> <span data-ttu-id="06c65-134">Par exemple, « a » n'est pas équivalent à « á ».</span><span class="sxs-lookup"><span data-stu-id="06c65-134">For example, 'a' is not equal to 'á'.</span></span>  
  
 <span data-ttu-id="06c65-135">Si l’option est désactivée, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] considère qu’il n’y a pas de différences entre les lettres accentuées et non accentuées.</span><span class="sxs-lookup"><span data-stu-id="06c65-135">If not selected, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] considers the accented and unaccented versions of letters to be equal.</span></span>  
  
 <span data-ttu-id="06c65-136">**Respecter le jeu de caractères Kana**</span><span class="sxs-lookup"><span data-stu-id="06c65-136">**Kana sensitive**</span></span>  
 <span data-ttu-id="06c65-137">Sélectionnez cette option pour trier et comparer les données d'après les règles du dictionnaire de la langue ou de l'alphabet associé et pour faire la distinction entre les deux types de caractères japonais Kana : Hiragana et Katakana.</span><span class="sxs-lookup"><span data-stu-id="06c65-137">Select this option to sort and compare data based on the dictionary rules provided for the associated language or alphabet, and to distinguish between the two types of Japanese kana characters: Hiragana and Katakana.</span></span>  
  
 <span data-ttu-id="06c65-138">Si l'option est désactivée, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] considère qu'il n'y a pas de différences entre les caractères Hiragana et Katakana.</span><span class="sxs-lookup"><span data-stu-id="06c65-138">If not selected, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] considers Hiragana and Katakana characters to be equal.</span></span>  
  
 <span data-ttu-id="06c65-139">**Respecter la largeur**</span><span class="sxs-lookup"><span data-stu-id="06c65-139">**Width sensitive**</span></span>  
 <span data-ttu-id="06c65-140">Sélectionnez cette option pour trier et comparer les données d'après les règles du dictionnaire de la langue ou de l'alphabet associé et pour faire la distinction entre un caractère sur un octet (demi-chasse) et le même caractère représenté sur deux octets (pleine chasse).</span><span class="sxs-lookup"><span data-stu-id="06c65-140">Select this option to sort and compare data based on the dictionary rules provided for the associated language or alphabet, and to distinguish between a single-byte character (half-width) and the same character when represented as a double-byte character (full-width).</span></span>  
  
 <span data-ttu-id="06c65-141">Si l'option est désactivée, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] considère qu'il n'y a pas de différences de représentation entre les caractères codés sur un ou deux octets.</span><span class="sxs-lookup"><span data-stu-id="06c65-141">If not selected, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] considers the single-byte and double-byte representation of the same character to be equal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06c65-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="06c65-142">See Also</span></span>  
 <span data-ttu-id="06c65-143">[Analysis Services les concepteurs et les boîtes de dialogue &#40;les données multidimensionnelles&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="06c65-143">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="06c65-144">Détails de la traduction &#40;onglet traductions, concepteur de dimensions&#41; &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="06c65-144">Translation Details &#40;Translations Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](translation-details-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
