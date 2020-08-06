---
title: Source SAP BW | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 749afb64-3567-4dc9-8431-783d650c25db
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d64af5e0d881e3b7dbbd2cc4e005aa3dbef3c43a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613072"
---
# <a name="sap-bw-source"></a><span data-ttu-id="37b27-102">Source SAP BW</span><span class="sxs-lookup"><span data-stu-id="37b27-102">SAP BW Source</span></span>
  <span data-ttu-id="37b27-103">La source SAP BW est le composant source de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 pour SAP BW.</span><span class="sxs-lookup"><span data-stu-id="37b27-103">The SAP BW source is the source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="37b27-104">Ainsi, la source SAP BW extrait des données d'un système SAP Netweaver BW version 7 et met ces données à la disposition du flux de données dans un package [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37b27-104">Thus, the SAP BW source extracts data from an SAP Netweaver BW version 7 system and makes this data available to the data flow in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span>  
  
 <span data-ttu-id="37b27-105">Cette source comporte une sortie et une sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="37b27-105">This source has one output and one error output.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="37b27-106">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="37b27-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="37b27-107">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="37b27-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="37b27-108">Vous devez disposer d'une licence SAP supplémentaire pour extraire des données à partir de SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="37b27-108">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="37b27-109">Vérifiez auprès de SAP.</span><span class="sxs-lookup"><span data-stu-id="37b27-109">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="37b27-110">Pour utiliser la source SAP BW, vous devez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="37b27-110">To use the SAP BW source, you have to do the following tasks:</span></span>  
  
-   [<span data-ttu-id="37b27-111">Préparer les objets SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="37b27-111">Prepare the SAP Netweaver BW objects</span></span>](#bkmk_Prepare_Objects)  
  
-   [<span data-ttu-id="37b27-112">Établir une connexion au système SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="37b27-112">Connect to the SAP Netweaver BW system</span></span>](#bkmk_Connect_Database)  
  
-   [<span data-ttu-id="37b27-113">Configurer la source SAP BW</span><span class="sxs-lookup"><span data-stu-id="37b27-113">Configure the SAP BW source</span></span>](#bkmk_Configure_Source)  
  
##  <a name="preparing-the-sap-netweaver-bw-objects-that-the-source-requires"></a><a name="bkmk_Prepare_Objects"></a> <span data-ttu-id="37b27-114">Préparation des objets SAP Netweaver BW requis par la source</span><span class="sxs-lookup"><span data-stu-id="37b27-114">Preparing the SAP Netweaver BW Objects That the Source Requires</span></span>  
 <span data-ttu-id="37b27-115">La source SAP BW nécessite la présence de certains objets dans le système SAP Netweaver BW pour que la source puisse fonctionner.</span><span class="sxs-lookup"><span data-stu-id="37b27-115">The SAP BW source requires that certain objects are in the SAP Netweaver BW system before the source can function.</span></span> <span data-ttu-id="37b27-116">Si ces objets n'existent pas, vous devez suivre ces étapes pour les créer et les configurer dans le système SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="37b27-116">If these objects do not already exist, you have to follow these steps to create and configure these objects in the SAP Netweaver BW system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="37b27-117">Pour plus d'informations sur ces objets et ces étapes de configuration, consultez la documentation de SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="37b27-117">For additional details about these objects and these configuration steps, see the SAP Netweaver BW documentation.</span></span>  
  
1.  <span data-ttu-id="37b27-118">Connectez-vous à SAP Netweaver BW via l'interface GUI SAP, entrez le code de transaction SM59, puis créez une destination RFC :</span><span class="sxs-lookup"><span data-stu-id="37b27-118">Log on to SAP Netweaver BW through the SAP GUI, enter transaction code SM59, and create an RFC destination:</span></span>  
  
    1.  <span data-ttu-id="37b27-119">Pour **Type de connexion**, sélectionnez **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="37b27-119">For **Connection Type**, select **TCP/IP**.</span></span>  
  
    2.  <span data-ttu-id="37b27-120">Pour **Type d'activation**, sélectionnez **Programme de serveur inscrit**.</span><span class="sxs-lookup"><span data-stu-id="37b27-120">For **Activation Type**, select **Registered Server Program**.</span></span>  
  
    3.  <span data-ttu-id="37b27-121">Pour **Type de communication avec le système cible**, sélectionnez **Non-Unicode (Paramètres MDMP inactifs)** .</span><span class="sxs-lookup"><span data-stu-id="37b27-121">For **Communication Type with Target System**, select **Non-Unicode (Inactive MDMP Settings)**.</span></span>  
  
    4.  <span data-ttu-id="37b27-122">Attribuez un ID de programme approprié.</span><span class="sxs-lookup"><span data-stu-id="37b27-122">Assign an appropriate Program ID.</span></span>  
  
2.  <span data-ttu-id="37b27-123">Créer une destination Open Hub :</span><span class="sxs-lookup"><span data-stu-id="37b27-123">Create an Open Hub Destination:</span></span>  
  
    1.  <span data-ttu-id="37b27-124">Accédez à l’atelier de l’administrateur (code de transaction RSA1) puis, dans le volet gauche, sélectionnez **Destination Open Hub**.</span><span class="sxs-lookup"><span data-stu-id="37b27-124">Go to the Administrator Workbench (transaction code RSA1) and, in the left pane, select **Open Hub Destination**.</span></span>  
  
    2.  <span data-ttu-id="37b27-125">Dans le volet central, cliquez avec le bouton droit sur un InfoArea, puis sélectionnez **Créer une destination Open Hub**.</span><span class="sxs-lookup"><span data-stu-id="37b27-125">In the middle pane, right-click an InfoArea, and then select **"Create Open Hub Destination"**.</span></span>  
  
    3.  <span data-ttu-id="37b27-126">Pour **Type de destination**, sélectionnez **Outil tiers**, puis entrez la destination RFC créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="37b27-126">For **Destination Type**, select **"Third Party Tool"**, and then enter the previously created RFC Destination.</span></span>  
  
    4.  <span data-ttu-id="37b27-127">Enregistrez et activez la nouvelle destination Open Hub.</span><span class="sxs-lookup"><span data-stu-id="37b27-127">Save and activate the new Open Hub Destination.</span></span>  
  
3.  <span data-ttu-id="37b27-128">Créer un processus de transfert de données (DTP) :</span><span class="sxs-lookup"><span data-stu-id="37b27-128">Create a Data Transfer Process (DTP):</span></span>  
  
    1.  <span data-ttu-id="37b27-129">Dans le volet central de l’InfoArea, cliquez avec le bouton droit sur la destination créée précédemment, puis sélectionnez **Créer le processus de transfert de données**.</span><span class="sxs-lookup"><span data-stu-id="37b27-129">In the middle pane of the InfoArea, right-click the previously created destination, and then select **"Create data transfer process"**.</span></span>  
  
    2.  <span data-ttu-id="37b27-130">Configurez, enregistrez et activez le processus DTP.</span><span class="sxs-lookup"><span data-stu-id="37b27-130">Configure, save, and activate the DTP.</span></span>  
  
    3.  <span data-ttu-id="37b27-131">Dans le menu, cliquez sur **Atteindre**, puis cliquez sur **Paramètres pour le gestionnaire de lots**.</span><span class="sxs-lookup"><span data-stu-id="37b27-131">On the menu, click **Goto**, and then click **Settings for Batch Manager**.</span></span>  
  
    4.  <span data-ttu-id="37b27-132">Mettez à jour **Nombre de processus** à 1 pour le traitement en série.</span><span class="sxs-lookup"><span data-stu-id="37b27-132">Update **Number of processes** to 1 for serial processing.</span></span>  
  
4.  <span data-ttu-id="37b27-133">Créer une chaîne de processus :</span><span class="sxs-lookup"><span data-stu-id="37b27-133">Create a process chain:</span></span>  
  
    1.  <span data-ttu-id="37b27-134">Lors de la configuration de la chaîne de processus, sélectionnez **Démarrer à l'aide de la chaîne de métadonnées ou de l'API** comme **Options de planification** du **Processus de démarrage**, puis ajoutez le processus DTP créé précédemment comme nœud suivant.</span><span class="sxs-lookup"><span data-stu-id="37b27-134">When configuring the process chain, select the **Start Using Metadata Chain or API** as the **Scheduling Options** of the **Start Process**, and then add the previously created DTP as the subsequent node.</span></span>  
  
    2.  <span data-ttu-id="37b27-135">Enregistrez et activez la chaîne de processus.</span><span class="sxs-lookup"><span data-stu-id="37b27-135">Save and activate the process chain.</span></span>  
  
     <span data-ttu-id="37b27-136">La source SAP BW peut appeler la chaîne de processus pour activer le processus de transfert de données.</span><span class="sxs-lookup"><span data-stu-id="37b27-136">The SAP BW source can call the process chain to activate the data transfer process.</span></span>  
  
##  <a name="connecting-to-the-sap-netweaver-bw-system"></a><a name="bkmk_Connect_Database"></a> <span data-ttu-id="37b27-137">Connexion au système SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="37b27-137">Connecting to the SAP Netweaver BW System</span></span>  
 <span data-ttu-id="37b27-138">Pour la connexion au système SAP Netweaver BW version 7, la source SAP BW utilise le gestionnaire de connexions SAP BW qui fait partie du package [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 pour SAP BW.</span><span class="sxs-lookup"><span data-stu-id="37b27-138">To connect to the SAP Netweaver BW version 7 system, the SAP BW source uses the SAP BW connection manager that is part of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW package.</span></span> <span data-ttu-id="37b27-139">Le gestionnaire de connexions SAP BW est le seul gestionnaire de connexions [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que la source SAP BW peut utiliser.</span><span class="sxs-lookup"><span data-stu-id="37b27-139">The SAP BW connection manager is the only [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] connection manager that the SAP BW source can use.</span></span>  
  
 <span data-ttu-id="37b27-140">Pour plus d'informations sur le gestionnaire de connexions SAP BW, consultez [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="37b27-140">For more information about the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
##  <a name="configuring-the-sap-bw-source"></a><a name="bkmk_Configure_Source"></a> <span data-ttu-id="37b27-141">Configuration de la source SAP BW</span><span class="sxs-lookup"><span data-stu-id="37b27-141">Configuring the SAP BW Source</span></span>  
 <span data-ttu-id="37b27-142">Vous pouvez configurer la source SAP BW comme suit :</span><span class="sxs-lookup"><span data-stu-id="37b27-142">You can configure the SAP BW source in the following ways:</span></span>  
  
-   <span data-ttu-id="37b27-143">Recherchez et sélectionnez la destination OHS (Open Hub Service) à utiliser pour extraire des données.</span><span class="sxs-lookup"><span data-stu-id="37b27-143">Look up and select the Open Hub Service (OHS) destination to use to extract data.</span></span>  
  
-   <span data-ttu-id="37b27-144">Sélectionnez l'une des méthodes suivantes pour extraire des données :</span><span class="sxs-lookup"><span data-stu-id="37b27-144">Select one of the following methods for extracting data:</span></span>  
  
    -   <span data-ttu-id="37b27-145">Déclenchez une chaîne de processus.</span><span class="sxs-lookup"><span data-stu-id="37b27-145">Trigger a process chain.</span></span> <span data-ttu-id="37b27-146">Dans ce cas, le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] démarre le processus d'extraction.</span><span class="sxs-lookup"><span data-stu-id="37b27-146">In this case, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package starts the extraction process.</span></span>  
  
    -   <span data-ttu-id="37b27-147">Attendez la notification du système SAP Netweaver BW pour démarrer une extraction.</span><span class="sxs-lookup"><span data-stu-id="37b27-147">Wait for notification from the SAP Netweaver BW system to begin an extraction.</span></span> <span data-ttu-id="37b27-148">Dans ce cas, le système SAP Netweaver BW démarre le processus d'extraction.</span><span class="sxs-lookup"><span data-stu-id="37b27-148">In this case, the SAP Netweaver BW system starts the extraction process.</span></span>  
  
    -   <span data-ttu-id="37b27-149">Récupérez les données associées à un ID de demande particulier.</span><span class="sxs-lookup"><span data-stu-id="37b27-149">Retrieve the data that is associated with a particular Request ID.</span></span> <span data-ttu-id="37b27-150">Dans ce cas, le système SAP Netweaver BW a déjà extrait les données dans une table interne et le package à [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] se contente de lire les données.</span><span class="sxs-lookup"><span data-stu-id="37b27-150">In this case, the SAP Netweaver BW system has already extracted the data to an internal table, and the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package just reads the data.</span></span>  
  
-   <span data-ttu-id="37b27-151">Selon la méthode sélectionnée pour extraire des données, fournissez les informations supplémentaires suivantes :</span><span class="sxs-lookup"><span data-stu-id="37b27-151">Depending on the method selected for extracting data, provide the following additional information:</span></span>  
  
    -   <span data-ttu-id="37b27-152">Pour l’option **P - Déclencher une chaîne de processus** , fournissez le nom d’hôte de passerelle, le nom du service de passerelle, l’ID de programme pour la destination RFC et le nom de la chaîne de processus.</span><span class="sxs-lookup"><span data-stu-id="37b27-152">For the **P - Trigger Process Chain** option, provide the gateway host name, gateway service name, program ID for the RFC destination, and name of the process chain.</span></span>  
  
    -   <span data-ttu-id="37b27-153">Pour l’option **A - Attendre la notification** , fournissez le nom d’hôte de passerelle, le nom du serveur de passerelle et l’ID de programme pour la destination RFC.</span><span class="sxs-lookup"><span data-stu-id="37b27-153">For the **W - Wait for Notify** option, provide the gateway host name, the gateway server name, and the program ID for the RFC destination.</span></span> <span data-ttu-id="37b27-154">Vous pouvez également spécifier le délai d'attente (en secondes).</span><span class="sxs-lookup"><span data-stu-id="37b27-154">You can also specify the timeout (in seconds).</span></span> <span data-ttu-id="37b27-155">Le délai d'attente représente la durée maximale pendant laquelle la source attendra une notification.</span><span class="sxs-lookup"><span data-stu-id="37b27-155">The timeout is the maximum period of time that the source will wait to be notified.</span></span>  
  
    -   <span data-ttu-id="37b27-156">Pour l’option **E - Extraire uniquement** , fournissez l’ID de demande.</span><span class="sxs-lookup"><span data-stu-id="37b27-156">For the **E - Extract Only** option, provide the Request ID.</span></span>  
  
-   <span data-ttu-id="37b27-157">Spécifiez les règles pour la conversion de chaînes.</span><span class="sxs-lookup"><span data-stu-id="37b27-157">Specify rules for string conversion.</span></span> <span data-ttu-id="37b27-158">(Par exemple, convertissez toutes les chaînes, selon que le système SAP Netweaver BW est Unicode ou non, ou convertissez toutes les chaînes en `varchar` ou `nvarchar`).</span><span class="sxs-lookup"><span data-stu-id="37b27-158">(For example, convert all strings depending on whether the SAP Netweaver BW system is Unicode or not, or convert all strings to `varchar` or `nvarchar`).</span></span>  
  
-   <span data-ttu-id="37b27-159">Utilisez les options que vous avez sélectionnées pour afficher un aperçu des données à extraire.</span><span class="sxs-lookup"><span data-stu-id="37b27-159">Use the options that you have selected to preview the data to be extracted.</span></span>  
  
 <span data-ttu-id="37b27-160">Vous pouvez également activer la journalisation des appels de fonction RFC par la source.</span><span class="sxs-lookup"><span data-stu-id="37b27-160">You can also enable logging of RFC function calls by the source.</span></span> <span data-ttu-id="37b27-161">(Cette journalisation diffère de la journalisation facultative que vous pouvez activer sur les packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .) Vous activez la journalisation des appels de fonction RFC lorsque vous configurez le gestionnaire de connexions SAP BW que la source utilisera.</span><span class="sxs-lookup"><span data-stu-id="37b27-161">(This logging is separate from the optional logging that you can enable on [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.) You enable logging of RFC function calls when you configure the SAP BW connection manager that the source will use.</span></span> <span data-ttu-id="37b27-162">Pour plus d'informations sur la configuration du gestionnaire de connexions SAP BW, consultez [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="37b27-162">For more information about how to configure the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
 <span data-ttu-id="37b27-163">Si vous ne connaissez pas toutes les valeurs requises pour configurer la source, adressez-vous à votre administrateur SAP.</span><span class="sxs-lookup"><span data-stu-id="37b27-163">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="37b27-164">Pour obtenir la procédure pas à pas qui montre comment configurer et utiliser le gestionnaire de connexions, la source et la destination SAP BW, consultez le livre blanc [Utilisation de SQL Server 2008 Integration Services avec SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span><span class="sxs-lookup"><span data-stu-id="37b27-164">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server 2008 Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span></span> <span data-ttu-id="37b27-165">Ce livre blanc explique également comment configurer les objets nécessaires dans SAP BW.</span><span class="sxs-lookup"><span data-stu-id="37b27-165">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
### <a name="using-the-ssis-designer-to-configure-the-source"></a><span data-ttu-id="37b27-166">Utilisation du concepteur SSIS pour configurer la source</span><span class="sxs-lookup"><span data-stu-id="37b27-166">Using the SSIS Designer to Configure the Source</span></span>  
 <span data-ttu-id="37b27-167">Pour plus d'informations sur les propriétés de la source SAP BW que vous pouvez définir dans le Concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="37b27-167">For more information about the properties of the SAP BW source that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="37b27-168">Éditeur de source SAP BW &#40;page Gestionnaire de connexions&#41;</span><span class="sxs-lookup"><span data-stu-id="37b27-168">SAP BW Source Editor &#40;Connection Manager Page&#41;</span></span>](sap-bw-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="37b27-169">Éditeur de source SAP BW &#40;page Colonnes&#41;</span><span class="sxs-lookup"><span data-stu-id="37b27-169">SAP BW Source Editor &#40;Columns Page&#41;</span></span>](sap-bw-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="37b27-170">Éditeur de source SAP BW &#40;page Sortie d’erreur&#41;</span><span class="sxs-lookup"><span data-stu-id="37b27-170">SAP BW Source Editor &#40;Error Output Page&#41;</span></span>](sap-bw-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="37b27-171">Éditeur de source SAP BW &#40;page Avancé&#41;</span><span class="sxs-lookup"><span data-stu-id="37b27-171">SAP BW Source Editor &#40;Advanced Page&#41;</span></span>](sap-bw-source-editor-advanced-page.md)  
  
 <span data-ttu-id="37b27-172">Pendant que vous configurez la source SAP BW, vous pouvez également utiliser différentes boîtes de dialogue pour rechercher des objets SAP Netweaver BW ou pour afficher un aperçu des données sources.</span><span class="sxs-lookup"><span data-stu-id="37b27-172">While you are configuring the SAP BW source, you can also use various dialog boxes to look up SAP Netweaver BW objects or to preview the source data.</span></span> <span data-ttu-id="37b27-173">Pour plus d'informations sur ces boîtes de dialogue, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="37b27-173">For more information about these dialog boxes, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="37b27-174">Rechercher la destination RFC</span><span class="sxs-lookup"><span data-stu-id="37b27-174">Look Up RFC Destination</span></span>](look-up-rfc-destination.md)  
  
-   [<span data-ttu-id="37b27-175">Rechercher la chaîne de processus</span><span class="sxs-lookup"><span data-stu-id="37b27-175">Look Up Process Chain</span></span>](look-up-process-chain.md)  
  
-   [<span data-ttu-id="37b27-176">Journal des requêtes</span><span class="sxs-lookup"><span data-stu-id="37b27-176">Request Log</span></span>](request-log.md)  
  
-   [<span data-ttu-id="37b27-177">Préversion</span><span class="sxs-lookup"><span data-stu-id="37b27-177">Preview</span></span>](preview.md)  
  
## <a name="see-also"></a><span data-ttu-id="37b27-178">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="37b27-178">See Also</span></span>  
 [<span data-ttu-id="37b27-179">Composants Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="37b27-179">Microsoft Connector 1.1 for SAP BW Components</span></span>](../microsoft-connector-for-sap-bw-components.md)  
  
  
