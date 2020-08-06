---
title: Aperçu | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 551494c4-9e27-4592-9200-c6bf19e80c9a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a795338122c1e7a37a23fdb6af6153f74b927e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602917"
---
# <a name="preview"></a><span data-ttu-id="4586f-102">PRÉVERSION</span><span class="sxs-lookup"><span data-stu-id="4586f-102">Preview</span></span>
  <span data-ttu-id="4586f-103">Utilisez la boîte de dialogue **Aperçu** pour afficher un aperçu des données que la source SAP BW devra extraire.</span><span class="sxs-lookup"><span data-stu-id="4586f-103">Use the **Preview** dialog box to preview the data that the SAP BW source will extract.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4586f-104">L'option **Aperçu** , qui est disponible sur la page **Gestionnaire de connexions** de l' **Éditeur de source SAP BW**, extrait réellement des données.</span><span class="sxs-lookup"><span data-stu-id="4586f-104">The **Preview** option, that is available on the **Connection Manager** page of the **SAP BW Source Editor**, actually extracts data.</span></span> <span data-ttu-id="4586f-105">Si vous avez configuré le système SAP Netweaver BW pour extraire uniquement les données qui ont été modifiées depuis l'extraction précédente, la sélection d' **Aperçu** exclura les données de l'aperçu de l'extraction suivante.</span><span class="sxs-lookup"><span data-stu-id="4586f-105">If you have configured SAP Netweaver BW to extract only data that has changed since the previous extraction, selecting **Preview** will exclude the previewed data from the next extraction.</span></span>  
  
 <span data-ttu-id="4586f-106">Pour en savoir plus sur le composant source SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 pour SAP BW, consultez [SAP BW Source](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="4586f-106">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4586f-107">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="4586f-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="4586f-108">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="4586f-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4586f-109">Vous devez disposer d'une licence SAP supplémentaire pour extraire des données à partir de SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="4586f-109">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="4586f-110">Vérifiez auprès de SAP.</span><span class="sxs-lookup"><span data-stu-id="4586f-110">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="4586f-111">**Pour ouvrir la boîte de dialogue Aperçu**</span><span class="sxs-lookup"><span data-stu-id="4586f-111">**To open the Preview dialog box**</span></span>  
  
1.  <span data-ttu-id="4586f-112">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui contient la source SAP BW.</span><span class="sxs-lookup"><span data-stu-id="4586f-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="4586f-113">Sous l’onglet **Flux de données** , double-cliquez sur la source SAP BW.</span><span class="sxs-lookup"><span data-stu-id="4586f-113">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="4586f-114">Dans l' **Éditeur de source SAP BW**, cliquez sur **Gestionnaire de connexions** pour ouvrir la page **Gestionnaire de connexions** de l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="4586f-114">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="4586f-115">Configurez la source SAP BW.</span><span class="sxs-lookup"><span data-stu-id="4586f-115">Configure the SAP BW source.</span></span>  
  
5.  <span data-ttu-id="4586f-116">Après avoir configuré la source SAP BW, sur la page **Gestionnaire de connexions** , cliquez sur **Aperçu** pour afficher un aperçu des données dans la boîte de dialogue **Aperçu** .</span><span class="sxs-lookup"><span data-stu-id="4586f-116">After you configure the SAP BW source, on the **Connection Manager** page, click **Preview** to preview the data in the **Preview** dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4586f-117">Cliquer sur **Aperçu** ouvre également la boîte de dialogue **Journal des requêtes** .</span><span class="sxs-lookup"><span data-stu-id="4586f-117">Clicking **Preview** also opens the **Request Log** dialog box.</span></span> <span data-ttu-id="4586f-118">Pour plus d'informations sur cette boîte de dialogue, consultez [Request Log](request-log.md).</span><span class="sxs-lookup"><span data-stu-id="4586f-118">For more information about this dialog box, see [Request Log](request-log.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4586f-119">Options</span><span class="sxs-lookup"><span data-stu-id="4586f-119">Options</span></span>  
 <span data-ttu-id="4586f-120">La boîte de dialogue **Aperçu** affiche les lignes qui sont demandées par le système SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="4586f-120">The **Preview** dialog box displays the rows that are requested from the SAP Netweaver BW system.</span></span> <span data-ttu-id="4586f-121">Les colonnes qui sont affichées sont les colonnes qui sont définies dans les données sources.</span><span class="sxs-lookup"><span data-stu-id="4586f-121">The columns that are displayed are the columns that are defined in the source data.</span></span>  
  
 <span data-ttu-id="4586f-122">Il n'existe aucune autre option dans cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="4586f-122">There are no other options in this dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4586f-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4586f-123">See Also</span></span>  
 <span data-ttu-id="4586f-124">[Éditeur de source SAP BW &#40;page Gestionnaire de connexions&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="4586f-124">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="4586f-125">Aide (F1) sur Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="4586f-125">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
