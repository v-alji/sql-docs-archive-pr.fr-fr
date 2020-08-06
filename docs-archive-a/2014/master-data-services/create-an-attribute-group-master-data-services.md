---
title: Créer un groupe d’attributs (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attribute groups [Master Data Services], creating
- creating attribute groups [Master Data Services]
ms.assetid: 798c325e-e8d8-412a-b02e-118f2741d1c7
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fbd95869082ea0a73f3abea092163c4705e4da5c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705223"
---
# <a name="create-an-attribute-group-master-data-services"></a><span data-ttu-id="4b574-102">Créer un groupe d'attributs (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="4b574-102">Create an Attribute Group (Master Data Services)</span></span>
  <span data-ttu-id="4b574-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], créez des groupes d'attributs lorsque vous souhaitez afficher des attributs sous des onglets individuels dans la grille de l' **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="4b574-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create attribute groups when you want to display attributes on individual tabs in the **Explorer** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4b574-104">Lorsque vous créez un groupe d'attributs, il est automatiquement masqué pour tous les utilisateurs, à l'exception de son créateur.</span><span class="sxs-lookup"><span data-stu-id="4b574-104">When you create an attribute group, it is automatically hidden from all users except the one who created it.</span></span> <span data-ttu-id="4b574-105">Pour plus d’informations sur le fait de rendre visible le groupe, consultez [Rendre un groupe d’attributs visible pour les utilisateurs &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4b574-105">For more information about making the group visible, see [Make an Attribute Group Visible to Users &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4b574-106">Prérequis</span><span class="sxs-lookup"><span data-stu-id="4b574-106">Prerequisites</span></span>  
 <span data-ttu-id="4b574-107">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="4b574-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="4b574-108">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="4b574-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="4b574-109">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="4b574-109">You must be a model administrator.</span></span> <span data-ttu-id="4b574-110">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4b574-110">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="4b574-111">Au moins un attribut doit exister.</span><span class="sxs-lookup"><span data-stu-id="4b574-111">At least one attribute must exist.</span></span> <span data-ttu-id="4b574-112">Pour plus d’informations, consultez [Créer un attribut de texte &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4b574-112">For more information, see [Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span></span>  
  
### <a name="to-create-an-attribute-group"></a><span data-ttu-id="4b574-113">Pour créer un groupe d'attributs</span><span class="sxs-lookup"><span data-stu-id="4b574-113">To create an attribute group</span></span>  
  
1.  <span data-ttu-id="4b574-114">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="4b574-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="4b574-115">Dans la page **vue du modèle** , dans la barre de menus, pointez sur **gérer** , puis cliquez sur groupes d' **attributs**.</span><span class="sxs-lookup"><span data-stu-id="4b574-115">On the **Model View** page, from the menu bar, point to **Manage** and click **Attribute Groups**.</span></span>  
  
3.  <span data-ttu-id="4b574-116">Dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="4b574-116">From the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="4b574-117">Dans la liste **Entité** , sélectionnez une entité.</span><span class="sxs-lookup"><span data-stu-id="4b574-117">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="4b574-118">Cliquez sur **Groupes feuille**, **Groupes consolidés**ou **Groupes de collections** pour créer respectivement un groupe d'attributs pour les membres feuille, les membres consolidés ou les collections.</span><span class="sxs-lookup"><span data-stu-id="4b574-118">Click **Leaf Groups**, **Consolidated Groups**, or **Collection Groups** to create an attribute group of leaf members, consolidated members, or collections respectively.</span></span>  
  
6.  <span data-ttu-id="4b574-119">Cliquez sur **Ajouter un groupe d’attributs**.</span><span class="sxs-lookup"><span data-stu-id="4b574-119">Click **Add attribute group**.</span></span>  
  
7.  <span data-ttu-id="4b574-120">Dans la zone **nom du groupe feuille** , tapez un nom pour le groupe.</span><span class="sxs-lookup"><span data-stu-id="4b574-120">In the **Leaf group name** box, type a name for the group.</span></span> <span data-ttu-id="4b574-121">Il s’agit du nom affiché sous l’onglet dans l' **Explorateur**.</span><span class="sxs-lookup"><span data-stu-id="4b574-121">This is the name displayed on the tab in **Explorer**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4b574-122">Si vous avez sélectionné **groupes consolidés** ou **groupes de collections** à l’étape 5, cette zone est respectivement un nom de **groupe consolidé** ou un **nom de groupe de collection**.</span><span class="sxs-lookup"><span data-stu-id="4b574-122">If you selected **Consolidated Groups** or **Collection Groups** in step 5, this box is **Consolidated group name** or **Collection group name**, respectively.</span></span>  
  
8.  <span data-ttu-id="4b574-123">Cliquez sur **Enregistrer le groupe**.</span><span class="sxs-lookup"><span data-stu-id="4b574-123">Click **Save group**.</span></span>  
  
9. <span data-ttu-id="4b574-124">Développez le dossier du groupe.</span><span class="sxs-lookup"><span data-stu-id="4b574-124">Expand the folder for the group.</span></span>  
  
10. <span data-ttu-id="4b574-125">Cliquez sur **Attributs**.</span><span class="sxs-lookup"><span data-stu-id="4b574-125">Click **Attributes**.</span></span>  
  
11. <span data-ttu-id="4b574-126">Cliquez sur **modifier l’élément sélectionné**.</span><span class="sxs-lookup"><span data-stu-id="4b574-126">Click **Edit selected item**.</span></span>  
  
12. <span data-ttu-id="4b574-127">Cliquez sur attributs dans la zone **disponible** , puis cliquez sur la flèche **Ajouter** .</span><span class="sxs-lookup"><span data-stu-id="4b574-127">Click attributes in the **Available** box and click the **Add** arrow.</span></span> <span data-ttu-id="4b574-128">Pour les ajouter tous, cliquez sur la flèche **Ajouter tout** .</span><span class="sxs-lookup"><span data-stu-id="4b574-128">To add all, click the **Add All** arrow.</span></span>  
  
13. <span data-ttu-id="4b574-129">Si vous le souhaitez, cliquez sur les flèches vers le **haut** et vers le **bas** pour modifier l’ordre de gauche à droite des attributs.</span><span class="sxs-lookup"><span data-stu-id="4b574-129">Optionally, click the **Up** and **Down** arrows to change the left-to-right order of the attributes.</span></span>  
  
14. <span data-ttu-id="4b574-130">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="4b574-130">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4b574-131">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="4b574-131">Next Steps</span></span>  
  
-   [<span data-ttu-id="4b574-132">Rendre un groupe d’attributs visible pour les utilisateurs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4b574-132">Make an Attribute Group Visible to Users &#40;Master Data Services&#41;</span></span>](make-an-attribute-group-visible-to-users-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="4b574-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4b574-133">See Also</span></span>  
 <span data-ttu-id="4b574-134">[Groupes d’attributs &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="4b574-134">[Attribute Groups &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span></span>  
 <span data-ttu-id="4b574-135">[Attributs &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="4b574-135">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="4b574-136">[Modifiez le nom d’un groupe d’attributs &#40;Master Data Services&#41;](../../2014/master-data-services/change-an-attribute-group-name-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="4b574-136">[Change an Attribute Group Name &#40;Master Data Services&#41;](../../2014/master-data-services/change-an-attribute-group-name-master-data-services.md) </span></span>  
 <span data-ttu-id="4b574-137">[Supprimer un groupe d’attributs &#40;Master Data Services&#41;](../../2014/master-data-services/delete-an-attribute-group-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="4b574-137">[Delete an Attribute Group &#40;Master Data Services&#41;](../../2014/master-data-services/delete-an-attribute-group-master-data-services.md) </span></span>  
 <span data-ttu-id="4b574-138">[Autorisations feuille &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="4b574-138">[Leaf Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="4b574-139">Autorisations consolidées &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4b574-139">Consolidated Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-permissions-master-data-services.md)  
  
  
