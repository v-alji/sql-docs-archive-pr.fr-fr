---
title: Créer un InfoSource | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e7db233b-5464-43de-9d26-6dd24c7ac1b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9620d3170310322c79679e8298ffe465067ae7d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695912"
---
# <a name="create-infosource"></a><span data-ttu-id="fc94d-102">Créer un InfoSource</span><span class="sxs-lookup"><span data-stu-id="fc94d-102">Create InfoSource</span></span>
  <span data-ttu-id="fc94d-103">Utilisez la boîte de dialogue **Créer un InfoSource** pour créer un InfoSource.</span><span class="sxs-lookup"><span data-stu-id="fc94d-103">Use the **Create InfoSource** dialog box to create a new InfoSource.</span></span> <span data-ttu-id="fc94d-104">Pour créer l’InfoSource, utilisez la boîte de dialogue **Créer un InfoSource pour les données de transaction** ou **Créer un InfoSource pour les données maîtres** .</span><span class="sxs-lookup"><span data-stu-id="fc94d-104">To create the new InfoSource, you use either the **Create InfoSource for Transaction Data** or the **Create InfoSource for Master Data** dialog box.</span></span>  
  
 <span data-ttu-id="fc94d-105">Vous pouvez ouvrir la boîte de dialogue **Créer un InfoSource** à partir de la page **Gestionnaire de connexions** de l’ **Éditeur de destination SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="fc94d-105">You can open the **Create InfoSource** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="fc94d-106">Pour en savoir plus sur la destination SAP BW, consultez [Destination SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="fc94d-106">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fc94d-107">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="fc94d-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="fc94d-108">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="fc94d-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="fc94d-109">**Pour ouvrir la boîte de dialogue Créer un InfoSource**</span><span class="sxs-lookup"><span data-stu-id="fc94d-109">**To open the Create InfoSource dialog box**</span></span>  
  
1.  <span data-ttu-id="fc94d-110">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui contient la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="fc94d-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="fc94d-111">Sous l’onglet **Flux de données** , double-cliquez sur la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="fc94d-111">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="fc94d-112">Dans l' **Éditeur de destination SAP BW**, cliquez sur **Gestionnaire de connexions** pour ouvrir la page **Gestionnaire de connexions** de l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="fc94d-112">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="fc94d-113">Dans la page **Gestionnaire de connexions** , dans la zone de groupe **Créer des objets SAP BW** , sélectionnez **InfoSource**, puis cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="fc94d-113">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoSource**, and then click **Create**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fc94d-114">Options</span><span class="sxs-lookup"><span data-stu-id="fc94d-114">Options</span></span>  
 <span data-ttu-id="fc94d-115">**Données de transaction**</span><span class="sxs-lookup"><span data-stu-id="fc94d-115">**Transaction data**</span></span>  
 <span data-ttu-id="fc94d-116">Créez un InfoSource pour les données de transaction.</span><span class="sxs-lookup"><span data-stu-id="fc94d-116">Create a new InfoSource for transaction data.</span></span>  
  
 <span data-ttu-id="fc94d-117">Si vous sélectionnez cette option, la boîte de dialogue **Créer un InfoSource pour les données de transaction** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="fc94d-117">If you select this option, the **Create InfoSource for Transaction Data** dialog box opens.</span></span> <span data-ttu-id="fc94d-118">Utilisez la boîte de dialogue **Créer un InfoSource pour les données de transaction** pour créer l’InfoSource.</span><span class="sxs-lookup"><span data-stu-id="fc94d-118">You use the **Create InfoSource for Transaction Data** dialog box to create the new InfoSource.</span></span> <span data-ttu-id="fc94d-119">Pour plus d’informations sur cette boîte de dialogue, consultez [Créer un InfoSource pour les données de transaction](create-infosource-for-transaction-data.md).</span><span class="sxs-lookup"><span data-stu-id="fc94d-119">For more information about this dialog box, see [Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md).</span></span>  
  
 <span data-ttu-id="fc94d-120">**Données maîtres**</span><span class="sxs-lookup"><span data-stu-id="fc94d-120">**Master data**</span></span>  
 <span data-ttu-id="fc94d-121">Créez un InfoSource pour les données maîtres.</span><span class="sxs-lookup"><span data-stu-id="fc94d-121">Create a new InfoSource for master data.</span></span>  
  
 <span data-ttu-id="fc94d-122">Si vous sélectionnez cette option, la boîte de dialogue **Créer un InfoSource pour les données maîtres** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="fc94d-122">If you select this option, the **Create InfoSource for Master Data** dialog box opens.</span></span> <span data-ttu-id="fc94d-123">Utilisez la boîte de dialogue **Créer un InfoSource pour les données maîtres** pour créer l’InfoSource.</span><span class="sxs-lookup"><span data-stu-id="fc94d-123">You use the **Create InfoSource for Master Data** dialog box to create the new InfoSource.</span></span> <span data-ttu-id="fc94d-124">Pour plus d’informations sur cette boîte de dialogue, consultez [Créer un Infosource pour les données maîtres](create-infosource-for-master-data.md).</span><span class="sxs-lookup"><span data-stu-id="fc94d-124">For more information about this dialog box, see [Create InfoSource for Master Data](create-infosource-for-master-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc94d-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fc94d-125">See Also</span></span>  
 [<span data-ttu-id="fc94d-126">Aide (F1) sur Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="fc94d-126">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
