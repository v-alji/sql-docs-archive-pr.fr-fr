---
title: Déplacer des membres au sein d’une hiérarchie (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Master Data Services], moving members
- explicit hierarchies, moving members
- derived hierarchies, moving members
- members [Master Data Services], moving
ms.assetid: 049c9a15-89c1-478c-8438-028fffc9e187
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 37167f76b965197dbf8e37e365778395ec640d38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604039"
---
# <a name="move-members-within-a-hierarchy-master-data-services"></a><span data-ttu-id="79b01-102">Déplacer des membres au sein d'une hiérarchie (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="79b01-102">Move Members within a Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="79b01-103">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], déplacez les membres au sein d'une hiérarchie pour modifier leur emplacement ou l'affectation du parent.</span><span class="sxs-lookup"><span data-stu-id="79b01-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], move members within a hierarchy to change their location or parent assignment.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="79b01-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="79b01-104">Prerequisites</span></span>  
 <span data-ttu-id="79b01-105">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="79b01-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="79b01-106">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="79b01-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="79b01-107">Pour les hiérarchies explicites, vous devez disposer au minimum de l’autorisation **mettre à jour** sur l’entité.</span><span class="sxs-lookup"><span data-stu-id="79b01-107">For explicit hierarchies, you must have a minimum of **Update** permission to the entity.</span></span>  
  
-   <span data-ttu-id="79b01-108">Pour les hiérarchies dérivées, vous devez disposer au minimum d’une **mise à jour** du modèle et de tous les attributs basés sur un domaine utilisés dans la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="79b01-108">For derived hierarchies, you must have a minimum of **Update** to the model and to any domain-based attributes used in the hierarchy.</span></span>  
  
### <a name="to-move-members-within-a-hierarchy"></a><span data-ttu-id="79b01-109">Pour déplacer des membres au sein d'une hiérarchie</span><span class="sxs-lookup"><span data-stu-id="79b01-109">To move members within a hierarchy</span></span>  
  
1.  <span data-ttu-id="79b01-110">Dans la page d'accueil de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="79b01-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="79b01-111">Dans la liste **Version** , sélectionnez une version.</span><span class="sxs-lookup"><span data-stu-id="79b01-111">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="79b01-112">Cliquez sur **Explorateur**.</span><span class="sxs-lookup"><span data-stu-id="79b01-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="79b01-113">Dans la barre de menus, pointez sur **hiérarchies** , puis cliquez sur *hierarchy_name*.</span><span class="sxs-lookup"><span data-stu-id="79b01-113">From the menu bar, point to **Hierarchies** and click *hierarchy_name*.</span></span>  
  
5.  <span data-ttu-id="79b01-114">Dans le volet **hiérarchie** , où la hiérarchie est affichée dans une arborescence, activez la case à cocher de chaque membre que vous souhaitez déplacer.</span><span class="sxs-lookup"><span data-stu-id="79b01-114">In the **Hierarchy** pane, where the hierarchy is displayed in a tree structure, click the check box for each member you want to move.</span></span>  
  
6.  <span data-ttu-id="79b01-115">En haut du volet **hiérarchie** , cliquez sur **couper**.</span><span class="sxs-lookup"><span data-stu-id="79b01-115">At the top of the **Hierarchy** pane, click **Cut**.</span></span>  
  
7.  <span data-ttu-id="79b01-116">Dans le volet **hiérarchie** , cliquez sur la case à cocher du membre vers lequel vous souhaitez déplacer les membres.</span><span class="sxs-lookup"><span data-stu-id="79b01-116">In the **Hierarchy** pane, click the check box for the member you want to move the members to.</span></span>  
  
8.  <span data-ttu-id="79b01-117">Cliquez sur **coller**.</span><span class="sxs-lookup"><span data-stu-id="79b01-117">Click **Paste**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="79b01-118">Dans les hiérarchies dérivées, vous pouvez uniquement déplacer des membres vers le même niveau.</span><span class="sxs-lookup"><span data-stu-id="79b01-118">In derived hierarchies, you can move members to the same level only.</span></span> <span data-ttu-id="79b01-119">Par ailleurs, vous ne pouvez pas modifier l'ordre de tri des membres.</span><span class="sxs-lookup"><span data-stu-id="79b01-119">Also, you cannot change the sort order of members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79b01-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="79b01-120">See Also</span></span>  
 <span data-ttu-id="79b01-121">[Déplacer des membres de hiérarchie explicites à l’aide du processus de site &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="79b01-121">[Move Explicit Hierarchy Members by Using the Staging Process &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span></span>  
 <span data-ttu-id="79b01-122">[Hiérarchies dérivées &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="79b01-122">[Derived Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span></span>  
 [<span data-ttu-id="79b01-123">Hiérarchies explicites &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="79b01-123">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)  
  
  
