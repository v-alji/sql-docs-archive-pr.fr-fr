---
title: Ajouter une image externe (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 81fd4a1f-79a9-4967-86d6-6229413c0995
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8d0030c8f29b14b2c62048be306daa15948cd8d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696412"
---
# <a name="add-an-external-image-report-builder-and-ssrs"></a><span data-ttu-id="86227-102">Ajouter une image externe (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="86227-102">Add an External Image (Report Builder and SSRS)</span></span>
  <span data-ttu-id="86227-103">Les images externes peuvent se trouver sur un serveur de rapports en mode natif ou en mode intégré SharePoint, ou sur un autre site Web.</span><span class="sxs-lookup"><span data-stu-id="86227-103">External images can be on a report server in native mode or SharePoint integrated mode, or on any other Web site.</span></span> <span data-ttu-id="86227-104">Lorsque vous incluez des images externes dans votre rapport, vous devez vous assurer que l'image existe et que le lecteur du rapport a les autorisations nécessaires pour y accéder.</span><span class="sxs-lookup"><span data-stu-id="86227-104">When you include external images in your report, you must verify that the image exists and that the report reader has permissions to access the image.</span></span> <span data-ttu-id="86227-105">Pour plus d’informations, consultez [Images &#40;Générateur de rapports et SSRS&#41;](images-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="86227-105">For more information, see [Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-an-external-image"></a><span data-ttu-id="86227-106">Pour ajouter une image externe</span><span class="sxs-lookup"><span data-stu-id="86227-106">To add an external image</span></span>  
  
1.  <span data-ttu-id="86227-107">En mode Création de rapport, sous l’onglet **Insérer** , cliquez sur **Image**.</span><span class="sxs-lookup"><span data-stu-id="86227-107">In report design view, on the **Insert** tab, click **Image**.</span></span>  
  
2.  <span data-ttu-id="86227-108">Cliquez sur l'aire de conception, puis faites glisser la souris pour créer une zone de la taille voulue pour l'image.</span><span class="sxs-lookup"><span data-stu-id="86227-108">On the design surface, click and then drag a box to the desired size of the image.</span></span>  
  
3.  <span data-ttu-id="86227-109">Sous l’onglet **Général** de la boîte de dialogue **Propriétés de l’image** , tapez un nom dans la zone de texte **Nom** ou acceptez le nom par défaut.</span><span class="sxs-lookup"><span data-stu-id="86227-109">On the **General** tab of the **Image Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span>  
  
4.  <span data-ttu-id="86227-110">(Facultatif) Dans la zone de texte **Info-bulle** , tapez le texte à afficher quand l’utilisateur pointe sur l’image dans un rapport rendu au format HTML.</span><span class="sxs-lookup"><span data-stu-id="86227-110">(Optional) In the **Tooltip** text box, type text to display when the user hovers over the image in a report rendered for HTML.</span></span>  
  
5.  <span data-ttu-id="86227-111">Dans **Sélectionner la source de l’image**, sélectionnez **Externe**.</span><span class="sxs-lookup"><span data-stu-id="86227-111">In **Select the image source**, select **External**.</span></span>  
  
     <span data-ttu-id="86227-112">Pour une image située sur un serveur de rapports en mode natif, tapez le chemin relatif de l’image dans la zone **Utiliser cette image**, par exemple ../images/image1.jpg.</span><span class="sxs-lookup"><span data-stu-id="86227-112">For an image on a report server in native mode, type a relative path to the image in the **Use this image** box-for example, ../images/image1.jpg.</span></span>  
  
     <span data-ttu-id="86227-113">Pour une image sur un serveur de rapports en mode intégré SharePoint, ou tout autre site Web, tapez une URL complète vers l’image dans la zone **utiliser cette image** , par exemple, http:// \<SharePointservername> / \<site> /Documents/images/image1.jpg.</span><span class="sxs-lookup"><span data-stu-id="86227-113">For an image on a report server in SharePoint integrated mode, or any other Web site, type a full URL to the image in the **Use this image** box-for example, http://\<SharePointservername>/\<site>/Documents/images/image1.jpg.</span></span>  
  
     <span data-ttu-id="86227-114">Pour plus d’informations, consultez [Spécification de chemins d’accès à des éléments externes &#40;Générateur de rapports et SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="86227-114">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="86227-115">(Facultatif) Cliquez sur **Taille**, **Visibilité**, **Action**ou **Bordure** pour définir des propriétés supplémentaires pour l’élément de rapport de type image.</span><span class="sxs-lookup"><span data-stu-id="86227-115">(Optional) Click **Size**, **Visibility**, **Action**, or **Border** to set additional properties for the image report item.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="86227-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="86227-116">See Also</span></span>  
 <span data-ttu-id="86227-117">[Incorporer une image dans un rapport &#40;Générateur de rapports et SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="86227-117">[Embed an Image in a Report &#40;Report Builder and SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="86227-118">[Ajouter une image d’arrière-plan &#40;Générateur de rapports et SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="86227-118">[Add a Background Image &#40;Report Builder and SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="86227-119">Boîte de dialogue Propriétés de l’image, Général &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="86227-119">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
