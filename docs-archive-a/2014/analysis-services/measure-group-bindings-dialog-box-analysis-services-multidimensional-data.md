---
title: Boîte de dialogue liaisons des groupes de mesures (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.dimensionusage.definerelationship.measuregroupbindings.f1
helpviewer_keywords:
- Measure Group Bindings dialog box
ms.assetid: ed642780-5350-438e-af73-b9ceab3f876d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 78693901a5898b140d6efeed16b6f0eaa7577e69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708824"
---
# <a name="measure-group-bindings-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="ea96c-102">Boîte de dialogue Liaisons des groupes de mesures (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="ea96c-102">Measure Group Bindings Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="ea96c-103">Utilisez la boîte de dialogue **Liaisons des groupes de mesures** pour créer et modifier des relations directes entre des attributs non granulaires d’une dimension d’un cube et les colonnes d’un groupe de mesures. Elle permet également de spécifier des options de traitement des valeurs NULL pour tout attribut dans une dimension d’un cube, à partir de la boîte de dialogue **Définir une relation** .</span><span class="sxs-lookup"><span data-stu-id="ea96c-103">Use the **Measure Group Bindings** dialog box to create and modify direct relationships between non-granularity attributes in a cube dimension and columns in a measure group for a regular dimension relationship, as well as to specify null processing options for any attribute in a cube dimension, from the **Define Relationship** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ea96c-104">Options</span><span class="sxs-lookup"><span data-stu-id="ea96c-104">Options</span></span>  
 <span data-ttu-id="ea96c-105">**Table de groupe de mesures**</span><span class="sxs-lookup"><span data-stu-id="ea96c-105">**Measure group table**</span></span>  
 <span data-ttu-id="ea96c-106">Affiche le nom de la table de faits pour le groupe de mesures sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ea96c-106">Displays the name of the fact table for the selected measure group.</span></span>  
  
 <span data-ttu-id="ea96c-107">**Attributs**</span><span class="sxs-lookup"><span data-stu-id="ea96c-107">**Attributes**</span></span>  
 <span data-ttu-id="ea96c-108">Affiche une grille d'attributs et de tables de dimension.</span><span class="sxs-lookup"><span data-stu-id="ea96c-108">Displays a grid of attributes and dimension tables.</span></span> <span data-ttu-id="ea96c-109">Sélectionnez un attribut pour créer ou modifier des propriétés dans **Relation** pour l'attribut sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ea96c-109">Select an attribute to create or modify properties in **Relationship** for the selected attribute.</span></span> <span data-ttu-id="ea96c-110">Cette grille comporte les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="ea96c-110">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="ea96c-111">Option</span><span class="sxs-lookup"><span data-stu-id="ea96c-111">Option</span></span>|<span data-ttu-id="ea96c-112">Définition</span><span class="sxs-lookup"><span data-stu-id="ea96c-112">Definition</span></span>|  
|------------|----------------|  
|<span data-ttu-id="ea96c-113">**Nom de l’attribut**</span><span class="sxs-lookup"><span data-stu-id="ea96c-113">**Attribute Name**</span></span>|<span data-ttu-id="ea96c-114">Affiche le nom de l'attribut.</span><span class="sxs-lookup"><span data-stu-id="ea96c-114">Displays the name of the attribute.</span></span>|  
|<span data-ttu-id="ea96c-115">**Table de dimension**</span><span class="sxs-lookup"><span data-stu-id="ea96c-115">**Dimension Table**</span></span>|<span data-ttu-id="ea96c-116">Affiche le nom de la table de dimension dont l'attribut est dérivé.</span><span class="sxs-lookup"><span data-stu-id="ea96c-116">Displays the name of the dimension table on which the attribute is based.</span></span>|  
  
 <span data-ttu-id="ea96c-117">**Relation**</span><span class="sxs-lookup"><span data-stu-id="ea96c-117">**Relationship**</span></span>  
 <span data-ttu-id="ea96c-118">Affiche une grille des relations entre les colonnes de la table de dimension pour l'attribut sélectionné et les colonnes de la table de faits pour le groupe de mesures sélectionné, ainsi que l'option de traitement des valeurs NULL pour la relation.</span><span class="sxs-lookup"><span data-stu-id="ea96c-118">Displays a grid of relationships between dimension table columns for the selected attribute and fact table columns for the selected measure group as well as the null processing option for the relationship.</span></span> <span data-ttu-id="ea96c-119">Cette grille comporte les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="ea96c-119">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="ea96c-120">Option</span><span class="sxs-lookup"><span data-stu-id="ea96c-120">Option</span></span>|<span data-ttu-id="ea96c-121">Définition</span><span class="sxs-lookup"><span data-stu-id="ea96c-121">Definition</span></span>|  
|------------|----------------|  
|<span data-ttu-id="ea96c-122">**Colonnes de dimension**</span><span class="sxs-lookup"><span data-stu-id="ea96c-122">**Dimension Columns**</span></span>|<span data-ttu-id="ea96c-123">Affiche les colonnes de la table de dimension dont est dérivé l'attribut sélectionné dans **Attributs** .</span><span class="sxs-lookup"><span data-stu-id="ea96c-123">Displays the columns from the dimension table on which the attribute selected in **Attributes** is based.</span></span>|  
|<span data-ttu-id="ea96c-124">**Colonnes de groupe de mesures**</span><span class="sxs-lookup"><span data-stu-id="ea96c-124">**Measure Group Columns**</span></span>|<span data-ttu-id="ea96c-125">Sélectionnez **Hérité de la dimension** pour utiliser la relation du groupe de mesures héritée de la dimension, ou sélectionnez une colonne de la table des faits dont est dérivé le groupe de mesures pour définir explicitement une relation.</span><span class="sxs-lookup"><span data-stu-id="ea96c-125">Select either **Inherited from dimension** to use the measure group relationship inherited from the dimension, or select a column from the fact table on which the measure group is based to explicitly define a relationship.</span></span>|  
|<span data-ttu-id="ea96c-126">**Traitement NULL**</span><span class="sxs-lookup"><span data-stu-id="ea96c-126">**Null Processing**</span></span>|<span data-ttu-id="ea96c-127">Sélectionnez une option de traitement des valeurs NULL pour l'attribut.</span><span class="sxs-lookup"><span data-stu-id="ea96c-127">Select a null processing option for the attribute.</span></span> <span data-ttu-id="ea96c-128">Pour plus d’informations sur les options de traitement des valeurs NULL, consultez [Élément NullProcessing &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/nullprocessing-element-assl).</span><span class="sxs-lookup"><span data-stu-id="ea96c-128">For more information about null processing options, see [NullProcessing Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/nullprocessing-element-assl).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea96c-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ea96c-129">See Also</span></span>  
 <span data-ttu-id="ea96c-130">[Boîte de dialogue définir une relation &#40;Analysis Services-données multidimensionnelles&#41;](define-relationship-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="ea96c-130">[Define Relationship Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](define-relationship-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="ea96c-131">Analysis Services les concepteurs et les boîtes de dialogue &#40;les données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="ea96c-131">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
