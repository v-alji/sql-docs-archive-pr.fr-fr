---
title: Boîte de dialogue colonnes clés (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql.asvs.dimensiondesigner.dbv.dataitemCollection.f1
helpviewer_keywords:
- DataItem Collection dialog box
ms.assetid: 585f27f2-d5eb-4516-b29a-2084010b7d51
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8a72a9e137700ddee822e68901bfde971637d07f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602404"
---
# <a name="key-columns-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="90509-102">Boîte de dialogue Colonnes clés (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="90509-102">Key Columns Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="90509-103">La boîte de dialogue **Colonnes clés** permet de modifier la propriété **KeyColumns** d’un attribut.</span><span class="sxs-lookup"><span data-stu-id="90509-103">Use the **Key Columns** dialog box to change the **KeyColumns** property of an attribute.</span></span> <span data-ttu-id="90509-104">Pour plus d’informations, consultez [Modifier la propriété KeyColumn d’un attribut](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span><span class="sxs-lookup"><span data-stu-id="90509-104">For more information, see [Modify the KeyColumn Property of an Attribute](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span></span>  
  
 <span data-ttu-id="90509-105">**Pour afficher la boîte de dialogue Colonnes clés**</span><span class="sxs-lookup"><span data-stu-id="90509-105">**To display the Key Columns dialog box**</span></span>  
  
-   <span data-ttu-id="90509-106">Dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], sélectionnez un attribut puis, dans la fenêtre **Propriétés** , cliquez sur le bouton de sélection (**…**) associé à la propriété **KeyColumns** de cet attribut.</span><span class="sxs-lookup"><span data-stu-id="90509-106">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], select an attribute, and in the **Properties** window, click the ellipsis button (**...**) associated with the **KeyColumns** property of that attribute.</span></span>  
  
## <a name="options"></a><span data-ttu-id="90509-107">Options</span><span class="sxs-lookup"><span data-stu-id="90509-107">Options</span></span>  
 <span data-ttu-id="90509-108">**Table source**</span><span class="sxs-lookup"><span data-stu-id="90509-108">**Source table**</span></span>  
 <span data-ttu-id="90509-109">Sélectionnez la table source dont vous souhaitez sélectionner les colonnes clés.</span><span class="sxs-lookup"><span data-stu-id="90509-109">Select the source table for which you want to select its key columns.</span></span> <span data-ttu-id="90509-110">Vous pouvez sélectionner la table source à partir d'une liste de toutes les tables dans la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="90509-110">You can select the source table from a list of all tables in the Data Source View.</span></span>  
  
 <span data-ttu-id="90509-111">**Colonnes disponibles**</span><span class="sxs-lookup"><span data-stu-id="90509-111">**Available Columns**</span></span>  
 <span data-ttu-id="90509-112">Sélectionnez les colonnes que vous souhaitez utiliser comme colonnes clés.</span><span class="sxs-lookup"><span data-stu-id="90509-112">Select the columns that you want to use as key columns.</span></span> <span data-ttu-id="90509-113">Vous pouvez sélectionner les colonnes qui n’ont pas encore été sélectionnées comme colonnes clés dans une liste de colonnes de la **Table source** spécifiée.</span><span class="sxs-lookup"><span data-stu-id="90509-113">You can select the columns from a list of columns in the specified **Source table** that have not yet been selected as key columns.</span></span>  
  
 <span data-ttu-id="90509-114">Pour ajouter les colonnes sélectionnées à la liste **Colonnes clés** , cliquez sur le bouton **>** .</span><span class="sxs-lookup"><span data-stu-id="90509-114">To add the selected columns to the **Key Columns** list, click the **>** button.</span></span>  
  
 <span data-ttu-id="90509-115">**Colonnes clés**</span><span class="sxs-lookup"><span data-stu-id="90509-115">**Key Columns**</span></span>  
 <span data-ttu-id="90509-116">Définissez l'ordre des colonnes clés sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="90509-116">Define the order of the selected key columns.</span></span> <span data-ttu-id="90509-117">L'ordre des colonnes clés est important pour définir la clé composite correcte.</span><span class="sxs-lookup"><span data-stu-id="90509-117">The order of the key columns is important in defining the correct composite key.</span></span> <span data-ttu-id="90509-118">Pour définir ou redéfinir l’ordre de la liste de colonnes clés, sélectionnez une colonne, puis cliquez sur les boutons **Haut** ou **Bas** .</span><span class="sxs-lookup"><span data-stu-id="90509-118">To order or reorder the list of key columns, select a column, and then click the **Up** or **Down** buttons.</span></span>  
  
 <span data-ttu-id="90509-119">Pour supprimer une colonne de la liste **Colonnes clés** , sélectionnez la colonne, puis cliquez sur le bouton **\<** .</span><span class="sxs-lookup"><span data-stu-id="90509-119">To remove a column from the **Key Columns** list, select the column and click the **\<** button.</span></span>  
  
 <span data-ttu-id="90509-120">**Haut**</span><span class="sxs-lookup"><span data-stu-id="90509-120">**Up**</span></span>  
 <span data-ttu-id="90509-121">Cliquez pour déplacer la colonne sélectionnée dans **Colonnes clés** d’une position vers le haut.</span><span class="sxs-lookup"><span data-stu-id="90509-121">Click to move the column selected in **Key Columns** up one position.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="90509-122">Cette option est activée uniquement si la liste contient plusieurs colonnes et si une colonne est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="90509-122">This option is enabled only if the list contains more than one column and a column is selected.</span></span>  
  
 <span data-ttu-id="90509-123">**Descendre**</span><span class="sxs-lookup"><span data-stu-id="90509-123">**Down**</span></span>  
 <span data-ttu-id="90509-124">Cliquez pour déplacer la colonne sélectionnée dans **Colonnes clés** d’une position vers le bas.</span><span class="sxs-lookup"><span data-stu-id="90509-124">Click to move the column selected in **Key Columns** down one position.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="90509-125">Cette option est activée uniquement si la liste contient plusieurs colonnes et si une colonne est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="90509-125">This option is enabled only if the list contains more than one column and a column is selected.</span></span>  
  
 **>**  
 <span data-ttu-id="90509-126">Cliquez pour ajouter une nouvelle colonne à la fin des colonnes répertoriées dans **Colonnes clés**.</span><span class="sxs-lookup"><span data-stu-id="90509-126">Click to add a new column to the end of the columns listed in **Key Columns**.</span></span>  
  
 **<**  
 <span data-ttu-id="90509-127">Cliquez pour supprimer la colonne sélectionnée des colonnes répertoriées dans **Colonnes clés**.</span><span class="sxs-lookup"><span data-stu-id="90509-127">Click to remove the selected column from the columns listed in **Key Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90509-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="90509-128">See Also</span></span>  
 [<span data-ttu-id="90509-129">Analysis Services les concepteurs et les boîtes de dialogue &#40;les données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="90509-129">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
