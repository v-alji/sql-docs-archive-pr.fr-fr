---
title: Ajouter un attribut à une dimension | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- adding attributes
- automatic attribute creation
- attributes [Analysis Services], creating
- attributes [Analysis Services], adding
- manual attribute creation [Analysis Services]
ms.assetid: 25826ba1-2b38-4b34-bd3a-7eba116093ae
author: minewiskan
ms.author: owend
ms.openlocfilehash: 776591e94deedc679592cfe36d53fb1fea4093d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614210"
---
# <a name="add-an--attribute-to-a-dimension"></a><span data-ttu-id="cc0a0-102">Ajouter un attribut à une dimension</span><span class="sxs-lookup"><span data-stu-id="cc0a0-102">Add an  Attribute to a Dimension</span></span>
  <span data-ttu-id="cc0a0-103">Vous pouvez ajouter un attribut à une dimension soit automatiquement, soit manuellement dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc0a0-103">You can add an attribute to a dimension either automatically or manually in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="cc0a0-104">Pour créer un attribut automatiquement, dans le volet **Structure de dimension** du Concepteur de dimensions de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], sélectionnez la colonne que vous voulez mapper avec un attribut, puis faites glisser cette colonne du volet **Vue de source de données** jusqu’au volet **Attributs** .</span><span class="sxs-lookup"><span data-stu-id="cc0a0-104">To create an attribute automatically, on the **Dimension Structure** tab of Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the column that you want to map to an attribute, and then drag that column from the **Data Source View** pane to the **Attributes** pane.</span></span> <span data-ttu-id="cc0a0-105">Vous créez ainsi un attribut qui est mappé avec la colonne et en reçoit le nom.</span><span class="sxs-lookup"><span data-stu-id="cc0a0-105">This creates an attribute that is mapped to the column, and assigns the same name to the attribute as the name of the column.</span></span> <span data-ttu-id="cc0a0-106">S’il existe déjà un attribut de ce nom, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] lui ajoute à la fin un numéro en commençant par « 1 » pour le premier nom en double.</span><span class="sxs-lookup"><span data-stu-id="cc0a0-106">If an attribute that uses that name already exists, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] adds an ordinal number suffix, starting with "1" for the first duplicate name.</span></span>  
  
 <span data-ttu-id="cc0a0-107">Pour créer un attribut manuellement, affichez la grille dans le volet **Attributs** .</span><span class="sxs-lookup"><span data-stu-id="cc0a0-107">To create an attribute manually, set the **Attributes** pane to grid view.</span></span> <span data-ttu-id="cc0a0-108">Dans la colonne nom de la dernière ligne de la grille, cliquez sur l' **\<new attribute>** élément.</span><span class="sxs-lookup"><span data-stu-id="cc0a0-108">In the name column of the last row in the grid, click the **\<new attribute>** item.</span></span> <span data-ttu-id="cc0a0-109">Tapez le nom du nouvel attribut.</span><span class="sxs-lookup"><span data-stu-id="cc0a0-109">Type a name for the new attribute.</span></span> <span data-ttu-id="cc0a0-110">Vous créez ainsi un attribut qui n'est pas mappé avec une colonne et dont toutes les propriétés ont leurs valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="cc0a0-110">This creates an attribute that is not mapped to a column and that has default settings for all its properties.</span></span> <span data-ttu-id="cc0a0-111">Vous pouvez définir le mappage dans la fenêtre **Propriétés** de [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] en configurant la propriété **KeyColumns** du nouvel attribut.</span><span class="sxs-lookup"><span data-stu-id="cc0a0-111">You can set the mapping in the **Properties** window of [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] by configuring the **KeyColumns** property for the new attribute.</span></span>  
  
 <span data-ttu-id="cc0a0-112">Pour plus d’informations, consultez [Définir un nouvel attribut automatiquement](attribute-properties-define-a-new-attribute-automatically.md), [Définir un nouvel attribut manuellement](../define-a-new-attribute-manually.md), [Lier un attribut à une colonne de nom](attribute-properties-bind-an-attribute-to-a-name-column.md)et [Modifier la propriété KeyColumn d’un attribut](attribute-properties-modify-the-keycolumn-property.md).</span><span class="sxs-lookup"><span data-stu-id="cc0a0-112">For more information, see [Define a New Attribute Automatically](attribute-properties-define-a-new-attribute-automatically.md), [Define a New Attribute Manually](../define-a-new-attribute-manually.md), [Bind an Attribute to a Name Column](attribute-properties-bind-an-attribute-to-a-name-column.md), and [Modify the KeyColumn Property of an Attribute](attribute-properties-modify-the-keycolumn-property.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc0a0-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cc0a0-113">See Also</span></span>  
 [<span data-ttu-id="cc0a0-114">Référence des propriétés d’attribut de dimension</span><span class="sxs-lookup"><span data-stu-id="cc0a0-114">Dimension Attribute Properties Reference</span></span>](dimension-attribute-properties-reference.md)  
  
  
