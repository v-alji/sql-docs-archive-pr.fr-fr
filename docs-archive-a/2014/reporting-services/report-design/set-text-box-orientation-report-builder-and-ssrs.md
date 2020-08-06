---
title: Définir l’orientation d’une zone de texte (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 64bd53f4-2f31-4732-8c2e-64c7b54b6972
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d509f1df29203fa5def79b61b74ae9db8f40d204
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600530"
---
# <a name="set-text-box-orientation-report-builder-and-ssrs"></a><span data-ttu-id="516e4-102">Définir l'orientation d'une zone de texte (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="516e4-102">Set Text Box Orientation (Report Builder and SSRS)</span></span>
  <span data-ttu-id="516e4-103">Une zone de texte peut être orientée dans différentes directions : horizontalement, verticalement (texte lu de haut en bas) ou rotation de 270 degrés (texte lu de bas en haut).</span><span class="sxs-lookup"><span data-stu-id="516e4-103">A text box can be oriented in different directions: horizontally, vertically (text reading from top to bottom), or rotated by 270 degrees (text reading from bottom to top).</span></span> <span data-ttu-id="516e4-104">Étant donné que l'orientation concerne la zone de texte, et non le texte, elle s'applique à l'ensemble du texte dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="516e4-104">Because orientation is set on the text box not the text, the orientation applies to all the text in the text box.</span></span> <span data-ttu-id="516e4-105">Vous ne pouvez pas spécifier d'orientations différentes pour certaines parties du texte.</span><span class="sxs-lookup"><span data-stu-id="516e4-105">You cannot specify different orientations for parts of the text.</span></span> <span data-ttu-id="516e4-106">Dimensionnez manuellement la largeur de colonne et la hauteur de ligne pour les adapter au texte pivoté.</span><span class="sxs-lookup"><span data-stu-id="516e4-106">Size the column width and the row height manually to accommodate the rotated text.</span></span>  
  
 <span data-ttu-id="516e4-107">La propriété WritingMode, que vous utilisez pour spécifier l’orientation du texte, n’est pas disponible dans la boîte de dialogue Propriétés de la **zone de texte** .</span><span class="sxs-lookup"><span data-stu-id="516e4-107">The WritingMode property, which you use to specify text orientation, is not available in the **Text Box Properties** dialog box.</span></span> <span data-ttu-id="516e4-108">Vous devez ouvrir le volet Propriétés et y définir la propriété.</span><span class="sxs-lookup"><span data-stu-id="516e4-108">You need to open the Properties pane and set the property there.</span></span> <span data-ttu-id="516e4-109">Les valeurs disponibles pour la propriété WritingMode sont **horizontales** (texte lu de gauche à droite), **vertical** (texte lu de haut en bas), **Rotate270** (texte lu de bas en haut).</span><span class="sxs-lookup"><span data-stu-id="516e4-109">The available values for the WritingMode property are **Horizontal** (text reading left to right), **Vertical** (text reading top to bottom), **Rotate270** (text reading bottom to top).</span></span> <span data-ttu-id="516e4-110">Vous devez dimensionner manuellement la largeur de colonne et la hauteur de ligne pour ajuster le texte.</span><span class="sxs-lookup"><span data-stu-id="516e4-110">You must manually size the column width and the row height to accommodate the text.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-text-orientation"></a><span data-ttu-id="516e4-111">Pour définir l'orientation du texte</span><span class="sxs-lookup"><span data-stu-id="516e4-111">To set text orientation</span></span>  
  
1.  <span data-ttu-id="516e4-112">Créez un rapport ou ouvrez-en un qui existe déjà.</span><span class="sxs-lookup"><span data-stu-id="516e4-112">Create a new report or open an existing report.</span></span>  
  
2.  <span data-ttu-id="516e4-113">Si le volet Propriétés n'est pas ouvert, cliquez sur l'onglet **Affichage** et activez la case à cocher **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="516e4-113">If the Properties pane is not open, click the **View** tab and select the **Properties** check box.</span></span>  
  
3.  <span data-ttu-id="516e4-114">Cliquez sur la zone de texte pour laquelle vous souhaitez modifier l'orientation du texte.</span><span class="sxs-lookup"><span data-stu-id="516e4-114">Click the text box for which you want to change text orientation.</span></span>  
  
4.  <span data-ttu-id="516e4-115">Localisez la propriété WritingMode dans le volet Propriétés et sélectionnez l’orientation de texte à appliquer à la zone de texte dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="516e4-115">Locate the WritingMode property in the Properties pane and in the drop-down list select the text orientation to apply to the text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="516e4-116">Quand les propriétés du volet Propriétés sont organisées en catégories, WritingMode figure dans la catégorie **Localisation** .</span><span class="sxs-lookup"><span data-stu-id="516e4-116">When the properties in the Properties pane are organized into categories, WritingMode is in the **Localization** category.</span></span>  
  
5.  <span data-ttu-id="516e4-117">Dans la zone de liste, sélectionnez **Horizontal**, **Vertical**ou **Rotate270**.</span><span class="sxs-lookup"><span data-stu-id="516e4-117">In the list box, select **Horizontal**, **Vertical**, or **Rotate270**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="516e4-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="516e4-118">See Also</span></span>  
 <span data-ttu-id="516e4-119">[Zones de texte &#40;Générateur de rapports et SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="516e4-119">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="516e4-120">Didacticiel : mettre en forme du texte &#40;Générateur de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="516e4-120">Tutorial: Format Text &#40;Report Builder&#41;</span></span>](../tutorial-format-text-report-builder.md)  
  
  
