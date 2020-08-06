---
title: Insérer une fonction, boîte de dialogue (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- SQL12.ASVS.BIDTOOLSET.INSERTFUNCTIONDB.F1
ms.assetid: c4b36d8f-2328-45f7-8bd4-cc0111571e25
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0d92dd34e671dc026215d79e7eaed88bebfac15f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605850"
---
# <a name="insert-function-dialog-box-ssas"></a><span data-ttu-id="03a0f-102">Insérer une fonction, boîte de dialogue (SSAS)</span><span class="sxs-lookup"><span data-stu-id="03a0f-102">Insert Function Dialog Box (SSAS)</span></span>
  <span data-ttu-id="03a0f-103">La boîte de dialogue **Insérer une fonction** vous permet de sélectionner une fonction parmi une liste de fonctions utilisables lors de la génération de formules.</span><span class="sxs-lookup"><span data-stu-id="03a0f-103">The **Insert Function** dialog box enables you to choose from a list of functions that can be used when building formulas.</span></span> <span data-ttu-id="03a0f-104">Pour accéder à cette boîte de dialogue à partir du générateur de modèles, dans la barre de formule située au-dessus de chaque table, cliquez sur le bouton de fonction (**fx**).</span><span class="sxs-lookup"><span data-stu-id="03a0f-104">To access this dialog box from the model designer, in the formula bar above each table, click the function (**fx**) button.</span></span> <span data-ttu-id="03a0f-105">Pour plus d'informations sur le choix des fonctions à utiliser dans les formules, consultez Introduction à DAX et génération d'une formule.</span><span class="sxs-lookup"><span data-stu-id="03a0f-105">For more information about choosing functions to use in formulas, see DAX Introduction and Build a Formula.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="03a0f-106">Élément</span><span class="sxs-lookup"><span data-stu-id="03a0f-106">Item</span></span>|<span data-ttu-id="03a0f-107">Description</span><span class="sxs-lookup"><span data-stu-id="03a0f-107">Description</span></span>|  
|<span data-ttu-id="03a0f-108">**Sélectionner une catégorie**</span><span class="sxs-lookup"><span data-stu-id="03a0f-108">**Select a category**</span></span>|<span data-ttu-id="03a0f-109">Si vous avez une idée générale du type de fonction dont vous avez besoin, sélectionnez une catégorie dans la liste ; sinon, sélectionnez **Tout** pour afficher une liste alphabétique des fonctions.</span><span class="sxs-lookup"><span data-stu-id="03a0f-109">If you have a general idea which kind of function you need, choose a category from the list; or select **All** to view an alphabetical list of functions.</span></span>|  
|<span data-ttu-id="03a0f-110">**Sélectionner une fonction**</span><span class="sxs-lookup"><span data-stu-id="03a0f-110">**Select a function**</span></span>|<span data-ttu-id="03a0f-111">Affiche une liste des fonctions dans la catégorie sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="03a0f-111">Displays a list of the functions in the selected category.</span></span>|  
|<span data-ttu-id="03a0f-112">**Description**</span><span class="sxs-lookup"><span data-stu-id="03a0f-112">**Description**</span></span>|<span data-ttu-id="03a0f-113">Affiche une description de ce que fait la fonction, avec tous les arguments obligatoires ou facultatifs, tels que les noms de colonnes et les expressions.</span><span class="sxs-lookup"><span data-stu-id="03a0f-113">Displays a description of what the function does, together with any required or optional arguments, such as column names and expressions.</span></span>|  
  
## <a name="function-categories"></a><span data-ttu-id="03a0f-114">Catégories de fonctions</span><span class="sxs-lookup"><span data-stu-id="03a0f-114">Function Categories</span></span>  
 <span data-ttu-id="03a0f-115">DAX (Data Analysis Expressions) fournit les types de catégories de fonctions ci-après dans la boîte de dialogue **Insérer une fonction** .</span><span class="sxs-lookup"><span data-stu-id="03a0f-115">Data Analysis Expressions (DAX) provides the following types of function categories in the **Insert Functions** dialog box.</span></span>  
  
 <span data-ttu-id="03a0f-116">Tous</span><span class="sxs-lookup"><span data-stu-id="03a0f-116">All</span></span>  
  
 <span data-ttu-id="03a0f-117">Date et heure</span><span class="sxs-lookup"><span data-stu-id="03a0f-117">Date & Time</span></span>  
  
 <span data-ttu-id="03a0f-118">Filtrer</span><span class="sxs-lookup"><span data-stu-id="03a0f-118">Filter</span></span>  
  
 <span data-ttu-id="03a0f-119">Logical</span><span class="sxs-lookup"><span data-stu-id="03a0f-119">Logical</span></span>  
  
 <span data-ttu-id="03a0f-120">Maths et trigonométrie</span><span class="sxs-lookup"><span data-stu-id="03a0f-120">Math & Trig</span></span>  
  
 <span data-ttu-id="03a0f-121">Statistique</span><span class="sxs-lookup"><span data-stu-id="03a0f-121">Statistical</span></span>  
  
 <span data-ttu-id="03a0f-122">Texte</span><span class="sxs-lookup"><span data-stu-id="03a0f-122">Text</span></span>  
  
## <a name="measures-and-formulas"></a><span data-ttu-id="03a0f-123">Mesures et formules</span><span class="sxs-lookup"><span data-stu-id="03a0f-123">Measures and Formulas</span></span>  
 <span data-ttu-id="03a0f-124">La boîte de dialogue **Insérer une fonction** est disponible uniquement lorsque vous générez une formule.</span><span class="sxs-lookup"><span data-stu-id="03a0f-124">The **Insert Function** dialog box is available only when you are building a formula.</span></span> <span data-ttu-id="03a0f-125">Vous pouvez créer des calculs dans une colonne calculée, un tableau croisé dynamique ou un graphique croisé dynamique.</span><span class="sxs-lookup"><span data-stu-id="03a0f-125">You can create calculations either in a calculated column, or in a PivotTable or PivotChart.</span></span> <span data-ttu-id="03a0f-126">Les formules que vous générez spécifiquement pour une utilisation dans un tableau croisé dynamique sont également appelées *mesures*.</span><span class="sxs-lookup"><span data-stu-id="03a0f-126">Formulas that you build expressly for use in a PivotTable are also called *measures*.</span></span> <span data-ttu-id="03a0f-127">Pour plus d’informations, consultez [Créer une colonne calculée &#40;SSAS Tabulaire&#41;](tabular-models/ssas-calculated-columns-create-a-calculated-column.md) et [Créer et gérer des mesures &#40;SSAS Tabulaire&#41;](tabular-models/measures-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="03a0f-127">For more information, see [Create a Calculated Column &#40;SSAS Tabular&#41;](tabular-models/ssas-calculated-columns-create-a-calculated-column.md) and [Create and Manage Measures &#40;SSAS Tabular&#41;](tabular-models/measures-ssas-tabular.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03a0f-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="03a0f-128">See Also</span></span>  
 [<span data-ttu-id="03a0f-129">Calculs &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="03a0f-129">Calculations &#40;SSAS Tabular&#41;</span></span>](tabular-models/calculations-ssas-tabular.md)  
  
  
