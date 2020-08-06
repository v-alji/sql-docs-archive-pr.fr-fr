---
title: Spécifier les informations sur la source (Assistant Dimension) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensionmaintable.f1
ms.assetid: 0538b490-5185-49e1-a783-4ce3539a0de5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 99bbaac0bdf24a18dcde455e779f056b98106dc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612503"
---
# <a name="specify-source-information-dimension-wizard"></a><span data-ttu-id="e0c64-102">Spécifier des informations sur la source (Assistant Dimension)</span><span class="sxs-lookup"><span data-stu-id="e0c64-102">Specify Source Information (Dimension Wizard)</span></span>
  <span data-ttu-id="e0c64-103">La page **Sélectionner la table de dimension principale** permet de sélectionner la vue de source de données, la table de dimension principale, les colonnes clés et la colonne des noms de membre pour la dimension à créer.</span><span class="sxs-lookup"><span data-stu-id="e0c64-103">Use the **Select the Main Dimension Table** page to select the data source view, main dimension table, key columns, and member name column for the dimension to be created.</span></span>  
  
 <span data-ttu-id="e0c64-104">**Pour ouvrir l'Assistant Dimension**</span><span class="sxs-lookup"><span data-stu-id="e0c64-104">**To open the Dimension Wizard**</span></span>  
  
-   <span data-ttu-id="e0c64-105">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], dans **l’Explorateur de solutions**, cliquez avec le bouton droit sur le dossier **Dimensions** pour un projet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , puis cliquez sur **Nouvelle dimension**.</span><span class="sxs-lookup"><span data-stu-id="e0c64-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, right-click the **Dimensions** folder for an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then click **New Dimension**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e0c64-106">Options</span><span class="sxs-lookup"><span data-stu-id="e0c64-106">Options</span></span>  
 <span data-ttu-id="e0c64-107">**Vue de source de données**</span><span class="sxs-lookup"><span data-stu-id="e0c64-107">**Data source view**</span></span>  
 <span data-ttu-id="e0c64-108">Sélectionnez une vue de source de données</span><span class="sxs-lookup"><span data-stu-id="e0c64-108">Select a data source view.</span></span>  
  
 <span data-ttu-id="e0c64-109">**Table principale**</span><span class="sxs-lookup"><span data-stu-id="e0c64-109">**Main table**</span></span>  
 <span data-ttu-id="e0c64-110">Sélectionnez une table à partir de la vue de source de données sélectionnée à utiliser en tant que table principale pour la dimension.</span><span class="sxs-lookup"><span data-stu-id="e0c64-110">Select a table from the selected data source view to use as the main table for the dimension.</span></span>  
  
 <span data-ttu-id="e0c64-111">**Colonnes clés**</span><span class="sxs-lookup"><span data-stu-id="e0c64-111">**Key columns**</span></span>  
 <span data-ttu-id="e0c64-112">Sélectionnez les colonnes clés à partir de la table spécifiée dans **Table principale** pour l’attribut clé de la dimension.</span><span class="sxs-lookup"><span data-stu-id="e0c64-112">Select the key columns from the table specified in **Main table** for the key attribute of the dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e0c64-113">Vous pouvez sélectionner plusieurs colonnes.</span><span class="sxs-lookup"><span data-stu-id="e0c64-113">More than one column can be selected.</span></span> <span data-ttu-id="e0c64-114">Si la table contient une clé primaire composite, sélectionnez toutes les colonnes y étant comprises.</span><span class="sxs-lookup"><span data-stu-id="e0c64-114">If the table contains a composite primary key, select all the columns included in the composite primary key.</span></span> <span data-ttu-id="e0c64-115">L'ordre des colonnes clés est important.</span><span class="sxs-lookup"><span data-stu-id="e0c64-115">The order of the key columns is important.</span></span>  
  
 <span data-ttu-id="e0c64-116">**Colonne de nom**</span><span class="sxs-lookup"><span data-stu-id="e0c64-116">**Name column**</span></span>  
 <span data-ttu-id="e0c64-117">Sélectionnez la colonne de la table spécifiée dans **Table principale** qui fournit les noms de membres pour la dimension.</span><span class="sxs-lookup"><span data-stu-id="e0c64-117">Select the column from the table specified in **Main table** that provides the member names for the dimension.</span></span> <span data-ttu-id="e0c64-118">Une colonne de nom doit être spécifiée lorsqu'une clé composite est utilisée.</span><span class="sxs-lookup"><span data-stu-id="e0c64-118">A name column must be specified when a composite key is used.</span></span> <span data-ttu-id="e0c64-119">Pour créer une colonne de nom pour une clé composite, il est recommandé de créer un calcul nommé dans la vue de source de données qui concatène les colonnes clés spécifiées.</span><span class="sxs-lookup"><span data-stu-id="e0c64-119">To create a name column for a composite key, we recommend that you create a named calculation in the data source view that concatenates the specified key columns.</span></span> <span data-ttu-id="e0c64-120">Lorsqu'une clé unique est utilisée, la colonne de nom est facultative.</span><span class="sxs-lookup"><span data-stu-id="e0c64-120">When a single key is used, the name column is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0c64-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e0c64-121">See Also</span></span>  
 <span data-ttu-id="e0c64-122">[Aide (F1) de l’Assistant Dimension](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="e0c64-122">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="e0c64-123">[Dimensions &#40;Analysis Services-données multidimensionnelles&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e0c64-123">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="e0c64-124">Dimensions dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="e0c64-124">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
