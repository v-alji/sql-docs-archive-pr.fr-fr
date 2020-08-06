---
title: Boîte de dialogue Propriétés de l’image, général (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10051"
- sql12.rtp.rptdesigner.pictureproperties.general.f1
ms.assetid: c2218b93-f7fe-46ef-995f-d7dadf9752ec
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e599a437ae367a38483dbde99ffff79f64b957ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710351"
---
# <a name="image-properties-dialog-box-general-report-builder-and-ssrs"></a><span data-ttu-id="18d5b-102">Boîte de dialogue Propriétés de l'image, Général (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="18d5b-102">Image Properties Dialog Box, General (Report Builder and SSRS)</span></span>
  <span data-ttu-id="18d5b-103">Sélectionnez **Général** dans la boîte de dialogue **Propriétés de l’image** pour ajouter une image, changer le nom par défaut de l’image et ajouter le texte de l’info-bulle.</span><span class="sxs-lookup"><span data-stu-id="18d5b-103">Select **General** on the **Image Properties** dialog box to add a picture, change the default name of the image, and add ToolTip text.</span></span>  
  
## <a name="options"></a><span data-ttu-id="18d5b-104">Options</span><span class="sxs-lookup"><span data-stu-id="18d5b-104">Options</span></span>  
 <span data-ttu-id="18d5b-105">**Nom**</span><span class="sxs-lookup"><span data-stu-id="18d5b-105">**Name**</span></span>  
 <span data-ttu-id="18d5b-106">Tapez le nom de l'élément.</span><span class="sxs-lookup"><span data-stu-id="18d5b-106">Type a name for the item.</span></span> <span data-ttu-id="18d5b-107">Ce nom doit être unique dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="18d5b-107">The name must be unique within the report.</span></span> <span data-ttu-id="18d5b-108">Par défaut, un nom général, tel qu'Image1 ou Image2, est assigné.</span><span class="sxs-lookup"><span data-stu-id="18d5b-108">By default, a general name, such as Image1 or Image2, is assigned.</span></span>  
  
 <span data-ttu-id="18d5b-109">**Info-bulle**</span><span class="sxs-lookup"><span data-stu-id="18d5b-109">**Tooltip**</span></span>  
 <span data-ttu-id="18d5b-110">Tapez du texte ou une expression qui se transforme en info-bulle.</span><span class="sxs-lookup"><span data-stu-id="18d5b-110">Type text or an expression that evaluates to a ToolTip.</span></span> <span data-ttu-id="18d5b-111">Cliquez sur le bouton Expression (*fx*) pour modifier l’expression.</span><span class="sxs-lookup"><span data-stu-id="18d5b-111">Click the Expression (*fx*) button to edit the expression.</span></span> <span data-ttu-id="18d5b-112">L’ **info-bulle** apparaît quand l’utilisateur place le pointeur sur l’élément dans un rapport HTML.</span><span class="sxs-lookup"><span data-stu-id="18d5b-112">The **Tooltip** appears when the user pauses the pointer over the item in an HTML report.</span></span>  
  
 <span data-ttu-id="18d5b-113">**Sélectionner la source de l'image**</span><span class="sxs-lookup"><span data-stu-id="18d5b-113">**Select the image source**</span></span>  
 <span data-ttu-id="18d5b-114">Indiquez l'endroit où l'image est stockée afin que lorsque le rapport est rendu, le processeur de rapports sache où la chercher.</span><span class="sxs-lookup"><span data-stu-id="18d5b-114">Indicate where the image is stored so that when the report is rendered, the report processor will know where to get the image from.</span></span>  
  
-   <span data-ttu-id="18d5b-115">**Externe** Choisissez cette option lorsque vous souhaitez que l'image continue à exister sous la forme d'un fichier sur un serveur de rapports ou un serveur Web.</span><span class="sxs-lookup"><span data-stu-id="18d5b-115">**External** Choose this option when you want the image to continue to exist as a file on a report server or Web server.</span></span>  
  
-   <span data-ttu-id="18d5b-116">**Rapport** Choisissez cette option lorsque vous souhaitez incorporer l’image dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="18d5b-116">**Embedded** Choose this option when you want to embed the image into the report.</span></span>  
  
-   <span data-ttu-id="18d5b-117">**Base de données** Choisissez cette option lorsque vous souhaitez inclure un nom de champ de base de données qui représente les images que vous souhaitez inclure dans votre rapport.</span><span class="sxs-lookup"><span data-stu-id="18d5b-117">**Database** Choose this option when you want to include a database field name that represents the images that you want to include in your report.</span></span>  
  
 <span data-ttu-id="18d5b-118">**Utiliser cette image**</span><span class="sxs-lookup"><span data-stu-id="18d5b-118">**Use this image**</span></span>  
 <span data-ttu-id="18d5b-119">Cette option s’affiche quand vous sélectionnez l’option **Rapport** ou **Externe** .</span><span class="sxs-lookup"><span data-stu-id="18d5b-119">This option appears when you select the **Embedded** or **External** option.</span></span>  
  
 <span data-ttu-id="18d5b-120">Si vous incorporez l'image, choisissez l'image que vous souhaitez ajouter au rapport dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="18d5b-120">If you are embedding the image, choose the image that you want to add to the report from the drop-down list.</span></span> <span data-ttu-id="18d5b-121">Cliquez sur le bouton **Importer** pour ajouter l’image à la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="18d5b-121">Click the **Import** button to add the image to the drop-down list.</span></span>  
  
 <span data-ttu-id="18d5b-122">Si vous sélectionnez l'option **Externe** , tapez l'URL de l'image.</span><span class="sxs-lookup"><span data-stu-id="18d5b-122">If you select the **External** option, type the URL of the image.</span></span> <span data-ttu-id="18d5b-123">Pour un rapport publié sur un serveur de rapports configuré pour le mode natif, utilisez un chemin d'accès complet ou relatif.</span><span class="sxs-lookup"><span data-stu-id="18d5b-123">For a report published to a report server configured for native mode, use a full or relative path.</span></span> <span data-ttu-id="18d5b-124">Par exemple, http:// \<servername> /images/image1.jpg.</span><span class="sxs-lookup"><span data-stu-id="18d5b-124">For example, http://\<servername>/images/image1.jpg.</span></span> <span data-ttu-id="18d5b-125">Pour un rapport publié sur un serveur de rapports configuré en mode intégré SharePoint, utilisez une URL complète.</span><span class="sxs-lookup"><span data-stu-id="18d5b-125">For a report published to a report server configured in SharePoint integrated mode, use a fully qualified URL.</span></span> <span data-ttu-id="18d5b-126">Par exemple, http:// \<*SharePointservername*> / \<*site*> /Documents/images/image1.jpg.</span><span class="sxs-lookup"><span data-stu-id="18d5b-126">For example, http://\<*SharePointservername*>/\<*site*>/Documents/images/image1.jpg.</span></span>  
  
 <span data-ttu-id="18d5b-127">**Importer**</span><span class="sxs-lookup"><span data-stu-id="18d5b-127">**Import**</span></span>  
 <span data-ttu-id="18d5b-128">Cliquez pour ajouter une image à la liste déroulante **Utiliser cette image** .</span><span class="sxs-lookup"><span data-stu-id="18d5b-128">Click to add an image to the **Use this image** drop-down list.</span></span>  
  
 <span data-ttu-id="18d5b-129">**Utiliser ce champ**</span><span class="sxs-lookup"><span data-stu-id="18d5b-129">**Use this field**</span></span>  
 <span data-ttu-id="18d5b-130">Cette option apparaît si vous avez sélectionné l’option **Base de données** .</span><span class="sxs-lookup"><span data-stu-id="18d5b-130">This option appears if you select the **Database** option.</span></span> <span data-ttu-id="18d5b-131">Sélectionnez le nom du champ.</span><span class="sxs-lookup"><span data-stu-id="18d5b-131">Select the field name.</span></span>  
  
 <span data-ttu-id="18d5b-132">**Utiliser ce type MIME**</span><span class="sxs-lookup"><span data-stu-id="18d5b-132">**Use this MIME type**</span></span>  
 <span data-ttu-id="18d5b-133">Choisissez le format approprié des images contenues dans la base de données, par exemple .bmp, .jpeg, .gif, .png et .x-png.</span><span class="sxs-lookup"><span data-stu-id="18d5b-133">Choose the appropriate format of the images contained in the database, for example, .bmp, .jpeg, .gif, .png, and .x-png.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18d5b-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="18d5b-134">See Also</span></span>  
 <span data-ttu-id="18d5b-135">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="18d5b-135">[Expression Examples &#40;Report Builder and SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="18d5b-136">[Images &#40;Générateur de rapports et SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="18d5b-136">[Images &#40;Report Builder and SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="18d5b-137">Aide du Générateur de rapports pour les boîtes de dialogue, les volets et les Assistants</span><span class="sxs-lookup"><span data-stu-id="18d5b-137">Report Builder Help for Dialog Boxes, Panes, and Wizards</span></span>](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md)  
  
  
