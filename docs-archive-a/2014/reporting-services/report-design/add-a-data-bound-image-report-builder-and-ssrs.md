---
title: Ajouter une image liée à des données (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: df4c38d4-bfcc-41c4-aa6d-952ca6fd7a2e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ea85bdcd6eab04ff51c879a9e790b6e12f73a771
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600552"
---
# <a name="add-a-data-bound-image-report-builder-and-ssrs"></a><span data-ttu-id="ede73-102">Ajouter une image liée à des données (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="ede73-102">Add a Data-Bound Image (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ede73-103">Un rapport peut inclure une référence à une image stockée dans une base de données.</span><span class="sxs-lookup"><span data-stu-id="ede73-103">A report can include a reference to an image that is stored in a database.</span></span> <span data-ttu-id="ede73-104">Cette image est appelée *image liée aux données*.</span><span class="sxs-lookup"><span data-stu-id="ede73-104">Such an image is known as a *data-bound image*.</span></span> <span data-ttu-id="ede73-105">Les images qui jouxtent les noms de produits dans une liste de produits sont des exemples d'images liées à des données.</span><span class="sxs-lookup"><span data-stu-id="ede73-105">The pictures that appear alongside product names in a product list are examples of data-bound images.</span></span>  
  
 <span data-ttu-id="ede73-106">L'ajout d'une image liée à des données à un en-tête de page ou pied de page requiert des étapes supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="ede73-106">Adding a data-bound image to a page header or page footer requires additional steps.</span></span> <span data-ttu-id="ede73-107">Pour plus d’informations, consultez [En-têtes et pieds de page &#40;Générateur de rapports et SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ede73-107">For more information, see [Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-data-bound-image"></a><span data-ttu-id="ede73-108">Pour ajouter une image liée à des données</span><span class="sxs-lookup"><span data-stu-id="ede73-108">To add a data-bound image</span></span>  
  
1.  <span data-ttu-id="ede73-109">En mode de conception de rapport, créez une table avec une connexion à la source de données et un dataset avec un champ qui contient des données binaires de type image.</span><span class="sxs-lookup"><span data-stu-id="ede73-109">In report design view, create a table with a data source connection and a dataset with a field that contains binary image data.</span></span> <span data-ttu-id="ede73-110">Pour plus d’informations, consultez [Tables &#40;Générateur de rapports et SSRS&#41;](tables-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ede73-110">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="ede73-111">Insérez une colonne dans votre table.</span><span class="sxs-lookup"><span data-stu-id="ede73-111">Insert a column in your table.</span></span> <span data-ttu-id="ede73-112">Pour plus d’informations, consultez [Insérer ou supprimer une colonne &#40;Générateur de rapports et SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ede73-112">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="ede73-113">Dans le menu **Insérer** , cliquez sur **Image**, puis cliquez sur la ligne de données de la nouvelle colonne.</span><span class="sxs-lookup"><span data-stu-id="ede73-113">On the **Insert** menu, click **Image**, and then click in the data row of the new column.</span></span>  
  
4.  <span data-ttu-id="ede73-114">Dans la page Général de la boîte de dialogue **Propriétés de l’image** , tapez un nom dans la zone de texte **Nom** ou acceptez le nom par défaut.</span><span class="sxs-lookup"><span data-stu-id="ede73-114">On the General page of the **Image Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span>  
  
5.  <span data-ttu-id="ede73-115">(Facultatif) Dans la zone de texte **Info-bulle** , tapez le texte à afficher quand l’utilisateur pointe sur l’image dans le rapport rendu au format HTML.</span><span class="sxs-lookup"><span data-stu-id="ede73-115">(Optional) In the **Tooltip** text box, type text to display when the user hovers over the image in the report rendered for HTML.</span></span>  
  
6.  <span data-ttu-id="ede73-116">Dans **Sélectionner la source de l’image**, sélectionnez **Base de données**.</span><span class="sxs-lookup"><span data-stu-id="ede73-116">In **Select the image source**, select **Database**.</span></span>  
  
7.  <span data-ttu-id="ede73-117">Dans **Utiliser ce champ**, sélectionnez le champ qui contient des images dans votre rapport.</span><span class="sxs-lookup"><span data-stu-id="ede73-117">In **Use this Field**, select the field that contains images in your report.</span></span>  
  
8.  <span data-ttu-id="ede73-118">Dans **Utiliser ce type MIME**, sélectionnez le type MIME ou le format de fichier de l’image, par exemple bmp.</span><span class="sxs-lookup"><span data-stu-id="ede73-118">In **Use this MIME type**, select the MIME type, or file format, of the image-for example, bmp.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="ede73-119">Un espace réservé à l'image apparaît sur l'aire de conception du rapport.</span><span class="sxs-lookup"><span data-stu-id="ede73-119">An image placeholder appears on the report design surface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ede73-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ede73-120">See Also</span></span>  
 <span data-ttu-id="ede73-121">[Images &#40;Générateur de rapports et SSRS&#41;](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ede73-121">[Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ede73-122">[Incorporer une image dans un rapport &#40;Générateur de rapports et SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ede73-122">[Embed an Image in a Report &#40;Report Builder and SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ede73-123">[Ajouter une image externe &#40;Générateur de rapports et SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ede73-123">[Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ede73-124">Boîte de dialogue Propriétés de l’image, Général &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ede73-124">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
