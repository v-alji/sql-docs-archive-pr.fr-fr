---
title: Rechercher un Infopackage| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7c0cb7a4-cd07-44cc-85cb-eb1ad91f85fd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1e45477e8faeed07faa114850e10a3bc4bbcf170
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700074"
---
# <a name="look-up-infopackage"></a><span data-ttu-id="692e8-102">Rechercher un InfoPackage</span><span class="sxs-lookup"><span data-stu-id="692e8-102">Look Up InfoPackage</span></span>
  <span data-ttu-id="692e8-103">Utilisez la boîte de dialogue **Rechercher un InfoPackage** pour rechercher un InfoPackage qui est défini dans le système SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="692e8-103">Use the **Look Up InfoPackage** dialog box to look up an InfoPackage that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="692e8-104">Lorsque la liste d'InfoPackages apparaît, sélectionnez l'InfoPackage de votre choix. La destination remplira les options associées à l'aide des valeurs requises.</span><span class="sxs-lookup"><span data-stu-id="692e8-104">When the list of InfoPackages appears, select the InfoPackage that you want, and the destination will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="692e8-105">La destination SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 pour SAP BW utilise la boîte de dialogue **Rechercher la chaîne de processus** .</span><span class="sxs-lookup"><span data-stu-id="692e8-105">The SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW uses the **Look Up Process Chain** dialog box.</span></span> <span data-ttu-id="692e8-106">Pour en savoir plus sur la destination SAP BW, consultez [Destination SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="692e8-106">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="692e8-107">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="692e8-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="692e8-108">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="692e8-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="692e8-109">**Pour ouvrir la boîte de dialogue Rechercher un InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="692e8-109">**To open the Look Up InfoPackage dialog box**</span></span>  
  
1.  <span data-ttu-id="692e8-110">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui contient la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="692e8-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="692e8-111">Sous l’onglet **Flux de données** , double-cliquez sur la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="692e8-111">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="692e8-112">Dans l' **Éditeur de destination SAP BW**, cliquez sur **Gestionnaire de connexions** pour ouvrir la page **Gestionnaire de connexions** de l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="692e8-112">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="692e8-113">Dans la page **Gestionnaire de connexions** , dans la zone de groupe **InfoPackage/InfoSource** , cliquez sur **Rechercher** pour afficher la boîte de dialogue **Rechercher un InfoPackage** .</span><span class="sxs-lookup"><span data-stu-id="692e8-113">On the **Connection Manager** page, in the **InfoPackage/InfoSource** group box, click **Look up** to display the **Look Up InfoPackage** dialog box.</span></span>  
  
## <a name="lookup-options"></a><span data-ttu-id="692e8-114">Options de recherche</span><span class="sxs-lookup"><span data-stu-id="692e8-114">Lookup Options</span></span>  
 <span data-ttu-id="692e8-115">Dans les champs de recherche, vous pouvez filtrer les résultats à l'aide du caractère générique astérisque (\*), ou en utilisant une chaîne partielle conjointement avec le caractère générique astérisque.</span><span class="sxs-lookup"><span data-stu-id="692e8-115">In the lookup fields, you can filter results by using the asterisk wildcard character (\*), or by using a partial string in combination with the asterisk wildcard character.</span></span> <span data-ttu-id="692e8-116">Cependant, si vous laissez un champ de recherche vide, l'opération de recherche mettra uniquement en correspondance les chaînes vides de ce champ.</span><span class="sxs-lookup"><span data-stu-id="692e8-116">However, if you leave a lookup field empty, the lookup operation will only match empty strings in that field.</span></span>  
  
 <span data-ttu-id="692e8-117">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="692e8-117">**InfoPackage**</span></span>  
 <span data-ttu-id="692e8-118">Entrez le nom de l'InfoPackage à rechercher, ou un nom partiel avec le caractère générique astérisque (\*).</span><span class="sxs-lookup"><span data-stu-id="692e8-118">Enter the name of the InfoPackage that you want to look up, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="692e8-119">Sinon, utilisez le caractère générique astérisque seul pour inclure tous les InfoPackages.</span><span class="sxs-lookup"><span data-stu-id="692e8-119">Or, use the asterisk wildcard character alone to include all InfoPackages.</span></span>  
  
 <span data-ttu-id="692e8-120">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="692e8-120">**InfoSource**</span></span>  
 <span data-ttu-id="692e8-121">Entrez le nom de l'InfoSource ou un nom partiel avec le caractère générique astérisque (\*).</span><span class="sxs-lookup"><span data-stu-id="692e8-121">Enter the name of the InfoSource, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="692e8-122">Sinon, utilisez le caractère générique astérisque seul pour inclure tous les InfoPackages, indépendamment d'InfoSource.</span><span class="sxs-lookup"><span data-stu-id="692e8-122">Or, use the asterisk wildcard character alone to include all InfoPackages regardless of InfoSource.</span></span>  
  
 <span data-ttu-id="692e8-123">**Système source**</span><span class="sxs-lookup"><span data-stu-id="692e8-123">**Source system**</span></span>  
 <span data-ttu-id="692e8-124">Entrez le nom du système source ou un nom partiel avec le caractère générique astérisque (\*).</span><span class="sxs-lookup"><span data-stu-id="692e8-124">Enter the name of the source system, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="692e8-125">Sinon, utilisez le caractère générique astérisque seul pour inclure tous les InfoPackages, indépendamment des systèmes sources.</span><span class="sxs-lookup"><span data-stu-id="692e8-125">Or, use the asterisk wildcard character alone to include all InfoPackages regardless of source systems.</span></span>  
  
 <span data-ttu-id="692e8-126">**Rechercher**</span><span class="sxs-lookup"><span data-stu-id="692e8-126">**Look up**</span></span>  
 <span data-ttu-id="692e8-127">Recherchez les InfoPackages correspondants qui sont définis dans le système SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="692e8-127">Look up matching InfoPackages that are defined in the SAP Netweaver BW system.</span></span>  
  
## <a name="lookup-results"></a><span data-ttu-id="692e8-128">Résultats de la recherche</span><span class="sxs-lookup"><span data-stu-id="692e8-128">Lookup Results</span></span>  
 <span data-ttu-id="692e8-129">Après avoir cliqué sur le bouton Rechercher, une liste des InfoPackages du système SAP Netweaver BW apparaît dans un tableau avec les en-têtes de colonnes suivants.</span><span class="sxs-lookup"><span data-stu-id="692e8-129">After you click the Look up button, a list of the InfoPackages in the SAP Netweaver BW system appears in a table with the following column headings.</span></span>  
  
 <span data-ttu-id="692e8-130">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="692e8-130">**InfoPackage**</span></span>  
 <span data-ttu-id="692e8-131">Affiche le nom de l'InfoPackage qui est défini dans le système SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="692e8-131">Displays the name of the InfoPackage that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="692e8-132">**Type**</span><span class="sxs-lookup"><span data-stu-id="692e8-132">**Type**</span></span>  
 <span data-ttu-id="692e8-133">Affiche le type de l'InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="692e8-133">Displays the type of the InfoPackage.</span></span> <span data-ttu-id="692e8-134">Le tableau suivant répertorie les valeurs possibles pour le type.</span><span class="sxs-lookup"><span data-stu-id="692e8-134">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="692e8-135">Valeur</span><span class="sxs-lookup"><span data-stu-id="692e8-135">Value</span></span>|<span data-ttu-id="692e8-136">Description</span><span class="sxs-lookup"><span data-stu-id="692e8-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="692e8-137">Trans.</span><span class="sxs-lookup"><span data-stu-id="692e8-137">Trans.</span></span>|<span data-ttu-id="692e8-138">Données de transaction.</span><span class="sxs-lookup"><span data-stu-id="692e8-138">Transaction data.</span></span>|  
|<span data-ttu-id="692e8-139">Attr.</span><span class="sxs-lookup"><span data-stu-id="692e8-139">Attr.</span></span>|<span data-ttu-id="692e8-140">Données d'attribut.</span><span class="sxs-lookup"><span data-stu-id="692e8-140">Attribute data.</span></span>|  
|<span data-ttu-id="692e8-141">Textes</span><span class="sxs-lookup"><span data-stu-id="692e8-141">Texts</span></span>|<span data-ttu-id="692e8-142">Textes.</span><span class="sxs-lookup"><span data-stu-id="692e8-142">Texts.</span></span>|  
  
 <span data-ttu-id="692e8-143">**Description**</span><span class="sxs-lookup"><span data-stu-id="692e8-143">**Description**</span></span>  
 <span data-ttu-id="692e8-144">Affiche la description de l'InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="692e8-144">Displays the description of the InfoPackage.</span></span>  
  
 <span data-ttu-id="692e8-145">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="692e8-145">**InfoSource**</span></span>  
 <span data-ttu-id="692e8-146">Affiche le nom de l'InfoSource, le cas échéant, qui est associé à l'InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="692e8-146">Displays the name of the InfoSource, if any, that is associated with the InfoPackage.</span></span>  
  
 <span data-ttu-id="692e8-147">**Source System**</span><span class="sxs-lookup"><span data-stu-id="692e8-147">**Source System**</span></span>  
 <span data-ttu-id="692e8-148">Affiche le nom du système source.</span><span class="sxs-lookup"><span data-stu-id="692e8-148">Displays the name of the source system.</span></span>  
  
 <span data-ttu-id="692e8-149">Lorsque la liste d'InfoPackages apparaît, sélectionnez l'InfoPackage de votre choix. La destination remplira les options associées à l'aide des valeurs requises.</span><span class="sxs-lookup"><span data-stu-id="692e8-149">When the list of InfoPackages appears, select the InfoPackage that you want, and the destination will populate the associated options with the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="692e8-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="692e8-150">See Also</span></span>  
 <span data-ttu-id="692e8-151">[Éditeur de destination SAP BW &#40;page Gestionnaire de connexions&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="692e8-151">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="692e8-152">Aide (F1) sur Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="692e8-152">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
