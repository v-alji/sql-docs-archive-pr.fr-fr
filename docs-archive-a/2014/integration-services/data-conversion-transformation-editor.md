---
title: Éditeur de transformation de conversion de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataconversiontransformation.f1
helpviewer_keywords:
- Data Conversion Transformation Editor
ms.assetid: 7b4e4873-e8fe-4549-a965-65bebdb270bc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4b893f04dcca2dd2a1a5874b55c1c1c608aaeb12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709835"
---
# <a name="data-conversion-transformation-editor"></a><span data-ttu-id="ab7e0-102">Éditeur de transformation de conversion de données</span><span class="sxs-lookup"><span data-stu-id="ab7e0-102">Data Conversion Transformation Editor</span></span>
  <span data-ttu-id="ab7e0-103">Utilisez la boîte de dialogue **Éditeur de transformation de conversion de données** pour sélectionner les colonnes à convertir, sélectionner le type de données de conversion des colonnes et définir les attributs de conversion.</span><span class="sxs-lookup"><span data-stu-id="ab7e0-103">Use the **Data Conversion Transformation Editor** dialog box to select the columns to convert, select the data type to which the column is converted, and set conversion attributes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ab7e0-104">La `FastParse` propriété des colonnes de sortie de la transformation de conversion de données n’est pas disponible dans l **'éditeur de transformation de conversion de données**, mais elle peut être définie à l’aide de l' **éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="ab7e0-104">The `FastParse` property of the output columns of the Data Conversion transformation is not available in the **Data Conversion Transformation Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="ab7e0-105">Pour plus d'informations sur cette propriété, consultez la section Transformation de conversion de données dans [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="ab7e0-105">For more information on this property, see the Data Conversion Transformation section of [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="ab7e0-106">Pour en savoir plus sur la transformation de conversion de données, consultez [Data Conversion Transformation](data-flow/transformations/data-conversion-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="ab7e0-106">To learn more about the Data Conversion transformation, see [Data Conversion Transformation](data-flow/transformations/data-conversion-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ab7e0-107">Options</span><span class="sxs-lookup"><span data-stu-id="ab7e0-107">Options</span></span>  
 <span data-ttu-id="ab7e0-108">**Colonnes d'entrée disponibles**</span><span class="sxs-lookup"><span data-stu-id="ab7e0-108">**Available Input Columns**</span></span>  
 <span data-ttu-id="ab7e0-109">Sélectionnez les colonnes à convertir en activant les cases à cocher.</span><span class="sxs-lookup"><span data-stu-id="ab7e0-109">Select columns to convert by using the check boxes.</span></span> <span data-ttu-id="ab7e0-110">Les sélections ajoutent des colonnes d'entrée à la table ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="ab7e0-110">Your selections add input columns to the table below.</span></span>  
  
 <span data-ttu-id="ab7e0-111">**Colonne d'entrée**</span><span class="sxs-lookup"><span data-stu-id="ab7e0-111">**Input Column**</span></span>  
 <span data-ttu-id="ab7e0-112">Sélectionnez les colonnes à convertir dans la liste des colonnes d'entrée disponibles.</span><span class="sxs-lookup"><span data-stu-id="ab7e0-112">Select columns to convert from the list of available input columns.</span></span> <span data-ttu-id="ab7e0-113">Vos sélections sont reflétées dans les sélections de cases à cocher ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="ab7e0-113">Your selections are reflected in the check box selections above.</span></span>  
  
 <span data-ttu-id="ab7e0-114">**Alias de sortie**</span><span class="sxs-lookup"><span data-stu-id="ab7e0-114">**Output Alias**</span></span>  
 <span data-ttu-id="ab7e0-115">Tapez un alias pour chaque nouvelle colonne.</span><span class="sxs-lookup"><span data-stu-id="ab7e0-115">Type an alias for each new column.</span></span> <span data-ttu-id="ab7e0-116">La valeur par défaut est `Copy of`, suivi du nom de la colonne d’entrée. Toutefois, vous pouvez choisir n’importe quel nom descriptif unique.</span><span class="sxs-lookup"><span data-stu-id="ab7e0-116">The default is `Copy of` followed by the input column name; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="ab7e0-117">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="ab7e0-117">**Data Type**</span></span>  
 <span data-ttu-id="ab7e0-118">Sélectionnez un type de données dans la liste.</span><span class="sxs-lookup"><span data-stu-id="ab7e0-118">Select an available data type from the list.</span></span> <span data-ttu-id="ab7e0-119">Pour plus d’informations, consultez [Types de données Integration Services](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ab7e0-119">For more information, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="ab7e0-120">**Longueur**</span><span class="sxs-lookup"><span data-stu-id="ab7e0-120">**Length**</span></span>  
 <span data-ttu-id="ab7e0-121">Définissez la longueur de colonne pour les données de chaînes.</span><span class="sxs-lookup"><span data-stu-id="ab7e0-121">Set the column length for string data.</span></span>  
  
 <span data-ttu-id="ab7e0-122">**Précision**</span><span class="sxs-lookup"><span data-stu-id="ab7e0-122">**Precision**</span></span>  
 <span data-ttu-id="ab7e0-123">Définissez la précision des données numériques.</span><span class="sxs-lookup"><span data-stu-id="ab7e0-123">Set the precision for numeric data.</span></span>  
  
 <span data-ttu-id="ab7e0-124">**Mise à l’échelle**</span><span class="sxs-lookup"><span data-stu-id="ab7e0-124">**Scale**</span></span>  
 <span data-ttu-id="ab7e0-125">Définissez l'échelle des données numériques.</span><span class="sxs-lookup"><span data-stu-id="ab7e0-125">Set the scale for numeric data.</span></span>  
  
 <span data-ttu-id="ab7e0-126">**Page de codes**</span><span class="sxs-lookup"><span data-stu-id="ab7e0-126">**Code page**</span></span>  
 <span data-ttu-id="ab7e0-127">Sélectionnez la page de codes appropriée pour les colonnes de type DT_STR.</span><span class="sxs-lookup"><span data-stu-id="ab7e0-127">Select the appropriate code page for columns of type DT_STR.</span></span>  
  
 <span data-ttu-id="ab7e0-128">**Configurer la sortie d’erreur**</span><span class="sxs-lookup"><span data-stu-id="ab7e0-128">**Configure error output**</span></span>  
 <span data-ttu-id="ab7e0-129">Indiquez la façon dont les erreurs au niveau des lignes sont gérées via la boîte de dialogue [Configurer la sortie d’erreur](../../2014/integration-services/configure-error-output.md) .</span><span class="sxs-lookup"><span data-stu-id="ab7e0-129">Specify how to handle row-level errors by using the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab7e0-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ab7e0-130">See Also</span></span>  
 <span data-ttu-id="ab7e0-131">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ab7e0-131">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="ab7e0-132">Convertir des données en un type différent à l'aide de la transformation de conversion de données</span><span class="sxs-lookup"><span data-stu-id="ab7e0-132">Convert Data to a Different Data Type by Using the Data Conversion Transformation</span></span>](data-flow/transformations/convert-data-type-by-using-data-conversion-transformation.md)  
  
  
