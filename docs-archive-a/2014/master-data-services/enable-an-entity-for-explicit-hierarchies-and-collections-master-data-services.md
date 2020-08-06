---
title: Activer une entité pour les hiérarchies et collections explicites (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- entities [Master Data Services], enabling for collections
- entities [Master Data Services], enabling for explicit hierarchies
ms.assetid: 380e77e5-ad60-43d4-9605-34a84525f5dd
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a8129b3f67f050603f85ffb782a9dd209cb303fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695756"
---
# <a name="enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services"></a><span data-ttu-id="966c1-102">Activer une entité pour les hiérarchies explicites et les collections (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="966c1-102">Enable an Entity for Explicit Hierarchies and Collections (Master Data Services)</span></span>
  <span data-ttu-id="966c1-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], activez une entité pour les hiérarchies et collections explicites afin de pouvoir créer des hiérarchies et collections explicites pour l'entité.</span><span class="sxs-lookup"><span data-stu-id="966c1-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], enable an entity for explicit hierarchies and collections so that you can create explicit hierarchies and collections for the entity.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="966c1-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="966c1-104">Prerequisites</span></span>  
 <span data-ttu-id="966c1-105">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="966c1-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="966c1-106">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="966c1-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="966c1-107">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="966c1-107">You must be a model administrator.</span></span> <span data-ttu-id="966c1-108">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="966c1-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="966c1-109">Une entité doit exister.</span><span class="sxs-lookup"><span data-stu-id="966c1-109">An entity must exist.</span></span> <span data-ttu-id="966c1-110">Pour plus d’informations, consultez [créer une entité &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="966c1-110">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-enable-an-entity-for-explicit-hierarchies-and-collections"></a><span data-ttu-id="966c1-111">Pour activer une entité pour les hiérarchies et collections explicites</span><span class="sxs-lookup"><span data-stu-id="966c1-111">To enable an entity for explicit hierarchies and collections</span></span>  
  
1.  <span data-ttu-id="966c1-112">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="966c1-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="966c1-113">Dans la page **Vue du modèle** , dans la barre de menus, pointez sur **Gérer** , puis cliquez sur **Entités**.</span><span class="sxs-lookup"><span data-stu-id="966c1-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="966c1-114">Dans la page **Maintenance de l'entité** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="966c1-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="966c1-115">Sélectionnez la ligne de l'entité à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="966c1-115">Select the row for the entity that you want to update.</span></span>  
  
5.  <span data-ttu-id="966c1-116">Cliquez sur **Modifier l'entité sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="966c1-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="966c1-117">Dans la liste **activer les hiérarchies explicites et les regroupements** , sélectionnez **Oui**.</span><span class="sxs-lookup"><span data-stu-id="966c1-117">From the **Enable explicit hierarchies and collections** list, select **Yes**.</span></span>  
  
7.  <span data-ttu-id="966c1-118">Dans la zone nom de la **hiérarchie explicite** , tapez un nom pour une hiérarchie explicite.</span><span class="sxs-lookup"><span data-stu-id="966c1-118">In the **Explicit hierarchy name** box, type a name for an explicit hierarchy.</span></span>  
  
8.  <span data-ttu-id="966c1-119">Décochez éventuellement la case **Hiérarchie obligatoire** pour créer la hiérarchie comme une hiérarchie non obligatoire.</span><span class="sxs-lookup"><span data-stu-id="966c1-119">Optionally, clear the **Mandatory hierarchy** check box to create the hierarchy as a non-mandatory hierarchy.</span></span>  
  
9. <span data-ttu-id="966c1-120">Cliquez sur **enregistrer l’entité**.</span><span class="sxs-lookup"><span data-stu-id="966c1-120">Click **Save entity**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="966c1-121">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="966c1-121">Next Steps</span></span>  
  
-   [<span data-ttu-id="966c1-122">Créer une hiérarchie explicite &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="966c1-122">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)  
  
-   [<span data-ttu-id="966c1-123">Créer une collection &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="966c1-123">Create a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-collection-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="966c1-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="966c1-124">See Also</span></span>  
 <span data-ttu-id="966c1-125">[Entités &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="966c1-125">[Entities &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span></span>  
 <span data-ttu-id="966c1-126">[Hiérarchies explicites &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="966c1-126">[Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span></span>  
 [<span data-ttu-id="966c1-127">Collections &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="966c1-127">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)  
  
  
