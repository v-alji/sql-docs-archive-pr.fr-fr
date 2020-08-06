---
title: Éditeur de source SAP BW (page Sortie d’erreur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b6e23b0c-949a-46d1-8424-4dc3d9035e79
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a4ad2d02d3f5ec5c1a786019e18fa01665fdc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695895"
---
# <a name="sap-bw-source-editor-error-output-page"></a><span data-ttu-id="24a9c-102">Éditeur de source SAP BW (page Sortie d'erreur)</span><span class="sxs-lookup"><span data-stu-id="24a9c-102">SAP BW Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="24a9c-103">Utilisez la page **Sortie d'erreur** de l' **Éditeur de source SAP BW** pour sélectionner les options de gestion des erreurs et pour définir les propriétés des colonnes de sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="24a9c-103">Use the **Error Output** page of the **SAP BW Source Editor** to select error handling options and to set properties on error output columns.</span></span>  
  
 <span data-ttu-id="24a9c-104">Pour en savoir plus sur le composant source SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 pour SAP BW, consultez [SAP BW Source](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="24a9c-104">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="24a9c-105">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="24a9c-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="24a9c-106">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="24a9c-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="24a9c-107">Vous devez disposer d'une licence SAP supplémentaire pour extraire des données à partir de SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="24a9c-107">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="24a9c-108">Vérifiez auprès de SAP.</span><span class="sxs-lookup"><span data-stu-id="24a9c-108">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="24a9c-109">**Pour ouvrir la page Sortie d'erreur**</span><span class="sxs-lookup"><span data-stu-id="24a9c-109">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="24a9c-110">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui contient la source SAP BW.</span><span class="sxs-lookup"><span data-stu-id="24a9c-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="24a9c-111">Sous l’onglet **Flux de données** , double-cliquez sur la source SAP BW.</span><span class="sxs-lookup"><span data-stu-id="24a9c-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="24a9c-112">Dans l' **Éditeur de source SAP BW**, cliquez sur **Sortie d'erreur** pour ouvrir la page **Sortie d'erreur** de l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="24a9c-112">In the **SAP BW Source Editor**, click **Error Output** to open the **Error Output** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="24a9c-113">Options</span><span class="sxs-lookup"><span data-stu-id="24a9c-113">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="24a9c-114">Si vous ne connaissez pas toutes les valeurs requises pour configurer la source, adressez-vous à votre administrateur SAP.</span><span class="sxs-lookup"><span data-stu-id="24a9c-114">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="24a9c-115">**Entrée ou Sortie**</span><span class="sxs-lookup"><span data-stu-id="24a9c-115">**Input or Output**</span></span>  
 <span data-ttu-id="24a9c-116">Affichez le nom de la source de données.</span><span class="sxs-lookup"><span data-stu-id="24a9c-116">View the name of the data source.</span></span>  
  
 <span data-ttu-id="24a9c-117">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="24a9c-117">**Column**</span></span>  
 <span data-ttu-id="24a9c-118">Affichez les colonnes externes (source) que vous avez sélectionnées dans la page **Colonnes** de la boîte de dialogue **Éditeur de source SAP BW** .</span><span class="sxs-lookup"><span data-stu-id="24a9c-118">View the external (source) columns that you selected on the **Columns** page of the **SAP BW Source Editor** dialog box.</span></span> <span data-ttu-id="24a9c-119">Pour plus d’informations sur cette boîte de dialogue, consultez [Éditeur de source SAP BW &#40;page Colonnes&#41;](sap-bw-source-editor-columns-page.md).</span><span class="sxs-lookup"><span data-stu-id="24a9c-119">For more information about this dialog box, see [SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md).</span></span>  
  
 <span data-ttu-id="24a9c-120">**Error**</span><span class="sxs-lookup"><span data-stu-id="24a9c-120">**Error**</span></span>  
 <span data-ttu-id="24a9c-121">Spécifiez ce que le composant source SAP BW doit faire en cas d'erreur : ignorer l'échec, rediriger la ligne ou faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="24a9c-121">Specify what the SAP BW source component should do when there is an error: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="24a9c-122">**Troncation**</span><span class="sxs-lookup"><span data-stu-id="24a9c-122">**Truncation**</span></span>  
 <span data-ttu-id="24a9c-123">Spécifiez ce que le composant source SAP BW doit faire en cas de troncation : ignorer l'échec, rediriger la ligne ou faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="24a9c-123">Specify what the SAP BW source component should do when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="24a9c-124">**Description**</span><span class="sxs-lookup"><span data-stu-id="24a9c-124">**Description**</span></span>  
 <span data-ttu-id="24a9c-125">Affiche la description de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="24a9c-125">View the description of the error.</span></span>  
  
 <span data-ttu-id="24a9c-126">**Définir cette valeur sur les cellules sélectionnées**</span><span class="sxs-lookup"><span data-stu-id="24a9c-126">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="24a9c-127">Spécifiez ce que le composant source SAP BW doit faire pour l'ensemble des cellules sélectionnées lorsqu'une erreur ou une troncation se produit : ignorer l'échec, rediriger la ligne ou faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="24a9c-127">Specify what the SAP BW source component should do to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="24a9c-128">**Appliquer**</span><span class="sxs-lookup"><span data-stu-id="24a9c-128">**Apply**</span></span>  
 <span data-ttu-id="24a9c-129">Appliquez l'option de gestion des erreurs aux cellules sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="24a9c-129">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24a9c-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="24a9c-130">See Also</span></span>  
 <span data-ttu-id="24a9c-131">[Éditeur de source SAP BW &#40;page Gestionnaire de connexions&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="24a9c-131">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="24a9c-132">[Éditeur de source SAP BW &#40;page Colonnes&#41;](sap-bw-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="24a9c-132">[SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="24a9c-133">[Éditeur de source SAP BW &#40;page Avancé&#41;](sap-bw-source-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="24a9c-133">[SAP BW Source Editor &#40;Advanced Page&#41;](sap-bw-source-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="24a9c-134">Aide (F1) sur Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="24a9c-134">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
