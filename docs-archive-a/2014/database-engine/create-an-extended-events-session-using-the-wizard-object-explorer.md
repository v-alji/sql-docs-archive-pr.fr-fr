---
title: Créer une session d’événements étendus à l’aide de l’Assistant (Explorateur d’objets) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- Sql12.ssms.XeWizard.Summary.f1
- Sql12.ssms.XeWizard.SetSessionProperties.f1
- Sql12.ssms.XeWizard.CaptureAddFields.f1
- Sql12.ssms.XeWizard.SelectEvents.f1
- Sql12.ssms.XeWizard.SpecifySessionTargets.f1
- Sql12.ssms.XeWizard.Welcome.f1
- sql12.ssms.XeWizard.Welcome.f1
- Sql12.ssms.XeWizard.ChooseTemplate.f1
- Sql12.ssms.XeWizard.SetSessionEventFilters.f1
- Sql12.ssms.XeWizard.Results.f1
helpviewer_keywords:
- Sql11.ssms.XeWizard.CaptureAddFields.f1
- Sql11.ssms.XeWizard.SetSessionEventFilters.f1
- Sql11.ssms.XeWizard.SpecifySessionTargets.f1
- Sql11.ssms.XeWizard.Results.f1
- Sql11.ssms.XeWizard.ChooseTemplate.f1
- Sql11.ssms.XeWizard.SetSessionProperties.f1
- Sql11.ssms.XeWizard.Welcome.f1
- Sql11.ssms.XeWizard.Summary.f1
- Sql11.ssms.XeWizard.SelectEvents.f1
ms.assetid: 80c0456f-17c0-41d8-b2aa-502a2f3bb6de
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cdfc9141b0b99d5b06fc73044b8f4fae623922b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605704"
---
# <a name="create-an-extended-events-session-using-the-wizard-object-explorer"></a><span data-ttu-id="d7554-102">Créer une session d'événements étendus à l'aide de l'Assistant (Explorateur d'objets)</span><span class="sxs-lookup"><span data-stu-id="d7554-102">Create an Extended Events Session Using the Wizard (Object Explorer)</span></span>
  <span data-ttu-id="d7554-103">Pour vous aider à sélectionner et capturer des événements sur votre serveur, les événements étendus incluent un Assistant Nouvelle session qui vous guide tout au long des étapes de création d'une session d'événements étendus.</span><span class="sxs-lookup"><span data-stu-id="d7554-103">To help you select and capture events on your server, Extended Events includes a New Session Wizard that guides you through the steps to create an Extended Events session.</span></span> <span data-ttu-id="d7554-104">L'Assistant Nouvelle session expose la plupart des fonctionnalités Événements étendus.</span><span class="sxs-lookup"><span data-stu-id="d7554-104">The New Session Wizard exposes most of the Extended Events functionality.</span></span> <span data-ttu-id="d7554-105">La [boîte de dialogue Nouvelle session](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md) vous permet également de définir une session Événements étendus qui capture, affiche et analyse vos données.</span><span class="sxs-lookup"><span data-stu-id="d7554-105">The [New Session dialog](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md) also lets you define an Extended Events session that captures, displays, and analyzes your data.</span></span> <span data-ttu-id="d7554-106">La boîte de dialogue Nouvelle session expose toutes les fonctionnalités Événements étendus.</span><span class="sxs-lookup"><span data-stu-id="d7554-106">The New Session dialog exposes all Extended Events functionality.</span></span>  
  
### <a name="to-open-the-new-session-wizard"></a><span data-ttu-id="d7554-107">Pour ouvrir l'Assistant Nouvelle session</span><span class="sxs-lookup"><span data-stu-id="d7554-107">To open the New Session Wizard</span></span>  
  
1.  <span data-ttu-id="d7554-108">Dans l'Explorateur d'objets, développez le nœud **Gestion** , puis **Événements étendus**.</span><span class="sxs-lookup"><span data-stu-id="d7554-108">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="d7554-109">Cliquez avec le bouton droit sur **Sessions**, puis cliquez sur **Assistant Nouvelle session**.</span><span class="sxs-lookup"><span data-stu-id="d7554-109">Right-click **Sessions**, and then click **New Session Wizard**.</span></span>  
  
### <a name="use-the-following-new-session-wizard-pages-to-create-an-event-session"></a><span data-ttu-id="d7554-110">Utiliser les pages suivantes de l'Assistant Nouvelle session pour créer une session d'événements</span><span class="sxs-lookup"><span data-stu-id="d7554-110">Use the following New Session Wizard pages to create an event session</span></span>  
  
-   [<span data-ttu-id="d7554-111">Introduction</span><span class="sxs-lookup"><span data-stu-id="d7554-111">Introduction</span></span>](#BKMK_Welcome)  
  
-   [<span data-ttu-id="d7554-112">Définir les propriétés de session</span><span class="sxs-lookup"><span data-stu-id="d7554-112">Set Session Properties</span></span>](#BKMK_SetSessionProperties)  
  
-   [<span data-ttu-id="d7554-113">Choisir un modèle</span><span class="sxs-lookup"><span data-stu-id="d7554-113">Choose Template</span></span>](#BKMK_ChooseTemplate)  
  
-   [<span data-ttu-id="d7554-114">Sélectionner les événements à capturer</span><span class="sxs-lookup"><span data-stu-id="d7554-114">Select Events to Capture</span></span>](#BKMK_SelectEventsToCapture)  
  
-   [<span data-ttu-id="d7554-115">Capturer les champs globaux</span><span class="sxs-lookup"><span data-stu-id="d7554-115">Capture Global Fields</span></span>](#BKMK_CaptureGlobalFields)  
  
-   [<span data-ttu-id="d7554-116">Définir des filtres d'événement de session</span><span class="sxs-lookup"><span data-stu-id="d7554-116">Set Session Event Filters</span></span>](#BKMK_SetSessionEventFilters)  
  
-   [<span data-ttu-id="d7554-117">Spécifier le stockage des données de session</span><span class="sxs-lookup"><span data-stu-id="d7554-117">Specify Session Data Storage</span></span>](#BKMK_SpecifySessionDataOutput)  
  
-   [<span data-ttu-id="d7554-118">Résumé</span><span class="sxs-lookup"><span data-stu-id="d7554-118">Summary</span></span>](#BKMK_Summary)  
  
-   [<span data-ttu-id="d7554-119">Créer une session d'événements</span><span class="sxs-lookup"><span data-stu-id="d7554-119">Create Event Session</span></span>](#BKMK_CreateEventSession)  
  
##  <a name="introduction"></a><a name="BKMK_Welcome"></a><span data-ttu-id="d7554-120">Présentation</span><span class="sxs-lookup"><span data-stu-id="d7554-120">Introduction</span></span>  
 <span data-ttu-id="d7554-121">Sur la page **Introduction** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d7554-121">On the **Introduction** page, do the following:</span></span>  
  
-   <span data-ttu-id="d7554-122">Sur la page **Introduction** de l'Assistant Nouvelle session, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d7554-122">On the **Introduction** page of the New Session Wizard, click **Next**.</span></span>  
  
     <span data-ttu-id="d7554-123">Cochez la case **Ne plus afficher cette page** si vous souhaitez utiliser l’Assistant plusieurs fois et ne souhaitez pas lire l’introduction à chaque lancement de l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="d7554-123">Select the **Do not show this page again** check box if you will be using the wizard more than once and do not want to read the introduction each time the wizard is launched.</span></span>  
  
##  <a name="set-session-properties"></a><a name="BKMK_SetSessionProperties"></a><span data-ttu-id="d7554-124">Définir les propriétés de session</span><span class="sxs-lookup"><span data-stu-id="d7554-124">Set Session Properties</span></span>  
 <span data-ttu-id="d7554-125">Sur la page **Définir les propriétés de session** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d7554-125">On the **Set Session Properties** page, do the following:</span></span>  
  
-   <span data-ttu-id="d7554-126">Dans la zone **Nom de session** , tapez un nom explicite pour la session d'événements.</span><span class="sxs-lookup"><span data-stu-id="d7554-126">In the **Session name** box, type a meaningful name for the event session.</span></span>  
  
     <span data-ttu-id="d7554-127">Si vous souhaitez démarrer la session lorsque vous démarrez le serveur, activez la case à cocher **Démarrer la session d'événements au démarrage du serveur** , puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d7554-127">If you want to start the session when you start the server, select the **Start the event session at server startup** check box, and then click **Next**.</span></span>  
  
##  <a name="choose-template"></a><a name="BKMK_ChooseTemplate"></a><span data-ttu-id="d7554-128">Choisir un modèle</span><span class="sxs-lookup"><span data-stu-id="d7554-128">Choose Template</span></span>  
 <span data-ttu-id="d7554-129">Sur la page **Choisir un modèle** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d7554-129">On the **Choose Template** page, do the following:</span></span>  
  
-   <span data-ttu-id="d7554-130">Sélectionnez l’option **Utilisez ce modèle de session d’événements** pour sélectionner un jeu de modèles préconfigurés conçu pour les problèmes courants.</span><span class="sxs-lookup"><span data-stu-id="d7554-130">Select the **Use this event session template** option to select from a set of pre-configured templates designed for common problems.</span></span> <span data-ttu-id="d7554-131">Sélectionnez le modèle à utiliser dans la liste déroulante, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d7554-131">Select the template you want to use from the drop-down list, and then click **Next**.</span></span>  
  
     <span data-ttu-id="d7554-132">OU</span><span class="sxs-lookup"><span data-stu-id="d7554-132">-OR-</span></span>  
  
-   <span data-ttu-id="d7554-133">Sélectionnez l’option **Ne pas utiliser de modèle** si vous ne souhaitez pas utiliser un modèle préconfiguré, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d7554-133">Select the **Do not use a template** option if you do not want to use any pre-configured template, and then click **Next**.</span></span>  
  
##  <a name="select-events-to-capture"></a><a name="BKMK_SelectEventsToCapture"></a><span data-ttu-id="d7554-134">Sélectionner les événements à capturer</span><span class="sxs-lookup"><span data-stu-id="d7554-134">Select Events to Capture</span></span>  
 <span data-ttu-id="d7554-135">Sur la page **Sélectionner les événements à capturer** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d7554-135">On the **Select Events to Capture** page, do the following:</span></span>  
  
1.  <span data-ttu-id="d7554-136">Sélectionnez les événements à capturer dans la **Bibliothèque d'événements**, puis cliquez sur la flèche droite.</span><span class="sxs-lookup"><span data-stu-id="d7554-136">Select the events you want to capture from the **Event library**, and then click the right arrow.</span></span> <span data-ttu-id="d7554-137">Vous pouvez sélectionner plusieurs événements dans la bibliothèque d'événements en les sélectionnant et en appuyant sur la touche Shift ou Ctrl.</span><span class="sxs-lookup"><span data-stu-id="d7554-137">You can select multiple events in the Event Library by using either Shift+Click or Ctrl+Click.</span></span>  
  
     <span data-ttu-id="d7554-138">Vous pouvez sélectionner comment rechercher les événements à capturer dans la zone de liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="d7554-138">You can select how you want to search for the events you want to capture from the drop-down list box.</span></span> <span data-ttu-id="d7554-139">Par exemple, vous pouvez rechercher des noms d'événements ou des noms d'événements et leurs descriptions.</span><span class="sxs-lookup"><span data-stu-id="d7554-139">For example, you can search for event names or event names and their descriptions.</span></span> <span data-ttu-id="d7554-140">Vous pouvez rechercher un mot dans la table en entrant le texte à rechercher dans la zone **Bibliothèque d'événements** .</span><span class="sxs-lookup"><span data-stu-id="d7554-140">You can search for any word in the table by entering the text you want to search for in the **Event library** box.</span></span> <span data-ttu-id="d7554-141">Par exemple, si vous souhaitez Rechercher l’événement **lock_acquired** , vous pouvez entrer **Lock**ou **Lock Acquire**.</span><span class="sxs-lookup"><span data-stu-id="d7554-141">For example, if you want to find the **lock_acquired** event, you can enter **lock**, or **lock acquire**.</span></span>  
  
     <span data-ttu-id="d7554-142">Les événements que vous sélectionnez s'affichent dans la zone **Événements sélectionnés** .</span><span class="sxs-lookup"><span data-stu-id="d7554-142">The events you select appear in the **Selected events** box.</span></span> <span data-ttu-id="d7554-143">Pour supprimer des événements de la zone **Événements sélectionnés** , cliquez sur la flèche gauche.</span><span class="sxs-lookup"><span data-stu-id="d7554-143">To remove events from the **Selected events** box, click the left arrow.</span></span>  
  
2.  <span data-ttu-id="d7554-144">Après avoir sélectionné les événements à capturer, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d7554-144">After you select the events you want to capture, click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d7554-145">Les événements du canal de **débogage** sont masqués par défaut.</span><span class="sxs-lookup"><span data-stu-id="d7554-145">Events from the **Debug** channel are hidden by default.</span></span> <span data-ttu-id="d7554-146">Pour afficher des événements de débogage, sélectionnez **Débogage** dans la liste déroulante **Canal** .</span><span class="sxs-lookup"><span data-stu-id="d7554-146">To display debug events, select **Debug** from the **Channel** drop-down list.</span></span>  
  
##  <a name="capture-global-fields"></a><a name="BKMK_CaptureGlobalFields"></a><span data-ttu-id="d7554-147">Capturer les champs globaux</span><span class="sxs-lookup"><span data-stu-id="d7554-147">Capture Global Fields</span></span>  
 <span data-ttu-id="d7554-148">Vous utilisez des champs globaux (également appelés actions) pour associer une ou plusieurs actions de vos événements sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="d7554-148">You use global fields (also referred to as actions) to associate single or multiple actions for your selected events.</span></span> <span data-ttu-id="d7554-149">Si vous avez sélectionné un modèle sur la page **Choisir un modèle** , tous les champs globaux définis dans le modèle sont affichés sur cette page.</span><span class="sxs-lookup"><span data-stu-id="d7554-149">If you selected a template on the **Choose Template** page, all of the global fields that are defined in the template are displayed on this page.</span></span>  
  
 <span data-ttu-id="d7554-150">Sur la page **Capturer les champs globaux** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d7554-150">On the **Capture Global Fields** page, do the following:</span></span>  
  
-   <span data-ttu-id="d7554-151">Sélectionnez les champs globaux à capturer pour la session d'événements, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d7554-151">Select the global fields that you want to capture for the event session, and then click **Next**.</span></span>  
  
     <span data-ttu-id="d7554-152">Vous pouvez supprimer ou ajouter des champs globaux en sélectionnant ou désactivant la case à cocher en regard du champ global.</span><span class="sxs-lookup"><span data-stu-id="d7554-152">You can remove or add global fields by selecting or clearing the check box next to the global field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d7554-153">Les actions sélectionnées sont triées par **Nom** , ce qui vous permet de consulter les actions associées dans l'ordre alphabétique.</span><span class="sxs-lookup"><span data-stu-id="d7554-153">The selected actions are sorted by **Name** enabling you to view the associated actions in alphabetical order.</span></span> <span data-ttu-id="d7554-154">Vous pouvez trier par description ou par état activé/désactivé en cliquant sur l'en-tête de colonne en regard du nom de champ.</span><span class="sxs-lookup"><span data-stu-id="d7554-154">You can sort by description or by the enable/disable status by clicking the column heading next to the field name.</span></span>  
  
##  <a name="set-session-event-filters"></a><a name="BKMK_SetSessionEventFilters"></a><span data-ttu-id="d7554-155">Définir des filtres d’événement de session</span><span class="sxs-lookup"><span data-stu-id="d7554-155">Set Session Event Filters</span></span>  
 <span data-ttu-id="d7554-156">Vous pouvez appliquer des filtres (également appelés prédicats) pour limiter les événements à capturer.</span><span class="sxs-lookup"><span data-stu-id="d7554-156">You can apply filters (also called predicates) to limit the events that you want to capture.</span></span> <span data-ttu-id="d7554-157">Sur la page **Définir des filtres d'événement de session** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d7554-157">On the **Set Session Event Filters** page, do the following:</span></span>  
  
1.  <span data-ttu-id="d7554-158">Si vous n’utilisez pas de modèle préconfiguré, créez vos critères de filtre, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d7554-158">If you are not using a pre-configured template, create your filter criteria, and then click **Next**.</span></span>  
  
     <span data-ttu-id="d7554-159">Si vous utilisez un modèle préconfiguré, dans la section **Filtres du modèle (en lecture seule)** , l’Assistant Nouvelle session répertorie les filtres déjà créés à partir du modèle.</span><span class="sxs-lookup"><span data-stu-id="d7554-159">If you are using a pre-configured template, in the **Filters from template (read-only)** section, the New Session Wizard lists filters already created from the template.</span></span>  
  
2.  <span data-ttu-id="d7554-160">Dans la section **Filtres supplémentaires** , vous pouvez configurer des filtres supplémentaires pour la session d'événements.</span><span class="sxs-lookup"><span data-stu-id="d7554-160">In the **Additional filters** section, you can configure additional filters for the event session.</span></span>  
  
     <span data-ttu-id="d7554-161">Les filtres que vous configurez s'appliquent à tous les événements sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="d7554-161">The filters you configure apply to all selected events.</span></span> <span data-ttu-id="d7554-162">L'Assistant Nouvelle session ne prend pas en charge la configuration de filtres pour chaque événement.</span><span class="sxs-lookup"><span data-stu-id="d7554-162">The New Session Wizard does not support configuring filters for each event.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d7554-163">Lorsque vous configurez une clause de groupe pour votre filtre, les parenthèses redondantes sont supprimées du filtre une fois le résultat enregistré.</span><span class="sxs-lookup"><span data-stu-id="d7554-163">When you configure a group clause for your filter, redundant parentheses are removed from the filter after the result is saved.</span></span> <span data-ttu-id="d7554-164">Par exemple, si vous créez un regroupement de filtre **Clause 1** et **Clause 2**, les parenthèses apparaîtront autour des clauses.</span><span class="sxs-lookup"><span data-stu-id="d7554-164">For example, if you create a filter grouping **Clause 1** and **Clause 2**, parentheses will appear around the clauses.</span></span> <span data-ttu-id="d7554-165">Une fois que vous avez enregistré le filtre, les parenthèses redondantes sont supprimées.</span><span class="sxs-lookup"><span data-stu-id="d7554-165">After you save the filter, the redundant parentheses are removed.</span></span> <span data-ttu-id="d7554-166">La suppression des parenthèses n'affecte pas la logique de filtre.</span><span class="sxs-lookup"><span data-stu-id="d7554-166">The removal of the parentheses does not affect the filter logic.</span></span>  
  
##  <a name="specify-session-data-storage"></a><a name="BKMK_SpecifySessionDataOutput"></a><span data-ttu-id="d7554-167">Spécifier le stockage des données de session</span><span class="sxs-lookup"><span data-stu-id="d7554-167">Specify Session Data Storage</span></span>  
 <span data-ttu-id="d7554-168">Vous utilisez la page **Spécifier le stockage des données de session** pour indiquer comment vous souhaitez collecter vos données pour l'analyse.</span><span class="sxs-lookup"><span data-stu-id="d7554-168">You use the **Specify Session Data Storage** page to specify how you want to collect your data for analysis.</span></span> <span data-ttu-id="d7554-169">Les événements étendus SQL Server utilisent des cibles pour la sortie des données.</span><span class="sxs-lookup"><span data-stu-id="d7554-169">SQL Server Extended Events uses targets for data output.</span></span> <span data-ttu-id="d7554-170">Les cibles stockent les données d'événement et peuvent effectuer des actions telles que l'écriture dans un fichier et l'agrégation des données d'événement.</span><span class="sxs-lookup"><span data-stu-id="d7554-170">Targets store event data and can perform actions such as writing to a file and aggregating event data.</span></span> <span data-ttu-id="d7554-171">Décidez comment vous souhaitez collecter vos données pour l'analyse, et sur la page **Spécifier le stockage des données de session**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d7554-171">Decide how you want to collect your data for analysis, and on the **Specify Session Data Storage** page, do the following:</span></span>  
  
1.  <span data-ttu-id="d7554-172">Pour les grands groupes de données et la création d'enregistrements historiques, activez la case à cocher **Enregistrer les données dans un fichier en vue d'une analyse ultérieure** , puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d7554-172">For large data sets and creating historical records, select the **Save data to a file for later analysis** check box, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="d7554-173">Dans la zone **Nom du fichier sur le serveur** , entrez le chemin d'accès et le nom de fichier ou cliquez sur **Parcourir** pour spécifier le répertoire de fichiers sur le serveur où vous souhaitez enregistrer les données.</span><span class="sxs-lookup"><span data-stu-id="d7554-173">In the **File name on server** box, enter the path and file name, or click **Browse** to specify the file directory on the server where you want to save the data.</span></span>  
  
    2.  <span data-ttu-id="d7554-174">Dans le champ **Taille de fichier maximale** , spécifiez la taille de fichier maximale à utiliser pour la cible de fichier.</span><span class="sxs-lookup"><span data-stu-id="d7554-174">In the **Maximum file size** box, specify the maximum file size to be used for the file target.</span></span> <span data-ttu-id="d7554-175">Si vous ne spécifiez pas de taille de fichier maximale, la taille du fichier augmente jusqu'à ce que le disque soit saturé.</span><span class="sxs-lookup"><span data-stu-id="d7554-175">If you do not specify the maximum file size, the file will grow until the disk is full.</span></span> <span data-ttu-id="d7554-176">La taille de fichier par défaut est 1 gigaoctet (Go).</span><span class="sxs-lookup"><span data-stu-id="d7554-176">The default file size is 1 gigabyte (GB).</span></span>  
  
    3.  <span data-ttu-id="d7554-177">Activez la case à cocher **Activer la substitution de fichier** pour permettre la substitution de fichier pour la cible de fichier.</span><span class="sxs-lookup"><span data-stu-id="d7554-177">Select the **Enable file rollover** check box to enable file rollover for the file target.</span></span>  
  
    4.  <span data-ttu-id="d7554-178">Dans la zone **Nombre maximal de fichiers** , spécifiez le nombre maximal de fichiers à conserver dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="d7554-178">In the **Maximum number of files** box, specify the maximum number of files you want to retain in the file system.</span></span>  
  
2.  <span data-ttu-id="d7554-179">Pour recueillir des données récentes, cochez la case **Utiliser uniquement les données les plus récentes (cible de mémoire tampon en anneau)** , puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d7554-179">For collecting recent data, select the **Work with only the most recent data (ring buffer target)** check box, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="d7554-180">Dans la zone **Nombre d'événements à conserver** , entrez ou sélectionnez le nombre d'événements à conserver en utilisant les flèches haut et bas.</span><span class="sxs-lookup"><span data-stu-id="d7554-180">In the **Number of events to keep** box, enter or select the number of events you want to keep by using the up and down arrows.</span></span>  
  
    2.  <span data-ttu-id="d7554-181">Dans la zone **Taille maximale de la mémoire tampon** , spécifiez la quantité maximale de mémoire tampon à utiliser.</span><span class="sxs-lookup"><span data-stu-id="d7554-181">In the **Maximum buffer memory size** box, specify the maximum amount of buffer memory to use.</span></span> <span data-ttu-id="d7554-182">Les événements existants sont supprimés lorsque cette valeur est atteinte.</span><span class="sxs-lookup"><span data-stu-id="d7554-182">The existing events are dropped when this value is reached.</span></span>  
  
    3.  <span data-ttu-id="d7554-183">Si vous souhaitez conserver un nombre spécifique d’événements de chaque type dans la mémoire tampon, cochez la case **Conserver un nombre spécifique d’événements (par type) lorsque la mémoire tampon est saturée** .</span><span class="sxs-lookup"><span data-stu-id="d7554-183">If you want to keep a specific number of events of each type in the buffer, select the **Keep a specified number of events (per type) when the buffer is full** check box.</span></span>  
  
    4.  <span data-ttu-id="d7554-184">Dans la zone **Nombre d’événements à conserver (par type)** , entrez ou sélectionnez le nombre d’événements (par type) à conserver en utilisant les flèches haut et bas.</span><span class="sxs-lookup"><span data-stu-id="d7554-184">In the **Number of events to keep (per type)** box, enter or select the number of events (per type) that you want to keep by using the up and down arrows.</span></span>  
  
##  <a name="summary"></a><a name="BKMK_Summary"></a> <span data-ttu-id="d7554-185">Résumé</span><span class="sxs-lookup"><span data-stu-id="d7554-185">Summary</span></span>  
 <span data-ttu-id="d7554-186">Sur la page **Résumé** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d7554-186">On the **Summary** page, do the following:</span></span>  
  
1.  <span data-ttu-id="d7554-187">Assurez-vous que vos sélections sont correctes.</span><span class="sxs-lookup"><span data-stu-id="d7554-187">Make sure that your selections are correct.</span></span> <span data-ttu-id="d7554-188">Développez les nœuds de la session d'événements pour vérifier que toutes vos sélections seront incluses dans la session d'événements.</span><span class="sxs-lookup"><span data-stu-id="d7554-188">Expand the event session nodes to verify that all of your selections will be included in the event session.</span></span>  
  
2.  <span data-ttu-id="d7554-189">Cliquez sur **Script** pour exporter le script de création de session vers une nouvelle fenêtre de l'Éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="d7554-189">Click **Script** to export the session creation script to a new Query Editor window.</span></span>  
  
3.  <span data-ttu-id="d7554-190">Cliquez sur **Terminer** pour créer la session d'événements.</span><span class="sxs-lookup"><span data-stu-id="d7554-190">Click **Finish** to create the event session.</span></span>  
  
##  <a name="create-event-session"></a><a name="BKMK_CreateEventSession"></a><span data-ttu-id="d7554-191">Créer une session d’événements</span><span class="sxs-lookup"><span data-stu-id="d7554-191">Create Event Session</span></span>  
 <span data-ttu-id="d7554-192">Sur la page **Créer une session d'événements** , une fois votre session d'événements créée, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d7554-192">On the **Create Event Session** page, after your event session has been successfully created, do the following:</span></span>  
  
1.  <span data-ttu-id="d7554-193">Cliquez sur **Démarrer la session d'événements immédiatement après la création de la session** pour démarrer la session après avoir fermé l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="d7554-193">Click **Start the event session immediately after session creation** to start the session after you close the wizard.</span></span> <span data-ttu-id="d7554-194">Vous devez démarrer la session d'événements immédiatement après avoir créé la session pour être en mesure d'observer les données actives.</span><span class="sxs-lookup"><span data-stu-id="d7554-194">You must start the event session immediately after you create the session to be able to watch live data.</span></span>  
  
2.  <span data-ttu-id="d7554-195">Pour consulter les données actives de votre session d'événements, cliquez sur **Observer les données actives à l'écran lors de leur capture** .</span><span class="sxs-lookup"><span data-stu-id="d7554-195">Click **Watch live data on screen as it is captured** to view live data for your event session.</span></span> <span data-ttu-id="d7554-196">Les données actives commenceront à afficher la trace une fois la session créée.</span><span class="sxs-lookup"><span data-stu-id="d7554-196">The live data will start displaying tracing immediately after the session is created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7554-197">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d7554-197">See Also</span></span>  
 [<span data-ttu-id="d7554-198">Créer une session Événements étendus à l'aide de la boîte de dialogue Nouvelle session</span><span class="sxs-lookup"><span data-stu-id="d7554-198">Create an Extended Events Session Using the New Session Dialog</span></span>](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md)  
  
  
