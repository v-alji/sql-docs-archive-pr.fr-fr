---
title: Masquer ou supprimer des niveaux dans une hiérarchie dérivée (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- derived hierarchies, hiding levels
- derived hierarchies, deleting levels
ms.assetid: e00582b9-9415-4b66-b4a7-9f590d83875f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 039b05633bcd1fdc69d226e565b3dc5211e9734f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611138"
---
# <a name="hide-or-delete-levels-in-a-derived-hierarchy-master-data-services"></a><span data-ttu-id="a5d73-102">Masquer ou supprimer des niveaux dans une hiérarchie dérivée (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="a5d73-102">Hide or Delete Levels in a Derived Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="a5d73-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], masquez un niveau dans une hiérarchie dérivée quand le niveau est requis pour le regroupement, mais que vous n’avez pas besoin de l’afficher.</span><span class="sxs-lookup"><span data-stu-id="a5d73-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], hide a level in a derived hierarchy when you require the level for grouping but you do not need to show the level.</span></span> <span data-ttu-id="a5d73-104">Supprimez un niveau lorsque vous ne souhaitez pas l'utiliser pour le regroupement.</span><span class="sxs-lookup"><span data-stu-id="a5d73-104">Delete a level when you do not want to use it for grouping.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a5d73-105">Prérequis</span><span class="sxs-lookup"><span data-stu-id="a5d73-105">Prerequisites</span></span>  
 <span data-ttu-id="a5d73-106">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="a5d73-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="a5d73-107">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="a5d73-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="a5d73-108">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="a5d73-108">You must be a model administrator.</span></span> <span data-ttu-id="a5d73-109">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a5d73-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-hide-or-delete-levels-in-a-derived-hierarchy"></a><span data-ttu-id="a5d73-110">Pour masquer ou supprimer des niveaux dans une hiérarchie dérivée</span><span class="sxs-lookup"><span data-stu-id="a5d73-110">To hide or delete levels in a derived hierarchy</span></span>  
  
1.  <span data-ttu-id="a5d73-111">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="a5d73-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="a5d73-112">Dans la page **vue du modèle** , dans la barre de menus, pointez sur **gérer** , puis cliquez sur **hiérarchies dérivées**.</span><span class="sxs-lookup"><span data-stu-id="a5d73-112">On the **Model View** page, from the menu bar, point to **Manage** and click **Derived Hierarchies**.</span></span>  
  
3.  <span data-ttu-id="a5d73-113">Dans la page **Maintenance de la hiérarchie dérivée** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="a5d73-113">On the **Derived Hierarchy Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="a5d73-114">Sélectionnez la ligne de la hiérarchie dérivée à modifier.</span><span class="sxs-lookup"><span data-stu-id="a5d73-114">Select the row for the derived hierarchy you want to edit.</span></span>  
  
5.  <span data-ttu-id="a5d73-115">Cliquez sur **modifier la hiérarchie dérivée sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="a5d73-115">Click **Edit selected derived hierarchy**.</span></span>  
  
6.  <span data-ttu-id="a5d73-116">Dans le volet **Niveaux actuels** :</span><span class="sxs-lookup"><span data-stu-id="a5d73-116">In the **Current Levels** pane:</span></span>  
  
    -   <span data-ttu-id="a5d73-117">Pour masquer un niveau, cliquez sur un niveau autre que le niveau supérieur ou inférieur.</span><span class="sxs-lookup"><span data-stu-id="a5d73-117">To hide a level, click a level other than the top or bottom.</span></span> <span data-ttu-id="a5d73-118">Dans la liste **Visible** , sélectionnez **Non**.</span><span class="sxs-lookup"><span data-stu-id="a5d73-118">From the **Visible** list, select **No**.</span></span> <span data-ttu-id="a5d73-119">Cliquez ensuite sur **Enregistrer l’élément de hiérarchie sélectionné**.</span><span class="sxs-lookup"><span data-stu-id="a5d73-119">Then click **Save selected hierarchy item**.</span></span>  
  
    -   <span data-ttu-id="a5d73-120">Pour supprimer le niveau supérieur, cliquez sur **Supprimer l’élément de hiérarchie sélectionné**.</span><span class="sxs-lookup"><span data-stu-id="a5d73-120">To delete the top level, click **Delete selected hierarchy item**.</span></span> <span data-ttu-id="a5d73-121">Dans la boîte de dialogue de confirmation, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5d73-121">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="a5d73-122">Vous pouvez supprimer uniquement le niveau supérieur.</span><span class="sxs-lookup"><span data-stu-id="a5d73-122">You can delete the top level only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5d73-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a5d73-123">See Also</span></span>  
 <span data-ttu-id="a5d73-124">[Déplacer des membres au sein d’une hiérarchie &#40;Master Data Services&#41;](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a5d73-124">[Move Members within a Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md) </span></span>  
 [<span data-ttu-id="a5d73-125">Hiérarchies dérivées &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a5d73-125">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)  
  
  
