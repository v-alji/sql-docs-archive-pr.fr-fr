---
title: Spécifier une requête SQL ou MDX (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.specsqlmdxquery.f1
ms.assetid: e4128221-3b46-48be-b0f1-d82477ce6782
author: minewiskan
ms.author: owend
ms.openlocfilehash: bce5e92aaed7a62311e989d6963e4fa5764028ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705476"
---
# <a name="specify-a-sql-or-mdx-query-ssas"></a><span data-ttu-id="0a0e5-102">Spécifier une requête SQL ou MDX (SSAS)</span><span class="sxs-lookup"><span data-stu-id="0a0e5-102">Specify a SQL or MDX Query (SSAS)</span></span>
  <span data-ttu-id="0a0e5-103">Cette page de l' **Assistant Importation de table** vous permet d'importer des données à l'aide d'une requête SQL ou MDX.</span><span class="sxs-lookup"><span data-stu-id="0a0e5-103">This page of the **Table Import Wizard** enables you to import data by using a SQL or MDX query.</span></span> <span data-ttu-id="0a0e5-104">Pour accéder à l'Assistant [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dans le menu **Modèle** , cliquez sur **Importer à partir de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="0a0e5-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="0a0e5-105">La requête peut manipuler les données importées.</span><span class="sxs-lookup"><span data-stu-id="0a0e5-105">The query can manipulate the data that is imported.</span></span> <span data-ttu-id="0a0e5-106">Par exemple, vous pouvez joindre des données depuis des tables différentes ou sélectionner uniquement les lignes qui répondent à certains critères.</span><span class="sxs-lookup"><span data-stu-id="0a0e5-106">For example, you could join data from different tables or select only rows that meet certain criteria.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="0a0e5-107">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="0a0e5-107">UI element list</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0a0e5-108">Terme</span><span class="sxs-lookup"><span data-stu-id="0a0e5-108">Term</span></span>|<span data-ttu-id="0a0e5-109">Définition</span><span class="sxs-lookup"><span data-stu-id="0a0e5-109">Definition</span></span>|  
|<span data-ttu-id="0a0e5-110">**Nom convivial de la requête**</span><span class="sxs-lookup"><span data-stu-id="0a0e5-110">**Friendly Query Name**</span></span>|<span data-ttu-id="0a0e5-111">Tapez un nom unique pour la requête.</span><span class="sxs-lookup"><span data-stu-id="0a0e5-111">Type a unique name for the query.</span></span> <span data-ttu-id="0a0e5-112">Ce champ est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="0a0e5-112">This is a required field.</span></span>|  
|<span data-ttu-id="0a0e5-113">**Instruction SQL**</span><span class="sxs-lookup"><span data-stu-id="0a0e5-113">**SQL Statement**</span></span>|<span data-ttu-id="0a0e5-114">Tapez ou collez une instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="0a0e5-114">Type or paste a SQL statement.</span></span>|  
|<span data-ttu-id="0a0e5-115">**Procéder à la validation**</span><span class="sxs-lookup"><span data-stu-id="0a0e5-115">**Validate**</span></span>|<span data-ttu-id="0a0e5-116">Déterminez si l'instruction SQL est valide.</span><span class="sxs-lookup"><span data-stu-id="0a0e5-116">Determine if the SQL statement is valid.</span></span>|  
|<span data-ttu-id="0a0e5-117">**Concevez**</span><span class="sxs-lookup"><span data-stu-id="0a0e5-117">**Design**</span></span>|<span data-ttu-id="0a0e5-118">Concevez une instruction SQL à l'aide de la boîte de dialogue du concepteur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="0a0e5-118">Design a SQL statement by using the query designer dialog box.</span></span> <span data-ttu-id="0a0e5-119">Pour plus d’informations, consultez [Concepteur de requêtes relationnelles &#40;SSAS&#41;](relational-query-designer-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="0a0e5-119">For more information, see [Relational Query Designer &#40;SSAS&#41;](relational-query-designer-ssas.md).</span></span>|  
  
  
