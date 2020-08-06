---
title: Boîte de dialogue remplissage (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.reportbody.fill.f1
- "10065"
- "10501"
- sql12.rtp.rptdesigner.shared.filldv.f1
- sql12.rtp.rptdesigner.rectangleproperties.fill.f1
- "10064"
- sql12.rtp.rptdesigner.textboxproperties.fill.f1
- "10124"
ms.assetid: 93a91d02-d558-4a0e-8d17-3fdf21e208d3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ae7f2b05d4d108c77f1dcae9ce7fefe5073e2522
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610462"
---
# <a name="fill-dialog-box-report-builder-and-ssrs"></a><span data-ttu-id="c280a-102">Boîte de dialogue Remplissage (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="c280a-102">Fill Dialog Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c280a-103">Sous l'onglet **Remplissage** , vous pouvez spécifier les options de couleur de l'arrière-plan d'une seule cellule ou de plusieurs cellules dans une région de données ou une zone de texte.</span><span class="sxs-lookup"><span data-stu-id="c280a-103">On the **Fill** tab, you can specify color options for the background of a single cell or multiple cells within a data region or a text box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c280a-104">Options</span><span class="sxs-lookup"><span data-stu-id="c280a-104">Options</span></span>  
 <span data-ttu-id="c280a-105">**Couleur de remplissage**</span><span class="sxs-lookup"><span data-stu-id="c280a-105">**Fill Color**</span></span>  
 <span data-ttu-id="c280a-106">Cliquez sur le bouton de couleur pour sélectionner une couleur de remplissage pour le rectangle.</span><span class="sxs-lookup"><span data-stu-id="c280a-106">Click the color button to select a fill color for the rectangle.</span></span> <span data-ttu-id="c280a-107">Cliquez sur le bouton **Expression**_(fx)_ pour modifier l’expression, qui peut être une valeur hexadécimale pour la couleur RVB ou l’un des noms de couleur prédéfinis fournis dans la boîte de dialogue **Expression** .</span><span class="sxs-lookup"><span data-stu-id="c280a-107">Click the **Expression**_(fx)_ button to edit the expression, which can be a hexadecimal value for the RGB color or one of the predefined color names that are provided in the **Expression** dialog box.</span></span> <span data-ttu-id="c280a-108">Pour afficher la liste des couleurs prédéfinies, sélectionnez **Web** dans le volet **Élément**.</span><span class="sxs-lookup"><span data-stu-id="c280a-108">To see a list of predefined colors, in the **Item** pane, select **Web**.</span></span> <span data-ttu-id="c280a-109">Les noms de couleur répertoriés dans le volet **Titre** peuvent être tapés dans le volet de texte de l'expression.</span><span class="sxs-lookup"><span data-stu-id="c280a-109">The color names listed in the **Title** pane can be typed into the expression text pane.</span></span> <span data-ttu-id="c280a-110">N'utilisez pas de signe égal (=) ou de guillemets ("") lorsque vous tapez le nom de couleur.</span><span class="sxs-lookup"><span data-stu-id="c280a-110">Do not use an equal sign (=) or quotation marks ("") when typing the color name.</span></span>  
  
 <span data-ttu-id="c280a-111">**Sélectionner la source de l'image**</span><span class="sxs-lookup"><span data-stu-id="c280a-111">**Select the image source**</span></span>  
 <span data-ttu-id="c280a-112">Indiquez l'endroit où l'image est stockée afin que lorsque le rapport est rendu, le processeur de rapports puisse l'afficher.</span><span class="sxs-lookup"><span data-stu-id="c280a-112">Indicate where the image is stored so that when the report is rendered, the report processor can display it.</span></span>  
  
-   <span data-ttu-id="c280a-113">**Externe** Choisissez cette option lorsque vous souhaitez que l'image continue à exister sous la forme d'un fichier sur un serveur de rapports ou un serveur Web.</span><span class="sxs-lookup"><span data-stu-id="c280a-113">**External** Choose this option when you want the image to continue to exist as a file on a report server or Web server.</span></span>  
  
-   <span data-ttu-id="c280a-114">**Rapport** Choisissez cette option lorsque vous souhaitez incorporer l’image dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="c280a-114">**Embedded** Choose this option when you want to embed the image into the report.</span></span>  
  
-   <span data-ttu-id="c280a-115">**Base de données** Choisissez cette option lorsque vous souhaitez inclure un nom de champ de base de données qui représente les images que vous souhaitez inclure dans votre rapport.</span><span class="sxs-lookup"><span data-stu-id="c280a-115">**Database** Choose this option when you want to include a database field name that represents the images that you want to include in your report.</span></span>  
  
 <span data-ttu-id="c280a-116">**Utiliser cette image**</span><span class="sxs-lookup"><span data-stu-id="c280a-116">**Use this image**</span></span>  
 <span data-ttu-id="c280a-117">Cette option s’affiche quand vous sélectionnez l’option **Rapport** ou **Externe** .</span><span class="sxs-lookup"><span data-stu-id="c280a-117">This option appears when you select the **Embedded** or **External** option.</span></span>  
  
 <span data-ttu-id="c280a-118">Si vous incorporez l’image, choisissez dans la liste déroulante l’image à ajouter au rapport.</span><span class="sxs-lookup"><span data-stu-id="c280a-118">If you are embedding the image, choose the picture that you want to add to the report from the drop-down list.</span></span> <span data-ttu-id="c280a-119">Cliquez sur **Importer** pour ajouter l’image à la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="c280a-119">Click **Import** to add the image to the drop-down list.</span></span> <span data-ttu-id="c280a-120">Si vous avez ajouté une image au volet **Données** , vous pouvez la sélectionner en choisissant **Rapport** , puis en sélectionnant l’image dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="c280a-120">If you added an image to the **Data** pane, you can select that image by choosing **Embedded** and then selecting the image from the drop-down list.</span></span>  
  
 <span data-ttu-id="c280a-121">Si vous sélectionnez l'option **Externe** , tapez l'URL de l'image.</span><span class="sxs-lookup"><span data-stu-id="c280a-121">If you select the **External** option, type the URL of the image.</span></span> <span data-ttu-id="c280a-122">Pour un rapport publié sur un serveur de rapports configuré pour le mode natif, utilisez un chemin d’accès complet ou relatif (par exemple, http:// *\<servername>* /images/image1.jpg).</span><span class="sxs-lookup"><span data-stu-id="c280a-122">For a report published to a report server configured for native mode, use a full or relative path (for example, http://*\<servername>*/images/image1.jpg).</span></span> <span data-ttu-id="c280a-123">Pour un rapport publié sur un serveur de rapports configuré en mode intégré SharePoint, utilisez une URL complète (par exemple, http:// *\<SharePointservername>/\<site>* /Documents/images/image1.jpg).</span><span class="sxs-lookup"><span data-stu-id="c280a-123">For a report published to a report server configured in SharePoint integrated mode, use a fully qualified URL (for example, http://*\<SharePointservername>/\<site>*/Documents/images/image1.jpg).</span></span>  
  
 <span data-ttu-id="c280a-124">**Importer**</span><span class="sxs-lookup"><span data-stu-id="c280a-124">**Import**</span></span>  
 <span data-ttu-id="c280a-125">Disponible quand vous sélectionnez **Rapport**.</span><span class="sxs-lookup"><span data-stu-id="c280a-125">Available when you select **Embedded**.</span></span> <span data-ttu-id="c280a-126">Cliquez pour ajouter une image à la liste déroulante **Utiliser cette image** .</span><span class="sxs-lookup"><span data-stu-id="c280a-126">Click to add an image to the **Use this image** drop-down list.</span></span>  
  
 <span data-ttu-id="c280a-127">**Utiliser ce champ**</span><span class="sxs-lookup"><span data-stu-id="c280a-127">**Use this field**</span></span>  
 <span data-ttu-id="c280a-128">Disponible quand vous sélectionnez **Base de données**.</span><span class="sxs-lookup"><span data-stu-id="c280a-128">Available when you select **Database**.</span></span> <span data-ttu-id="c280a-129">Sélectionnez le nom du champ.</span><span class="sxs-lookup"><span data-stu-id="c280a-129">Select the field name.</span></span>  
  
 <span data-ttu-id="c280a-130">**Utiliser ce type MIME**</span><span class="sxs-lookup"><span data-stu-id="c280a-130">**Use this MIME type**</span></span>  
 <span data-ttu-id="c280a-131">Choisissez le format approprié des images contenues dans la base de données (par exemple .bmp, .jpeg, .gif, .png ou .x-png).</span><span class="sxs-lookup"><span data-stu-id="c280a-131">Choose the appropriate format of the pictures contained in the database (for example, .bmp, .jpeg, .gif, .png, or .x-png).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c280a-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c280a-132">See Also</span></span>  
 <span data-ttu-id="c280a-133">[Mise en forme des éléments de rapport &#40;Générateur de rapports et SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c280a-133">[Formatting Report Items &#40;Report Builder and SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c280a-134">[Mise en forme du texte et des espaces réservés &#40;Générateur de rapports et SSRS&#41;](report-design/formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c280a-134">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](report-design/formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c280a-135">Images &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c280a-135">Images &#40;Report Builder and SSRS&#41;</span></span>](report-design/images-report-builder-and-ssrs.md)  
  
  
