---
title: Modèles (services de données de référence) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], about models
- models [Master Data Services]
ms.assetid: 9f862a3d-25ab-41e9-b833-1db99959e825
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1d5a4a431d3ca7b6fa499de68a2bc4c5033cd086
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614129"
---
# <a name="models-master-data-services"></a><span data-ttu-id="7a367-102">Modèles (services de données de référence)</span><span class="sxs-lookup"><span data-stu-id="7a367-102">Models (Master Data Services)</span></span>
  <span data-ttu-id="7a367-103">Les modèles constituent le niveau d'organisation des données le plus élevé dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a367-103">Models are the highest level of data organization in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span> <span data-ttu-id="7a367-104">Un modèle définit la structure des données dans votre solution de gestion des données de référence.</span><span class="sxs-lookup"><span data-stu-id="7a367-104">A model defines the structure of data in your master data management solution.</span></span> <span data-ttu-id="7a367-105">Un modèle contient les objets suivants :</span><span class="sxs-lookup"><span data-stu-id="7a367-105">A model contains the following objects:</span></span>  
  
-   <span data-ttu-id="7a367-106">Entités</span><span class="sxs-lookup"><span data-stu-id="7a367-106">Entities</span></span>  
  
-   <span data-ttu-id="7a367-107">Attributs et groupes d'attributs</span><span class="sxs-lookup"><span data-stu-id="7a367-107">Attributes and attribute groups</span></span>  
  
-   <span data-ttu-id="7a367-108">Hiérarchies explicites et dérivées</span><span class="sxs-lookup"><span data-stu-id="7a367-108">Explicit and derived hierarchies</span></span>  
  
-   <span data-ttu-id="7a367-109">Collections</span><span class="sxs-lookup"><span data-stu-id="7a367-109">Collections</span></span>  
  
 <span data-ttu-id="7a367-110">Les modèles organisent la structure de vos données de référence.</span><span class="sxs-lookup"><span data-stu-id="7a367-110">Models organize the structure of your master data.</span></span> <span data-ttu-id="7a367-111">Votre implémentation [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] peut avoir un ou plusieurs modèles regroupant chacun des types de données similaires.</span><span class="sxs-lookup"><span data-stu-id="7a367-111">Your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] implementation can have one or many models that each group similar kinds of data.</span></span> <span data-ttu-id="7a367-112">En général, les données de référence peuvent figurer dans l'une des quatre catégories suivantes : personnes, lieux, choses ou concepts.</span><span class="sxs-lookup"><span data-stu-id="7a367-112">In general, master data can be categorized in one of four ways: people, places, things, or concepts.</span></span> <span data-ttu-id="7a367-113">Par exemple, vous pouvez créer un modèle Product pour contenir des données relatives à un produit ou un modèle Customer pour contenir des données relatives à un client.</span><span class="sxs-lookup"><span data-stu-id="7a367-113">For example, you can create a Product model to contain product-related data or a Customer model to contain customer-related data.</span></span>  
  
 <span data-ttu-id="7a367-114">Vous pouvez affecter aux utilisateurs et groupes l'autorisation d'afficher et de mettre à jour des objets dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="7a367-114">You can assign users and groups permission to view and update objects within the model.</span></span> <span data-ttu-id="7a367-115">Si vous ne donnez pas d'autorisation sur le modèle, il n'est pas affiché.</span><span class="sxs-lookup"><span data-stu-id="7a367-115">If you do not give permission to the model, it is not displayed.</span></span>  
  
 <span data-ttu-id="7a367-116">À tout moment, vous pouvez créer des copies des données de référence dans un modèle.</span><span class="sxs-lookup"><span data-stu-id="7a367-116">At any given time, you can create copies of the master data within a model.</span></span> <span data-ttu-id="7a367-117">Ces copies sont appelées versions.</span><span class="sxs-lookup"><span data-stu-id="7a367-117">These copies are called versions.</span></span>  
  
 <span data-ttu-id="7a367-118">Lorsque vous avez défini un modèle dans un environnement de test, vous pouvez le déployer, avec ou sans les données correspondantes, de l'environnement de test vers un environnement de production.</span><span class="sxs-lookup"><span data-stu-id="7a367-118">When you have defined a model in a test environment, you can deploy it, with or without the corresponding data, from the test environment to a production environment.</span></span> <span data-ttu-id="7a367-119">Vous n'avez ainsi plus besoin de recréer vos modèles dans votre environnement de production.</span><span class="sxs-lookup"><span data-stu-id="7a367-119">This eliminates the need to recreate your models in your production environment.</span></span>  
  
## <a name="how-models-relate-to-other-objects"></a><span data-ttu-id="7a367-120">Relations entre les modèles et les autres objets</span><span class="sxs-lookup"><span data-stu-id="7a367-120">How Models Relate to Other Objects</span></span>  
 <span data-ttu-id="7a367-121">Un modèle contient des entités.</span><span class="sxs-lookup"><span data-stu-id="7a367-121">A model contains entities.</span></span> <span data-ttu-id="7a367-122">Les entités contiennent des attributs, des hiérarchies explicites et des collections.</span><span class="sxs-lookup"><span data-stu-id="7a367-122">Entities contain attributes, explicit hierarchies, and collections.</span></span> <span data-ttu-id="7a367-123">Les attributs peuvent être contenus dans des groupes d'attributs.</span><span class="sxs-lookup"><span data-stu-id="7a367-123">Attributes can be contained in attribute groups.</span></span> <span data-ttu-id="7a367-124">Les attributs basés sur un domaine existent lorsqu'une entité sert d'attribut à une autre entité.</span><span class="sxs-lookup"><span data-stu-id="7a367-124">Domain-based attributes exist when an entity is used as an attribute for another entity.</span></span>  
  
 <span data-ttu-id="7a367-125">Cette image montre les relations entre les objets dans un modèle.</span><span class="sxs-lookup"><span data-stu-id="7a367-125">This image shows the relationships among the objects in a model.</span></span>  
  
 <span data-ttu-id="7a367-126">![Objets dans un modèle Master Data Services](../../2014/master-data-services/media/mds-conc-model-circles.gif "Objets dans un modèle Master Data Services")</span><span class="sxs-lookup"><span data-stu-id="7a367-126">![Objects in a Master Data Services Model](../../2014/master-data-services/media/mds-conc-model-circles.gif "Objects in a Master Data Services Model")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7a367-127">Les hiérarchies dérivées sont également des objets de modèle, mais ils ne figurent pas dans l'image.</span><span class="sxs-lookup"><span data-stu-id="7a367-127">Derived hierarchies are also model objects, but they are not shown in the image.</span></span> <span data-ttu-id="7a367-128">Les hiérarchies dérivées sont dérivées des relations d'attributs basés sur un domaine qui existent entre les entités.</span><span class="sxs-lookup"><span data-stu-id="7a367-128">Derived hierarchies are derived from the domain-based attribute relationships that exist between entities.</span></span> <span data-ttu-id="7a367-129">Consultez [Hiérarchies dérivées &#40;Master Data Services&#41;](derived-hierarchies-master-data-services.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="7a367-129">See [Derived Hierarchies &#40;Master Data Services&#41;](derived-hierarchies-master-data-services.md) for more information.</span></span>  
  
 <span data-ttu-id="7a367-130">Les données de référence sont les données contenues dans les objets de modèle.</span><span class="sxs-lookup"><span data-stu-id="7a367-130">Master data is the data that is contained in the model objects.</span></span> <span data-ttu-id="7a367-131">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], les données de référence sont stockées en tant que membres dans une entité.</span><span class="sxs-lookup"><span data-stu-id="7a367-131">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], master data is stored as members in an entity.</span></span>  
  
 <span data-ttu-id="7a367-132">Les objets de modèle sont conservés dans la zone fonctionnelle **Administration de système** de l'interface utilisateur de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a367-132">Model objects are maintained in the **System Administration** functional area of the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] user interface.</span></span>  
  
## <a name="model-example"></a><span data-ttu-id="7a367-133">Exemple de modèle</span><span class="sxs-lookup"><span data-stu-id="7a367-133">Model Example</span></span>  
 <span data-ttu-id="7a367-134">Dans l'exemple suivant, les objets dans le modèle Product regroupent logiquement les données relatives au produit.</span><span class="sxs-lookup"><span data-stu-id="7a367-134">In the following example, the objects in the Product model logically group product-related data.</span></span>  
  
 <span data-ttu-id="7a367-135">![Exemple de modèle de produit Master Data](../../2014/master-data-services/media/mds-conc-model.gif "Exemple de modèle de produit Master Data")</span><span class="sxs-lookup"><span data-stu-id="7a367-135">![Product Model Master Data Example](../../2014/master-data-services/media/mds-conc-model.gif "Product Model Master Data Example")</span></span>  
  
 <span data-ttu-id="7a367-136">D'autres modèles courants figurent ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="7a367-136">Other common models are:</span></span>  
  
-   <span data-ttu-id="7a367-137">Accounts, qui peut inclure des entités, telles que les comptes de bilans, les comptes de résultats, les statistiques et le type de compte.</span><span class="sxs-lookup"><span data-stu-id="7a367-137">Accounts, which could include entities such as balance sheet accounts, income statement accounts, statistics, and account type.</span></span>  
  
-   <span data-ttu-id="7a367-138">Customer, qui peut inclure des entités, telles que le sexe, l'éducation, la profession et l'état civil.</span><span class="sxs-lookup"><span data-stu-id="7a367-138">Customer, which could include entities such as gender, education, occupation, and marital status.</span></span>  
  
-   <span data-ttu-id="7a367-139">Geography, qui peut inclure des entités, telles que les codes postaux, villes, comtés, états, provinces, régions, territoires, pays et continents.</span><span class="sxs-lookup"><span data-stu-id="7a367-139">Geography, which could include entities such as postal codes, cities, counties, states, provinces, regions, territories, countries, and continents.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="7a367-140">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="7a367-140">Related Tasks</span></span>  
  
|<span data-ttu-id="7a367-141">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="7a367-141">Task Description</span></span>|<span data-ttu-id="7a367-142">Rubrique</span><span class="sxs-lookup"><span data-stu-id="7a367-142">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="7a367-143">Créer un modèle pour organiser vos données de référence.</span><span class="sxs-lookup"><span data-stu-id="7a367-143">Create a model to organize your master data.</span></span>|[<span data-ttu-id="7a367-144">Créer un modèle &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7a367-144">Create a Model &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-model-master-data-services.md)|  
|<span data-ttu-id="7a367-145">Modifier le nom d'un modèle existant.</span><span class="sxs-lookup"><span data-stu-id="7a367-145">Change the name of an existing model.</span></span>|[<span data-ttu-id="7a367-146">Modifier un nom de modèle &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7a367-146">Change a Model Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-a-model-name-master-data-services.md)|  
|<span data-ttu-id="7a367-147">Supprimer un modèle existant.</span><span class="sxs-lookup"><span data-stu-id="7a367-147">Delete an existing model.</span></span>|[<span data-ttu-id="7a367-148">Supprimer un modèle &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7a367-148">Delete a Model &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-model-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="7a367-149">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="7a367-149">Related Content</span></span>  
  
-   [<span data-ttu-id="7a367-150">Vue d'ensemble de Master Data Services</span><span class="sxs-lookup"><span data-stu-id="7a367-150">Master Data Services Overview</span></span>](master-data-services-overview-mds.md)  
  
-   [<span data-ttu-id="7a367-151">Entités &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7a367-151">Entities &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/entities-master-data-services.md)  
  
-   [<span data-ttu-id="7a367-152">Attributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7a367-152">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
-   [<span data-ttu-id="7a367-153">Déploiement de modèles &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7a367-153">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
-   [<span data-ttu-id="7a367-154">Autorisations d’objet de modèle &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7a367-154">Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/model-object-permissions-master-data-services.md)  
  
  
