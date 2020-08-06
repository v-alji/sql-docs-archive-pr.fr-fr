---
title: Rechercher la chaîne de processus | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f6303ea4-fbbf-4cba-bc60-828df62be8c2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2e0d3743071d018a8a82f60eeaf04fd86dec3e63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700073"
---
# <a name="look-up-process-chain"></a><span data-ttu-id="08026-102">Rechercher la chaîne de processus</span><span class="sxs-lookup"><span data-stu-id="08026-102">Look Up Process Chain</span></span>
  <span data-ttu-id="08026-103">Utilisez la boîte de dialogue **Rechercher la chaîne de processus** pour rechercher une chaîne de processus qui est définie dans le système SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="08026-103">Use the **Look Up Process Chain** dialog box to look up a process chain that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="08026-104">Lorsque la liste de chaînes de processus disponibles apparaît, sélectionnez la chaîne de votre choix. La source remplira les options associées à l'aide des valeurs requises.</span><span class="sxs-lookup"><span data-stu-id="08026-104">When the list of available process chains appears, select the chain that you want, and the source will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="08026-105">La source SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 pour SAP BW utilise la boîte de dialogue **Rechercher la chaîne de processus** .</span><span class="sxs-lookup"><span data-stu-id="08026-105">The SAP BW source of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW uses the **Look Up Process Chain** dialog box.</span></span> <span data-ttu-id="08026-106">Pour en savoir plus sur la source SAP BW, consultez [SAP BW Source](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="08026-106">To learn more about the SAP BW source, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="08026-107">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="08026-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="08026-108">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="08026-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="08026-109">**Pour ouvrir la boîte de dialogue Rechercher la chaîne de processus**</span><span class="sxs-lookup"><span data-stu-id="08026-109">**To open the Look Up Process Chain dialog box**</span></span>  
  
1.  <span data-ttu-id="08026-110">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui contient la source SAP BW.</span><span class="sxs-lookup"><span data-stu-id="08026-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="08026-111">Sous l’onglet **Flux de données** , double-cliquez sur la source SAP BW.</span><span class="sxs-lookup"><span data-stu-id="08026-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="08026-112">Dans l' **Éditeur de source SAP BW**, cliquez sur **Gestionnaire de connexions** pour ouvrir la page **Gestionnaire de connexions** de l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="08026-112">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="08026-113">Dans la zone de groupe **Chaîne de processus** , cliquez sur **Rechercher** pour afficher la boîte de dialogue **Rechercher la chaîne de processus** .</span><span class="sxs-lookup"><span data-stu-id="08026-113">In the **Process Chain** group box, click **Look up** to display the **Look Up Process Chain** dialog box.</span></span>  
  
     <span data-ttu-id="08026-114">La zone de groupe **Chaîne de processus** apparaît uniquement si la valeur de **Mode d’exécution** est **P - Déclencher une chaîne de processus**.</span><span class="sxs-lookup"><span data-stu-id="08026-114">The **Process Chain** group box appears only if the value for **Execution mode** is **P - Trigger process chain**.</span></span>  
  
## <a name="lookup-options"></a><span data-ttu-id="08026-115">Options de recherche</span><span class="sxs-lookup"><span data-stu-id="08026-115">Lookup Options</span></span>  
 <span data-ttu-id="08026-116">Dans les champs de recherche, vous pouvez filtrer les résultats à l'aide du caractère générique astérisque (\*), ou en utilisant une chaîne partielle conjointement avec le caractère générique astérisque.</span><span class="sxs-lookup"><span data-stu-id="08026-116">In the lookup fields, you can filter results by using the asterisk wildcard character (\*), or by using a partial string in combination with the asterisk wildcard character.</span></span> <span data-ttu-id="08026-117">Cependant, si vous laissez un champ de recherche vide, l'opération de recherche mettra uniquement en correspondance les chaînes vides de ce champ.</span><span class="sxs-lookup"><span data-stu-id="08026-117">However, if you leave a lookup field empty, the lookup operation will only match empty strings in that field.</span></span>  
  
 <span data-ttu-id="08026-118">**Chaîne de processus**</span><span class="sxs-lookup"><span data-stu-id="08026-118">**Process chain**</span></span>  
 <span data-ttu-id="08026-119">Entrez le nom de la chaîne de processus à rechercher, ou entrez un nom partiel avec le caractère générique astérisque (\*).</span><span class="sxs-lookup"><span data-stu-id="08026-119">Enter the name of the process chain that you want to look up, or enter a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="08026-120">Sinon, utilisez le caractère générique astérisque seul pour inclure toutes les chaînes de processus.</span><span class="sxs-lookup"><span data-stu-id="08026-120">Or, use the asterisk wildcard character alone to include all process chains.</span></span>  
  
 <span data-ttu-id="08026-121">**Rechercher**</span><span class="sxs-lookup"><span data-stu-id="08026-121">**Look up**</span></span>  
 <span data-ttu-id="08026-122">Recherchez des chaînes de processus correspondantes définies dans le système SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="08026-122">Look up matching process chains that are defined in the SAP Netweaver BW system.</span></span>  
  
## <a name="lookup-results"></a><span data-ttu-id="08026-123">Résultats de la recherche</span><span class="sxs-lookup"><span data-stu-id="08026-123">Lookup Results</span></span>  
 <span data-ttu-id="08026-124">Après avoir cliqué sur le bouton Rechercher, une liste de chaînes de processus dans le système SAP Netweaver BW apparaît dans un tableau avec les en-têtes de colonnes suivants :</span><span class="sxs-lookup"><span data-stu-id="08026-124">After you click the Look up button, a list of the process chains in the SAP Netweaver BW system appears in a table with the following column headings:</span></span>  
  
 <span data-ttu-id="08026-125">**Chaîne de processus**</span><span class="sxs-lookup"><span data-stu-id="08026-125">**Process Chain**</span></span>  
 <span data-ttu-id="08026-126">Affiche le nom de la chaîne de processus qui est définie dans le système SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="08026-126">Displays the name of the process chain that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="08026-127">**Description**</span><span class="sxs-lookup"><span data-stu-id="08026-127">**Description**</span></span>  
 <span data-ttu-id="08026-128">Affiche la description de la chaîne de processus.</span><span class="sxs-lookup"><span data-stu-id="08026-128">Displays the description of the process chain.</span></span>  
  
 <span data-ttu-id="08026-129">Lorsque la liste de chaînes de processus disponibles apparaît, sélectionnez la chaîne de votre choix. La source remplira les options associées à l'aide des valeurs requises.</span><span class="sxs-lookup"><span data-stu-id="08026-129">When the list of available process chains appears, select the chain that you want, and the source will populate the associated options with the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08026-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="08026-130">See Also</span></span>  
 <span data-ttu-id="08026-131">[Éditeur de source SAP BW &#40;page Gestionnaire de connexions&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="08026-131">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="08026-132">Aide (F1) sur Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="08026-132">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
