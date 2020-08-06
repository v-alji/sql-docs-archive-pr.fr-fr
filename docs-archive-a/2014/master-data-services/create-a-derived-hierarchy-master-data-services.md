---
title: Créer une hiérarchie dérivée (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- derived hierarchies, creating
- creating derived hierarchies [Master Data Services]
ms.assetid: fec653c4-11cc-46a2-8dd8-b605341ebb40
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 20469ad30222e43a3104503cc32187c2e6512743
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701256"
---
# <a name="create-a-derived-hierarchy-master-data-services"></a><span data-ttu-id="d8f96-102">Créer une hiérarchie dérivée (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d8f96-102">Create a Derived Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="d8f96-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], créez une hiérarchie dérivée lorsque vous avez besoin d'une hiérarchie basée sur le niveau qui vérifie que les membres existent au niveau correct.</span><span class="sxs-lookup"><span data-stu-id="d8f96-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a derived hierarchy when you want a level-based hierarchy that ensures that members exist at the correct level.</span></span> <span data-ttu-id="d8f96-104">Les hiérarchies dérivées sont basées sur les relations d'attribut basé sur un domaine qui existent dans un modèle.</span><span class="sxs-lookup"><span data-stu-id="d8f96-104">Derived hierarchies are based on the domain-based attribute relationships that exist in a model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d8f96-105">S'il n'existe pas de valeur d'attribut basé sur un domaine pour un membre, le membre n'est pas inclus dans la hiérarchie dérivée.</span><span class="sxs-lookup"><span data-stu-id="d8f96-105">If a domain-based attribute value doesn't exist for a member, the member is not included in the derived hierarchy.</span></span> <span data-ttu-id="d8f96-106">Pour demander une valeur d’attribut basé sur un domaine pour tous les membres, consultez [Requérir des valeurs d’attribut &#40;Master Data Services&#41;](require-attribute-values-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d8f96-106">See [Require Attribute Values &#40;Master Data Services&#41;](require-attribute-values-master-data-services.md) to require a domain-based attribute value for all members.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d8f96-107">Prérequis</span><span class="sxs-lookup"><span data-stu-id="d8f96-107">Prerequisites</span></span>  
 <span data-ttu-id="d8f96-108">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="d8f96-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="d8f96-109">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="d8f96-109">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="d8f96-110">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="d8f96-110">You must be a model administrator.</span></span> <span data-ttu-id="d8f96-111">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d8f96-111">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-derived-hierarchy"></a><span data-ttu-id="d8f96-112">Pour créer une hiérarchie dérivée</span><span class="sxs-lookup"><span data-stu-id="d8f96-112">To create a derived hierarchy</span></span>  
  
1.  <span data-ttu-id="d8f96-113">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="d8f96-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="d8f96-114">Dans la page **vue du modèle** , dans la barre de menus, pointez sur **gérer** , puis cliquez sur **hiérarchies dérivées**.</span><span class="sxs-lookup"><span data-stu-id="d8f96-114">On the **Model View** page, from the menu bar, point to **Manage** and click **Derived Hierarchies**.</span></span>  
  
3.  <span data-ttu-id="d8f96-115">Dans la page **Maintenance de la hiérarchie dérivée** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="d8f96-115">On the **Derived Hierarchy Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="d8f96-116">Cliquez sur **Ajouter une hiérarchie dérivée**.</span><span class="sxs-lookup"><span data-stu-id="d8f96-116">Click **Add derived hierarchy**.</span></span>  
  
5.  <span data-ttu-id="d8f96-117">Dans la page **Ajouter une hiérarchie dérivée** , renseignez la zone **Nom de la hiérarchie dérivée** .</span><span class="sxs-lookup"><span data-stu-id="d8f96-117">On the **Add Derived Hierarchy** page, in the **Derived hierarchy name** box, type a name for the hierarchy.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="d8f96-118"> Utilisez un nom qui décrit les niveaux dans la hiérarchie, par exemple **Product to Subcategory to Category**.</span><span class="sxs-lookup"><span data-stu-id="d8f96-118">Use a name that describes the levels in the hierarchy, for example **Product to Subcategory to Category**.</span></span>  
  
6.  <span data-ttu-id="d8f96-119">Cliquez sur **Enregistrer la hiérarchie dérivée**.</span><span class="sxs-lookup"><span data-stu-id="d8f96-119">Click **Save derived hierarchy**.</span></span>  
  
7.  <span data-ttu-id="d8f96-120">Dans la page **modifier la hiérarchie dérivée** , dans le volet **entités et hiérarchies disponibles** , cliquez sur une entité ou une hiérarchie et faites-la glisser vers le volet **niveaux actuels** .</span><span class="sxs-lookup"><span data-stu-id="d8f96-120">On the **Edit Derived Hierarchy** page, in the **Available Entities and Hierarchies** pane, click an entity or hierarchy and drag it to the **Current Levels** pane.</span></span>  
  
8.  <span data-ttu-id="d8f96-121">Continuez à faire glisser des entités ou des hiérarchies jusqu'à ce que votre hiérarchie soit terminée.</span><span class="sxs-lookup"><span data-stu-id="d8f96-121">Continue dragging entities or hierarchies until your hierarchy is complete.</span></span>  
  
9. <span data-ttu-id="d8f96-122">Cliquez sur **Précédent**.</span><span class="sxs-lookup"><span data-stu-id="d8f96-122">Click **Back**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8f96-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d8f96-123">See Also</span></span>  
 <span data-ttu-id="d8f96-124">[Hiérarchies dérivées &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d8f96-124">[Derived Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span></span>  
 <span data-ttu-id="d8f96-125">[Hiérarchies dérivées avec des majuscules &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d8f96-125">[Derived Hierarchies with Explicit Caps &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span></span>  
 [<span data-ttu-id="d8f96-126">Attributs basés sur un domaine &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d8f96-126">Domain-Based Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/domain-based-attributes-master-data-services.md)  
  
  
