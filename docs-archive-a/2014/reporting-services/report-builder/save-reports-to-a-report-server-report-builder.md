---
title: Enregistrer des rapports sur un serveur de rapports (Générateur de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 48dfef01-ed8c-4f23-90c3-de67c90a97dd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d80e35c447593e89d422e72ea31ec6be34c3619f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707196"
---
# <a name="save-reports-to-a-report-server-report-builder"></a><span data-ttu-id="80cec-102">Enregistrer des rapports sur un serveur de rapports (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="80cec-102">Save Reports to a Report Server (Report Builder)</span></span>
  <span data-ttu-id="80cec-103">Dans le Générateur de rapports, vous pouvez enregistrer une définition de rapport sur un serveur de rapports (on parle également de publier un rapport).</span><span class="sxs-lookup"><span data-stu-id="80cec-103">In Report Builder, you can save a report definition to a report server (also known as publishing a report).</span></span> <span data-ttu-id="80cec-104">Le fait d'enregistrer un rapport sur un serveur de rapports permet aux autres utilisateurs de le consulter.</span><span class="sxs-lookup"><span data-stu-id="80cec-104">When the report is saved to a report server, other users can view the report.</span></span> <span data-ttu-id="80cec-105">Chaque fois que vous exécutez le rapport publié, vous récupérez les données les plus récentes.</span><span class="sxs-lookup"><span data-stu-id="80cec-105">Each time you run the published report, you will retrieve the most current data.</span></span> <span data-ttu-id="80cec-106">Pour enregistrer une copie statique d'un rapport rendu, exportez le rapport sous un format de fichier différent et enregistrez-le ou utilisez la fonctionnalité d'historique de rapport pour enregistrer des versions de rapports rendus.</span><span class="sxs-lookup"><span data-stu-id="80cec-106">To save a static copy of a rendered report, export the report to a different file format and save it or use the report history feature to save versions of rendered reports.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="80cec-107">L'emplacement de la définition de rapport enregistrée ne détermine pas si le rapport est traité sur le serveur ou en local lorsque vous affichez un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="80cec-107">The location of the saved report definition does not affect whether the report is processed on the server or processed locally when you preview the report.</span></span>  
  
### <a name="to-save-a-report-to-a-report-server"></a><span data-ttu-id="80cec-108">Pour enregistrer un rapport sur un serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="80cec-108">To save a report to a report server</span></span>  
  
1.  <span data-ttu-id="80cec-109">À partir du bouton Générateur de rapports, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="80cec-109">From the Report Builder button, click **Save**.</span></span> <span data-ttu-id="80cec-110">La boîte de dialogue **Enregistrer sous** _\<Report Item\>_ s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="80cec-110">The **Save As**_\<Report Item\>_ dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="80cec-111">Si vous réenregistrez un rapport, il est automatiquement stocké à son emplacement précédent.</span><span class="sxs-lookup"><span data-stu-id="80cec-111">If you are resaving a report, it is automatically resaved to its previous location.</span></span> <span data-ttu-id="80cec-112">Utilisez l'option Enregistrer sous pour modifier l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="80cec-112">Use the Save As option to change location.</span></span>  
  
2.  <span data-ttu-id="80cec-113">Cliquez éventuellement sur **Sites et serveurs récents** pour afficher une liste de serveurs de rapports et de sites SharePoint récemment utilisés.</span><span class="sxs-lookup"><span data-stu-id="80cec-113">Optionally, click **Recent Sites and Servers** to show a list of recently used report servers and SharePoint sites.</span></span>  
  
3.  <span data-ttu-id="80cec-114">Accédez à l'emplacement du serveur de rapports où vous souhaitez enregistrer le rapport.</span><span class="sxs-lookup"><span data-stu-id="80cec-114">Browse to the report server location where you want to save the report.</span></span>  
  
4.  <span data-ttu-id="80cec-115">Dans **Nom**, tapez le nom du rapport.</span><span class="sxs-lookup"><span data-stu-id="80cec-115">In **Name**, type the name of the report.</span></span>  
  
5.  <span data-ttu-id="80cec-116">Dans **Éléments de type**, sélectionnez le type d’élément de rapport à enregistrer.</span><span class="sxs-lookup"><span data-stu-id="80cec-116">In **Items of type**, select the type of report item you are saving.</span></span> <span data-ttu-id="80cec-117">Le type des rapports est Rapports (\*.rdl).</span><span class="sxs-lookup"><span data-stu-id="80cec-117">The type for reports is Reports(\*.rdl).</span></span>  
  
### <a name="to-save-a-report-as-a-different-name"></a><span data-ttu-id="80cec-118">Pour enregistrer un rapport sous un nom différent</span><span class="sxs-lookup"><span data-stu-id="80cec-118">To save a report as a different name</span></span>  
  
1.  <span data-ttu-id="80cec-119">À partir du bouton Générateur de rapports , cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="80cec-119">From the Report Builder button, click **Save As**.</span></span> <span data-ttu-id="80cec-120">La boîte de dialogue **Enregistrer sous** _\<Report Item\>_ s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="80cec-120">The **Save As**_\<Report Item\>_ dialog box opens.</span></span>  
  
2.  <span data-ttu-id="80cec-121">Naviguez jusqu'à l'emplacement du serveur de rapports ou jusqu'au partage de fichiers où vous souhaitez enregistrer le rapport.</span><span class="sxs-lookup"><span data-stu-id="80cec-121">Browse to the report server location or to the file share where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="80cec-122">Dans **Nom**, tapez le nom du rapport.</span><span class="sxs-lookup"><span data-stu-id="80cec-122">In **Name**, type the name of the report.</span></span>  
  
4.  <span data-ttu-id="80cec-123">Dans **Éléments de type**, sélectionnez le type d’élément de rapport à enregistrer.</span><span class="sxs-lookup"><span data-stu-id="80cec-123">In **Items of type**, select the type of report item you are saving.</span></span> <span data-ttu-id="80cec-124">Le type des rapports est Rapports (\*.rdl).</span><span class="sxs-lookup"><span data-stu-id="80cec-124">The type for reports is Reports(\*.rdl).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80cec-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="80cec-125">See Also</span></span>  
 <span data-ttu-id="80cec-126">[Recherche, affichage et gestion de rapports &#40;Générateur de rapports et SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="80cec-126">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="80cec-127">[Exportation de rapports &#40;Générateur de rapports et SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="80cec-127">[Exporting Reports &#40;Report Builder and SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="80cec-128">[Enregistrement des rapports &#40;Générateur de rapports&#41;](saving-reports-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="80cec-128">[Saving Reports &#40;Report Builder&#41;](saving-reports-report-builder.md) </span></span>  
 [<span data-ttu-id="80cec-129">Exporter un rapport dans un autre type de fichier &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="80cec-129">Export a Report as Another File Type &#40;Report Builder and SSRS&#41;</span></span>](../export-a-report-as-another-file-type-report-builder-and-ssrs.md)  
  
  
