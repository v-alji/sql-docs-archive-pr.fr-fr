---
title: Créer un attribut de lien (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], creating link attributes
- creating link attributes [Master Data Services]
ms.assetid: e6658e9c-5b08-4b8d-b556-17ec2dd041d2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4770d7904371c10dc6720e8d3d7f28ca797d9b80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614711"
---
# <a name="create-a-link-attribute-master-data-services"></a><span data-ttu-id="9a161-102">Créer un attribut de lien (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9a161-102">Create a Link Attribute (Master Data Services)</span></span>
  <span data-ttu-id="9a161-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], créez un attribut de lien quand vous souhaitez que les utilisateurs entrent un lien hypertexte comme valeur d’attribut, par exemple, `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="9a161-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a link attribute when you want users to enter a hyperlink as an attribute value, such as `http://www.contoso.com`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9a161-104">Quand les utilisateurs entrent une valeur pour un attribut de lien, la chaîne doit commencer par **http://** , sinon une erreur est affichée.</span><span class="sxs-lookup"><span data-stu-id="9a161-104">When users enter a value for a link attribute, the string must begin with **http://** or an error will be displayed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9a161-105">Prérequis</span><span class="sxs-lookup"><span data-stu-id="9a161-105">Prerequisites</span></span>  
 <span data-ttu-id="9a161-106">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="9a161-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="9a161-107">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="9a161-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="9a161-108">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="9a161-108">You must be a model administrator.</span></span> <span data-ttu-id="9a161-109">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9a161-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="9a161-110">Une entité doit exister pour créer l'attribut qui lui est destiné.</span><span class="sxs-lookup"><span data-stu-id="9a161-110">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="9a161-111">Pour plus d’informations, consultez [créer une entité &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9a161-111">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-link-attribute"></a><span data-ttu-id="9a161-112">Pour créer un attribut de lien</span><span class="sxs-lookup"><span data-stu-id="9a161-112">To create a link attribute</span></span>  
  
1.  <span data-ttu-id="9a161-113">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="9a161-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="9a161-114">Dans la page **Vue du modèle** , dans la barre de menus, pointez sur **Gérer** , puis cliquez sur **Entités**.</span><span class="sxs-lookup"><span data-stu-id="9a161-114">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="9a161-115">Dans la page **Maintenance de l'entité** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="9a161-115">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="9a161-116">Sélectionnez la ligne de l'entité pour laquelle vous souhaitez créer un attribut.</span><span class="sxs-lookup"><span data-stu-id="9a161-116">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="9a161-117">Cliquez sur **Modifier l'entité sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="9a161-117">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="9a161-118">Dans la page **Modifier l'entité** :</span><span class="sxs-lookup"><span data-stu-id="9a161-118">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="9a161-119">Si l'attribut est destiné à des membres feuille, dans le volet **Attributs de membre feuille** , cliquez sur **Ajouter un attribut feuille**.</span><span class="sxs-lookup"><span data-stu-id="9a161-119">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="9a161-120">Si l'attribut est destiné à des membres consolidés, dans le volet **Attributs de membre consolidé** , cliquez sur **Ajouter un attribut consolidé**.</span><span class="sxs-lookup"><span data-stu-id="9a161-120">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="9a161-121">Si l'attribut est destiné à des collections, dans le volet **Attributs de collection** , cliquez sur **Ajouter un attribut de collection**.</span><span class="sxs-lookup"><span data-stu-id="9a161-121">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="9a161-122">Dans la page **Ajouter un attribut** , sélectionnez l'option **Forme libre** .</span><span class="sxs-lookup"><span data-stu-id="9a161-122">On the **Add Attribute** page, select the **Free-form** option.</span></span>  
  
8.  <span data-ttu-id="9a161-123">Dans la zone **Nom** , tapez un nom pour l'attribut.</span><span class="sxs-lookup"><span data-stu-id="9a161-123">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="9a161-124">Pour obtenir la liste des mots qui ne doivent pas être utilisés comme noms d’attribut, consultez la section [Mots réservés &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9a161-124">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="9a161-125">Dans la zone **Largeur d'affichage en pixels** , tapez la largeur de la colonne d'attribut à afficher dans la grille **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="9a161-125">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="9a161-126">Dans la liste **Type de données** , sélectionnez **Lien**.</span><span class="sxs-lookup"><span data-stu-id="9a161-126">From the **Data type** list, select **Link**.</span></span>  
  
11. <span data-ttu-id="9a161-127">Dans la zone **Longueur** , tapez le nombre maximal de caractères autorisé.</span><span class="sxs-lookup"><span data-stu-id="9a161-127">In the **Length** box, type the maximum number of characters allowed.</span></span>  
  
12. <span data-ttu-id="9a161-128">Sélectionnez éventuellement **Activer le suivi des modifications** pour effectuer le suivi des modifications apportées aux groupes d'attributs.</span><span class="sxs-lookup"><span data-stu-id="9a161-128">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="9a161-129">Pour plus d’informations, consultez [Ajouter des attributs à un groupe de suivi des modifications &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9a161-129">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
13. <span data-ttu-id="9a161-130">Cliquez sur **Enregistrer l'attribut**.</span><span class="sxs-lookup"><span data-stu-id="9a161-130">Click **Save attribute**.</span></span>  
  
14. <span data-ttu-id="9a161-131">Dans la page **Maintenance de l'entité** , cliquez sur **Enregistrer l'entité**.</span><span class="sxs-lookup"><span data-stu-id="9a161-131">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a161-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9a161-132">See Also</span></span>  
 <span data-ttu-id="9a161-133">[Attributs &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9a161-133">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="9a161-134">[Modifier le nom d’un attribut &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9a161-134">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="9a161-135">[Créer un attribut basé sur un domaine &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9a161-135">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="9a161-136">Créer un attribut de fichier &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9a161-136">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
  
