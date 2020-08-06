---
title: Boîte de dialogue Modifier les paramètres (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.process.batchsettingsdialog.f1
ms.assetid: 0041e042-d7ce-48f9-a690-a6dc65471ff3
author: minewiskan
ms.author: owend
ms.openlocfilehash: e2649195e3aff4e17d378e54c4b1d656361dfe3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603156"
---
# <a name="change-settings-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="70c1e-102">Boîte de dialogue Modifier les paramètres (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="70c1e-102">Change Settings Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="70c1e-103">Utilisez la boîte de dialogue **Modifier les paramètres** dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] et [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pour changer les paramètres de traitement des objets figurant dans la boîte de dialogue **Traiter** .</span><span class="sxs-lookup"><span data-stu-id="70c1e-103">Use the **Change Settings** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to change the settings that govern the processing of objects listed in the **Process** dialog box.</span></span> <span data-ttu-id="70c1e-104">Vous pouvez afficher la boîte de dialogue **Modifier les paramètres** en cliquant sur **Modifier les paramètres** dans la boîte de dialogue **Traiter** .</span><span class="sxs-lookup"><span data-stu-id="70c1e-104">You can display the **Change Settings** dialog box by clicking **Change Settings** on the **Process** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="70c1e-105"> Les paramètres y étant spécifiés remplacent les paramètres par défaut hérités de la base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , pour les objets répertoriés dans la boîte de dialogue **Traiter** .</span><span class="sxs-lookup"><span data-stu-id="70c1e-105">Settings specified in this dialog box override default settings inherited from the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database for the objects listed in the **Process** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="70c1e-106">Options</span><span class="sxs-lookup"><span data-stu-id="70c1e-106">Options</span></span>  
 <span data-ttu-id="70c1e-107">**Options de traitement**</span><span class="sxs-lookup"><span data-stu-id="70c1e-107">**Processing options**</span></span>  
 <span data-ttu-id="70c1e-108">Utilisez cet onglet pour modifier les paramètres relatifs à l'ordre de traitement, à la table d'écriture différée et aux objets affectés pour le traitement.</span><span class="sxs-lookup"><span data-stu-id="70c1e-108">Use this tab to modify settings related to the processing order, writeback table, and affected objects for the processing operation.</span></span> <span data-ttu-id="70c1e-109">Cet onglet contient les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="70c1e-109">The tab contains the following options:</span></span>  
  
 <span data-ttu-id="70c1e-110">**Parallel**</span><span class="sxs-lookup"><span data-stu-id="70c1e-110">**Parallel**</span></span>  
 <span data-ttu-id="70c1e-111">Cliquez sur cette option pour traiter les objets en parallèle.</span><span class="sxs-lookup"><span data-stu-id="70c1e-111">Click to process the objects in parallel.</span></span>  
  
 <span data-ttu-id="70c1e-112">**Nombre maximum de tâches en parallèle**</span><span class="sxs-lookup"><span data-stu-id="70c1e-112">**Maximum parallel tasks**</span></span>  
 <span data-ttu-id="70c1e-113">Sélectionnez le nombre maximal de tâches à exécuter en parallèle par l’opération de traitement ou sélectionnez **Laisser le serveur décider** pour permettre à [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] de choisir un nombre optimal de tâches en parallèle.</span><span class="sxs-lookup"><span data-stu-id="70c1e-113">Select the maximum number of tasks to execute in parallel by the processing operation, or choose **Let the server decide** to allow [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to select an optimal number of parallel tasks.</span></span>  
  
 <span data-ttu-id="70c1e-114">**Séquentiel**</span><span class="sxs-lookup"><span data-stu-id="70c1e-114">**Sequential**</span></span>  
 <span data-ttu-id="70c1e-115">Cliquez sur cette option pour traiter les objets de manière séquentielle.</span><span class="sxs-lookup"><span data-stu-id="70c1e-115">Click to process the objects sequentially.</span></span>  
  
 <span data-ttu-id="70c1e-116">**Mode de transaction**</span><span class="sxs-lookup"><span data-stu-id="70c1e-116">**Transaction mode**</span></span>  
 <span data-ttu-id="70c1e-117">Choisissez le mode de transaction utilisé lors d'un traitement séquentiel des objets :</span><span class="sxs-lookup"><span data-stu-id="70c1e-117">Choose the transaction mode that is used when objects are processed in sequential order:</span></span>  
  
-   <span data-ttu-id="70c1e-118">L'option**Une seule transaction** traite tous les objets dans la même transaction.</span><span class="sxs-lookup"><span data-stu-id="70c1e-118">**One Transaction** processes all objects in the same transaction.</span></span>  
  
-   <span data-ttu-id="70c1e-119">L'option**Transactions séparées** traite tous les objets, notamment les objets dépendants, dans des transactions séparées.</span><span class="sxs-lookup"><span data-stu-id="70c1e-119">**Separate Transactions** processes all objects, including dependent objects, in separate transactions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="70c1e-120"> Cette option est activée uniquement si l'option **Séquentiel** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="70c1e-120">This option is enabled only if **Sequential** is selected.</span></span>  
  
 <span data-ttu-id="70c1e-121">**Option de la table d'écriture différée**</span><span class="sxs-lookup"><span data-stu-id="70c1e-121">**Writeback table option**</span></span>  
 <span data-ttu-id="70c1e-122">Sélectionnez cette option utilisée pour gérer une table d'écriture différée :</span><span class="sxs-lookup"><span data-stu-id="70c1e-122">Choose the option used to manage a writeback table:</span></span>  
  
-   <span data-ttu-id="70c1e-123">L'option**Créer** crée une table d'écriture différée si elle n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="70c1e-123">**Create** creates a writeback table if it does not exist.</span></span> <span data-ttu-id="70c1e-124">Une erreur se produit si une table d'écriture différée existe déjà.</span><span class="sxs-lookup"><span data-stu-id="70c1e-124">An error occurs if a writeback table already exists.</span></span>  
  
-   <span data-ttu-id="70c1e-125">L'option**Toujours créer** crée une table d'écriture différée si elle n'existe pas ou elle remplace la table existante si elle existe.</span><span class="sxs-lookup"><span data-stu-id="70c1e-125">**Create always** creates a writeback table if it does not exist, or overwrites the existing writeback table if it does exist.</span></span>  
  
-   <span data-ttu-id="70c1e-126">L'option**Utiliser l'existante** utilise la table d'écriture différée existante si elle existe.</span><span class="sxs-lookup"><span data-stu-id="70c1e-126">**Use existing** uses the existing writeback table if it exists.</span></span> <span data-ttu-id="70c1e-127">Une erreur se produit si une table d'écriture différée n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="70c1e-127">An error occurs if a writeback table does not exist.</span></span>  
  
 <span data-ttu-id="70c1e-128">**Traiter les objets affectés**</span><span class="sxs-lookup"><span data-stu-id="70c1e-128">**Process affected objects**</span></span>  
 <span data-ttu-id="70c1e-129">Sélectionnez cette option pour inclure et traiter les objets dépendants de ceux compris dans le traitement.</span><span class="sxs-lookup"><span data-stu-id="70c1e-129">Select to include and process objects that depend on objects included in the processing operation.</span></span>  
  
 <span data-ttu-id="70c1e-130">**Erreurs de clé de dimension**</span><span class="sxs-lookup"><span data-stu-id="70c1e-130">**Dimension key errors**</span></span>  
 <span data-ttu-id="70c1e-131">Utilisez cet onglet pour modifier les paramètres relatifs à la configuration d'erreur pour l'opération de traitement.</span><span class="sxs-lookup"><span data-stu-id="70c1e-131">Use this tab to modify settings related to the error configuration for the processing operation.</span></span> <span data-ttu-id="70c1e-132">Cet onglet contient les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="70c1e-132">The tab contains the following options:</span></span>  
  
 <span data-ttu-id="70c1e-133">**Utiliser la configuration d’erreur par défaut**</span><span class="sxs-lookup"><span data-stu-id="70c1e-133">**Use default error configuration**</span></span>  
 <span data-ttu-id="70c1e-134">Sélectionne la configuration par défaut des erreurs pour les objets dans le traitement.</span><span class="sxs-lookup"><span data-stu-id="70c1e-134">Select to use the default error configuration for objects in the processing operation.</span></span>  
  
 <span data-ttu-id="70c1e-135">**Utiliser la configuration d'erreur personnalisée**</span><span class="sxs-lookup"><span data-stu-id="70c1e-135">**Use custom error configuration**</span></span>  
 <span data-ttu-id="70c1e-136">Sélectionnez cette option pour définir la configuration d'erreur pour les objets dans l'opération de traitement.</span><span class="sxs-lookup"><span data-stu-id="70c1e-136">Select to define the error configuration for objects in the processing operation.</span></span>  
  
 <span data-ttu-id="70c1e-137">**Action de l’erreur de clé**</span><span class="sxs-lookup"><span data-stu-id="70c1e-137">**Key error action**</span></span>  
 <span data-ttu-id="70c1e-138">Choisissez l'une des actions suivantes qui se produit lorsqu'une nouvelle clé est détectée lors du traitement sans recherche possible :</span><span class="sxs-lookup"><span data-stu-id="70c1e-138">Choose one of the following actions that occur when a new key is encountered during processing that cannot be looked up:</span></span>  
  
-   <span data-ttu-id="70c1e-139">L'option**Convertir en clé inconnue** agrège les informations de l'enregistrement dans le membre inconnu.</span><span class="sxs-lookup"><span data-stu-id="70c1e-139">**Convert to unknown** aggregates the information for the record into the unknown member.</span></span>  
  
-   <span data-ttu-id="70c1e-140">L'option**Annuler l'enregistrement** empêche le traitement des informations de l'enregistrement, avec cet objet.</span><span class="sxs-lookup"><span data-stu-id="70c1e-140">**Discard record** excludes the information for the record from being processed with the object.</span></span>  
  
 <span data-ttu-id="70c1e-141">**Ignorer le nombre d’erreurs**</span><span class="sxs-lookup"><span data-stu-id="70c1e-141">**Ignore errors count**</span></span>  
 <span data-ttu-id="70c1e-142">Cliquez sur cette option pour ignorer les erreurs qui se produisent lors du traitement.</span><span class="sxs-lookup"><span data-stu-id="70c1e-142">Click to ignore any errors that occur when processing.</span></span>  
  
 <span data-ttu-id="70c1e-143">**Arrêter en cas d’erreur**</span><span class="sxs-lookup"><span data-stu-id="70c1e-143">**Stop on error**</span></span>  
 <span data-ttu-id="70c1e-144">Cliquez sur cette option pour arrêter le traitement en cas d'erreurs.</span><span class="sxs-lookup"><span data-stu-id="70c1e-144">Click to stop processing when errors occur.</span></span> <span data-ttu-id="70c1e-145">Cette option active les options **Nombre d'erreurs** et **Action pour l'erreur** .</span><span class="sxs-lookup"><span data-stu-id="70c1e-145">This option enables the **Number of errors** and the **On error action** options.</span></span>  
  
 <span data-ttu-id="70c1e-146">**Nombre d’erreurs**</span><span class="sxs-lookup"><span data-stu-id="70c1e-146">**Number of errors**</span></span>  
 <span data-ttu-id="70c1e-147">Tapez le nombre d'erreurs à ignorer avant l'arrêt du traitement.</span><span class="sxs-lookup"><span data-stu-id="70c1e-147">Type the number of errors that are ignored before processing stops.</span></span>  
  
 <span data-ttu-id="70c1e-148">**Action pour l'erreur**</span><span class="sxs-lookup"><span data-stu-id="70c1e-148">**On error action**</span></span>  
 <span data-ttu-id="70c1e-149">Choisissez l’une des actions suivantes à effectuer quand le nombre d’erreurs dépasse la valeur spécifiée dans **Nombre d’erreurs**:</span><span class="sxs-lookup"><span data-stu-id="70c1e-149">Choose one of the following actions to be taken when the number of errors exceeds the value in **Number of errors**:</span></span>  
  
-   <span data-ttu-id="70c1e-150">L'option**Arrêter le traitement** met un terme au traitement.</span><span class="sxs-lookup"><span data-stu-id="70c1e-150">**Stop processing** ends the processing operation.</span></span>  
  
-   <span data-ttu-id="70c1e-151">L'option**Arrêter l'inscription dans le journal** arrête l'inscription des erreurs dans le journal mais elle continue le traitement.</span><span class="sxs-lookup"><span data-stu-id="70c1e-151">**Stop logging** stops logging errors, but continues the processing operation.</span></span>  
  
 <span data-ttu-id="70c1e-152">**Clé introuvable**</span><span class="sxs-lookup"><span data-stu-id="70c1e-152">**Key not found**</span></span>  
 <span data-ttu-id="70c1e-153">Spécifiez une des actions suivantes à effectuer lorsqu'une clé est introuvable pendant le traitement d'un objet :</span><span class="sxs-lookup"><span data-stu-id="70c1e-153">Specify one of the following actions to be taken when a key is not found when an object is processed:</span></span>  
  
-   <span data-ttu-id="70c1e-154">L'option**Ignorer l'erreur** ignore l'erreur.</span><span class="sxs-lookup"><span data-stu-id="70c1e-154">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="70c1e-155">L'option**Signaler et continuer** signale l'erreur et continue le traitement.</span><span class="sxs-lookup"><span data-stu-id="70c1e-155">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="70c1e-156">**Signaler et arrêter** signale l'erreur et met fin au traitement.</span><span class="sxs-lookup"><span data-stu-id="70c1e-156">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="70c1e-157">**Clé dupliquée**</span><span class="sxs-lookup"><span data-stu-id="70c1e-157">**Duplicate key**</span></span>  
 <span data-ttu-id="70c1e-158">Spécifiez une des actions suivantes à effectuer lorsqu'une clé dupliquée est trouvée pendant le traitement d'un objet :</span><span class="sxs-lookup"><span data-stu-id="70c1e-158">Specify one of the following actions to be taken if a duplicate key is found when an object is processed:</span></span>  
  
-   <span data-ttu-id="70c1e-159">L'option**Ignorer l'erreur** ignore l'erreur.</span><span class="sxs-lookup"><span data-stu-id="70c1e-159">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="70c1e-160">L'option**Signaler et continuer** signale l'erreur et continue le traitement.</span><span class="sxs-lookup"><span data-stu-id="70c1e-160">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="70c1e-161">**Signaler et arrêter** signale l'erreur et met fin au traitement.</span><span class="sxs-lookup"><span data-stu-id="70c1e-161">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="70c1e-162">**Clé NULL convertie en clé inconnue**</span><span class="sxs-lookup"><span data-stu-id="70c1e-162">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="70c1e-163">Spécifiez l'une des actions suivantes à entreprendre lorsqu'une clé de membre NULL est ajoutée au membre inconnu lors du traitement d'un objet :</span><span class="sxs-lookup"><span data-stu-id="70c1e-163">Specify one of the following actions to be taken when a null member key is added to the unknown member when an object is processed:</span></span>  
  
-   <span data-ttu-id="70c1e-164">L'option**Ignorer l'erreur** ignore l'erreur.</span><span class="sxs-lookup"><span data-stu-id="70c1e-164">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="70c1e-165">L'option**Signaler et continuer** signale l'erreur et continue le traitement.</span><span class="sxs-lookup"><span data-stu-id="70c1e-165">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="70c1e-166">**Signaler et arrêter** signale l'erreur et met fin au traitement.</span><span class="sxs-lookup"><span data-stu-id="70c1e-166">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="70c1e-167">**Clé NULL non autorisée**</span><span class="sxs-lookup"><span data-stu-id="70c1e-167">**Null key not allowed**</span></span>  
 <span data-ttu-id="70c1e-168">Spécifiez l'une des actions suivantes à entreprendre lorsqu'une clé NULL est détectée mais non autorisée, lors du traitement d'un objet :</span><span class="sxs-lookup"><span data-stu-id="70c1e-168">Specify one of the following actions to be taken when a null key is found, but not allowed, when an object is processed:</span></span>  
  
-   <span data-ttu-id="70c1e-169">L'option**Ignorer l'erreur** ignore l'erreur.</span><span class="sxs-lookup"><span data-stu-id="70c1e-169">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="70c1e-170">L'option**Signaler et continuer** signale l'erreur et continue le traitement.</span><span class="sxs-lookup"><span data-stu-id="70c1e-170">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="70c1e-171">**Signaler et arrêter** signale l'erreur et met fin au traitement.</span><span class="sxs-lookup"><span data-stu-id="70c1e-171">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="70c1e-172">**Chemin d'accès du journal des erreurs**</span><span class="sxs-lookup"><span data-stu-id="70c1e-172">**Error log path**</span></span>  
 <span data-ttu-id="70c1e-173">Tapez le chemin d'accès et le nom complets du fichier journal d'erreurs.</span><span class="sxs-lookup"><span data-stu-id="70c1e-173">Type the full path and file name for the error log file.</span></span>  
  
 <span data-ttu-id="70c1e-174">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="70c1e-174">**Browse**</span></span>  
 <span data-ttu-id="70c1e-175">Cliquez sur ce bouton pour ouvrir la boîte de dialogue **Ouvrir** et sélectionnez le chemin complet et le nom de fichier pour le fichier journal d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="70c1e-175">Click to open the **Open** dialog box and select the full path and file name for the error log file.</span></span>  
  
 <span data-ttu-id="70c1e-176">**Traiter les objets affectés**</span><span class="sxs-lookup"><span data-stu-id="70c1e-176">**Process affected objects**</span></span>  
 <span data-ttu-id="70c1e-177">Cliquez sur cette option pour traiter les objets dépendants de ceux étant sélectionnés dans la boîte de dialogue **Traiter** .</span><span class="sxs-lookup"><span data-stu-id="70c1e-177">Click to process the objects that have a dependency on the objects selected in the **Process** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70c1e-178">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="70c1e-178">See Also</span></span>  
 <span data-ttu-id="70c1e-179">[Analysis Services les concepteurs et les boîtes de dialogue &#40;les données multidimensionnelles&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="70c1e-179">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="70c1e-180">Boîte de dialogue traiter &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="70c1e-180">Process Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](process-dialog-box-analysis-services-multidimensional-data.md)  
  
  
