---
title: Éditeur de destination SAP BW (page Gestionnaire de connexions) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 04ae38f8-5287-45a3-826a-8aac5dd15a91
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0dd628f1a0fec09490e0d3720610d1232882ed92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695911"
---
# <a name="sap-bw-destination-editor-connection-manager-page"></a><span data-ttu-id="b46d4-102">Éditeur de destination SAP BW (page Gestionnaire de connexions)</span><span class="sxs-lookup"><span data-stu-id="b46d4-102">SAP BW Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="b46d4-103">Utilisez la page **Gestionnaire de connexions** de l' **Éditeur de destination SAP BW** pour sélectionner le gestionnaire de connexions SAP BW qui sera utilisé par la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="b46d4-103">Use the **Connection Manager** page of the **SAP BW Destination Editor** to select the SAP BW connection manager that the SAP BW destination will use.</span></span> <span data-ttu-id="b46d4-104">Sur cette page, sélectionnez également les paramètres pour charger les données dans le système SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="b46d4-104">On this page, you also select the parameters for loading the data into the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="b46d4-105">Pour en savoir plus sur la destination SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 pour SAP BW, consultez [Destination SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="b46d4-105">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b46d4-106">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="b46d4-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="b46d4-107">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="b46d4-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="b46d4-108">**Pour ouvrir la page Gestionnaire de connexions**</span><span class="sxs-lookup"><span data-stu-id="b46d4-108">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="b46d4-109">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui contient la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="b46d4-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="b46d4-110">Sous l’onglet **Flux de données** , double-cliquez sur la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="b46d4-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="b46d4-111">Dans l' **Éditeur de destination SAP BW**, cliquez sur **Gestionnaire de connexions** pour ouvrir la page **Gestionnaire de connexions** de l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="b46d4-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b46d4-112">Options</span><span class="sxs-lookup"><span data-stu-id="b46d4-112">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b46d4-113">Si vous ne connaissez pas toutes les valeurs requises pour configurer la destination, adressez-vous à votre administrateur SAP.</span><span class="sxs-lookup"><span data-stu-id="b46d4-113">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="b46d4-114">**Gestionnaire de connexions SAP BW**</span><span class="sxs-lookup"><span data-stu-id="b46d4-114">**SAP BW connection manager**</span></span>  
 <span data-ttu-id="b46d4-115">Sélectionnez un gestionnaire de connexions existant dans la liste ou créez une nouvelle connexion en cliquant sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b46d4-115">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="b46d4-116">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="b46d4-116">**New**</span></span>  
 <span data-ttu-id="b46d4-117">Créez un gestionnaire de connexions à l’aide de la boîte de dialogue **Gestionnaire de connexions SAP BW** .</span><span class="sxs-lookup"><span data-stu-id="b46d4-117">Create a new connection manager by using the **SAP BW Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="b46d4-118">**Test de charge**</span><span class="sxs-lookup"><span data-stu-id="b46d4-118">**Test Load**</span></span>  
 <span data-ttu-id="b46d4-119">Réalisez un test du processus de chargement qui utilise les paramètres que vous avez sélectionnés et qui charge zéro ligne.</span><span class="sxs-lookup"><span data-stu-id="b46d4-119">Perform a test of the loading process that uses the settings that you have selected and loads zero rows.</span></span>  
  
### <a name="infopackageinfosource-options"></a><span data-ttu-id="b46d4-120">Options InfoPackage/InfoSource</span><span class="sxs-lookup"><span data-stu-id="b46d4-120">InfoPackage/InfoSource Options</span></span>  
 <span data-ttu-id="b46d4-121">Vous n'avez pas à connaître ni à entrer ces valeurs à l'avance.</span><span class="sxs-lookup"><span data-stu-id="b46d4-121">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="b46d4-122">Utilisez le bouton **Rechercher** pour rechercher et sélectionner l'InfoPackage approprié.</span><span class="sxs-lookup"><span data-stu-id="b46d4-122">Use the **Look up** button to find and select the appropriate InfoPackage.</span></span> <span data-ttu-id="b46d4-123">Après avoir sélectionné un InfoPackage, le composant entre les valeurs appropriées pour ces options.</span><span class="sxs-lookup"><span data-stu-id="b46d4-123">After you select an InfoPackage, the component enters the appropriate values for these options.</span></span>  
  
 <span data-ttu-id="b46d4-124">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="b46d4-124">**InfoPackage**</span></span>  
 <span data-ttu-id="b46d4-125">Entrez le nom de l'InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="b46d4-125">Enter the name of the InfoPackage.</span></span>  
  
 <span data-ttu-id="b46d4-126">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="b46d4-126">**InfoSource**</span></span>  
 <span data-ttu-id="b46d4-127">Entrez le nom de l'InfoSource.</span><span class="sxs-lookup"><span data-stu-id="b46d4-127">Enter the name of the InfoSource.</span></span>  
  
 <span data-ttu-id="b46d4-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="b46d4-128">**Type**</span></span>  
 <span data-ttu-id="b46d4-129">Entrez le caractère unique qui identifie le type de l'InfoSource.</span><span class="sxs-lookup"><span data-stu-id="b46d4-129">Enter the single-character that identifies the type of the InfoSource.</span></span> <span data-ttu-id="b46d4-130">Le tableau suivant répertorie les valeurs à un seul caractère acceptables.</span><span class="sxs-lookup"><span data-stu-id="b46d4-130">The following table lists the acceptable single-character values.</span></span>  
  
|<span data-ttu-id="b46d4-131">Valeur</span><span class="sxs-lookup"><span data-stu-id="b46d4-131">Value</span></span>|<span data-ttu-id="b46d4-132">Description</span><span class="sxs-lookup"><span data-stu-id="b46d4-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b46d4-133">**D**</span><span class="sxs-lookup"><span data-stu-id="b46d4-133">**D**</span></span>|<span data-ttu-id="b46d4-134">Données de transaction</span><span class="sxs-lookup"><span data-stu-id="b46d4-134">Transaction data</span></span>|  
|<span data-ttu-id="b46d4-135">**M**</span><span class="sxs-lookup"><span data-stu-id="b46d4-135">**M**</span></span>|<span data-ttu-id="b46d4-136">Données maîtres</span><span class="sxs-lookup"><span data-stu-id="b46d4-136">Master data</span></span>|  
|<span data-ttu-id="b46d4-137">**T**</span><span class="sxs-lookup"><span data-stu-id="b46d4-137">**T**</span></span>|<span data-ttu-id="b46d4-138">Textes</span><span class="sxs-lookup"><span data-stu-id="b46d4-138">Texts</span></span>|  
|<span data-ttu-id="b46d4-139">**H**</span><span class="sxs-lookup"><span data-stu-id="b46d4-139">**H**</span></span>|<span data-ttu-id="b46d4-140">Données de hiérarchie</span><span class="sxs-lookup"><span data-stu-id="b46d4-140">Hierarchy data</span></span>|  
  
 <span data-ttu-id="b46d4-141">**Système logique**</span><span class="sxs-lookup"><span data-stu-id="b46d4-141">**Logical system**</span></span>  
 <span data-ttu-id="b46d4-142">Entrez le nom du système logique qui est associé à l'InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="b46d4-142">Enter the name of the logical system that is associated with the InfoPackage.</span></span>  
  
 <span data-ttu-id="b46d4-143">**Rechercher**</span><span class="sxs-lookup"><span data-stu-id="b46d4-143">**Look up**</span></span>  
 <span data-ttu-id="b46d4-144">Recherchez l’InfoPackage à l’aide de la boîte de dialogue **Rechercher un InfoPackage** .</span><span class="sxs-lookup"><span data-stu-id="b46d4-144">Look up the InfoPackage by using the **Look Up InfoPackage** dialog box.</span></span> <span data-ttu-id="b46d4-145">Pour plus d'informations sur cette boîte de dialogue, consultez [Look Up InfoPackage](look-up-infopackage.md).</span><span class="sxs-lookup"><span data-stu-id="b46d4-145">For more information about this dialog box, see [Look Up InfoPackage](look-up-infopackage.md).</span></span>  
  
### <a name="rfc-destination-options"></a><span data-ttu-id="b46d4-146">Options de la destination RFC</span><span class="sxs-lookup"><span data-stu-id="b46d4-146">RFC Destination Options</span></span>  
 <span data-ttu-id="b46d4-147">Vous n'avez pas à connaître ni à entrer ces valeurs à l'avance.</span><span class="sxs-lookup"><span data-stu-id="b46d4-147">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="b46d4-148">Utilisez le bouton **Rechercher** pour rechercher et sélectionner la destination RFC appropriée.</span><span class="sxs-lookup"><span data-stu-id="b46d4-148">Use the **Look up** button to find and select the appropriate RFC destination.</span></span> <span data-ttu-id="b46d4-149">Après avoir sélectionné une destination RFC, le composant entre les valeurs appropriées pour ces options.</span><span class="sxs-lookup"><span data-stu-id="b46d4-149">After you select an RFC destination, the component enters the appropriate values for these options.</span></span>  
  
 <span data-ttu-id="b46d4-150">**Hôte de passerelle**</span><span class="sxs-lookup"><span data-stu-id="b46d4-150">**Gateway host**</span></span>  
 <span data-ttu-id="b46d4-151">Entrez le nom du serveur ou l'adresse IP de l'hôte de passerelle.</span><span class="sxs-lookup"><span data-stu-id="b46d4-151">Enter the server name or IP address of the gateway host.</span></span> <span data-ttu-id="b46d4-152">Généralement, le nom ou l'adresse IP est identique au serveur d'applications SAP.</span><span class="sxs-lookup"><span data-stu-id="b46d4-152">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="b46d4-153">**Service de passerelle**</span><span class="sxs-lookup"><span data-stu-id="b46d4-153">**Gateway service**</span></span>  
 <span data-ttu-id="b46d4-154">Entrez le nom du service de passerelle, au format `sapgwNN` , où `NN` est le numéro du système.</span><span class="sxs-lookup"><span data-stu-id="b46d4-154">Enter the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="b46d4-155">**ID de programme**</span><span class="sxs-lookup"><span data-stu-id="b46d4-155">**Program ID**</span></span>  
 <span data-ttu-id="b46d4-156">Entrez l'ID du programme qui est associé à la destination RFC.</span><span class="sxs-lookup"><span data-stu-id="b46d4-156">Enter the Program ID that is associated with the RFC destination.</span></span>  
  
 <span data-ttu-id="b46d4-157">**Rechercher**</span><span class="sxs-lookup"><span data-stu-id="b46d4-157">**Look up**</span></span>  
 <span data-ttu-id="b46d4-158">Recherchez la destination RFC à l’aide de la boîte de dialogue **Rechercher la destination RFC** .</span><span class="sxs-lookup"><span data-stu-id="b46d4-158">Look up the RFC destination by using the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="b46d4-159">Pour plus d'informations sur cette boîte de dialogue, consultez [Look Up RFC Destination](look-up-rfc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="b46d4-159">For more information about this dialog box, see [Look Up RFC Destination](look-up-rfc-destination.md).</span></span>  
  
### <a name="create-sap-bw-objects-options"></a><span data-ttu-id="b46d4-160">Options de création d'objets SAP BW</span><span class="sxs-lookup"><span data-stu-id="b46d4-160">Create SAP BW Objects Options</span></span>  
 <span data-ttu-id="b46d4-161">**Sélectionner type d'objet**</span><span class="sxs-lookup"><span data-stu-id="b46d4-161">**Select object type**</span></span>  
 <span data-ttu-id="b46d4-162">Sélectionnez le type d'objet SAP Netweaver BW que vous souhaitez créer.</span><span class="sxs-lookup"><span data-stu-id="b46d4-162">Select the type of SAP Netweaver BW object that you want to create.</span></span> <span data-ttu-id="b46d4-163">Vous pouvez sélectionner l'un des types suivants :</span><span class="sxs-lookup"><span data-stu-id="b46d4-163">You can select one of the following types:</span></span>  
  
-   <span data-ttu-id="b46d4-164">InfoObject</span><span class="sxs-lookup"><span data-stu-id="b46d4-164">InfoObject</span></span>  
  
-   <span data-ttu-id="b46d4-165">InfoCube</span><span class="sxs-lookup"><span data-stu-id="b46d4-165">InfoCube</span></span>  
  
-   <span data-ttu-id="b46d4-166">InfoSource</span><span class="sxs-lookup"><span data-stu-id="b46d4-166">InfoSource</span></span>  
  
-   <span data-ttu-id="b46d4-167">InfoPackage</span><span class="sxs-lookup"><span data-stu-id="b46d4-167">InfoPackage</span></span>  
  
 <span data-ttu-id="b46d4-168">**Créer**</span><span class="sxs-lookup"><span data-stu-id="b46d4-168">**Create**</span></span>  
 <span data-ttu-id="b46d4-169">Créez le type sélectionné d'objet SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="b46d4-169">Create the selected type of SAP Netweaver BW object.</span></span>  
  
|<span data-ttu-id="b46d4-170">Type d'objet</span><span class="sxs-lookup"><span data-stu-id="b46d4-170">Object Type</span></span>|<span data-ttu-id="b46d4-171">Résultats</span><span class="sxs-lookup"><span data-stu-id="b46d4-171">Result</span></span>|  
|-----------------|------------|  
|<span data-ttu-id="b46d4-172">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="b46d4-172">**InfoObject**</span></span>|<span data-ttu-id="b46d4-173">Créez un nouvel InfoObject à l'aide de la boîte de dialogue **Créer un nouvel InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="b46d4-173">Create a new InfoObject by using the **Create New InfoObject** dialog box.</span></span> <span data-ttu-id="b46d4-174">Pour plus d'informations sur cette boîte de dialogue, consultez [Create New InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="b46d4-174">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>|  
|<span data-ttu-id="b46d4-175">**InfoCube**</span><span class="sxs-lookup"><span data-stu-id="b46d4-175">**InfoCube**</span></span>|<span data-ttu-id="b46d4-176">Créez un nouvel InfoCube à l'aide de la boîte de dialogue **Créer un InfoCube pour les données de transaction** .</span><span class="sxs-lookup"><span data-stu-id="b46d4-176">Create a new InfoCube by using the **Create InfoCube for Transaction Data** dialog box.</span></span> <span data-ttu-id="b46d4-177">Pour plus d'informations sur cette boîte de dialogue, consultez [Create InfoCube for Transaction Data](create-infocube-for-transaction-data.md).</span><span class="sxs-lookup"><span data-stu-id="b46d4-177">For more information about this dialog box, see [Create InfoCube for Transaction Data](create-infocube-for-transaction-data.md).</span></span>|  
|<span data-ttu-id="b46d4-178">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="b46d4-178">**InfoSource**</span></span>|<span data-ttu-id="b46d4-179">Créez un nouvel InfoSource à l'aide de la boîte de dialogue **Créer un InfoSource** , puis avec **Créer un InfoSource pour les données de transaction** ou la boîte de dialogue **Créer un InfoSource pour les données maîtres** .</span><span class="sxs-lookup"><span data-stu-id="b46d4-179">Create a new InfoSource by using the **Create InfoSource** dialog box, and then by using the **Create InfoSource for Transaction Data** or the **Create InfoSource for Master Data** dialog box.</span></span> <span data-ttu-id="b46d4-180">Pour plus d'informations sur ces boîtes de dialogue, consultez [Create InfoSource](create-infosource.md), [Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md) et [Create InfoSource for Master Data](create-infosource-for-master-data.md).</span><span class="sxs-lookup"><span data-stu-id="b46d4-180">For more information about these dialog boxes, see [Create InfoSource](create-infosource.md), [Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md) and [Create InfoSource for Master Data](create-infosource-for-master-data.md).</span></span>|  
|<span data-ttu-id="b46d4-181">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="b46d4-181">**InfoPackage**</span></span>|<span data-ttu-id="b46d4-182">Créez un nouvel InfoPackage à l'aide de la boîte de dialogue **Créer un InfoPackage** .</span><span class="sxs-lookup"><span data-stu-id="b46d4-182">Create a new InfoPackage by using the **Create InfoPackage** dialog box.</span></span> <span data-ttu-id="b46d4-183">Pour plus d'informations sur cette boîte de dialogue, consultez [Create InfoPackage](create-infopackage.md).</span><span class="sxs-lookup"><span data-stu-id="b46d4-183">For more information about this dialog box, see [Create InfoPackage](create-infopackage.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b46d4-184">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b46d4-184">See Also</span></span>  
 <span data-ttu-id="b46d4-185">[Éditeur de destination SAP BW &#40;page Mappages&#41;](sap-bw-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="b46d4-185">[SAP BW Destination Editor &#40;Mappings Page&#41;](sap-bw-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="b46d4-186">[Éditeur de destination SAP BW &#40;page Sortie d’erreur&#41;](sap-bw-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="b46d4-186">[SAP BW Destination Editor &#40;Error Output Page&#41;](sap-bw-destination-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="b46d4-187">[Éditeur de destination SAP BW &#40;page Avancé&#41;](sap-bw-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="b46d4-187">[SAP BW Destination Editor &#40;Advanced Page&#41;](sap-bw-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="b46d4-188">Aide (F1) sur Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="b46d4-188">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
