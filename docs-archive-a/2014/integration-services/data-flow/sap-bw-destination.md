---
title: Destination SAP BW | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a612ed91-b89b-4173-a0b1-0bce381e1e28
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8a0d7c5b75da89e665dbe60bbd7e29ce74da67db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611935"
---
# <a name="sap-bw-destination"></a><span data-ttu-id="fabd3-102">Destination SAP BW</span><span class="sxs-lookup"><span data-stu-id="fabd3-102">SAP BW Destination</span></span>
  <span data-ttu-id="fabd3-103">La destination SAP BW est le composant de destination de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 pour SAP BW.</span><span class="sxs-lookup"><span data-stu-id="fabd3-103">The SAP BW destination is the destination component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="fabd3-104">Ainsi, la destination SAP BW charge les données du flux de données d'un package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] dans un système SAP Netweaver BW version 7.</span><span class="sxs-lookup"><span data-stu-id="fabd3-104">Thus, the SAP BW destination loads data from the data flow in an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package into an SAP Netweaver BW version 7 system.</span></span>  
  
 <span data-ttu-id="fabd3-105">Cette destination comporte une entrée et une sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="fabd3-105">This destination has one input and one error output.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fabd3-106">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="fabd3-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="fabd3-107">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="fabd3-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="fabd3-108">Pour utiliser la destination SAP BW, vous devez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="fabd3-108">To use the SAP BW destination, you have to do the following tasks:</span></span>  
  
-   [<span data-ttu-id="fabd3-109">Préparer les objets SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="fabd3-109">Prepare the SAP Netweaver BW objects</span></span>](#bkmk_Prepare_Objects)  
  
-   [<span data-ttu-id="fabd3-110">Établir une connexion au système SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="fabd3-110">Connect to the SAP Netweaver BW system</span></span>](#bkmk_Connect_Database)  
  
-   [<span data-ttu-id="fabd3-111">Configurer la destination SAP BW</span><span class="sxs-lookup"><span data-stu-id="fabd3-111">Configure the SAP BW destination</span></span>](#bkmk_Configure_Destination)  
  
##  <a name="preparing-the-sap-netweaver-bw-objects-that-the-destination-requires"></a><a name="bkmk_Prepare_Objects"></a> <span data-ttu-id="fabd3-112">Préparation des objets SAP Netweaver BW requis par la destination</span><span class="sxs-lookup"><span data-stu-id="fabd3-112">Preparing the SAP Netweaver BW Objects That the Destination Requires</span></span>  
 <span data-ttu-id="fabd3-113">La destination SAP BW nécessite la présence de certains objets dans le système SAP Netweaver BW pour que la destination puisse fonctionner.</span><span class="sxs-lookup"><span data-stu-id="fabd3-113">The SAP BW destination requires that certain objects are in the SAP Netweaver BW system before the destination can function.</span></span> <span data-ttu-id="fabd3-114">Si ces objets n'existent pas, vous devez suivre ces étapes pour les créer et les configurer dans le système SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="fabd3-114">If these objects do not already exist, you have to follow these steps to create and configure these objects in the SAP Netweaver BW system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fabd3-115">Pour plus d'informations sur ces objets et ces étapes de configuration, consultez la documentation de SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="fabd3-115">For additional details about these objects and these configuration steps, see the SAP Netweaver BW documentation.</span></span>  
  
1.  <span data-ttu-id="fabd3-116">Créer un nouveau système source :</span><span class="sxs-lookup"><span data-stu-id="fabd3-116">Create a new Source System:</span></span>  
  
    1.  <span data-ttu-id="fabd3-117">Sélectionnez le type **« Interfaces BAPI intermédiaires/tierces »** .</span><span class="sxs-lookup"><span data-stu-id="fabd3-117">Select the type, **"Third Party/Staging BAPIs"**.</span></span>  
  
    2.  <span data-ttu-id="fabd3-118">Pour **Type de communication avec le système cible**, sélectionnez **Non-Unicode (Paramètres MDMP inactifs)** .</span><span class="sxs-lookup"><span data-stu-id="fabd3-118">For **Communication Type with Target System**, select **Non-Unicode (Inactive MDMP Settings)**.</span></span>  
  
    3.  <span data-ttu-id="fabd3-119">Attribuez un ID de programme approprié.</span><span class="sxs-lookup"><span data-stu-id="fabd3-119">Assign an appropriate Program ID.</span></span>  
  
2.  <span data-ttu-id="fabd3-120">Attribuez le système source à un InfoSource.</span><span class="sxs-lookup"><span data-stu-id="fabd3-120">Assign the Source System to an InfoSource.</span></span>  
  
3.  <span data-ttu-id="fabd3-121">Créez un InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="fabd3-121">Create an InfoPackage.</span></span>  
  
     <span data-ttu-id="fabd3-122">L'InfoPackage est l'objet le plus important requis par la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="fabd3-122">The InfoPackage is the most important object that is required by the SAP BW destination.</span></span>  
  
 <span data-ttu-id="fabd3-123">Vous pouvez aussi créer des InfoObjects, des InfoCubes, des InfoSources et des InfoPackages supplémentaires, requis pour prendre en charge le chargement des données dans le système SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="fabd3-123">You can also create additional InfoObjects, InfoCubes, InfoSources, and InfoPackages that are required to support loading data into the SAP Netweaver BW system.</span></span>  
  
##  <a name="connecting-to-the-sap-netweaver-bw-system"></a><a name="bkmk_Connect_Database"></a> <span data-ttu-id="fabd3-124">Connexion au système SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="fabd3-124">Connecting to the SAP Netweaver BW System</span></span>  
 <span data-ttu-id="fabd3-125">Pour la connexion au système SAP Netweaver BW version 7, la destination SAP BW utilise le gestionnaire de connexions SAP BW qui fait partie du package [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 pour SAP BW.</span><span class="sxs-lookup"><span data-stu-id="fabd3-125">To connect to the SAP Netweaver BW version 7 system, the SAP BW destination uses the SAP BW connection manager that is part of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW package.</span></span> <span data-ttu-id="fabd3-126">Le gestionnaire de connexions SAP BW est le seul gestionnaire de connexions [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que la destination SAP BW peut utiliser.</span><span class="sxs-lookup"><span data-stu-id="fabd3-126">The SAP BW connection manager is the only [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] connection manager that the SAP BW destination can use.</span></span>  
  
 <span data-ttu-id="fabd3-127">Pour plus d'informations sur le gestionnaire de connexions SAP BW, consultez [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="fabd3-127">For more information about the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
##  <a name="configuring-the-sap-bw-destination"></a><a name="bkmk_Configure_Destination"></a> <span data-ttu-id="fabd3-128">Configuration de la destination SAP BW</span><span class="sxs-lookup"><span data-stu-id="fabd3-128">Configuring the SAP BW Destination</span></span>  
 <span data-ttu-id="fabd3-129">Vous pouvez configurer la destination SAP BW de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="fabd3-129">You can configure the SAP BW destination in the following ways:</span></span>  
  
-   <span data-ttu-id="fabd3-130">Recherchez et sélectionnez l'InfoPackage à utiliser pour charger les données.</span><span class="sxs-lookup"><span data-stu-id="fabd3-130">Look up and select the InfoPackage to use to load data.</span></span>  
  
-   <span data-ttu-id="fabd3-131">Mappez chaque colonne du flux de données à l'InfoObject approprié dans l'InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="fabd3-131">Map each column in the data flow to the appropriate InfoObject in the InfoPackage.</span></span>  
  
-   <span data-ttu-id="fabd3-132">Spécifiez le nombre de lignes de données qui seront transférées à la fois en configurant la propriété `PackageSize`.</span><span class="sxs-lookup"><span data-stu-id="fabd3-132">Specify how many rows of data will be transferred at a time by configuring the `PackageSize` property.</span></span>  
  
-   <span data-ttu-id="fabd3-133">Choisissez d'attendre la fin du chargement des données par le système SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="fabd3-133">Choose to wait until the loading of data is completed by the SAP Netweaver BW system.</span></span>  
  
-   <span data-ttu-id="fabd3-134">Choisissez de ne pas déclencher l'InfoPackage, mais d'attendre une notification indiquant que le système SAP Netweaver BW a démarré le chargement des données.</span><span class="sxs-lookup"><span data-stu-id="fabd3-134">Choose not to trigger the InfoPackage, but to wait for notification that the SAP Netweaver BW system has started the loading of data.</span></span>  
  
-   <span data-ttu-id="fabd3-135">Déclenchez éventuellement une autre chaîne de processus une fois le chargement des données terminé.</span><span class="sxs-lookup"><span data-stu-id="fabd3-135">Optionally, trigger another process chain after the loading of data is completed.</span></span>  
  
-   <span data-ttu-id="fabd3-136">Créez éventuellement les objets SAP Netweaver BW requis par la destination.</span><span class="sxs-lookup"><span data-stu-id="fabd3-136">Optionally, create the SAP Netweaver BW objects that are required by the destination.</span></span> <span data-ttu-id="fabd3-137">Cela inclut la création d'InfoObjects, d'InfoCubes, d'InfoSources et d'InfoPackages.</span><span class="sxs-lookup"><span data-stu-id="fabd3-137">This includes creating InfoObjects, InfoCubes, InfoSources, and InfoPackages.</span></span>  
  
-   <span data-ttu-id="fabd3-138">Testez le chargement des données avec les options que vous avez sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="fabd3-138">Test the loading of data with the options that you have selected.</span></span>  
  
 <span data-ttu-id="fabd3-139">Vous pouvez également activer la journalisation des appels de fonction RFC par la destination.</span><span class="sxs-lookup"><span data-stu-id="fabd3-139">You can also enable logging of RFC function calls by the destination.</span></span> <span data-ttu-id="fabd3-140">(Cette journalisation diffère de la journalisation facultative que vous pouvez activer sur les packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .) Activez la journalisation des appels de fonction RFC lorsque vous configurez le gestionnaire de connexions SAP BW que la destination utilisera.</span><span class="sxs-lookup"><span data-stu-id="fabd3-140">(This logging is separate from the optional logging that you can enable on [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.) You enable logging of RFC function calls when you configure the SAP BW connection manager that the destination will use.</span></span> <span data-ttu-id="fabd3-141">Pour plus d'informations sur la configuration du gestionnaire de connexions SAP BW, consultez [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="fabd3-141">For more information about how to configure the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
 <span data-ttu-id="fabd3-142">Si vous ne connaissez pas toutes les valeurs requises pour configurer la destination, adressez-vous à votre administrateur SAP.</span><span class="sxs-lookup"><span data-stu-id="fabd3-142">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="fabd3-143">Pour obtenir la procédure pas à pas qui montre comment configurer et utiliser le gestionnaire de connexions, la source et la destination SAP BW, consultez le livre blanc [Utilisation de SQL Server 2008 Integration Services avec SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span><span class="sxs-lookup"><span data-stu-id="fabd3-143">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server 2008 Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span></span> <span data-ttu-id="fabd3-144">Ce livre blanc explique également comment configurer les objets nécessaires dans SAP BW.</span><span class="sxs-lookup"><span data-stu-id="fabd3-144">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
### <a name="using-the-ssis-designer-to-configure-the-destination"></a><span data-ttu-id="fabd3-145">Utilisation du concepteur SSIS pour configurer la destination</span><span class="sxs-lookup"><span data-stu-id="fabd3-145">Using the SSIS Designer to Configure the Destination</span></span>  
 <span data-ttu-id="fabd3-146">Pour plus d'informations sur les propriétés de la destination SAP BW que vous pouvez définir dans le Concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="fabd3-146">For more information about the properties of the SAP BW destination that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="fabd3-147">Éditeur de destination SAP BW &#40;page Gestionnaire de connexions&#41;</span><span class="sxs-lookup"><span data-stu-id="fabd3-147">SAP BW Destination Editor &#40;Connection Manager Page&#41;</span></span>](sap-bw-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="fabd3-148">Éditeur de destination SAP BW &#40;page Mappages&#41;</span><span class="sxs-lookup"><span data-stu-id="fabd3-148">SAP BW Destination Editor &#40;Mappings Page&#41;</span></span>](sap-bw-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="fabd3-149">Éditeur de destination SAP BW &#40;page Sortie d’erreur&#41;</span><span class="sxs-lookup"><span data-stu-id="fabd3-149">SAP BW Destination Editor &#40;Error Output Page&#41;</span></span>](sap-bw-destination-editor-error-output-page.md)  
  
-   [<span data-ttu-id="fabd3-150">Éditeur de destination SAP BW &#40;page Avancé&#41;</span><span class="sxs-lookup"><span data-stu-id="fabd3-150">SAP BW Destination Editor &#40;Advanced Page&#41;</span></span>](sap-bw-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="fabd3-151">Lorsque vous configurez la destination SAP BW, vous pouvez également utiliser différentes boîtes de dialogue pour rechercher ou pour créer des objets SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="fabd3-151">While you are configuring the SAP BW destination, you can also use various dialog boxes to look up or to create SAP Netweaver BW objects.</span></span> <span data-ttu-id="fabd3-152">Pour plus d'informations sur ces boîtes de dialogue, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="fabd3-152">For more information about these dialog boxes, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="fabd3-153">Rechercher un InfoPackage</span><span class="sxs-lookup"><span data-stu-id="fabd3-153">Look Up InfoPackage</span></span>](look-up-infopackage.md)  
  
-   [<span data-ttu-id="fabd3-154">Créer un nouvel InfoObject</span><span class="sxs-lookup"><span data-stu-id="fabd3-154">Create New InfoObject</span></span>](create-new-infoobject.md)  
  
-   [<span data-ttu-id="fabd3-155">Créer un InfoCube pour les données de transaction</span><span class="sxs-lookup"><span data-stu-id="fabd3-155">Create InfoCube for Transaction Data</span></span>](create-infocube-for-transaction-data.md)  
  
-   [<span data-ttu-id="fabd3-156">Rechercher un InfoObject</span><span class="sxs-lookup"><span data-stu-id="fabd3-156">Look Up InfoObject</span></span>](look-up-infoobject.md)  
  
-   [<span data-ttu-id="fabd3-157">Créer un InfoSource</span><span class="sxs-lookup"><span data-stu-id="fabd3-157">Create InfoSource</span></span>](create-infosource.md)  
  
-   [<span data-ttu-id="fabd3-158">Créer un InfoSource pour les données de transaction</span><span class="sxs-lookup"><span data-stu-id="fabd3-158">Create InfoSource for Transaction Data</span></span>](create-infosource-for-transaction-data.md)  
  
-   [<span data-ttu-id="fabd3-159">Créer un InfoSource pour les données maîtres</span><span class="sxs-lookup"><span data-stu-id="fabd3-159">Create InfoSource for Master Data</span></span>](create-infosource-for-master-data.md)  
  
-   [<span data-ttu-id="fabd3-160">Créer un InfoPackage</span><span class="sxs-lookup"><span data-stu-id="fabd3-160">Create InfoPackage</span></span>](create-infopackage.md)  
  
## <a name="see-also"></a><span data-ttu-id="fabd3-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fabd3-161">See Also</span></span>  
 [<span data-ttu-id="fabd3-162">Composants Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="fabd3-162">Microsoft Connector 1.1 for SAP BW Components</span></span>](../microsoft-connector-for-sap-bw-components.md)  
  
  
