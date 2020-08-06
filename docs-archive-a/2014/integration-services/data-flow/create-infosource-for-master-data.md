---
title: Créer un InfoSource pour les données maîtres | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b52a9a89-8380-4a02-8a83-dcfb46ae860e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bb90bc5cf27f37dc89df236b765db98088a5804a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695924"
---
# <a name="create-infosource-for-master-data"></a><span data-ttu-id="9c956-102">Créer un InfoSource pour les données maîtres</span><span class="sxs-lookup"><span data-stu-id="9c956-102">Create InfoSource for Master Data</span></span>
  <span data-ttu-id="9c956-103">Utilisez la boîte de dialogue **Créer un InfoSource pour les données maîtres** pour créer un nouvel InfoSource pour les données maîtres dans le système SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="9c956-103">Use the **Create InfoSource for Master Data** dialog box to create a new InfoSource for master data in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="9c956-104">Vous pouvez ouvrir la boîte de dialogue **Créer un InfoSource pour les données maîtres** à partir de la page **Gestionnaire de connexions** de **l’Éditeur de destination SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="9c956-104">You can open the **Create InfoSource for Master Data** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="9c956-105">Pour en savoir plus sur la destination SAP BW, consultez [Destination SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="9c956-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9c956-106">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="9c956-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="9c956-107">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="9c956-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="9c956-108">**Pour ouvrir la boîte de dialogue Créer un InfoSource pour les données maîtres**</span><span class="sxs-lookup"><span data-stu-id="9c956-108">**To open the Create InfoSource for Master Data dialog box**</span></span>  
  
1.  <span data-ttu-id="9c956-109">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui contient la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="9c956-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="9c956-110">Sous l’onglet **Flux de données** , double-cliquez sur la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="9c956-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="9c956-111">Dans l' **Éditeur de destination SAP BW**, cliquez sur **Gestionnaire de connexions** pour ouvrir la page **Gestionnaire de connexions** de l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="9c956-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="9c956-112">Dans la page **Gestionnaire de connexions** , dans la zone de groupe **Créer des objets SAP BW** , sélectionnez **InfoSource**, puis cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="9c956-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoSource**, and then click **Create**.</span></span>  
  
5.  <span data-ttu-id="9c956-113">Dans la boîte de dialogue **Créer un InfoSource** , sélectionnez **Données maîtres**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c956-113">In the **Create InfoSource** dialog box, select **Master data**, and then click **OK**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9c956-114">Options</span><span class="sxs-lookup"><span data-stu-id="9c956-114">Options</span></span>  
 <span data-ttu-id="9c956-115">**Nom de l'InfoObject**</span><span class="sxs-lookup"><span data-stu-id="9c956-115">**InfoObject name**</span></span>  
 <span data-ttu-id="9c956-116">Entrez le nom de l'InfoObject sur lequel le nouvel InfoSource doit être basé.</span><span class="sxs-lookup"><span data-stu-id="9c956-116">Enter the name of the InfoObject on which the new InfoSource should be based.</span></span>  
  
 <span data-ttu-id="9c956-117">**Rechercher**</span><span class="sxs-lookup"><span data-stu-id="9c956-117">**Look up**</span></span>  
 <span data-ttu-id="9c956-118">Recherchez l'InfoObject.</span><span class="sxs-lookup"><span data-stu-id="9c956-118">Look up the InfoObject.</span></span> <span data-ttu-id="9c956-119">Cette option ouvre la boîte de dialogue **Rechercher un InfoObject** dans laquelle vous pouvez sélectionner l’InfoObject.</span><span class="sxs-lookup"><span data-stu-id="9c956-119">This option opens the **Look Up InfoObject** dialog box in which you can select the InfoObject.</span></span> <span data-ttu-id="9c956-120">Pour plus d’informations sur cette boîte de dialogue, consultez [Rechercher un InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="9c956-120">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="9c956-121">Après avoir sélectionné un InfoObject, le composant remplit la zone de texte **Nom de l’InfoObject** avec le nom de l’InfoObject sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9c956-121">After you select an InfoObject, the component populates the **InfoObject name** text box with the name of the selected InfoObject.</span></span>  
  
 <span data-ttu-id="9c956-122">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="9c956-122">**New**</span></span>  
 <span data-ttu-id="9c956-123">Créez un nouvel InfoObject.</span><span class="sxs-lookup"><span data-stu-id="9c956-123">Create a new InfoObject.</span></span> <span data-ttu-id="9c956-124">Cette option ouvre la boîte de dialogue **Créer un nouvel InfoObject** dans laquelle vous pouvez créer l’InfoObject.</span><span class="sxs-lookup"><span data-stu-id="9c956-124">This option opens the **Create New InfoObject** dialog box in which you can create the new InfoObject.</span></span> <span data-ttu-id="9c956-125">Pour plus d'informations sur cette boîte de dialogue, consultez [Create New InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="9c956-125">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>  
  
 <span data-ttu-id="9c956-126">Après avoir créé un InfoObject, le composant remplit la zone de texte **Nom de l’InfoObject** avec le nom du nouvel InfoObject.</span><span class="sxs-lookup"><span data-stu-id="9c956-126">After you create an InfoObject, the component populates the **InfoObject name** text box with the name of the new InfoObject.</span></span>  
  
 <span data-ttu-id="9c956-127">**Brève description**</span><span class="sxs-lookup"><span data-stu-id="9c956-127">**Short description**</span></span>  
 <span data-ttu-id="9c956-128">Entrez une brève description pour le nouvel InfoSource.</span><span class="sxs-lookup"><span data-stu-id="9c956-128">Enter a short description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="9c956-129">**Description longue**</span><span class="sxs-lookup"><span data-stu-id="9c956-129">**Long description**</span></span>  
 <span data-ttu-id="9c956-130">Entrez une longue description pour le nouvel InfoSource.</span><span class="sxs-lookup"><span data-stu-id="9c956-130">Enter a long description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="9c956-131">**Système source**</span><span class="sxs-lookup"><span data-stu-id="9c956-131">**Source system**</span></span>  
 <span data-ttu-id="9c956-132">Sélectionnez le système source à associer au nouvel InfoSource.</span><span class="sxs-lookup"><span data-stu-id="9c956-132">Select the source system to be associated with the new InfoSource.</span></span>  
  
 <span data-ttu-id="9c956-133">**Application**</span><span class="sxs-lookup"><span data-stu-id="9c956-133">**Application**</span></span>  
 <span data-ttu-id="9c956-134">Entrez le nom de l'application à associer au nouvel InfoSource.</span><span class="sxs-lookup"><span data-stu-id="9c956-134">Enter the name of the application to be associated with the new InfoSource.</span></span>  
  
 <span data-ttu-id="9c956-135">**Attributs**</span><span class="sxs-lookup"><span data-stu-id="9c956-135">**Attributes**</span></span>  
 <span data-ttu-id="9c956-136">Indique que les données maîtres sont des attributs.</span><span class="sxs-lookup"><span data-stu-id="9c956-136">Indicates that the master data consists of attributes.</span></span>  
  
 <span data-ttu-id="9c956-137">**Textes**</span><span class="sxs-lookup"><span data-stu-id="9c956-137">**Texts**</span></span>  
 <span data-ttu-id="9c956-138">Indique que les données maîtres sont des attributs.</span><span class="sxs-lookup"><span data-stu-id="9c956-138">Indicates that the master data consists of attributes.</span></span>  
  
 <span data-ttu-id="9c956-139">**Enregistrer et activer**</span><span class="sxs-lookup"><span data-stu-id="9c956-139">**Save & Activate**</span></span>  
 <span data-ttu-id="9c956-140">Enregistrez et activez le nouvel InfoSource.</span><span class="sxs-lookup"><span data-stu-id="9c956-140">Save and activate the new InfoSource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c956-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9c956-141">See Also</span></span>  
 <span data-ttu-id="9c956-142">[Créer un InfoSource](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="9c956-142">[Create InfoSource](create-infosource.md) </span></span>  
 [<span data-ttu-id="9c956-143">Aide (F1) sur Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="9c956-143">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
