---
title: Ajouter ou supprimer une hiérarchie définie par l’utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Analysis Services], adding
- removing hierarchies
- adding hierarchies
- deleting hierarchies
- hierarchies [Analysis Services], removing
ms.assetid: 953818b4-9543-4c01-bb20-1d45ec6dfb91
author: minewiskan
ms.author: owend
ms.openlocfilehash: d20404a1d93d57221eb830366392eb90600f26c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611347"
---
# <a name="add-or-delete-a-user-defined-hierarchy"></a><span data-ttu-id="9c2f0-102">Ajouter ou supprimer une hiérarchie définie par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="9c2f0-102">Add or Delete a User-Defined Hierarchy</span></span>
  <span data-ttu-id="9c2f0-103">Vous pouvez ajouter ou supprimer une hiérarchie définie par l’utilisateur dans une dimension sous l’onglet **Structure de dimension** du Concepteur de dimensions dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c2f0-103">You add a user-defined hierarchy to or remove a user-defined hierarchy from a dimension on the **Dimension Structure** tab in Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="9c2f0-104">Quand vous ajoutez une hiérarchie définie par l’utilisateur, elle ne devient accessible aux utilisateurs qu’à partir du moment où elle est instanciée dans une instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] et que la dimension est traitée.</span><span class="sxs-lookup"><span data-stu-id="9c2f0-104">When you add a user-defined hierarchy, it is not available to users until it is instantiated in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and the dimension is processed.</span></span> <span data-ttu-id="9c2f0-105">Pour plus d’informations, consultez [bases de données de modèle multidimensionnels &#40;SSAS&#41;](multidimensional-model-databases-ssas.md) et [traitement d’objet de modèle multidimensionnel](processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="9c2f0-105">For more information, see [Multidimensional Model Databases &#40;SSAS&#41;](multidimensional-model-databases-ssas.md) and [Multidimensional Model Object Processing](processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
### <a name="to-add-a-user-defined-hierarchy-to-a-dimension"></a><span data-ttu-id="9c2f0-106">Pour ajouter une hiérarchie définie par l'utilisateur à une dimension</span><span class="sxs-lookup"><span data-stu-id="9c2f0-106">To add a user-defined hierarchy to a dimension</span></span>  
  
1.  <span data-ttu-id="9c2f0-107">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] approprié, puis ouvrez la dimension avec laquelle vous souhaitez travailler.</span><span class="sxs-lookup"><span data-stu-id="9c2f0-107">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the appropriate [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, and then open the dimension with which you want to work.</span></span>  
  
     <span data-ttu-id="9c2f0-108">La dimension s’ouvre dans le Concepteur de dimensions sous l’onglet **Structure de dimension** .</span><span class="sxs-lookup"><span data-stu-id="9c2f0-108">The dimension opens in Dimension Designer on the **Dimension Structure** tab.</span></span>  
  
2.  <span data-ttu-id="9c2f0-109">Dans le volet **Attributs** , faites glisser l’attribut que vous souhaitez utiliser dans la hiérarchie définie par l’utilisateur vers le volet **Hiérarchies** .</span><span class="sxs-lookup"><span data-stu-id="9c2f0-109">From the **Attributes** pane, drag an attribute that you want to use in the user-defined hierarchy to the **Hierarchies** pane.</span></span>  
  
3.  <span data-ttu-id="9c2f0-110">Faites glisser des attributs supplémentaires pour former des niveaux dans la hiérarchie définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9c2f0-110">Drag additional attributes to form levels in the user-defined hierarchy.</span></span>  
  
     <span data-ttu-id="9c2f0-111">L'ordre dans lequel les attributs sont classés dans la hiérarchie est important.</span><span class="sxs-lookup"><span data-stu-id="9c2f0-111">The order in which attributes are listed in the hierarchy is important.</span></span> <span data-ttu-id="9c2f0-112">Par exemple, dans une hiérarchie de temps, les années doivent apparaître plus haut que les jours dans la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="9c2f0-112">For example, in a time hierarchy, years should appear higher in the hierarchy list than days.</span></span>  
  
4.  <span data-ttu-id="9c2f0-113">Vous pouvez éventuellement réordonner les niveaux dans la nouvelle hiérarchie définie par l'utilisateur en les faisant glisser vers les positions appropriées.</span><span class="sxs-lookup"><span data-stu-id="9c2f0-113">Optionally, rearrange the levels in the user-defined hierarchy by dragging them to the correct positions.</span></span>  
  
5.  <span data-ttu-id="9c2f0-114">Vous pouvez éventuellement modifier les propriétés de la hiérarchie définie par l'utilisateur ou de ses niveaux.</span><span class="sxs-lookup"><span data-stu-id="9c2f0-114">Optionally, modify properties of the user-defined hierarchy or its levels.</span></span>  
  
     <span data-ttu-id="9c2f0-115">Par exemple, vous pouvez spécifier un nom pour la hiérarchie définie par l'utilisateur, renommer un ou plusieurs de ses niveaux et définir un nom personnalisé pour le niveau Tous.</span><span class="sxs-lookup"><span data-stu-id="9c2f0-115">For example, you might want to specify a name for the user-defined hierarchy, rename one or more of its levels, and define a custom name for the All level.</span></span> <span data-ttu-id="9c2f0-116">Pour plus d’informations, consultez Propriétés de la hiérarchie de l' [utilisateur](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md)et [propriétés de niveau &#91;avec&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md).</span><span class="sxs-lookup"><span data-stu-id="9c2f0-116">For more information, see [User Hierarchy Properties](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md), and [Level Properties &#91;Paved Over&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9c2f0-117">Par défaut, une hiérarchie définie par l'utilisateur est un simple chemin d'accès qui permet aux utilisateurs de rechercher des informations.</span><span class="sxs-lookup"><span data-stu-id="9c2f0-117">By default, a user-defined hierarchy is just a path that enables users to drill down for information.</span></span> <span data-ttu-id="9c2f0-118">Cependant, s'il existe des relations entre les niveaux, vous pouvez augmenter les performances des requêtes en configurant ces relations d'attributs entre les niveaux.</span><span class="sxs-lookup"><span data-stu-id="9c2f0-118">However, if relationships exist between levels, you can increase query performance by configuring attribute relationships between levels.</span></span> <span data-ttu-id="9c2f0-119">Pour plus d’informations, consultez [Relations d’attributs](../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md) et [Définir des relations d’attributs](attribute-relationships-define.md).</span><span class="sxs-lookup"><span data-stu-id="9c2f0-119">For more information, see [Attribute Relationships](../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md) and [Define Attribute Relationships](attribute-relationships-define.md).</span></span>  
  
### <a name="to-remove-a-user-defined-hierarchy-from-a-dimension"></a><span data-ttu-id="9c2f0-120">Pour supprimer une hiérarchie définie par l'utilisateur d'une dimension</span><span class="sxs-lookup"><span data-stu-id="9c2f0-120">To remove a user-defined hierarchy from a dimension</span></span>  
  
-   <span data-ttu-id="9c2f0-121">Sous l’onglet **Structure de dimension** , cliquez sur la hiérarchie définie par l’utilisateur que vous souhaitez supprimer dans le volet **Hiérarchies** .</span><span class="sxs-lookup"><span data-stu-id="9c2f0-121">On the **Dimension Structure** tab, click the user-defined hierarchy that you want to remove in the **Hierarchies** pane.</span></span> <span data-ttu-id="9c2f0-122">Dans la barre d’outils, cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="9c2f0-122">On the toolbar, click **Delete**.</span></span>  
  
     - <span data-ttu-id="9c2f0-123">ou -</span><span class="sxs-lookup"><span data-stu-id="9c2f0-123">or -</span></span>  
  
-   <span data-ttu-id="9c2f0-124">Cliquez avec le bouton droit sur la hiérarchie définie par l’utilisateur que vous souhaitez supprimer dans le volet **Hiérarchies** , puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="9c2f0-124">Right-click the user-defined hierarchy that you want to remove in the **Hierarchies** pane and then click **Delete**.</span></span>  
  
     - <span data-ttu-id="9c2f0-125">ou -</span><span class="sxs-lookup"><span data-stu-id="9c2f0-125">or -</span></span>  
  
-   <span data-ttu-id="9c2f0-126">Faites glisser la hiérarchie définie par l'utilisateur hors de l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="9c2f0-126">Drag the user-defined hierarchy off of the design surface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c2f0-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9c2f0-127">See Also</span></span>  
 <span data-ttu-id="9c2f0-128">[Hiérarchies utilisateur](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="9c2f0-128">[User Hierarchies](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies.md) </span></span>  
 [<span data-ttu-id="9c2f0-129">Créer des hiérarchies définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="9c2f0-129">Create User-Defined Hierarchies</span></span>](user-defined-hierarchies-create.md)  
  
  
