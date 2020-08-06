---
title: 'Les fonctionnalités suivantes ne sont pas prises en charge par Excel Services et risquent de ne pas s’afficher ou de ne s’afficher que partiellement : les commentaires, les formes ou d’autres objets | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ade92e15-dfbf-496b-9378-a00bd83ba750
author: minewiskan
ms.author: owend
ms.openlocfilehash: 67c2989ab89f242fdce2ca64f3c2f361e17d49ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700314"
---
# <a name="the-following-features-are-not-supported-by-excel-services-and-may-not-display-or-may-display-only-partially-comments-shapes-or-other-objects"></a><span data-ttu-id="132fa-102">Les fonctionnalités suivantes ne sont pas prises en charge par Excel Services et risquent de ne pas s'afficher ou de ne s'afficher que partiellement : les commentaires, les formes ou d'autres objets</span><span class="sxs-lookup"><span data-stu-id="132fa-102">The following features are not supported by Excel Services and may not display or may display only partially: Comments, Shapes, or other objects</span></span>
  <span data-ttu-id="132fa-103">Cette erreur se produit lorsque vous ajoutez des segments à un classeur PowerPivot à partir d'une liste de champs PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="132fa-103">This error occurs when you add Slicers to a PowerPivot workbook from a PowerPivot Field List.</span></span>  
  
## <a name="details"></a><span data-ttu-id="132fa-104">Détails</span><span class="sxs-lookup"><span data-stu-id="132fa-104">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="132fa-105">S’applique à</span><span class="sxs-lookup"><span data-stu-id="132fa-105">Applies to</span></span>|<span data-ttu-id="132fa-106">PowerPivot pour SharePoint</span><span class="sxs-lookup"><span data-stu-id="132fa-106">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="132fa-107">Version du produit</span><span class="sxs-lookup"><span data-stu-id="132fa-107">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="132fa-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="132fa-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="132fa-109">Cause</span><span class="sxs-lookup"><span data-stu-id="132fa-109">Cause</span></span>|<span data-ttu-id="132fa-110">Excel Web Access ne peut pas restituer l'objet Forme utilisé pour contrôler le positionnement et la mise en forme des segments ajoutés à un classeur à partir de la liste de champs PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="132fa-110">Excel Web Access cannot render the Shape object used to control positioning and formatting of Slicers added to a workbook from the PowerPivot Field List.</span></span>|  
|<span data-ttu-id="132fa-111">Texte du message</span><span class="sxs-lookup"><span data-stu-id="132fa-111">Message Text</span></span>|<span data-ttu-id="132fa-112">Les fonctionnalités suivantes ne sont pas prises en charge par Excel Services et risquent de ne pas s'afficher ou de ne s'afficher que partiellement :</span><span class="sxs-lookup"><span data-stu-id="132fa-112">The following features are not supported by Excel Services and may not display or may display only partially:</span></span><br /><br /> <span data-ttu-id="132fa-113">les commentaires, les formes ou d'autres objets</span><span class="sxs-lookup"><span data-stu-id="132fa-113">Comments, Shapes, or other objects</span></span><br /><br /> <span data-ttu-id="132fa-114">Certaines fonctionnalités, comme les requêtes de données externes, affichent des données mises en cache qui ne peuvent être actualisées que dans Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="132fa-114">Some features, such as external data queries, display cached data which can only be refreshed in Microsoft Excel.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="132fa-115">Explication</span><span class="sxs-lookup"><span data-stu-id="132fa-115">Explanation</span></span>  
 <span data-ttu-id="132fa-116">Excel Accès web affiche cette erreur lorsque vous ouvrez un classeur PowerPivot dans un navigateur et que vous cliquez sur le bouton **Détails** du message, **fonctionnalités non prises en charge que ce classeur risque de ne pas afficher comme prévu**.</span><span class="sxs-lookup"><span data-stu-id="132fa-116">Excel Web Access shows this error when you open a PowerPivot workbook in a browser and you click the **Details** button for the message, **Unsupported Features This workbook may not display as intended**.</span></span>  
  
 <span data-ttu-id="132fa-117">Cette erreur se produit parce que le classeur PowerPivot contient des segments dont la disposition est contrôlée par un objet Forme masqué dans Excel.</span><span class="sxs-lookup"><span data-stu-id="132fa-117">This error occurs because the PowerPivot workbook contains Slicers whose layout is controlled by a hidden Shape object in Excel.</span></span> <span data-ttu-id="132fa-118">L'objet Forme contrôle la mise en forme et le positionnement des segments dans les placements horizontaux et verticaux.</span><span class="sxs-lookup"><span data-stu-id="132fa-118">The Shape object controls the formatting and positioning of the Slicers in horizontal and vertical placements.</span></span>  
  
 <span data-ttu-id="132fa-119">Excel Services ne peut pas restituer un objet Forme, mais étant donné que l'objet est masqué, le fait qu'il n'effectue le rendu n'est pas un problème.</span><span class="sxs-lookup"><span data-stu-id="132fa-119">Excel Services cannot render a Shape object, but because the object is hidden, the fact that it does not render is not an issue.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="132fa-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="132fa-120">User Action</span></span>  
 <span data-ttu-id="132fa-121">Cette erreur peut être ignorée.</span><span class="sxs-lookup"><span data-stu-id="132fa-121">This error can be ignored.</span></span> <span data-ttu-id="132fa-122">Cliquez sur **OK** pour fermer le message d'erreur et utiliser le classeur et les segments sans problème.</span><span class="sxs-lookup"><span data-stu-id="132fa-122">Click **OK** to close the error message and proceed to use the workbook and Slicers with no problem.</span></span>  
  
  
