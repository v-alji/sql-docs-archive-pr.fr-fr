---
title: Configuration d’erreur (boîte de dialogue structure d’exploration de données) (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.miningstructuredialog.general.f1
ms.assetid: d9aa028b-bad9-49c7-a81c-c2150e4dd481
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5eb41da36400271a9b058ecf275d26bd22d3ee53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614881"
---
# <a name="error-configuration-mining-structure-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="e7770-102">Configuration d'erreur (boîte de dialogue Structure d'exploration de données) (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="e7770-102">Error Configuration (Mining Structure Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="e7770-103">Utilisez la page **Configuration d'erreur** de la boîte de dialogue **Propriétés de la structure d'exploration de données** de **SQL Server Management Studio** pour définir les propriétés de configuration des erreurs d'une structure d'exploration des données dans une base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e7770-103">Use the **Error Configuration** page of the **Mining Structure Properties** dialog box in **SQL Server Management Studio** to set the error configuration properties of a mining structure in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e7770-104">Options</span><span class="sxs-lookup"><span data-stu-id="e7770-104">Options</span></span>  
 <span data-ttu-id="e7770-105">**Utiliser la configuration d’erreur par défaut**</span><span class="sxs-lookup"><span data-stu-id="e7770-105">**Use default error configuration**</span></span>  
 <span data-ttu-id="e7770-106">Sélectionne la configuration par défaut des erreurs pour les objets dans le traitement.</span><span class="sxs-lookup"><span data-stu-id="e7770-106">Select to use the default error configuration for objects in the processing operation.</span></span>  
  
 <span data-ttu-id="e7770-107">**Action de l’erreur de clé**</span><span class="sxs-lookup"><span data-stu-id="e7770-107">**Key error action**</span></span>  
 <span data-ttu-id="e7770-108">Choisissez l'une des actions suivantes qui se produit lorsqu'une nouvelle clé est détectée lors du traitement sans recherche possible :</span><span class="sxs-lookup"><span data-stu-id="e7770-108">Choose one of the following actions that occur when a new key is encountered during processing that cannot be looked up:</span></span>  
  
-   <span data-ttu-id="e7770-109">L'option**Convertir en clé inconnue** agrège les informations de l'enregistrement dans le membre inconnu.</span><span class="sxs-lookup"><span data-stu-id="e7770-109">**Convert to unknown** aggregates the information for the record into the unknown member.</span></span>  
  
-   <span data-ttu-id="e7770-110">L'option**Annuler l'enregistrement** empêche le traitement des informations de l'enregistrement, avec cet objet.</span><span class="sxs-lookup"><span data-stu-id="e7770-110">**Discard record** excludes the information for the record from being processed with the object.</span></span>  
  
 <span data-ttu-id="e7770-111">**Ignorer le nombre d’erreurs**</span><span class="sxs-lookup"><span data-stu-id="e7770-111">**Ignore errors count**</span></span>  
 <span data-ttu-id="e7770-112">Cliquez sur cette option pour ignorer les erreurs qui se produisent lors du traitement.</span><span class="sxs-lookup"><span data-stu-id="e7770-112">Click to ignore any errors that occur when processing.</span></span>  
  
 <span data-ttu-id="e7770-113">**Arrêter en cas d’erreur**</span><span class="sxs-lookup"><span data-stu-id="e7770-113">**Stop on error**</span></span>  
 <span data-ttu-id="e7770-114">Cliquez sur cette option pour arrêter le traitement en cas d'erreurs.</span><span class="sxs-lookup"><span data-stu-id="e7770-114">Click to stop processing when errors occur.</span></span> <span data-ttu-id="e7770-115">Cette option active les options **Nombre d'erreurs** et **Action pour l'erreur** .</span><span class="sxs-lookup"><span data-stu-id="e7770-115">This option enables the **Number of errors** and the **On error action** options.</span></span>  
  
 <span data-ttu-id="e7770-116">**Nombre d’erreurs**</span><span class="sxs-lookup"><span data-stu-id="e7770-116">**Number of errors**</span></span>  
 <span data-ttu-id="e7770-117">Tapez le nombre d'erreurs à ignorer avant l'arrêt du traitement.</span><span class="sxs-lookup"><span data-stu-id="e7770-117">Type the number of errors that are ignored before processing stops.</span></span>  
  
 <span data-ttu-id="e7770-118">**Action pour l'erreur**</span><span class="sxs-lookup"><span data-stu-id="e7770-118">**On error action**</span></span>  
 <span data-ttu-id="e7770-119">Choisissez l’une des actions suivantes à effectuer quand le nombre d’erreurs dépasse la valeur spécifiée dans **Nombre d’erreurs**:</span><span class="sxs-lookup"><span data-stu-id="e7770-119">Choose one of the following actions to be taken when the number of errors exceeds the value in **Number of errors**:</span></span>  
  
-   <span data-ttu-id="e7770-120">L'option**Arrêter le traitement** met un terme au traitement.</span><span class="sxs-lookup"><span data-stu-id="e7770-120">**Stop processing** ends the processing operation.</span></span>  
  
-   <span data-ttu-id="e7770-121">L'option**Arrêter l'inscription dans le journal** arrête l'inscription des erreurs dans le journal mais elle continue le traitement.</span><span class="sxs-lookup"><span data-stu-id="e7770-121">**Stop logging** stops logging errors, but continues the processing operation.</span></span>  
  
 <span data-ttu-id="e7770-122">**Clé introuvable**</span><span class="sxs-lookup"><span data-stu-id="e7770-122">**Key not found**</span></span>  
 <span data-ttu-id="e7770-123">Spécifiez une des actions suivantes à effectuer lorsqu'une clé est introuvable pendant le traitement d'un objet :</span><span class="sxs-lookup"><span data-stu-id="e7770-123">Specify one of the following actions to be taken when a key is not found when an object is processed:</span></span>  
  
-   <span data-ttu-id="e7770-124">**Ignorer l’erreur** ignore l’erreur</span><span class="sxs-lookup"><span data-stu-id="e7770-124">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="e7770-125">**Signaler et continuer** signale l’erreur et poursuit l’opération de traitement</span><span class="sxs-lookup"><span data-stu-id="e7770-125">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="e7770-126">**Signaler et arrêter** signale l'erreur et met fin au traitement.</span><span class="sxs-lookup"><span data-stu-id="e7770-126">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="e7770-127">**Clé dupliquée**</span><span class="sxs-lookup"><span data-stu-id="e7770-127">**Duplicate key**</span></span>  
 <span data-ttu-id="e7770-128">Spécifiez une des actions suivantes à effectuer lorsqu'une clé dupliquée est trouvée pendant le traitement d'un objet :</span><span class="sxs-lookup"><span data-stu-id="e7770-128">Specify one of the following actions to be taken if a duplicate key is found when an object is processed:</span></span>  
  
-   <span data-ttu-id="e7770-129">**Ignorer l’erreur** ignore l’erreur</span><span class="sxs-lookup"><span data-stu-id="e7770-129">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="e7770-130">**Signaler et continuer** signale l’erreur et poursuit l’opération de traitement</span><span class="sxs-lookup"><span data-stu-id="e7770-130">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="e7770-131">**Signaler et arrêter** signale l'erreur et met fin au traitement.</span><span class="sxs-lookup"><span data-stu-id="e7770-131">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="e7770-132">**Clé NULL convertie en clé inconnue**</span><span class="sxs-lookup"><span data-stu-id="e7770-132">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="e7770-133">Spécifiez une des actions suivantes à effectuer lorsqu'un membre NULL est ajouté au membre inconnu pendant le traitement d'un objet :</span><span class="sxs-lookup"><span data-stu-id="e7770-133">Specify one of the following actions to be taken when a null member key is added to the unknown member when an object is processed.</span></span>  
  
-   <span data-ttu-id="e7770-134">**Ignorer l’erreur** ignore l’erreur</span><span class="sxs-lookup"><span data-stu-id="e7770-134">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="e7770-135">**Signaler et continuer** signale l’erreur et poursuit l’opération de traitement</span><span class="sxs-lookup"><span data-stu-id="e7770-135">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="e7770-136">**Signaler et arrêter** signale l'erreur et met fin au traitement.</span><span class="sxs-lookup"><span data-stu-id="e7770-136">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="e7770-137">**Clé NULL non autorisée**</span><span class="sxs-lookup"><span data-stu-id="e7770-137">**Null key not allowed**</span></span>  
 <span data-ttu-id="e7770-138">Spécifiez une des actions suivantes à effectuer lorsqu'une clé NULL est trouvée, mais non autorisée, pendant le traitement d'un objet :</span><span class="sxs-lookup"><span data-stu-id="e7770-138">Specify one of the following actions to be taken when a null key is found, but not allowed, when an object is processed.</span></span>  
  
-   <span data-ttu-id="e7770-139">**Ignorer l’erreur** ignore l’erreur</span><span class="sxs-lookup"><span data-stu-id="e7770-139">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="e7770-140">**Signaler et continuer** signale l’erreur et poursuit l’opération de traitement</span><span class="sxs-lookup"><span data-stu-id="e7770-140">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="e7770-141">**Signaler et arrêter** signale l'erreur et met fin au traitement.</span><span class="sxs-lookup"><span data-stu-id="e7770-141">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="e7770-142">**Chemin d'accès du journal des erreurs**</span><span class="sxs-lookup"><span data-stu-id="e7770-142">**Error log path**</span></span>  
 <span data-ttu-id="e7770-143">Tapez le chemin d'accès et le nom complets du fichier journal d'erreurs.</span><span class="sxs-lookup"><span data-stu-id="e7770-143">Type the full path and file name for the error log file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7770-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e7770-144">See Also</span></span>  
 <span data-ttu-id="e7770-145">[Boîte de dialogue Propriétés de la structure d’exploration de données &#40;Analysis Services d’exploration de données&#41;](mining-structure-properties-dialog-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="e7770-145">[Mining Structure Properties Dialog &#40;Analysis Services - Data Mining&#41;](mining-structure-properties-dialog-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="e7770-146">Boîte de dialogue structure d’exploration de données &#40;&#41; &#40;Analysis Services d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="e7770-146">General &#40;Mining Structure Dialog Box&#41; &#40;Analysis Services - Data Mining&#41;</span></span>](general-mining-structure-dialog-box-analysis-services-data-mining.md)  
  
  
