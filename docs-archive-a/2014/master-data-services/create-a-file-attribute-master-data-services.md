---
title: Créer un attribut de fichier (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating file attributes [Master Data Services]
- attributes [Master Data Services], creating file attributes
ms.assetid: d224886b-2ef1-4658-8b01-2213cc4b8df6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f4f6e2f10a830d089d1d217f7cf54d0b8557add9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602182"
---
# <a name="create-a-file-attribute-master-data-services"></a><span data-ttu-id="a67cf-102">Créer un attribut de fichier (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="a67cf-102">Create a File Attribute (Master Data Services)</span></span>
  <span data-ttu-id="a67cf-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], créez un attribut de fichier pour remplir les valeurs d'attribut avec des fichiers.</span><span class="sxs-lookup"><span data-stu-id="a67cf-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a file attribute to populate attribute values with files.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a67cf-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="a67cf-104">Prerequisites</span></span>  
 <span data-ttu-id="a67cf-105">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="a67cf-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="a67cf-106">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="a67cf-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="a67cf-107">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="a67cf-107">You must be a model administrator.</span></span> <span data-ttu-id="a67cf-108">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a67cf-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="a67cf-109">Une entité doit exister pour créer l'attribut qui lui est destiné.</span><span class="sxs-lookup"><span data-stu-id="a67cf-109">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="a67cf-110">Pour plus d’informations, consultez [créer une entité &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a67cf-110">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-file-attribute"></a><span data-ttu-id="a67cf-111">Pour créer un attribut de fichier</span><span class="sxs-lookup"><span data-stu-id="a67cf-111">To create a file attribute</span></span>  
  
1.  <span data-ttu-id="a67cf-112">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="a67cf-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="a67cf-113">Dans la page **Vue du modèle** , dans la barre de menus, pointez sur **Gérer** , puis cliquez sur **Entités**.</span><span class="sxs-lookup"><span data-stu-id="a67cf-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="a67cf-114">Dans la page **Maintenance de l'entité** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="a67cf-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="a67cf-115">Sélectionnez la ligne de l'entité pour laquelle vous souhaitez créer un attribut.</span><span class="sxs-lookup"><span data-stu-id="a67cf-115">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="a67cf-116">Cliquez sur **Modifier l'entité sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="a67cf-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="a67cf-117">Dans la page **Modifier l'entité** :</span><span class="sxs-lookup"><span data-stu-id="a67cf-117">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="a67cf-118">Si l'attribut est destiné à des membres feuille, dans le volet **Attributs de membre feuille** , cliquez sur **Ajouter un attribut feuille**.</span><span class="sxs-lookup"><span data-stu-id="a67cf-118">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="a67cf-119">Si l'attribut est destiné à des membres consolidés, dans le volet **Attributs de membre consolidé** , cliquez sur **Ajouter un attribut consolidé**.</span><span class="sxs-lookup"><span data-stu-id="a67cf-119">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="a67cf-120">Si l'attribut est destiné à des collections, dans le volet **Attributs de collection** , cliquez sur **Ajouter un attribut de collection**.</span><span class="sxs-lookup"><span data-stu-id="a67cf-120">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="a67cf-121">Dans la page **Ajouter un attribut** , sélectionnez l’option **fichier** .</span><span class="sxs-lookup"><span data-stu-id="a67cf-121">On the **Add Attribute** page, select the **File** option.</span></span>  
  
8.  <span data-ttu-id="a67cf-122">Dans la zone **Nom** , tapez un nom pour l'attribut.</span><span class="sxs-lookup"><span data-stu-id="a67cf-122">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="a67cf-123">Pour obtenir la liste des mots qui ne doivent pas être utilisés comme noms d’attribut, consultez la section [Mots réservés &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a67cf-123">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="a67cf-124">Dans la zone **Largeur d'affichage en pixels** , tapez la largeur de la colonne d'attribut à afficher dans la grille **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="a67cf-124">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="a67cf-125">Dans la liste **extension de fichier** , sélectionnez un ou plusieurs types de fichiers qu’un utilisateur peut télécharger, ou laissez la valeur par défaut (\*. \* ) pour autoriser tous les types de fichiers.</span><span class="sxs-lookup"><span data-stu-id="a67cf-125">From the **File extension** list, select one or more file types that a user can upload, or leave the default (\*.\*) to allow all file types.</span></span>  
  
11. <span data-ttu-id="a67cf-126">Sélectionnez éventuellement **Activer le suivi des modifications** pour effectuer le suivi des modifications apportées aux groupes d'attributs.</span><span class="sxs-lookup"><span data-stu-id="a67cf-126">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="a67cf-127">Pour plus d’informations, consultez [Ajouter des attributs à un groupe de suivi des modifications &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a67cf-127">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
12. <span data-ttu-id="a67cf-128">Cliquez sur **Enregistrer l'attribut**.</span><span class="sxs-lookup"><span data-stu-id="a67cf-128">Click **Save attribute**.</span></span>  
  
13. <span data-ttu-id="a67cf-129">Dans la page **Maintenance de l'entité** , cliquez sur **Enregistrer l'entité**.</span><span class="sxs-lookup"><span data-stu-id="a67cf-129">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a67cf-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a67cf-130">See Also</span></span>  
 <span data-ttu-id="a67cf-131">[Attributs &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a67cf-131">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="a67cf-132">[Modifier le nom d’un attribut &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a67cf-132">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="a67cf-133">[Créer un attribut basé sur un domaine &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a67cf-133">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="a67cf-134">Créer un attribut de texte &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a67cf-134">Create a Text Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-text-attribute-master-data-services.md)  
  
  
