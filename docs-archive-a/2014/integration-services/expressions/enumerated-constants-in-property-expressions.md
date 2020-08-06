---
title: Constantes énumérées dans des expressions de propriété | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- enumerators [Integration Services]
- packages [Integration Services], expressions
- dynamic properties
- updating package properties
- enumerated constants [Integration Services]
- property expressions [Integration Services]
ms.assetid: a4418315-38e2-4ad3-8784-576163b25d6f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9cb4ae32bf564e98d8cfc843e9497b15222fa79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701483"
---
# <a name="enumerated-constants-in-property-expressions"></a><span data-ttu-id="aef64-102">Constantes énumérées dans des expressions de propriété</span><span class="sxs-lookup"><span data-stu-id="aef64-102">Enumerated Constants in Property Expressions</span></span>
  <span data-ttu-id="aef64-103">Si des expressions de propriété incluent des valeurs d'une liste de membres d'énumérateur, l'expression doit utiliser la valeur numérique du membre énumérateur et non le nom convivial du membre.</span><span class="sxs-lookup"><span data-stu-id="aef64-103">If property expressions include values from an enumerator member list, the expression must use the numeric value of the enumerator member instead of the friendly name of the member.</span></span> <span data-ttu-id="aef64-104">Par exemple, si une expression définit la propriété `LoggingMode`, vous devez utiliser la valeur numérique 2 à la place du nom convivial Désactivé.</span><span class="sxs-lookup"><span data-stu-id="aef64-104">For example, if an expression sets the `LoggingMode` property then you must use the numeric value 2 instead of the friendly name Disabled.</span></span>  
  
 <span data-ttu-id="aef64-105">Cette rubrique répertorie uniquement les valeurs numériques équivalant aux noms conviviaux d'énumérateurs dont les membres sont fréquemment utilisés dans des expressions de propriété.</span><span class="sxs-lookup"><span data-stu-id="aef64-105">This topic lists only the numeric values equivalent to friendly names of enumerators whose members are commonly used in property expressions.</span></span> <span data-ttu-id="aef64-106">Le modèle objet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] inclut de nombreux énumérateurs supplémentaires que vous utilisez quand vous programmez le modèle objet pour générer des packages par programmation ou des éléments de package de code personnalisé, tels que des tâches et des composants de flux de données.</span><span class="sxs-lookup"><span data-stu-id="aef64-106">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model includes many additional enumerators that you use when you program the object model to build packages programmatically or code custom package elements such as tasks and data flow components.</span></span>  
  
 <span data-ttu-id="aef64-107">En complément des propriétés personnalisées pour les packages et les objets package, la fenêtre Propriétés de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] inclut un jeu de propriétés accessibles aux packages, aux tâches, ainsi qu'aux conteneurs de boucles Foreach, de boucles For et de séquences.</span><span class="sxs-lookup"><span data-stu-id="aef64-107">In addition to the custom properties for packages and package objects, the Properties window in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] includes a set of properties that are available to packages, tasks, and the Foreach Loop, For Loop, and Sequence containers.</span></span> <span data-ttu-id="aef64-108">Les propriétés communes qui sont définies par des valeurs provenant d’énumérateurs- `ForceExecutionResult` , `LoggingMode` , `IsolationLevel` et `Transaction Option` -sont répertoriées dans la section Propriétés communes.</span><span class="sxs-lookup"><span data-stu-id="aef64-108">The common properties that are set by values from enumerators-`ForceExecutionResult`, `LoggingMode`, `IsolationLevel`, and `Transaction Option`-are listed in Common Properties section.</span></span>  
  
 <span data-ttu-id="aef64-109">Les sections suivantes fournissent des informations sur les constantes énumérées :</span><span class="sxs-lookup"><span data-stu-id="aef64-109">The following sections provide information about enumerated constants:</span></span>  
  
 [<span data-ttu-id="aef64-110">Package</span><span class="sxs-lookup"><span data-stu-id="aef64-110">Package</span></span>](#Package)  
  
 [<span data-ttu-id="aef64-111">Énumérateurs de boucles Foreach</span><span class="sxs-lookup"><span data-stu-id="aef64-111">Foreach Loop Enumerators</span></span>](#Foreach)  
  
 [<span data-ttu-id="aef64-112">Tâches :</span><span class="sxs-lookup"><span data-stu-id="aef64-112">Tasks</span></span>](#Tasks)  
  
 [<span data-ttu-id="aef64-113">Tâches du plan de maintenance</span><span class="sxs-lookup"><span data-stu-id="aef64-113">Maintenance Plan Tasks</span></span>](#MaintenancePlanTasks)  
  
 [<span data-ttu-id="aef64-114">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="aef64-114">Common Properties</span></span>](#CommonProperties)  
  
##  <a name="package"></a><a name="Package"></a> <span data-ttu-id="aef64-115">Package</span><span class="sxs-lookup"><span data-stu-id="aef64-115">Package</span></span>  
 <span data-ttu-id="aef64-116">Les tableaux suivants répertorient les noms conviviaux et les équivalents en valeur numérique pour des propriétés de packages que vous définissez à l'aide de valeurs provenant d'un énumérateur.</span><span class="sxs-lookup"><span data-stu-id="aef64-116">The following tables lists the friendly names and the numeric value equivalents for properties of packages that you set by using values from an enumerator.</span></span>  
  
 <span data-ttu-id="aef64-117">`PackageType`Définie par la propriété à l’aide des valeurs de l' `DTSPackageType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-117">`PackageType` property-Set by using values from the `DTSPackageType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-118">Nom convivial dans DTSPackageType</span><span class="sxs-lookup"><span data-stu-id="aef64-118">Friendly name in DTSPackageType</span></span>|<span data-ttu-id="aef64-119">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-119">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="aef64-120">Default</span><span class="sxs-lookup"><span data-stu-id="aef64-120">Default</span></span>|<span data-ttu-id="aef64-121">0</span><span class="sxs-lookup"><span data-stu-id="aef64-121">0</span></span>|  
|<span data-ttu-id="aef64-122">DTSWizard</span><span class="sxs-lookup"><span data-stu-id="aef64-122">DTSWizard</span></span>|<span data-ttu-id="aef64-123">1</span><span class="sxs-lookup"><span data-stu-id="aef64-123">1</span></span>|  
|<span data-ttu-id="aef64-124">DTSDesigner</span><span class="sxs-lookup"><span data-stu-id="aef64-124">DTSDesigner</span></span>|<span data-ttu-id="aef64-125">2</span><span class="sxs-lookup"><span data-stu-id="aef64-125">2</span></span>|  
|<span data-ttu-id="aef64-126">SQLReplication</span><span class="sxs-lookup"><span data-stu-id="aef64-126">SQLReplication</span></span>|<span data-ttu-id="aef64-127">3</span><span class="sxs-lookup"><span data-stu-id="aef64-127">3</span></span>|  
|<span data-ttu-id="aef64-128">DTSDesigner100</span><span class="sxs-lookup"><span data-stu-id="aef64-128">DTSDesigner100</span></span>|<span data-ttu-id="aef64-129">5</span><span class="sxs-lookup"><span data-stu-id="aef64-129">5</span></span>|  
|<span data-ttu-id="aef64-130">SQLDBMaint</span><span class="sxs-lookup"><span data-stu-id="aef64-130">SQLDBMaint</span></span>|<span data-ttu-id="aef64-131">6</span><span class="sxs-lookup"><span data-stu-id="aef64-131">6</span></span>|  
  
 <span data-ttu-id="aef64-132">`CheckpointUsage`Définie par la propriété à l’aide des valeurs de l' `DTSCheckpointUsage` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-132">`CheckpointUsage` property-Set by using values from the `DTSCheckpointUsage` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-133">Nom convivial dans DTSCheckpointUsage</span><span class="sxs-lookup"><span data-stu-id="aef64-133">Friendly name in DTSCheckpointUsage</span></span>|<span data-ttu-id="aef64-134">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-134">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="aef64-135">Jamais</span><span class="sxs-lookup"><span data-stu-id="aef64-135">Never</span></span>|<span data-ttu-id="aef64-136">0</span><span class="sxs-lookup"><span data-stu-id="aef64-136">0</span></span>|  
|<span data-ttu-id="aef64-137">IfExists</span><span class="sxs-lookup"><span data-stu-id="aef64-137">IfExists</span></span>|<span data-ttu-id="aef64-138">1</span><span class="sxs-lookup"><span data-stu-id="aef64-138">1</span></span>|  
|<span data-ttu-id="aef64-139">Toujours</span><span class="sxs-lookup"><span data-stu-id="aef64-139">Always</span></span>|<span data-ttu-id="aef64-140">2</span><span class="sxs-lookup"><span data-stu-id="aef64-140">2</span></span>|  
  
 <span data-ttu-id="aef64-141">`PackagePriorityClass`Définie par la propriété à l’aide des valeurs de l' `DTSPriorityClass` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-141">`PackagePriorityClass` property-Set by using values from the `DTSPriorityClass` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-142">Nom convivial dans DTSPriorityClass</span><span class="sxs-lookup"><span data-stu-id="aef64-142">Friendly name in DTSPriorityClass</span></span>|<span data-ttu-id="aef64-143">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-143">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="aef64-144">Default</span><span class="sxs-lookup"><span data-stu-id="aef64-144">Default</span></span>|<span data-ttu-id="aef64-145">0</span><span class="sxs-lookup"><span data-stu-id="aef64-145">0</span></span>|  
|<span data-ttu-id="aef64-146">AboveNormal</span><span class="sxs-lookup"><span data-stu-id="aef64-146">AboveNormal</span></span>|<span data-ttu-id="aef64-147">1</span><span class="sxs-lookup"><span data-stu-id="aef64-147">1</span></span>|  
|<span data-ttu-id="aef64-148">Normal</span><span class="sxs-lookup"><span data-stu-id="aef64-148">Normal</span></span>|<span data-ttu-id="aef64-149">2</span><span class="sxs-lookup"><span data-stu-id="aef64-149">2</span></span>|  
|<span data-ttu-id="aef64-150">BelowNormal</span><span class="sxs-lookup"><span data-stu-id="aef64-150">BelowNormal</span></span>|<span data-ttu-id="aef64-151">3</span><span class="sxs-lookup"><span data-stu-id="aef64-151">3</span></span>|  
|<span data-ttu-id="aef64-152">Idle</span><span class="sxs-lookup"><span data-stu-id="aef64-152">Idle</span></span>|<span data-ttu-id="aef64-153">4</span><span class="sxs-lookup"><span data-stu-id="aef64-153">4</span></span>|  
  
 <span data-ttu-id="aef64-154">`ProtectionLevel`Définie par la propriété à l’aide des valeurs de l' `DTSProtectionLevel` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-154">`ProtectionLevel` property-Set by using values from the `DTSProtectionLevel` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-155">Nom convivial dans DTSProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="aef64-155">Friendly name in DTSProtectionLevel</span></span>|<span data-ttu-id="aef64-156">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-156">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="aef64-157">DontSaveSensitive</span><span class="sxs-lookup"><span data-stu-id="aef64-157">DontSaveSensitive</span></span>|<span data-ttu-id="aef64-158">0</span><span class="sxs-lookup"><span data-stu-id="aef64-158">0</span></span>|  
|<span data-ttu-id="aef64-159">EncryptSensitiveWithUserKey</span><span class="sxs-lookup"><span data-stu-id="aef64-159">EncryptSensitiveWithUserKey</span></span>|<span data-ttu-id="aef64-160">1</span><span class="sxs-lookup"><span data-stu-id="aef64-160">1</span></span>|  
|<span data-ttu-id="aef64-161">EncryptSensitiveWithPassword</span><span class="sxs-lookup"><span data-stu-id="aef64-161">EncryptSensitiveWithPassword</span></span>|<span data-ttu-id="aef64-162">2</span><span class="sxs-lookup"><span data-stu-id="aef64-162">2</span></span>|  
|<span data-ttu-id="aef64-163">EncryptAllWithPassword</span><span class="sxs-lookup"><span data-stu-id="aef64-163">EncryptAllWithPassword</span></span>|<span data-ttu-id="aef64-164">3</span><span class="sxs-lookup"><span data-stu-id="aef64-164">3</span></span>|  
|<span data-ttu-id="aef64-165">EncryptAllWithUserKey</span><span class="sxs-lookup"><span data-stu-id="aef64-165">EncryptAllWithUserKey</span></span>|<span data-ttu-id="aef64-166">4</span><span class="sxs-lookup"><span data-stu-id="aef64-166">4</span></span>|  
|<span data-ttu-id="aef64-167">ServerStorage</span><span class="sxs-lookup"><span data-stu-id="aef64-167">ServerStorage</span></span>|<span data-ttu-id="aef64-168">5</span><span class="sxs-lookup"><span data-stu-id="aef64-168">5</span></span>|  
  
##  <a name="precedence-constraints"></a><a name="PrecedenceConstraints"></a> <span data-ttu-id="aef64-169">Contraintes de précédence</span><span class="sxs-lookup"><span data-stu-id="aef64-169">Precedence Constraints</span></span>  
 <span data-ttu-id="aef64-170">`EvalOp`Définie par la propriété à l’aide des valeurs de l' `DTSPrecedenceEvalOp` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-170">`EvalOp` property-Set by using values from the `DTSPrecedenceEvalOp` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-171">Nom convivial dans DTSPrecedenceEvalOp</span><span class="sxs-lookup"><span data-stu-id="aef64-171">Friendly name in DTSPrecedenceEvalOp</span></span>|<span data-ttu-id="aef64-172">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-172">Numeric value</span></span>|  
|------------------------------------------|-------------------|  
|<span data-ttu-id="aef64-173">Expression</span><span class="sxs-lookup"><span data-stu-id="aef64-173">Expression</span></span>|<span data-ttu-id="aef64-174">1</span><span class="sxs-lookup"><span data-stu-id="aef64-174">1</span></span>|  
|<span data-ttu-id="aef64-175">Contrainte</span><span class="sxs-lookup"><span data-stu-id="aef64-175">Constraint</span></span>|<span data-ttu-id="aef64-176">2</span><span class="sxs-lookup"><span data-stu-id="aef64-176">2</span></span>|  
|<span data-ttu-id="aef64-177">ExpressionAndConstraint</span><span class="sxs-lookup"><span data-stu-id="aef64-177">ExpressionAndConstraint</span></span>|<span data-ttu-id="aef64-178">3</span><span class="sxs-lookup"><span data-stu-id="aef64-178">3</span></span>|  
|<span data-ttu-id="aef64-179">ExpressionOrConstraint</span><span class="sxs-lookup"><span data-stu-id="aef64-179">ExpressionOrConstraint</span></span>|<span data-ttu-id="aef64-180">4</span><span class="sxs-lookup"><span data-stu-id="aef64-180">4</span></span>|  
  
 <span data-ttu-id="aef64-181">`Value`Définie par la propriété à l’aide des valeurs de l' `DTSExecResult` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-181">`Value` property-Set by using values from the `DTSExecResult` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-182">Nom convivial</span><span class="sxs-lookup"><span data-stu-id="aef64-182">Friendly Name</span></span>|<span data-ttu-id="aef64-183">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-183">Numeric Value</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="aef64-184">Succès</span><span class="sxs-lookup"><span data-stu-id="aef64-184">Success</span></span>|<span data-ttu-id="aef64-185">0</span><span class="sxs-lookup"><span data-stu-id="aef64-185">0</span></span>|  
|<span data-ttu-id="aef64-186">Échec</span><span class="sxs-lookup"><span data-stu-id="aef64-186">Failure</span></span>|<span data-ttu-id="aef64-187">1</span><span class="sxs-lookup"><span data-stu-id="aef64-187">1</span></span>|  
|<span data-ttu-id="aef64-188">Completion</span><span class="sxs-lookup"><span data-stu-id="aef64-188">Completion</span></span>|<span data-ttu-id="aef64-189">2</span><span class="sxs-lookup"><span data-stu-id="aef64-189">2</span></span>|  
|<span data-ttu-id="aef64-190">Opération annulée</span><span class="sxs-lookup"><span data-stu-id="aef64-190">Canceled</span></span>|<span data-ttu-id="aef64-191">3</span><span class="sxs-lookup"><span data-stu-id="aef64-191">3</span></span>|  
  
##  <a name="foreach-loop-enumerators"></a><a name="Foreach"></a> <span data-ttu-id="aef64-192">Énumérateurs de boucles Foreach</span><span class="sxs-lookup"><span data-stu-id="aef64-192">Foreach Loop Enumerators</span></span>  
 <span data-ttu-id="aef64-193">La boucle Foreach inclut un jeu d'énumérateurs comportant des propriétés pouvant être définies par des expressions de la propriété.</span><span class="sxs-lookup"><span data-stu-id="aef64-193">The Foreach Loop includes a set of enumerators with properties that can be set by property expressions.</span></span>  
  
### <a name="foreach-ado-enumerator"></a><span data-ttu-id="aef64-194">Énumérateur Foreach ADO</span><span class="sxs-lookup"><span data-stu-id="aef64-194">Foreach ADO Enumerator</span></span>  
 <span data-ttu-id="aef64-195">`Type`Définie par la propriété à l’aide des valeurs de l' `ADOEnumerationType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-195">`Type` property-Set by using values from the `ADOEnumerationType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-196">Nom convivial dans ADOEnumerationType</span><span class="sxs-lookup"><span data-stu-id="aef64-196">Friendly name in ADOEnumerationType</span></span>|<span data-ttu-id="aef64-197">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-197">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="aef64-198">EnumerateTables</span><span class="sxs-lookup"><span data-stu-id="aef64-198">EnumerateTables</span></span>|<span data-ttu-id="aef64-199">0</span><span class="sxs-lookup"><span data-stu-id="aef64-199">0</span></span>|  
|<span data-ttu-id="aef64-200">EnumerateAllRows</span><span class="sxs-lookup"><span data-stu-id="aef64-200">EnumerateAllRows</span></span>|<span data-ttu-id="aef64-201">1</span><span class="sxs-lookup"><span data-stu-id="aef64-201">1</span></span>|  
|<span data-ttu-id="aef64-202">EnumerateRowsInFirstTable</span><span class="sxs-lookup"><span data-stu-id="aef64-202">EnumerateRowsInFirstTable</span></span>|<span data-ttu-id="aef64-203">2</span><span class="sxs-lookup"><span data-stu-id="aef64-203">2</span></span>|  
  
### <a name="foreach-nodelist-enumerator"></a><span data-ttu-id="aef64-204">Énumérateur Foreach Nodelist</span><span class="sxs-lookup"><span data-stu-id="aef64-204">Foreach Nodelist Enumerator</span></span>  
 <span data-ttu-id="aef64-205">`SourceDocumentType``InnerXPathStringSourceType`Propriétés, et **OuterXPathStringSourceType** -définies à l’aide des valeurs de l' `SourceType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-205">`SourceDocumentType`, `InnerXPathStringSourceType`, and **OuterXPathStringSourceType** properties-Set by using values from the `SourceType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-206">Nom convivial dans SourceType</span><span class="sxs-lookup"><span data-stu-id="aef64-206">Friendly name in SourceType</span></span>|<span data-ttu-id="aef64-207">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-207">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="aef64-208">FileConnection</span><span class="sxs-lookup"><span data-stu-id="aef64-208">FileConnection</span></span>|<span data-ttu-id="aef64-209">0</span><span class="sxs-lookup"><span data-stu-id="aef64-209">0</span></span>|  
|<span data-ttu-id="aef64-210">Variable</span><span class="sxs-lookup"><span data-stu-id="aef64-210">Variable</span></span>|<span data-ttu-id="aef64-211">1</span><span class="sxs-lookup"><span data-stu-id="aef64-211">1</span></span>|  
|<span data-ttu-id="aef64-212">DirectInput</span><span class="sxs-lookup"><span data-stu-id="aef64-212">DirectInput</span></span>|<span data-ttu-id="aef64-213">2</span><span class="sxs-lookup"><span data-stu-id="aef64-213">2</span></span>|  
  
 <span data-ttu-id="aef64-214">`EnumerationType`Définie par la propriété à l’aide des valeurs de l' `EnumerationType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-214">`EnumerationType` property-Set by using values from the `EnumerationType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-215">Nom convivial dans EnumerationType</span><span class="sxs-lookup"><span data-stu-id="aef64-215">Friendly name in EnumerationType</span></span>|<span data-ttu-id="aef64-216">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-216">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="aef64-217">Navigateur</span><span class="sxs-lookup"><span data-stu-id="aef64-217">Navigator</span></span>|<span data-ttu-id="aef64-218">0</span><span class="sxs-lookup"><span data-stu-id="aef64-218">0</span></span>|  
|<span data-ttu-id="aef64-219">Nœud</span><span class="sxs-lookup"><span data-stu-id="aef64-219">Node</span></span>|<span data-ttu-id="aef64-220">1</span><span class="sxs-lookup"><span data-stu-id="aef64-220">1</span></span>|  
|<span data-ttu-id="aef64-221">NodeText</span><span class="sxs-lookup"><span data-stu-id="aef64-221">NodeText</span></span>|<span data-ttu-id="aef64-222">2</span><span class="sxs-lookup"><span data-stu-id="aef64-222">2</span></span>|  
|<span data-ttu-id="aef64-223">ElementCollection</span><span class="sxs-lookup"><span data-stu-id="aef64-223">ElementCollection</span></span>|<span data-ttu-id="aef64-224">3</span><span class="sxs-lookup"><span data-stu-id="aef64-224">3</span></span>|  
  
 <span data-ttu-id="aef64-225">`InnerElementType`Définie par la propriété à l’aide des valeurs de l' `InnerElementType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-225">`InnerElementType` property-Set by using values from the `InnerElementType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-226">Nom convivial dans InnerElementType</span><span class="sxs-lookup"><span data-stu-id="aef64-226">Friendly name in InnerElementType</span></span>|<span data-ttu-id="aef64-227">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-227">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="aef64-228">Navigateur</span><span class="sxs-lookup"><span data-stu-id="aef64-228">Navigator</span></span>|<span data-ttu-id="aef64-229">0</span><span class="sxs-lookup"><span data-stu-id="aef64-229">0</span></span>|  
|<span data-ttu-id="aef64-230">Nœud</span><span class="sxs-lookup"><span data-stu-id="aef64-230">Node</span></span>|<span data-ttu-id="aef64-231">1</span><span class="sxs-lookup"><span data-stu-id="aef64-231">1</span></span>|  
|<span data-ttu-id="aef64-232">NodeText</span><span class="sxs-lookup"><span data-stu-id="aef64-232">NodeText</span></span>|<span data-ttu-id="aef64-233">2</span><span class="sxs-lookup"><span data-stu-id="aef64-233">2</span></span>|  
  
##  <a name="tasks"></a><a name="Tasks"></a> <span data-ttu-id="aef64-234">Tâches</span><span class="sxs-lookup"><span data-stu-id="aef64-234">Tasks</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="aef64-235">inclut de nombreuses tâches avec des propriétés pouvant être définies par des expressions de la propriété.</span><span class="sxs-lookup"><span data-stu-id="aef64-235">includes numerous tasks with properties that can be set by property expressions.</span></span>  
  
### <a name="analysis-services-execute-ddl-task"></a><span data-ttu-id="aef64-236">Tâche DDL d'exécution de SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="aef64-236">Analysis Services Execute DDL Task</span></span>  
 <span data-ttu-id="aef64-237">`SourceType`Définie par la propriété à l’aide des valeurs de l' `DDLSourceType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-237">`SourceType` property-Set by using values from the `DDLSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-238">Nom convivial dans DDLSourceType</span><span class="sxs-lookup"><span data-stu-id="aef64-238">Friendly name in DDLSourceType</span></span>|<span data-ttu-id="aef64-239">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-239">Numeric value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="aef64-240">DirectInput</span><span class="sxs-lookup"><span data-stu-id="aef64-240">DirectInput</span></span>|<span data-ttu-id="aef64-241">0</span><span class="sxs-lookup"><span data-stu-id="aef64-241">0</span></span>|  
|<span data-ttu-id="aef64-242">FileConnection</span><span class="sxs-lookup"><span data-stu-id="aef64-242">FileConnection</span></span>|<span data-ttu-id="aef64-243">1</span><span class="sxs-lookup"><span data-stu-id="aef64-243">1</span></span>|  
|<span data-ttu-id="aef64-244">Variable</span><span class="sxs-lookup"><span data-stu-id="aef64-244">Variable</span></span>|<span data-ttu-id="aef64-245">2</span><span class="sxs-lookup"><span data-stu-id="aef64-245">2</span></span>|  
  
### <a name="bulk-insert-task"></a><span data-ttu-id="aef64-246">tâche d'insertion en bloc</span><span class="sxs-lookup"><span data-stu-id="aef64-246">Bulk Insert Task</span></span>  
 <span data-ttu-id="aef64-247">`DataFileType`Définie par la propriété à l’aide des valeurs de l' `DTSBulkInsert_DataFileType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-247">`DataFileType` property-Set by using values from the `DTSBulkInsert_DataFileType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-248">Nom convivial dans DTSBulkInsert_DataFileType</span><span class="sxs-lookup"><span data-stu-id="aef64-248">Friendly name in DTSBulkInsert_DataFileType</span></span>|<span data-ttu-id="aef64-249">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-249">Numeric value</span></span>|  
|--------------------------------------------------|-------------------|  
|<span data-ttu-id="aef64-250">DTSBulkInsert_DataFileType_Char</span><span class="sxs-lookup"><span data-stu-id="aef64-250">DTSBulkInsert_DataFileType_Char</span></span>|<span data-ttu-id="aef64-251">0</span><span class="sxs-lookup"><span data-stu-id="aef64-251">0</span></span>|  
|<span data-ttu-id="aef64-252">DTSBulkInsert_DataFileType_Native</span><span class="sxs-lookup"><span data-stu-id="aef64-252">DTSBulkInsert_DataFileType_Native</span></span>|<span data-ttu-id="aef64-253">1</span><span class="sxs-lookup"><span data-stu-id="aef64-253">1</span></span>|  
|<span data-ttu-id="aef64-254">DTSBulkInsert_DataFileType_WideChar</span><span class="sxs-lookup"><span data-stu-id="aef64-254">DTSBulkInsert_DataFileType_WideChar</span></span>|<span data-ttu-id="aef64-255">2</span><span class="sxs-lookup"><span data-stu-id="aef64-255">2</span></span>|  
|<span data-ttu-id="aef64-256">DTSBulkInsert_DataFileType_WideNative</span><span class="sxs-lookup"><span data-stu-id="aef64-256">DTSBulkInsert_DataFileType_WideNative</span></span>|<span data-ttu-id="aef64-257">3</span><span class="sxs-lookup"><span data-stu-id="aef64-257">3</span></span>|  
  
### <a name="execute-sql-task"></a><span data-ttu-id="aef64-258">Tâche d’exécution de requêtes SQL</span><span class="sxs-lookup"><span data-stu-id="aef64-258">Execute SQL Task</span></span>  
 <span data-ttu-id="aef64-259">`ResultSetType`Définie par la propriété à l’aide des valeurs de l' `ResultSetType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-259">`ResultSetType` property-Set by using values from the `ResultSetType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-260">Nom convivial dans ResultSetType</span><span class="sxs-lookup"><span data-stu-id="aef64-260">Friendly name in ResultSetType</span></span>|<span data-ttu-id="aef64-261">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-261">Numeric Value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="aef64-262">ResultSetType_None</span><span class="sxs-lookup"><span data-stu-id="aef64-262">ResultSetType_None</span></span>|<span data-ttu-id="aef64-263">1</span><span class="sxs-lookup"><span data-stu-id="aef64-263">1</span></span>|  
|<span data-ttu-id="aef64-264">ResultSetType_SingleRow</span><span class="sxs-lookup"><span data-stu-id="aef64-264">ResultSetType_SingleRow</span></span>|<span data-ttu-id="aef64-265">2</span><span class="sxs-lookup"><span data-stu-id="aef64-265">2</span></span>|  
|<span data-ttu-id="aef64-266">ResultSetType_Rowset</span><span class="sxs-lookup"><span data-stu-id="aef64-266">ResultSetType_Rowset</span></span>|<span data-ttu-id="aef64-267">3</span><span class="sxs-lookup"><span data-stu-id="aef64-267">3</span></span>|  
|<span data-ttu-id="aef64-268">ResultSetType_XML</span><span class="sxs-lookup"><span data-stu-id="aef64-268">ResultSetType_XML</span></span>|<span data-ttu-id="aef64-269">4</span><span class="sxs-lookup"><span data-stu-id="aef64-269">4</span></span>|  
  
 <span data-ttu-id="aef64-270">`SqlStatementSourceType`Définie par la propriété à l’aide des valeurs de l' `SqlStatementSourceType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-270">`SqlStatementSourceType` property-Set by using values from the `SqlStatementSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-271">Nom convivial dans SqlStatementSourceType</span><span class="sxs-lookup"><span data-stu-id="aef64-271">Friendly name in SqlStatementSourceType</span></span>|<span data-ttu-id="aef64-272">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-272">Numeric Value</span></span>|  
|---------------------------------------------|-------------------|  
|<span data-ttu-id="aef64-273">DirectInput</span><span class="sxs-lookup"><span data-stu-id="aef64-273">DirectInput</span></span>|<span data-ttu-id="aef64-274">1</span><span class="sxs-lookup"><span data-stu-id="aef64-274">1</span></span>|  
|<span data-ttu-id="aef64-275">FileConnection</span><span class="sxs-lookup"><span data-stu-id="aef64-275">FileConnection</span></span>|<span data-ttu-id="aef64-276">2</span><span class="sxs-lookup"><span data-stu-id="aef64-276">2</span></span>|  
|<span data-ttu-id="aef64-277">Variable</span><span class="sxs-lookup"><span data-stu-id="aef64-277">Variable</span></span>|<span data-ttu-id="aef64-278">3</span><span class="sxs-lookup"><span data-stu-id="aef64-278">3</span></span>|  
  
### <a name="file-system-task"></a><span data-ttu-id="aef64-279">Tâches du système de fichiers</span><span class="sxs-lookup"><span data-stu-id="aef64-279">File System Task</span></span>  
 <span data-ttu-id="aef64-280">`Operation`Définie par la propriété à l’aide des valeurs de l' `DTSFileSystemOperation` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-280">`Operation` property-Set by using values from the `DTSFileSystemOperation` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-281">Nom convivial dans DTSFileSystemOperation</span><span class="sxs-lookup"><span data-stu-id="aef64-281">Friendly name in DTSFileSystemOperation</span></span>|<span data-ttu-id="aef64-282">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-282">Numeric value</span></span>|  
|---------------------------------------------|-------------------|  
|<span data-ttu-id="aef64-283">CopyFile</span><span class="sxs-lookup"><span data-stu-id="aef64-283">CopyFile</span></span>|<span data-ttu-id="aef64-284">0</span><span class="sxs-lookup"><span data-stu-id="aef64-284">0</span></span>|  
|<span data-ttu-id="aef64-285">MoveFile</span><span class="sxs-lookup"><span data-stu-id="aef64-285">MoveFile</span></span>|<span data-ttu-id="aef64-286">1</span><span class="sxs-lookup"><span data-stu-id="aef64-286">1</span></span>|  
|<span data-ttu-id="aef64-287">DeleteFile</span><span class="sxs-lookup"><span data-stu-id="aef64-287">DeleteFile</span></span>|<span data-ttu-id="aef64-288">2</span><span class="sxs-lookup"><span data-stu-id="aef64-288">2</span></span>|  
|<span data-ttu-id="aef64-289">RenameFile</span><span class="sxs-lookup"><span data-stu-id="aef64-289">RenameFile</span></span>|<span data-ttu-id="aef64-290">3</span><span class="sxs-lookup"><span data-stu-id="aef64-290">3</span></span>|  
|<span data-ttu-id="aef64-291">SetAttributes</span><span class="sxs-lookup"><span data-stu-id="aef64-291">SetAttributes</span></span>|<span data-ttu-id="aef64-292">4</span><span class="sxs-lookup"><span data-stu-id="aef64-292">4</span></span>|  
|<span data-ttu-id="aef64-293">CreateDirectory</span><span class="sxs-lookup"><span data-stu-id="aef64-293">CreateDirectory</span></span>|<span data-ttu-id="aef64-294">5</span><span class="sxs-lookup"><span data-stu-id="aef64-294">5</span></span>|  
|<span data-ttu-id="aef64-295">CopyDirectory</span><span class="sxs-lookup"><span data-stu-id="aef64-295">CopyDirectory</span></span>|<span data-ttu-id="aef64-296">6</span><span class="sxs-lookup"><span data-stu-id="aef64-296">6</span></span>|  
|<span data-ttu-id="aef64-297">MoveDirectory</span><span class="sxs-lookup"><span data-stu-id="aef64-297">MoveDirectory</span></span>|<span data-ttu-id="aef64-298">7</span><span class="sxs-lookup"><span data-stu-id="aef64-298">7</span></span>|  
|<span data-ttu-id="aef64-299">DeleteDirectory</span><span class="sxs-lookup"><span data-stu-id="aef64-299">DeleteDirectory</span></span>|<span data-ttu-id="aef64-300">8</span><span class="sxs-lookup"><span data-stu-id="aef64-300">8</span></span>|  
|<span data-ttu-id="aef64-301">DeleteDirectoryContent</span><span class="sxs-lookup"><span data-stu-id="aef64-301">DeleteDirectoryContent</span></span>|<span data-ttu-id="aef64-302">9</span><span class="sxs-lookup"><span data-stu-id="aef64-302">9</span></span>|  
  
 <span data-ttu-id="aef64-303">`Attributes`Définie par la propriété à l’aide des valeurs de l' `DTSFileSystemAttributes` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-303">`Attributes` property-Set by using values from the `DTSFileSystemAttributes` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-304">Nom convivial dans DTSFileSystemAttributes</span><span class="sxs-lookup"><span data-stu-id="aef64-304">Friendly name in DTSFileSystemAttributes</span></span>|<span data-ttu-id="aef64-305">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-305">Numeric value</span></span>|  
|----------------------------------------------|-------------------|  
|<span data-ttu-id="aef64-306">Normal</span><span class="sxs-lookup"><span data-stu-id="aef64-306">Normal</span></span>|<span data-ttu-id="aef64-307">0</span><span class="sxs-lookup"><span data-stu-id="aef64-307">0</span></span>|  
|<span data-ttu-id="aef64-308">Archivage</span><span class="sxs-lookup"><span data-stu-id="aef64-308">Archive</span></span>|<span data-ttu-id="aef64-309">1</span><span class="sxs-lookup"><span data-stu-id="aef64-309">1</span></span>|  
|<span data-ttu-id="aef64-310">Hidden</span><span class="sxs-lookup"><span data-stu-id="aef64-310">Hidden</span></span>|<span data-ttu-id="aef64-311">2</span><span class="sxs-lookup"><span data-stu-id="aef64-311">2</span></span>|  
|<span data-ttu-id="aef64-312">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="aef64-312">ReadOnly</span></span>|<span data-ttu-id="aef64-313">4</span><span class="sxs-lookup"><span data-stu-id="aef64-313">4</span></span>|  
|<span data-ttu-id="aef64-314">Système</span><span class="sxs-lookup"><span data-stu-id="aef64-314">System</span></span>|<span data-ttu-id="aef64-315">8</span><span class="sxs-lookup"><span data-stu-id="aef64-315">8</span></span>|  
  
### <a name="ftp-task"></a><span data-ttu-id="aef64-316">Tâche FTP</span><span class="sxs-lookup"><span data-stu-id="aef64-316">FTP Task</span></span>  
 <span data-ttu-id="aef64-317">`Operation`Définie par la propriété à l’aide des valeurs de l' `DTSFTPOp` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-317">`Operation` property-Set by using values from the `DTSFTPOp` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-318">Nom convivial dans DTSFTPOp</span><span class="sxs-lookup"><span data-stu-id="aef64-318">Friendly name in DTSFTPOp</span></span>|<span data-ttu-id="aef64-319">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-319">Numeric value</span></span>|  
|-------------------------------|-------------------|  
|<span data-ttu-id="aef64-320">Envoyer</span><span class="sxs-lookup"><span data-stu-id="aef64-320">Send</span></span>|<span data-ttu-id="aef64-321">0</span><span class="sxs-lookup"><span data-stu-id="aef64-321">0</span></span>|  
|<span data-ttu-id="aef64-322">Recevoir</span><span class="sxs-lookup"><span data-stu-id="aef64-322">Receive</span></span>|<span data-ttu-id="aef64-323">1</span><span class="sxs-lookup"><span data-stu-id="aef64-323">1</span></span>|  
|<span data-ttu-id="aef64-324">DeleteLocal</span><span class="sxs-lookup"><span data-stu-id="aef64-324">DeleteLocal</span></span>|<span data-ttu-id="aef64-325">2</span><span class="sxs-lookup"><span data-stu-id="aef64-325">2</span></span>|  
|<span data-ttu-id="aef64-326">DeleteRemote</span><span class="sxs-lookup"><span data-stu-id="aef64-326">DeleteRemote</span></span>|<span data-ttu-id="aef64-327">3</span><span class="sxs-lookup"><span data-stu-id="aef64-327">3</span></span>|  
|<span data-ttu-id="aef64-328">MakeDirLocal</span><span class="sxs-lookup"><span data-stu-id="aef64-328">MakeDirLocal</span></span>|<span data-ttu-id="aef64-329">4</span><span class="sxs-lookup"><span data-stu-id="aef64-329">4</span></span>|  
|<span data-ttu-id="aef64-330">MakeDirRemote</span><span class="sxs-lookup"><span data-stu-id="aef64-330">MakeDirRemote</span></span>|<span data-ttu-id="aef64-331">5</span><span class="sxs-lookup"><span data-stu-id="aef64-331">5</span></span>|  
|<span data-ttu-id="aef64-332">RemoveDirLocal</span><span class="sxs-lookup"><span data-stu-id="aef64-332">RemoveDirLocal</span></span>|<span data-ttu-id="aef64-333">6</span><span class="sxs-lookup"><span data-stu-id="aef64-333">6</span></span>|  
|<span data-ttu-id="aef64-334">RemoveDirRemote</span><span class="sxs-lookup"><span data-stu-id="aef64-334">RemoveDirRemote</span></span>|<span data-ttu-id="aef64-335">7</span><span class="sxs-lookup"><span data-stu-id="aef64-335">7</span></span>|  
  
### <a name="message-queue-task"></a><span data-ttu-id="aef64-336">Message Queue Task</span><span class="sxs-lookup"><span data-stu-id="aef64-336">Message Queue Task</span></span>  
 <span data-ttu-id="aef64-337">`MessageType`Définie par la propriété à l’aide des valeurs de l' `MQMessageType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-337">`MessageType` property-Set by using values from the `MQMessageType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-338">Nom convivial dans MQMessageType</span><span class="sxs-lookup"><span data-stu-id="aef64-338">Friendly name in MQMessageType</span></span>|<span data-ttu-id="aef64-339">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-339">Numeric value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="aef64-340">DTSMQMessageType_String</span><span class="sxs-lookup"><span data-stu-id="aef64-340">DTSMQMessageType_String</span></span>|<span data-ttu-id="aef64-341">0</span><span class="sxs-lookup"><span data-stu-id="aef64-341">0</span></span>|  
|<span data-ttu-id="aef64-342">DTSMQMessageType_DataFile</span><span class="sxs-lookup"><span data-stu-id="aef64-342">DTSMQMessageType_DataFile</span></span>|<span data-ttu-id="aef64-343">1</span><span class="sxs-lookup"><span data-stu-id="aef64-343">1</span></span>|  
|<span data-ttu-id="aef64-344">DTSMQMessageType_Variables</span><span class="sxs-lookup"><span data-stu-id="aef64-344">DTSMQMessageType_Variables</span></span>|<span data-ttu-id="aef64-345">2</span><span class="sxs-lookup"><span data-stu-id="aef64-345">2</span></span>|  
|<span data-ttu-id="aef64-346">DTSMQMessagType_StringMessageToVariable</span><span class="sxs-lookup"><span data-stu-id="aef64-346">DTSMQMessagType_StringMessageToVariable</span></span>|<span data-ttu-id="aef64-347">3</span><span class="sxs-lookup"><span data-stu-id="aef64-347">3</span></span>|  
  
 <span data-ttu-id="aef64-348">`StringCompareType`Définie par la propriété à l’aide des valeurs de l' `MQStringMessageCompare` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-348">`StringCompareType` property-Set by using values from the `MQStringMessageCompare` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-349">Nom convivial dans MQStringMessageCompare</span><span class="sxs-lookup"><span data-stu-id="aef64-349">Friendly name in MQStringMessageCompare</span></span>|<span data-ttu-id="aef64-350">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-350">Numeric value</span></span>|  
|---------------------------------------------|-------------------|  
|<span data-ttu-id="aef64-351">DTSMQStringMessageCompare_None</span><span class="sxs-lookup"><span data-stu-id="aef64-351">DTSMQStringMessageCompare_None</span></span>|<span data-ttu-id="aef64-352">0</span><span class="sxs-lookup"><span data-stu-id="aef64-352">0</span></span>|  
|<span data-ttu-id="aef64-353">DTSMQStringMessageCompare_Exact</span><span class="sxs-lookup"><span data-stu-id="aef64-353">DTSMQStringMessageCompare_Exact</span></span>|<span data-ttu-id="aef64-354">1</span><span class="sxs-lookup"><span data-stu-id="aef64-354">1</span></span>|  
|<span data-ttu-id="aef64-355">DTSMQStringMessageCompare_IgnoreCase</span><span class="sxs-lookup"><span data-stu-id="aef64-355">DTSMQStringMessageCompare_IgnoreCase</span></span>|<span data-ttu-id="aef64-356">2</span><span class="sxs-lookup"><span data-stu-id="aef64-356">2</span></span>|  
|<span data-ttu-id="aef64-357">DTSMQStringMessageCompare_Contains</span><span class="sxs-lookup"><span data-stu-id="aef64-357">DTSMQStringMessageCompare_Contains</span></span>|<span data-ttu-id="aef64-358">3</span><span class="sxs-lookup"><span data-stu-id="aef64-358">3</span></span>|  
  
 <span data-ttu-id="aef64-359">`TaskType`Définie par la propriété à l’aide des valeurs de l' `MQType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-359">`TaskType` property-Set by using values from the `MQType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-360">Nom convivial dans MQType</span><span class="sxs-lookup"><span data-stu-id="aef64-360">Friendly name in MQType</span></span>|<span data-ttu-id="aef64-361">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-361">Numeric value</span></span>|  
|-----------------------------|-------------------|  
|<span data-ttu-id="aef64-362">DTSMQType_Sender</span><span class="sxs-lookup"><span data-stu-id="aef64-362">DTSMQType_Sender</span></span>|<span data-ttu-id="aef64-363">0</span><span class="sxs-lookup"><span data-stu-id="aef64-363">0</span></span>|  
|<span data-ttu-id="aef64-364">DTSMQType_Receiver</span><span class="sxs-lookup"><span data-stu-id="aef64-364">DTSMQType_Receiver</span></span>|<span data-ttu-id="aef64-365">1</span><span class="sxs-lookup"><span data-stu-id="aef64-365">1</span></span>|  
  
### <a name="send-mail-task"></a><span data-ttu-id="aef64-366">tache Envoyer un message</span><span class="sxs-lookup"><span data-stu-id="aef64-366">Send Mail Task</span></span>  
 <span data-ttu-id="aef64-367">`MessageSourceType`Définie par la propriété à l’aide des valeurs de l' `SendMailMessageSourceType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-367">`MessageSourceType` property-Set by using values from the `SendMailMessageSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-368">Nom convivial dans SendMailMessageSourceType</span><span class="sxs-lookup"><span data-stu-id="aef64-368">Friendly Name in SendMailMessageSourceType</span></span>|<span data-ttu-id="aef64-369">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-369">Numeric Value</span></span>|  
|------------------------------------------------|-------------------|  
|<span data-ttu-id="aef64-370">DirectInput</span><span class="sxs-lookup"><span data-stu-id="aef64-370">DirectInput</span></span>|<span data-ttu-id="aef64-371">0</span><span class="sxs-lookup"><span data-stu-id="aef64-371">0</span></span>|  
|<span data-ttu-id="aef64-372">FileConnection</span><span class="sxs-lookup"><span data-stu-id="aef64-372">FileConnection</span></span>|<span data-ttu-id="aef64-373">1</span><span class="sxs-lookup"><span data-stu-id="aef64-373">1</span></span>|  
|<span data-ttu-id="aef64-374">Variable</span><span class="sxs-lookup"><span data-stu-id="aef64-374">Variable</span></span>|<span data-ttu-id="aef64-375">2</span><span class="sxs-lookup"><span data-stu-id="aef64-375">2</span></span>|  
  
 <span data-ttu-id="aef64-376">`Priority`Définie par la propriété à l’aide des valeurs de l' `MailPriority` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-376">`Priority` property-Set by using values from the `MailPriority` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-377">Nom convivial dans MailPriority</span><span class="sxs-lookup"><span data-stu-id="aef64-377">Friendly Name in MailPriority</span></span>|<span data-ttu-id="aef64-378">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-378">Numeric Value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="aef64-379">Élevé</span><span class="sxs-lookup"><span data-stu-id="aef64-379">High</span></span>|<span data-ttu-id="aef64-380">1</span><span class="sxs-lookup"><span data-stu-id="aef64-380">1</span></span>|  
|<span data-ttu-id="aef64-381">Normal</span><span class="sxs-lookup"><span data-stu-id="aef64-381">Normal</span></span>|<span data-ttu-id="aef64-382">3</span><span class="sxs-lookup"><span data-stu-id="aef64-382">3</span></span>|  
|<span data-ttu-id="aef64-383">Faible</span><span class="sxs-lookup"><span data-stu-id="aef64-383">Low</span></span>|<span data-ttu-id="aef64-384">5</span><span class="sxs-lookup"><span data-stu-id="aef64-384">5</span></span>|  
  
### <a name="transfer-database-task"></a><span data-ttu-id="aef64-385">Tâche de transfert de bases de données</span><span class="sxs-lookup"><span data-stu-id="aef64-385">Transfer Database Task</span></span>  
 <span data-ttu-id="aef64-386">`Action`Définie par la propriété à l’aide des valeurs de l' `TransferAction` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-386">`Action` property-Set by using values from the `TransferAction` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-387">Nom convivial dans TransferAction</span><span class="sxs-lookup"><span data-stu-id="aef64-387">Friendly name in TransferAction</span></span>|<span data-ttu-id="aef64-388">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-388">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="aef64-389">Copier</span><span class="sxs-lookup"><span data-stu-id="aef64-389">Copy</span></span>|<span data-ttu-id="aef64-390">0</span><span class="sxs-lookup"><span data-stu-id="aef64-390">0</span></span>|  
|<span data-ttu-id="aef64-391">Déplacer</span><span class="sxs-lookup"><span data-stu-id="aef64-391">Move</span></span>|<span data-ttu-id="aef64-392">1</span><span class="sxs-lookup"><span data-stu-id="aef64-392">1</span></span>|  
  
 <span data-ttu-id="aef64-393">`Method`Définie par la propriété à l’aide des valeurs de l' `TransferMethod` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-393">`Method` property-Set by using values from the `TransferMethod` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-394">Nom convivial dans TransferMethod</span><span class="sxs-lookup"><span data-stu-id="aef64-394">Friendly name in TransferMethod</span></span>|<span data-ttu-id="aef64-395">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-395">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="aef64-396">DatabaseOffline</span><span class="sxs-lookup"><span data-stu-id="aef64-396">DatabaseOffline</span></span>|<span data-ttu-id="aef64-397">0</span><span class="sxs-lookup"><span data-stu-id="aef64-397">0</span></span>|  
|<span data-ttu-id="aef64-398">DatabaseOnline</span><span class="sxs-lookup"><span data-stu-id="aef64-398">DatabaseOnline</span></span>|<span data-ttu-id="aef64-399">1</span><span class="sxs-lookup"><span data-stu-id="aef64-399">1</span></span>|  
  
### <a name="transfer-error-messages-task"></a><span data-ttu-id="aef64-400">Tâche de transfert de messages d'erreur</span><span class="sxs-lookup"><span data-stu-id="aef64-400">Transfer Error Messages Task</span></span>  
 <span data-ttu-id="aef64-401">`IfObjectExists`Définie par la propriété à l’aide des valeurs de l' `IfObjectExists` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-401">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-402">Nom convivial dans IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="aef64-402">Friendly Name in IfObjectExists</span></span>|<span data-ttu-id="aef64-403">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-403">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="aef64-404">FailTask</span><span class="sxs-lookup"><span data-stu-id="aef64-404">FailTask</span></span>|<span data-ttu-id="aef64-405">0</span><span class="sxs-lookup"><span data-stu-id="aef64-405">0</span></span>|  
|<span data-ttu-id="aef64-406">Remplacer</span><span class="sxs-lookup"><span data-stu-id="aef64-406">Overwrite</span></span>|<span data-ttu-id="aef64-407">1</span><span class="sxs-lookup"><span data-stu-id="aef64-407">1</span></span>|  
|<span data-ttu-id="aef64-408">Ignorer</span><span class="sxs-lookup"><span data-stu-id="aef64-408">Skip</span></span>|<span data-ttu-id="aef64-409">2</span><span class="sxs-lookup"><span data-stu-id="aef64-409">2</span></span>|  
  
### <a name="transfer-jobs-task"></a><span data-ttu-id="aef64-410">Tâche de transfert de travaux</span><span class="sxs-lookup"><span data-stu-id="aef64-410">Transfer Jobs Task</span></span>  
 <span data-ttu-id="aef64-411">`IfObjectExists`Définie par la propriété à l’aide des valeurs de l' `IfObjectExists` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-411">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-412">Nom convivial dans IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="aef64-412">Friendly Name in IfObjectExists</span></span>|<span data-ttu-id="aef64-413">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-413">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="aef64-414">FailTask</span><span class="sxs-lookup"><span data-stu-id="aef64-414">FailTask</span></span>|<span data-ttu-id="aef64-415">0</span><span class="sxs-lookup"><span data-stu-id="aef64-415">0</span></span>|  
|<span data-ttu-id="aef64-416">Remplacer</span><span class="sxs-lookup"><span data-stu-id="aef64-416">Overwrite</span></span>|<span data-ttu-id="aef64-417">1</span><span class="sxs-lookup"><span data-stu-id="aef64-417">1</span></span>|  
|<span data-ttu-id="aef64-418">Ignorer</span><span class="sxs-lookup"><span data-stu-id="aef64-418">Skip</span></span>|<span data-ttu-id="aef64-419">2</span><span class="sxs-lookup"><span data-stu-id="aef64-419">2</span></span>|  
  
### <a name="transfer-logins-task"></a><span data-ttu-id="aef64-420">Tâche de transfert de connexions</span><span class="sxs-lookup"><span data-stu-id="aef64-420">Transfer Logins Task</span></span>  
 <span data-ttu-id="aef64-421">`IfObjectExists`Définie par la propriété à l’aide des valeurs de l' `IfObjectExists` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-421">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-422">Nom convivial dans IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="aef64-422">Friendly name in IfObjectExists</span></span>|<span data-ttu-id="aef64-423">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-423">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="aef64-424">FailTask</span><span class="sxs-lookup"><span data-stu-id="aef64-424">FailTask</span></span>|<span data-ttu-id="aef64-425">0</span><span class="sxs-lookup"><span data-stu-id="aef64-425">0</span></span>|  
|<span data-ttu-id="aef64-426">Remplacer</span><span class="sxs-lookup"><span data-stu-id="aef64-426">Overwrite</span></span>|<span data-ttu-id="aef64-427">1</span><span class="sxs-lookup"><span data-stu-id="aef64-427">1</span></span>|  
|<span data-ttu-id="aef64-428">Ignorer</span><span class="sxs-lookup"><span data-stu-id="aef64-428">Skip</span></span>|<span data-ttu-id="aef64-429">2</span><span class="sxs-lookup"><span data-stu-id="aef64-429">2</span></span>|  
  
 <span data-ttu-id="aef64-430">`LoginsToTransfer`Définie par la propriété à l’aide des valeurs de l' `LoginsToTransfer` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-430">`LoginsToTransfer` property-Set by using values from the `LoginsToTransfer` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-431">Nom convivial dans LoginsToTransfer</span><span class="sxs-lookup"><span data-stu-id="aef64-431">Friendly name in LoginsToTransfer</span></span>|<span data-ttu-id="aef64-432">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-432">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="aef64-433">AllLogins</span><span class="sxs-lookup"><span data-stu-id="aef64-433">AllLogins</span></span>|<span data-ttu-id="aef64-434">0</span><span class="sxs-lookup"><span data-stu-id="aef64-434">0</span></span>|  
|<span data-ttu-id="aef64-435">SelectedLogins</span><span class="sxs-lookup"><span data-stu-id="aef64-435">SelectedLogins</span></span>|<span data-ttu-id="aef64-436">1</span><span class="sxs-lookup"><span data-stu-id="aef64-436">1</span></span>|  
|<span data-ttu-id="aef64-437">AllLoginsFromSelectedDatabases</span><span class="sxs-lookup"><span data-stu-id="aef64-437">AllLoginsFromSelectedDatabases</span></span>|<span data-ttu-id="aef64-438">2</span><span class="sxs-lookup"><span data-stu-id="aef64-438">2</span></span>|  
  
### <a name="transfer-master-stored-procedures-task"></a><span data-ttu-id="aef64-439">Tâche de transfert de procédures stockées de master</span><span class="sxs-lookup"><span data-stu-id="aef64-439">Transfer Master Stored Procedures Task</span></span>  
 <span data-ttu-id="aef64-440">`IfObjectExists`Définie par la propriété à l’aide des valeurs de l' `IfObjectExists` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-440">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-441">Nom convivial dans IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="aef64-441">Friendly name in IfObjectExists</span></span>|<span data-ttu-id="aef64-442">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-442">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="aef64-443">FailTask</span><span class="sxs-lookup"><span data-stu-id="aef64-443">FailTask</span></span>|<span data-ttu-id="aef64-444">0</span><span class="sxs-lookup"><span data-stu-id="aef64-444">0</span></span>|  
|<span data-ttu-id="aef64-445">Remplacer</span><span class="sxs-lookup"><span data-stu-id="aef64-445">Overwrite</span></span>|<span data-ttu-id="aef64-446">1</span><span class="sxs-lookup"><span data-stu-id="aef64-446">1</span></span>|  
|<span data-ttu-id="aef64-447">Ignorer</span><span class="sxs-lookup"><span data-stu-id="aef64-447">Skip</span></span>|<span data-ttu-id="aef64-448">2</span><span class="sxs-lookup"><span data-stu-id="aef64-448">2</span></span>|  
  
### <a name="transfer-sql-server-objects-task"></a><span data-ttu-id="aef64-449">Tâche de transfert d'objets SQL Server</span><span class="sxs-lookup"><span data-stu-id="aef64-449">Transfer SQL Server Objects Task</span></span>  
 <span data-ttu-id="aef64-450">`ExistingData`Définie par la propriété à l’aide des valeurs de l' `ExistingData` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-450">`ExistingData` property-Set by using values from the `ExistingData` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-451">Nom convivial dans ExistingData</span><span class="sxs-lookup"><span data-stu-id="aef64-451">Friendly name in ExistingData</span></span>|<span data-ttu-id="aef64-452">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-452">Numeric Value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="aef64-453">Replace</span><span class="sxs-lookup"><span data-stu-id="aef64-453">Replace</span></span>|<span data-ttu-id="aef64-454">0</span><span class="sxs-lookup"><span data-stu-id="aef64-454">0</span></span>|  
|<span data-ttu-id="aef64-455">Ajouter</span><span class="sxs-lookup"><span data-stu-id="aef64-455">Append</span></span>|<span data-ttu-id="aef64-456">1</span><span class="sxs-lookup"><span data-stu-id="aef64-456">1</span></span>|  
  
### <a name="web-service-task"></a><span data-ttu-id="aef64-457">Tâche de service Web</span><span class="sxs-lookup"><span data-stu-id="aef64-457">Web Service Task</span></span>  
 <span data-ttu-id="aef64-458">`OutputType`Définie par la propriété à l’aide des valeurs de l' `DTSOutputType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-458">`OutputType` property-Set by using values from the `DTSOutputType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-459">Nom convivial dans DTSOutputType</span><span class="sxs-lookup"><span data-stu-id="aef64-459">Friendly name in DTSOutputType</span></span>|<span data-ttu-id="aef64-460">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-460">Numeric value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="aef64-461">Fichier</span><span class="sxs-lookup"><span data-stu-id="aef64-461">File</span></span>|<span data-ttu-id="aef64-462">0</span><span class="sxs-lookup"><span data-stu-id="aef64-462">0</span></span>|  
|<span data-ttu-id="aef64-463">Variable</span><span class="sxs-lookup"><span data-stu-id="aef64-463">Variable</span></span>|<span data-ttu-id="aef64-464">1</span><span class="sxs-lookup"><span data-stu-id="aef64-464">1</span></span>|  
  
### <a name="wmi-data-reader-task"></a><span data-ttu-id="aef64-465">Tâche Lecteur de données WMI</span><span class="sxs-lookup"><span data-stu-id="aef64-465">WMI Data Reader Task</span></span>  
 <span data-ttu-id="aef64-466">`OverwriteDestination`Définie par la propriété à l’aide des valeurs de l' `OverwriteDestination` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-466">`OverwriteDestination` property-Set by using values from the `OverwriteDestination` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-467">Nom convivial dans OverwriteDestination</span><span class="sxs-lookup"><span data-stu-id="aef64-467">Friendly name in OverwriteDestination</span></span>|<span data-ttu-id="aef64-468">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-468">Numeric value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="aef64-469">OverwriteDestination</span><span class="sxs-lookup"><span data-stu-id="aef64-469">OverwriteDestination</span></span>|<span data-ttu-id="aef64-470">0</span><span class="sxs-lookup"><span data-stu-id="aef64-470">0</span></span>|  
|<span data-ttu-id="aef64-471">AppendToDestination</span><span class="sxs-lookup"><span data-stu-id="aef64-471">AppendToDestination</span></span>|<span data-ttu-id="aef64-472">1</span><span class="sxs-lookup"><span data-stu-id="aef64-472">1</span></span>|  
|<span data-ttu-id="aef64-473">KeepOriginal</span><span class="sxs-lookup"><span data-stu-id="aef64-473">KeepOriginal</span></span>|<span data-ttu-id="aef64-474">2</span><span class="sxs-lookup"><span data-stu-id="aef64-474">2</span></span>|  
  
 <span data-ttu-id="aef64-475">`OutputType`Définie par la propriété à l’aide des valeurs de l' `OutputType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-475">`OutputType` property-Set by using values from the `OutputType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-476">Nom convivial dans OutputType</span><span class="sxs-lookup"><span data-stu-id="aef64-476">Friendly name in OutputType</span></span>|<span data-ttu-id="aef64-477">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-477">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="aef64-478">DataTable</span><span class="sxs-lookup"><span data-stu-id="aef64-478">DataTable</span></span>|<span data-ttu-id="aef64-479">0</span><span class="sxs-lookup"><span data-stu-id="aef64-479">0</span></span>|  
|<span data-ttu-id="aef64-480">PropertyValue</span><span class="sxs-lookup"><span data-stu-id="aef64-480">PropertyValue</span></span>|<span data-ttu-id="aef64-481">1</span><span class="sxs-lookup"><span data-stu-id="aef64-481">1</span></span>|  
|<span data-ttu-id="aef64-482">PropertyNameAndValue</span><span class="sxs-lookup"><span data-stu-id="aef64-482">PropertyNameAndValue</span></span>|<span data-ttu-id="aef64-483">2</span><span class="sxs-lookup"><span data-stu-id="aef64-483">2</span></span>|  
  
 <span data-ttu-id="aef64-484">`DestinationType`Définie par la propriété à l’aide des valeurs de l' `DestinationType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-484">`DestinationType` property-Set by using values from the `DestinationType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-485">Nom convivial dans DestinationType</span><span class="sxs-lookup"><span data-stu-id="aef64-485">Friendly name in DestinationType</span></span>|<span data-ttu-id="aef64-486">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-486">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="aef64-487">FileConnection</span><span class="sxs-lookup"><span data-stu-id="aef64-487">FileConnection</span></span>|<span data-ttu-id="aef64-488">0</span><span class="sxs-lookup"><span data-stu-id="aef64-488">0</span></span>|  
|<span data-ttu-id="aef64-489">Variable</span><span class="sxs-lookup"><span data-stu-id="aef64-489">Variable</span></span>|<span data-ttu-id="aef64-490">1</span><span class="sxs-lookup"><span data-stu-id="aef64-490">1</span></span>|  
  
 <span data-ttu-id="aef64-491">`WqlQuerySourceType`Définie par la propriété à l’aide des valeurs de l' `QuerySourceType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-491">`WqlQuerySourceType` property-Set by using values from the `QuerySourceType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-492">Nom convivial dans QuerySourceType</span><span class="sxs-lookup"><span data-stu-id="aef64-492">Friendly Name in QuerySourceType</span></span>|<span data-ttu-id="aef64-493">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-493">Numeric Value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="aef64-494">FileConnection</span><span class="sxs-lookup"><span data-stu-id="aef64-494">FileConnection</span></span>|<span data-ttu-id="aef64-495">0</span><span class="sxs-lookup"><span data-stu-id="aef64-495">0</span></span>|  
|<span data-ttu-id="aef64-496">DirectInput</span><span class="sxs-lookup"><span data-stu-id="aef64-496">DirectInput</span></span>|<span data-ttu-id="aef64-497">1</span><span class="sxs-lookup"><span data-stu-id="aef64-497">1</span></span>|  
|<span data-ttu-id="aef64-498">Variable</span><span class="sxs-lookup"><span data-stu-id="aef64-498">Variable</span></span>|<span data-ttu-id="aef64-499">2</span><span class="sxs-lookup"><span data-stu-id="aef64-499">2</span></span>|  
  
 <span data-ttu-id="aef64-500">Propriété observateur d’événement WMI `ActionAtEvent` -défini à l’aide des valeurs de l' `ActionAtEvent` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-500">WMI Event Watcher `ActionAtEvent` property-Set by using values from the `ActionAtEvent` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-501">Nom convivial dans ActionAtEvent</span><span class="sxs-lookup"><span data-stu-id="aef64-501">Friendly Name in ActionAtEvent</span></span>|<span data-ttu-id="aef64-502">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-502">Numeric Value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="aef64-503">LogTheEventAndFireDTSEvent</span><span class="sxs-lookup"><span data-stu-id="aef64-503">LogTheEventAndFireDTSEvent</span></span>|<span data-ttu-id="aef64-504">0</span><span class="sxs-lookup"><span data-stu-id="aef64-504">0</span></span>|  
|<span data-ttu-id="aef64-505">LogTheEvent</span><span class="sxs-lookup"><span data-stu-id="aef64-505">LogTheEvent</span></span>|<span data-ttu-id="aef64-506">1</span><span class="sxs-lookup"><span data-stu-id="aef64-506">1</span></span>|  
  
 <span data-ttu-id="aef64-507">`ActionAtTimeout`Définie par la propriété à l’aide des valeurs de l' `ActionAtTimeout` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-507">`ActionAtTimeout` property-Set by using values from the `ActionAtTimeout` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-508">Nom convivial dans ActionAtTimeout</span><span class="sxs-lookup"><span data-stu-id="aef64-508">Friendly name in ActionAtTimeout</span></span>|<span data-ttu-id="aef64-509">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-509">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="aef64-510">LogTimeoutAndFireDTSEvent</span><span class="sxs-lookup"><span data-stu-id="aef64-510">LogTimeoutAndFireDTSEvent</span></span>|<span data-ttu-id="aef64-511">0</span><span class="sxs-lookup"><span data-stu-id="aef64-511">0</span></span>|  
|<span data-ttu-id="aef64-512">LogTimeout</span><span class="sxs-lookup"><span data-stu-id="aef64-512">LogTimeout</span></span>|<span data-ttu-id="aef64-513">1</span><span class="sxs-lookup"><span data-stu-id="aef64-513">1</span></span>|  
  
 <span data-ttu-id="aef64-514">`AfterEvent`Définie par la propriété à l’aide des valeurs de l' `AfterEvent` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-514">`AfterEvent` property-Set by using values from the `AfterEvent` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-515">Nom convivial dans AfterEvent</span><span class="sxs-lookup"><span data-stu-id="aef64-515">Friendly name in AfterEvent</span></span>|<span data-ttu-id="aef64-516">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-516">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="aef64-517">ReturnWithSuccess</span><span class="sxs-lookup"><span data-stu-id="aef64-517">ReturnWithSuccess</span></span>|<span data-ttu-id="aef64-518">0</span><span class="sxs-lookup"><span data-stu-id="aef64-518">0</span></span>|  
|<span data-ttu-id="aef64-519">ReturnWithFailure</span><span class="sxs-lookup"><span data-stu-id="aef64-519">ReturnWithFailure</span></span>|<span data-ttu-id="aef64-520">1</span><span class="sxs-lookup"><span data-stu-id="aef64-520">1</span></span>|  
|<span data-ttu-id="aef64-521">WatchfortheEventAgain</span><span class="sxs-lookup"><span data-stu-id="aef64-521">WatchfortheEventAgain</span></span>|<span data-ttu-id="aef64-522">2</span><span class="sxs-lookup"><span data-stu-id="aef64-522">2</span></span>|  
  
 <span data-ttu-id="aef64-523">`AfterTimeout`Définie par la propriété à l’aide des valeurs de l' `AfterTimeout` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-523">`AfterTimeout` property-Set by using values from the `AfterTimeout` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-524">Nom convivial dans AfterTimeout</span><span class="sxs-lookup"><span data-stu-id="aef64-524">Friendly name in AfterTimeout</span></span>|<span data-ttu-id="aef64-525">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-525">Numeric value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="aef64-526">ReturnWithSuccess</span><span class="sxs-lookup"><span data-stu-id="aef64-526">ReturnWithSuccess</span></span>|<span data-ttu-id="aef64-527">0</span><span class="sxs-lookup"><span data-stu-id="aef64-527">0</span></span>|  
|<span data-ttu-id="aef64-528">ReturnWithFailure</span><span class="sxs-lookup"><span data-stu-id="aef64-528">ReturnWithFailure</span></span>|<span data-ttu-id="aef64-529">1</span><span class="sxs-lookup"><span data-stu-id="aef64-529">1</span></span>|  
|<span data-ttu-id="aef64-530">WatchfortheEventAgain</span><span class="sxs-lookup"><span data-stu-id="aef64-530">WatchfortheEventAgain</span></span>|<span data-ttu-id="aef64-531">2</span><span class="sxs-lookup"><span data-stu-id="aef64-531">2</span></span>|  
  
 <span data-ttu-id="aef64-532">`WqlQuerySourceType`Définie par la propriété à l’aide des valeurs de l' `QuerySourceType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-532">`WqlQuerySourceType` property-Set by using values from the `QuerySourceType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-533">Nom convivial dans QuerySourceType</span><span class="sxs-lookup"><span data-stu-id="aef64-533">Friendly name in QuerySourceType</span></span>|<span data-ttu-id="aef64-534">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-534">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="aef64-535">FileConnection</span><span class="sxs-lookup"><span data-stu-id="aef64-535">FileConnection</span></span>|<span data-ttu-id="aef64-536">0</span><span class="sxs-lookup"><span data-stu-id="aef64-536">0</span></span>|  
|<span data-ttu-id="aef64-537">DirectInput</span><span class="sxs-lookup"><span data-stu-id="aef64-537">DirectInput</span></span>|<span data-ttu-id="aef64-538">1</span><span class="sxs-lookup"><span data-stu-id="aef64-538">1</span></span>|  
|<span data-ttu-id="aef64-539">Variable</span><span class="sxs-lookup"><span data-stu-id="aef64-539">Variable</span></span>|<span data-ttu-id="aef64-540">2</span><span class="sxs-lookup"><span data-stu-id="aef64-540">2</span></span>|  
  
### <a name="xml-task"></a><span data-ttu-id="aef64-541">Tâche XML</span><span class="sxs-lookup"><span data-stu-id="aef64-541">XML Task</span></span>  
 <span data-ttu-id="aef64-542">`OperationType`Définie par la propriété à l’aide des valeurs de l' `DTSXMLOperation` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-542">`OperationType` property-Set by using values from the `DTSXMLOperation` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-543">Nom convivial dans DTSXMLOperation</span><span class="sxs-lookup"><span data-stu-id="aef64-543">Friendly name in DTSXMLOperation</span></span>|<span data-ttu-id="aef64-544">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-544">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="aef64-545">Valider</span><span class="sxs-lookup"><span data-stu-id="aef64-545">Validate</span></span>|<span data-ttu-id="aef64-546">0</span><span class="sxs-lookup"><span data-stu-id="aef64-546">0</span></span>|  
|<span data-ttu-id="aef64-547">XSLT</span><span class="sxs-lookup"><span data-stu-id="aef64-547">XSLT</span></span>|<span data-ttu-id="aef64-548">1</span><span class="sxs-lookup"><span data-stu-id="aef64-548">1</span></span>|  
|<span data-ttu-id="aef64-549">XPATH</span><span class="sxs-lookup"><span data-stu-id="aef64-549">XPATH</span></span>|<span data-ttu-id="aef64-550">2</span><span class="sxs-lookup"><span data-stu-id="aef64-550">2</span></span>|  
|<span data-ttu-id="aef64-551">Fusionner</span><span class="sxs-lookup"><span data-stu-id="aef64-551">Merge</span></span>|<span data-ttu-id="aef64-552">3</span><span class="sxs-lookup"><span data-stu-id="aef64-552">3</span></span>|  
|<span data-ttu-id="aef64-553">Diff</span><span class="sxs-lookup"><span data-stu-id="aef64-553">Diff</span></span>|<span data-ttu-id="aef64-554">4</span><span class="sxs-lookup"><span data-stu-id="aef64-554">4</span></span>|  
|<span data-ttu-id="aef64-555">Correctif</span><span class="sxs-lookup"><span data-stu-id="aef64-555">Patch</span></span>|<span data-ttu-id="aef64-556">5</span><span class="sxs-lookup"><span data-stu-id="aef64-556">5</span></span>|  
  
 <span data-ttu-id="aef64-557">`SourceType``SecondOperandType`Propriétés, et `XPathSourceType` définies à l’aide des valeurs de l' `DTSXMLSourceType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-557">`SourceType`, `SecondOperandType`, and `XPathSourceType` properties-Set by using values from the `DTSXMLSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-558">Nom convivial dans DTSXMLSourceType</span><span class="sxs-lookup"><span data-stu-id="aef64-558">Friendly name in DTSXMLSourceType</span></span>|<span data-ttu-id="aef64-559">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-559">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="aef64-560">FileConnection</span><span class="sxs-lookup"><span data-stu-id="aef64-560">FileConnection</span></span>|<span data-ttu-id="aef64-561">0</span><span class="sxs-lookup"><span data-stu-id="aef64-561">0</span></span>|  
|<span data-ttu-id="aef64-562">Variable</span><span class="sxs-lookup"><span data-stu-id="aef64-562">Variable</span></span>|<span data-ttu-id="aef64-563">1</span><span class="sxs-lookup"><span data-stu-id="aef64-563">1</span></span>|  
|<span data-ttu-id="aef64-564">DirectInput</span><span class="sxs-lookup"><span data-stu-id="aef64-564">DirectInput</span></span>|<span data-ttu-id="aef64-565">2</span><span class="sxs-lookup"><span data-stu-id="aef64-565">2</span></span>|  
  
 <span data-ttu-id="aef64-566">`DestinationType`et les propriétés **DiffGramDestinationType** -définies à l’aide des valeurs de l' `DTSXMLSaveResultTo` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-566">`DestinationType` and **DiffGramDestinationType** properties-Set by using values from the `DTSXMLSaveResultTo` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-567">Nom convivial dans DTSXMLSaveResultTo</span><span class="sxs-lookup"><span data-stu-id="aef64-567">Friendly name in DTSXMLSaveResultTo</span></span>|<span data-ttu-id="aef64-568">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-568">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="aef64-569">FileConnection</span><span class="sxs-lookup"><span data-stu-id="aef64-569">FileConnection</span></span>|<span data-ttu-id="aef64-570">0</span><span class="sxs-lookup"><span data-stu-id="aef64-570">0</span></span>|  
|<span data-ttu-id="aef64-571">Variable</span><span class="sxs-lookup"><span data-stu-id="aef64-571">Variable</span></span>|<span data-ttu-id="aef64-572">1</span><span class="sxs-lookup"><span data-stu-id="aef64-572">1</span></span>|  
  
 <span data-ttu-id="aef64-573">`ValidationType`Définie par la propriété à l’aide des valeurs de l' `DTSXMLValidationType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-573">`ValidationType` property-Set by using values from the `DTSXMLValidationType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-574">Nom convivial dans DTSXMLValidationType</span><span class="sxs-lookup"><span data-stu-id="aef64-574">Friendly name in DTSXMLValidationType</span></span>|<span data-ttu-id="aef64-575">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-575">Numeric value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="aef64-576">DTD</span><span class="sxs-lookup"><span data-stu-id="aef64-576">DTD</span></span>|<span data-ttu-id="aef64-577">0</span><span class="sxs-lookup"><span data-stu-id="aef64-577">0</span></span>|  
|<span data-ttu-id="aef64-578">XSD</span><span class="sxs-lookup"><span data-stu-id="aef64-578">XSD</span></span>|<span data-ttu-id="aef64-579">1</span><span class="sxs-lookup"><span data-stu-id="aef64-579">1</span></span>|  
  
 <span data-ttu-id="aef64-580">`XPathOperation`Définie par la propriété à l’aide des valeurs de l' `DTSXMLXPathOperation` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-580">`XPathOperation` property-Set by using values from the `DTSXMLXPathOperation` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-581">Nom convivial dans DTSXMLXPathOperation</span><span class="sxs-lookup"><span data-stu-id="aef64-581">Friendly name in DTSXMLXPathOperation</span></span>|<span data-ttu-id="aef64-582">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-582">Numeric Value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="aef64-583">Évaluation</span><span class="sxs-lookup"><span data-stu-id="aef64-583">Evaluation</span></span>|<span data-ttu-id="aef64-584">0</span><span class="sxs-lookup"><span data-stu-id="aef64-584">0</span></span>|  
|<span data-ttu-id="aef64-585">Valeurs</span><span class="sxs-lookup"><span data-stu-id="aef64-585">Values</span></span>|<span data-ttu-id="aef64-586">1</span><span class="sxs-lookup"><span data-stu-id="aef64-586">1</span></span>|  
|<span data-ttu-id="aef64-587">NodeList</span><span class="sxs-lookup"><span data-stu-id="aef64-587">NodeList</span></span>|<span data-ttu-id="aef64-588">2</span><span class="sxs-lookup"><span data-stu-id="aef64-588">2</span></span>|  
  
 <span data-ttu-id="aef64-589">`DiffOptions`Définie par la propriété à l’aide des valeurs de l' `DTSXMLDiffOptions` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-589">`DiffOptions` property-Set by using values from the `DTSXMLDiffOptions` enumeration.</span></span> <span data-ttu-id="aef64-590">Les options dans cet énumérateur ne sont pas mutuellement exclusives.</span><span class="sxs-lookup"><span data-stu-id="aef64-590">The options in this enumerator are not mutually exclusive.</span></span> <span data-ttu-id="aef64-591">Pour utiliser plusieurs options, fournissez une liste des options à appliquer, séparées par des virgules.</span><span class="sxs-lookup"><span data-stu-id="aef64-591">To use multiple options, provide a comma-separated list of the options to apply.</span></span>  
  
|<span data-ttu-id="aef64-592">Nom convivial dans DTSXMLDiffOptions</span><span class="sxs-lookup"><span data-stu-id="aef64-592">Friendly name in DTSXMLDiffOptions</span></span>|<span data-ttu-id="aef64-593">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-593">Numeric Value</span></span>|  
|----------------------------------------|-------------------|  
|<span data-ttu-id="aef64-594">None</span><span class="sxs-lookup"><span data-stu-id="aef64-594">None</span></span>|<span data-ttu-id="aef64-595">0</span><span class="sxs-lookup"><span data-stu-id="aef64-595">0</span></span>|  
|<span data-ttu-id="aef64-596">IgnoreChildOrder</span><span class="sxs-lookup"><span data-stu-id="aef64-596">IgnoreChildOrder</span></span>|<span data-ttu-id="aef64-597">1</span><span class="sxs-lookup"><span data-stu-id="aef64-597">1</span></span>|  
|<span data-ttu-id="aef64-598">IgnoreComments</span><span class="sxs-lookup"><span data-stu-id="aef64-598">IgnoreComments</span></span>|<span data-ttu-id="aef64-599">2</span><span class="sxs-lookup"><span data-stu-id="aef64-599">2</span></span>|  
|<span data-ttu-id="aef64-600">IgnorePI</span><span class="sxs-lookup"><span data-stu-id="aef64-600">IgnorePI</span></span>|<span data-ttu-id="aef64-601">4</span><span class="sxs-lookup"><span data-stu-id="aef64-601">4</span></span>|  
|<span data-ttu-id="aef64-602">IgnoreWhitespace</span><span class="sxs-lookup"><span data-stu-id="aef64-602">IgnoreWhitespace</span></span>|<span data-ttu-id="aef64-603">8</span><span class="sxs-lookup"><span data-stu-id="aef64-603">8</span></span>|  
|<span data-ttu-id="aef64-604">IgnoreNamespaces</span><span class="sxs-lookup"><span data-stu-id="aef64-604">IgnoreNamespaces</span></span>|<span data-ttu-id="aef64-605">16</span><span class="sxs-lookup"><span data-stu-id="aef64-605">16</span></span>|  
|<span data-ttu-id="aef64-606">IgnorePrefixes</span><span class="sxs-lookup"><span data-stu-id="aef64-606">IgnorePrefixes</span></span>|<span data-ttu-id="aef64-607">32</span><span class="sxs-lookup"><span data-stu-id="aef64-607">32</span></span>|  
|<span data-ttu-id="aef64-608">IgnoreXmlDecl</span><span class="sxs-lookup"><span data-stu-id="aef64-608">IgnoreXmlDecl</span></span>|<span data-ttu-id="aef64-609">64</span><span class="sxs-lookup"><span data-stu-id="aef64-609">64</span></span>|  
|<span data-ttu-id="aef64-610">IgnoreDtd</span><span class="sxs-lookup"><span data-stu-id="aef64-610">IgnoreDtd</span></span>|<span data-ttu-id="aef64-611">128</span><span class="sxs-lookup"><span data-stu-id="aef64-611">128</span></span>|  
  
 <span data-ttu-id="aef64-612">`DiffAlgorithm`Définie par la propriété à l’aide des valeurs de l' `DTSXMLDiffAlgorithm` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-612">`DiffAlgorithm` property-Set by using values from the `DTSXMLDiffAlgorithm` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-613">Nom convivial dans DTSXMLDiffAlgorithm</span><span class="sxs-lookup"><span data-stu-id="aef64-613">Friendly name in DTSXMLDiffAlgorithm</span></span>|<span data-ttu-id="aef64-614">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-614">Numeric value</span></span>|  
|------------------------------------------|-------------------|  
|<span data-ttu-id="aef64-615">Auto</span><span class="sxs-lookup"><span data-stu-id="aef64-615">Auto</span></span>|<span data-ttu-id="aef64-616">0</span><span class="sxs-lookup"><span data-stu-id="aef64-616">0</span></span>|  
|<span data-ttu-id="aef64-617">Rapide</span><span class="sxs-lookup"><span data-stu-id="aef64-617">Fast</span></span>|<span data-ttu-id="aef64-618">1</span><span class="sxs-lookup"><span data-stu-id="aef64-618">1</span></span>|  
|<span data-ttu-id="aef64-619">Précise</span><span class="sxs-lookup"><span data-stu-id="aef64-619">Precise</span></span>|<span data-ttu-id="aef64-620">2</span><span class="sxs-lookup"><span data-stu-id="aef64-620">2</span></span>|  
  
##  <a name="maintenance-plan-tasks"></a><a name="MaintenancePlanTasks"></a> <span data-ttu-id="aef64-621">Tâches du plan de maintenance</span><span class="sxs-lookup"><span data-stu-id="aef64-621">Maintenance Plan Tasks</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="aef64-622">inclut un ensemble de tâches qui effectuent des tâches SQL Server à utiliser dans des plans de maintenance et dans des packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aef64-622">includes a set of tasks that perform SQL Server tasks for use in maintenance plans and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="aef64-623">ne prend pas en charge la gestion de ces tâches par programmation et la documentation de référence de programmation n’inclut pas la documentation API de ces tâches et de leurs énumérateurs.</span><span class="sxs-lookup"><span data-stu-id="aef64-623">does not support working with these tasks programmatically and programming reference documentation does not include API documentation of these tasks and their enumerators.</span></span>  
  
### <a name="all-maintenance-tasks"></a><span data-ttu-id="aef64-624">Toutes les tâches de maintenance</span><span class="sxs-lookup"><span data-stu-id="aef64-624">All Maintenance Tasks</span></span>  
 <span data-ttu-id="aef64-625">Toutes les tâches de maintenance utilisent les énumérations suivantes pour définir les propriétés spécifiées.</span><span class="sxs-lookup"><span data-stu-id="aef64-625">All maintenance tasks use the following enumerations to set the specified properties.</span></span>  
  
 <span data-ttu-id="aef64-626">`DatabaseSelectionType`Définie par la propriété à l’aide des valeurs de l' `DatabaseSelection` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-626">`DatabaseSelectionType` property-Set by using values from the `DatabaseSelection` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-627">Nom convivial dans DatabaseSelection</span><span class="sxs-lookup"><span data-stu-id="aef64-627">Friendly name in DatabaseSelection</span></span>|<span data-ttu-id="aef64-628">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-628">Numeric value</span></span>|  
|----------------------------------------|-------------------|  
|<span data-ttu-id="aef64-629">None</span><span class="sxs-lookup"><span data-stu-id="aef64-629">None</span></span>|<span data-ttu-id="aef64-630">0</span><span class="sxs-lookup"><span data-stu-id="aef64-630">0</span></span>|  
|<span data-ttu-id="aef64-631">Tous</span><span class="sxs-lookup"><span data-stu-id="aef64-631">All</span></span>|<span data-ttu-id="aef64-632">1</span><span class="sxs-lookup"><span data-stu-id="aef64-632">1</span></span>|  
|<span data-ttu-id="aef64-633">Système</span><span class="sxs-lookup"><span data-stu-id="aef64-633">System</span></span>|<span data-ttu-id="aef64-634">2</span><span class="sxs-lookup"><span data-stu-id="aef64-634">2</span></span>|  
|<span data-ttu-id="aef64-635">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="aef64-635">User</span></span>|<span data-ttu-id="aef64-636">3</span><span class="sxs-lookup"><span data-stu-id="aef64-636">3</span></span>|  
|<span data-ttu-id="aef64-637">Spécifique</span><span class="sxs-lookup"><span data-stu-id="aef64-637">Specific</span></span>|<span data-ttu-id="aef64-638">4</span><span class="sxs-lookup"><span data-stu-id="aef64-638">4</span></span>|  
  
 <span data-ttu-id="aef64-639">`TableSelectionType`Définie par la propriété à l’aide des valeurs de l' `TableSelection` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-639">`TableSelectionType` property-Set by using values from the `TableSelection` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-640">Nom convivial dans TableSelection</span><span class="sxs-lookup"><span data-stu-id="aef64-640">Friendly name in TableSelection</span></span>|<span data-ttu-id="aef64-641">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-641">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="aef64-642">None</span><span class="sxs-lookup"><span data-stu-id="aef64-642">None</span></span>|<span data-ttu-id="aef64-643">0</span><span class="sxs-lookup"><span data-stu-id="aef64-643">0</span></span>|  
|<span data-ttu-id="aef64-644">Tous</span><span class="sxs-lookup"><span data-stu-id="aef64-644">All</span></span>|<span data-ttu-id="aef64-645">1</span><span class="sxs-lookup"><span data-stu-id="aef64-645">1</span></span>|  
|<span data-ttu-id="aef64-646">Spécifique</span><span class="sxs-lookup"><span data-stu-id="aef64-646">Specific</span></span>|<span data-ttu-id="aef64-647">2</span><span class="sxs-lookup"><span data-stu-id="aef64-647">2</span></span>|  
  
 <span data-ttu-id="aef64-648">`ObjectTypeSelection`Définie par la propriété à l’aide des valeurs de l' `ObjectType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-648">`ObjectTypeSelection` property-Set by using values from the `ObjectType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-649">Nom convivial dans ObjectType</span><span class="sxs-lookup"><span data-stu-id="aef64-649">Friendly name in ObjectType</span></span>|<span data-ttu-id="aef64-650">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-650">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="aef64-651">Table de charge de travail</span><span class="sxs-lookup"><span data-stu-id="aef64-651">Table</span></span>|<span data-ttu-id="aef64-652">0</span><span class="sxs-lookup"><span data-stu-id="aef64-652">0</span></span>|  
|<span data-ttu-id="aef64-653">Affichage</span><span class="sxs-lookup"><span data-stu-id="aef64-653">View</span></span>|<span data-ttu-id="aef64-654">1</span><span class="sxs-lookup"><span data-stu-id="aef64-654">1</span></span>|  
|<span data-ttu-id="aef64-655">TableView</span><span class="sxs-lookup"><span data-stu-id="aef64-655">TableView</span></span>|<span data-ttu-id="aef64-656">2</span><span class="sxs-lookup"><span data-stu-id="aef64-656">2</span></span>|  
  
### <a name="back-up-database-task"></a><span data-ttu-id="aef64-657">Tâche Sauvegarder la base de données</span><span class="sxs-lookup"><span data-stu-id="aef64-657">Back Up Database Task</span></span>  
 <span data-ttu-id="aef64-658">`DestinationCreationType`Définie par la propriété à l’aide des valeurs de l' `DestinationType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-658">`DestinationCreationType` property-Set by using values from the `DestinationType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-659">Nom convivial dans DestinationType</span><span class="sxs-lookup"><span data-stu-id="aef64-659">Friendly name in DestinationType</span></span>|<span data-ttu-id="aef64-660">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-660">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="aef64-661">Auto</span><span class="sxs-lookup"><span data-stu-id="aef64-661">Auto</span></span>|<span data-ttu-id="aef64-662">0</span><span class="sxs-lookup"><span data-stu-id="aef64-662">0</span></span>|  
|<span data-ttu-id="aef64-663">Manuel</span><span class="sxs-lookup"><span data-stu-id="aef64-663">Manual</span></span>|<span data-ttu-id="aef64-664">1</span><span class="sxs-lookup"><span data-stu-id="aef64-664">1</span></span>|  
  
 <span data-ttu-id="aef64-665">`ExistingBackupsAction`Définie par la propriété à l’aide des valeurs de l' `ActionForExistingBackups` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-665">`ExistingBackupsAction` property-Set by using values from the `ActionForExistingBackups` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-666">Nom convivial dans ActionForExistingBackups</span><span class="sxs-lookup"><span data-stu-id="aef64-666">Friendly name in ActionForExistingBackups</span></span>|<span data-ttu-id="aef64-667">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-667">Numeric value</span></span>|  
|-----------------------------------------------|-------------------|  
|<span data-ttu-id="aef64-668">Ajouter</span><span class="sxs-lookup"><span data-stu-id="aef64-668">Append</span></span>|<span data-ttu-id="aef64-669">0</span><span class="sxs-lookup"><span data-stu-id="aef64-669">0</span></span>|  
|<span data-ttu-id="aef64-670">Remplacer</span><span class="sxs-lookup"><span data-stu-id="aef64-670">Overwrite</span></span>|<span data-ttu-id="aef64-671">1</span><span class="sxs-lookup"><span data-stu-id="aef64-671">1</span></span>|  
  
 <span data-ttu-id="aef64-672">`BackupAction`Définie par la propriété à l’aide des valeurs de l' `BackupTaskType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-672">`BackupAction` property-Set by using values from the `BackupTaskType` enumeration.</span></span> <span data-ttu-id="aef64-673">Cette propriété définit avec la propriété `BackupIsIncremental` le type de sauvegarde que la tâche effectue.</span><span class="sxs-lookup"><span data-stu-id="aef64-673">This property works with the `BackupIsIncremental` property to define the type of backup that the task performs.</span></span>  
  
|<span data-ttu-id="aef64-674">Nom convivial dans BackupTaskType</span><span class="sxs-lookup"><span data-stu-id="aef64-674">Friendly name in BackupTaskType</span></span>|<span data-ttu-id="aef64-675">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-675">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="aef64-676">Base de données</span><span class="sxs-lookup"><span data-stu-id="aef64-676">Database</span></span>|<span data-ttu-id="aef64-677">0</span><span class="sxs-lookup"><span data-stu-id="aef64-677">0</span></span>|  
|<span data-ttu-id="aef64-678">Fichiers</span><span class="sxs-lookup"><span data-stu-id="aef64-678">Files</span></span>|<span data-ttu-id="aef64-679">1</span><span class="sxs-lookup"><span data-stu-id="aef64-679">1</span></span>|  
|<span data-ttu-id="aef64-680">Journal</span><span class="sxs-lookup"><span data-stu-id="aef64-680">Log</span></span>|<span data-ttu-id="aef64-681">2</span><span class="sxs-lookup"><span data-stu-id="aef64-681">2</span></span>|  
  
 <span data-ttu-id="aef64-682">`BackupDevice`Défini par la propriété à l’aide de valeurs provenant de l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] énumération Smo (Management Objects) `DeviceType` .</span><span class="sxs-lookup"><span data-stu-id="aef64-682">`BackupDevice` property-Set by using values from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO) `DeviceType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-683">Nom convivial dans DeviceType</span><span class="sxs-lookup"><span data-stu-id="aef64-683">Friendly name in DeviceType</span></span>|<span data-ttu-id="aef64-684">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-684">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="aef64-685">LogicalDevice</span><span class="sxs-lookup"><span data-stu-id="aef64-685">LogicalDevice</span></span>|<span data-ttu-id="aef64-686">0</span><span class="sxs-lookup"><span data-stu-id="aef64-686">0</span></span>|  
|<span data-ttu-id="aef64-687">Bande</span><span class="sxs-lookup"><span data-stu-id="aef64-687">Tape</span></span>|<span data-ttu-id="aef64-688">1</span><span class="sxs-lookup"><span data-stu-id="aef64-688">1</span></span>|  
|<span data-ttu-id="aef64-689">Fichier</span><span class="sxs-lookup"><span data-stu-id="aef64-689">File</span></span>|<span data-ttu-id="aef64-690">2</span><span class="sxs-lookup"><span data-stu-id="aef64-690">2</span></span>|  
|<span data-ttu-id="aef64-691">Pipe</span><span class="sxs-lookup"><span data-stu-id="aef64-691">Pipe</span></span>|<span data-ttu-id="aef64-692">3</span><span class="sxs-lookup"><span data-stu-id="aef64-692">3</span></span>|  
|<span data-ttu-id="aef64-693">VirtualDevice</span><span class="sxs-lookup"><span data-stu-id="aef64-693">VirtualDevice</span></span>|<span data-ttu-id="aef64-694">4</span><span class="sxs-lookup"><span data-stu-id="aef64-694">4</span></span>|  
  
### <a name="maintenance-cleanup-task"></a><span data-ttu-id="aef64-695">Tâche de nettoyage de maintenance</span><span class="sxs-lookup"><span data-stu-id="aef64-695">Maintenance Cleanup Task</span></span>  
 <span data-ttu-id="aef64-696">`FileTypeSelected`Définie par la propriété à l’aide des valeurs de l' `FileType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-696">`FileTypeSelected` property-Set by using values from the `FileType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-697">Nom convivial dans FileType</span><span class="sxs-lookup"><span data-stu-id="aef64-697">Friendly name in FileType</span></span>|<span data-ttu-id="aef64-698">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-698">Numeric value</span></span>|  
|-------------------------------|-------------------|  
|<span data-ttu-id="aef64-699">FileBackup</span><span class="sxs-lookup"><span data-stu-id="aef64-699">FileBackup</span></span>|<span data-ttu-id="aef64-700">0</span><span class="sxs-lookup"><span data-stu-id="aef64-700">0</span></span>|  
|<span data-ttu-id="aef64-701">FileReport</span><span class="sxs-lookup"><span data-stu-id="aef64-701">FileReport</span></span>|<span data-ttu-id="aef64-702">1</span><span class="sxs-lookup"><span data-stu-id="aef64-702">1</span></span>|  
  
 <span data-ttu-id="aef64-703">`OlderThanTimeUnitType`Définie par la propriété à l’aide des valeurs de l' `TimeUnitType` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-703">`OlderThanTimeUnitType` property-Set by using values from the `TimeUnitType` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-704">Nom convivial dans TimeUnitType</span><span class="sxs-lookup"><span data-stu-id="aef64-704">Friendly Name in TimeUnitType</span></span>|<span data-ttu-id="aef64-705">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-705">Numeric Value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="aef64-706">jour</span><span class="sxs-lookup"><span data-stu-id="aef64-706">Day</span></span>|<span data-ttu-id="aef64-707">0</span><span class="sxs-lookup"><span data-stu-id="aef64-707">0</span></span>|  
|<span data-ttu-id="aef64-708">Week</span><span class="sxs-lookup"><span data-stu-id="aef64-708">Week</span></span>|<span data-ttu-id="aef64-709">1</span><span class="sxs-lookup"><span data-stu-id="aef64-709">1</span></span>|  
|<span data-ttu-id="aef64-710">Month</span><span class="sxs-lookup"><span data-stu-id="aef64-710">Month</span></span>|<span data-ttu-id="aef64-711">2</span><span class="sxs-lookup"><span data-stu-id="aef64-711">2</span></span>|  
|<span data-ttu-id="aef64-712">Year</span><span class="sxs-lookup"><span data-stu-id="aef64-712">Year</span></span>|<span data-ttu-id="aef64-713">3</span><span class="sxs-lookup"><span data-stu-id="aef64-713">3</span></span>|  
  
### <a name="update-statistics-task"></a><span data-ttu-id="aef64-714">Tâche Mettre à jour les statistiques</span><span class="sxs-lookup"><span data-stu-id="aef64-714">Update Statistics Task</span></span>  
 <span data-ttu-id="aef64-715">`UpdateType`Défini par la propriété à l’aide de valeurs provenant de l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] énumération Smo (Management Objects) `StatisticsTarget` .</span><span class="sxs-lookup"><span data-stu-id="aef64-715">`UpdateType` property-Set by using values from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO) `StatisticsTarget` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-716">Nom convivial dans StatisticsTarget</span><span class="sxs-lookup"><span data-stu-id="aef64-716">Friendly name in StatisticsTarget</span></span>|<span data-ttu-id="aef64-717">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-717">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="aef64-718">Colonne</span><span class="sxs-lookup"><span data-stu-id="aef64-718">Column</span></span>|<span data-ttu-id="aef64-719">1</span><span class="sxs-lookup"><span data-stu-id="aef64-719">1</span></span>|  
|<span data-ttu-id="aef64-720">Index</span><span class="sxs-lookup"><span data-stu-id="aef64-720">Index</span></span>|<span data-ttu-id="aef64-721">2</span><span class="sxs-lookup"><span data-stu-id="aef64-721">2</span></span>|  
|<span data-ttu-id="aef64-722">Tous</span><span class="sxs-lookup"><span data-stu-id="aef64-722">All</span></span>|<span data-ttu-id="aef64-723">3</span><span class="sxs-lookup"><span data-stu-id="aef64-723">3</span></span>|  
  
##  <a name="common-properties"></a><a name="CommonProperties"></a> <span data-ttu-id="aef64-724">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="aef64-724">Common Properties</span></span>  
 <span data-ttu-id="aef64-725">Les packages, les tâches et les conteneurs de boucles Foreach, de boucles For et de séquences peuvent utiliser les énumérations suivantes pour définir les propriétés spécifiées.</span><span class="sxs-lookup"><span data-stu-id="aef64-725">Packages, tasks, and the Foreach Loop, For Loop, and Sequence containers can use the following enumerations to set the specified properties.</span></span>  
  
 <span data-ttu-id="aef64-726">`ForceExecutionResult`Définie par la propriété à l’aide des valeurs de l' `DTSForcedExecResult` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-726">`ForceExecutionResult` property-Set by using values from the `DTSForcedExecResult` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-727">Nom convivial dans DTSForcedExecResult</span><span class="sxs-lookup"><span data-stu-id="aef64-727">Friendly name in DTSForcedExecResult</span></span>|<span data-ttu-id="aef64-728">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-728">Numeric value</span></span>|  
|------------------------------------------|-------------------|  
|<span data-ttu-id="aef64-729">None</span><span class="sxs-lookup"><span data-stu-id="aef64-729">None</span></span>|<span data-ttu-id="aef64-730">-1</span><span class="sxs-lookup"><span data-stu-id="aef64-730">-1</span></span>|  
|<span data-ttu-id="aef64-731">Succès</span><span class="sxs-lookup"><span data-stu-id="aef64-731">Success</span></span>|<span data-ttu-id="aef64-732">0</span><span class="sxs-lookup"><span data-stu-id="aef64-732">0</span></span>|  
|<span data-ttu-id="aef64-733">Échec</span><span class="sxs-lookup"><span data-stu-id="aef64-733">Failure</span></span>|<span data-ttu-id="aef64-734">1</span><span class="sxs-lookup"><span data-stu-id="aef64-734">1</span></span>|  
|<span data-ttu-id="aef64-735">Completion</span><span class="sxs-lookup"><span data-stu-id="aef64-735">Completion</span></span>|<span data-ttu-id="aef64-736">2</span><span class="sxs-lookup"><span data-stu-id="aef64-736">2</span></span>|  
  
 <span data-ttu-id="aef64-737">`IsolationLevel`propriété définie par l' `IsolationLevel` énumération .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="aef64-737">`IsolationLevel` property-Set by the .NET Framework `IsolationLevel` enumeration.</span></span> <span data-ttu-id="aef64-738">Pour plus d’informations, consultez la bibliothèque de classes .NET Framework dans [MSDN Library](https://go.microsoft.com/fwlink?LinkId=17313).</span><span class="sxs-lookup"><span data-stu-id="aef64-738">For more information, see the .NET Framework Class Library in the [MSDN Library](https://go.microsoft.com/fwlink?LinkId=17313).</span></span>  
  
 <span data-ttu-id="aef64-739">`LoggingMode`Définie par la propriété à l’aide des valeurs de l' `DTSLoggingMode` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-739">`LoggingMode` property-Set by using values from the `DTSLoggingMode` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-740">Nom convivial dans DTSLoggingMode</span><span class="sxs-lookup"><span data-stu-id="aef64-740">Friendly name in DTSLoggingMode</span></span>|<span data-ttu-id="aef64-741">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-741">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="aef64-742">UseParentSetting</span><span class="sxs-lookup"><span data-stu-id="aef64-742">UseParentSetting</span></span>|<span data-ttu-id="aef64-743">0</span><span class="sxs-lookup"><span data-stu-id="aef64-743">0</span></span>|  
|<span data-ttu-id="aef64-744">activé</span><span class="sxs-lookup"><span data-stu-id="aef64-744">Enabled</span></span>|<span data-ttu-id="aef64-745">1</span><span class="sxs-lookup"><span data-stu-id="aef64-745">1</span></span>|  
|<span data-ttu-id="aef64-746">Désactivé</span><span class="sxs-lookup"><span data-stu-id="aef64-746">Disabled</span></span>|<span data-ttu-id="aef64-747">2</span><span class="sxs-lookup"><span data-stu-id="aef64-747">2</span></span>|  
  
 <span data-ttu-id="aef64-748">`TransactionOption`Définie par la propriété à l’aide des valeurs de l' `DTSTransactionOption` énumération.</span><span class="sxs-lookup"><span data-stu-id="aef64-748">`TransactionOption` property-Set by using values from the `DTSTransactionOption` enumeration.</span></span>  
  
|<span data-ttu-id="aef64-749">Nom convivial dans DTSTransactionOption</span><span class="sxs-lookup"><span data-stu-id="aef64-749">Friendly name in DTSTransactionOption</span></span>|<span data-ttu-id="aef64-750">Valeur numérique</span><span class="sxs-lookup"><span data-stu-id="aef64-750">Numeric value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="aef64-751">NotSupported</span><span class="sxs-lookup"><span data-stu-id="aef64-751">NotSupported</span></span>|<span data-ttu-id="aef64-752">0</span><span class="sxs-lookup"><span data-stu-id="aef64-752">0</span></span>|  
|<span data-ttu-id="aef64-753">Prise en charge</span><span class="sxs-lookup"><span data-stu-id="aef64-753">Supported</span></span>|<span data-ttu-id="aef64-754">1</span><span class="sxs-lookup"><span data-stu-id="aef64-754">1</span></span>|  
|<span data-ttu-id="aef64-755">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="aef64-755">Required</span></span>|<span data-ttu-id="aef64-756">2</span><span class="sxs-lookup"><span data-stu-id="aef64-756">2</span></span>|  
  
## <a name="related-tasks"></a><span data-ttu-id="aef64-757">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="aef64-757">Related Tasks</span></span>  
 [<span data-ttu-id="aef64-758">Ajouter ou modifier une expression de propriété</span><span class="sxs-lookup"><span data-stu-id="aef64-758">Add or Change a Property Expression</span></span>](add-or-change-a-property-expression.md)  
  
## <a name="see-also"></a><span data-ttu-id="aef64-759">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="aef64-759">See Also</span></span>  
 <span data-ttu-id="aef64-760">[Expressions de propriété dans des packages](use-property-expressions-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="aef64-760">[Use Property Expressions in Packages](use-property-expressions-in-packages.md) </span></span>  
 <span data-ttu-id="aef64-761">[Packages Integration Services &#40;SSIS&#41;](../integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="aef64-761">[Integration Services &#40;SSIS&#41; Packages](../integration-services-ssis-packages.md) </span></span>  
 <span data-ttu-id="aef64-762">[Conteneurs Integration Services](../control-flow/integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="aef64-762">[Integration Services Containers](../control-flow/integration-services-containers.md) </span></span>  
 <span data-ttu-id="aef64-763">[Tâches Integration Services](../control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="aef64-763">[Integration Services Tasks](../control-flow/integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="aef64-764">Contraintes de précédence</span><span class="sxs-lookup"><span data-stu-id="aef64-764">Precedence Constraints</span></span>](../control-flow/precedence-constraints.md)  
  
  
