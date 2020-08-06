---
title: Éditeur de source SAP BW (page Avancé) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 44f3c991-9e8f-4126-a9a2-2d9da779fb11
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7c78d40555a30031bf39abda18048fda9c648d01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707707"
---
# <a name="sap-bw-source-editor-advanced-page"></a><span data-ttu-id="95ef7-102">Éditeur de source SAP BW (page Avancé)</span><span class="sxs-lookup"><span data-stu-id="95ef7-102">SAP BW Source Editor (Advanced Page)</span></span>
  <span data-ttu-id="95ef7-103">Utilisez la page **Avancé** de **l’Éditeur de source SAP BW** pour spécifier la règle de conversion de chaînes et le délai d’attente, et également pour réinitialiser l’état d’un ID de demande particulier.</span><span class="sxs-lookup"><span data-stu-id="95ef7-103">Use the **Advanced** page of the **SAP BW Source Editor** to specify the string conversion rule and the time-out period, and also to reset the status of a particular Request ID.</span></span>  
  
 <span data-ttu-id="95ef7-104">Pour en savoir plus sur le composant source SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 pour SAP BW, consultez [SAP BW Source](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="95ef7-104">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="95ef7-105">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="95ef7-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="95ef7-106">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="95ef7-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="95ef7-107">Vous devez disposer d'une licence SAP supplémentaire pour extraire des données à partir de SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="95ef7-107">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="95ef7-108">Vérifiez auprès de SAP.</span><span class="sxs-lookup"><span data-stu-id="95ef7-108">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="95ef7-109">**Pour ouvrir la page Gestionnaire de connexions**</span><span class="sxs-lookup"><span data-stu-id="95ef7-109">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="95ef7-110">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui contient la source SAP BW.</span><span class="sxs-lookup"><span data-stu-id="95ef7-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="95ef7-111">Sous l’onglet **Flux de données** , double-cliquez sur la source SAP BW.</span><span class="sxs-lookup"><span data-stu-id="95ef7-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="95ef7-112">Dans **l’Éditeur de source SAP BW**, cliquez sur **Avancé** pour ouvrir la page **Avancé** de l’éditeur.</span><span class="sxs-lookup"><span data-stu-id="95ef7-112">In the **SAP BW Source Editor**, click **Advanced** to open the **Advanced** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="95ef7-113">Options</span><span class="sxs-lookup"><span data-stu-id="95ef7-113">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="95ef7-114">Si vous ne connaissez pas toutes les valeurs requises pour configurer la source, adressez-vous à votre administrateur SAP.</span><span class="sxs-lookup"><span data-stu-id="95ef7-114">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="95ef7-115">**Conversion de chaîne**</span><span class="sxs-lookup"><span data-stu-id="95ef7-115">**String Conversion**</span></span>  
 <span data-ttu-id="95ef7-116">Spécifiez la règle à appliquer pour la conversion de chaîne.</span><span class="sxs-lookup"><span data-stu-id="95ef7-116">Specify the rule to apply for string conversion.</span></span>  
  
|<span data-ttu-id="95ef7-117">Option</span><span class="sxs-lookup"><span data-stu-id="95ef7-117">Option</span></span>|<span data-ttu-id="95ef7-118">Description</span><span class="sxs-lookup"><span data-stu-id="95ef7-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="95ef7-119">**Conversion de chaîne automatique**</span><span class="sxs-lookup"><span data-stu-id="95ef7-119">**Automatic string conversion**</span></span>|<span data-ttu-id="95ef7-120">Convertissez toutes les chaînes en `nvarchar` lorsque le système SAP Netweaver BW est un système Unicode.</span><span class="sxs-lookup"><span data-stu-id="95ef7-120">Convert all strings to `nvarchar` when the SAP Netweaver BW system is a Unicode system.</span></span> <span data-ttu-id="95ef7-121">Sinon, convertissez toutes les chaînes en `varchar`.</span><span class="sxs-lookup"><span data-stu-id="95ef7-121">Otherwise, convert all strings to `varchar`.</span></span>|  
|<span data-ttu-id="95ef7-122">**Convertir les chaînes en varchar**</span><span class="sxs-lookup"><span data-stu-id="95ef7-122">**Convert strings to varchar**</span></span>|<span data-ttu-id="95ef7-123">Convertissez toutes les chaînes en `varchar`.</span><span class="sxs-lookup"><span data-stu-id="95ef7-123">Convert all strings to `varchar`.</span></span>|  
|<span data-ttu-id="95ef7-124">**Convertir les chaînes en nvarchar**</span><span class="sxs-lookup"><span data-stu-id="95ef7-124">**Convert strings to nvarchar**</span></span>|<span data-ttu-id="95ef7-125">Convertissez toutes les chaînes en `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="95ef7-125">Convert all strings to `nvarchar`.</span></span>|  
  
 <span data-ttu-id="95ef7-126">**Délai d'attente (secondes)**</span><span class="sxs-lookup"><span data-stu-id="95ef7-126">**Timeout (seconds)**</span></span>  
 <span data-ttu-id="95ef7-127">Spécifiez le nombre maximal de secondes pendant lesquelles la source doit attendre.</span><span class="sxs-lookup"><span data-stu-id="95ef7-127">Specify the maximum number of seconds that the source should wait.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="95ef7-128">Cette option n’est valide que si vous avez sélectionné **A - Attendre la notification** comme valeur du **Mode d’exécution** dans la page **Gestionnaire de connexions** de l’éditeur.</span><span class="sxs-lookup"><span data-stu-id="95ef7-128">This option is only valid if you have selected **W - Wait for Notify** as the value of **Execution Mode** on the **Connection Manager** page of the editor.</span></span> <span data-ttu-id="95ef7-129">Pour plus d’informations, consultez [Éditeur de source SAP BW &#40;page Gestionnaire de connexions&#41;](sap-bw-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="95ef7-129">For more information, see [SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md).</span></span>  
  
 <span data-ttu-id="95ef7-130">**ID de la demande**</span><span class="sxs-lookup"><span data-stu-id="95ef7-130">**Request ID**</span></span>  
 <span data-ttu-id="95ef7-131">Spécifiez l’ID de demande dont vous voulez réinitialiser l’état sur « V - Vert » quand vous cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="95ef7-131">Specify the Request ID whose status you want to reset to "G - Green" when you click **Reset**.</span></span>  
  
 <span data-ttu-id="95ef7-132">**Réinitialiser**</span><span class="sxs-lookup"><span data-stu-id="95ef7-132">**Reset**</span></span>  
 <span data-ttu-id="95ef7-133">Vous permet de réinitialiser l'état de l'ID de demande spécifié sur « V - Vert », après l'invite de confirmation.</span><span class="sxs-lookup"><span data-stu-id="95ef7-133">Lets you reset the status of the specified Request ID to "G - Green", after prompting you for confirmation.</span></span> <span data-ttu-id="95ef7-134">Ce peut être utile lorsqu'un problème est survenu et que le système SAP Netweaver BW a marqué la demande avec un état jaune ou rouge.</span><span class="sxs-lookup"><span data-stu-id="95ef7-134">This can be useful when a problem has occurred, and the SAP Netweaver BW system has flagged the request with a yellow or red status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95ef7-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="95ef7-135">See Also</span></span>  
 <span data-ttu-id="95ef7-136">[Éditeur de source SAP BW &#40;page Gestionnaire de connexions&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="95ef7-136">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="95ef7-137">[Éditeur de source SAP BW &#40;page Colonnes&#41;](sap-bw-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="95ef7-137">[SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="95ef7-138">[Éditeur de source SAP BW &#40;page Sortie d’erreur&#41;](sap-bw-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="95ef7-138">[SAP BW Source Editor &#40;Error Output Page&#41;](sap-bw-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="95ef7-139">Aide (F1) sur Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="95ef7-139">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
