---
title: Éditeur de destination SAP BW (page Sortie d’erreur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a543d811-0bd2-4890-a0d3-f5fdcd4524b8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9ffd58580865a71626252aa2d177530e41156537
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695903"
---
# <a name="sap-bw-destination-editor-error-output-page"></a><span data-ttu-id="48add-102">Éditeur de destination SAP BW (page Sortie d'erreur)</span><span class="sxs-lookup"><span data-stu-id="48add-102">SAP BW Destination Editor (Error Output Page)</span></span>
  <span data-ttu-id="48add-103">Utilisez la page **Sortie d’erreur** de **l’Éditeur de destination SAP BW** pour définir les options de gestion des erreurs.</span><span class="sxs-lookup"><span data-stu-id="48add-103">Use the **Error Output** page of the **SAP BW Destination Editor** to specify error handling options.</span></span>  
  
 <span data-ttu-id="48add-104">Pour en savoir plus sur la destination SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 pour SAP BW, consultez [Destination SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="48add-104">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="48add-105">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="48add-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="48add-106">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="48add-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="48add-107">**Pour ouvrir la page Sortie d'erreur**</span><span class="sxs-lookup"><span data-stu-id="48add-107">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="48add-108">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui contient la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="48add-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="48add-109">Sous l’onglet **Flux de données** , double-cliquez sur la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="48add-109">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="48add-110">Dans **l’Éditeur de destination SAP BW**, cliquez sur **Sortie d’erreur** pour ouvrir la page **Sortie d’erreur** de l’éditeur.</span><span class="sxs-lookup"><span data-stu-id="48add-110">In the **SAP BW Destination Editor**, click **Error Output** to open the **Error Output** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="48add-111">Options</span><span class="sxs-lookup"><span data-stu-id="48add-111">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48add-112">Si vous ne connaissez pas toutes les valeurs requises pour configurer la destination, adressez-vous à votre administrateur SAP.</span><span class="sxs-lookup"><span data-stu-id="48add-112">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="48add-113">**Entrée ou Sortie**</span><span class="sxs-lookup"><span data-stu-id="48add-113">**Input or Output**</span></span>  
 <span data-ttu-id="48add-114">Affichez le nom de l'entrée.</span><span class="sxs-lookup"><span data-stu-id="48add-114">View the name of the input.</span></span>  
  
 <span data-ttu-id="48add-115">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="48add-115">**Column**</span></span>  
 <span data-ttu-id="48add-116">Cette option n'est pas utilisée.</span><span class="sxs-lookup"><span data-stu-id="48add-116">This option is not used.</span></span>  
  
 <span data-ttu-id="48add-117">**Error**</span><span class="sxs-lookup"><span data-stu-id="48add-117">**Error**</span></span>  
 <span data-ttu-id="48add-118">Spécifiez ce que la destination doit faire en cas d'erreur : ignorer l'échec, rediriger la ligne ou faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="48add-118">Specify what the destination should do when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="48add-119">**Troncation**</span><span class="sxs-lookup"><span data-stu-id="48add-119">**Truncation**</span></span>  
 <span data-ttu-id="48add-120">Cette option n'est pas utilisée.</span><span class="sxs-lookup"><span data-stu-id="48add-120">This option is not used.</span></span>  
  
 <span data-ttu-id="48add-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="48add-121">**Description**</span></span>  
 <span data-ttu-id="48add-122">Affichez la description de l'opération.</span><span class="sxs-lookup"><span data-stu-id="48add-122">View the description of the operation.</span></span>  
  
 <span data-ttu-id="48add-123">**Définir cette valeur sur les cellules sélectionnées**</span><span class="sxs-lookup"><span data-stu-id="48add-123">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="48add-124">Spécifiez ce que la destination doit faire pour l'ensemble des cellules sélectionnées lorsqu'une erreur ou une troncation se produit : ignorer l'échec, rediriger la ligne ou faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="48add-124">Specify what the destination should do to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="48add-125">**Appliquer**</span><span class="sxs-lookup"><span data-stu-id="48add-125">**Apply**</span></span>  
 <span data-ttu-id="48add-126">Appliquez l'option de gestion des erreurs aux cellules sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="48add-126">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48add-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="48add-127">See Also</span></span>  
 <span data-ttu-id="48add-128">[Éditeur de destination SAP BW &#40;page Gestionnaire de connexions&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="48add-128">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="48add-129">[Éditeur de destination SAP BW &#40;page Mappages&#41;](sap-bw-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="48add-129">[SAP BW Destination Editor &#40;Mappings Page&#41;](sap-bw-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="48add-130">[Éditeur de destination SAP BW &#40;page Avancé&#41;](sap-bw-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="48add-130">[SAP BW Destination Editor &#40;Advanced Page&#41;](sap-bw-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="48add-131">Aide (F1) sur Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="48add-131">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
