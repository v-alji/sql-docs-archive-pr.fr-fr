---
title: Supprimer un membre ou une collection (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services], deleting
- leaf members [Master Data Services], deleting
- deleting members [Master Data Services]
- members [Master Data Services], deleting
- consolidated members [Master Data Services], deleting
ms.assetid: 519130a7-4226-4d71-9124-d2ee0ce7e5bd
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9b248750c0e755c3fc9e32d45068c754e64957b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695780"
---
# <a name="delete-a-member-or-collection-master-data-services"></a><span data-ttu-id="2a6c3-102">Supprimer un membre ou une collection (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2a6c3-102">Delete a Member or Collection (Master Data Services)</span></span>
  <span data-ttu-id="2a6c3-103">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], supprimez un membre ou une collection lorsque vous n'en avez plus besoin.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], delete a member or collection when you no longer need it.</span></span> <span data-ttu-id="2a6c3-104">Si vous souhaitez supprimer des membres en bloc, utilisez le processus de site à la place.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-104">If you want to delete members in bulk, use the staging process instead.</span></span> <span data-ttu-id="2a6c3-105">Pour plus d’informations, consultez [désactiver ou supprimer des membres à l’aide du processus de site &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2a6c3-105">For more information, see [Deactivate or Delete Members by Using the Staging Process &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2a6c3-106">Vous ne pouvez pas supprimer un membre s'il est utilisé comme une valeur d'attribut basée sur un domaine pour un autre membre.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-106">You cannot delete a member if it is used as a domain-based attribute value for another member.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2a6c3-107">Prérequis</span><span class="sxs-lookup"><span data-stu-id="2a6c3-107">Prerequisites</span></span>  
 <span data-ttu-id="2a6c3-108">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="2a6c3-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="2a6c3-109">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="2a6c3-109">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="2a6c3-110">Pour les membres, vous devez disposer au minimum de l’autorisation **mettre à jour** sur l’objet modèle feuille à partir duquel vous supprimez un membre.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-110">For members, you must have a minimum of **Update** permission to the leaf model object you are deleting a member from.</span></span>  
  
-   <span data-ttu-id="2a6c3-111">Pour les collections, vous devez avoir au minimum l'autorisation **Mettre à jour** sur l'objet modèle de collection feuille que vous supprimez.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-111">For collections, you must have a minimum of **Update** permission to the leaf collection object you are deleting.</span></span>  
  
### <a name="to-delete-a-member-or-collection"></a><span data-ttu-id="2a6c3-112">Pour supprimer un membre ou une collection</span><span class="sxs-lookup"><span data-stu-id="2a6c3-112">To delete a member or collection</span></span>  
  
1.  <span data-ttu-id="2a6c3-113">Dans la page d'accueil de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-113">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="2a6c3-114">Dans la liste **Version** , sélectionnez une version.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-114">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="2a6c3-115">Cliquez sur **Explorateur**.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-115">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="2a6c3-116">Pour supprimer les éléments suivants, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="2a6c3-116">To delete:</span></span>  
  
    -   <span data-ttu-id="2a6c3-117">Pour un membre feuille, dans la barre de menus, pointez sur **Entités** , puis cliquez sur le nom de l'entité qui contient le membre.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-117">A leaf member, from the menu bar, point to **Entities** and click the name of the entity that contains the member.</span></span>  
  
    -   <span data-ttu-id="2a6c3-118">Pour un membre consolidé, dans la barre de menus, pointez sur **Hiérarchies** , puis cliquez sur le nom de la hiérarchie qui contient le membre.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-118">A consolidated member, from the menu bar, point to **Hierarchies** and click the name of the hierarchy that contains the member.</span></span> <span data-ttu-id="2a6c3-119">Cliquez sur le nœud de la hiérarchie qui contient le membre.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-119">Then click the node in the hierarchy that contains the member.</span></span>  
  
    -   <span data-ttu-id="2a6c3-120">Pour une collection, dans la barre de menus, pointez sur **Collections** , puis cliquez sur le nom de l'entité qui contient la collection.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-120">A collection, from the menu bar, point to **Collections** and click the name of the entity that contains the collection.</span></span>  
  
5.  <span data-ttu-id="2a6c3-121">Dans la grille, cliquez sur la ligne correspondant au membre ou à la collection à supprimer.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-121">In the grid, click the row of the member or collection you want to delete.</span></span>  
  
6.  <span data-ttu-id="2a6c3-122">Cliquez sur **Supprimer un membre**, sur **Supprimer**ou sur **Supprimer une collection**.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-122">Click **Delete Member**, **Delete**, or **Delete Collection**.</span></span>  
  
7.  <span data-ttu-id="2a6c3-123">Dans la boîte de dialogue de confirmation, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2a6c3-123">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a6c3-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2a6c3-124">See Also</span></span>  
 <span data-ttu-id="2a6c3-125">[Réactiver un membre ou une collection &#40;Master Data Services&#41;](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2a6c3-125">[Reactivate a Member or Collection &#40;Master Data Services&#41;](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md) </span></span>  
 <span data-ttu-id="2a6c3-126">[Membres &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2a6c3-126">[Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span></span>  
 [<span data-ttu-id="2a6c3-127">Collections &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2a6c3-127">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)  
  
  
