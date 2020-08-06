---
title: Éditeur de transformation UNPIVOT | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unpivottransformation.f1
helpviewer_keywords:
- Unpivot Transformation Editor
ms.assetid: 72a36ef0-4070-4f6c-9c74-0720109617dd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6c3b93370b34440b73b4c9c78dc7d19fa4095275
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602190"
---
# <a name="unpivot-transformation-editor"></a><span data-ttu-id="0a8a4-102">Éditeur de transformation UnPivot</span><span class="sxs-lookup"><span data-stu-id="0a8a4-102">Unpivot Transformation Editor</span></span>
  <span data-ttu-id="0a8a4-103">Utilisez la boîte de dialogue **Éditeur de transformation UnPivot** pour sélectionner les colonnes à convertir en ligne, et définir la colonne de données et la nouvelle colonne de sortie de valeur croisée.</span><span class="sxs-lookup"><span data-stu-id="0a8a4-103">Use the **Unpivot Transformation Editor** dialog box to select the columns to pivot into rows, and to specify the data column and the new pivot value output column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a8a4-104"> Cette rubrique porte sur le scénario Unpivot décrit dans [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md) pour illustrer l'utilisation des options.</span><span class="sxs-lookup"><span data-stu-id="0a8a4-104">This topic relies on the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md) to illustrate the use of the options.</span></span>  
  
 <span data-ttu-id="0a8a4-105">Pour en savoir plus sur la transformation Unpivot, consultez [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="0a8a4-105">To learn more about the Unpivot transformation, see [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="0a8a4-106">Options</span><span class="sxs-lookup"><span data-stu-id="0a8a4-106">Options</span></span>  
 <span data-ttu-id="0a8a4-107">**Colonnes d'entrée disponibles**</span><span class="sxs-lookup"><span data-stu-id="0a8a4-107">**Available Input Columns**</span></span>  
 <span data-ttu-id="0a8a4-108">Définissez les colonnes à convertir en lignes en utilisant les cases à cocher.</span><span class="sxs-lookup"><span data-stu-id="0a8a4-108">Using the check boxes, specify the columns to pivot into rows.</span></span>  
  
 <span data-ttu-id="0a8a4-109">**Nom**</span><span class="sxs-lookup"><span data-stu-id="0a8a4-109">**Name**</span></span>  
 <span data-ttu-id="0a8a4-110">Affiche le nom de la colonne d'entrée disponible.</span><span class="sxs-lookup"><span data-stu-id="0a8a4-110">View the name of the available input column.</span></span>  
  
 <span data-ttu-id="0a8a4-111">**Transfert direct**</span><span class="sxs-lookup"><span data-stu-id="0a8a4-111">**Pass Through**</span></span>  
 <span data-ttu-id="0a8a4-112">Indique s'il faut inclure la colonne dans la sortie supprimée du tableau croisé dynamique.</span><span class="sxs-lookup"><span data-stu-id="0a8a4-112">Indicate whether to include the column in the unpivoted output.</span></span>  
  
 <span data-ttu-id="0a8a4-113">**Colonne d'entrée**</span><span class="sxs-lookup"><span data-stu-id="0a8a4-113">**Input Column**</span></span>  
 <span data-ttu-id="0a8a4-114">Sélectionnez dans la liste le nom d'une colonne d'entrée pour chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="0a8a4-114">Select from the list of available input columns for each row.</span></span> <span data-ttu-id="0a8a4-115">Vos sélections se reflètent dans les sélections des cases à cocher de la table **Colonnes d'entrée disponibles** .</span><span class="sxs-lookup"><span data-stu-id="0a8a4-115">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="0a8a4-116">Dans le scénario Unpivot décrit dans [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), les colonnes d'entrée sont **Ham**, **Soda**, **Milk**, **Beer**et **Chips** .</span><span class="sxs-lookup"><span data-stu-id="0a8a4-116">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Input Columns are the **Ham**, **Soda**, **Milk**, **Beer**, and **Chips** columns.</span></span>  
  
 <span data-ttu-id="0a8a4-117">**Colonne de destination**</span><span class="sxs-lookup"><span data-stu-id="0a8a4-117">**Destination Column**</span></span>  
 <span data-ttu-id="0a8a4-118">Définissez le nom de la colonne de données.</span><span class="sxs-lookup"><span data-stu-id="0a8a4-118">Provide a name for the data column.</span></span>  
  
 <span data-ttu-id="0a8a4-119">Dans le scénario Unpivot décrit dans [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), la colonne de destination est la colonne de quantité (**Qty**).</span><span class="sxs-lookup"><span data-stu-id="0a8a4-119">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Destination Column is the quantity (**Qty**) column.</span></span>  
  
 <span data-ttu-id="0a8a4-120">**Valeur de clé de tableau croisé dynamique**</span><span class="sxs-lookup"><span data-stu-id="0a8a4-120">**Pivot Key Value**</span></span>  
 <span data-ttu-id="0a8a4-121">Tapez le nom de la valeur croisée dynamique.</span><span class="sxs-lookup"><span data-stu-id="0a8a4-121">Provide a name for the pivot value.</span></span> <span data-ttu-id="0a8a4-122">Par défaut, il s'agit du nom de la colonne d'entrée ; vous pouvez néanmoins choisir un nom unique et descriptif.</span><span class="sxs-lookup"><span data-stu-id="0a8a4-122">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="0a8a4-123">Il est possible de spécifier la valeur de cette propriété en utilisant l'expression d'une propriété.</span><span class="sxs-lookup"><span data-stu-id="0a8a4-123">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="0a8a4-124">Dans le scénario Unpivot décrit dans [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), les valeurs croisées dynamiques apparaîtront dans la nouvelle colonne Produit définie par l'option **Nom de colonne de la valeur de clé de tableau croisé dynamique** comme les valeurs de texte **Ham**, **Soda**, **Milk**, **Beer**et **Chips**.</span><span class="sxs-lookup"><span data-stu-id="0a8a4-124">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Pivot Values will appear in the new Product column designated by the **Pivot Key Value Column Name** option, as the text values **Ham**, **Soda**, **Milk**, **Beer**, and **Chips**.</span></span>  
  
 <span data-ttu-id="0a8a4-125">**Nom de colonne de la valeur de clé de tableau croisé dynamique**</span><span class="sxs-lookup"><span data-stu-id="0a8a4-125">**Pivot Key Value Column Name**</span></span>  
 <span data-ttu-id="0a8a4-126">Tapez le nom de la colonne de valeur croisée dynamique.</span><span class="sxs-lookup"><span data-stu-id="0a8a4-126">Provide a name for the pivot value column.</span></span> <span data-ttu-id="0a8a4-127">La valeur par défaut est « Valeur de clé de tableau croisé dynamique ». Toutefois, vous pouvez choisir un nom descriptif unique.</span><span class="sxs-lookup"><span data-stu-id="0a8a4-127">The default is "Pivot Key Value"; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="0a8a4-128">Dans le scénario Unpivot décrit dans [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), le nom de la colonne de la valeur de clé de tableau croisé dynamique est **Product** et définit la nouvelle colonne **Product** dans laquelle les colonnes **Ham**, **Soda**, **Milk**, **Beer**et **Chips** ne sont pas croisées dynamiquement.</span><span class="sxs-lookup"><span data-stu-id="0a8a4-128">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Pivot Key Value Column Name is **Product** and designates the new **Product** column into which the **Ham**, **Soda**, **Milk**, **Beer**, and **Chips** columns are unpivoted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a8a4-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0a8a4-129">See Also</span></span>  
 <span data-ttu-id="0a8a4-130">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="0a8a4-130">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="0a8a4-131">Transformation de tableau croisé dynamique</span><span class="sxs-lookup"><span data-stu-id="0a8a4-131">Pivot Transformation</span></span>](data-flow/transformations/pivot-transformation.md)  
  
  
