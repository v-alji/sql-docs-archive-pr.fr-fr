---
title: Incorporer une image dans un rapport (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.embeddedimages.f1
- "10060"
ms.assetid: aed77345-5eeb-41f0-96c9-db6b4a11ec6f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6599092e0ef37dd9bbc15f4815c0315c77e7943b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695404"
---
# <a name="embed-an-image-in-a-report-report-builder-and-ssrs"></a><span data-ttu-id="93304-102">Incorporer une image dans un rapport (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="93304-102">Embed an Image in a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="93304-103">Un rapport peut inclure une image incorporée.</span><span class="sxs-lookup"><span data-stu-id="93304-103">A report can include an embedded image.</span></span> <span data-ttu-id="93304-104">L'incorporation garantit que l'image est toujours disponible pour un rapport, mais elle affecte la taille de la définition de rapport, le fichier qui définit le rapport.</span><span class="sxs-lookup"><span data-stu-id="93304-104">Embedding an image ensures that the image is always available to a report, but can affect the size of the report definition, the file that defines the report.</span></span> <span data-ttu-id="93304-105">Les images incorporées dans un rapport sont répertoriées dans le volet des données de rapport.</span><span class="sxs-lookup"><span data-stu-id="93304-105">The images embedded in a report are listed in the Report Data pane.</span></span>  
  
 <span data-ttu-id="93304-106">Vous pouvez incorporer une image dans la définition de rapport avant d'ajouter l'image à l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="93304-106">You might want to embed an image in the report definition before adding the image to the design surface.</span></span> <span data-ttu-id="93304-107">Pour plus d’informations, consultez [Ajouter une image d’arrière-plan &#40;Générateur de rapports et SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="93304-107">For more information, see [Add a Background Image &#40;Report Builder and SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-embed-an-image-in-a-report"></a><span data-ttu-id="93304-108">Pour incorporer une image dans un rapport</span><span class="sxs-lookup"><span data-stu-id="93304-108">To embed an image in a report</span></span>  
  
1.  <span data-ttu-id="93304-109">En mode Création de rapport, sous l’onglet **Insérer** , cliquez sur **Image**.</span><span class="sxs-lookup"><span data-stu-id="93304-109">In report design view, on the **Insert** tab, click **Image**.</span></span>  
  
2.  <span data-ttu-id="93304-110">Cliquez sur l'aire de conception, puis faites glisser la souris pour créer une zone de la taille voulue pour l'image.</span><span class="sxs-lookup"><span data-stu-id="93304-110">On the design surface, click and then drag a box to the desired size of the image.</span></span>  
  
3.  <span data-ttu-id="93304-111">Dans la page **Général** de la boîte de dialogue **Propriétés de l’image** , tapez un nom dans la zone de texte **Nom** ou acceptez le nom par défaut.</span><span class="sxs-lookup"><span data-stu-id="93304-111">In the **General** page of the **Image Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span>  
  
4.  <span data-ttu-id="93304-112">(Facultatif) Dans la zone de texte **Info-bulle** , tapez le texte qui doit s’afficher quand l’utilisateur pointe sur l’image dans le rapport rendu.</span><span class="sxs-lookup"><span data-stu-id="93304-112">(Optional) In the **ToolTip** text box, type the text that you want to appear when the user hovers over the image in the rendered report.</span></span>  
  
5.  <span data-ttu-id="93304-113">Dans **Sélectionner la source de l’image**, sélectionnez **Incorporé**.</span><span class="sxs-lookup"><span data-stu-id="93304-113">In **Select the image source**, select **Embedded**.</span></span>  
  
6.  <span data-ttu-id="93304-114">Cliquez sur le bouton **Importer** en regard de la zone de texte **Utiliser cette image** .</span><span class="sxs-lookup"><span data-stu-id="93304-114">Click the **Import** button next to the **Use this image** text box</span></span>  
  
7.  <span data-ttu-id="93304-115">Dans **Fichiers de type**, sélectionnez le type de fichier image, accédez au fichier, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="93304-115">In **Files of type**, select the image file type, navigate to the file, and then click **Open**.</span></span>  
  
8.  <span data-ttu-id="93304-116">Dans la boîte de dialogue **Propriétés de l’image** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="93304-116">In the **Image Properties** dialog box, click **OK**.</span></span>  
  
     <span data-ttu-id="93304-117">L'image s'affiche dans la zone que vous avez dessinée sur l'aire de conception, et le fichier s'affiche sous le dossier Images dans le volet des données de rapport.</span><span class="sxs-lookup"><span data-stu-id="93304-117">The image is displayed in the box you drew on the design surface, and the file is displayed under the Images folder in the Report Data pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="93304-118">Le type MIME (par exemple, bmp) est dérivé automatiquement lorsque l'image est importée.</span><span class="sxs-lookup"><span data-stu-id="93304-118">The MIME type (for example, bmp) is derived automatically when the image is imported.</span></span> <span data-ttu-id="93304-119">Pour modifier le type MIME, consultez la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="93304-119">To change the MIME type, see the next procedure.</span></span>  
  
### <a name="optional-to-change-the-mime-type-of-an-imported-image"></a><span data-ttu-id="93304-120">(Facultatif) Pour modifier le type MIME d'une image importée</span><span class="sxs-lookup"><span data-stu-id="93304-120">(optional) To change the MIME type of an imported image</span></span>  
  
1.  <span data-ttu-id="93304-121">Ouvrez le rapport en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="93304-121">Open the report in Design view.</span></span>  
  
2.  <span data-ttu-id="93304-122">Sélectionnez l'image sur l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="93304-122">Select the image on the design surface.</span></span> <span data-ttu-id="93304-123">Le volet **Propriétés** affiche les propriétés de l’image.</span><span class="sxs-lookup"><span data-stu-id="93304-123">The **Properties** pane displays the image properties.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="93304-124">Si le volet Propriétés n’est pas visible, cliquez sur **Propriétés** sous l’onglet **Affichage**.</span><span class="sxs-lookup"><span data-stu-id="93304-124">If the Properties pane is not visible, on the **View** tab, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="93304-125">Cliquez dans la zone de texte en regard de la propriété **MIMEType** et sélectionnez un nouveau type MIME dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="93304-125">Click in the text box next to the **MIMEType** property and select a new MIME type from the drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93304-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="93304-126">See Also</span></span>  
 <span data-ttu-id="93304-127">[Images &#40;Générateur de rapports et SSRS&#41;](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="93304-127">[Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="93304-128">[Ajouter une image liée à des données &#40;Générateur de rapports et SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="93304-128">[Add a Data-Bound Image &#40;Report Builder and SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="93304-129">Boîte de dialogue Propriétés de l’image, Général &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="93304-129">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
