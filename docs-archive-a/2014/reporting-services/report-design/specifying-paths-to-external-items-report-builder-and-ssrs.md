---
title: Spécification de chemins vers des éléments externes (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4fe513da-f3c5-479c-9fec-8662b91a0d6d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 097a3566f914e7810039ee07bc3d3bf3185d7f06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600514"
---
# <a name="specifying-paths-to-external-items-report-builder-and-ssrs"></a><span data-ttu-id="22e61-102">Spécification de chemins d'accès à des éléments externes (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="22e61-102">Specifying Paths to External Items (Report Builder and SSRS)</span></span>
  <span data-ttu-id="22e61-103">Vous pouvez spécifier des chemins d'accès dans les propriétés d'éléments de rapport pour faire référence à des éléments externes au fichier de définition de rapport et qui sont stockés sur un serveur de rapports. Il peut s'agir notamment de rapports d'extraction, de sous-rapports et de fichiers image.</span><span class="sxs-lookup"><span data-stu-id="22e61-103">You specify paths in report item properties to reference items such as drillthrough reports, subreports, and image files that are external to the report definition file and are stored on a report server.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="22e61-104">Dans le Générateur de rapports, les chemins d'accès aux éléments doivent indiquer des éléments stockés sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="22e61-104">In Report Builder, paths to items must specify items on a report server.</span></span> <span data-ttu-id="22e61-105">Les chemins d'accès aux éléments situés sur un système de fichiers ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="22e61-105">Paths to items on a file system are not supported.</span></span> <span data-ttu-id="22e61-106">Vous ne pouvez afficher l'aperçu d'un rapport qui utilise ces éléments que si vous êtes connecté au serveur de rapports où résident les éléments.</span><span class="sxs-lookup"><span data-stu-id="22e61-106">You can preview a report that uses these items only if you are connected to the report server where the items are located.</span></span>  
  
 <span data-ttu-id="22e61-107">Lorsque vous spécifiez un chemin d'accès à un élément externe dans une boîte de dialogue pour des actions, des sous-rapports ou des images, vous pouvez accéder directement au serveur de rapports et sélectionner l'élément.</span><span class="sxs-lookup"><span data-stu-id="22e61-107">When you specify a path for an external item in a dialog box for actions, subreports, or images, you can browse directly to the report server and select the item.</span></span> <span data-ttu-id="22e61-108">La méthode recommandée pour spécifier un rapport ou sous-rapport d'extraction consiste à accéder à un élément afin de le sélectionner directement.</span><span class="sxs-lookup"><span data-stu-id="22e61-108">Browsing to an item and selecting it directly is the recommended way to specify a drillthrough report or subreport.</span></span> <span data-ttu-id="22e61-109">De cette façon, les noms de paramètres appropriés vous seront présentés dans une liste déroulante au moment de spécifier les paramètres de rapport ou de sous-rapport.</span><span class="sxs-lookup"><span data-stu-id="22e61-109">That way the correct parameter names will be available in a drop-down list when you specify report or subreport parameters.</span></span> <span data-ttu-id="22e61-110">Lorsque vous modifiez un chemin d'accès d'élément pour en désigner un autre, vous devez mettre à jour manuellement les noms de paramètres corrects et les valeurs, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="22e61-110">When you change an item path to point to a different item, you must manually update the correct parameter names and values as needed.</span></span>  
  
 <span data-ttu-id="22e61-111">Sur un serveur de rapports configuré en mode natif, spécifiez un nom de rapport d'extraction sans l'extension de fichier .rdl.</span><span class="sxs-lookup"><span data-stu-id="22e61-111">On a report server configured in native mode, specify a drillthrough report name without the file extension .rdl.</span></span>  
  
 <span data-ttu-id="22e61-112">Sur un serveur de rapports configuré en mode intégré SharePoint, vous devez inclure l'extension de fichier .rdl.</span><span class="sxs-lookup"><span data-stu-id="22e61-112">On a report server configured in SharePoint integrated mode, you must include the file extension .rdl.</span></span> <span data-ttu-id="22e61-113">Le chemin d'accès peut prendre l'une des formes suivantes :</span><span class="sxs-lookup"><span data-stu-id="22e61-113">The path can be one of the following:</span></span>  
  
-   <span data-ttu-id="22e61-114">**Un chemin d'accès relatif à l'élément du rapport principal.**</span><span class="sxs-lookup"><span data-stu-id="22e61-114">**A relative path to the item from the main report.**</span></span> <span data-ttu-id="22e61-115">Par exemple, ../AllSubreports/Subreport1.</span><span class="sxs-lookup"><span data-stu-id="22e61-115">For example, ../AllSubreports/Subreport1.</span></span> <span data-ttu-id="22e61-116">Dans cet exemple, le symbole **..**</span><span class="sxs-lookup"><span data-stu-id="22e61-116">In this example, the **..**</span></span> <span data-ttu-id="22e61-117">désigne le dossier situé au-dessus du dossier où réside le rapport principal.</span><span class="sxs-lookup"><span data-stu-id="22e61-117">indicates the folder above the folder where the main report is located.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="22e61-118">Les chemins d'accès relatifs ne sont pas pris en charge lorsque le rapport est exécuté à l'intérieur du Générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="22e61-118">Relative paths are not supported when the report is run inside Report Builder.</span></span> <span data-ttu-id="22e61-119">Pour afficher un rapport qui utilise des chemins d'accès relatifs à des éléments externes, enregistrez le rapport sur le serveur de rapports, puis exécutez-le depuis ce dernier.</span><span class="sxs-lookup"><span data-stu-id="22e61-119">To view a report that uses relative paths to external items, save the report to the report server, and run the report from there</span></span>  
  
-   <span data-ttu-id="22e61-120">**Un chemin d'accès complet à l'élément.**</span><span class="sxs-lookup"><span data-stu-id="22e61-120">**A full path to the item.**</span></span>  
  
    -   <span data-ttu-id="22e61-121">**Sur un serveur de rapports :** le chemin d’accès commence par **/** , le dossier de base.</span><span class="sxs-lookup"><span data-stu-id="22e61-121">**On a report server:** The path starts from **/**, the Home folder.</span></span> <span data-ttu-id="22e61-122">Par exemple, /Reports/AllSubreports/Subreport1.</span><span class="sxs-lookup"><span data-stu-id="22e61-122">For example, /Reports/AllSubreports/Subreport1.</span></span>  
  
    -   <span data-ttu-id="22e61-123">**Sur un site SharePoint :** vous devez spécifier le nom de rapport dans une expression en incluant l'URL complète de l'élément et l'extension de fichier .rdl.</span><span class="sxs-lookup"><span data-stu-id="22e61-123">**On a SharePoint site:** You must specify the report name in an expression, with the full URL of the item and the file extension .rdl.</span></span> <span data-ttu-id="22e61-124">Par exemple : `="http://server/site/library/folder/Report1.rdl"`.</span><span class="sxs-lookup"><span data-stu-id="22e61-124">For example, `="http://server/site/library/folder/Report1.rdl"`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22e61-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="22e61-125">See Also</span></span>  
 <span data-ttu-id="22e61-126">[Ajouter une image externe &#40;Générateur de rapports et SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="22e61-126">[Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="22e61-127">[Ajouter un sous-rapport et des paramètres &#40;Générateur de rapports et SSRS&#41;](add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="22e61-127">[Add a Subreport and Parameters &#40;Report Builder and SSRS&#41;](add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="22e61-128">Ajouter une action d’extraction à un rapport &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="22e61-128">Add a Drillthrough Action on a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-drillthrough-action-on-a-report-report-builder-and-ssrs.md)  
  
  
