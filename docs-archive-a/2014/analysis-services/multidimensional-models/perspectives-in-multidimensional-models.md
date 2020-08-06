---
title: Perspectives dans les modèles multidimensionnels | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- default members
- hiding objects from perspective
- renaming perspectives
- attributes [Analysis Services], default members
- removing perspectives
- perspectives [Analysis Services]
- names [Analysis Services], perspectives
- cubes [Analysis Services], perspectives
- deleting perspectives
ms.assetid: 5a3d6577-6833-4c24-820c-b65bb856157b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2d4be87ddbd691710b361d8b07d225bce37659fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603100"
---
# <a name="perspectives-in-multidimensional-models"></a><span data-ttu-id="4e264-102">Perspectives dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="4e264-102">Perspectives in Multidimensional Models</span></span>
  <span data-ttu-id="4e264-103">Une perspective est un sous-ensemble de cube créé pour une application ou un groupe d'utilisateurs particuliers.</span><span class="sxs-lookup"><span data-stu-id="4e264-103">A perspective is a subset of a cube created for a particular application or group of users.</span></span> <span data-ttu-id="4e264-104">Le cube lui-même est la perspective par défaut.</span><span class="sxs-lookup"><span data-stu-id="4e264-104">The cube itself is the default perspective.</span></span> <span data-ttu-id="4e264-105">Une perspective se présente à un client sous forme de cube.</span><span class="sxs-lookup"><span data-stu-id="4e264-105">A perspective is exposed to a client as a cube.</span></span> <span data-ttu-id="4e264-106">Lorsqu'un utilisateur affiche une perspective, elle ressemble à n'importe quel autre cube.</span><span class="sxs-lookup"><span data-stu-id="4e264-106">When a user views a perspective, it appears like another cube.</span></span> <span data-ttu-id="4e264-107">Toute modification apportée aux données du cube via l'écriture différée dans la perspective affecte le cube d'origine.</span><span class="sxs-lookup"><span data-stu-id="4e264-107">Any changes made to cube data through writeback in the perspective are to the original cube.</span></span> <span data-ttu-id="4e264-108">Pour plus d’informations sur les vues dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], consultez [Perspectives](../multidimensional-models-olap-logical-cube-objects/perspectives.md).</span><span class="sxs-lookup"><span data-stu-id="4e264-108">For more information about the views in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], see [Perspectives](../multidimensional-models-olap-logical-cube-objects/perspectives.md).</span></span>  
  
 <span data-ttu-id="4e264-109">Pour créer ou modifier les perspectives d’un cube, utilisez l’onglet **Perspectives** dans le Concepteur de cube.</span><span class="sxs-lookup"><span data-stu-id="4e264-109">Use the **Perspectives** tab in Cube Designer to create or modify perspectives in a cube.</span></span> <span data-ttu-id="4e264-110">La première colonne de l’onglet **Perspectives** est la colonne **Objets de cube** , qui répertorie tous les objets du cube.</span><span class="sxs-lookup"><span data-stu-id="4e264-110">The first column of the **Perspectives** tab is the **Cube Objects** column, which lists all the objects in the cube.</span></span> <span data-ttu-id="4e264-111">Ceci correspond à la perspective par défaut du cube, soit le cube lui-même.</span><span class="sxs-lookup"><span data-stu-id="4e264-111">This corresponds to the default perspective for the cube, which is the cube itself.</span></span>  
  
## <a name="creating-or-deleting-perspectives"></a><span data-ttu-id="4e264-112">Création ou suppression de perspectives</span><span class="sxs-lookup"><span data-stu-id="4e264-112">Creating or Deleting Perspectives</span></span>  
 <span data-ttu-id="4e264-113">Vous pouvez ajouter une perspective à l’onglet **Perspectives** en cliquant sur **Nouvelle perspective** dans le menu **Cube** .</span><span class="sxs-lookup"><span data-stu-id="4e264-113">You can add a perspective to the **Perspectives** tab by clicking **New Perspective** on the **Cube** menu.</span></span> <span data-ttu-id="4e264-114">Vous pouvez aussi cliquer sur le bouton **Nouvelle perspective** de la barre d’outils ou cliquer avec le bouton droit à un endroit quelconque du volet, puis cliquer sur **Nouvelle perspective** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="4e264-114">You can also click the **New Perspective** button on the toolbar, or right-click anywhere in the pane and click **New Perspective** on the shortcut menu.</span></span> <span data-ttu-id="4e264-115">Vous pouvez ajouter un nombre illimité de perspectives à un cube.</span><span class="sxs-lookup"><span data-stu-id="4e264-115">You can add any number of perspectives to a cube.</span></span>  
  
 <span data-ttu-id="4e264-116">Pour supprimer une perspective, cliquez d'abord sur une cellule de la colonne de la perspective à supprimer.</span><span class="sxs-lookup"><span data-stu-id="4e264-116">To remove a perspective, first click any cell in the column for the perspective that you want to delete.</span></span> <span data-ttu-id="4e264-117">Ensuite, dans le menu **Cube** , cliquez sur **Supprimer la perspective**.</span><span class="sxs-lookup"><span data-stu-id="4e264-117">Then, on the **Cube** menu, click **Delete Perspective**.</span></span> <span data-ttu-id="4e264-118">Vous pouvez aussi cliquer sur le bouton **Supprimer la perspective** de la barre d’outils ou cliquer avec le bouton droit sur une cellule de la perspective à supprimer, puis cliquer sur **Supprimer la perspective** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="4e264-118">You can also click the **Delete Perspective** button on the toolbar, or right-click any cell in the perspective you want to delete, and then click **Delete Perspective** on the shortcut menu.</span></span>  
  
## <a name="renaming-perspectives"></a><span data-ttu-id="4e264-119">affectation d'un nouveau nom aux perspectives</span><span class="sxs-lookup"><span data-stu-id="4e264-119">Renaming Perspectives</span></span>  
 <span data-ttu-id="4e264-120">La première ligne de chaque perspective affiche son nom.</span><span class="sxs-lookup"><span data-stu-id="4e264-120">The first row of each perspective shows its name.</span></span> <span data-ttu-id="4e264-121">Lorsque vous créez une perspective, son nom initial est Perspective (suivi d'un nombre ordinal, commençant par 1, s'il existe déjà une perspective nommée Perspective).</span><span class="sxs-lookup"><span data-stu-id="4e264-121">When you create a perspective, the name is initially Perspective (followed by an ordinal number, starting with 1, if there is already a perspective called Perspective).</span></span> <span data-ttu-id="4e264-122">Vous pouvez cliquer sur le nom pour le modifier.</span><span class="sxs-lookup"><span data-stu-id="4e264-122">You can click the name to edit it.</span></span>  
  
## <a name="hiding-objects-from-a-perspective"></a><span data-ttu-id="4e264-123">Masquage des objets dans une perspective</span><span class="sxs-lookup"><span data-stu-id="4e264-123">Hiding Objects from a Perspective</span></span>  
 <span data-ttu-id="4e264-124">Pour masquer un objet dans une perspective, désactivez la case à cocher dans la ligne qui correspond à l'objet dans la colonne de la perspective.</span><span class="sxs-lookup"><span data-stu-id="4e264-124">To hide an object from a perspective, clear the check box in the row that corresponds to the object in the column for the perspective.</span></span> <span data-ttu-id="4e264-125">Les objets de cube qui peuvent être masqués dans une perspective sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="4e264-125">The cube objects that can be hidden from a perspective are:</span></span>  
  
-   <span data-ttu-id="4e264-126">les groupes de mesures ;</span><span class="sxs-lookup"><span data-stu-id="4e264-126">Measure groups</span></span>  
  
-   <span data-ttu-id="4e264-127">Mesures</span><span class="sxs-lookup"><span data-stu-id="4e264-127">Measures</span></span>  
  
-   <span data-ttu-id="4e264-128">Dimensions</span><span class="sxs-lookup"><span data-stu-id="4e264-128">Dimensions</span></span>  
  
-   <span data-ttu-id="4e264-129">Hierarchies</span><span class="sxs-lookup"><span data-stu-id="4e264-129">Hierarchies</span></span>  
  
-   <span data-ttu-id="4e264-130">Les jeux nommés</span><span class="sxs-lookup"><span data-stu-id="4e264-130">Named sets</span></span>  
  
-   <span data-ttu-id="4e264-131">Indicateurs de performance clés</span><span class="sxs-lookup"><span data-stu-id="4e264-131">KPIs</span></span>  
  
-   <span data-ttu-id="4e264-132">Actions</span><span class="sxs-lookup"><span data-stu-id="4e264-132">Actions</span></span>  
  
-   <span data-ttu-id="4e264-133">Membres calculés</span><span class="sxs-lookup"><span data-stu-id="4e264-133">Calculated members</span></span>  
  
 <span data-ttu-id="4e264-134">Pour afficher un objet, développez la catégorie (**Groupes de mesures**, **Dimensions**, **Indicateurs de performance clés**, **Calculs**ou **Actions**) pour n’importe quel type d’objet sous **Objets de cube**.</span><span class="sxs-lookup"><span data-stu-id="4e264-134">To view any object, expand the category (**Measure Groups**, **Dimensions**, **KPIs**, **Calculations**, or **Actions**) for any object type under **Cube Objects**.</span></span> <span data-ttu-id="4e264-135">Pour afficher les hiérarchies ou les attributs d’une dimension, développez d’abord une dimension, puis la ligne **Hiérarchies** ou **Attributs** .</span><span class="sxs-lookup"><span data-stu-id="4e264-135">To view hierarchies or attributes in a dimension, first expand a dimension, and then expand the **Hierarchies** or **Attributes** row.</span></span> <span data-ttu-id="4e264-136">Pour afficher les mesures d'un groupe de mesures, développez ce dernier.</span><span class="sxs-lookup"><span data-stu-id="4e264-136">To view measures in a measure group, expand the measure group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e264-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4e264-137">See Also</span></span>  
 [<span data-ttu-id="4e264-138">Cubes dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="4e264-138">Cubes in Multidimensional Models</span></span>](cubes-in-multidimensional-models.md)  
  
  
