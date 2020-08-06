---
title: Éditeur de destination de traitement de dimension (page avancé) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dimprocessingtransformation.advanced.f1
helpviewer_keywords:
- Dimension Processing Destination Editor
ms.assetid: 2b30835a-2680-4d98-89a4-4f17e29e3818
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5be80cbbfb6871594d7481ccc0f9444d014885e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613556"
---
# <a name="dimension-processing-destination-editor-advanced-page"></a><span data-ttu-id="8bd74-102">Éditeur de destination de traitement de dimension (page Avancé)</span><span class="sxs-lookup"><span data-stu-id="8bd74-102">Dimension Processing Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="8bd74-103">Utilisez la page **Avancé** de la boîte de dialogue **Éditeur de destination de traitement de dimension** pour configurer la gestion des erreurs.</span><span class="sxs-lookup"><span data-stu-id="8bd74-103">Use the **Advanced** page of the **Dimension Processing Destination Editor** dialog box to configure error handling.</span></span>  
  
 <span data-ttu-id="8bd74-104">Pour en savoir plus sur la destination de traitement de dimension, consultez [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="8bd74-104">To learn more about the Dimension Processing destination, see [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="8bd74-105">Options</span><span class="sxs-lookup"><span data-stu-id="8bd74-105">Options</span></span>  
 <span data-ttu-id="8bd74-106">**Utiliser la configuration d'erreur par défaut**</span><span class="sxs-lookup"><span data-stu-id="8bd74-106">**Use default error configuration.**</span></span>  
 <span data-ttu-id="8bd74-107">Indiquez si vous voulez utiliser la gestion des erreurs par défaut d' [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8bd74-107">Specify whether to use the default [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] error handling.</span></span> <span data-ttu-id="8bd74-108">Par défaut, cette valeur est définie sur `True`.</span><span class="sxs-lookup"><span data-stu-id="8bd74-108">By default, this value is `True`.</span></span>  
  
 <span data-ttu-id="8bd74-109">**Action de l’erreur de clé**</span><span class="sxs-lookup"><span data-stu-id="8bd74-109">**Key error action**</span></span>  
 <span data-ttu-id="8bd74-110">Indiquez comment traiter les enregistrements dont les valeurs de clé ne sont pas acceptables.</span><span class="sxs-lookup"><span data-stu-id="8bd74-110">Specify how to handle records that have unacceptable key values.</span></span>  
  
|<span data-ttu-id="8bd74-111">Valeur</span><span class="sxs-lookup"><span data-stu-id="8bd74-111">Value</span></span>|<span data-ttu-id="8bd74-112">Description</span><span class="sxs-lookup"><span data-stu-id="8bd74-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8bd74-113">**ConvertToUnknown**</span><span class="sxs-lookup"><span data-stu-id="8bd74-113">**ConvertToUnknown**</span></span>|<span data-ttu-id="8bd74-114">Convertir la valeur de clé non acceptable en valeur `UnknownMember`.</span><span class="sxs-lookup"><span data-stu-id="8bd74-114">Convert the unacceptable key value to the `UnknownMember` value.</span></span>|  
|<span data-ttu-id="8bd74-115">**DiscardRecord**</span><span class="sxs-lookup"><span data-stu-id="8bd74-115">**DiscardRecord**</span></span>|<span data-ttu-id="8bd74-116">Ignorer l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="8bd74-116">Discard the record.</span></span>|  
  
 <span data-ttu-id="8bd74-117">**Ignorer les erreurs**</span><span class="sxs-lookup"><span data-stu-id="8bd74-117">**Ignore errors**</span></span>  
 <span data-ttu-id="8bd74-118">Spécifiez que les erreurs doivent être ignorées.</span><span class="sxs-lookup"><span data-stu-id="8bd74-118">Specify that errors should be ignored.</span></span>  
  
 <span data-ttu-id="8bd74-119">**Arrêter en cas d’erreur**</span><span class="sxs-lookup"><span data-stu-id="8bd74-119">**Stop on error**</span></span>  
 <span data-ttu-id="8bd74-120">Spécifiez que le traitement doit s'arrêter lorsqu'une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="8bd74-120">Specify that processing should stop when an error occurs.</span></span>  
  
 <span data-ttu-id="8bd74-121">**Nombre d’erreurs**</span><span class="sxs-lookup"><span data-stu-id="8bd74-121">**Number of errors**</span></span>  
 <span data-ttu-id="8bd74-122">Spécifiez le seuil d’erreurs au-delà duquel le traitement doit s’arrêter, si vous avez sélectionné **Arrêter en cas d’erreur**.</span><span class="sxs-lookup"><span data-stu-id="8bd74-122">Specify the error threshold at which processing should stop, if you have selected **Stop on errors**.</span></span>  
  
 <span data-ttu-id="8bd74-123">**Action pour l'erreur**</span><span class="sxs-lookup"><span data-stu-id="8bd74-123">**On error action**</span></span>  
 <span data-ttu-id="8bd74-124">Indiquez l’action à appliquer quand le seuil d’erreurs est atteint, si vous avez sélectionné **Arrêter en cas d’erreur**.</span><span class="sxs-lookup"><span data-stu-id="8bd74-124">Specify the action to take when the error threshold is reached, if you have selected **Stop on errors**.</span></span>  
  
|<span data-ttu-id="8bd74-125">Valeur</span><span class="sxs-lookup"><span data-stu-id="8bd74-125">Value</span></span>|<span data-ttu-id="8bd74-126">Description</span><span class="sxs-lookup"><span data-stu-id="8bd74-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8bd74-127">**StopProcessing**</span><span class="sxs-lookup"><span data-stu-id="8bd74-127">**StopProcessing**</span></span>|<span data-ttu-id="8bd74-128">Arrêter le traitement.</span><span class="sxs-lookup"><span data-stu-id="8bd74-128">Stop processing.</span></span>|  
|<span data-ttu-id="8bd74-129">**StopLogging**</span><span class="sxs-lookup"><span data-stu-id="8bd74-129">**StopLogging**</span></span>|<span data-ttu-id="8bd74-130">Arrêter d'enregistrer les erreurs.</span><span class="sxs-lookup"><span data-stu-id="8bd74-130">Stop logging errors.</span></span>|  
  
 <span data-ttu-id="8bd74-131">**Clé introuvable**</span><span class="sxs-lookup"><span data-stu-id="8bd74-131">**Key not found**</span></span>  
 <span data-ttu-id="8bd74-132">Indiquez l'action à appliquer en cas d'erreur de clé introuvable.</span><span class="sxs-lookup"><span data-stu-id="8bd74-132">Specify the action to take for a key not found error.</span></span> <span data-ttu-id="8bd74-133">Par défaut, cette valeur est définie sur **ReportAndContinue**.</span><span class="sxs-lookup"><span data-stu-id="8bd74-133">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="8bd74-134">Valeur</span><span class="sxs-lookup"><span data-stu-id="8bd74-134">Value</span></span>|<span data-ttu-id="8bd74-135">Description</span><span class="sxs-lookup"><span data-stu-id="8bd74-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8bd74-136">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="8bd74-136">**IgnoreError**</span></span>|<span data-ttu-id="8bd74-137">Ignorer l'erreur et continuer le traitement.</span><span class="sxs-lookup"><span data-stu-id="8bd74-137">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="8bd74-138">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="8bd74-138">**ReportAndContinue**</span></span>|<span data-ttu-id="8bd74-139">Signaler l'erreur et continuer le traitement.</span><span class="sxs-lookup"><span data-stu-id="8bd74-139">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="8bd74-140">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="8bd74-140">**ReportAndStop**</span></span>|<span data-ttu-id="8bd74-141">Signaler l'erreur et arrêter le traitement.</span><span class="sxs-lookup"><span data-stu-id="8bd74-141">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="8bd74-142">**Clé dupliquée**</span><span class="sxs-lookup"><span data-stu-id="8bd74-142">**Duplicate key**</span></span>  
 <span data-ttu-id="8bd74-143">Indiquez l'action à appliquer en cas d'erreur de clé dupliquée.</span><span class="sxs-lookup"><span data-stu-id="8bd74-143">Specify the action to take for a duplicate key error.</span></span> <span data-ttu-id="8bd74-144">Par défaut, cette valeur est définie sur **IgnoreError**.</span><span class="sxs-lookup"><span data-stu-id="8bd74-144">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="8bd74-145">Valeur</span><span class="sxs-lookup"><span data-stu-id="8bd74-145">Value</span></span>|<span data-ttu-id="8bd74-146">Description</span><span class="sxs-lookup"><span data-stu-id="8bd74-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8bd74-147">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="8bd74-147">**IgnoreError**</span></span>|<span data-ttu-id="8bd74-148">Ignorer l'erreur et continuer le traitement.</span><span class="sxs-lookup"><span data-stu-id="8bd74-148">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="8bd74-149">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="8bd74-149">**ReportAndContinue**</span></span>|<span data-ttu-id="8bd74-150">Signaler l'erreur et continuer le traitement.</span><span class="sxs-lookup"><span data-stu-id="8bd74-150">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="8bd74-151">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="8bd74-151">**ReportAndStop**</span></span>|<span data-ttu-id="8bd74-152">Signaler l'erreur et arrêter le traitement.</span><span class="sxs-lookup"><span data-stu-id="8bd74-152">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="8bd74-153">**Clé NULL convertie en clé inconnue**</span><span class="sxs-lookup"><span data-stu-id="8bd74-153">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="8bd74-154">Indiquez l'action à appliquer lorsqu'une clé NULL a été convertie en clé `UnknownMember`.</span><span class="sxs-lookup"><span data-stu-id="8bd74-154">Specify the action to take when a null key has been converted to the `UnknownMember` value.</span></span> <span data-ttu-id="8bd74-155">Par défaut, cette valeur est définie sur **IgnoreError**.</span><span class="sxs-lookup"><span data-stu-id="8bd74-155">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="8bd74-156">Valeur</span><span class="sxs-lookup"><span data-stu-id="8bd74-156">Value</span></span>|<span data-ttu-id="8bd74-157">Description</span><span class="sxs-lookup"><span data-stu-id="8bd74-157">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8bd74-158">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="8bd74-158">**IgnoreError**</span></span>|<span data-ttu-id="8bd74-159">Ignorer l'erreur et continuer le traitement.</span><span class="sxs-lookup"><span data-stu-id="8bd74-159">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="8bd74-160">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="8bd74-160">**ReportAndContinue**</span></span>|<span data-ttu-id="8bd74-161">Signaler l'erreur et continuer le traitement.</span><span class="sxs-lookup"><span data-stu-id="8bd74-161">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="8bd74-162">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="8bd74-162">**ReportAndStop**</span></span>|<span data-ttu-id="8bd74-163">Signaler l'erreur et arrêter le traitement.</span><span class="sxs-lookup"><span data-stu-id="8bd74-163">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="8bd74-164">**Clé NULL non autorisée**</span><span class="sxs-lookup"><span data-stu-id="8bd74-164">**Null key not allowed**</span></span>  
 <span data-ttu-id="8bd74-165">Indiquez l'action à appliquer si une clé NULL est trouvée alors que les clés NULL ne sont pas autorisées.</span><span class="sxs-lookup"><span data-stu-id="8bd74-165">Specify the action to take when null keys are not allowed and a null key is encountered.</span></span> <span data-ttu-id="8bd74-166">Par défaut, cette valeur est définie sur **ReportAndContinue**.</span><span class="sxs-lookup"><span data-stu-id="8bd74-166">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="8bd74-167">Valeur</span><span class="sxs-lookup"><span data-stu-id="8bd74-167">Value</span></span>|<span data-ttu-id="8bd74-168">Description</span><span class="sxs-lookup"><span data-stu-id="8bd74-168">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8bd74-169">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="8bd74-169">**IgnoreError**</span></span>|<span data-ttu-id="8bd74-170">Ignorer l'erreur et continuer le traitement.</span><span class="sxs-lookup"><span data-stu-id="8bd74-170">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="8bd74-171">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="8bd74-171">**ReportAndContinue**</span></span>|<span data-ttu-id="8bd74-172">Signaler l'erreur et continuer le traitement.</span><span class="sxs-lookup"><span data-stu-id="8bd74-172">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="8bd74-173">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="8bd74-173">**ReportAndStop**</span></span>|<span data-ttu-id="8bd74-174">Signaler l'erreur et arrêter le traitement.</span><span class="sxs-lookup"><span data-stu-id="8bd74-174">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="8bd74-175">**Chemin d'accès du journal des erreurs**</span><span class="sxs-lookup"><span data-stu-id="8bd74-175">**Error log path**</span></span>  
 <span data-ttu-id="8bd74-176">Tapez le chemin du journal des erreurs ou cliquez sur le bouton **Parcourir (...)** pour sélectionner une destination.</span><span class="sxs-lookup"><span data-stu-id="8bd74-176">Type the path of the error log, or click the **browse(...)** button to select a destination.</span></span>  
  
 <span data-ttu-id="8bd74-177">**Parcourir (...)**</span><span class="sxs-lookup"><span data-stu-id="8bd74-177">**Browse (...)**</span></span>  
 <span data-ttu-id="8bd74-178">Sélectionnez le chemin d'accès du journal des erreurs.</span><span class="sxs-lookup"><span data-stu-id="8bd74-178">Select a path for the error log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd74-179">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8bd74-179">See Also</span></span>  
 <span data-ttu-id="8bd74-180">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8bd74-180">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="8bd74-181">[Éditeur de destination de traitement de dimension &#40;page Gestionnaire de connexions&#41;](../../2014/integration-services/dimension-processing-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="8bd74-181">[Dimension Processing Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/dimension-processing-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="8bd74-182">Éditeur de destination de traitement de dimension &#40;page Mappages&#41;</span><span class="sxs-lookup"><span data-stu-id="8bd74-182">Dimension Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/dimension-processing-destination-editor-mappings-page.md)  
  
  
