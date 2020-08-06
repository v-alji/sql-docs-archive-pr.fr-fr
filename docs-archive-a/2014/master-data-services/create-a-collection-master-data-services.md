---
title: Créer une collection (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating collections [Master Data Services]
- collections [Master Data Services], creating
ms.assetid: 3d4f152c-863c-4385-bca9-a9fcd0402e1f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f76171b4fd9b07f751d4f919011a443253fbe31b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703051"
---
# <a name="create-a-collection-master-data-services"></a><span data-ttu-id="0c408-102">Créer une collection (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0c408-102">Create a Collection (Master Data Services)</span></span>
  <span data-ttu-id="0c408-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], créez une collection lorsque vous souhaitez créer des listes en 2D de membres feuille et de membres consolidés.</span><span class="sxs-lookup"><span data-stu-id="0c408-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a collection when you want to create flat lists of leaf and consolidated members.</span></span> <span data-ttu-id="0c408-104">Les collections n'ont pas besoin d'inclure tous les membres de l'entité.</span><span class="sxs-lookup"><span data-stu-id="0c408-104">Collections do not need to include all members from the entity.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0c408-105">Prérequis</span><span class="sxs-lookup"><span data-stu-id="0c408-105">Prerequisites</span></span>  
 <span data-ttu-id="0c408-106">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="0c408-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="0c408-107">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="0c408-107">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="0c408-108">Vous devez avoir au minimum l’autorisation **Mettre à jour** sur l’objet de modèle de collection de l’entité.</span><span class="sxs-lookup"><span data-stu-id="0c408-108">You must have a minimum of **Update** permission to the collection model object for the entity.</span></span>  
  
-   <span data-ttu-id="0c408-109">L'entité doit être activée pour les hiérarchies et collections explicites.</span><span class="sxs-lookup"><span data-stu-id="0c408-109">The entity must be enabled for explicit hierarchies and collections.</span></span> <span data-ttu-id="0c408-110">Pour plus d’informations, consultez [activer une entité pour les hiérarchies explicites et les Collections &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0c408-110">For more information, see [Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span></span>  
  
### <a name="to-create-a-collection"></a><span data-ttu-id="0c408-111">Pour créer une collection</span><span class="sxs-lookup"><span data-stu-id="0c408-111">To create a collection</span></span>  
  
1.  <span data-ttu-id="0c408-112">Dans la page d'accueil de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="0c408-112">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="0c408-113">Dans la liste **Version** , sélectionnez une version.</span><span class="sxs-lookup"><span data-stu-id="0c408-113">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="0c408-114">Cliquez sur **Explorateur**.</span><span class="sxs-lookup"><span data-stu-id="0c408-114">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="0c408-115">Dans la barre de menus, pointez sur **Collections** , puis cliquez sur *entity_name*.</span><span class="sxs-lookup"><span data-stu-id="0c408-115">From the menu bar, point to **Collections** and click *entity_name*.</span></span>  
  
5.  <span data-ttu-id="0c408-116">Cliquez sur **Ajouter une collection**.</span><span class="sxs-lookup"><span data-stu-id="0c408-116">Click **Add collection**.</span></span>  
  
6.  <span data-ttu-id="0c408-117">Sous l’onglet **Détails** , dans la zone **Nom** , tapez un nom pour la collection.</span><span class="sxs-lookup"><span data-stu-id="0c408-117">On the **Details** tab, in the **Name** box, type a name for the collection.</span></span>  
  
7.  <span data-ttu-id="0c408-118">Dans la zone **Code** , tapez un code unique pour la collection.</span><span class="sxs-lookup"><span data-stu-id="0c408-118">In the **Code** box, type a unique code for the collection.</span></span>  
  
8.  <span data-ttu-id="0c408-119">Si vous le souhaitez, dans la zone **Description** , tapez la description de la collection.</span><span class="sxs-lookup"><span data-stu-id="0c408-119">Optionally, in the **Description** box, type a description for the collection.</span></span>  
  
9. <span data-ttu-id="0c408-120">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c408-120">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0c408-121">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="0c408-121">Next Steps</span></span>  
  
-   [<span data-ttu-id="0c408-122">Ajouter des membres à une collection &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0c408-122">Add Members to a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-members-to-a-collection-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="0c408-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0c408-123">See Also</span></span>  
 <span data-ttu-id="0c408-124">[Collections &#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="0c408-124">[Collections &#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md) </span></span>  
 <span data-ttu-id="0c408-125">[Supprimer un membre ou une collection &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="0c408-125">[Delete a Member or Collection &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md) </span></span>  
 [<span data-ttu-id="0c408-126">Créer une hiérarchie explicite &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0c408-126">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)  
  
  
