---
title: Créer un InfoCube pour les données de transaction | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 673cea01-a260-4fce-a1a0-f73839289805
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a20fe051cfdd3e6afe285279996fcf696a83c21b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695932"
---
# <a name="create-infocube-for-transaction-data"></a><span data-ttu-id="37000-102">Créer un InfoCube pour les données de transaction</span><span class="sxs-lookup"><span data-stu-id="37000-102">Create InfoCube for Transaction Data</span></span>
  <span data-ttu-id="37000-103">Utilisez la boîte de dialogue **Créer un InfoCube pour les données de transaction** pour créer un InfoCube pour les données de transaction dans le système SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="37000-103">Use the **Create InfoCube for Transaction Data** dialog box to create a new InfoCube for transaction data in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="37000-104">Vous pouvez ouvrir la boîte de dialogue **Créer un InfoCube pour les données de transaction** depuis la page **Gestionnaire de connexions** de **l’Éditeur de destination SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="37000-104">You can open the **Create InfoCube for Transaction Data** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="37000-105">Pour en savoir plus sur la destination SAP BW, consultez [Destination SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="37000-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="37000-106">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="37000-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="37000-107">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="37000-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="37000-108">**Pour ouvrir la boîte de dialogue Créer un InfoCube pour les données de transaction**</span><span class="sxs-lookup"><span data-stu-id="37000-108">**To open the Create InfoCube for Transaction Data dialog box**</span></span>  
  
1.  <span data-ttu-id="37000-109">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui contient la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="37000-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="37000-110">Sous l’onglet **Flux de données** , double-cliquez sur la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="37000-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="37000-111">Dans l' **Éditeur de destination SAP BW**, cliquez sur **Gestionnaire de connexions** pour ouvrir la page **Gestionnaire de connexions** de l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="37000-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="37000-112">Dans la page **Gestionnaire de connexions** , dans la zone de groupe **Créer des objets SAP BW** , sélectionnez **InfoCube**, puis cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="37000-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoCube**, and then click **Create**.</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="37000-113">Options générales</span><span class="sxs-lookup"><span data-stu-id="37000-113">General Options</span></span>  
 <span data-ttu-id="37000-114">**Nom de l'InfoCube**</span><span class="sxs-lookup"><span data-stu-id="37000-114">**InfoCube name**</span></span>  
 <span data-ttu-id="37000-115">Entrez le nom du nouvel InfoCube.</span><span class="sxs-lookup"><span data-stu-id="37000-115">Enter a name for the new InfoCube.</span></span>  
  
 <span data-ttu-id="37000-116">**Description longue**</span><span class="sxs-lookup"><span data-stu-id="37000-116">**Long description**</span></span>  
 <span data-ttu-id="37000-117">Entrez une description pour le nouvel InfoCube.</span><span class="sxs-lookup"><span data-stu-id="37000-117">Enter a description for the new InfoCube.</span></span>  
  
 <span data-ttu-id="37000-118">**Enregistrer et activer**</span><span class="sxs-lookup"><span data-stu-id="37000-118">**Save & Activate**</span></span>  
 <span data-ttu-id="37000-119">Enregistrez et activez le nouvel InfoCube.</span><span class="sxs-lookup"><span data-stu-id="37000-119">Save and activate the new InfoCube.</span></span>  
  
## <a name="infocube-transfer-structure-options"></a><span data-ttu-id="37000-120">Options de structure de transfert de l'InfoCube</span><span class="sxs-lookup"><span data-stu-id="37000-120">InfoCube Transfer Structure Options</span></span>  
 <span data-ttu-id="37000-121">La section de structure de transfert de l'InfoCube vous permet d'associer les colonnes de flux de données à des InfoObjects.</span><span class="sxs-lookup"><span data-stu-id="37000-121">The InfoCube transfer structure section lets you associate data flow columns to InfoObjects.</span></span>  
  
 <span data-ttu-id="37000-122">**PipelineElement**</span><span class="sxs-lookup"><span data-stu-id="37000-122">**PipelineElement**</span></span>  
 <span data-ttu-id="37000-123">Affiche la colonne dans la sortie du flux de données qui est connectée à la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="37000-123">Displays the column in the output of the data flow that is connected to the SAP BW destination.</span></span>  
  
 <span data-ttu-id="37000-124">**PipelineDataType**</span><span class="sxs-lookup"><span data-stu-id="37000-124">**PipelineDataType**</span></span>  
 <span data-ttu-id="37000-125">Affiche le type de données de la colonne de flux de données.</span><span class="sxs-lookup"><span data-stu-id="37000-125">Displays the data type of the data flow column.</span></span>  
  
 <span data-ttu-id="37000-126">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="37000-126">**InfoObject**</span></span>  
 <span data-ttu-id="37000-127">Affiche le nom de l'InfoObject qui est associé à la colonne de flux de données.</span><span class="sxs-lookup"><span data-stu-id="37000-127">Displays the name of the InfoObject that is associated with the data flow column.</span></span>  
  
 <span data-ttu-id="37000-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="37000-128">**Type**</span></span>  
 <span data-ttu-id="37000-129">Affiche le type de l'InfoObject qui est associé à la colonne de flux de données.</span><span class="sxs-lookup"><span data-stu-id="37000-129">Displays the type of the InfoObject that is associated with the data flow column.</span></span> <span data-ttu-id="37000-130">Le tableau suivant répertorie les valeurs possibles pour le type.</span><span class="sxs-lookup"><span data-stu-id="37000-130">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="37000-131">Valeur</span><span class="sxs-lookup"><span data-stu-id="37000-131">Value</span></span>|<span data-ttu-id="37000-132">Description</span><span class="sxs-lookup"><span data-stu-id="37000-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="37000-133">CHA</span><span class="sxs-lookup"><span data-stu-id="37000-133">CHA</span></span>|<span data-ttu-id="37000-134">Caractéristiques</span><span class="sxs-lookup"><span data-stu-id="37000-134">Characteristics</span></span>|  
|<span data-ttu-id="37000-135">UNI</span><span class="sxs-lookup"><span data-stu-id="37000-135">UNI</span></span>|<span data-ttu-id="37000-136">Units</span><span class="sxs-lookup"><span data-stu-id="37000-136">Units</span></span>|  
|<span data-ttu-id="37000-137">KYF</span><span class="sxs-lookup"><span data-stu-id="37000-137">KYF</span></span>|<span data-ttu-id="37000-138">Chiffres clés</span><span class="sxs-lookup"><span data-stu-id="37000-138">Key figures</span></span>|  
|<span data-ttu-id="37000-139">TIM</span><span class="sxs-lookup"><span data-stu-id="37000-139">TIM</span></span>|<span data-ttu-id="37000-140">Caractéristiques de temps</span><span class="sxs-lookup"><span data-stu-id="37000-140">Time characteristics</span></span>|  
  
 <span data-ttu-id="37000-141">**Iobject - Rechercher**</span><span class="sxs-lookup"><span data-stu-id="37000-141">**Iobject - Search**</span></span>  
 <span data-ttu-id="37000-142">Associez un InfoObject existant à la colonne de flux de données de la ligne actuelle.</span><span class="sxs-lookup"><span data-stu-id="37000-142">Associate an existing InfoObject to the data flow column for the current row.</span></span> <span data-ttu-id="37000-143">Pour effectuer cette association, cliquez sur **Rechercher**, puis utilisez la boîte de dialogue **Rechercher un InfoObject** pour sélectionner l’InfoObject existant.</span><span class="sxs-lookup"><span data-stu-id="37000-143">To make this association, click **Search**, and then use the **Look Up InfoObject** dialog box to select the existing InfoObject.</span></span> <span data-ttu-id="37000-144">Pour plus d’informations sur cette boîte de dialogue, consultez [Rechercher un InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="37000-144">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="37000-145">Après avoir sélectionné un InfoObject existant, le composant remplit les colonnes **InfoObject** et **Type** avec les valeurs sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="37000-145">After you select an existing InfoObject, the component populates the **InfoObject** and **Type** columns with the selected values.</span></span>  
  
 <span data-ttu-id="37000-146">**Iobject - Nouveau**</span><span class="sxs-lookup"><span data-stu-id="37000-146">**Iobject - New**</span></span>  
 <span data-ttu-id="37000-147">Créez un nouvel InfoObject et associez ce nouvel InfoObject à la colonne de flux de données de la ligne actuelle.</span><span class="sxs-lookup"><span data-stu-id="37000-147">Create a new InfoObject and associate this new InfoObject to the data flow column in the current row.</span></span> <span data-ttu-id="37000-148">Pour créer l’InfoObject, cliquez sur **Nouveau**, puis utilisez la boîte de dialogue **Créer un nouvel InfoObject** pour créer l’InfoObject.</span><span class="sxs-lookup"><span data-stu-id="37000-148">To create the new InfoObject, click **New**, and then use the **Create New InfoObject** dialog box to create the InfoObject.</span></span> <span data-ttu-id="37000-149">Pour plus d'informations sur cette boîte de dialogue, consultez [Create New InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="37000-149">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>  
  
 <span data-ttu-id="37000-150">Après avoir créé un InfoObject, le composant remplit les colonnes **InfoObject** et **Type** avec les nouvelles valeurs.</span><span class="sxs-lookup"><span data-stu-id="37000-150">After you create a new InfoObject, the component populates the **InfoObject** and **Type** columns with the new values.</span></span>  
  
 <span data-ttu-id="37000-151">**Iobject - Supprimer**</span><span class="sxs-lookup"><span data-stu-id="37000-151">**Iobject - Remove**</span></span>  
 <span data-ttu-id="37000-152">Supprimez l'association entre l'InfoObject et la colonne de flux de données de la ligne actuelle.</span><span class="sxs-lookup"><span data-stu-id="37000-152">Remove the association between the InfoObject and the data flow column for the current row.</span></span> <span data-ttu-id="37000-153">Pour supprimer cette association, cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="37000-153">To remove this association, click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37000-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="37000-154">See Also</span></span>  
 [<span data-ttu-id="37000-155">Aide (F1) sur Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="37000-155">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
