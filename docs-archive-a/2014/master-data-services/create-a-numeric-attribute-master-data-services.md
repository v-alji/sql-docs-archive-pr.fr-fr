---
title: Créer un attribut numérique (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], creating number attributes
- creating number attributes [Master Data Services]
ms.assetid: c0dbb6d8-ba78-485a-a40d-6d5cb7e75d0a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bb9302c0b585c21410a6a764dc2e6dac845c6299
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600127"
---
# <a name="create-a-numeric-attribute-master-data-services"></a><span data-ttu-id="e1895-102">Créer un attribut numérique (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="e1895-102">Create a Numeric Attribute (Master Data Services)</span></span>
  <span data-ttu-id="e1895-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], créez un attribut numérique lorsque vous souhaitez que les utilisateurs entrent un nombre comme valeur d'attribut.</span><span class="sxs-lookup"><span data-stu-id="e1895-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a numeric attribute when you want users to enter a number as an attribute value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e1895-104">Les attributs numériques ont des limitations.</span><span class="sxs-lookup"><span data-stu-id="e1895-104">Numeric attributes have limitations.</span></span> <span data-ttu-id="e1895-105">Pour plus d’informations, consultez [Attributs &#40;Master Data Services&#41;](attributes-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e1895-105">For more information, see [Attributes &#40;Master Data Services&#41;](attributes-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e1895-106">Prérequis</span><span class="sxs-lookup"><span data-stu-id="e1895-106">Prerequisites</span></span>  
 <span data-ttu-id="e1895-107">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="e1895-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="e1895-108">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="e1895-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="e1895-109">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="e1895-109">You must be a model administrator.</span></span> <span data-ttu-id="e1895-110">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e1895-110">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="e1895-111">Une entité doit exister pour créer l'attribut qui lui est destiné.</span><span class="sxs-lookup"><span data-stu-id="e1895-111">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="e1895-112">Pour plus d’informations, consultez [créer une entité &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e1895-112">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-numeric-attribute"></a><span data-ttu-id="e1895-113">Pour créer un attribut numérique</span><span class="sxs-lookup"><span data-stu-id="e1895-113">To create a numeric attribute</span></span>  
  
1.  <span data-ttu-id="e1895-114">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="e1895-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="e1895-115">Dans la page **Vue du modèle** , dans la barre de menus, pointez sur **Gérer** , puis cliquez sur **Entités**.</span><span class="sxs-lookup"><span data-stu-id="e1895-115">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="e1895-116">Dans la page **Maintenance de l'entité** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="e1895-116">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="e1895-117">Sélectionnez la ligne de l'entité pour laquelle vous souhaitez créer un attribut.</span><span class="sxs-lookup"><span data-stu-id="e1895-117">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="e1895-118">Cliquez sur **Modifier l'entité sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="e1895-118">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="e1895-119">Dans la page **Modifier l'entité** :</span><span class="sxs-lookup"><span data-stu-id="e1895-119">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="e1895-120">Si l'attribut est destiné à des membres feuille, dans le volet **Attributs de membre feuille** , cliquez sur **Ajouter un attribut feuille**.</span><span class="sxs-lookup"><span data-stu-id="e1895-120">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="e1895-121">Si l'attribut est destiné à des membres consolidés, dans le volet **Attributs de membre consolidé** , cliquez sur **Ajouter un attribut consolidé**.</span><span class="sxs-lookup"><span data-stu-id="e1895-121">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="e1895-122">Si l'attribut est destiné à des collections, dans le volet **Attributs de collection** , cliquez sur **Ajouter un attribut de collection**.</span><span class="sxs-lookup"><span data-stu-id="e1895-122">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="e1895-123">Dans la page **Ajouter un attribut** , sélectionnez l'option **Forme libre** .</span><span class="sxs-lookup"><span data-stu-id="e1895-123">On the **Add Attribute** page, select the **Free-form** option.</span></span>  
  
8.  <span data-ttu-id="e1895-124">Dans la zone **Nom** , tapez un nom pour l'attribut.</span><span class="sxs-lookup"><span data-stu-id="e1895-124">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="e1895-125">Pour obtenir la liste des mots qui ne doivent pas être utilisés comme noms d’attribut, consultez la section [Mots réservés &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e1895-125">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="e1895-126">Dans la zone **Largeur d'affichage en pixels** , tapez la largeur de la colonne d'attribut à afficher dans la grille **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="e1895-126">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="e1895-127">Dans la liste **Type de données** , sélectionnez **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="e1895-127">From the **Data type** list, select **Number**.</span></span>  
  
11. <span data-ttu-id="e1895-128">Dans la zone **Décimales** , tapez le nombre de chiffres qui peuvent être entrés après la virgule décimale.</span><span class="sxs-lookup"><span data-stu-id="e1895-128">In the **Decimals** box, type the number of numbers that can be entered after a decimal.</span></span>  
  
12. <span data-ttu-id="e1895-129">Dans la liste **masque d’entrée** , sélectionnez un format pour les nombres négatifs.</span><span class="sxs-lookup"><span data-stu-id="e1895-129">From the **Input mask** list, select a format for negative numbers.</span></span>  
  
13. <span data-ttu-id="e1895-130">Sélectionnez éventuellement **Activer le suivi des modifications** pour effectuer le suivi des modifications apportées aux groupes d'attributs.</span><span class="sxs-lookup"><span data-stu-id="e1895-130">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="e1895-131">Pour plus d’informations, consultez [Ajouter des attributs à un groupe de suivi des modifications &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) .</span><span class="sxs-lookup"><span data-stu-id="e1895-131">See [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) for more information.</span></span>  
  
14. <span data-ttu-id="e1895-132">Cliquez sur **Enregistrer l'attribut**.</span><span class="sxs-lookup"><span data-stu-id="e1895-132">Click **Save attribute**.</span></span>  
  
15. <span data-ttu-id="e1895-133">Dans la page **Maintenance de l'entité** , cliquez sur **Enregistrer l'entité**.</span><span class="sxs-lookup"><span data-stu-id="e1895-133">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1895-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e1895-134">See Also</span></span>  
 <span data-ttu-id="e1895-135">[Attributs &#40;Master Data Services&#41;](attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e1895-135">[Attributes &#40;Master Data Services&#41;](attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="e1895-136">[Modifier le nom d’un attribut &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e1895-136">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="e1895-137">[Créer un attribut basé sur un domaine &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e1895-137">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="e1895-138">Créer un attribut de fichier &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e1895-138">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
  
