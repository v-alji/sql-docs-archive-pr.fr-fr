---
title: Classement, boîte de dialogue (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.definecolumncollation
- vdtsql.chm:65561
ms.assetid: e4020f79-7abf-4839-b9b2-984ef7049817
author: stevestein
ms.author: sstein
ms.openlocfilehash: d551b2ae7ca27250c144afedf13038efd78ad6ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614945"
---
# <a name="collation-dialog-box-visual-database-tools"></a><span data-ttu-id="6913b-102">Boîte de dialogue Classement (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="6913b-102">Collation Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="6913b-103">Cette boîte de dialogue permet de spécifier une séquence de classement pour la colonne.</span><span class="sxs-lookup"><span data-stu-id="6913b-103">This dialog box lets you specify a collation sequence for the column.</span></span> <span data-ttu-id="6913b-104">La séquence de classement est utilisée pour les opérations qui comparent les valeurs de la colonne à une autre colonne ou par rapport à des valeurs constantes.</span><span class="sxs-lookup"><span data-stu-id="6913b-104">A column's collation sequence is used in any operation that compares values of the column to another column or to constant values.</span></span> <span data-ttu-id="6913b-105">Elle affecte également le comportement de certaines fonctions de chaîne, telles que SUBSTRING et CHARINDEX.</span><span class="sxs-lookup"><span data-stu-id="6913b-105">It also affects the behavior of some string functions, such as SUBSTRING and CHARINDEX.</span></span> <span data-ttu-id="6913b-106">Pour une liste complète des effets du paramètre de classement d'une colonne, consultez la documentation sur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6913b-106">For a complete list of the effects of a column's collation setting, see the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] documentation.</span></span>  
  
 <span data-ttu-id="6913b-107">Cette boîte de dialogue apparaît :</span><span class="sxs-lookup"><span data-stu-id="6913b-107">This dialog box appears:</span></span>  
  
-   <span data-ttu-id="6913b-108">Si vous entrez un nom de classement non valide dans le champ **Classement** de l'onglet **Propriétés des colonnes**</span><span class="sxs-lookup"><span data-stu-id="6913b-108">If you enter an invalid collation name in the **Collation** field on the **Column Properties** tab.</span></span>  
  
-   <span data-ttu-id="6913b-109">Si vous cliquez dans le champ **Classement** de l’onglet **Propriétés des colonnes**, puis sur le bouton de sélection ( **...** ) à droite du champ.</span><span class="sxs-lookup"><span data-stu-id="6913b-109">If you click in the **Collation** field on the **Column Properties** tab, and then click the ellipsis button (**...**) to the right of the field.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6913b-110">Options</span><span class="sxs-lookup"><span data-stu-id="6913b-110">Options</span></span>  
 <span data-ttu-id="6913b-111">**Classement SQL**</span><span class="sxs-lookup"><span data-stu-id="6913b-111">**SQL Collation**</span></span>  
 <span data-ttu-id="6913b-112">Choisi parmi les séquences de classement définies par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="6913b-112">Choose among the collation sequences defined by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the drop-down list.</span></span>  
  
 <span data-ttu-id="6913b-113">**Classement Windows**</span><span class="sxs-lookup"><span data-stu-id="6913b-113">**Windows Collation**</span></span>  
 <span data-ttu-id="6913b-114">Choisi parmi les séquences de classement définies par Windows dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="6913b-114">Choose among the collation sequences defined by Windows from the drop-down list.</span></span>  
  
 <span data-ttu-id="6913b-115">**Tri binaire**</span><span class="sxs-lookup"><span data-stu-id="6913b-115">**Binary Sort**</span></span>  
 <span data-ttu-id="6913b-116">Utilise les codes binaires des valeurs de caractères pour les comparaisons.</span><span class="sxs-lookup"><span data-stu-id="6913b-116">Use the binary codes of character values for comparisons.</span></span> <span data-ttu-id="6913b-117">Si vous sélectionnez cette option, certaines options de comparaison alphabétique ne seront plus disponibles.</span><span class="sxs-lookup"><span data-stu-id="6913b-117">If you select this option, certain alphabetic comparison options become unavailable.</span></span> <span data-ttu-id="6913b-118">Par exemple, les comparaisons qui ne respectent pas la casse ne seront plus disponibles car les majuscules et les minuscules ont des encodages binaires différents.</span><span class="sxs-lookup"><span data-stu-id="6913b-118">For example, case-insensitive comparisons become unavailable because uppercase letters and lowercase letters have different binary encodings.</span></span> <span data-ttu-id="6913b-119">S'applique uniquement si vous sélectionnez **Classement Windows**.</span><span class="sxs-lookup"><span data-stu-id="6913b-119">Applies only if you select **Windows collation**.</span></span>  
  
 <span data-ttu-id="6913b-120">**Tri du dictionnaire**</span><span class="sxs-lookup"><span data-stu-id="6913b-120">**Dictionary Sort**</span></span>  
 <span data-ttu-id="6913b-121">Utilise les options de comparaison alphabétique.</span><span class="sxs-lookup"><span data-stu-id="6913b-121">Use alphabetic comparison options.</span></span> <span data-ttu-id="6913b-122">S'applique uniquement si vous sélectionnez **Classement Windows**.</span><span class="sxs-lookup"><span data-stu-id="6913b-122">Applies only if you select **Windows collation**.</span></span> <span data-ttu-id="6913b-123">Les options de comparaison alphabétique sont :</span><span class="sxs-lookup"><span data-stu-id="6913b-123">The alphabetic comparisons options are:</span></span>  
  
-   <span data-ttu-id="6913b-124">**Respecter la casse** Sélectionnez cette option si vous souhaitez que les comparaisons différencient les majuscules et les minuscules.</span><span class="sxs-lookup"><span data-stu-id="6913b-124">**Case Sensitive** Select this if you want comparisons to consider uppercase and lowercase letters to be unequal.</span></span>  
  
-   <span data-ttu-id="6913b-125">**Respecter les accents** Sélectionnez cette option si vous souhaitez que les comparaisons différencient les lettres accentuées et non accentuées.</span><span class="sxs-lookup"><span data-stu-id="6913b-125">**Accent Sensitive** Select this if you want comparisons to consider accented and unaccented letters to be unequal.</span></span> <span data-ttu-id="6913b-126">Si vous sélectionnez ceci, les comparaisons différencieront également les lettres différemment accentuées.</span><span class="sxs-lookup"><span data-stu-id="6913b-126">If you select this, comparisons will also consider differently accented letters to be unequal.</span></span>  
  
-   <span data-ttu-id="6913b-127">**Respecter le jeu de caractères Kana** Sélectionnez cette option si vous souhaitez que les comparaisons différencient les syllabes japonaises katakana et hiragana.</span><span class="sxs-lookup"><span data-stu-id="6913b-127">**Kana Sensitive** Select this if you want comparisons to consider katakana and hiragana Japanese syllables to be unequal.</span></span>  
  
-   <span data-ttu-id="6913b-128">**Respecter la largeur** Sélectionnez cette option si vous souhaitez que les comparaisons différencient les caractères pleine largeur et demi-largeur.</span><span class="sxs-lookup"><span data-stu-id="6913b-128">**Width Sensitive** Select this if you want comparisons to consider half-width and full-width characters to be unequal.</span></span>  
  
 <span data-ttu-id="6913b-129">**Bouton Paramètres par défaut**</span><span class="sxs-lookup"><span data-stu-id="6913b-129">**Restore Default Button**</span></span>  
 <span data-ttu-id="6913b-130">Applique à la colonne la séquence de classement par défaut pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="6913b-130">Apply the default collation sequence for the database to the column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6913b-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6913b-131">See Also</span></span>  
 [<span data-ttu-id="6913b-132">Utiliser des colonnes dans des requêtes d'agrégation &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="6913b-132">Work with Columns in Aggregate Queries &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
