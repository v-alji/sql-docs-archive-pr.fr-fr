---
title: Changer les icônes d’indicateur et jeux d’indicateurs (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8a056adf-4473-473d-9b0c-314675af7bfd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 398d21319ab6da22f2b10c3607baf8f110d6e65b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706207"
---
# <a name="change-indicator-icons-and-indicator-sets-report-builder-and-ssrs"></a><span data-ttu-id="09830-102">Modifier les icônes d'indicateur et jeux d'indicateurs (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="09830-102">Change Indicator Icons and Indicator Sets (Report Builder and SSRS)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="09830-103">fournit des jeux d'indicateurs préconfigurés, qui peuvent ne pas toujours représenter efficacement vos données ni fonctionner correctement dans le rapport remis.</span><span class="sxs-lookup"><span data-stu-id="09830-103">provides preconfigured indicators sets, which might not always depict your data effectively and work well in the delivered report.</span></span> <span data-ttu-id="09830-104">Cette rubrique fournit des procédures permettant de modifier l'apparence des icônes d'indicateur et les jeux d'indicateurs pour inclure plus ou moins d'icônes d'indicateur, ou d'autres icônes d'indicateur.</span><span class="sxs-lookup"><span data-stu-id="09830-104">This topic provides procedures to change the appearance of indicator icons and change the indicator sets to include different, more, or fewer indicator icons.</span></span>  
  
 <span data-ttu-id="09830-105">Les options telles que les couleurs peuvent être définies à l'aide d'expressions.</span><span class="sxs-lookup"><span data-stu-id="09830-105">Options such as colors can be set by using expressions.</span></span> <span data-ttu-id="09830-106">Pour plus d’informations, consultez [Expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="09830-106">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-color-of-an-indicator-icon"></a><span data-ttu-id="09830-107">Pour modifier la couleur d'une icône d'indicateur</span><span class="sxs-lookup"><span data-stu-id="09830-107">To change the color of an indicator icon</span></span>  
  
1.  <span data-ttu-id="09830-108">Cliquez avec le bouton droit sur l’indicateur à modifier, puis cliquez sur **Propriétés de l’indicateur**.</span><span class="sxs-lookup"><span data-stu-id="09830-108">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="09830-109">Cliquez sur **Valeur et états** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="09830-109">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="09830-110">Cliquez sur la flèche vers le bas dans la colonne **Couleur** en regard de l’icône que vous souhaitez changer et cliquez sur la couleur à utiliser, **Aucune couleur**ou **Couleurs supplémentaires**.</span><span class="sxs-lookup"><span data-stu-id="09830-110">Click the down arrow in the **Color** column next to the icon that you want to change and click the color to use, **No Color**, or **More colors**.</span></span>  
  
     <span data-ttu-id="09830-111">Cliquez éventuellement sur le bouton **Expression** (*fx*) pour modifier une expression qui définit la valeur de l’option **Couleur** .</span><span class="sxs-lookup"><span data-stu-id="09830-111">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the **Color** option.</span></span>  
  
     <span data-ttu-id="09830-112">Si vous avez cliqué sur **Couleurs supplémentaires**, la boîte de dialogue **Sélectionner une couleur** s’ouvre, dans laquelle vous pouvez choisir parmi un grand nombre de couleurs.</span><span class="sxs-lookup"><span data-stu-id="09830-112">If you clicked **More Colors**, the **Select Color** dialog box opens, where you can choose from a wide array of colors.</span></span> <span data-ttu-id="09830-113">Pour plus d’informations sur ses options, consultez [Boîte de dialogue Sélectionner une couleur &#40;Générateur de rapports et SSRS&#41;](../select-color-dialog-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="09830-113">For more information about its options, see [Select Color Dialog Box &#40;Report Builder and SSRS&#41;](../select-color-dialog-box-report-builder-and-ssrs.md).</span></span> <span data-ttu-id="09830-114">Cliquez sur **OK** pour fermer la boîte de dialogue **Sélectionner une couleur** .</span><span class="sxs-lookup"><span data-stu-id="09830-114">Click **OK** to close the **Select Color** dialog box.</span></span>  
  
4.  <span data-ttu-id="09830-115">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="09830-115">Click **OK**.</span></span>  
  
### <a name="to-change-the-icon"></a><span data-ttu-id="09830-116">Pour modifier l'icône</span><span class="sxs-lookup"><span data-stu-id="09830-116">To change the icon</span></span>  
  
1.  <span data-ttu-id="09830-117">Cliquez avec le bouton droit sur l’indicateur à modifier, puis cliquez sur **Propriétés de l’indicateur**.</span><span class="sxs-lookup"><span data-stu-id="09830-117">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="09830-118">Cliquez sur **Valeur et états** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="09830-118">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="09830-119">Cliquez sur la flèche vers le bas en regard de l'icône que vous souhaitez changer et sélectionnez une icône différente.</span><span class="sxs-lookup"><span data-stu-id="09830-119">Click the down arrow next to the icon that you want to change and select a different icon.</span></span>  
  
     <span data-ttu-id="09830-120">Cliquez éventuellement sur le bouton **Expression** (*fx*) pour modifier une expression qui définit la valeur de l’option **Icône** .</span><span class="sxs-lookup"><span data-stu-id="09830-120">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the **Icon** option.</span></span>  
  
4.  <span data-ttu-id="09830-121">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="09830-121">Click **OK**.</span></span>  
  
### <a name="to-use-a-custom-image-as-an-indicator-icon"></a><span data-ttu-id="09830-122">Pour utiliser une image personnalisée comme icône d'indicateur</span><span class="sxs-lookup"><span data-stu-id="09830-122">To use a custom image as an indicator icon</span></span>  
  
1.  <span data-ttu-id="09830-123">Cliquez avec le bouton droit sur l’indicateur à modifier, puis cliquez sur **Propriétés de l’indicateur**.</span><span class="sxs-lookup"><span data-stu-id="09830-123">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="09830-124">Cliquez sur **Valeur et états** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="09830-124">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="09830-125">Cliquez sur la flèche vers le bas en regard de l’icône que vous souhaitez changer et sélectionnez **Image**.</span><span class="sxs-lookup"><span data-stu-id="09830-125">Click the down arrow next to the icon that you wan to change and select **Image**.</span></span>  
  
4.  <span data-ttu-id="09830-126">Dans la liste **Sélectionner la source de l’image** , cliquez sur **Externe**, **Rapport**ou **Base de données**.</span><span class="sxs-lookup"><span data-stu-id="09830-126">In the **Select the image source** list, click **External**, **Embedded**, or **Database**.</span></span>  
  
5.  <span data-ttu-id="09830-127">Selon la source de l'image, procédez de l'une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="09830-127">Depending on the source of the image, do the one of the following:</span></span>  
  
    -   <span data-ttu-id="09830-128">Pour utiliser une image stockée hors du rapport, cliquez sur **Parcourir** et recherchez l’image.</span><span class="sxs-lookup"><span data-stu-id="09830-128">To use an image that is stored externally to the report, click **Browse** and locate the image.</span></span> <span data-ttu-id="09830-129">Le rapport inclura une référence à l'image.</span><span class="sxs-lookup"><span data-stu-id="09830-129">The report will include a reference to the image.</span></span>  
  
    -   <span data-ttu-id="09830-130">Pour utiliser une image incorporée dans le rapport, cliquez sur **Importer** et recherchez l’image.</span><span class="sxs-lookup"><span data-stu-id="09830-130">To use an image that is embedded in the report, click **Import** and locate the image.</span></span> <span data-ttu-id="09830-131">L'image sera ajoutée à la définition de rapport et enregistrée avec celle-ci.</span><span class="sxs-lookup"><span data-stu-id="09830-131">The image will be added to the report definition and saved with it.</span></span>  
  
    -   <span data-ttu-id="09830-132">Pour utiliser une image qui est dans une base de données, dans la liste **Utiliser ce champ** ,</span><span class="sxs-lookup"><span data-stu-id="09830-132">To use an image that is in a database, in the **Use this field** list.</span></span> <span data-ttu-id="09830-133">sélectionnez le champ de la liste, puis dans la liste **Utiliser ce type MIME** , sélectionnez le type MIME de l’image.</span><span class="sxs-lookup"><span data-stu-id="09830-133">select the field from the list and then in the **Use this MIME type** list, select the MIME type of the image.</span></span>  
  
6.  <span data-ttu-id="09830-134">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="09830-134">Click **OK**.</span></span>  
  
### <a name="to-add-an-icon-to-the-indicator-set"></a><span data-ttu-id="09830-135">Pour ajouter une icône au jeu d'indicateurs</span><span class="sxs-lookup"><span data-stu-id="09830-135">To add an icon to the indicator set</span></span>  
  
1.  <span data-ttu-id="09830-136">Cliquez avec le bouton droit sur l’indicateur à modifier, puis cliquez sur **Propriétés de l’indicateur**.</span><span class="sxs-lookup"><span data-stu-id="09830-136">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="09830-137">Cliquez sur **Valeur et états** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="09830-137">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="09830-138">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="09830-138">Click **Add**.</span></span> <span data-ttu-id="09830-139">Un indicateur est ajouté, à l’aide de l’icône par défaut et de l’option **Aucune couleur** .</span><span class="sxs-lookup"><span data-stu-id="09830-139">An indicator is added, using the default icon and the **No Color** option.</span></span>  
  
     <span data-ttu-id="09830-140">Configurez l'indicateur pour utiliser l'icône et la couleur souhaitées.</span><span class="sxs-lookup"><span data-stu-id="09830-140">Configure the indictor to use the icon and color you want.</span></span> <span data-ttu-id="09830-141">Les procédures plus haut dans cette rubrique décrivent les étapes de cette opération.</span><span class="sxs-lookup"><span data-stu-id="09830-141">Procedures earlier in this topic describe the steps to do this.</span></span>  
  
4.  <span data-ttu-id="09830-142">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="09830-142">Click **OK**.</span></span>  
  
### <a name="to-delete-an-icon-to-the-indicator-set"></a><span data-ttu-id="09830-143">Pour supprimer une icône du jeu d'indicateurs</span><span class="sxs-lookup"><span data-stu-id="09830-143">To delete an icon to the indicator set</span></span>  
  
1.  <span data-ttu-id="09830-144">Cliquez avec le bouton droit sur l’indicateur à modifier, puis cliquez sur **Propriétés de l’indicateur**.</span><span class="sxs-lookup"><span data-stu-id="09830-144">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="09830-145">Cliquez sur **Valeur et états** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="09830-145">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="09830-146">Sélectionnez l’icône à supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="09830-146">Select the icon to delete, and click **Delete**.</span></span>  
  
4.  <span data-ttu-id="09830-147">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="09830-147">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09830-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="09830-148">See Also</span></span>  
 [<span data-ttu-id="09830-149">Indicateurs &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="09830-149">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
