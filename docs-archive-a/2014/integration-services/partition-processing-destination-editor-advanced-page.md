---
title: Éditeur de destination de traitement de partition (page avancé) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partprocessingtransformation.advanced.f1
helpviewer_keywords:
- Partition Processing Destination Editor
ms.assetid: 2039ee0f-069d-479d-90b2-2a12481b1162
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 12845ecd644eabd949ea37fbb18ba6cc9cf342f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601547"
---
# <a name="partition-processing-destination-editor-advanced-page"></a><span data-ttu-id="6d34f-102">Éditeur de destination de traitement de partition (page Avancé)</span><span class="sxs-lookup"><span data-stu-id="6d34f-102">Partition Processing Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="6d34f-103">Utilisez la page **Avancé** de la boîte de dialogue **Éditeur de destination de traitement de partition** pour configurer la gestion des erreurs.</span><span class="sxs-lookup"><span data-stu-id="6d34f-103">Use the **Advanced** page of the **Partition Processing Destination Editor** dialog box to configure error handling.</span></span>  
  
 <span data-ttu-id="6d34f-104">Pour en savoir plus sur la destination de traitement de partition, consultez [Partition Processing Destination](data-flow/partition-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="6d34f-104">To learn more about the Partition Processing destination, see [Partition Processing Destination](data-flow/partition-processing-destination.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6d34f-105">Les tâches décrites ici ne s’appliquent pas aux modèles tabulaires Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="6d34f-105">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="6d34f-106">Vous ne pouvez pas mapper des colonnes d’entrée aux colonnes de partition pour les modèles tabulaires.</span><span class="sxs-lookup"><span data-stu-id="6d34f-106">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="6d34f-107">Vous pouvez en revanche utiliser la tâche DDL d'exécution [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) d'Analysis Services pour traiter la partition.</span><span class="sxs-lookup"><span data-stu-id="6d34f-107">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6d34f-108">Options</span><span class="sxs-lookup"><span data-stu-id="6d34f-108">Options</span></span>  
 <span data-ttu-id="6d34f-109">**Utiliser la configuration d'erreur par défaut**</span><span class="sxs-lookup"><span data-stu-id="6d34f-109">**Use default error configuration.**</span></span>  
 <span data-ttu-id="6d34f-110">Indiquez si vous voulez utiliser la gestion des erreurs par défaut d' [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6d34f-110">Specify whether to use the default [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] error handling.</span></span> <span data-ttu-id="6d34f-111">Par défaut, cette valeur est définie sur `True`.</span><span class="sxs-lookup"><span data-stu-id="6d34f-111">By default, this value is `True`.</span></span>  
  
 <span data-ttu-id="6d34f-112">**Action de l’erreur de clé**</span><span class="sxs-lookup"><span data-stu-id="6d34f-112">**Key error action**</span></span>  
 <span data-ttu-id="6d34f-113">Indiquez comment traiter les enregistrements dont les valeurs de clé ne sont pas acceptables.</span><span class="sxs-lookup"><span data-stu-id="6d34f-113">Specify how to handle records that have unacceptable key values.</span></span>  
  
|<span data-ttu-id="6d34f-114">Valeur</span><span class="sxs-lookup"><span data-stu-id="6d34f-114">Value</span></span>|<span data-ttu-id="6d34f-115">Description</span><span class="sxs-lookup"><span data-stu-id="6d34f-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6d34f-116">**ConvertToUnknown**</span><span class="sxs-lookup"><span data-stu-id="6d34f-116">**ConvertToUnknown**</span></span>|<span data-ttu-id="6d34f-117">Convertir la valeur de clé non acceptable en valeur inconnue (Unknown).</span><span class="sxs-lookup"><span data-stu-id="6d34f-117">Convert the unacceptable key value to the Unknown value.</span></span>|  
|<span data-ttu-id="6d34f-118">**DiscardRecord**</span><span class="sxs-lookup"><span data-stu-id="6d34f-118">**DiscardRecord**</span></span>|<span data-ttu-id="6d34f-119">Ignorer l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="6d34f-119">Discard the record.</span></span>|  
  
 <span data-ttu-id="6d34f-120">**Ignorer les erreurs**</span><span class="sxs-lookup"><span data-stu-id="6d34f-120">**Ignore errors**</span></span>  
 <span data-ttu-id="6d34f-121">Spécifiez que les erreurs doivent être ignorées.</span><span class="sxs-lookup"><span data-stu-id="6d34f-121">Specify that errors should be ignored.</span></span>  
  
 <span data-ttu-id="6d34f-122">**Arrêter en cas d’erreur**</span><span class="sxs-lookup"><span data-stu-id="6d34f-122">**Stop on error**</span></span>  
 <span data-ttu-id="6d34f-123">Spécifiez que le traitement doit s'arrêter lorsqu'une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="6d34f-123">Specify that processing should stop when an error occurs.</span></span>  
  
 <span data-ttu-id="6d34f-124">**Nombre d’erreurs**</span><span class="sxs-lookup"><span data-stu-id="6d34f-124">**Number of errors**</span></span>  
 <span data-ttu-id="6d34f-125">Spécifiez le nombre maximal d’erreurs au-delà duquel le traitement doit s’arrêter, si vous avez sélectionné **Arrêter en cas d’erreur**.</span><span class="sxs-lookup"><span data-stu-id="6d34f-125">Specify the error threshold at which processing should stop, if you have selected **Stop on error**.</span></span>  
  
 <span data-ttu-id="6d34f-126">**Action pour l'erreur**</span><span class="sxs-lookup"><span data-stu-id="6d34f-126">**On error action**</span></span>  
 <span data-ttu-id="6d34f-127">Indiquez l’action à appliquer lorsque le nombre maximal d’erreurs est atteint, si vous avez sélectionné **Arrêter en cas d’erreur**.</span><span class="sxs-lookup"><span data-stu-id="6d34f-127">Specify the action to take when the error threshold is reached, if you have selected **Stop on error**.</span></span>  
  
|<span data-ttu-id="6d34f-128">Valeur</span><span class="sxs-lookup"><span data-stu-id="6d34f-128">Value</span></span>|<span data-ttu-id="6d34f-129">Description</span><span class="sxs-lookup"><span data-stu-id="6d34f-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6d34f-130">**StopProcessing**</span><span class="sxs-lookup"><span data-stu-id="6d34f-130">**StopProcessing**</span></span>|<span data-ttu-id="6d34f-131">Arrêter le traitement.</span><span class="sxs-lookup"><span data-stu-id="6d34f-131">Stop processing.</span></span>|  
|<span data-ttu-id="6d34f-132">**StopLogging**</span><span class="sxs-lookup"><span data-stu-id="6d34f-132">**StopLogging**</span></span>|<span data-ttu-id="6d34f-133">Arrêter d'enregistrer les erreurs.</span><span class="sxs-lookup"><span data-stu-id="6d34f-133">Stop logging errors.</span></span>|  
  
 <span data-ttu-id="6d34f-134">**Clé introuvable**</span><span class="sxs-lookup"><span data-stu-id="6d34f-134">**Key not found**</span></span>  
 <span data-ttu-id="6d34f-135">Indiquez l'action à appliquer en cas d'erreur de clé introuvable.</span><span class="sxs-lookup"><span data-stu-id="6d34f-135">Specify the action to take for a key not found error.</span></span> <span data-ttu-id="6d34f-136">Par défaut, cette valeur est définie sur **ReportAndContinue**.</span><span class="sxs-lookup"><span data-stu-id="6d34f-136">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="6d34f-137">Valeur</span><span class="sxs-lookup"><span data-stu-id="6d34f-137">Value</span></span>|<span data-ttu-id="6d34f-138">Description</span><span class="sxs-lookup"><span data-stu-id="6d34f-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6d34f-139">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="6d34f-139">**IgnoreError**</span></span>|<span data-ttu-id="6d34f-140">Ignorer l'erreur et continuer le traitement.</span><span class="sxs-lookup"><span data-stu-id="6d34f-140">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="6d34f-141">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="6d34f-141">**ReportAndContinue**</span></span>|<span data-ttu-id="6d34f-142">Signaler l'erreur et continuer le traitement.</span><span class="sxs-lookup"><span data-stu-id="6d34f-142">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="6d34f-143">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="6d34f-143">**ReportAndStop**</span></span>|<span data-ttu-id="6d34f-144">Signaler l'erreur et arrêter le traitement.</span><span class="sxs-lookup"><span data-stu-id="6d34f-144">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="6d34f-145">**Clé dupliquée**</span><span class="sxs-lookup"><span data-stu-id="6d34f-145">**Duplicate key**</span></span>  
 <span data-ttu-id="6d34f-146">Indiquez l'action à appliquer en cas d'erreur de clé dupliquée.</span><span class="sxs-lookup"><span data-stu-id="6d34f-146">Specify the action to take for a duplicate key error.</span></span> <span data-ttu-id="6d34f-147">Par défaut, cette valeur est définie sur **IgnoreError**.</span><span class="sxs-lookup"><span data-stu-id="6d34f-147">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="6d34f-148">Valeur</span><span class="sxs-lookup"><span data-stu-id="6d34f-148">Value</span></span>|<span data-ttu-id="6d34f-149">Description</span><span class="sxs-lookup"><span data-stu-id="6d34f-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6d34f-150">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="6d34f-150">**IgnoreError**</span></span>|<span data-ttu-id="6d34f-151">Ignorer l'erreur et continuer le traitement.</span><span class="sxs-lookup"><span data-stu-id="6d34f-151">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="6d34f-152">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="6d34f-152">**ReportAndContinue**</span></span>|<span data-ttu-id="6d34f-153">Signaler l'erreur et continuer le traitement.</span><span class="sxs-lookup"><span data-stu-id="6d34f-153">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="6d34f-154">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="6d34f-154">**ReportAndStop**</span></span>|<span data-ttu-id="6d34f-155">Signaler l'erreur et arrêter le traitement.</span><span class="sxs-lookup"><span data-stu-id="6d34f-155">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="6d34f-156">**Clé NULL convertie en clé inconnue**</span><span class="sxs-lookup"><span data-stu-id="6d34f-156">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="6d34f-157">Indiquez l'action à appliquer lorsqu'une clé NULL a été convertie en clé inconnue (Unknown).</span><span class="sxs-lookup"><span data-stu-id="6d34f-157">Specify the action to take when a null key has been converted to the Unknown value.</span></span> <span data-ttu-id="6d34f-158">Par défaut, cette valeur est définie sur **IgnoreError**.</span><span class="sxs-lookup"><span data-stu-id="6d34f-158">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="6d34f-159">Valeur</span><span class="sxs-lookup"><span data-stu-id="6d34f-159">Value</span></span>|<span data-ttu-id="6d34f-160">Description</span><span class="sxs-lookup"><span data-stu-id="6d34f-160">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6d34f-161">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="6d34f-161">**IgnoreError**</span></span>|<span data-ttu-id="6d34f-162">Ignorer l'erreur et continuer le traitement.</span><span class="sxs-lookup"><span data-stu-id="6d34f-162">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="6d34f-163">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="6d34f-163">**ReportAndContinue**</span></span>|<span data-ttu-id="6d34f-164">Signaler l'erreur et continuer le traitement.</span><span class="sxs-lookup"><span data-stu-id="6d34f-164">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="6d34f-165">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="6d34f-165">**ReportAndStop**</span></span>|<span data-ttu-id="6d34f-166">Signaler l'erreur et arrêter le traitement.</span><span class="sxs-lookup"><span data-stu-id="6d34f-166">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="6d34f-167">**Clé NULL non autorisée**</span><span class="sxs-lookup"><span data-stu-id="6d34f-167">**Null key not allowed**</span></span>  
 <span data-ttu-id="6d34f-168">Indiquez l'action à appliquer si une clé NULL est trouvée alors que les clés NULL ne sont pas autorisées.</span><span class="sxs-lookup"><span data-stu-id="6d34f-168">Specify the action to take when null keys are not allowed and a null key is encountered.</span></span> <span data-ttu-id="6d34f-169">Par défaut, cette valeur est définie sur **ReportAndContinue**.</span><span class="sxs-lookup"><span data-stu-id="6d34f-169">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="6d34f-170">Valeur</span><span class="sxs-lookup"><span data-stu-id="6d34f-170">Value</span></span>|<span data-ttu-id="6d34f-171">Description</span><span class="sxs-lookup"><span data-stu-id="6d34f-171">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6d34f-172">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="6d34f-172">**IgnoreError**</span></span>|<span data-ttu-id="6d34f-173">Ignorer l'erreur et continuer le traitement.</span><span class="sxs-lookup"><span data-stu-id="6d34f-173">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="6d34f-174">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="6d34f-174">**ReportAndContinue**</span></span>|<span data-ttu-id="6d34f-175">Signaler l'erreur et continuer le traitement.</span><span class="sxs-lookup"><span data-stu-id="6d34f-175">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="6d34f-176">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="6d34f-176">**ReportAndStop**</span></span>|<span data-ttu-id="6d34f-177">Signaler l'erreur et arrêter le traitement.</span><span class="sxs-lookup"><span data-stu-id="6d34f-177">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="6d34f-178">**Chemin d'accès du journal des erreurs**</span><span class="sxs-lookup"><span data-stu-id="6d34f-178">**Error log path**</span></span>  
 <span data-ttu-id="6d34f-179">Tapez le chemin du journal des erreurs ou sélectionnez une destination à l’aide du bouton Parcourir **(...)** .</span><span class="sxs-lookup"><span data-stu-id="6d34f-179">Type the path for the error log, or select a destination by using the browse **(...)** button.</span></span>  
  
 <span data-ttu-id="6d34f-180">**Parcourir (...)**</span><span class="sxs-lookup"><span data-stu-id="6d34f-180">**Browse (...)**</span></span>  
 <span data-ttu-id="6d34f-181">Sélectionnez le chemin d'accès du journal des erreurs.</span><span class="sxs-lookup"><span data-stu-id="6d34f-181">Select a path for the error log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d34f-182">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6d34f-182">See Also</span></span>  
 <span data-ttu-id="6d34f-183">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="6d34f-183">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="6d34f-184">Éditeur de destination de traitement de partition &#40;page Mappages&#41;</span><span class="sxs-lookup"><span data-stu-id="6d34f-184">Partition Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/partition-processing-destination-editor-mappings-page.md)  
  
  
