---
title: Créer un InfoSource pour les données de transaction | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ab5f23e2-cd4e-4507-83d9-ac5ef721c171
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3e3a60bb93da17e79087982473e92c35fa0856d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695916"
---
# <a name="create-infosource-for-transaction-data"></a><span data-ttu-id="ffcda-102">Créer un InfoSource pour les données de transaction</span><span class="sxs-lookup"><span data-stu-id="ffcda-102">Create InfoSource for Transaction Data</span></span>
  <span data-ttu-id="ffcda-103">Utilisez la boîte de dialogue **Créer un InfoSource pour les données de transaction** pour créer un InfoSource pour les données de transaction dans le système SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="ffcda-103">Use the **Create InfoSource for Transaction Data** dialog box to create a new InfoSource for transaction data in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="ffcda-104">Vous pouvez ouvrir la boîte de dialogue **Créer un InfoSource pour les données de transaction** depuis la page **Gestionnaire de connexions** de **l’Éditeur de destination SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="ffcda-104">You can open the **Create InfoSource for Transaction Data** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="ffcda-105">Pour en savoir plus sur la destination SAP BW, consultez [Destination SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="ffcda-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ffcda-106">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="ffcda-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="ffcda-107">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="ffcda-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="ffcda-108">**Pour ouvrir la boîte de dialogue Créer un InfoSource pour les données de transaction**</span><span class="sxs-lookup"><span data-stu-id="ffcda-108">**To open the Create InfoSource for Transaction Data dialog box**</span></span>  
  
1.  <span data-ttu-id="ffcda-109">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui contient la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="ffcda-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="ffcda-110">Sous l’onglet **Flux de données** , double-cliquez sur la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="ffcda-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="ffcda-111">Dans l' **Éditeur de destination SAP BW**, cliquez sur **Gestionnaire de connexions** pour ouvrir la page **Gestionnaire de connexions** de l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="ffcda-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="ffcda-112">Dans la page **Gestionnaire de connexions** , dans la zone de groupe **Créer des objets SAP BW** , sélectionnez **InfoSource**, puis cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="ffcda-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoSource**, and then click **Create**.</span></span>  
  
5.  <span data-ttu-id="ffcda-113">Dans la boîte de dialogue **Créer un InfoSource** , sélectionnez **Données de transaction**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffcda-113">In the **Create InfoSource** dialog box, select **Transaction data**, and then click **OK**.</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="ffcda-114">Options générales</span><span class="sxs-lookup"><span data-stu-id="ffcda-114">General Options</span></span>  
 <span data-ttu-id="ffcda-115">**Nom de l'InfoSource**</span><span class="sxs-lookup"><span data-stu-id="ffcda-115">**InfoSource name**</span></span>  
 <span data-ttu-id="ffcda-116">Entrez un nom pour le nouvel InfoSource.</span><span class="sxs-lookup"><span data-stu-id="ffcda-116">Enter a name for the new InfoSource.</span></span>  
  
 <span data-ttu-id="ffcda-117">**Brève description**</span><span class="sxs-lookup"><span data-stu-id="ffcda-117">**Short description**</span></span>  
 <span data-ttu-id="ffcda-118">Entrez une brève description pour le nouvel InfoSource.</span><span class="sxs-lookup"><span data-stu-id="ffcda-118">Enter a short description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="ffcda-119">**Description longue**</span><span class="sxs-lookup"><span data-stu-id="ffcda-119">**Long description**</span></span>  
 <span data-ttu-id="ffcda-120">Entrez une longue description pour le nouvel InfoSource.</span><span class="sxs-lookup"><span data-stu-id="ffcda-120">Enter a long description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="ffcda-121">**Système source**</span><span class="sxs-lookup"><span data-stu-id="ffcda-121">**Source system**</span></span>  
 <span data-ttu-id="ffcda-122">Sélectionnez le système source associé à InfoSource.</span><span class="sxs-lookup"><span data-stu-id="ffcda-122">Select the source system associated with the InfoSource.</span></span>  
  
 <span data-ttu-id="ffcda-123">**Enregistrer et activer**</span><span class="sxs-lookup"><span data-stu-id="ffcda-123">**Save & Activate**</span></span>  
 <span data-ttu-id="ffcda-124">Enregistrez et activez le nouvel InfoSource.</span><span class="sxs-lookup"><span data-stu-id="ffcda-124">Save and activate the new InfoSource.</span></span>  
  
## <a name="infosource-transfer-structure-options"></a><span data-ttu-id="ffcda-125">Options de structure de transfert d'InfoSource</span><span class="sxs-lookup"><span data-stu-id="ffcda-125">InfoSource Transfer Structure Options</span></span>  
 <span data-ttu-id="ffcda-126">La structure de transfert d'InfoSource vous permet associer les colonnes de flux de données à des InfoSources.</span><span class="sxs-lookup"><span data-stu-id="ffcda-126">The InfoSource transfer structure lets you associate data flow columns to InfoSources.</span></span>  
  
 <span data-ttu-id="ffcda-127">**PipelineElement**</span><span class="sxs-lookup"><span data-stu-id="ffcda-127">**PipelineElement**</span></span>  
 <span data-ttu-id="ffcda-128">Affiche la colonne dans la sortie du flux de données qui est connectée à la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="ffcda-128">Displays the column in the output of the data flow that is connected to the SAP BW destination.</span></span>  
  
 <span data-ttu-id="ffcda-129">**PipelineDataType**</span><span class="sxs-lookup"><span data-stu-id="ffcda-129">**PipelineDataType**</span></span>  
 <span data-ttu-id="ffcda-130">Affiche le type de données [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] de la colonne du flux de données.</span><span class="sxs-lookup"><span data-stu-id="ffcda-130">Displays the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data type of the data flow column.</span></span>  
  
 <span data-ttu-id="ffcda-131">**Iobject - Rechercher**</span><span class="sxs-lookup"><span data-stu-id="ffcda-131">**Iobject - Search**</span></span>  
 <span data-ttu-id="ffcda-132">Associez un InfoObject existant à la colonne de flux de données dans la ligne actuelle.</span><span class="sxs-lookup"><span data-stu-id="ffcda-132">Associate an existing InfoObject to the data flow column in the current row.</span></span> <span data-ttu-id="ffcda-133">Pour effectuer cette association, cliquez sur **Rechercher**, puis utilisez la boîte de dialogue **Rechercher un InfoObject** pour sélectionner l’InfoObject existant.</span><span class="sxs-lookup"><span data-stu-id="ffcda-133">To make this association, click **Search**, and then use the **Look Up InfoObject** dialog box to select the existing InfoObject.</span></span> <span data-ttu-id="ffcda-134">Pour plus d’informations sur cette boîte de dialogue, consultez [Rechercher un InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="ffcda-134">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="ffcda-135">Après avoir sélectionné un InfoObject existant, le composant remplit les colonnes **InfoObject** et **Type** avec les valeurs sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="ffcda-135">After you select an existing InfoObject, the component populates the **InfoObject** and **Type** columns with the selected values.</span></span>  
  
 <span data-ttu-id="ffcda-136">**Iobject - Nouveau**</span><span class="sxs-lookup"><span data-stu-id="ffcda-136">**Iobject - New**</span></span>  
 <span data-ttu-id="ffcda-137">Créez un nouvel InfoObject et associez-le à la colonne de flux de données de la ligne actuelle.</span><span class="sxs-lookup"><span data-stu-id="ffcda-137">Create a new InfoObject and associate this new InfoObect to the data flow column in the current row.</span></span> <span data-ttu-id="ffcda-138">Pour créer l’InfoObject, cliquez sur **Nouveau**, puis utilisez la boîte de dialogue **Créer un nouvel InfoObject** pour créer l’InfoObject.</span><span class="sxs-lookup"><span data-stu-id="ffcda-138">To create the new InfoObject, click **New**, and then use the **Create New InfoObject** dialog box to create the InfoObject.</span></span> <span data-ttu-id="ffcda-139">Pour plus d'informations sur cette boîte de dialogue, consultez [Create New InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="ffcda-139">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>  
  
 <span data-ttu-id="ffcda-140">Après avoir créé un InfoObject, le composant remplit les colonnes **InfoObject** et **Type** avec les nouvelles valeurs.</span><span class="sxs-lookup"><span data-stu-id="ffcda-140">After you create a new InfoObject, the component populates the **InfoObject** and **Type** columns with the new values.</span></span>  
  
 <span data-ttu-id="ffcda-141">**Iobject - Supprimer**</span><span class="sxs-lookup"><span data-stu-id="ffcda-141">**Iobject - Remove**</span></span>  
 <span data-ttu-id="ffcda-142">Supprimez l'association entre l'InfoObject et la colonne de flux de données de la ligne actuelle.</span><span class="sxs-lookup"><span data-stu-id="ffcda-142">Remove the association between the InfoObject and the data flow column for the current row.</span></span> <span data-ttu-id="ffcda-143">Pour supprimer cette association, cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="ffcda-143">To remove this association, click **Remove**.</span></span>  
  
 <span data-ttu-id="ffcda-144">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="ffcda-144">**InfoObject**</span></span>  
 <span data-ttu-id="ffcda-145">Affiche le nom de l'InfoObject qui est associé à la colonne de flux de données.</span><span class="sxs-lookup"><span data-stu-id="ffcda-145">Displays the name of the InfoObject that is associated with the data flow column.</span></span>  
  
 <span data-ttu-id="ffcda-146">**Type**</span><span class="sxs-lookup"><span data-stu-id="ffcda-146">**Type**</span></span>  
 <span data-ttu-id="ffcda-147">Affiche le type de l'InfoObject qui est associé à la colonne de flux de données.</span><span class="sxs-lookup"><span data-stu-id="ffcda-147">Displays the type of the InfoObject that is associated with the data flow column.</span></span> <span data-ttu-id="ffcda-148">Le tableau suivant répertorie les valeurs possibles pour le type.</span><span class="sxs-lookup"><span data-stu-id="ffcda-148">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="ffcda-149">Valeur</span><span class="sxs-lookup"><span data-stu-id="ffcda-149">Value</span></span>|<span data-ttu-id="ffcda-150">Description</span><span class="sxs-lookup"><span data-stu-id="ffcda-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ffcda-151">CHA</span><span class="sxs-lookup"><span data-stu-id="ffcda-151">CHA</span></span>|<span data-ttu-id="ffcda-152">Caractéristiques</span><span class="sxs-lookup"><span data-stu-id="ffcda-152">Characteristics</span></span>|  
|<span data-ttu-id="ffcda-153">UNI</span><span class="sxs-lookup"><span data-stu-id="ffcda-153">UNI</span></span>|<span data-ttu-id="ffcda-154">Units</span><span class="sxs-lookup"><span data-stu-id="ffcda-154">Units</span></span>|  
|<span data-ttu-id="ffcda-155">KYF</span><span class="sxs-lookup"><span data-stu-id="ffcda-155">KYF</span></span>|<span data-ttu-id="ffcda-156">Chiffres clés</span><span class="sxs-lookup"><span data-stu-id="ffcda-156">Key figures</span></span>|  
|<span data-ttu-id="ffcda-157">TIM</span><span class="sxs-lookup"><span data-stu-id="ffcda-157">TIM</span></span>|<span data-ttu-id="ffcda-158">Caractéristiques de temps</span><span class="sxs-lookup"><span data-stu-id="ffcda-158">Time characteristics</span></span>|  
  
 <span data-ttu-id="ffcda-159">**Champ d'unité**</span><span class="sxs-lookup"><span data-stu-id="ffcda-159">**Unit Field**</span></span>  
 <span data-ttu-id="ffcda-160">Spécifiez les unités que l'InfoObject va utiliser.</span><span class="sxs-lookup"><span data-stu-id="ffcda-160">Specify the units that the InfoObject will use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffcda-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ffcda-161">See Also</span></span>  
 <span data-ttu-id="ffcda-162">[Créer un InfoSource](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="ffcda-162">[Create InfoSource](create-infosource.md) </span></span>  
 [<span data-ttu-id="ffcda-163">Aide (F1) sur Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="ffcda-163">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
