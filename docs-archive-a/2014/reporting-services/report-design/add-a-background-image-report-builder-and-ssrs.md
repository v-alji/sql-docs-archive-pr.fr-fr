---
title: Ajouter une image d’arrière-plan (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c777fefb-8695-44a7-b5cd-a18c587583f2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d7bc15e1b063a73c463cdb1e7e99075af2a3dce9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707168"
---
# <a name="add-a-background-image-report-builder-and-ssrs"></a><span data-ttu-id="00b9a-102">Ajouter une image d'arrière-plan (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="00b9a-102">Add a Background Image (Report Builder and SSRS)</span></span>
  <span data-ttu-id="00b9a-103">Vous pouvez ajouter une image d'arrière-plan à un élément de rapport, par exemple un rectangle, une zone de texte, une liste, une matrice, un tableau et certaines parties d'un graphique, ou à une section de rapport, par exemple l'en-tête de page, le pied de page ou le corps du rapport.</span><span class="sxs-lookup"><span data-stu-id="00b9a-103">You can add a background image to a report item such as a rectangle, text box, list, matrix, table, and some parts of a chart, or a report section such as the page header, page footer, or report body.</span></span> <span data-ttu-id="00b9a-104">Vous pouvez définir une image d’arrière-plan pour tout élément sélectionné sur l’aire de conception du rapport qui affiche **BackgroundImage** dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="00b9a-104">You can define a background image for any selected item on the report design surface that displays **BackgroundImage** in the Properties pane.</span></span> <span data-ttu-id="00b9a-105">Comme les autres images, l'image d'arrière-plan peut être une URL vers une image sur le serveur de rapports, une image d'un champ de dataset ou une image incorporée dans la définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="00b9a-105">Like other images, the background image can be a URL to an image on the report server, an image from a dataset field, or an image embedded in the report definition.</span></span> <span data-ttu-id="00b9a-106">Pour utiliser une image incorporée dans le rapport, vous devez d'abord ajouter l'image à la définition de rapport avant d'ajouter l'image à l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="00b9a-106">To use an image embedded in the report, you must first add the image to the report definition before you can add the image to the design surface.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-embed-an-image-in-the-report-definition"></a><span data-ttu-id="00b9a-107">Pour incorporer une image dans la définition de rapport</span><span class="sxs-lookup"><span data-stu-id="00b9a-107">To embed an image in the report definition</span></span>  
  
1.  <span data-ttu-id="00b9a-108">Dans le volet des données de rapport, cliquez avec le bouton droit sur le nœud **Images** , puis cliquez sur **Ajouter une image**.</span><span class="sxs-lookup"><span data-stu-id="00b9a-108">In the Report Data pane, right-click the **Images** node, and then click **Add Image**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="00b9a-109">Si le volet des données de rapport n’est pas visible, cliquez sur **Données du rapport** sous l’onglet **Affichage**.</span><span class="sxs-lookup"><span data-stu-id="00b9a-109">If the Report Data pane is not visible, on the **View** tab, click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="00b9a-110">Accédez à l’image à incorporer dans votre définition de rapport, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="00b9a-110">Navigate to the image you want to embed in your report definition, and then click **OK**.</span></span>  
  
### <a name="to-add-a-background-image"></a><span data-ttu-id="00b9a-111">Pour ajouter une image d'arrière-plan</span><span class="sxs-lookup"><span data-stu-id="00b9a-111">To add a background image</span></span>  
  
1.  <span data-ttu-id="00b9a-112">En mode création de rapport, sélectionnez l'élément de rapport auquel ajouter une image d'arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="00b9a-112">In report design view, select the report item to which you want to add a background image.</span></span>  
  
2.  <span data-ttu-id="00b9a-113">Si le volet Propriétés n’est pas visible, sélectionnez **Propriétés** sous l’onglet **Affichage**.</span><span class="sxs-lookup"><span data-stu-id="00b9a-113">If the Properties pane is not visible, on the **View** tab, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="00b9a-114">Dans le volet Propriétés, développez **BackgroundImage**et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="00b9a-114">In the Properties pane, expand **BackgroundImage**, and then do the following:</span></span>  
  
    -   <span data-ttu-id="00b9a-115">Pour une image incorporée :</span><span class="sxs-lookup"><span data-stu-id="00b9a-115">For an embedded image:</span></span>  
  
         <span data-ttu-id="00b9a-116">Affectez **Embedded** à **Source**.</span><span class="sxs-lookup"><span data-stu-id="00b9a-116">Set **Source** to **Embedded**.</span></span>  
  
         <span data-ttu-id="00b9a-117">Affectez le nom d’une image incorporée dans le rapport à **Value** .</span><span class="sxs-lookup"><span data-stu-id="00b9a-117">Set **Value** to the name of an image that is embedded in the report.</span></span>  
  
    -   <span data-ttu-id="00b9a-118">Pour une image externe :</span><span class="sxs-lookup"><span data-stu-id="00b9a-118">For an external image:</span></span>  
  
         <span data-ttu-id="00b9a-119">Affectez **External** à **Source**.</span><span class="sxs-lookup"><span data-stu-id="00b9a-119">Set **Source** to **External**.</span></span>  
  
         <span data-ttu-id="00b9a-120">Affectez le chemin valide d’une image à **Value** .</span><span class="sxs-lookup"><span data-stu-id="00b9a-120">Set **Value** to a valid path to an image.</span></span> <span data-ttu-id="00b9a-121">Il peut s'agir d'un serveur de rapports en mode natif ou en mode intégré SharePoint, ou il peut s'agir d'un autre site Web.</span><span class="sxs-lookup"><span data-stu-id="00b9a-121">This can be on a report server in native mode or SharePoint integrated mode, or it can be on any other Web site.</span></span> <span data-ttu-id="00b9a-122">Pour plus d’informations, consultez [Ajouter une image externe &#40;Générateur de rapports et SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="00b9a-122">For more information, see [Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md).</span></span>  
  
    -   <span data-ttu-id="00b9a-123">Pour une image contenue dans un champ de la base de données à laquelle l'élément de rapport est connecté :</span><span class="sxs-lookup"><span data-stu-id="00b9a-123">For an image is that is contained in a field in the database to which the report item is connected:</span></span>  
  
         <span data-ttu-id="00b9a-124">Affectez **Database** à **Source**.</span><span class="sxs-lookup"><span data-stu-id="00b9a-124">Set **Source** to **Database**.</span></span>  
  
         <span data-ttu-id="00b9a-125">Affectez le nom d’un champ dans le dataset du rapport à **Value** .</span><span class="sxs-lookup"><span data-stu-id="00b9a-125">Set **Value** to the name of a field in the report dataset.</span></span> <span data-ttu-id="00b9a-126">Pour plus d’informations, consultez [Ajouter une image liée à des données &#40;Générateur de rapports et SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="00b9a-126">For more information, see [Add a Data-Bound Image &#40;Report Builder and SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md).</span></span>  
  
         <span data-ttu-id="00b9a-127">Pour **MIMEType**, ou le format de fichier, sélectionnez le type MIME approprié pour l’image, par exemple .bmp.</span><span class="sxs-lookup"><span data-stu-id="00b9a-127">For **MIMEType**, or file format, select the appropriate MIME type for the image-for example, .bmp.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="00b9a-128">MIMEType s’applique uniquement si la propriété **Source** a la valeur **Database**.</span><span class="sxs-lookup"><span data-stu-id="00b9a-128">MIMEType applies only if the **Source** property is set to **Database**.</span></span> <span data-ttu-id="00b9a-129">Si la propriété **Source** a la valeur **External** ou **Embedded**, la valeur de **MIMEType** est ignorée.</span><span class="sxs-lookup"><span data-stu-id="00b9a-129">If the **Source** property is set to **External** or **Embedded**, the value of **MIMEType** is ignored.</span></span>  
  
    -   <span data-ttu-id="00b9a-130">Pour **BackgroundRepeat**, sélectionnez une expression : **Default**, **Repeat**, **RepeatX**ou **RepeatY**, ou **Clip**.</span><span class="sxs-lookup"><span data-stu-id="00b9a-130">For **BackgroundRepeat**, select an expression, **Default**, **Repeat**, **RepeatX**, or **RepeatY**, or **Clip**.</span></span>  
  
         <span data-ttu-id="00b9a-131">Pour les images d’arrière-plan d’un graphique, **BackgroundRepeat** peut avoir la valeur **Default**, **Repeat**, **Fit** **Clip**, mais pas **RepeatX** ni **RepeatY**.</span><span class="sxs-lookup"><span data-stu-id="00b9a-131">For background images in a chart, **BackgroundRepeat** can be set to **Default**, **Repeat**, **Fit**, and **Clip**, but not **RepeatX** or **RepeatY**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00b9a-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="00b9a-132">See Also</span></span>  
 <span data-ttu-id="00b9a-133">[Images &#40;Générateur de rapports et SSRS&#41;](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="00b9a-133">[Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="00b9a-134">Boîte de dialogue Propriétés de l’image, Général &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="00b9a-134">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
