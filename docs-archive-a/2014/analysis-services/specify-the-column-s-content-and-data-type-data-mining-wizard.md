---
title: Spécifier le contenu et le type de données de la colonne&#39;s (Assistant Exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.specifycontentdatatype.f1
ms.assetid: 7061f674-e806-46f2-8c15-e260a3c69a17
author: minewiskan
ms.author: owend
ms.openlocfilehash: 66af7280e444036468b9cc33a131993524d3586d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612499"
---
# <a name="specify-the-column39s-content-and-data-type-data-mining-wizard"></a><span data-ttu-id="55b77-102">Spécifier le contenu et le type de données de la colonne&#39;s (Assistant Exploration de données)</span><span class="sxs-lookup"><span data-stu-id="55b77-102">Specify the Column&#39;s Content and Data Type (Data Mining Wizard)</span></span>
  <span data-ttu-id="55b77-103">La page **Spécifier le type de contenu et de données des colonnes** permet de modifier les types de colonne et de contenu qui ont déjà été définis par l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="55b77-103">Use the **Specify the Column's Content and Data Type** page to modify the column and content types that have already been set by the wizard.</span></span> <span data-ttu-id="55b77-104">L'Assistant utilise les types de données des colonnes sources et les capacités de l'algorithme sélectionné pour déterminer les types de données et de contenu par défaut de chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="55b77-104">The wizard uses the data types of the source columns and the capabilities of the selected algorithm to determine the default data and content types for each column.</span></span>  
  
 <span data-ttu-id="55b77-105">**Pour plus d’informations :** [Assistant Exploration de données &#40;Analysis Services - Exploration de données&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Créer une structure d’exploration de données relationnelle](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="55b77-105">**For More Information:** [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="55b77-106">Options</span><span class="sxs-lookup"><span data-stu-id="55b77-106">Options</span></span>  
 <span data-ttu-id="55b77-107">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="55b77-107">**Columns**</span></span>  
 <span data-ttu-id="55b77-108">Liste des colonnes définies dans la page **Spécifier les données d’apprentissage** de l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="55b77-108">A list of the columns that are defined in the **Specify the Training Data** page of the wizard.</span></span>  
  
 <span data-ttu-id="55b77-109">**Type de contenu**</span><span class="sxs-lookup"><span data-stu-id="55b77-109">**Content Type**</span></span>  
 <span data-ttu-id="55b77-110">Type de contenu attribué à chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="55b77-110">The content type that is assigned to each column.</span></span> <span data-ttu-id="55b77-111">Cliquez dans une cellule pour modifier le type de contenu.</span><span class="sxs-lookup"><span data-stu-id="55b77-111">Click inside a cell to change the content type.</span></span> <span data-ttu-id="55b77-112">Pour plus d’informations sur les types de contenu, consultez [Types de contenu &#40;exploration de données&#41;](data-mining/content-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="55b77-112">For more information about content types, see [Content Types &#40;Data Mining&#41;](data-mining/content-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="55b77-113">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="55b77-113">**Data Type**</span></span>  
 <span data-ttu-id="55b77-114">Types de données attribués à chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="55b77-114">The data types that are assigned to each column.</span></span> <span data-ttu-id="55b77-115">Cliquez dans une cellule pour modifier le type de données.</span><span class="sxs-lookup"><span data-stu-id="55b77-115">Click inside a cell to change the data type.</span></span> <span data-ttu-id="55b77-116">Pour plus d’informations sur les types de données, consultez [Types de données &#40;exploration de données&#41;](data-mining/data-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="55b77-116">For more information about data types, see [Data Types &#40;Data Mining&#41;](data-mining/data-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="55b77-117">**Detect**</span><span class="sxs-lookup"><span data-stu-id="55b77-117">**Detect**</span></span>  
 <span data-ttu-id="55b77-118">Cliquez sur cette option pour détecter automatiquement les types de contenu continu et discret d'une colonne numérique.</span><span class="sxs-lookup"><span data-stu-id="55b77-118">Click to automatically detect the continuous and discrete content types for numeric column.</span></span> <span data-ttu-id="55b77-119">Ceci ne s'applique pas aux structures d'exploration de données basées sur les sources de données OLAP.</span><span class="sxs-lookup"><span data-stu-id="55b77-119">This does not apply to mining structures that are based on OLAP data sources.</span></span> <span data-ttu-id="55b77-120">Pour les structures d'exploration de données OLAP, l'Assistant détecte automatiquement les types de contenu et en choisit un compatible avec l'algorithme sélectionné.</span><span class="sxs-lookup"><span data-stu-id="55b77-120">For OLAP mining structures, the wizard automatically detects content types and chooses a type that is compatible with the selected algorithm.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55b77-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="55b77-121">See Also</span></span>  
 <span data-ttu-id="55b77-122">[Fin de l’Assistant &#40;l’Assistant Exploration de données&#41;](completing-the-wizard-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="55b77-122">[Completing the Wizard &#40;Data Mining Wizard&#41;](completing-the-wizard-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="55b77-123">[Aide (F1) de l’Assistant Exploration de données &#40;Analysis Services-exploration de données&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="55b77-123">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="55b77-124">Spécifiez les données d’apprentissage &#40;l’Assistant Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="55b77-124">Specify the Training Data &#40;Data Mining Wizard&#41;</span></span>](specify-the-training-data-data-mining-wizard.md)  
  
  
