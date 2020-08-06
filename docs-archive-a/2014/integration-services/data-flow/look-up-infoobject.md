---
title: Rechercher un InfoObject | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e7f4c132-a5ec-49d8-a964-45775432731f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1616b4fcb368afc9e3f1157a3fc2511d4a7e8cce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700079"
---
# <a name="look-up-infoobject"></a><span data-ttu-id="27810-102">Rechercher un InfoObject</span><span class="sxs-lookup"><span data-stu-id="27810-102">Look Up InfoObject</span></span>
  <span data-ttu-id="27810-103">Utilisez la boîte de dialogue **Rechercher un InfoObject** pour rechercher un InfoObject qui est défini dans le système SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="27810-103">Use the **Look Up InfoObject** dialog box to look up an InfoObject that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="27810-104">Lorsque la liste d'InfoObjects disponibles apparaît, sélectionnez l'InfoObject de votre choix. La destination SAP BW remplira les options associées à l'aide des valeurs requises.</span><span class="sxs-lookup"><span data-stu-id="27810-104">When the list of available InfoObjects appears, select the InfoObject that you want, and the SAP BW destination will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="27810-105">La destination SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 pour SAP BW utilise la boîte de dialogue **Rechercher un InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="27810-105">The SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW uses the **Look Up InfoObject** dialog box.</span></span> <span data-ttu-id="27810-106">Pour en savoir plus sur la destination SAP BW, consultez [Destination SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="27810-106">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="27810-107">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="27810-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="27810-108">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="27810-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="27810-109">**Pour ouvrir la boîte de dialogue Rechercher un InfoObject**</span><span class="sxs-lookup"><span data-stu-id="27810-109">**To open the Look Up InfoObject dialog box**</span></span>  
  
1.  <span data-ttu-id="27810-110">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui contient la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="27810-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="27810-111">Sous l’onglet **Flux de données** , double-cliquez sur la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="27810-111">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="27810-112">Dans l' **Éditeur de destination SAP BW**, cliquez sur **Gestionnaire de connexions** pour ouvrir la page **Gestionnaire de connexions** de l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="27810-112">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="27810-113">Sur la page **Gestionnaire de connexions** , dans la zone de groupe **Créer des objets SAP BW** , sélectionnez l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="27810-113">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select one of the following options:</span></span>  
  
    1.  <span data-ttu-id="27810-114">Sélectionnez **InfoCube**.</span><span class="sxs-lookup"><span data-stu-id="27810-114">Select **InfoCube**.</span></span> <span data-ttu-id="27810-115">Cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="27810-115">Then, click **Create**.</span></span> <span data-ttu-id="27810-116">Dans la boîte de dialogue **Créer un InfoCube pour les données de transaction** , cliquez sur **Rechercher** dans la colonne **IObject** pour l'une des lignes de la liste.</span><span class="sxs-lookup"><span data-stu-id="27810-116">In the **Create InfoCube for Transaction Data** dialog box, click **Search** in the **IObject** column for one of the rows in the list.</span></span> <span data-ttu-id="27810-117">Chaque ligne représente une colonne dans le flux de données du package.</span><span class="sxs-lookup"><span data-stu-id="27810-117">Each row represents a column in the data flow of the package.</span></span>  
  
    2.  <span data-ttu-id="27810-118">Sélectionnez **InfoSource**.</span><span class="sxs-lookup"><span data-stu-id="27810-118">Select **InfoSource**.</span></span> <span data-ttu-id="27810-119">Cliquez ensuite sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="27810-119">Then click **Create**.</span></span> <span data-ttu-id="27810-120">Dans la boîte de dialogue **Créer un InfoSource** , sélectionnez **Données de transaction**.</span><span class="sxs-lookup"><span data-stu-id="27810-120">In the **Create InfoSource** dialog box, select **Transaction data**.</span></span> <span data-ttu-id="27810-121">Dans la boîte de dialogue **Créer un InfoSource pour les données de transaction** , cliquez sur **Rechercher** dans la colonne **IObject** pour l'une des lignes de la liste.</span><span class="sxs-lookup"><span data-stu-id="27810-121">In the **Create InfoSource for Transaction Data** dialog box, click **Search** in the **IObject** column for one of the rows in the list.</span></span> <span data-ttu-id="27810-122">Chaque ligne représente une colonne dans le flux de données du package.</span><span class="sxs-lookup"><span data-stu-id="27810-122">Each row represents a column in the data flow of the package.</span></span>  
  
    3.  <span data-ttu-id="27810-123">Sélectionnez **InfoSource**.</span><span class="sxs-lookup"><span data-stu-id="27810-123">Select **InfoSource**.</span></span> <span data-ttu-id="27810-124">Cliquez ensuite sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="27810-124">Then click **Create**.</span></span> <span data-ttu-id="27810-125">Dans la boîte de dialogue **Créer un InfoSource** , sélectionnez **Données maîtres**.</span><span class="sxs-lookup"><span data-stu-id="27810-125">In the **Create InfoSource** dialog box, select **Master data**.</span></span> <span data-ttu-id="27810-126">Dans la boîte de dialogue **Créer un InfoSource pour les données maîtres** , cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="27810-126">In the **Create InfoSource for Master Data** dialog box, click **Look up**.</span></span>  
  
 <span data-ttu-id="27810-127">Vous pouvez également ouvrir la boîte de dialogue **Rechercher un InfoObject** en cliquant sur **Ajouter** dans la section **Attributs** de la boîte de dialogue **Créer un nouvel InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="27810-127">You can also open the **Look Up InfoObject** dialog box by clicking **Add** in the **Attributes** section of the **Create New InfoObject** dialog box.</span></span>  
  
## <a name="lookup-options"></a><span data-ttu-id="27810-128">Options de recherche</span><span class="sxs-lookup"><span data-stu-id="27810-128">Lookup Options</span></span>  
 <span data-ttu-id="27810-129">Dans les zones de texte du champ de recherche, vous pouvez filtrer les résultats en utilisant le caractère générique astérisque (\*), ou en utilisant une chaîne partielle conjointement avec le caractère générique astérisque.</span><span class="sxs-lookup"><span data-stu-id="27810-129">In the lookup field text boxes, you can filter results by using the asterisk wildcard character (\*), or by using a partial string in combination with the asterisk wildcard character.</span></span> <span data-ttu-id="27810-130">Cependant, si vous laissez un champ de recherche vide, le processus de recherche mettra uniquement en correspondance les chaînes vides de ce champ.</span><span class="sxs-lookup"><span data-stu-id="27810-130">However, if you leave a lookup field empty, the lookup process will only match empty strings in that field.</span></span>  
  
 <span data-ttu-id="27810-131">**Caractéristiques**</span><span class="sxs-lookup"><span data-stu-id="27810-131">**Characteristics**</span></span>  
 <span data-ttu-id="27810-132">Recherchez des InfoObjects qui représentent des caractéristiques.</span><span class="sxs-lookup"><span data-stu-id="27810-132">Look up InfoObjects that represent characteristics.</span></span>  
  
 <span data-ttu-id="27810-133">**Unités**</span><span class="sxs-lookup"><span data-stu-id="27810-133">**Units**</span></span>  
 <span data-ttu-id="27810-134">Recherchez des InfoObjects qui représentent des unités.</span><span class="sxs-lookup"><span data-stu-id="27810-134">Look up InfoObjects that represent units.</span></span>  
  
 <span data-ttu-id="27810-135">**Chiffres clés**</span><span class="sxs-lookup"><span data-stu-id="27810-135">**Key figures**</span></span>  
 <span data-ttu-id="27810-136">Recherchez des InfoObjects qui représentent des chiffres clés.</span><span class="sxs-lookup"><span data-stu-id="27810-136">Look up InfoObjects that represent key figures.</span></span>  
  
 <span data-ttu-id="27810-137">**Caractéristiques de temps**</span><span class="sxs-lookup"><span data-stu-id="27810-137">**Time characteristics**</span></span>  
 <span data-ttu-id="27810-138">Recherchez des InfoObjects qui représentent des caractéristiques de temps.</span><span class="sxs-lookup"><span data-stu-id="27810-138">Look up InfoObjects that represent time characteristics.</span></span>  
  
 <span data-ttu-id="27810-139">**Nom**</span><span class="sxs-lookup"><span data-stu-id="27810-139">**Name**</span></span>  
 <span data-ttu-id="27810-140">Entrez le nom de l'InfoObject à rechercher, ou un nom partiel avec le caractère générique astérisque (\*).</span><span class="sxs-lookup"><span data-stu-id="27810-140">Enter the name of the InfoObject that you want to look up, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="27810-141">Sinon, utilisez le caractère générique astérisque seul pour inclure tous les InfoObjects.</span><span class="sxs-lookup"><span data-stu-id="27810-141">Or, use the asterisk wildcard character alone to include all InfoObjects.</span></span>  
  
 <span data-ttu-id="27810-142">**Description**</span><span class="sxs-lookup"><span data-stu-id="27810-142">**Description**</span></span>  
 <span data-ttu-id="27810-143">Entrez la description, ou une description partielle avec le caractère générique astérisque (\*).</span><span class="sxs-lookup"><span data-stu-id="27810-143">Enter the description, or a partial description with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="27810-144">Sinon, utilisez le caractère générique astérisque seul pour inclure tous les InfoObjects, quelle que soit la description.</span><span class="sxs-lookup"><span data-stu-id="27810-144">Or, use the asterisk wildcard character alone to include all InfoObjects regardless of description.</span></span>  
  
 <span data-ttu-id="27810-145">**Rechercher**</span><span class="sxs-lookup"><span data-stu-id="27810-145">**Look up**</span></span>  
 <span data-ttu-id="27810-146">Recherchez les InfoObjects correspondants qui sont définis dans le système SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="27810-146">Look up matching InfoObjects that are defined in the SAP Netweaver BW system.</span></span>  
  
## <a name="lookup-results"></a><span data-ttu-id="27810-147">Résultats de la recherche</span><span class="sxs-lookup"><span data-stu-id="27810-147">Lookup Results</span></span>  
 <span data-ttu-id="27810-148">Après avoir cliqué sur le bouton Rechercher, une liste des InfoObjects du système SAP Netweaver BW apparaît dans un tableau avec les en-têtes de colonnes suivants.</span><span class="sxs-lookup"><span data-stu-id="27810-148">After you click the Look up button, a list of the InfoObjects in the SAP Netweaver BW system appears in a table with the following column headings.</span></span>  
  
 <span data-ttu-id="27810-149">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="27810-149">**InfoObject**</span></span>  
 <span data-ttu-id="27810-150">Affiche le nom de l'InfoObject qui est défini dans le système SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="27810-150">Displays the name of the InfoObject that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="27810-151">**Texte (court)**</span><span class="sxs-lookup"><span data-stu-id="27810-151">**Text (short)**</span></span>  
 <span data-ttu-id="27810-152">Affiche le texte court associé à l'InfoObject.</span><span class="sxs-lookup"><span data-stu-id="27810-152">Displays the short text that is associated with the InfoObject.</span></span>  
  
 <span data-ttu-id="27810-153">Lorsque la liste d'InfoObjects disponibles apparaît, sélectionnez l'InfoObject de votre choix. La destination remplira les options associées à l'aide des valeurs requises.</span><span class="sxs-lookup"><span data-stu-id="27810-153">When the list of available InfoObjects appears, select the InfoObject that you want, and the destination will populate the associated options with the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27810-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="27810-154">See Also</span></span>  
 <span data-ttu-id="27810-155">[Créer un InfoCube pour les données de transaction](create-infocube-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="27810-155">[Create InfoCube for Transaction Data](create-infocube-for-transaction-data.md) </span></span>  
 <span data-ttu-id="27810-156">[Créer un InfoSource](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="27810-156">[Create InfoSource](create-infosource.md) </span></span>  
 <span data-ttu-id="27810-157">[Créer un InfoSource pour les données de transaction](create-infosource-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="27810-157">[Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md) </span></span>  
 <span data-ttu-id="27810-158">[Créer un InfoSource pour les données maîtres](create-infosource-for-master-data.md) </span><span class="sxs-lookup"><span data-stu-id="27810-158">[Create InfoSource for Master Data](create-infosource-for-master-data.md) </span></span>  
 <span data-ttu-id="27810-159">[Créer un nouvel InfoObject](create-new-infoobject.md) </span><span class="sxs-lookup"><span data-stu-id="27810-159">[Create New InfoObject](create-new-infoobject.md) </span></span>  
 <span data-ttu-id="27810-160">[Éditeur de destination SAP BW &#40;page Gestionnaire de connexions&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="27810-160">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="27810-161">Aide (F1) sur Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="27810-161">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
