---
title: Créer un membre consolidé (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating consolidated members [Master Data Services]
- members [Master Data Services], creating consolidated members
- consolidated members [Master Data Services], creating
ms.assetid: 431ab2d2-5517-4372-9980-142b05427c08
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c41673f6f3bf1f4de2a831ecd659321b273b6af9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703040"
---
# <a name="create-a-consolidated-member-master-data-services"></a><span data-ttu-id="4c742-102">Créer un membre consolidé (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="4c742-102">Create a Consolidated Member (Master Data Services)</span></span>
  <span data-ttu-id="4c742-103">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], créez un membre consolidé lorsque vous souhaitez un nœud parent pour une hiérarchie explicite.</span><span class="sxs-lookup"><span data-stu-id="4c742-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], create a consolidated member when you want a parent node for an explicit hierarchy.</span></span> <span data-ttu-id="4c742-104">Les membres consolidés peuvent avoir leurs propres attributs.</span><span class="sxs-lookup"><span data-stu-id="4c742-104">Consolidated members can have their own attributes.</span></span> <span data-ttu-id="4c742-105">Ils sont utilisés pour le regroupement.</span><span class="sxs-lookup"><span data-stu-id="4c742-105">They are used for grouping.</span></span> <span data-ttu-id="4c742-106">Comme indiqué dans l'exemple suivant, les membres consolidés peuvent être utilisés pour les groupes de comptes qui ont des comptes sous eux.</span><span class="sxs-lookup"><span data-stu-id="4c742-106">As shown in the following example, consolidated members can be used for account groups that have accounts under them.</span></span>

 <span data-ttu-id="4c742-107">![Membres consolidés MDS](../../2014/master-data-services/media/mds-consolidated-members.png "Membres consolidés MDS")</span><span class="sxs-lookup"><span data-stu-id="4c742-107">![MDS Consolidated Members](../../2014/master-data-services/media/mds-consolidated-members.png "MDS Consolidated Members")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4c742-108">Prérequis</span><span class="sxs-lookup"><span data-stu-id="4c742-108">Prerequisites</span></span>
 <span data-ttu-id="4c742-109">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="4c742-109">To perform this procedure:</span></span>

-   <span data-ttu-id="4c742-110">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="4c742-110">You must have permission to access the **Explorer** functional area.</span></span>

-   <span data-ttu-id="4c742-111">Vous devez au minimum disposer de l'autorisation **Mettre à jour** sur l'objet modèle consolidé de l'entité à laquelle vous ajoutez un membre.</span><span class="sxs-lookup"><span data-stu-id="4c742-111">You must have a minimum of **Update** permission to the consolidated model object for the entity you are adding a member to.</span></span>

### <a name="to-create-a-consolidated-member"></a><span data-ttu-id="4c742-112">Pour créer un membre consolidé</span><span class="sxs-lookup"><span data-stu-id="4c742-112">To create a consolidated member</span></span>

1.  <span data-ttu-id="4c742-113">Dans la page d'accueil de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="4c742-113">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>

2.  <span data-ttu-id="4c742-114">Dans la liste **Version** , sélectionnez une version.</span><span class="sxs-lookup"><span data-stu-id="4c742-114">From the **Version** list, select a version.</span></span>

3.  <span data-ttu-id="4c742-115">Cliquez sur **Explorateur**.</span><span class="sxs-lookup"><span data-stu-id="4c742-115">Click **Explorer**.</span></span>

4.  <span data-ttu-id="4c742-116">Dans la barre de menus, pointez sur **Hiérarchies** , puis cliquez sur le nom de la hiérarchie à laquelle vous souhaitez ajouter un membre consolidé.</span><span class="sxs-lookup"><span data-stu-id="4c742-116">From the menu bar, point to **Hierarchies** and click the name of the hierarchy you want to add a consolidated member to.</span></span>

5.  <span data-ttu-id="4c742-117">Au-dessus de la grille, sélectionnez **Membres consolidés** ou l'option **Tous les membres consolidés de la hiérarchie** .</span><span class="sxs-lookup"><span data-stu-id="4c742-117">Above the grid, select either the **Consolidated members** or the **All consolidated members in hierarchy** option.</span></span>

6.  <span data-ttu-id="4c742-118">Cliquez sur **Add**.</span><span class="sxs-lookup"><span data-stu-id="4c742-118">Click **Add**.</span></span>

7.  <span data-ttu-id="4c742-119">Dans le volet de droite, remplissez les champs.</span><span class="sxs-lookup"><span data-stu-id="4c742-119">In the pane on the right, complete the fields.</span></span>

8.  <span data-ttu-id="4c742-120">facultatif.</span><span class="sxs-lookup"><span data-stu-id="4c742-120">Optional.</span></span> <span data-ttu-id="4c742-121">Dans la zone **Annotations** , tapez un commentaire pour expliquer l'ajout du membre.</span><span class="sxs-lookup"><span data-stu-id="4c742-121">In the **Annotations** box, type a comment about why the member was added.</span></span> <span data-ttu-id="4c742-122">Tous les utilisateurs ayant accès au membre peuvent afficher l'annotation.</span><span class="sxs-lookup"><span data-stu-id="4c742-122">All users who have access to the member can view the annotation.</span></span>

9. <span data-ttu-id="4c742-123">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c742-123">Click **OK**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4c742-124">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="4c742-124">Next Steps</span></span>

-   [<span data-ttu-id="4c742-125">Déplacer des membres au sein d’une hiérarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4c742-125">Move Members within a Hierarchy &#40;Master Data Services&#41;</span></span>](move-members-within-a-hierarchy-master-data-services.md)

## <a name="see-also"></a><span data-ttu-id="4c742-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4c742-126">See Also</span></span>
 <span data-ttu-id="4c742-127">[Créez une hiérarchie explicite &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) [créer un membre feuille &#40;Master Data Services](../../2014/master-data-services/create-a-leaf-member-master-data-services.md)&#41;[charger ou mettre à jour des membres dans Master Data Services à l’aide des membres du processus de](add-update-and-delete-data-master-data-services.md) site [&#40;](../../2014/master-data-services/members-master-data-services.md) Master Data Services&#41;les [hiérarchies explicites](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4c742-127">[Create an Explicit Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) [Create a Leaf Member &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-leaf-member-master-data-services.md) [Load or Update Members in Master Data Services by Using the Staging Process](add-update-and-delete-data-master-data-services.md) [Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) [Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)</span></span>


