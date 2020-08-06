---
title: Éditeur de source SAP BW (page Gestionnaire de connexions) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 2a6dc531-85ca-43c5-a65f-3ad3f7d537c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8c6b1782daf8c00b3b3d3a7d13b5ffa00adeeba2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695899"
---
# <a name="sap-bw-source-editor-connection-manager-page"></a><span data-ttu-id="0cc1b-102">Éditeur de source SAP BW (page Gestionnaire de connexions)</span><span class="sxs-lookup"><span data-stu-id="0cc1b-102">SAP BW Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="0cc1b-103">Utilisez la page **Gestionnaire de connexions** de **l’Éditeur de source SAP BW** pour sélectionner le gestionnaire de connexions SAP BW pour la source SAP BW.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-103">Use the **Connection Manager** page of the **SAP BW Source Editor** to select the SAP BW connection manager for the SAP BW source.</span></span> <span data-ttu-id="0cc1b-104">Sur cette page, sélectionnez également le mode d'exécution et les paramètres pour extraire les données du système SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-104">On this page, you also select the execution mode and the parameters for extracting the data from the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="0cc1b-105">Pour en savoir plus sur le composant source SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 pour SAP BW, consultez [SAP BW Source](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="0cc1b-105">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0cc1b-106">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="0cc1b-107">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0cc1b-108">Vous devez disposer d'une licence SAP supplémentaire pour extraire des données à partir de SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-108">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="0cc1b-109">Vérifiez auprès de SAP.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-109">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="0cc1b-110">**Pour ouvrir la page Gestionnaire de connexions**</span><span class="sxs-lookup"><span data-stu-id="0cc1b-110">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="0cc1b-111">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui contient la source SAP BW.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="0cc1b-112">Sous l’onglet **Flux de données** , double-cliquez sur la source SAP BW.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-112">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="0cc1b-113">Dans l' **Éditeur de source SAP BW**, cliquez sur **Gestionnaire de connexions** pour ouvrir la page **Gestionnaire de connexions** de l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-113">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="0cc1b-114">Options statiques</span><span class="sxs-lookup"><span data-stu-id="0cc1b-114">Static Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0cc1b-115">Si vous ne connaissez pas toutes les valeurs requises pour configurer la source, adressez-vous à votre administrateur SAP.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-115">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="0cc1b-116">**Gestionnaire de connexions SAP BW**</span><span class="sxs-lookup"><span data-stu-id="0cc1b-116">**SAP BW connection manager**</span></span>  
 <span data-ttu-id="0cc1b-117">Sélectionnez un gestionnaire de connexions existant dans la liste ou créez une nouvelle connexion en cliquant sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-117">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="0cc1b-118">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="0cc1b-118">**New**</span></span>  
 <span data-ttu-id="0cc1b-119">Créez un gestionnaire de connexions à l’aide de la boîte de dialogue **Gestionnaire de connexions SAP BW** .</span><span class="sxs-lookup"><span data-stu-id="0cc1b-119">Create a new connection manager by using the **SAP BW Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="0cc1b-120">Pour plus d’informations sur cette boîte de dialogue, consultez [Éditeur du Gestionnaire de connexions SAP BW](../sap-bw-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="0cc1b-120">For more information about this dialog box, see [SAP BW Connection Manager Editor](../sap-bw-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="0cc1b-121">**Destination OHS**</span><span class="sxs-lookup"><span data-stu-id="0cc1b-121">**OHS destination**</span></span>  
 <span data-ttu-id="0cc1b-122">Sélectionnez la destination OHS (Open Hub Service) à utiliser pour extraire des données de la source.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-122">Select the Open Hub Service (OHS) destination to use to extract data from the source.</span></span>  
  
 <span data-ttu-id="0cc1b-123">**Mode d'exécution**</span><span class="sxs-lookup"><span data-stu-id="0cc1b-123">**Execution mode**</span></span>  
 <span data-ttu-id="0cc1b-124">Spécifiez la méthode d'extraction des données de la source.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-124">Specify the method for extracting data from the source.</span></span>  
  
|<span data-ttu-id="0cc1b-125">Option</span><span class="sxs-lookup"><span data-stu-id="0cc1b-125">Option</span></span>|<span data-ttu-id="0cc1b-126">Description</span><span class="sxs-lookup"><span data-stu-id="0cc1b-126">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="0cc1b-127">**P - Déclencher une chaîne de processus**</span><span class="sxs-lookup"><span data-stu-id="0cc1b-127">**P - Trigger Process Chain**</span></span>|<span data-ttu-id="0cc1b-128">Déclenchez une chaîne de processus.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-128">Trigger a process chain.</span></span> <span data-ttu-id="0cc1b-129">Dans ce cas, le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] démarre le processus d'extraction.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-129">In this case, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package starts the extraction process.</span></span>|  
|<span data-ttu-id="0cc1b-130">**A - Attendre la notification**</span><span class="sxs-lookup"><span data-stu-id="0cc1b-130">**W - Wait for Notify**</span></span>|<span data-ttu-id="0cc1b-131">Attendez la notification du système SAP Netweaver BW pour démarrer l'extraction des données.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-131">Wait for notification from the SAP Netweaver BW system to begin extracting the data.</span></span> <span data-ttu-id="0cc1b-132">Dans ce cas, le système SAP Netweaver BW démarre le processus d'extraction.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-132">In this case, the SAP Netweaver BW system starts the extraction process.</span></span>|  
|<span data-ttu-id="0cc1b-133">**E - Extraire uniquement**</span><span class="sxs-lookup"><span data-stu-id="0cc1b-133">**E - Extract Only**</span></span>|<span data-ttu-id="0cc1b-134">Récupérez les données associées à un ID de demande particulier.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-134">Retrieve the data that is associated with a particular Request ID.</span></span> <span data-ttu-id="0cc1b-135">Dans ce cas, le système SAP Netweaver BW a déjà extrait les données dans une table interne et le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] se contente de lire les données.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-135">In this case, the SAP Netweaver BW system has already extracted the data into an internal table, and the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package just reads the data.</span></span>|  
  
 <span data-ttu-id="0cc1b-136">**Préversion**</span><span class="sxs-lookup"><span data-stu-id="0cc1b-136">**Preview**</span></span>  
 <span data-ttu-id="0cc1b-137">Ouvrez la boîte de dialogue **Aperçu** dans laquelle vous pouvez afficher un aperçu des résultats.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-137">Open the **Preview** dialog box in which you can preview results.</span></span> <span data-ttu-id="0cc1b-138">Pour plus d’informations, consultez [Aperçu](preview.md).</span><span class="sxs-lookup"><span data-stu-id="0cc1b-138">For more information, see [Preview](preview.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0cc1b-139">L’option **Aperçu** , disponible dans page **Gestionnaire de connexions** de l’Éditeur de source SAP BW, extrait réellement des données.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-139">The **Preview** option, that is available on the **Connection Manager** page of the SAP BW Source Editor, actually extracts data.</span></span> <span data-ttu-id="0cc1b-140">Si vous avez configuré le système SAP Netweaver BW pour extraire uniquement les données qui ont été modifiées depuis l'extraction précédente, la sélection d' **Aperçu** exclura les données de l'aperçu de l'extraction suivante.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-140">If you have configured SAP Netweaver BW to extract only data that has changed since the previous extraction, selecting **Preview** will exclude the previewed data from the next extraction.</span></span>  
  
 <span data-ttu-id="0cc1b-141">Quand vous cliquez sur **Aperçu**, vous ouvrez également la boîte de dialogue **Journal des requêtes** .</span><span class="sxs-lookup"><span data-stu-id="0cc1b-141">When you click **Preview**, you also open the **Request Log** dialog box.</span></span> <span data-ttu-id="0cc1b-142">Vous pouvez utiliser cette boîte de dialogue pour afficher les événements qui sont journalisés lors de la demande qui est effectuée au système SAP Netweaver BW pour les exemples de données.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-142">You can use this dialog box to view the events that are logged during the request that is made to the SAP Netweaver BW system for sample data.</span></span> <span data-ttu-id="0cc1b-143">Pour plus d’informations, consultez [Journal des requêtes](request-log.md).</span><span class="sxs-lookup"><span data-stu-id="0cc1b-143">For more information, see [Request Log](request-log.md).</span></span>  
  
## <a name="execution-mode-dynamic-options"></a><span data-ttu-id="0cc1b-144">Options dynamiques du mode d'exécution</span><span class="sxs-lookup"><span data-stu-id="0cc1b-144">Execution Mode Dynamic Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0cc1b-145">Si vous ne connaissez pas toutes les valeurs requises pour configurer la source, adressez-vous à votre administrateur SAP.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-145">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
### <a name="execution-mode--p---trigger-process-chain"></a><span data-ttu-id="0cc1b-146">Mode d'exécution = P - Déclencher une chaîne de processus</span><span class="sxs-lookup"><span data-stu-id="0cc1b-146">Execution Mode = P - Trigger Process Chain</span></span>  
  
#### <a name="rfc-destination-options"></a><span data-ttu-id="0cc1b-147">Options de la destination RFC</span><span class="sxs-lookup"><span data-stu-id="0cc1b-147">RFC Destination Options</span></span>  
 <span data-ttu-id="0cc1b-148">Vous n'avez pas à connaître ni à entrer ces valeurs à l'avance.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-148">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="0cc1b-149">Utilisez le bouton **Rechercher** pour rechercher et sélectionner la destination RFC appropriée.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-149">Use the **Look up** button to find and select the appropriate RFC destination.</span></span> <span data-ttu-id="0cc1b-150">Après avoir sélectionné une destination RFC, le composant entre les valeurs appropriées pour ces options.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-150">After you select an RFC destination, the component enters the appropriate values for these options.</span></span>  
  
 <span data-ttu-id="0cc1b-151">**Hôte de passerelle**</span><span class="sxs-lookup"><span data-stu-id="0cc1b-151">**Gateway host**</span></span>  
 <span data-ttu-id="0cc1b-152">Entrez le nom du serveur ou l'adresse IP de l'hôte de passerelle.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-152">Enter the server name or IP address of the gateway host.</span></span> <span data-ttu-id="0cc1b-153">Généralement, le nom ou l'adresse IP est identique au serveur d'applications SAP.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-153">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="0cc1b-154">**Service de passerelle**</span><span class="sxs-lookup"><span data-stu-id="0cc1b-154">**Gateway service**</span></span>  
 <span data-ttu-id="0cc1b-155">Entrez le nom du service de passerelle, au format `sapgwNN` , où `NN` est le numéro du système.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-155">Enter the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="0cc1b-156">**ID de programme**</span><span class="sxs-lookup"><span data-stu-id="0cc1b-156">**Program ID**</span></span>  
 <span data-ttu-id="0cc1b-157">Entrez l'ID du programme qui est associé à la destination RFC.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-157">Enter the Program ID that is associated with the RFC destination.</span></span>  
  
 <span data-ttu-id="0cc1b-158">**Rechercher**</span><span class="sxs-lookup"><span data-stu-id="0cc1b-158">**Look up**</span></span>  
 <span data-ttu-id="0cc1b-159">Recherchez la destination RFC à l’aide de la boîte de dialogue **Rechercher la destination RFC** .</span><span class="sxs-lookup"><span data-stu-id="0cc1b-159">Look up the RFC destination by using the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="0cc1b-160">Pour plus d'informations sur cette boîte de dialogue, consultez [Look Up RFC Destination](look-up-rfc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="0cc1b-160">For more information about this dialog box, see [Look Up RFC Destination](look-up-rfc-destination.md).</span></span>  
  
#### <a name="process-chain-options"></a><span data-ttu-id="0cc1b-161">Options de chaîne de processus</span><span class="sxs-lookup"><span data-stu-id="0cc1b-161">Process Chain Options</span></span>  
 <span data-ttu-id="0cc1b-162">Vous n'avez pas à connaître ni à entrer ces valeurs à l'avance.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-162">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="0cc1b-163">Utilisez le bouton **Rechercher** pour rechercher et sélectionner la chaîne de processus appropriée.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-163">Use the **Look up** button to find and select the appropriate process chain.</span></span> <span data-ttu-id="0cc1b-164">Après avoir sélectionné une chaîne de processus, le composant entre la valeur appropriée pour l'option.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-164">After you select a process chain, the component enters the appropriate value for the option.</span></span>  
  
 <span data-ttu-id="0cc1b-165">**Chaîne de processus**</span><span class="sxs-lookup"><span data-stu-id="0cc1b-165">**Process chain**</span></span>  
 <span data-ttu-id="0cc1b-166">Entrez le nom de la chaîne de processus à déclencher par la source.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-166">Enter the name of the process chain to be triggered by the source.</span></span>  
  
 <span data-ttu-id="0cc1b-167">**Rechercher**</span><span class="sxs-lookup"><span data-stu-id="0cc1b-167">**Look up**</span></span>  
 <span data-ttu-id="0cc1b-168">Recherchez la chaîne de processus à l’aide de la boîte de dialogue **Rechercher la chaîne de processus** .</span><span class="sxs-lookup"><span data-stu-id="0cc1b-168">Look up the process chain by using the **Look Up Process Chain** dialog box.</span></span> <span data-ttu-id="0cc1b-169">Pour plus d’informations sur cette boîte de dialogue, consultez [Rechercher la chaîne de processus](look-up-process-chain.md).</span><span class="sxs-lookup"><span data-stu-id="0cc1b-169">For more information about this dialog box, see [Look Up Process Chain](look-up-process-chain.md).</span></span>  
  
### <a name="execution-mode--w---wait-for-notify"></a><span data-ttu-id="0cc1b-170">Mode d'exécution = A - Attendre la notification</span><span class="sxs-lookup"><span data-stu-id="0cc1b-170">Execution Mode = W - Wait for Notify</span></span>  
  
#### <a name="rfc-destination-options"></a><span data-ttu-id="0cc1b-171">Options de la destination RFC</span><span class="sxs-lookup"><span data-stu-id="0cc1b-171">RFC Destination Options</span></span>  
 <span data-ttu-id="0cc1b-172">Vous n'avez pas à connaître ni à entrer ces valeurs à l'avance.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-172">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="0cc1b-173">Utilisez le bouton **Rechercher** pour rechercher et sélectionner la destination RFC appropriée.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-173">Use the **Look up** button to find and select the appropriate RFC destination.</span></span> <span data-ttu-id="0cc1b-174">Une fois que vous avez sélectionné une destination RFC, le composant entre les valeurs appropriées pour les options.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-174">After you select an RFC destination, the component enters the appropriate values for the options.</span></span>  
  
 <span data-ttu-id="0cc1b-175">**Hôte de passerelle**</span><span class="sxs-lookup"><span data-stu-id="0cc1b-175">**Gateway host**</span></span>  
 <span data-ttu-id="0cc1b-176">Entrez le nom du serveur ou l'adresse IP de l'hôte de passerelle.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-176">Enter the server name or IP address of the gateway host.</span></span> <span data-ttu-id="0cc1b-177">Généralement, le nom ou l'adresse IP est identique au serveur d'applications SAP.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-177">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="0cc1b-178">**Service de passerelle**</span><span class="sxs-lookup"><span data-stu-id="0cc1b-178">**Gateway service**</span></span>  
 <span data-ttu-id="0cc1b-179">Entrez le nom du service de passerelle, au format `sapgwNN` , où `NN` est le numéro du système.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-179">Enter the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="0cc1b-180">**ID de programme**</span><span class="sxs-lookup"><span data-stu-id="0cc1b-180">**Program ID**</span></span>  
 <span data-ttu-id="0cc1b-181">Entrez l'ID du programme qui est associé à la destination RFC.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-181">Enter the Program ID that is associated with the RFC destination.</span></span>  
  
 <span data-ttu-id="0cc1b-182">**Rechercher**</span><span class="sxs-lookup"><span data-stu-id="0cc1b-182">**Look up**</span></span>  
 <span data-ttu-id="0cc1b-183">Recherchez la destination RFC à l’aide de la boîte de dialogue **Rechercher la destination RFC** .</span><span class="sxs-lookup"><span data-stu-id="0cc1b-183">Look up the RFC destination by using the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="0cc1b-184">Pour plus d'informations sur cette boîte de dialogue, consultez [Look Up RFC Destination](look-up-rfc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="0cc1b-184">For more information about this dialog box, see [Look Up RFC Destination](look-up-rfc-destination.md).</span></span>  
  
### <a name="execution-mode--e---extract-only"></a><span data-ttu-id="0cc1b-185">Mode d'exécution - E = Extraire uniquement</span><span class="sxs-lookup"><span data-stu-id="0cc1b-185">Execution Mode = E - Extract Only</span></span>  
 <span data-ttu-id="0cc1b-186">**ID de la demande**</span><span class="sxs-lookup"><span data-stu-id="0cc1b-186">**Request ID**</span></span>  
 <span data-ttu-id="0cc1b-187">Entrez l'ID de demande qui est associé à l'extraction.</span><span class="sxs-lookup"><span data-stu-id="0cc1b-187">Enter the Request ID that is associated with the extraction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cc1b-188">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0cc1b-188">See Also</span></span>  
 <span data-ttu-id="0cc1b-189">[Éditeur de source SAP BW &#40;page Colonnes&#41;](sap-bw-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="0cc1b-189">[SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="0cc1b-190">[Éditeur de source SAP BW &#40;page Sortie d’erreur&#41;](sap-bw-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="0cc1b-190">[SAP BW Source Editor &#40;Error Output Page&#41;](sap-bw-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="0cc1b-191">[Éditeur de source SAP BW &#40;page Avancé&#41;](sap-bw-source-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="0cc1b-191">[SAP BW Source Editor &#40;Advanced Page&#41;](sap-bw-source-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="0cc1b-192">Aide (F1) sur Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="0cc1b-192">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
