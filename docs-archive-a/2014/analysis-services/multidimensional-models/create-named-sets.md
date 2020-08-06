---
title: Créer des jeux nommés | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- calculations [Analysis Services], named sets
- named sets [Analysis Services]
- members [Analysis Services], named sets
ms.assetid: 03cf97a4-1a18-45f3-acb0-35123bd619be
author: minewiskan
ms.author: owend
ms.openlocfilehash: e92984102ceb8ad0ac049c15870e9f1efd6090fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696255"
---
# <a name="create-named-sets"></a><span data-ttu-id="13355-102">Créer des jeux nommés</span><span class="sxs-lookup"><span data-stu-id="13355-102">Create Named Sets</span></span>
  <span data-ttu-id="13355-103">Un jeu nommé est un ensemble de membres de dimension (ou une expression de jeu) créé en vue d'être réutilisé, par exemple dans des requêtes MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="13355-103">A named set is a set of dimension members or a set expression that is created for reuse, for example in Multidimensional Expressions (MDX) queries.</span></span> <span data-ttu-id="13355-104">Vous pouvez créer des jeux nommés en combinant des données de cube, des opérateurs arithmétiques, des nombres et des fonctions.</span><span class="sxs-lookup"><span data-stu-id="13355-104">You can create named sets by combining cube data, arithmetic operators, numbers, and functions.</span></span> <span data-ttu-id="13355-105">Par exemple, vous pouvez créer le jeu nommé « Dix meilleures usines » qui contient les dix membres de la dimension Usines ayant les valeurs les plus élevées pour la mesure Production.</span><span class="sxs-lookup"><span data-stu-id="13355-105">For example, you can create a named set called Top Ten Factories that contains the ten members of the Factories dimension that have the highest values for the Production measure.</span></span> <span data-ttu-id="13355-106">« Dix meilleures usines » peut ensuite être utilisé dans des requêtes par les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="13355-106">Top Ten Factories can then be used in queries by end users.</span></span> <span data-ttu-id="13355-107">Par exemple, un utilisateur peut placer « Dix meilleures usines » sur un axe et la dimension Measures, avec Production, sur un autre axe.</span><span class="sxs-lookup"><span data-stu-id="13355-107">For example, an end user can place Top Ten Factories on one axis and the Measures dimension, including Production, on another axis.</span></span> <span data-ttu-id="13355-108">Pour plus d’informations, consultez [Calculs dans les modèles multidimensionnels](calculations-in-multidimensional-models.md) et [Création de jeux nommés à l’aide d’expressions MDX &#40;MDX&#41;](mdx/mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="13355-108">For more information, see [Calculations in Multidimensional Models](calculations-in-multidimensional-models.md), and [Building Named Sets in MDX &#40;MDX&#41;](mdx/mdx-named-sets-building-named-sets.md).</span></span>  
  
 <span data-ttu-id="13355-109">Pour créer un jeu nommé, utilisez la commande **Nouveau jeu nommé** , disponible sous l'onglet **Calculs** du Concepteur de cube.</span><span class="sxs-lookup"><span data-stu-id="13355-109">To create a named set, use the **New Named Set** command on the **Calculations** tab of Cube Designer.</span></span> <span data-ttu-id="13355-110">Cette commande peut être appelée dans le menu **Cube** de la barre d’outils de l’onglet **Calculs** .</span><span class="sxs-lookup"><span data-stu-id="13355-110">This command can be invoked on the **Cube** menu on the **Calculations** tab toolbar.</span></span> <span data-ttu-id="13355-111">Cette commande affiche un formulaire permettant de spécifier les options suivantes pour le jeu nommé :</span><span class="sxs-lookup"><span data-stu-id="13355-111">This command displays a form to specify the following options for the named set:</span></span>  
  
 <span data-ttu-id="13355-112">**Nom**</span><span class="sxs-lookup"><span data-stu-id="13355-112">**Name**</span></span>  
 <span data-ttu-id="13355-113">Choisissez le nom du jeu nommé.</span><span class="sxs-lookup"><span data-stu-id="13355-113">Select the name of the named set.</span></span> <span data-ttu-id="13355-114">C'est celui que verront les utilisateurs lorsqu'ils parcourront le cube.</span><span class="sxs-lookup"><span data-stu-id="13355-114">This name appears to end users when they browse the cube.</span></span>  
  
 <span data-ttu-id="13355-115">**Expression**</span><span class="sxs-lookup"><span data-stu-id="13355-115">**Expression**</span></span>  
 <span data-ttu-id="13355-116">Spécifiez l'expression qui produit le jeu nommé.</span><span class="sxs-lookup"><span data-stu-id="13355-116">Specify the expression that produces the named set.</span></span> <span data-ttu-id="13355-117">Cette expression peut être écrite en MDX.</span><span class="sxs-lookup"><span data-stu-id="13355-117">This expression can be written in MDX.</span></span> <span data-ttu-id="13355-118">L'expression peut contenir l'un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="13355-118">The expression can contain any of the following:</span></span>  
  
-   <span data-ttu-id="13355-119">Expressions de données représentant des composants de cube (par exemple des dimensions, des niveaux, des mesures, etc.)</span><span class="sxs-lookup"><span data-stu-id="13355-119">Data expressions that represent cube components such as dimensions, levels, measures, and so on.</span></span>  
  
-   <span data-ttu-id="13355-120">Opérateurs arithmétiques.</span><span class="sxs-lookup"><span data-stu-id="13355-120">Arithmetic operators.</span></span>  
  
-   <span data-ttu-id="13355-121">Nombres.</span><span class="sxs-lookup"><span data-stu-id="13355-121">Numbers.</span></span>  
  
-   <span data-ttu-id="13355-122">Fonctions.</span><span class="sxs-lookup"><span data-stu-id="13355-122">Functions.</span></span>  
  
 <span data-ttu-id="13355-123">Vous pouvez copier ou faire glisser des composants de cube depuis l’onglet **Métadonnées** du volet **Outils de calcul** vers la zone **Expression** du volet **Éditeur de formulaire de jeu nommé** .</span><span class="sxs-lookup"><span data-stu-id="13355-123">You can copy or drag cube components from the **Metadata** tab of the **Calculation Tools** pane to the **Expression** box in the **Named Set Form Editor** pane.</span></span> <span data-ttu-id="13355-124">Vous pouvez copier ou faire glisser des fonctions depuis l’onglet **Fonctions** du volet **Outils de calcul** vers la zone **Expression** du volet **Éditeur de formulaire de jeu nommé** .</span><span class="sxs-lookup"><span data-stu-id="13355-124">You can copy or drag functions from the **Functions** tab in the **Calculation Tools** pane to the **Expression** box in the **Named Set Form Editor** pane.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="13355-125">Si vous créez l’expression d’ensemble en nommant explicitement les membres du jeu, mettez la liste des membres entre parenthèses ( {} ).</span><span class="sxs-lookup"><span data-stu-id="13355-125">If you create the set expression by explicitly naming the members in the set, enclose the list of members in a pair of braces ({}).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13355-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="13355-126">See Also</span></span>  
 [<span data-ttu-id="13355-127">Calculs dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="13355-127">Calculations in Multidimensional Models</span></span>](calculations-in-multidimensional-models.md)  
  
  
