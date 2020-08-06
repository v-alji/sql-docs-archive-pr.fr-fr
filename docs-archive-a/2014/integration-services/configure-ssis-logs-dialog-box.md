---
title: Boîte de dialogue Configurer les journaux SSIS | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.configuredtslogs.loggingdetails.f1
- sql12.dts.designer.configuredtslogs.providersandlogs.f1
- sql12.dts.designer.configuredtslogs.containers.f1
helpviewer_keywords:
- Configure SSIS Logs dialog box
ms.assetid: 4b980275-cd9a-4943-8c36-727d51f9a484
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 252b45765fb784790bcca0fb86e2e56e7e7baddc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604082"
---
# <a name="configure-ssis-logs-dialog-box"></a><span data-ttu-id="af409-102">Configurer les journaux SSIS (boîte de dialogue)</span><span class="sxs-lookup"><span data-stu-id="af409-102">Configure SSIS Logs Dialog Box</span></span>
  <span data-ttu-id="af409-103">Utilisez la boîte de dialogue **Configurer les journaux SSIS** pour définir les options de journalisation d’un package.</span><span class="sxs-lookup"><span data-stu-id="af409-103">Use the **Configure SSIS Logs** dialog box to define logging options for a package.</span></span>  
  
 <span data-ttu-id="af409-104">**Que voulez-vous faire ?**</span><span class="sxs-lookup"><span data-stu-id="af409-104">**What do you want to do?**</span></span>  
  
1.  [<span data-ttu-id="af409-105">Ouvrir la boîte de dialogue Configurer les journaux SSIS</span><span class="sxs-lookup"><span data-stu-id="af409-105">Open the Configure SSIS Logs Dialog Box</span></span>](#open_dialog)  
  
2.  [<span data-ttu-id="af409-106">Configurer les options du volet Conteneurs</span><span class="sxs-lookup"><span data-stu-id="af409-106">Configure the Options in the Containers Pane</span></span>](#container)  
  
3.  [<span data-ttu-id="af409-107">Configurer les options sous l'onglet Fournisseurs et journaux</span><span class="sxs-lookup"><span data-stu-id="af409-107">Configure the Options on the Providers and Logs Tab</span></span>](#provider)  
  
4.  [<span data-ttu-id="af409-108">Configurer les options sous l'onglet Détails</span><span class="sxs-lookup"><span data-stu-id="af409-108">Configure the Options on the Details Tab</span></span>](#detail)  
  
##  <a name="open-the-configure-ssis-logs-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="af409-109">Ouvrir la boîte de dialogue Configurer les journaux SSIS</span><span class="sxs-lookup"><span data-stu-id="af409-109">Open the Configure SSIS Logs Dialog Box</span></span>  
 <span data-ttu-id="af409-110">**Pour ouvrir la boîte de dialogue Configurer les journaux SSIS**</span><span class="sxs-lookup"><span data-stu-id="af409-110">**To open the Configure SSIS Logs dialog box**</span></span>  
  
-   <span data-ttu-id="af409-111">Dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] , dans le menu **SSIS** , cliquez sur **Enregistrement** .</span><span class="sxs-lookup"><span data-stu-id="af409-111">In the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click **Logging** on the **SSIS** menu.</span></span>  
  
##  <a name="configure-the-options-in-the-containers-pane"></a><a name="container"></a> <span data-ttu-id="af409-112">Configurer les options du volet Conteneurs</span><span class="sxs-lookup"><span data-stu-id="af409-112">Configure the Options in the Containers Pane</span></span>  
 <span data-ttu-id="af409-113">Utilisez le volet **Conteneurs** de la boîte de dialogue **Configurer les journaux SSIS** pour activer l’enregistrement du fichier journal du package et de ses conteneurs.</span><span class="sxs-lookup"><span data-stu-id="af409-113">Use the **Containers** pane of the **Configure SSIS Logs** dialog box to enable the package and its containers for logging.</span></span>  
  
### <a name="options"></a><span data-ttu-id="af409-114">Options</span><span class="sxs-lookup"><span data-stu-id="af409-114">Options</span></span>  
 <span data-ttu-id="af409-115">**Containers**</span><span class="sxs-lookup"><span data-stu-id="af409-115">**Containers**</span></span>  
 <span data-ttu-id="af409-116">Activez les cases à cocher dans la vue hiérarchique pour activer l'enregistrement du fichier journal du package et de ses conteneurs :</span><span class="sxs-lookup"><span data-stu-id="af409-116">Select the check boxes in the hierarchical view to enable the package and its containers for logging:</span></span>  
  
-   <span data-ttu-id="af409-117">Si la case à cocher est désactivée, l'enregistrement du container dans le fichier journal n'est pas activé.</span><span class="sxs-lookup"><span data-stu-id="af409-117">If cleared, the container is not enabled for logging.</span></span> <span data-ttu-id="af409-118">Activez-la pour permettre l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="af409-118">Select to enable logging.</span></span>  
  
-   <span data-ttu-id="af409-119">Si elle est grisée, le conteneur utilise les options d'enregistrement dans le journal de son parent.</span><span class="sxs-lookup"><span data-stu-id="af409-119">If dimmed, the container uses the logging options of its parent.</span></span> <span data-ttu-id="af409-120">Cette option n'est pas disponible pour le package.</span><span class="sxs-lookup"><span data-stu-id="af409-120">This option is not available for the package.</span></span>  
  
-   <span data-ttu-id="af409-121">Si elle est activée, le conteneur définit ses propres options d'enregistrement dans le journal.</span><span class="sxs-lookup"><span data-stu-id="af409-121">If checked, the container defines its own logging options.</span></span>  
  
 <span data-ttu-id="af409-122">Si un conteneur est grisé alors que vous voulez définir ses options d'enregistrement dans le journal, cliquez sur sa case à cocher deux fois.</span><span class="sxs-lookup"><span data-stu-id="af409-122">If a container is dimmed and you want to set logging options on the container, click its check box twice.</span></span> <span data-ttu-id="af409-123">Le premier clic désactive la case à cocher et le deuxième l'active, vous permettant ainsi de choisir le module fournisseur d'informations à utiliser et de sélectionner les informations à enregistrer.</span><span class="sxs-lookup"><span data-stu-id="af409-123">The first click clears the check box, and the second click selects it, enabling you to choose the log providers to use and select the information to log.</span></span>  
  
##  <a name="configure-the-options-on-the-providers-and-logs-tab"></a><a name="provider"></a> <span data-ttu-id="af409-124">Configurer les options sous l'onglet Fournisseurs et journaux</span><span class="sxs-lookup"><span data-stu-id="af409-124">Configure the Options on the Providers and Logs Tab</span></span>  
 <span data-ttu-id="af409-125">Utilisez l’onglet **Fournisseurs et journaux** de la boîte de dialogue **Configurer les journaux SSIS** pour créer et configurer des journaux permettant de capturer des événements à l’exécution.</span><span class="sxs-lookup"><span data-stu-id="af409-125">Use the **Providers and Logs** tab of the **Configure SSIS Logs** dialog box to create and configure logs for capturing run-time events.</span></span>  
  
### <a name="options"></a><span data-ttu-id="af409-126">Options</span><span class="sxs-lookup"><span data-stu-id="af409-126">Options</span></span>  
 <span data-ttu-id="af409-127">**Type de fournisseur**</span><span class="sxs-lookup"><span data-stu-id="af409-127">**Provider type**</span></span>  
 <span data-ttu-id="af409-128">Sélectionnez un type de module fournisseur d'informations dans la liste.</span><span class="sxs-lookup"><span data-stu-id="af409-128">Select a type of log provider from the list.</span></span>  
  
 <span data-ttu-id="af409-129">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="af409-129">**Add**</span></span>  
 <span data-ttu-id="af409-130">Ajoutez un journal du type spécifié à la collection de modules fournisseurs d'informations du package.</span><span class="sxs-lookup"><span data-stu-id="af409-130">Add a log of the specified type to the collection of log providers of the package.</span></span>  
  
 <span data-ttu-id="af409-131">**Nom**</span><span class="sxs-lookup"><span data-stu-id="af409-131">**Name**</span></span>  
 <span data-ttu-id="af409-132">Activez ou désactivez les journaux pour les conteneurs ou les tâches sélectionnés dans le volet **Conteneurs** de la boîte de dialogue **Configurer les journaux SSIS** à l’aide des cases à cocher.</span><span class="sxs-lookup"><span data-stu-id="af409-132">Enable or disable logs for containers or tasks selected in the **Containers** pane of the **Configure SSIS Logs** dialog box, by using the check boxes.</span></span> <span data-ttu-id="af409-133">Le champ de nom est modifiable.</span><span class="sxs-lookup"><span data-stu-id="af409-133">The name field is editable.</span></span> <span data-ttu-id="af409-134">Utilisez le nom par défaut du fournisseur ou tapez un nom descriptif unique.</span><span class="sxs-lookup"><span data-stu-id="af409-134">Use the default name for the provider, or type a unique descriptive name.</span></span>  
  
 <span data-ttu-id="af409-135">**Description**</span><span class="sxs-lookup"><span data-stu-id="af409-135">**Description**</span></span>  
 <span data-ttu-id="af409-136">Le champ de description est modifiable.</span><span class="sxs-lookup"><span data-stu-id="af409-136">The description field is editable.</span></span> <span data-ttu-id="af409-137">Cliquez sur cette option, puis modifiez la description par défaut du journal.</span><span class="sxs-lookup"><span data-stu-id="af409-137">Click and then modify the default description of the log.</span></span>  
  
 <span data-ttu-id="af409-138">**Configuration**</span><span class="sxs-lookup"><span data-stu-id="af409-138">**Configuration**</span></span>  
 <span data-ttu-id="af409-139">Sélectionnez un gestionnaire de connexions existant dans la liste ou cliquez sur \<**New connection...**> pour en créer un.</span><span class="sxs-lookup"><span data-stu-id="af409-139">Select an existing connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span> <span data-ttu-id="af409-140">En fonction du type de module fournisseur d'informations, vous pouvez configurer un gestionnaire de connexions OLE DB ou un gestionnaire de connexions de fichiers.</span><span class="sxs-lookup"><span data-stu-id="af409-140">Depending on the type of log provider, you can configure an OLE DB connection manager or a File connection manager.</span></span> <span data-ttu-id="af409-141">Le module fournisseur d’informations du journal des événements [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows ne nécessite aucune connexion.</span><span class="sxs-lookup"><span data-stu-id="af409-141">The log provider for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Event Log requires no connection.</span></span>  
  
 <span data-ttu-id="af409-142">Rubriques connexes : [Gestionnaire de connexions OLE DB](connection-manager/ole-db-connection-manager.md) , [Gestionnaire de connexions de fichiers](connection-manager/file-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="af409-142">Related Topics: [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md) manager, [File Connection Manager](connection-manager/file-connection-manager.md)</span></span>  
  
 <span data-ttu-id="af409-143">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="af409-143">**Delete**</span></span>  
 <span data-ttu-id="af409-144">Sélectionnez un module fournisseur d’informations, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="af409-144">Select a log provider and then click **Delete**.</span></span>  
  
##  <a name="configure-the-options-on-the-details-tab"></a><a name="detail"></a> <span data-ttu-id="af409-145">Configurer les options sous l'onglet Détails</span><span class="sxs-lookup"><span data-stu-id="af409-145">Configure the Options on the Details Tab</span></span>  
 <span data-ttu-id="af409-146">Utilisez l’onglet **Détails** de la boîte de dialogue **Configurer les journaux SSIS** pour spécifier les événements à enregistrer dans le journal et les détails des informations à consigner.</span><span class="sxs-lookup"><span data-stu-id="af409-146">Use the **Details** tab of the **Configure SSIS Logs** dialog box to specify the events to enable for logging and the information details to log.</span></span> <span data-ttu-id="af409-147">Les informations sélectionnées s'appliquent à tous les modules fournisseurs d'informations du package.</span><span class="sxs-lookup"><span data-stu-id="af409-147">The information that you select applies to all the log providers in the package.</span></span> <span data-ttu-id="af409-148">Par exemple, vous ne pouvez pas écrire d’informations dans l’instance [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] et écrire des informations différentes dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="af409-148">For example, you cannot write some information to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance and different information to a text file.</span></span>  
  
### <a name="options"></a><span data-ttu-id="af409-149">Options</span><span class="sxs-lookup"><span data-stu-id="af409-149">Options</span></span>  
 <span data-ttu-id="af409-150">**Événements**</span><span class="sxs-lookup"><span data-stu-id="af409-150">**Events**</span></span>  
 <span data-ttu-id="af409-151">Activez ou désactivez les événements à enregistrer dans le journal.</span><span class="sxs-lookup"><span data-stu-id="af409-151">Enable or disable events for logging.</span></span>  
  
 <span data-ttu-id="af409-152">**Description**</span><span class="sxs-lookup"><span data-stu-id="af409-152">**Description**</span></span>  
 <span data-ttu-id="af409-153">Affichez la description de l'événement.</span><span class="sxs-lookup"><span data-stu-id="af409-153">View a description of the event.</span></span>  
  
 <span data-ttu-id="af409-154">**Avancée**</span><span class="sxs-lookup"><span data-stu-id="af409-154">**Advanced**</span></span>  
 <span data-ttu-id="af409-155">Sélectionnez ou désélectionnez les événements à enregistrer dans le journal et les informations à enregistrer pour chaque événement.</span><span class="sxs-lookup"><span data-stu-id="af409-155">Select or clear events to log, and select or clear information to log for each event.</span></span> <span data-ttu-id="af409-156">Cliquez sur **Simple** pour masquer tous les détails de l’enregistrement dans le journal à l’exception de la liste des événements.</span><span class="sxs-lookup"><span data-stu-id="af409-156">Click **Basic** to hide all logging details, except the list of events.</span></span> <span data-ttu-id="af409-157">Les informations suivantes peuvent être enregistrées dans le journal :</span><span class="sxs-lookup"><span data-stu-id="af409-157">The following information is available for logging:</span></span>  
  
|<span data-ttu-id="af409-158">Valeur</span><span class="sxs-lookup"><span data-stu-id="af409-158">Value</span></span>|<span data-ttu-id="af409-159">Description</span><span class="sxs-lookup"><span data-stu-id="af409-159">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="af409-160">**Ordinateur**</span><span class="sxs-lookup"><span data-stu-id="af409-160">**Computer**</span></span>|<span data-ttu-id="af409-161">Nom de l'ordinateur sur lequel s'est produit l'événement enregistré.</span><span class="sxs-lookup"><span data-stu-id="af409-161">The name of the computer on which the logged event occurred.</span></span>|  
|<span data-ttu-id="af409-162">**Opérateur**</span><span class="sxs-lookup"><span data-stu-id="af409-162">**Operator**</span></span>|<span data-ttu-id="af409-163">Nom de l'utilisateur qui a démarré le package.</span><span class="sxs-lookup"><span data-stu-id="af409-163">The user name of the person who started the package.</span></span>|  
|<span data-ttu-id="af409-164">**SourceName**</span><span class="sxs-lookup"><span data-stu-id="af409-164">**SourceName**</span></span>|<span data-ttu-id="af409-165">Nom du package, du conteneur ou de la tâche dans lequel s'est produit l'événement enregistré.</span><span class="sxs-lookup"><span data-stu-id="af409-165">The name of the package, container, or task in which the logged event occurred.</span></span>|  
|<span data-ttu-id="af409-166">**SourceID**</span><span class="sxs-lookup"><span data-stu-id="af409-166">**SourceID**</span></span>|<span data-ttu-id="af409-167">GUID (Global Unique IDentifier) du package, du conteneur ou de la tâche dans lequel s'est produit l'événement enregistré.</span><span class="sxs-lookup"><span data-stu-id="af409-167">The global unique identifier (GUID) of the package, container, or task in which the logged event occurred.</span></span>|  
|<span data-ttu-id="af409-168">**ExecutionID**</span><span class="sxs-lookup"><span data-stu-id="af409-168">**ExecutionID**</span></span>|<span data-ttu-id="af409-169">GUID de l'instance d'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="af409-169">The global unique identifier of the package execution instance.</span></span>|  
|<span data-ttu-id="af409-170">**MessageText**</span><span class="sxs-lookup"><span data-stu-id="af409-170">**MessageText**</span></span>|<span data-ttu-id="af409-171">Un message associé à l'entrée de journal.</span><span class="sxs-lookup"><span data-stu-id="af409-171">A message associated with the log entry.</span></span>|  
|<span data-ttu-id="af409-172">**DataBytes**</span><span class="sxs-lookup"><span data-stu-id="af409-172">**DataBytes**</span></span>|<span data-ttu-id="af409-173">Réservé pour un usage futur.</span><span class="sxs-lookup"><span data-stu-id="af409-173">Reserved for future use.</span></span>|  
  
 <span data-ttu-id="af409-174">**De base**</span><span class="sxs-lookup"><span data-stu-id="af409-174">**Basic**</span></span>  
 <span data-ttu-id="af409-175">Sélectionnez ou désélectionnez les événements à enregistrer dans le journal.</span><span class="sxs-lookup"><span data-stu-id="af409-175">Select or clear events to log.</span></span> <span data-ttu-id="af409-176">Cette option masque les détails d'enregistrement à l'exception de la liste des événements.</span><span class="sxs-lookup"><span data-stu-id="af409-176">This option hides logging details except the list of events.</span></span> <span data-ttu-id="af409-177">Si vous sélectionnez un événement, tous les détails d'enregistrement dans le journal sont sélectionnés pour l'événement par défaut.</span><span class="sxs-lookup"><span data-stu-id="af409-177">If you select an event, all logging details are selected for the event by default.</span></span> <span data-ttu-id="af409-178">Cliquez sur **Avancé** pour afficher tous les détails d’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="af409-178">Click **Advanced** to show all logging details.</span></span>  
  
 <span data-ttu-id="af409-179">**Load**</span><span class="sxs-lookup"><span data-stu-id="af409-179">**Load**</span></span>  
 <span data-ttu-id="af409-180">Spécifiez un fichier XML existant à utiliser comme modèle de configuration des options d'enregistrement dans le journal.</span><span class="sxs-lookup"><span data-stu-id="af409-180">Specify an existing XML file to use as a template for setting logging options.</span></span>  
  
 <span data-ttu-id="af409-181">**Save**</span><span class="sxs-lookup"><span data-stu-id="af409-181">**Save**</span></span>  
 <span data-ttu-id="af409-182">Enregistrez les détails de la configuration en tant que modèle dans un fichier XML.</span><span class="sxs-lookup"><span data-stu-id="af409-182">Save configuration details as a template to an XML file.</span></span>  
  
  
