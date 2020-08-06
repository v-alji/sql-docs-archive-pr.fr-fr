---
title: Journal des requêtes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 165d3833-0493-490c-9f63-8a134a7fafb8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 024012878ae94c5ba6276648e289e6e6f7c93d7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602907"
---
# <a name="request-log"></a><span data-ttu-id="827b3-102">Journal des requêtes</span><span class="sxs-lookup"><span data-stu-id="827b3-102">Request Log</span></span>
  <span data-ttu-id="827b3-103">Utilisez la boîte de dialogue **Journal des requêtes** pour afficher les événements journalisés lors de la demande qui est effectuée au système SAP Netweaver BW pour les exemples de données.</span><span class="sxs-lookup"><span data-stu-id="827b3-103">Use the **Request Log** dialog box to view the events that are logged during the request that is made to the SAP Netweaver BW system for sample data.</span></span> <span data-ttu-id="827b3-104">Ces informations peuvent être utiles si vous devez dépanner votre configuration de la source SAP BW.</span><span class="sxs-lookup"><span data-stu-id="827b3-104">This information can be useful if you have to troubleshoot your configuration of the SAP BW source.</span></span>  
  
 <span data-ttu-id="827b3-105">Pour en savoir plus sur le composant source SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 pour SAP BW, consultez [SAP BW Source](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="827b3-105">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="827b3-106">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="827b3-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="827b3-107">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="827b3-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="827b3-108">Vous devez disposer d'une licence SAP supplémentaire pour extraire des données à partir de SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="827b3-108">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="827b3-109">Vérifiez auprès de SAP.</span><span class="sxs-lookup"><span data-stu-id="827b3-109">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="827b3-110">**Pour ouvrir la boîte de dialogue Journal des requêtes**</span><span class="sxs-lookup"><span data-stu-id="827b3-110">**To open the Request Log dialog box**</span></span>  
  
1.  <span data-ttu-id="827b3-111">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui contient la source SAP BW.</span><span class="sxs-lookup"><span data-stu-id="827b3-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="827b3-112">Sous l’onglet **Flux de données** , double-cliquez sur la source SAP BW.</span><span class="sxs-lookup"><span data-stu-id="827b3-112">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="827b3-113">Dans l' **Éditeur de source SAP BW**, cliquez sur **Gestionnaire de connexions** pour ouvrir la page **Gestionnaire de connexions** de l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="827b3-113">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="827b3-114">Après avoir configuré la source SAP BW, cliquez sur **Aperçu** pour afficher un aperçu des événements dans la boîte de dialogue **Journal des requêtes** .</span><span class="sxs-lookup"><span data-stu-id="827b3-114">After you configure the SAP BW source, click **Preview** to preview the events in the **Request Log** dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="827b3-115">Cliquer sur **Aperçu** ouvre également la boîte de dialogue **Aperçu** .</span><span class="sxs-lookup"><span data-stu-id="827b3-115">Clicking **Preview** also opens the **Preview** dialog box.</span></span> <span data-ttu-id="827b3-116">Pour plus d'informations sur cette boîte de dialogue, consultez [Preview](preview.md).</span><span class="sxs-lookup"><span data-stu-id="827b3-116">For more information about this dialog box, see [Preview](preview.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="827b3-117">Options</span><span class="sxs-lookup"><span data-stu-id="827b3-117">Options</span></span>  
 <span data-ttu-id="827b3-118">**Time**</span><span class="sxs-lookup"><span data-stu-id="827b3-118">**Time**</span></span>  
 <span data-ttu-id="827b3-119">Affiche l'heure à laquelle l'événement a été journalisé.</span><span class="sxs-lookup"><span data-stu-id="827b3-119">Displays the time that the event that was logged.</span></span>  
  
 <span data-ttu-id="827b3-120">**Type**</span><span class="sxs-lookup"><span data-stu-id="827b3-120">**Type**</span></span>  
 <span data-ttu-id="827b3-121">Affiche le type de l'événement qui a été journalisé.</span><span class="sxs-lookup"><span data-stu-id="827b3-121">Displays the type of the event that was logged.</span></span> <span data-ttu-id="827b3-122">Le tableau suivant répertorie les types d'événements possibles.</span><span class="sxs-lookup"><span data-stu-id="827b3-122">The following table lists the possible event types.</span></span>  
  
|<span data-ttu-id="827b3-123">Valeur</span><span class="sxs-lookup"><span data-stu-id="827b3-123">Value</span></span>|<span data-ttu-id="827b3-124">Description</span><span class="sxs-lookup"><span data-stu-id="827b3-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="827b3-125">S</span><span class="sxs-lookup"><span data-stu-id="827b3-125">S</span></span>|<span data-ttu-id="827b3-126">Message de réussite.</span><span class="sxs-lookup"><span data-stu-id="827b3-126">Success message.</span></span>|  
|<span data-ttu-id="827b3-127">E</span><span class="sxs-lookup"><span data-stu-id="827b3-127">E</span></span>|<span data-ttu-id="827b3-128">Message d’erreur</span><span class="sxs-lookup"><span data-stu-id="827b3-128">Error message</span></span>|  
|<span data-ttu-id="827b3-129">W</span><span class="sxs-lookup"><span data-stu-id="827b3-129">W</span></span>|<span data-ttu-id="827b3-130">Message d'avertissement.</span><span class="sxs-lookup"><span data-stu-id="827b3-130">Warning message.</span></span>|  
|<span data-ttu-id="827b3-131">I</span><span class="sxs-lookup"><span data-stu-id="827b3-131">I</span></span>|<span data-ttu-id="827b3-132">Message d’information.</span><span class="sxs-lookup"><span data-stu-id="827b3-132">Informational message.</span></span>|  
|<span data-ttu-id="827b3-133">Un</span><span class="sxs-lookup"><span data-stu-id="827b3-133">A</span></span>|<span data-ttu-id="827b3-134">L'opération a été abandonnée.</span><span class="sxs-lookup"><span data-stu-id="827b3-134">The operation was aborted.</span></span>|  
  
 <span data-ttu-id="827b3-135">**Message**</span><span class="sxs-lookup"><span data-stu-id="827b3-135">**Message**</span></span>  
 <span data-ttu-id="827b3-136">Affiche le texte du message associé à l'événement journalisé.</span><span class="sxs-lookup"><span data-stu-id="827b3-136">Displays the message text that is associated with the logged event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="827b3-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="827b3-137">See Also</span></span>  
 <span data-ttu-id="827b3-138">[Éditeur de source SAP BW &#40;page Gestionnaire de connexions&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="827b3-138">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="827b3-139">Aide (F1) sur Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="827b3-139">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
