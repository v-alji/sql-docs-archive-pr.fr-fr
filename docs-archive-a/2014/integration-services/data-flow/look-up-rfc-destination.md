---
title: Rechercher la destination RFC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: db9404d8-4c42-45e5-a100-c7a84b056109
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 397298fce16509e667aa4baccaee62c6ff0f5cca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708511"
---
# <a name="look-up-rfc-destination"></a><span data-ttu-id="3438d-102">Rechercher la destination RFC</span><span class="sxs-lookup"><span data-stu-id="3438d-102">Look Up RFC Destination</span></span>
  <span data-ttu-id="3438d-103">Utilisez la boîte de dialogue **Rechercher la destination RFC** pour rechercher une destination RFC qui est définie dans le système SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="3438d-103">Use the **Look Up RFC Destination** dialog box to look up an RFC destination that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="3438d-104">Lorsque la liste de destinations RFC disponibles apparaît, sélectionnez la destination de votre choix. Le composant remplira les options associées à l'aide des valeurs requises.</span><span class="sxs-lookup"><span data-stu-id="3438d-104">When the list of available RFC destinations appears, select the destination that you want, and the component will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="3438d-105">La source SAP BW et la destination SAP BW utilisent toutes les deux la boîte de dialogue **Rechercher la destination RFC** .</span><span class="sxs-lookup"><span data-stu-id="3438d-105">Both the SAP BW source and the SAP BW destination use the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="3438d-106">Pour plus d’informations sur ces composants de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 pour SAP BW, consultez [Source SAP BW](sap-bw-source.md) et [Destination SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="3438d-106">For more information about these components of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md) and [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3438d-107">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="3438d-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="3438d-108">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="3438d-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="3438d-109">**Pour ouvrir la boîte de dialogue Rechercher la destination RFC**</span><span class="sxs-lookup"><span data-stu-id="3438d-109">**To open the Look Up RFC Destination dialog box**</span></span>  
  
1.  <span data-ttu-id="3438d-110">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le package à [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui contient la source ou la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="3438d-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source or destination.</span></span>  
  
2.  <span data-ttu-id="3438d-111">Sous l’onglet **Flux de données** , double-cliquez sur la source ou la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="3438d-111">On the **Data Flow** tab, double-click the SAP BW source or destination.</span></span>  
  
3.  <span data-ttu-id="3438d-112">Dans l' **Éditeur de source SAP BW** ou dans l' **Éditeur de destination SAP BW**, cliquez sur **Gestionnaire de connexions** pour ouvrir la page **Gestionnaire de connexions** de l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="3438d-112">In the **SAP BW Source Editor** or the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="3438d-113">Sur la page **Gestionnaire de connexions** , dans la zone de groupe **Destination RFC** , cliquez sur **Rechercher** pour afficher la boîte de dialogue **Rechercher la destination RFC** .</span><span class="sxs-lookup"><span data-stu-id="3438d-113">On the **Connection Manager** page, in the **RFC Destination** group box, click **Look up** to display the **Look Up RFC Destination** dialog box.</span></span>  
  
     <span data-ttu-id="3438d-114">Dans **l’Éditeur de source SAP BW**, la zone de groupe **Destination RFC** s’affiche uniquement si l’option **Mode d’exécution** a la valeur **P - Déclencher une chaîne de processus** ou **A - Attendre la notification**.</span><span class="sxs-lookup"><span data-stu-id="3438d-114">In the **SAP BW Source Editor**, the **RFC Destination** group box appears only if the value for **Execution mode** is **P - Trigger process chain** or **W - Wait for notify**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3438d-115">Options</span><span class="sxs-lookup"><span data-stu-id="3438d-115">Options</span></span>  
 <span data-ttu-id="3438d-116">**Destination**</span><span class="sxs-lookup"><span data-stu-id="3438d-116">**Destination**</span></span>  
 <span data-ttu-id="3438d-117">Affichez le nom de la destination RFC qui est définie dans le système SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="3438d-117">View the name of the RFC destination that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="3438d-118">**Hôte de passerelle**</span><span class="sxs-lookup"><span data-stu-id="3438d-118">**Gateway Host**</span></span>  
 <span data-ttu-id="3438d-119">Affichez le nom du serveur ou l'adresse IP de l'hôte de passerelle.</span><span class="sxs-lookup"><span data-stu-id="3438d-119">View the server name or IP address of the gateway host.</span></span> <span data-ttu-id="3438d-120">Généralement, le nom ou l'adresse IP est identique au serveur d'applications SAP.</span><span class="sxs-lookup"><span data-stu-id="3438d-120">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="3438d-121">**Service de passerelle**</span><span class="sxs-lookup"><span data-stu-id="3438d-121">**Gateway Service**</span></span>  
 <span data-ttu-id="3438d-122">Entrez le nom du service de passerelle, au format `sapgwNN`, où `NN` représente le numéro du système.</span><span class="sxs-lookup"><span data-stu-id="3438d-122">View the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="3438d-123">**ID de programme**</span><span class="sxs-lookup"><span data-stu-id="3438d-123">**Program ID**</span></span>  
 <span data-ttu-id="3438d-124">Affichez l'ID de programme associé à la destination RFC.</span><span class="sxs-lookup"><span data-stu-id="3438d-124">View the Program ID that is associated with the RFC destination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3438d-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3438d-125">See Also</span></span>  
 <span data-ttu-id="3438d-126">[Éditeur de source SAP BW &#40;page Gestionnaire de connexions&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="3438d-126">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="3438d-127">[Éditeur de destination SAP BW &#40;page Gestionnaire de connexions&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="3438d-127">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="3438d-128">Aide (F1) sur Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="3438d-128">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
