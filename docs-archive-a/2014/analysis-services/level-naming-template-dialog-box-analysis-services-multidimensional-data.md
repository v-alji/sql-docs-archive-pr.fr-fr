---
title: Boîte de dialogue modèle de nom de niveau (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.levelnamingtemplatedialog.f1
helpviewer_keywords:
- Level Naming Template dialog box
ms.assetid: 96cad715-213e-4eac-9003-130a2f5fc985
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4dd704e619e49f0dd1adb8fed8f1e743b61309af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710935"
---
# <a name="level-naming-template-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="d28c3-102">Boîte de dialogue Modèle de nom de niveau (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="d28c3-102">Level Naming Template Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="d28c3-103">Utilisez la boîte de dialogue **Modèle de nom de niveau** dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] pour créer un modèle de nom de niveau pour un attribut parent d'une dimension.</span><span class="sxs-lookup"><span data-stu-id="d28c3-103">Use the **Level Naming Template** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to construct the level naming template for a parent attribute in a dimension.</span></span> <span data-ttu-id="d28c3-104">Pour plus d’informations sur ces modèles de nom de niveau, consultez [Élément NamingTemplate &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/namingtemplate-element-assl).</span><span class="sxs-lookup"><span data-stu-id="d28c3-104">For more information about level naming templates, see [NamingTemplate Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/namingtemplate-element-assl).</span></span> <span data-ttu-id="d28c3-105">Vous pouvez afficher la boîte de dialogue **modèle de nom de niveau** en cliquant sur le bouton de sélection (**...**) sur la `NamingTemplate` valeur d’une traduction pour un attribut dans le volet **Détails** des traductions de l’onglet **traductions** du **Concepteur de dimensions**.</span><span class="sxs-lookup"><span data-stu-id="d28c3-105">You can display the **Level Naming Template** dialog box by clicking the ellipsis button (**...**) on the `NamingTemplate` value of a translation for an attribute in the **Translation Details** pane on the **Translations** tab of **Dimension Designer**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d28c3-106">Options</span><span class="sxs-lookup"><span data-stu-id="d28c3-106">Options</span></span>  
  
|<span data-ttu-id="d28c3-107">Terme</span><span class="sxs-lookup"><span data-stu-id="d28c3-107">Term</span></span>|<span data-ttu-id="d28c3-108">Définition</span><span class="sxs-lookup"><span data-stu-id="d28c3-108">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="d28c3-109">**Définissez le modèle de niveau**</span><span class="sxs-lookup"><span data-stu-id="d28c3-109">**Define the level template**</span></span>|<span data-ttu-id="d28c3-110">Permet d'afficher une grille dans laquelle vous pouvez concevoir la hiérarchie propre aux niveaux inclus dans l'attribut parent.</span><span class="sxs-lookup"><span data-stu-id="d28c3-110">Displays a grid in which you can design the hierarchy of levels in the parent attribute.</span></span> <span data-ttu-id="d28c3-111">Cette grille comporte les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="d28c3-111">The grid contains the following columns:</span></span><br /><br /> <span data-ttu-id="d28c3-112">**Level**: affiche la position ordinale du niveau pour lequel le nom spécifié dans **nom** est utilisé.</span><span class="sxs-lookup"><span data-stu-id="d28c3-112">**Level**: Displays the ordinal position of the level for which the name specified in **Name** is used.</span></span> <span data-ttu-id="d28c3-113">Pour ajouter un nouveau modèle de nom pour un niveau, sélectionnez **Nom** sur la ligne qui contient un astérisque (\*) dans **Niveau**.</span><span class="sxs-lookup"><span data-stu-id="d28c3-113">To add a new naming template for a level, select **Name** on the row that contains an asterisk (\*) in **Level**.</span></span><br /><br /> <span data-ttu-id="d28c3-114">**Nom**: contient le modèle de nom utilisé pour le niveau indiqué dans **niveau**.</span><span class="sxs-lookup"><span data-stu-id="d28c3-114">**Name**: Contains the naming template used for the level indicated in **Level**.</span></span> <span data-ttu-id="d28c3-115">Pour ajouter un espace réservé correspondant à la position ordinale du niveau dans le modèle de nom, ajoutez un seul astérisque (\*).</span><span class="sxs-lookup"><span data-stu-id="d28c3-115">To add a placeholder for the level ordinal position in the naming template, add a single asterisk (\*).</span></span> <span data-ttu-id="d28c3-116">Pour ajouter un astérisque dans le nom créé par le modèle de nom, ajoutez deux astérisques ( \* \* ).</span><span class="sxs-lookup"><span data-stu-id="d28c3-116">To add an asterisk as part of the name created by the naming template, add two asterisks (\*\*).</span></span>|  
|<span data-ttu-id="d28c3-117">**Effacer tout**</span><span class="sxs-lookup"><span data-stu-id="d28c3-117">**Clear All**</span></span>|<span data-ttu-id="d28c3-118">Permet de supprimer toutes les lignes issues de l'option **Définissez le modèle de niveau**.</span><span class="sxs-lookup"><span data-stu-id="d28c3-118">Select to remove all rows in **Define the level template**.</span></span>|  
|<span data-ttu-id="d28c3-119">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="d28c3-119">**Result**</span></span>|<span data-ttu-id="d28c3-120">Affiche le modèle de nom de niveau construit par la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d28c3-120">Displays the level naming template constructed by the dialog box.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d28c3-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d28c3-121">See Also</span></span>  
 <span data-ttu-id="d28c3-122">[Analysis Services les concepteurs et les boîtes de dialogue &#40;les données multidimensionnelles&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="d28c3-122">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="d28c3-123">Traductions &#40;concepteur de dimensions&#41; &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="d28c3-123">Translations &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](translations-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
