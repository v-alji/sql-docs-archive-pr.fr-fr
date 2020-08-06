---
title: Créer une hiérarchie explicite (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating explicit hierarchies [Master Data Services]
- explicit hierarchies, creating
ms.assetid: ba768393-6990-4eda-8cb0-d58cb3cfc2e2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: aebf95e68f210fe5a573aed092231670c10fa188
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611835"
---
# <a name="create-an-explicit-hierarchy-master-data-services"></a><span data-ttu-id="60974-102">Créer une hiérarchie explicite (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="60974-102">Create an Explicit Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="60974-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], créez une hiérarchie explicite lorsque vous avez besoin d'une hiérarchie déséquilibrée dans laquelle les membres peuvent exister à tous les niveaux.</span><span class="sxs-lookup"><span data-stu-id="60974-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create an explicit hierarchy when you need a ragged hierarchy in which members can exist at any level.</span></span> <span data-ttu-id="60974-104">Les hiérarchies explicites contiennent des membres d'une entité unique.</span><span class="sxs-lookup"><span data-stu-id="60974-104">Explicit hierarchies contain members from a single entity.</span></span>  
  
 <span data-ttu-id="60974-105">Après avoir créé une hiérarchie explicite, vous pouvez lui ajouter des membres dans la zone fonctionnelle **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="60974-105">After you create an explicit hierarchy, you can add members to it in the **Explorer** functional area.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="60974-106">Prérequis</span><span class="sxs-lookup"><span data-stu-id="60974-106">Prerequisites</span></span>  
 <span data-ttu-id="60974-107">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="60974-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="60974-108">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="60974-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="60974-109">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="60974-109">You must be a model administrator.</span></span> <span data-ttu-id="60974-110">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="60974-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="60974-111">L'entité doit être activée pour les hiérarchies et collections explicites.</span><span class="sxs-lookup"><span data-stu-id="60974-111">The entity must be enabled for explicit hierarchies and collections.</span></span> <span data-ttu-id="60974-112">Pour plus d’informations, consultez [activer une entité pour les hiérarchies explicites et les Collections &#40;Master Data Services&#41;](../../2014/master-data-services/enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="60974-112">For more information, see [Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;](../../2014/master-data-services/enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span></span>  
  
### <a name="to-create-an-explicit-hierarchy"></a><span data-ttu-id="60974-113">Pour créer une hiérarchie explicite</span><span class="sxs-lookup"><span data-stu-id="60974-113">To create an explicit hierarchy</span></span>  
  
1.  <span data-ttu-id="60974-114">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="60974-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="60974-115">Dans la page **Vue du modèle** , dans la barre de menus, pointez sur **Gérer** , puis cliquez sur **Entités**.</span><span class="sxs-lookup"><span data-stu-id="60974-115">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="60974-116">Dans la page **Maintenance de l'entité** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="60974-116">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="60974-117">Sélectionnez la ligne de l'entité pour laquelle vous souhaitez créer une hiérarchie explicite.</span><span class="sxs-lookup"><span data-stu-id="60974-117">Select the row for the entity that you want to create an explicit hierarchy for.</span></span>  
  
5.  <span data-ttu-id="60974-118">Cliquez sur **Modifier l'entité sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="60974-118">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="60974-119">Dans la page **modifier l’entité** , dans le volet **hiérarchies explicites** , cliquez sur **Ajouter une hiérarchie explicite**.</span><span class="sxs-lookup"><span data-stu-id="60974-119">On the **Edit Entity** page, in the **Explicit hierarchies** pane, click **Add explicit hierarchy**.</span></span>  
  
7.  <span data-ttu-id="60974-120">Dans la page **Ajouter une hiérarchie explicite** , dans la zone nom de la **hiérarchie explicite** , tapez un nom pour la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="60974-120">On the **Add Explicit Hierarchy** page, in the **Explicit hierarchy name** box, type a name for the hierarchy.</span></span>  
  
8.  <span data-ttu-id="60974-121">Décochez éventuellement la case **Hiérarchie obligatoire** pour créer la hiérarchie comme une hiérarchie non obligatoire.</span><span class="sxs-lookup"><span data-stu-id="60974-121">Optionally, clear the **Mandatory hierarchy** check box to create the hierarchy as a non-mandatory hierarchy.</span></span> <span data-ttu-id="60974-122">Pour plus d’informations sur les types de hiérarchies, consultez [Hiérarchies explicites &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="60974-122">For more information about hierarchy types, see [Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="60974-123">Cliquez sur **enregistrer la hiérarchie**.</span><span class="sxs-lookup"><span data-stu-id="60974-123">Click **Save hierarchy**.</span></span>  
  
10. <span data-ttu-id="60974-124">Dans la page **modifier l’entité** , cliquez sur enregistrer l' **entité**.</span><span class="sxs-lookup"><span data-stu-id="60974-124">On the **Edit Entity** page, click **Save entity**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="60974-125">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="60974-125">Next Steps</span></span>  
  
-   [<span data-ttu-id="60974-126">Créer un membre consolidé &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="60974-126">Create a Consolidated Member &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md)  
  
-   [<span data-ttu-id="60974-127">Déplacer des membres au sein d’une hiérarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="60974-127">Move Members within a Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="60974-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="60974-128">See Also</span></span>  
 <span data-ttu-id="60974-129">[Hiérarchies explicites &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="60974-129">[Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span></span>  
 <span data-ttu-id="60974-130">[Hiérarchies dérivées avec des majuscules &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="60974-130">[Derived Hierarchies with Explicit Caps &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span></span>  
 [<span data-ttu-id="60974-131">Modifier le nom d’une hiérarchie explicite &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="60974-131">Change an Explicit Hierarchy Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-an-explicit-hierarchy-name-master-data-services.md)  
  
  
