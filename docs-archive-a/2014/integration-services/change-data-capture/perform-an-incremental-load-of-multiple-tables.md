---
title: Exécuter un chargement incrémentiel de plusieurs tables | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],multiple tables
ms.assetid: 39252dd5-09c3-46f9-a17b-15208cfd336d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e4bf81d1d529e8102271c66839440ef712219600
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602265"
---
# <a name="perform-an-incremental-load-of-multiple-tables"></a><span data-ttu-id="c8cb9-102">Exécuter un chargement incrémentiel de plusieurs table</span><span class="sxs-lookup"><span data-stu-id="c8cb9-102">Perform an Incremental Load of Multiple Tables</span></span>
  <span data-ttu-id="c8cb9-103">Dans la rubrique [Amélioration des chargements incrémentiels avec la capture de données modifiées](change-data-capture-ssis.md), le diagramme illustre un package de base qui effectue un chargement incrémentiel sur une seule table.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-103">In the topic, [Improving Incremental Loads with Change Data Capture](change-data-capture-ssis.md), the diagram illustrates a basic package that performs an incremental load on just one table.</span></span> <span data-ttu-id="c8cb9-104">Toutefois, il est plus fréquent de devoir effectuer un chargement incrémentiel de plusieurs tables.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-104">However, loading one table is not as common as having to perform an incremental load of multiple tables.</span></span>  
  
 <span data-ttu-id="c8cb9-105">Dans le cadre d'un chargement incrémentiel de plusieurs tables, certaines étapes doivent être effectuées une seule fois pour toutes les tables, alors que d'autres doivent être répétées pour chaque table source.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-105">When you perform an incremental load of multiple tables, some steps have to be performed once for all the tables, and other steps have to be repeated for each source table.</span></span> <span data-ttu-id="c8cb9-106">Plusieurs options s’offrent à vous pour implémenter ces étapes dans [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c8cb9-106">You have more than one option for implementing these steps in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="c8cb9-107">Utiliser un package parent et des packages enfants.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-107">Use a parent package and child packages.</span></span>  
  
-   <span data-ttu-id="c8cb9-108">Utiliser plusieurs tâches de flux de données dans un package unique.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-108">Use multiple Data Flow tasks in a single package.</span></span>  
  
## <a name="loading-multiple-tables-by-using-a-parent-package-and-multiple-child-packages"></a><span data-ttu-id="c8cb9-109">Chargement de plusieurs tables à l'aide d'un package parent et de plusieurs packages enfants</span><span class="sxs-lookup"><span data-stu-id="c8cb9-109">Loading Multiple Tables by Using a Parent Package and Multiple Child Packages</span></span>  
 <span data-ttu-id="c8cb9-110">Vous pouvez utiliser un package parent pour effectuer les étapes qui ne doivent être réalisées qu'une seule fois.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-110">You can use a parent package to perform those steps that only have to be done once.</span></span> <span data-ttu-id="c8cb9-111">Les packages enfants effectuent quant à eux les étapes devant être réalisées pour chaque table source.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-111">The child packages will perform those steps that have to be done for each source table.</span></span>  
  
#### <a name="to-create-a-parent-package-that-performs-those-steps-that-only-have-to-be-done-once"></a><span data-ttu-id="c8cb9-112">Pour créer un package parent qui effectue les étapes qui ne doivent être réalisées qu'une seule fois</span><span class="sxs-lookup"><span data-stu-id="c8cb9-112">To create a parent package that performs those steps that only have to be done once</span></span>  
  
1.  <span data-ttu-id="c8cb9-113">Créez un package parent.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-113">Create a parent package.</span></span>  
  
2.  <span data-ttu-id="c8cb9-114">Dans le flux de contrôle, utilisez une tâche d'exécution SQL ou des expressions [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] pour calculer les points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-114">In the control flow, use an Execute SQL task or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expressions to calculate the endpoints.</span></span>  
  
     <span data-ttu-id="c8cb9-115">Pour obtenir un exemple montrant comment calculer les points de terminaison, consultez [Spécifier un intervalle de données modifiées](specify-an-interval-of-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="c8cb9-115">For an example of how to calculate endpoints, see [Specify an Interval of Change Data](specify-an-interval-of-change-data.md).</span></span>  
  
3.  <span data-ttu-id="c8cb9-116">Si nécessaire, utilisez un conteneur de boucles For pour différer l'exécution jusqu'à ce que les données modifiées pour la période sélectionnée soient prêtes.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-116">If needed, use a For Loop container to delay execution until change data for the selected period is ready.</span></span>  
  
     <span data-ttu-id="c8cb9-117">Pour obtenir un exemple de ce type de conteneur For Loop, consultez [Déterminer si les données modifiées sont prêtes](determine-whether-the-change-data-is-ready.md).</span><span class="sxs-lookup"><span data-stu-id="c8cb9-117">For an example of such a For Loop container, see [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md).</span></span>  
  
4.  <span data-ttu-id="c8cb9-118">Utilisez plusieurs tâches d'exécution SQL pour exécuter des packages enfants pour chaque table à charger.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-118">Use multiple Execute Package tasks to execute child packages for each table to be loaded.</span></span> <span data-ttu-id="c8cb9-119">Passez les points de terminaison calculés dans le package parent à chaque package enfant en utilisant des configurations Variable de package parent.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-119">Pass the endpoints calculated in the parent package to each child package by using Parent Package Variable configurations.</span></span>  
  
     <span data-ttu-id="c8cb9-120">Pour plus d’informations, consultez [Tâche d’exécution de package](../control-flow/execute-package-task.md) et [Utiliser les valeurs des variables et des paramètres dans un package enfant](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span><span class="sxs-lookup"><span data-stu-id="c8cb9-120">For more information, see [Execute Package Task](../control-flow/execute-package-task.md) and [Use the Values of Variables and Parameters in a Child Package](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span></span>  
  
#### <a name="to-create-child-packages-to-perform-those-steps-that-have-to-be-done-for-each-source-table"></a><span data-ttu-id="c8cb9-121">Pour créer des packages enfants afin d'effectuer les étapes devant être réalisées pour chaque table source</span><span class="sxs-lookup"><span data-stu-id="c8cb9-121">To create child packages to perform those steps that have to be done for each source table</span></span>  
  
1.  <span data-ttu-id="c8cb9-122">Pour chaque table source, créez un package enfant.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-122">For each source table, create a child package.</span></span>  
  
2.  <span data-ttu-id="c8cb9-123">Dans le flux de contrôle, utilisez une tâche de script ou une tâche d'exécution SQL pour assembler l'instruction SQL qui sera utilisée pour rechercher les modifications.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-123">In the control flow, use a Script task or an Execute SQL task to assemble the SQL statement that will be used to query for changes.</span></span>  
  
     <span data-ttu-id="c8cb9-124">Pour obtenir un exemple montrant comment assembler la requête, consultez [Préparer la recherche des données modifiées](prepare-to-query-for-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="c8cb9-124">For an example of how to assemble the query, see [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md).</span></span>  
  
3.  <span data-ttu-id="c8cb9-125">Utilisez une tâche de flux de données unique dans chaque package enfant pour charger les données modifiées et les appliquer à la destination.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-125">Use a single Data Flow task in each child package to load the change data and apply it to the destination.</span></span> <span data-ttu-id="c8cb9-126">Configurez le flux de données comme décrit dans les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="c8cb9-126">Configure the Data Flow as described in the following steps:</span></span>  
  
    1.  <span data-ttu-id="c8cb9-127">Dans le flux de données, utilisez un composant source pour interroger les tables de modifications à propos des modifications qui se situent dans les points de terminaison sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-127">In the data flow, use a source component to query the change tables for the changes that fall within the selected endpoints.</span></span>  
  
         <span data-ttu-id="c8cb9-128">Pour obtenir un exemple montrant comment interroger les tables de modifications, consultez [Récupérer et comprendre les données modifiées](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="c8cb9-128">For an example of how to query the change tables, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span>  
  
    2.  <span data-ttu-id="c8cb9-129">Utilisez une transformation de fractionnement conditionnel pour diriger les insertions, les mises à jour et les suppressions vers les différentes sorties pour un traitement approprié.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-129">Use a Conditional Split transformation to direct inserts, updates, and deletes to different outputs for appropriate processing.</span></span>  
  
         <span data-ttu-id="c8cb9-130">Pour obtenir un exemple montrant comment configurer cette transformation pour diriger la sortie, consultez [Traiter les insertions, les mises à jour et les suppressions](process-inserts-updates-and-deletes.md).</span><span class="sxs-lookup"><span data-stu-id="c8cb9-130">For an example of how to configure this transformation to direct output, see [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md).</span></span>  
  
    3.  <span data-ttu-id="c8cb9-131">Utilisez un composant de destination pour appliquer les insertions à la destination.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-131">Use a destination component to apply the inserts to the destination.</span></span> <span data-ttu-id="c8cb9-132">Utilisez des transformations de commande OLE DB avec des instructions UPDATE et DELETE paramétrables pour appliquer les mises à jour et les suppressions à la destination.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-132">Use OLE DB Command transformations with parameterized UPDATE and DELETE statements to apply updates and deletes to the destination.</span></span>  
  
         <span data-ttu-id="c8cb9-133">Pour obtenir un exemple montrant comment utiliser cette transformation pour appliquer les mises à jour et les suppressions, consultez [Appliquer des modifications à la destination](apply-the-changes-to-the-destination.md).</span><span class="sxs-lookup"><span data-stu-id="c8cb9-133">For an example of how to use this transformation to apply updates and deletes, see [Apply the Changes to the Destination](apply-the-changes-to-the-destination.md).</span></span>  
  
## <a name="loading-multiple-tables-by-using-multiple-data-flow-tasks-in-a-single-package"></a><span data-ttu-id="c8cb9-134">Chargement de plusieurs tables à l'aide de plusieurs tâches de flux de données dans un package unique</span><span class="sxs-lookup"><span data-stu-id="c8cb9-134">Loading Multiple Tables by Using Multiple Data Flow Tasks in a Single Package</span></span>  
 <span data-ttu-id="c8cb9-135">Une autre méthode consiste à utiliser un package unique qui contient une tâche de flux de données séparée pour chaque table source à charger.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-135">Alternatively, you can use a single package that contains a separate Data Flow task for each source table to be loaded.</span></span>  
  
#### <a name="to-load-multiple-tables-by-using-multiple-data-flow-tasks-in-a-single-package"></a><span data-ttu-id="c8cb9-136">Pour charger plusieurs tables à l'aide de plusieurs tâches de flux de données dans un package unique</span><span class="sxs-lookup"><span data-stu-id="c8cb9-136">To load multiple tables by using multiple Data Flow tasks in a single package</span></span>  
  
1.  <span data-ttu-id="c8cb9-137">Créez un package unique.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-137">Create a single package.</span></span>  
  
2.  <span data-ttu-id="c8cb9-138">Dans le flux de contrôle, utilisez une tâche d’exécution SQL ou des expressions [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] pour calculer les points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-138">In the control flow, use an Execute SQL Task or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expressions to calculate the endpoints.</span></span>  
  
     <span data-ttu-id="c8cb9-139">Pour obtenir un exemple montrant comment calculer les points de terminaison, consultez [Spécifier un intervalle de données modifiées](specify-an-interval-of-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="c8cb9-139">For an example of how to calculate endpoints, see [Specify an Interval of Change Data](specify-an-interval-of-change-data.md).</span></span>  
  
3.  <span data-ttu-id="c8cb9-140">Si nécessaire, utilisez un conteneur de boucles For pour différer l'exécution jusqu'à ce que les données modifiées pour l'intervalle sélectionné soient prêtes.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-140">If needed, use a For Loop container to delay execution until the change data for the selected interval is ready.</span></span>  
  
     <span data-ttu-id="c8cb9-141">Pour obtenir un exemple de ce type de conteneur For Loop, consultez [Déterminer si les données modifiées sont prêtes](determine-whether-the-change-data-is-ready.md).</span><span class="sxs-lookup"><span data-stu-id="c8cb9-141">For an example of such a For Loop container, see [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md).</span></span>  
  
4.  <span data-ttu-id="c8cb9-142">Utilisez une tâche de script ou une tâche d'exécution SQL pour assembler l'instruction SQL qui sera utilisée pour rechercher les modifications.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-142">Use a Script task or an Execute SQL task to assemble the SQL statement that will be used to query for changes.</span></span>  
  
     <span data-ttu-id="c8cb9-143">Pour obtenir un exemple montrant comment assembler la requête, consultez [Préparer la recherche des données modifiées](prepare-to-query-for-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="c8cb9-143">For an example of how to assemble the query, see [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md).</span></span>  
  
5.  <span data-ttu-id="c8cb9-144">Utilisez plusieurs tâches de flux de données pour charger les données modifiées à partir de chaque table source et les appliquer à la destination.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-144">Use multiple Data Flow tasks to load the change data from each source table and apply it to the destination.</span></span> <span data-ttu-id="c8cb9-145">Configurez chaque tâche de flux de données comme décrit dans les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-145">Configure each Data Flow task as described in the following steps.</span></span>  
  
    1.  <span data-ttu-id="c8cb9-146">Dans chaque flux de données, utilisez un composant source pour interroger les tables de modifications à propos des modifications qui se situent dans les points de terminaison sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-146">In each data flow, use a source component to query the change tables for the changes that fall within the selected endpoints.</span></span>  
  
         <span data-ttu-id="c8cb9-147">Pour obtenir un exemple montrant comment interroger les tables de modifications, consultez [Récupérer et comprendre les données modifiées](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="c8cb9-147">For an example of how to query the change tables, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span>  
  
    2.  <span data-ttu-id="c8cb9-148">Utilisez une transformation de fractionnement conditionnel pour diriger les insertions, les mises à jour et les suppressions vers les différentes sorties pour un traitement approprié.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-148">Use a Conditional Split transformation to direct inserts, updates, and deletes to different outputs for appropriate processing.</span></span>  
  
         <span data-ttu-id="c8cb9-149">Pour obtenir un exemple montrant comment configurer cette transformation pour diriger la sortie, consultez [Traiter les insertions, les mises à jour et les suppressions](process-inserts-updates-and-deletes.md).</span><span class="sxs-lookup"><span data-stu-id="c8cb9-149">For an example of how to configure this transformation to direct output, see [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md).</span></span>  
  
    3.  <span data-ttu-id="c8cb9-150">Utilisez un composant de destination pour appliquer les insertions à la destination.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-150">Use a destination component to apply the inserts to the destination.</span></span> <span data-ttu-id="c8cb9-151">Utilisez des transformations de commande OLE DB avec des instructions UPDATE et DELETE paramétrables pour appliquer les mises à jour et les suppressions à la destination.</span><span class="sxs-lookup"><span data-stu-id="c8cb9-151">Use OLE DB Command transformations with parameterized UPDATE and DELETE statements to apply updates and deletes to the destination.</span></span>  
  
         <span data-ttu-id="c8cb9-152">Pour obtenir un exemple montrant comment utiliser cette transformation pour appliquer les mises à jour et les suppressions, consultez [Appliquer des modifications à la destination](apply-the-changes-to-the-destination.md).</span><span class="sxs-lookup"><span data-stu-id="c8cb9-152">For an example of how to use this transformation to apply updates and deletes, see [Apply the Changes to the Destination](apply-the-changes-to-the-destination.md).</span></span>  
  
  
