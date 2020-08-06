---
title: Créer un attribut basé sur un domaine (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- domain-based attributes [Master Data Services], creating
- creating domain-based attributes [Master Data Services]
- attributes [Master Data Services], creating domain-based attributes
ms.assetid: 11c31c9f-e6cc-47b7-b76a-d691f84c93c6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 51c0f44bb76ae2ad4c25987ed5e5ee144a18c739
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602183"
---
# <a name="create-a-domain-based-attribute-master-data-services"></a><span data-ttu-id="75c76-102">Créer un attribut basé sur un domaine (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="75c76-102">Create a Domain-Based Attribute (Master Data Services)</span></span>
  <span data-ttu-id="75c76-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], créez un attribut basé sur un domaine pour remplir les valeurs d'un attribut avec les membres d'une entité.</span><span class="sxs-lookup"><span data-stu-id="75c76-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a domain-based attribute to populate an attribute's values with members from an entity.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="75c76-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="75c76-104">Prerequisites</span></span>  
 <span data-ttu-id="75c76-105">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="75c76-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="75c76-106">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="75c76-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="75c76-107">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="75c76-107">You must be a model administrator.</span></span> <span data-ttu-id="75c76-108">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="75c76-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="75c76-109">Une entité doit exister pour servir de source de valeurs d'attribut.</span><span class="sxs-lookup"><span data-stu-id="75c76-109">An entity must exist to use as the source of the attribute values.</span></span> <span data-ttu-id="75c76-110">Par exemple, vous devez créer l'entité Color avant de créer un attribut basé sur un domaine et sur l'entité Color.</span><span class="sxs-lookup"><span data-stu-id="75c76-110">For example, to create a domain-based attribute based on the Color entity, you must first create the Color entity.</span></span> <span data-ttu-id="75c76-111">Pour plus d’informations, consultez [créer une entité &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="75c76-111">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="75c76-112">Une entité doit exister pour créer l'attribut qui lui est destiné.</span><span class="sxs-lookup"><span data-stu-id="75c76-112">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="75c76-113">Pour plus d’informations, consultez [créer une entité &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="75c76-113">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-domain-based-attribute"></a><span data-ttu-id="75c76-114">Pour créer un attribut basé sur un domaine</span><span class="sxs-lookup"><span data-stu-id="75c76-114">To create a domain-based attribute</span></span>  
  
1.  <span data-ttu-id="75c76-115">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="75c76-115">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="75c76-116">Dans la page **Vue du modèle** , dans la barre de menus, pointez sur **Gérer** , puis cliquez sur **Entités**.</span><span class="sxs-lookup"><span data-stu-id="75c76-116">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="75c76-117">Dans la page **Maintenance de l'entité** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="75c76-117">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="75c76-118">Sélectionnez la ligne de l'entité pour laquelle vous souhaitez créer un attribut.</span><span class="sxs-lookup"><span data-stu-id="75c76-118">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="75c76-119">Cliquez sur **Modifier l'entité sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="75c76-119">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="75c76-120">Dans la page **Modifier l'entité** :</span><span class="sxs-lookup"><span data-stu-id="75c76-120">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="75c76-121">Si l'attribut est destiné à des membres feuille, dans le volet **Attributs de membre feuille** , cliquez sur **Ajouter un attribut feuille**.</span><span class="sxs-lookup"><span data-stu-id="75c76-121">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="75c76-122">Si l'attribut est destiné à des membres consolidés, dans le volet **Attributs de membre consolidé** , cliquez sur **Ajouter un attribut consolidé**.</span><span class="sxs-lookup"><span data-stu-id="75c76-122">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="75c76-123">Si l'attribut est destiné à des collections, dans le volet **Attributs de collection** , cliquez sur **Ajouter un attribut de collection**.</span><span class="sxs-lookup"><span data-stu-id="75c76-123">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="75c76-124">Dans la page **Ajouter un attribut** , sélectionnez l’option **basée sur un domaine** .</span><span class="sxs-lookup"><span data-stu-id="75c76-124">On the **Add Attribute** page, select the **Domain-based** option.</span></span>  
  
8.  <span data-ttu-id="75c76-125">Dans la zone **Nom** , tapez un nom pour l'attribut.</span><span class="sxs-lookup"><span data-stu-id="75c76-125">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="75c76-126">Il ne doit pas nécessairement s'agir du nom de l'entité qui sert de source aux valeurs d'attribut.</span><span class="sxs-lookup"><span data-stu-id="75c76-126">It does not have to be the same name as the entity that you use for the source of the attribute values.</span></span>  
  
9. <span data-ttu-id="75c76-127">Dans la zone **Largeur d'affichage en pixels** , tapez la largeur de la colonne d'attribut à afficher dans la grille **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="75c76-127">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="75c76-128">Dans la liste **entité** , choisissez l’entité à utiliser pour renseigner les valeurs d’attribut.</span><span class="sxs-lookup"><span data-stu-id="75c76-128">From the **Entity** list, choose the entity to be used to populate the attribute values.</span></span>  
  
11. <span data-ttu-id="75c76-129">facultatif.</span><span class="sxs-lookup"><span data-stu-id="75c76-129">Optional.</span></span> <span data-ttu-id="75c76-130">Sélectionnez **Activer le suivi des modifications** pour effectuer le suivi des modifications apportées aux groupes d'attributs.</span><span class="sxs-lookup"><span data-stu-id="75c76-130">Select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="75c76-131">Pour plus d’informations, consultez [Ajouter des attributs à un groupe de suivi des modifications &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="75c76-131">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
12. <span data-ttu-id="75c76-132">Cliquez sur **Enregistrer l'attribut**.</span><span class="sxs-lookup"><span data-stu-id="75c76-132">Click **Save attribute**.</span></span>  
  
13. <span data-ttu-id="75c76-133">Dans la page **Maintenance de l'entité** , cliquez sur **Enregistrer l'entité**.</span><span class="sxs-lookup"><span data-stu-id="75c76-133">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75c76-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="75c76-134">See Also</span></span>  
 <span data-ttu-id="75c76-135">[Attributs basés sur un domaine &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="75c76-135">[Domain-Based Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="75c76-136">[Créer une hiérarchie dérivée &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-derived-hierarchy-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="75c76-136">[Create a Derived Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-derived-hierarchy-master-data-services.md) </span></span>  
 <span data-ttu-id="75c76-137">[Modifier le nom d’un attribut &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="75c76-137">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 [<span data-ttu-id="75c76-138">Supprimer un attribut &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="75c76-138">Delete an Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-attribute-master-data-services.md)  
  
  
