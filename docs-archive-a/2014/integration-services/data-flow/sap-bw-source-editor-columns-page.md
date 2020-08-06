---
title: Éditeur de source SAP BW (page Colonnes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c2ec8bb7-be9b-4783-ad88-32512de784b0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ba605360d01abc520cedfbc457dd89319ed83c52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706611"
---
# <a name="sap-bw-source-editor-columns-page"></a><span data-ttu-id="0ed68-102">Éditeur de source SAP BW (page Colonnes)</span><span class="sxs-lookup"><span data-stu-id="0ed68-102">SAP BW Source Editor (Columns Page)</span></span>
  <span data-ttu-id="0ed68-103">Utilisez la page **Colonnes** de **l’Éditeur de source SAP BW** pour mapper une colonne de sortie à chaque colonne (source) externe.</span><span class="sxs-lookup"><span data-stu-id="0ed68-103">Use the **Columns** page of the **SAP BW Source Editor** to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="0ed68-104">Pour en savoir plus sur le composant source SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 pour SAP BW, consultez [SAP BW Source](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="0ed68-104">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0ed68-105">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="0ed68-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="0ed68-106">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="0ed68-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0ed68-107">Vous devez disposer d'une licence SAP supplémentaire pour extraire des données à partir de SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="0ed68-107">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="0ed68-108">Vérifiez auprès de SAP.</span><span class="sxs-lookup"><span data-stu-id="0ed68-108">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="0ed68-109">**Pour ouvrir la page Colonnes**</span><span class="sxs-lookup"><span data-stu-id="0ed68-109">**To open the Columns page**</span></span>  
  
1.  <span data-ttu-id="0ed68-110">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui contient la source SAP BW.</span><span class="sxs-lookup"><span data-stu-id="0ed68-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="0ed68-111">Sous l’onglet **Flux de données** , double-cliquez sur la source SAP BW.</span><span class="sxs-lookup"><span data-stu-id="0ed68-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="0ed68-112">Dans l' **Éditeur de source SAP BW**, cliquez sur **Colonnes** pour ouvrir la page **Colonnes** de l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="0ed68-112">In the **SAP BW Source Editor**, click **Columns** to open the **Columns** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0ed68-113">Options</span><span class="sxs-lookup"><span data-stu-id="0ed68-113">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ed68-114">Si vous ne connaissez pas toutes les valeurs requises pour configurer la source, adressez-vous à votre administrateur SAP.</span><span class="sxs-lookup"><span data-stu-id="0ed68-114">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="0ed68-115">**Colonnes externes disponibles**</span><span class="sxs-lookup"><span data-stu-id="0ed68-115">**Available External Columns**</span></span>  
 <span data-ttu-id="0ed68-116">Affichez la liste des colonnes externes disponibles dans la source de données, puis sélectionnez les colonnes à inclure dans le flux de données.</span><span class="sxs-lookup"><span data-stu-id="0ed68-116">View the list of available external columns in the data source, and then select the columns to be included in the data flow.</span></span>  
  
 <span data-ttu-id="0ed68-117">Pour inclure une colonne dans le flux de données, activez la case à cocher correspondant à cette colonne.</span><span class="sxs-lookup"><span data-stu-id="0ed68-117">To include a column in the data flow, select the check box that corresponds to that column.</span></span> <span data-ttu-id="0ed68-118">L'ordre dans lequel vous sélectionnez les cases à cocher détermine l'ordre dans lequel les colonnes sont générées.</span><span class="sxs-lookup"><span data-stu-id="0ed68-118">The order in which you select the check boxes determines the order in which columns will be output.</span></span> <span data-ttu-id="0ed68-119">Autrement dit, la première case à cocher que vous sélectionnez sera la première colonne de sortie, la deuxième case à cocher correspondra à la deuxième colonne de sortie, etc.</span><span class="sxs-lookup"><span data-stu-id="0ed68-119">That is, the first check box that you select will be the first output column, the second check box will be the second output columns, and so on.</span></span>  
  
 <span data-ttu-id="0ed68-120">**Colonne externe**</span><span class="sxs-lookup"><span data-stu-id="0ed68-120">**External Column**</span></span>  
 <span data-ttu-id="0ed68-121">Affichez les colonnes externes (source) que vous avez sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="0ed68-121">View the selected external (source) columns.</span></span> <span data-ttu-id="0ed68-122">Les colonnes sélectionnées apparaissent dans l'ordre dans lequel vous verrez les colonnes de sortie correspondantes lorsque vous configurerez les composants en aval qui consomment des données de cette source.</span><span class="sxs-lookup"><span data-stu-id="0ed68-122">The selected columns appear in the order in which you will see their corresponding output columns when you configure downstream components that consume data from this source.</span></span>  
  
 <span data-ttu-id="0ed68-123">Pour modifier l'ordre des colonnes, dans la liste **Colonnes externes disponibles** , désactivez les cases à cocher de toutes les colonnes.</span><span class="sxs-lookup"><span data-stu-id="0ed68-123">To change the order of the columns, in the **Available External Columns** list, clear the check boxes for all columns.</span></span> <span data-ttu-id="0ed68-124">Puis, sélectionnez les colonnes dans l'ordre d'apparition souhaité.</span><span class="sxs-lookup"><span data-stu-id="0ed68-124">Then, select the columns in the order that you want them to appear.</span></span>  
  
 <span data-ttu-id="0ed68-125">**Colonne de sortie**</span><span class="sxs-lookup"><span data-stu-id="0ed68-125">**Output Column**</span></span>  
 <span data-ttu-id="0ed68-126">Spécifiez un nom unique pour chaque colonne de sortie.</span><span class="sxs-lookup"><span data-stu-id="0ed68-126">Provide a unique name for each output column.</span></span> <span data-ttu-id="0ed68-127">La valeur par défaut correspond au nom de la colonne externe (source) sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0ed68-127">The default is the name of the selected external (source) column.</span></span> <span data-ttu-id="0ed68-128">Toutefois, vous pouvez entrer un nom descriptif unique.</span><span class="sxs-lookup"><span data-stu-id="0ed68-128">However, you can enter any unique, descriptive name.</span></span> [!INCLUDE[ssIS](../../includes/ssis-md.md)] <span data-ttu-id="0ed68-129">affiche les noms **Colonne de sortie** pour les colonnes lorsque vous configurez les composants en aval qui consomment des données de cette source.</span><span class="sxs-lookup"><span data-stu-id="0ed68-129">Designer will display the **Output Column** names for the columns when you configure downstream components that consume data from this source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ed68-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0ed68-130">See Also</span></span>  
 <span data-ttu-id="0ed68-131">[Éditeur de source SAP BW &#40;page Gestionnaire de connexions&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="0ed68-131">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="0ed68-132">[Éditeur de source SAP BW &#40;page Sortie d’erreur&#41;](sap-bw-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="0ed68-132">[SAP BW Source Editor &#40;Error Output Page&#41;](sap-bw-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="0ed68-133">[Éditeur de source SAP BW &#40;page Avancé&#41;](sap-bw-source-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="0ed68-133">[SAP BW Source Editor &#40;Advanced Page&#41;](sap-bw-source-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="0ed68-134">Aide (F1) sur Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="0ed68-134">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
