---
title: Définir un nouvel attribut automatiquement | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- automatic attribute creation
- attributes [Analysis Services], creating
ms.assetid: 208a050a-5e2f-470c-b645-8d835e123db7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 40f9ae1f00dd0a6520c6d1b06111864fba02e8f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708808"
---
# <a name="define-a-new-attribute-automatically"></a><span data-ttu-id="eeb85-102">Définir un nouvel attribut automatiquement</span><span class="sxs-lookup"><span data-stu-id="eeb85-102">Define a New Attribute Automatically</span></span>
  <span data-ttu-id="eeb85-103">Vous pouvez créer un nouvel attribut dans une dimension en utilisant la modification par glisser-déplacer dans le Concepteur de dimensions.</span><span class="sxs-lookup"><span data-stu-id="eeb85-103">You can create a new attribute in a dimension by using drag-and-drop editing in the Dimension Designer.</span></span>  
  
### <a name="to-create-a-new-attribute-automatically"></a><span data-ttu-id="eeb85-104">Pour créer un nouvel attribut automatiquement</span><span class="sxs-lookup"><span data-stu-id="eeb85-104">To create a new attribute automatically</span></span>  
  
1.  <span data-ttu-id="eeb85-105">Dans le Concepteur de dimensions, ouvrez la dimension dans laquelle vous souhaitez créer l'attribut.</span><span class="sxs-lookup"><span data-stu-id="eeb85-105">In Dimension Designer, open the dimension in which you want to create the attribute.</span></span>  
  
2.  <span data-ttu-id="eeb85-106">Sous l’onglet **Structure de dimension** , sélectionnez la colonne du tableau à laquelle vous souhaitez lier l’attribut dans le volet **Vue de source de données** , puis faites-la glisser jusqu’au volet **Attributs** .</span><span class="sxs-lookup"><span data-stu-id="eeb85-106">On the **Dimension Structure** tab, in the **Data Source View** pane, in the table to which you want to bind the attribute, select the column, and then drag the column to the **Attributes** pane.</span></span>  
  
     [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="eeb85-107">crée l’attribut qui a le même nom que la colonne à laquelle il est lié.</span><span class="sxs-lookup"><span data-stu-id="eeb85-107">creates the new attribute that has the same name as the column to which it is bound.</span></span> <span data-ttu-id="eeb85-108">Si plusieurs attributs utilisent la même colonne, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ajoute un numéro au nom de l’attribut.</span><span class="sxs-lookup"><span data-stu-id="eeb85-108">If there are multiple attributes that use the same column, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] appends a number to the attribute name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeb85-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eeb85-109">See Also</span></span>  
 <span data-ttu-id="eeb85-110">[Dimensions dans les modèles multidimensionnels](dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="eeb85-110">[Dimensions in Multidimensional Models](dimensions-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="eeb85-111">Référence des propriétés d’attribut de dimension</span><span class="sxs-lookup"><span data-stu-id="eeb85-111">Dimension Attribute Properties Reference</span></span>](dimension-attribute-properties-reference.md)  
  
  
