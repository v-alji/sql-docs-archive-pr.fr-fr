---
title: Supprimer une hiérarchie explicite (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- explicit hierarchies, deleting
- deleting explicit hierarchies [Master Data Services]
ms.assetid: 4ce177b0-9884-47a2-9cea-212e845dd762
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 744f96a2705a3abbc2318ecd3c9b0c7fffb7605e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615188"
---
# <a name="delete-an-explicit-hierarchy-master-data-services"></a><span data-ttu-id="958d0-102">Supprimer une hiérarchie explicite (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="958d0-102">Delete an Explicit Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="958d0-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], supprimez une hiérarchie explicite lorsque vous n'en avez plus besoin.</span><span class="sxs-lookup"><span data-stu-id="958d0-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete an explicit hierarchy when you no longer need it.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="958d0-104">Lorsque vous supprimez une hiérarchie explicite, tous les membres consolidés de la hiérarchie sont également supprimés.</span><span class="sxs-lookup"><span data-stu-id="958d0-104">When you delete an explicit hierarchy, all consolidated members in the hierarchy are deleted also.</span></span> <span data-ttu-id="958d0-105">Si vous supprimez toutes les hiérarchies explicites d'une entité, toutes les collections de l'entité sont également supprimées et l'entité n'est plus activée pour les hiérarchies explicites et les collections.</span><span class="sxs-lookup"><span data-stu-id="958d0-105">If you delete all explicit hierarchies for an entity, all collections for the entity are also deleted and the entity is no longer enabled for explicit hierarchies and collections.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="958d0-106">Prérequis</span><span class="sxs-lookup"><span data-stu-id="958d0-106">Prerequisites</span></span>  
 <span data-ttu-id="958d0-107">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="958d0-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="958d0-108">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="958d0-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="958d0-109">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="958d0-109">You must be a model administrator.</span></span> <span data-ttu-id="958d0-110">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="958d0-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-an-explicit-hierarchy"></a><span data-ttu-id="958d0-111">Pour supprimer une hiérarchie explicite</span><span class="sxs-lookup"><span data-stu-id="958d0-111">To delete an explicit hierarchy</span></span>  
  
1.  <span data-ttu-id="958d0-112">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="958d0-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="958d0-113">Dans la page **Vue du modèle** , dans la barre de menus, pointez sur **Gérer** , puis cliquez sur **Entités**.</span><span class="sxs-lookup"><span data-stu-id="958d0-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="958d0-114">Dans la page **Maintenance de l'entité** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="958d0-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="958d0-115">Sélectionnez la ligne de l'entité qui contient la hiérarchie explicite à supprimer.</span><span class="sxs-lookup"><span data-stu-id="958d0-115">Select the row for the entity that contains the explicit hierarchy you want to delete.</span></span>  
  
5.  <span data-ttu-id="958d0-116">Cliquez sur **Modifier l'entité sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="958d0-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="958d0-117">Dans la page **modifier l’entité** , dans le volet **hiérarchies explicites** , cliquez sur la hiérarchie explicite à supprimer.</span><span class="sxs-lookup"><span data-stu-id="958d0-117">On the **Edit Entity** page, in the **Explicit Hierarchies** pane, click the explicit hierarchy you want to delete.</span></span>  
  
7.  <span data-ttu-id="958d0-118">Cliquez sur **Supprimer la hiérarchie sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="958d0-118">Click **Delete selected hierarchy**.</span></span>  
  
8.  <span data-ttu-id="958d0-119">Dans la boîte de dialogue de confirmation, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="958d0-119">In the confirmation dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="958d0-120">Dans la boîte de dialogue de confirmation supplémentaire, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="958d0-120">In the additional confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="958d0-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="958d0-121">See Also</span></span>  
 <span data-ttu-id="958d0-122">[Créer une hiérarchie explicite &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="958d0-122">[Create an Explicit Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) </span></span>  
 [<span data-ttu-id="958d0-123">Hiérarchies explicites &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="958d0-123">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)  
  
  
