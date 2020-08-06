---
title: Créer un Infopackage| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9cd4a848-409f-4681-a390-1c49a2aadbd7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 95f6ddce4e97c0c21d9f77c432231d414770dbce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695928"
---
# <a name="create-infopackage"></a><span data-ttu-id="5cf1c-102">Créer un InfoPackage</span><span class="sxs-lookup"><span data-stu-id="5cf1c-102">Create InfoPackage</span></span>
  <span data-ttu-id="5cf1c-103">Utilisez la boîte de dialogue **Créer un InfoPackage** pour créer un InfoPackage dans le système SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="5cf1c-103">Use the **Create InfoPackage** dialog box to create a new InfoPackage in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="5cf1c-104">Vous pouvez ouvrir la boîte de dialogue **Créer un InfoPackage** depuis la page **Gestionnaire de connexions** de **l’Éditeur de destination SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="5cf1c-104">You can open the **Create InfoPackage** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="5cf1c-105">Pour en savoir plus sur la destination SAP BW, consultez [Destination SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="5cf1c-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5cf1c-106">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="5cf1c-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="5cf1c-107">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="5cf1c-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="5cf1c-108">**Pour ouvrir la boîte de dialogue Créer un InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="5cf1c-108">**To open the Create InfoPackage dialog box**</span></span>  
  
1.  <span data-ttu-id="5cf1c-109">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui contient la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="5cf1c-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="5cf1c-110">Sous l’onglet **Flux de données** , double-cliquez sur la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="5cf1c-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="5cf1c-111">Dans l' **Éditeur de destination SAP BW**, cliquez sur **Gestionnaire de connexions** pour ouvrir la page **Gestionnaire de connexions** de l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="5cf1c-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="5cf1c-112">Dans la page **Gestionnaire de connexions** , dans la zone de groupe **Créer des objets SAP BW** , sélectionnez **InfoPackage**, puis cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="5cf1c-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoPackage**, and then click **Create**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5cf1c-113">Options</span><span class="sxs-lookup"><span data-stu-id="5cf1c-113">Options</span></span>  
 <span data-ttu-id="5cf1c-114">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="5cf1c-114">**InfoSource**</span></span>  
 <span data-ttu-id="5cf1c-115">Entrez le nom de l'InfoSource sur lequel le nouvel InfoPackage doit être basé.</span><span class="sxs-lookup"><span data-stu-id="5cf1c-115">Enter the name of the InfoSource on which the new InfoPackage should be based.</span></span>  
  
 <span data-ttu-id="5cf1c-116">**Brève description**</span><span class="sxs-lookup"><span data-stu-id="5cf1c-116">**Short description**</span></span>  
 <span data-ttu-id="5cf1c-117">Entrez une description pour le nouvel InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="5cf1c-117">Enter a description for the new InfoPackage.</span></span>  
  
 <span data-ttu-id="5cf1c-118">**Système source**</span><span class="sxs-lookup"><span data-stu-id="5cf1c-118">**Source system**</span></span>  
 <span data-ttu-id="5cf1c-119">Sélectionnez le système source auquel le nouvel InfoPackage doit être associé.</span><span class="sxs-lookup"><span data-stu-id="5cf1c-119">Select the source system with which the new InfoPackage should be associated.</span></span>  
  
 <span data-ttu-id="5cf1c-120">**Attributs**</span><span class="sxs-lookup"><span data-stu-id="5cf1c-120">**Attributes**</span></span>  
 <span data-ttu-id="5cf1c-121">Indique que l'InfoPackage chargera les données d'attribut.</span><span class="sxs-lookup"><span data-stu-id="5cf1c-121">Indicates that the InfoPackage will load attribute data.</span></span>  
  
 <span data-ttu-id="5cf1c-122">**Textes**</span><span class="sxs-lookup"><span data-stu-id="5cf1c-122">**Texts**</span></span>  
 <span data-ttu-id="5cf1c-123">Indique que l'InfoPackage chargera les données de texte.</span><span class="sxs-lookup"><span data-stu-id="5cf1c-123">Indicates that the InfoPackage will load text data.</span></span>  
  
 <span data-ttu-id="5cf1c-124">**Transaction**</span><span class="sxs-lookup"><span data-stu-id="5cf1c-124">**Transaction**</span></span>  
 <span data-ttu-id="5cf1c-125">Indique que l'InfoPackage chargera les données de transaction.</span><span class="sxs-lookup"><span data-stu-id="5cf1c-125">Indicates that the InfoPackage will load transaction data.</span></span>  
  
 <span data-ttu-id="5cf1c-126">**Enregistrer et activer**</span><span class="sxs-lookup"><span data-stu-id="5cf1c-126">**Save & Activate**</span></span>  
 <span data-ttu-id="5cf1c-127">Enregistrez et activez le nouvel InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="5cf1c-127">Save and activate the new InfoPackage.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cf1c-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5cf1c-128">See Also</span></span>  
 [<span data-ttu-id="5cf1c-129">Aide (F1) sur Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="5cf1c-129">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
