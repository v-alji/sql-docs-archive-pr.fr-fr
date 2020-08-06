---
title: Sélectionner la méthode de création (Assistant Dimension) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensiondefinition.f1
ms.assetid: 291b0b2d-a03a-4df6-82f7-90ad92d4d1cf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6338a0bde7865482fb7a98d7ec36ba5a71feb806
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696212"
---
# <a name="select-creation-method-dimension-wizard"></a><span data-ttu-id="cf046-102">Sélectionner la méthode de création (Assistant Dimension)</span><span class="sxs-lookup"><span data-stu-id="cf046-102">Select Creation Method (Dimension Wizard)</span></span>
  <span data-ttu-id="cf046-103">La page **Sélectionner la méthode de création** permet de choisir la méthode de création de la dimension.</span><span class="sxs-lookup"><span data-stu-id="cf046-103">Use the **Select Creation Method** page to select how to create the dimension.</span></span>  
  
 <span data-ttu-id="cf046-104">**Pour ouvrir l'Assistant Dimension**</span><span class="sxs-lookup"><span data-stu-id="cf046-104">**To open the Dimension Wizard**</span></span>  
  
-   <span data-ttu-id="cf046-105">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], dans **l’Explorateur de solutions**, cliquez avec le bouton droit sur le dossier **Dimensions** pour un projet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , puis cliquez sur **Nouvelle dimension**.</span><span class="sxs-lookup"><span data-stu-id="cf046-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, right-click the **Dimensions** folder for an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then click **New Dimension**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cf046-106">Options</span><span class="sxs-lookup"><span data-stu-id="cf046-106">Options</span></span>  
 <span data-ttu-id="cf046-107">**Utiliser une table existante**</span><span class="sxs-lookup"><span data-stu-id="cf046-107">**Use an existing table**</span></span>  
 <span data-ttu-id="cf046-108">Créez une dimension à partir d'une ou de plusieurs tables dans une source de données.</span><span class="sxs-lookup"><span data-stu-id="cf046-108">Create a dimension from one or more tables in a data source.</span></span> <span data-ttu-id="cf046-109">Les attributs qui sont disponibles pour la dimension dépendent de la structure des données dans la table.</span><span class="sxs-lookup"><span data-stu-id="cf046-109">The attributes that are available for the dimension will depend on the structure of the data in the table.</span></span>  
  
 <span data-ttu-id="cf046-110">Pour plus d’informations, consultez [Créer une dimension à l’aide d’une table existante](multidimensional-models/create-a-dimension-by-using-an-existing-table.md).</span><span class="sxs-lookup"><span data-stu-id="cf046-110">For more information, see [Create a Dimension by Using an Existing Table](multidimensional-models/create-a-dimension-by-using-an-existing-table.md).</span></span>  
  
 <span data-ttu-id="cf046-111">**Générer une table de temps dans la source de données**</span><span class="sxs-lookup"><span data-stu-id="cf046-111">**Generate a time table in the data source**</span></span>  
 <span data-ttu-id="cf046-112">Créez une table de temps dans la source de données sous-jacente puis utilisez cette table pour créer une dimension de temps.</span><span class="sxs-lookup"><span data-stu-id="cf046-112">Create a time table in the underlying data source and then use that table to create a time dimension.</span></span> <span data-ttu-id="cf046-113">Utilisez cette option lorsque aucune table de ce type n'existe et que vous ne souhaitez pas utiliser de script pour en créer une.</span><span class="sxs-lookup"><span data-stu-id="cf046-113">Use this option when no such table exists and you do not want to use a script to create one.</span></span> <span data-ttu-id="cf046-114">La nouvelle table de temps contiendra des données pour la plage de dates, les attributs et les calendriers que vous spécifiez dans l'assistant.</span><span class="sxs-lookup"><span data-stu-id="cf046-114">The new time table will contain data for the date range, attributes, and calendars that you specify in the wizard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cf046-115">Pour utiliser cette option, vous devez avoir l'autorisation de créer des objets dans la source de données sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="cf046-115">To use this option, you must have permission to create objects in the underlying data source.</span></span> <span data-ttu-id="cf046-116">Si vous n’avez pas l’autorisation de créer des objets dans la source de données, essayez d’utiliser l’option **Générer une table de temps sur le serveur** .</span><span class="sxs-lookup"><span data-stu-id="cf046-116">If you do not have permission to create objects on the data source, try to use the **Generate a time table on the server** option instead.</span></span>  
  
 <span data-ttu-id="cf046-117">Pour plus d’informations, consultez [Créer une dimension de temps en générant une table de temps](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md).</span><span class="sxs-lookup"><span data-stu-id="cf046-117">For more information, see [Create a Time Dimension by Generating a Time Table](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md).</span></span>  
  
 <span data-ttu-id="cf046-118">**Générer une table de temps sur le serveur**</span><span class="sxs-lookup"><span data-stu-id="cf046-118">**Generate a time table on the server**</span></span>  
 <span data-ttu-id="cf046-119">Créez directement une table de temps sur le serveur, puis utilisez cette table pour créer une dimension de temps.</span><span class="sxs-lookup"><span data-stu-id="cf046-119">Create a time table directly on the server and then use that table to create a time dimension.</span></span> <span data-ttu-id="cf046-120">Utilisez cette option si vous n'avez pas l'autorisation de créer des objets dans la source de données sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="cf046-120">Use this option if you do not have permission to create objects in the underlying data source.</span></span> <span data-ttu-id="cf046-121">La nouvelle dimension de temps contiendra des données pour la plage de dates, les attributs et les calendriers que vous spécifiez dans l'assistant.</span><span class="sxs-lookup"><span data-stu-id="cf046-121">The new time dimension will contain data for the date range, attributes, and calendars that you specify in the wizard.</span></span>  
  
 <span data-ttu-id="cf046-122">Pour plus d’informations, consultez [Créer une dimension de temps en générant une table de temps](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md).</span><span class="sxs-lookup"><span data-stu-id="cf046-122">For more information, see [Create a Time Dimension by Generating a Time Table](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md).</span></span>  
  
 <span data-ttu-id="cf046-123">**Générer une table non temporelle dans la source de données**</span><span class="sxs-lookup"><span data-stu-id="cf046-123">**Generate a non-time table in the data source**</span></span>  
 <span data-ttu-id="cf046-124">Concevez la dimension sans source de données relationnelles sous-jacente, puis générez le schéma nécessaire pour la source de données.</span><span class="sxs-lookup"><span data-stu-id="cf046-124">Design the dimension without an underlying relational data source, and then generate the necessary schema for the data source.</span></span> <span data-ttu-id="cf046-125">Cette approche est appelée modélisation verticale.</span><span class="sxs-lookup"><span data-stu-id="cf046-125">This approach is known as top-down modeling.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cf046-126">Pour utiliser cette option, vous devez avoir l'autorisation de créer des objets dans la source de données sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="cf046-126">To use this option, you must have permission to create objects in the underlying data source.</span></span>  
  
 <span data-ttu-id="cf046-127">Vous pouvez générer la dimension avec ou sans modèle.</span><span class="sxs-lookup"><span data-stu-id="cf046-127">You can build the dimension with or without a template.</span></span> <span data-ttu-id="cf046-128">Pour générer la dimension avec un modèle, sélectionnez le modèle dans la liste **Modèle** .</span><span class="sxs-lookup"><span data-stu-id="cf046-128">To build the dimension with a template, select the template from the **Template** list.</span></span>  
  
 <span data-ttu-id="cf046-129">Pour plus d’informations, consultez [Créer une dimension en générant une table non temporelle dans la source de données](multidimensional-models/create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="cf046-129">For more information, see [Create a Dimension by Generating a Non-Time Table in the Data Source](multidimensional-models/create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md).</span></span>  
  
 <span data-ttu-id="cf046-130">**Modèle**</span><span class="sxs-lookup"><span data-stu-id="cf046-130">**Template**</span></span>  
 <span data-ttu-id="cf046-131">Sélectionnez le modèle que vous souhaitez utiliser pour créer la dimension.</span><span class="sxs-lookup"><span data-stu-id="cf046-131">Select the template that you want to use to create the dimension.</span></span> <span data-ttu-id="cf046-132">Les modèles fournissent un jeu complet de définitions d'attributs et de hiérarchies orientées vers un objectif commercial spécifique.</span><span class="sxs-lookup"><span data-stu-id="cf046-132">Templates provide a complete set of attribute and hierarchy definitions oriented towards a specific business purpose.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cf046-133">Cette option est disponible uniquement quand l’option **Générer une table non temporelle dans la source de données** a été sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cf046-133">This option is only available when the **Generate a non-time table in the data source** option has been selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf046-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cf046-134">See Also</span></span>  
 <span data-ttu-id="cf046-135">[Aide (F1) de l’Assistant Dimension](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="cf046-135">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="cf046-136">[Dimensions &#40;Analysis Services-données multidimensionnelles&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="cf046-136">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="cf046-137">Dimensions dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="cf046-137">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
