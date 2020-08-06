---
title: Options de schéma de la base de données de la zone de sujet (Assistant génération de schéma) (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.schemagenwizard.subjectareaschemaopts.f1
ms.assetid: 4c109bb8-e19d-412b-908f-bfdd7f872439
author: minewiskan
ms.author: owend
ms.openlocfilehash: 98460332478d02de823addcd113fb9c1e87d6958
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604166"
---
# <a name="subject-area-database-schema-options-schema-generation-wizard-analysis-services---multidimensional-data"></a><span data-ttu-id="28d1f-102">Options du schéma de la base de données de la zone de sujet (Assistant Génération de schéma) (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="28d1f-102">Subject Area Database Schema Options (Schema Generation Wizard) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="28d1f-103">Utilisez la page **Options du schéma de la base de données de la zone de sujet** pour contrôler la génération du schéma et définir la préservation des données.</span><span class="sxs-lookup"><span data-stu-id="28d1f-103">Use the **Subject Area Database Schema Options** page to control how the schema is generated, as well as to define how data is preserved.</span></span>  
  
## <a name="options"></a><span data-ttu-id="28d1f-104">Options</span><span class="sxs-lookup"><span data-stu-id="28d1f-104">Options</span></span>  
 <span data-ttu-id="28d1f-105">**Schéma propriétaire**</span><span class="sxs-lookup"><span data-stu-id="28d1f-105">**Owning schema**</span></span>  
 <span data-ttu-id="28d1f-106">Définit le nom du schéma dans la nouvelle base de données de la zone de sujet.</span><span class="sxs-lookup"><span data-stu-id="28d1f-106">Specifies the name of the schema within the new subject area database.</span></span>  
  
 <span data-ttu-id="28d1f-107">**Créer des clés primaires sur les tables de la dimension**</span><span class="sxs-lookup"><span data-stu-id="28d1f-107">**Create primary keys on dimension tables**</span></span>  
 <span data-ttu-id="28d1f-108">Crée des clés primaires dans les tables de dimension dans le schéma généré.</span><span class="sxs-lookup"><span data-stu-id="28d1f-108">Creates primary keys on the dimension tables in the generated schema.</span></span> <span data-ttu-id="28d1f-109">Aucun index n'est généré si vous ne sélectionnez pas cette option.</span><span class="sxs-lookup"><span data-stu-id="28d1f-109">No index is generated if you do not select this option.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28d1f-110">Si vous ne sélectionnez pas cette option, l'intégrité référentielle est améliorée.</span><span class="sxs-lookup"><span data-stu-id="28d1f-110">If you do not select this option, referential integrity is enforced.</span></span>  
  
 <span data-ttu-id="28d1f-111">**Créer des index**</span><span class="sxs-lookup"><span data-stu-id="28d1f-111">**Create indexes**</span></span>  
 <span data-ttu-id="28d1f-112">Crée des index dans les colonnes clés étrangères dans le schéma généré.</span><span class="sxs-lookup"><span data-stu-id="28d1f-112">Creates indexes on foreign key columns in the generated schema.</span></span>  
  
 <span data-ttu-id="28d1f-113">**Appliquer l'intégrité référentielle**</span><span class="sxs-lookup"><span data-stu-id="28d1f-113">**Enforce referential integrity**</span></span>  
 <span data-ttu-id="28d1f-114">Applique l'intégrité référentielle dans le schéma généré.</span><span class="sxs-lookup"><span data-stu-id="28d1f-114">Enforces referential integrity within the generated schema.</span></span> <span data-ttu-id="28d1f-115">Si vous ne sélectionnez pas cette option, les relations sont créées, mais pas appliquées.</span><span class="sxs-lookup"><span data-stu-id="28d1f-115">If you do not select this option, relationships are created but not enforced.</span></span>  
  
 <span data-ttu-id="28d1f-116">**Préserver les données lors de la régénération**</span><span class="sxs-lookup"><span data-stu-id="28d1f-116">**Preserve data on regeneration**</span></span>  
 <span data-ttu-id="28d1f-117">Conserve les données dans base de données de la zone de sujet lorsque l'Assistant termine son exécution.</span><span class="sxs-lookup"><span data-stu-id="28d1f-117">Retains data in the subject area database when the wizard finishes.</span></span> <span data-ttu-id="28d1f-118">Si vous ne sélectionnez pas cette option, toutes les données de la base de données de la zone de sujet peuvent être effacées sans avertissement.</span><span class="sxs-lookup"><span data-stu-id="28d1f-118">If you do not select this option, all the data in the subject area database may be erased without warning.</span></span>  
  
 <span data-ttu-id="28d1f-119">**Remplir la ou les tables de temps**</span><span class="sxs-lookup"><span data-stu-id="28d1f-119">**Populate time table(s)**</span></span>  
 <span data-ttu-id="28d1f-120">Définit la manière dont l'Assistant remplit les tables de temps.</span><span class="sxs-lookup"><span data-stu-id="28d1f-120">Specifies how the wizard populates the time tables.</span></span> <span data-ttu-id="28d1f-121">Le tableau suivant répertorie les valeurs possibles de cette option.</span><span class="sxs-lookup"><span data-stu-id="28d1f-121">The following table describes the possible values for this option.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28d1f-122">Cette option est activée uniquement si l’Assistant Génération de schéma est ouvert depuis un projet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] en utilisant [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] en mode projet.</span><span class="sxs-lookup"><span data-stu-id="28d1f-122">This option is enabled only if Schema Generation Wizard is called from an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, using [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] in project mode.</span></span>  
  
|<span data-ttu-id="28d1f-123">Valeur</span><span class="sxs-lookup"><span data-stu-id="28d1f-123">Value</span></span>|<span data-ttu-id="28d1f-124">Description</span><span class="sxs-lookup"><span data-stu-id="28d1f-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="28d1f-125">Remplir</span><span class="sxs-lookup"><span data-stu-id="28d1f-125">Populate</span></span>|<span data-ttu-id="28d1f-126">Les tables de temps de la zone de sujet sont remplies.</span><span class="sxs-lookup"><span data-stu-id="28d1f-126">The subject area time tables are populated.</span></span>|  
|<span data-ttu-id="28d1f-127">Ne pas remplir</span><span class="sxs-lookup"><span data-stu-id="28d1f-127">Do not populate</span></span>|<span data-ttu-id="28d1f-128">Les tables de temps de la zone de sujet ne sont pas remplies.</span><span class="sxs-lookup"><span data-stu-id="28d1f-128">The subject area time tables are not populated.</span></span>|  
|<span data-ttu-id="28d1f-129">Remplir uniquement si la table est vide</span><span class="sxs-lookup"><span data-stu-id="28d1f-129">Populate only if empty</span></span>|<span data-ttu-id="28d1f-130">Les tables de temps de la zone de sujet sont remplies uniquement si elles sont vides.</span><span class="sxs-lookup"><span data-stu-id="28d1f-130">The subject area time tables are populated only if they are empty.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28d1f-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="28d1f-131">See Also</span></span>  
 [<span data-ttu-id="28d1f-132">Aide (F1) de l’Assistant génération de schéma &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="28d1f-132">Schema Generation Wizard F1 Help &#40;Analysis Services - Multidimensional Data&#41;</span></span>](schema-generation-wizard-f1-help-analysis-services-multidimensional-data.md)  
  
  
