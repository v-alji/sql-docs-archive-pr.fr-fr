---
title: Générer des flux de données à partir d’un rapport (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e68baae2-9f2a-4f13-9179-9ac7f29111c5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 340191396aaaa92fe14fe8c3c6b42539a713eb45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600610"
---
# <a name="generate-data-feeds-from-a-report-report-builder-and-ssrs"></a><span data-ttu-id="d809f-102">Générer des flux de données à partir d'un rapport (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="d809f-102">Generate Data Feeds from a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d809f-103">Vous pouvez générer des flux de données conformes à Atom à partir de rapports, puis utiliser les flux de données dans des applications, telles que le [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] client, qui peuvent consommer des flux de données.</span><span class="sxs-lookup"><span data-stu-id="d809f-103">You can generate Atom-compliant data feeds from reports, and then use the data feeds in applications, such as the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] client, that can consume data feeds.</span></span>  
  
 <span data-ttu-id="d809f-104">L'extension de rendu Atom [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] génère un document de service Atom qui répertorie les flux de données disponibles d'un rapport.</span><span class="sxs-lookup"><span data-stu-id="d809f-104">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Atom rendering extension generates an Atom service document that lists the data feeds available from a report.</span></span> <span data-ttu-id="d809f-105">Le document répertorie au moins un flux de données pour chaque région de données du rapport.</span><span class="sxs-lookup"><span data-stu-id="d809f-105">The document lists at least one data feed for each data region in the report.</span></span> <span data-ttu-id="d809f-106">Selon le type de région de données et les données affichées par cette région, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] peut générer plusieurs flux de données à partir d'une région de données.</span><span class="sxs-lookup"><span data-stu-id="d809f-106">Depending on the type of data region and the data that the data region displays, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] might generate multiple data feeds from a data region.</span></span>  
  
 <span data-ttu-id="d809f-107">Le document de service Atom contient un identificateur unique pour chaque flux de données. Par ailleurs, vous utilisez cet identificateur dans une URL afin d'afficher le contenu du flux de données.</span><span class="sxs-lookup"><span data-stu-id="d809f-107">Atom service document contains a unique identifier for each the data feed and you use the identifier in a URL to view the content of the data feed.</span></span>  
  
 <span data-ttu-id="d809f-108">Pour plus d’informations, consultez [génération de flux de données à partir de rapports &#40;générateur de rapports et SSRS&#41;](generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d809f-108">For more information, see [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-generate-an-atom-service-document"></a><span data-ttu-id="d809f-109">Pour générer un document de service Atom</span><span class="sxs-lookup"><span data-stu-id="d809f-109">To generate an Atom service document</span></span>  
  
1.  <span data-ttu-id="d809f-110">À partir de la page **Accueil** du Gestionnaire de rapports, naviguez jusqu'au rapport que vous souhaitez utiliser pour générer des flux de données.</span><span class="sxs-lookup"><span data-stu-id="d809f-110">From the Report Manager **Home** page, navigate to the report from which you want to generate data feeds.</span></span>  
  
2.  <span data-ttu-id="d809f-111">Cliquez sur le rapport.</span><span class="sxs-lookup"><span data-stu-id="d809f-111">Click the report.</span></span>  
  
     <span data-ttu-id="d809f-112">Le rapport s'exécute.</span><span class="sxs-lookup"><span data-stu-id="d809f-112">The report is run.</span></span>  
  
3.  <span data-ttu-id="d809f-113">Dans la barre d'outils, cliquez sur l'icône Exporter vers un flux de données.</span><span class="sxs-lookup"><span data-stu-id="d809f-113">On the toolbar, click the Export to Data Feed icon.</span></span>  
  
     <span data-ttu-id="d809f-114">Un message s'affiche pour vous demander si vous souhaitez enregistrer ou ouvrir le document Atom qui contient le flux de données.</span><span class="sxs-lookup"><span data-stu-id="d809f-114">A message appears asking you if you want to save or open the atom document that contains the data feed.</span></span>  
  
4.  <span data-ttu-id="d809f-115">Cliquez sur **Enregistrer** pour enregistrer le document dans le système de fichiers, ou cliquez sur **Ouvrir** pour afficher le contenu du document avant de l'enregistrer.</span><span class="sxs-lookup"><span data-stu-id="d809f-115">Click **Save** to save the document to the file system, or click **Open** to view the document content before saving.</span></span> <span data-ttu-id="d809f-116">**Par défaut, le document s'ouvre dans un navigateur.**</span><span class="sxs-lookup"><span data-stu-id="d809f-116">**By default, the document opens in a browser.**</span></span>  
  
5.  <span data-ttu-id="d809f-117">Accédez à l'emplacement d'enregistrement du document.</span><span class="sxs-lookup"><span data-stu-id="d809f-117">Browse to the location to save the document.</span></span>  
  
6.  <span data-ttu-id="d809f-118">Modifiez éventuellement le nom du document.</span><span class="sxs-lookup"><span data-stu-id="d809f-118">Optionally, change the name of the document.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d809f-119">Par défaut, le nom du document correspond au nom du rapport.</span><span class="sxs-lookup"><span data-stu-id="d809f-119">By default, the document name is the report name.</span></span>  
  
7.  <span data-ttu-id="d809f-120">Assurez-vous que le type du document est **Fichier ATOMSVC**, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d809f-120">Verify the document type is **ATOMSVC File**, and then click **Save**.</span></span>  
  
8.  <span data-ttu-id="d809f-121">Si vous le souhaitez, ouvrez le fichier .atomsvc dans un navigateur, un éditeur de texte ou un éditeur XML.</span><span class="sxs-lookup"><span data-stu-id="d809f-121">Optionally, open the .atomsvc file in a browser or text or XML editor.</span></span>  
  
### <a name="to-view-an-atom-compliant-data-feed"></a><span data-ttu-id="d809f-122">Pour afficher un flux de données conforme à Atom</span><span class="sxs-lookup"><span data-stu-id="d809f-122">To view an Atom-compliant data feed</span></span>  
  
1.  <span data-ttu-id="d809f-123">Si le document de service Atom n'est pas déjà ouvert, recherchez ce dernier et ouvrez-le dans un navigateur tel qu'Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="d809f-123">If the Atom service document is not already open, locate it and open it in a browser such as Internet Explorer.</span></span>  
  
2.  <span data-ttu-id="d809f-124">Copiez l'URL du flux de données que vous souhaitez afficher à partir du document de service Atom dans le navigateur.</span><span class="sxs-lookup"><span data-stu-id="d809f-124">Copy the URL of the data feed that you want to view from the Atom service document to the browser.</span></span>  
  
     <span data-ttu-id="d809f-125">Le format de l'URL est le suivant :</span><span class="sxs-lookup"><span data-stu-id="d809f-125">The format of the URL is the following:</span></span>  
  
 `http://<server name>/ReportServer?%2f<ReportName>rs%3aCommand=Render&rs%3aFormat=ATOM&rc%3aDataFeed=<Identifier>`  
  
1.  <span data-ttu-id="d809f-126">Appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="d809f-126">Press ENTER.</span></span>  
  
     <span data-ttu-id="d809f-127">Un message s'affiche pour vous demander si vous souhaitez enregistrer ou ouvrir le document Atom qui contient le flux de données.</span><span class="sxs-lookup"><span data-stu-id="d809f-127">A message appears asking you if you want to save or open the atom document that contains the data feed.</span></span>  
  
2.  <span data-ttu-id="d809f-128">Cliquez sur **Enregistrer** pour enregistrer le document dans le système de fichiers, ou cliquez sur **Ouvrir** pour afficher le flux de données avant de l'enregistrer.</span><span class="sxs-lookup"><span data-stu-id="d809f-128">Click **Save** to save the document to the file system, or click **Open** to view the data feed before saving.</span></span>  
  
3.  <span data-ttu-id="d809f-129">Accédez à l'emplacement d'enregistrement du document.</span><span class="sxs-lookup"><span data-stu-id="d809f-129">Browse to the location to save the document.</span></span>  
  
4.  <span data-ttu-id="d809f-130">Modifiez éventuellement le nom du document.</span><span class="sxs-lookup"><span data-stu-id="d809f-130">Optionally, change the name of the document.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d809f-131">Par défaut, le nom du document correspond au nom du rapport.</span><span class="sxs-lookup"><span data-stu-id="d809f-131">By default the document name is the report name.</span></span> <span data-ttu-id="d809f-132">Si le document de service Atom contient plusieurs flux, ils utilisent tous le même nom par défaut, à savoir le nom du rapport.</span><span class="sxs-lookup"><span data-stu-id="d809f-132">If the Atom service document has multiple feeds, by default all use the same name, the report name.</span></span> <span data-ttu-id="d809f-133">Pour les différencier, renommez-les à l'aide de noms explicites.</span><span class="sxs-lookup"><span data-stu-id="d809f-133">To differentiate them, rename them to use meaningful names.</span></span>  
  
5.  <span data-ttu-id="d809f-134">Assurez-vous que le type du document est **Fichier ATOM**, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d809f-134">Verify the document type is **ATOM File**, and then click **Save**.</span></span>  
  
6.  <span data-ttu-id="d809f-135">Si vous le souhaitez, ouvrez le fichier .atom dans un navigateur, un éditeur de texte ou un éditeur XML.</span><span class="sxs-lookup"><span data-stu-id="d809f-135">Optionally, open the .atom file in a browser or text editor or XML editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d809f-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d809f-136">See Also</span></span>  
 [<span data-ttu-id="d809f-137">Exportation de rapports &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d809f-137">Exporting Reports &#40;Report Builder and SSRS&#41;</span></span>](export-reports-report-builder-and-ssrs.md)  
  
  
