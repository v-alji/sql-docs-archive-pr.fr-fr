---
title: Masquer ou figer des colonnes (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.hideunhidecolumnsdb.f1
ms.assetid: 5407aee5-6a07-4559-a2ba-2ca00a242f02
author: minewiskan
ms.author: owend
ms.openlocfilehash: 71398eecbc342b4e3f9c2445fef3023132266dac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696195"
---
# <a name="hide-or-freeze-columns-ssas-tabular"></a><span data-ttu-id="782b4-102">Masquer ou figer des colonnes (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="782b4-102">Hide or Freeze Columns (SSAS Tabular)</span></span>
  <span data-ttu-id="782b4-103">Dans le générateur de modèles, s'il existe des colonnes que vous ne souhaitez pas afficher dans une table, vous pouvez les masquer temporairement.</span><span class="sxs-lookup"><span data-stu-id="782b4-103">In the model designer, if there are columns that you don't want to display in a table, you can temporarily hide them.</span></span> <span data-ttu-id="782b4-104">Masquer une colonne vous permet de disposer de plus d'espace à l'écran pour ajouter de nouvelles colonnes ou de travailler uniquement avec les colonnes contenant des données pertinentes.</span><span class="sxs-lookup"><span data-stu-id="782b4-104">Hiding a column gives you more room on the screen to add new columns or to work with only relevant columns of data.</span></span> <span data-ttu-id="782b4-105">Vous pouvez masquer et afficher des colonnes à partir du menu **Colonne** dans le générateur de modèles ou à partir du menu contextuel disponible dans chaque en-tête de colonne.</span><span class="sxs-lookup"><span data-stu-id="782b4-105">You can hide and unhide columns from the **Column** menu in the model designer, and from the right-click menu available from each column header.</span></span> <span data-ttu-id="782b4-106">Pour garder une zone d'un modèle visible pendant que vous faites défiler le modèle jusqu'à une autre zone, vous pouvez verrouiller des colonnes spécifiques dans une zone en les figeant.</span><span class="sxs-lookup"><span data-stu-id="782b4-106">To keep an area of a model visible while you scroll to another area of the model, you can lock specific columns in one area by freezing them.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="782b4-107">La possibilité de masquer des colonnes n'est pas liée à la sécurité des données, mais sert uniquement à simplifier et raccourcir la liste de colonnes visibles dans le générateur de modèles ou les rapports.</span><span class="sxs-lookup"><span data-stu-id="782b4-107">The ability to hide columns is not intended to be used for data security, only to simplify and shorten the list of columns visible in the model designer or reports.</span></span> <span data-ttu-id="782b4-108">Pour sécuriser des données, vous pouvez définir des rôles de sécurité.</span><span class="sxs-lookup"><span data-stu-id="782b4-108">To secure data, you can define security roles.</span></span> <span data-ttu-id="782b4-109">Les rôles peuvent limiter les métadonnées visibles et les données aux seuls objets définis dans le rôle.</span><span class="sxs-lookup"><span data-stu-id="782b4-109">Roles can limit viewable metadata and data to only those objects defined in the role.</span></span> <span data-ttu-id="782b4-110">Pour plus d’informations, consultez [Rôles &#40;SSAS tabulaire&#41;](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="782b4-110">For more information, see [Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="782b4-111">Quand vous masquez une colonne, vous pouvez masquer la colonne pendant que vous travaillez dans le générateur de modèles ou dans les rapports.</span><span class="sxs-lookup"><span data-stu-id="782b4-111">When you hide a column, you have the option to hide the column while you are working in the model designer or in reports.</span></span> <span data-ttu-id="782b4-112">Si vous masquez toutes les colonnes, la table entière apparaît vide dans le générateur de modèles.</span><span class="sxs-lookup"><span data-stu-id="782b4-112">If you hide all columns, the entire table appears blank in the model designer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="782b4-113">Si vous avez de nombreuses colonnes à masquer, vous pouvez créer une perspective au lieu de masquer et d'afficher des colonnes.</span><span class="sxs-lookup"><span data-stu-id="782b4-113">If you have many columns to hide, you can create a perspective instead of hiding and unhiding columns.</span></span> <span data-ttu-id="782b4-114">Une perspective est une vue personnalisée des données qui simplifie l'utilisation d'un sous-ensemble de données associées.</span><span class="sxs-lookup"><span data-stu-id="782b4-114">A perspective is a custom view of the data that makes it easier to work with subset of related data.</span></span> <span data-ttu-id="782b4-115">Pour plus d’informations, consultez [Créer et gérer des perspectives &#40;SSAS Tabulaire&#41;](perspectives-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="782b4-115">For more information, see [Create and Manage Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md)</span></span>  
  
### <a name="to-hide-an-individual-column"></a><span data-ttu-id="782b4-116">Pour masquer une colonne individuelle</span><span class="sxs-lookup"><span data-stu-id="782b4-116">To hide an individual column</span></span>  
  
1.  <span data-ttu-id="782b4-117">Dans le générateur de modèles, sélectionnez la table contenant la colonne à masquer.</span><span class="sxs-lookup"><span data-stu-id="782b4-117">In the model designer, select the table that contains the column that you want to hide.</span></span>  
  
2.  <span data-ttu-id="782b4-118">Cliquez avec le bouton droit sur la colonne, puis sélectionnez **Masquer les colonnes**, puis cliquez sur **Depuis le concepteur et les rapports**, **Depuis les rapports**ou **Depuis le concepteur**.</span><span class="sxs-lookup"><span data-stu-id="782b4-118">Right-click the column, then click **Hide Columns**, and then click **From Designer and Reports**, **From Reports**, or **From Designer**.</span></span>  
  
### <a name="to-hide-multiple-columns"></a><span data-ttu-id="782b4-119">Pour masquer plusieurs colonnes</span><span class="sxs-lookup"><span data-stu-id="782b4-119">To hide multiple columns</span></span>  
  
1.  <span data-ttu-id="782b4-120">Dans le générateur de modèles, sélectionnez la table contenant les colonnes à masquer.</span><span class="sxs-lookup"><span data-stu-id="782b4-120">In the model designer, select the table that contains the columns that you want to hide.</span></span>  
  
2.  <span data-ttu-id="782b4-121">Cliquez sur le menu **Colonnes** , puis sur **Masquer et afficher.**</span><span class="sxs-lookup"><span data-stu-id="782b4-121">Click on the **Columns** menu, and then click **Hide and Unhide**.</span></span>  
  
3.  <span data-ttu-id="782b4-122">Dans la boîte de dialogue **Masquer et afficher les colonnes** , recherchez le nom de chaque colonne que vous souhaitez masquer, puis désélectionnez **Dans le concepteur** et/ou **Dans les rapports**.</span><span class="sxs-lookup"><span data-stu-id="782b4-122">In the **Hide and Unhide Columns** dialog box, locate each column that you want to hide, and then deselect one or both of **In Designer** and **In Reports**.</span></span>  
  
4.  <span data-ttu-id="782b4-123">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="782b4-123">Click **OK**.</span></span>  
  
### <a name="to-freeze-columns"></a><span data-ttu-id="782b4-124">Pour figer des colonnes</span><span class="sxs-lookup"><span data-stu-id="782b4-124">To freeze columns</span></span>  
  
1.  <span data-ttu-id="782b4-125">Dans le générateur de modèles, sélectionnez la table contenant les colonnes à figer.</span><span class="sxs-lookup"><span data-stu-id="782b4-125">In the model designer, select the table that contains the columns that you want to freeze.</span></span>  
  
2.  <span data-ttu-id="782b4-126">Sélectionnez une ou plusieurs colonnes à figer.</span><span class="sxs-lookup"><span data-stu-id="782b4-126">Select one or more columns to freeze.</span></span>  
  
3.  <span data-ttu-id="782b4-127">Cliquez sur le menu **Colonnes** , puis sur **Figer**.</span><span class="sxs-lookup"><span data-stu-id="782b4-127">Click on the **Columns** menu, and then click **Freeze**..</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="782b4-128">Lorsqu'une colonne est figée, elle est déplacée vers la gauche (ou à l'avant) de la table dans le concepteur.</span><span class="sxs-lookup"><span data-stu-id="782b4-128">When a column(s) is frozen, it is moved to left (or front) of the table in the designer.</span></span> <span data-ttu-id="782b4-129">Libérer la colonne ne la replace pas à son emplacement d'origine.</span><span class="sxs-lookup"><span data-stu-id="782b4-129">Unfreezing the column does not move it back to its original location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="782b4-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="782b4-130">See Also</span></span>  
 <span data-ttu-id="782b4-131">[Tables et colonnes &#40;SSAS tabulaire&#41;](tables-and-columns-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="782b4-131">[Tables and Columns &#40;SSAS Tabular&#41;](tables-and-columns-ssas-tabular.md) </span></span>  
 <span data-ttu-id="782b4-132">[Perspectives &#40;&#41;tabulaire SSAS](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="782b4-132">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="782b4-133">Rôles &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="782b4-133">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  
