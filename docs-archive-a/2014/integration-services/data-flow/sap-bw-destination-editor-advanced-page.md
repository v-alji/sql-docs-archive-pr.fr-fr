---
title: Éditeur de destination SAP BW (page Avancé) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 862957db-bbc6-4dda-bc0e-591457f1baa7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0c5ca943b804ad39cc391cb1cf7f06e056ddbe56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610771"
---
# <a name="sap-bw-destination-editor-advanced-page"></a><span data-ttu-id="d6d23-102">Éditeur de destination SAP BW (page Avancé)</span><span class="sxs-lookup"><span data-stu-id="d6d23-102">SAP BW Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="d6d23-103">Utilisez la page **Avancé** de **l’Éditeur de destination SAP BW** pour définir les paramètres avancés tels que la taille du package et les informations de temps d’attente.</span><span class="sxs-lookup"><span data-stu-id="d6d23-103">Use the **Advanced** page of the **SAP BW Destination Editor** to set advanced settings such as package size and time-out information.</span></span>  
  
 <span data-ttu-id="d6d23-104">Pour en savoir plus sur la destination SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 pour SAP BW, consultez [Destination SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="d6d23-104">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d6d23-105">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="d6d23-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="d6d23-106">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="d6d23-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="d6d23-107">**Pour ouvrir la page Avancé**</span><span class="sxs-lookup"><span data-stu-id="d6d23-107">**To open the Advanced page**</span></span>  
  
1.  <span data-ttu-id="d6d23-108">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui contient la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d6d23-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="d6d23-109">Sous l’onglet **Flux de données** , double-cliquez sur la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d6d23-109">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="d6d23-110">Dans **l’Éditeur de destination SAP BW**, cliquez sur **Avancé** pour ouvrir la page **Avancé** de l’éditeur.</span><span class="sxs-lookup"><span data-stu-id="d6d23-110">In the **SAP BW Destination Editor**, click **Advanced** to open the **Advanced** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d6d23-111">Options</span><span class="sxs-lookup"><span data-stu-id="d6d23-111">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d6d23-112">Si vous ne connaissez pas toutes les valeurs requises pour configurer la destination, adressez-vous à votre administrateur SAP.</span><span class="sxs-lookup"><span data-stu-id="d6d23-112">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="d6d23-113">**Taille du package**</span><span class="sxs-lookup"><span data-stu-id="d6d23-113">**Package size**</span></span>  
 <span data-ttu-id="d6d23-114">Spécifiez combien de lignes de données seront transférées à la fois.</span><span class="sxs-lookup"><span data-stu-id="d6d23-114">Specify how many rows of data will be transferred at a time.</span></span> <span data-ttu-id="d6d23-115">La valeur optimale de ce paramètre dépend du système SAP Netweaver BW et du traitement supplémentaire des données qui peut avoir lieu.</span><span class="sxs-lookup"><span data-stu-id="d6d23-115">The optimal value for this parameter depends on the SAP Netweaver BW system and on additional processing of the data that might occur.</span></span> <span data-ttu-id="d6d23-116">En général, des valeurs comprises entre 2 000 et 20 000 offrent les meilleures performances.</span><span class="sxs-lookup"><span data-stu-id="d6d23-116">Typically, values between 2000 and 20000 offer the best performance.</span></span>  
  
 <span data-ttu-id="d6d23-117">**Déclencher la chaîne de processus**</span><span class="sxs-lookup"><span data-stu-id="d6d23-117">**Trigger process chain**</span></span>  
 <span data-ttu-id="d6d23-118">(Facultatif) Spécifiez le nom d'une chaîne de processus à déclencher une fois le chargement des données terminé.</span><span class="sxs-lookup"><span data-stu-id="d6d23-118">(Optional) Specify the name of a process chain to be triggered after the loading of data is completed.</span></span>  
  
 <span data-ttu-id="d6d23-119">**Délai d'attente d'InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="d6d23-119">**Timeout for waiting InfoPackage**</span></span>  
 <span data-ttu-id="d6d23-120">Spécifiez le nombre maximal de secondes pendant lesquelles la destination doit attendre la fin de l'InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="d6d23-120">Specify the maximum number of seconds that the destination should wait for the InfoPackage to finish.</span></span>  
  
 <span data-ttu-id="d6d23-121">**Attendre la fin du transfert de données**</span><span class="sxs-lookup"><span data-stu-id="d6d23-121">**Wait for data transfer to finish**</span></span>  
 <span data-ttu-id="d6d23-122">Spécifiez si la destination doit attendre que le système SAP Netweaver BW ait terminé de charger les données.</span><span class="sxs-lookup"><span data-stu-id="d6d23-122">Specify whether the destination should wait until the SAP Netweaver BW system has finished loading the data.</span></span>  
  
 <span data-ttu-id="d6d23-123">**Ne pas démarrer InfoPackage (attendre uniquement)**</span><span class="sxs-lookup"><span data-stu-id="d6d23-123">**No InfoPackage Start (Only Wait)**</span></span>  
 <span data-ttu-id="d6d23-124">Spécifiez que la destination ne doit pas déclencher d'InfoPackage, mais attendre uniquement la notification informant que le système SAP Netweaver BW a démarré le chargement des données.</span><span class="sxs-lookup"><span data-stu-id="d6d23-124">Specify that the destination does not trigger an InfoPackage, but just waits for notification that the SAP Netweaver BW system has started loading the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6d23-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d6d23-125">See Also</span></span>  
 <span data-ttu-id="d6d23-126">[Éditeur de destination SAP BW &#40;page Gestionnaire de connexions&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="d6d23-126">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="d6d23-127">[Éditeur de destination SAP BW &#40;page Mappages&#41;](sap-bw-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="d6d23-127">[SAP BW Destination Editor &#40;Mappings Page&#41;](sap-bw-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="d6d23-128">[Éditeur de destination SAP BW &#40;page Sortie d’erreur&#41;](sap-bw-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="d6d23-128">[SAP BW Destination Editor &#40;Error Output Page&#41;](sap-bw-destination-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="d6d23-129">Aide (F1) sur Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="d6d23-129">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
