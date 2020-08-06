---
title: Spécifier les conventions de nom (Assistant génération de schéma) (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.schemagenwizard.namingconventions.f1
ms.assetid: 02d830ea-5b1f-4485-9f94-d64b8bea592b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2e9588b49331934041cad888142d29d189fc1a7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612511"
---
# <a name="specify-naming-conventions-schema-generation-wizard-analysis-services---multidimensional-data"></a><span data-ttu-id="b78c6-102">Spécifier les conventions de nom (Assistant Génération de schéma) (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="b78c6-102">Specify Naming Conventions (Schema Generation Wizard) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="b78c6-103">Utilisez la page **Spécifier les conventions de nom** pour définir les conventions de nom utilisées par l'Assistant Génération de schéma lors de la création des objets de schéma.</span><span class="sxs-lookup"><span data-stu-id="b78c6-103">Use the **Specify Naming Conventions** page to define the naming conventions that the Schema Generation Wizard uses when creating schema objects.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b78c6-104">Options</span><span class="sxs-lookup"><span data-stu-id="b78c6-104">Options</span></span>  
 <span data-ttu-id="b78c6-105">**Option**</span><span class="sxs-lookup"><span data-stu-id="b78c6-105">**Option**</span></span>  
 <span data-ttu-id="b78c6-106">Spécifiez les conventions de nom à utiliser par l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="b78c6-106">Specify the naming conventions for the wizard to use.</span></span> <span data-ttu-id="b78c6-107">Le tableau ci-dessous décrit les options que vous pouvez spécifier.</span><span class="sxs-lookup"><span data-stu-id="b78c6-107">The following table describes the options you can specify.</span></span>  
  
|<span data-ttu-id="b78c6-108">Option</span><span class="sxs-lookup"><span data-stu-id="b78c6-108">Option</span></span>|<span data-ttu-id="b78c6-109">Description</span><span class="sxs-lookup"><span data-stu-id="b78c6-109">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b78c6-110">**Séparateur**</span><span class="sxs-lookup"><span data-stu-id="b78c6-110">**Separator**</span></span>|<span data-ttu-id="b78c6-111">Spécifie le caractère qui sépare les mots dans un nom d'objet.</span><span class="sxs-lookup"><span data-stu-id="b78c6-111">Specifies the character that separates words in an object name.</span></span> <span data-ttu-id="b78c6-112">Dans la colonne **Valeur** , sélectionnez les options **Trait de soulignement**, **Espace**ou **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="b78c6-112">In the **Value** column, select **Underscore**, **Space**, or **None**.</span></span> <span data-ttu-id="b78c6-113">La valeur par défaut est **Trait de soulignement**.</span><span class="sxs-lookup"><span data-stu-id="b78c6-113">The default is **Underscore**.</span></span>|  
|<span data-ttu-id="b78c6-114">**Préfixe de la colonne clé primaire**</span><span class="sxs-lookup"><span data-stu-id="b78c6-114">**Primary key column prefix**</span></span>|<span data-ttu-id="b78c6-115">Spécifie la chaîne de préfixe du nom de chaque colonne clé primaire.</span><span class="sxs-lookup"><span data-stu-id="b78c6-115">Specifies the string to prefix the name of each primary key column.</span></span> <span data-ttu-id="b78c6-116">La valeur par défaut est **PK**.</span><span class="sxs-lookup"><span data-stu-id="b78c6-116">The default is **PK**.</span></span>|  
|<span data-ttu-id="b78c6-117">**Préfixe de la colonne clé étrangère**</span><span class="sxs-lookup"><span data-stu-id="b78c6-117">**Foreign key column prefix**</span></span>|<span data-ttu-id="b78c6-118">Spécifie la chaîne de préfixe du nom de chaque colonne clé étrangère.</span><span class="sxs-lookup"><span data-stu-id="b78c6-118">Specifies the string to prefix the name of each foreign key column.</span></span> <span data-ttu-id="b78c6-119">La valeur par défaut est **FK**.</span><span class="sxs-lookup"><span data-stu-id="b78c6-119">The default is **FK**.</span></span>|  
|<span data-ttu-id="b78c6-120">**Suffixe du nom de l'attribut**</span><span class="sxs-lookup"><span data-stu-id="b78c6-120">**Attribute name suffix**</span></span>|<span data-ttu-id="b78c6-121">Spécifie la chaîne à ajouter au nom de chaque colonne d'attribut.</span><span class="sxs-lookup"><span data-stu-id="b78c6-121">Specifies the string to be appended to the name of each attribute column.</span></span> <span data-ttu-id="b78c6-122">La valeur par défaut est **Name**.</span><span class="sxs-lookup"><span data-stu-id="b78c6-122">The default is **Name**.</span></span>|  
|<span data-ttu-id="b78c6-123">**Suffixe du cumul personnalisé**</span><span class="sxs-lookup"><span data-stu-id="b78c6-123">**Custom rollup suffix**</span></span>|<span data-ttu-id="b78c6-124">Spécifie la chaîne à ajouter au nom de chaque colonne de cumul.</span><span class="sxs-lookup"><span data-stu-id="b78c6-124">Specifies the string to be appended to the name of each rollup column.</span></span> <span data-ttu-id="b78c6-125">La valeur par défaut est **CustomRollup**.</span><span class="sxs-lookup"><span data-stu-id="b78c6-125">The default is **CustomRollup**.</span></span>|  
|<span data-ttu-id="b78c6-126">**Suffixe des propriétés de cumul personnalisé**</span><span class="sxs-lookup"><span data-stu-id="b78c6-126">**Custom rollup Properties suffix**</span></span>|<span data-ttu-id="b78c6-127">Spécifie la chaîne à ajouter au nom de chaque colonne des propriétés de cumul.</span><span class="sxs-lookup"><span data-stu-id="b78c6-127">Specifies the string to be appended to the name of each rollup property column.</span></span> <span data-ttu-id="b78c6-128">La valeur par défaut est **CustomRollupProperties**.</span><span class="sxs-lookup"><span data-stu-id="b78c6-128">The default is **CustomRollupProperties**.</span></span>|  
|<span data-ttu-id="b78c6-129">**Suffixe de l'opérateur unaire**</span><span class="sxs-lookup"><span data-stu-id="b78c6-129">**Unary operator suffix**</span></span>|<span data-ttu-id="b78c6-130">Spécifie la chaîne à ajouter au nom de chaque colonne d'opérateur unaire.</span><span class="sxs-lookup"><span data-stu-id="b78c6-130">Specifies the string to be appended to the name of each unary operator column.</span></span> <span data-ttu-id="b78c6-131">La valeur par défaut est **UnaryOperator**.</span><span class="sxs-lookup"><span data-stu-id="b78c6-131">The default is **UnaryOperator**.</span></span>|  
  
 <span data-ttu-id="b78c6-132">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="b78c6-132">**Value**</span></span>  
 <span data-ttu-id="b78c6-133">Spécifiez une valeur pour l’option spécifiée dans **Option** , que vous souhaitez utiliser lors de la génération du schéma.</span><span class="sxs-lookup"><span data-stu-id="b78c6-133">Specify a value for the option specified in **Option** that you want to use when the schema is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b78c6-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b78c6-134">See Also</span></span>  
 <span data-ttu-id="b78c6-135">[Aide (F1) de l’Assistant génération de schéma &#40;Analysis Services-données multidimensionnelles&#41;](schema-generation-wizard-f1-help-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="b78c6-135">[Schema Generation Wizard F1 Help &#40;Analysis Services - Multidimensional Data&#41;](schema-generation-wizard-f1-help-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="b78c6-136">Analysis Services assistants &#40;&#41;de données multidimensionnelles</span><span class="sxs-lookup"><span data-stu-id="b78c6-136">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
