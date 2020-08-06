---
title: Métadonnées (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- user-defined metadata [Master Data Services], about user-defined metadata
- metadata [Master Data Services], about metadata
- metadata [Master Data Services]
- user-defined metadata [Master Data Services]
ms.assetid: ac1aabe3-d8d4-4d7a-8954-50ee3c185d81
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 39ab95b7925306febb551962495da7ec9751589b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698405"
---
# <a name="metadata-master-data-services"></a><span data-ttu-id="44cfd-102">Métadonnées (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="44cfd-102">Metadata (Master Data Services)</span></span>
  <span data-ttu-id="44cfd-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], les métadonnées définies par l'utilisateur sont des informations qui vous permettent de décrire les objets de modèle.</span><span class="sxs-lookup"><span data-stu-id="44cfd-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], user-defined metadata is information that you use to describe model objects.</span></span> <span data-ttu-id="44cfd-104">Par exemple, vous pouvez effectuer le suivi des propriétaires d'un modèle ou d'une entité spécifique, ou des systèmes sources qui fournissent des données à une entité.</span><span class="sxs-lookup"><span data-stu-id="44cfd-104">For example, you may want to track the owners of a particular model or entity, or track the source systems that supply data to an entity.</span></span>  
  
 <span data-ttu-id="44cfd-105">Les métadonnées définies par l’utilisateur sont gérées par un modèle appelé **métadonnées**.</span><span class="sxs-lookup"><span data-stu-id="44cfd-105">User-defined metadata is managed by a model called **Metadata**.</span></span> <span data-ttu-id="44cfd-106">Ce modèle est inclus automatiquement lorsque [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] est installé, et il est similaire à tous les autres modèles MDS, sauf que vous ne pouvez pas en créer.</span><span class="sxs-lookup"><span data-stu-id="44cfd-106">This model is automatically included when [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] is installed, and it is similar to all other MDS models, except that you cannot create versions of it.</span></span>  
  
 <span data-ttu-id="44cfd-107">Après avoir rempli le modèle Métadonnées avec les métadonnées définies par l'utilisateur, vous pouvez l'inclure dans des vues d'abonnement, de façon à ce qu'il puisse être consommé par les systèmes d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="44cfd-107">After you populate the Metadata model with user-defined metadata, you can include it in subscription views, so it can be consumed by subscribing systems.</span></span>  
  
## <a name="metadata-entities"></a><span data-ttu-id="44cfd-108">Entités de métadonnées</span><span class="sxs-lookup"><span data-stu-id="44cfd-108">Metadata Entities</span></span>  
 <span data-ttu-id="44cfd-109">Le modèle Métadonnées inclut cinq entités, chacune représentant un type d'objet modèle de données de référence qui prend en charge les métadonnées définies par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="44cfd-109">The Metadata model includes five entities, each of which represents a type of master data model object that supports user-defined metadata.</span></span> <span data-ttu-id="44cfd-110">Par exemple, l’entité de **définition des métadonnées du modèle** contient des membres qui représentent des modèles, et l’entité de **définition des métadonnées d’attribut** a des membres qui représentent tous les attributs de tous les modèles.</span><span class="sxs-lookup"><span data-stu-id="44cfd-110">For example, the **Model Metadata Definition** entity contains members that represent models, and the **Attribute Metadata Definition** entity has members that represent all attributes in all models.</span></span>  
  
 <span data-ttu-id="44cfd-111">Pour définir les métadonnées d'un objet de modèle, vous devez remplir un de ces attributs de membre.</span><span class="sxs-lookup"><span data-stu-id="44cfd-111">To define metadata for a model object, you populate one of these member's attributes.</span></span> <span data-ttu-id="44cfd-112">Par exemple, dans l’entité de **définition des métadonnées d’entité** , vous pouvez remplir l’attribut Description du membre Price avec le texte suivant : **prix du produit lorsqu’il est vendu à un client**.</span><span class="sxs-lookup"><span data-stu-id="44cfd-112">For example, in the **Entity Metadata Definition** entity, you can populate the Price member's Description attribute with the text: **The product price when sold to a customer**.</span></span>  
  
 <span data-ttu-id="44cfd-113">Les membres du modèle Métadonnées sont mis à jour automatiquement à chaque ajout ou suppression d'objets de modèle qui prennent en charge des métadonnées définies par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="44cfd-113">The members in the Metadata model are automatically updated whenever model objects that support user-defined metadata are added or deleted.</span></span>  
  
 <span data-ttu-id="44cfd-114">Le modèle Métadonnées ne peut pas être pourvu de version ; il n'est pas possible de lui ajouter des indicateurs de version ni de les modifier ; il ne peut pas être enregistré en tant que package de déploiement de modèle.</span><span class="sxs-lookup"><span data-stu-id="44cfd-114">The Metadata model cannot be versioned, have version flags added or changed, or be saved as a model deployment package.</span></span> <span data-ttu-id="44cfd-115">Toutefois, il possède à l'identique toutes les autres fonctionnalités disponibles pour les autres modèles de données de référence.</span><span class="sxs-lookup"><span data-stu-id="44cfd-115">However, it has all the same other functionality available to other master data models.</span></span> <span data-ttu-id="44cfd-116">Par exemple, vous pouvez implémenter un jeu de règles d'entreprise sur le modèle Métadonnées pour appliquer des stratégies de données.</span><span class="sxs-lookup"><span data-stu-id="44cfd-116">For example, you might implement a set of business rules on the Metadata model to enforce data policies.</span></span>  
  
## <a name="customizing-your-metadata-model"></a><span data-ttu-id="44cfd-117">Personnalisation de votre modèle de métadonnées</span><span class="sxs-lookup"><span data-stu-id="44cfd-117">Customizing Your Metadata Model</span></span>  
 <span data-ttu-id="44cfd-118">Chaque entité de définition de métadonnées inclut les attributs Name, Code et Description.</span><span class="sxs-lookup"><span data-stu-id="44cfd-118">Each metadata definition entity includes Name, Code, and Description attributes.</span></span> <span data-ttu-id="44cfd-119">Vous pouvez créer des attributs supplémentaires pour décrire plus précisément vos objets de modèle.</span><span class="sxs-lookup"><span data-stu-id="44cfd-119">You may want to create additional attributes to further describe your model objects.</span></span>  
  
 <span data-ttu-id="44cfd-120">Par exemple, vous pouvez créer les attributs suivants :</span><span class="sxs-lookup"><span data-stu-id="44cfd-120">For example, you might create:</span></span>  
  
-   <span data-ttu-id="44cfd-121">Un attribut basé sur un domaine nommé Owner, que vous utilisez pour effectuer le suivi du propriétaire de chaque objet de modèle.</span><span class="sxs-lookup"><span data-stu-id="44cfd-121">A domain-based attribute named Owner, which you use to track the owner of each model object.</span></span>  
  
-   <span data-ttu-id="44cfd-122">Un attribut de forme libre nommé Last Review Date, qui vous permet d'effectuer le suivi de la date à laquelle un objet a été révisé par le propriétaire pour la dernière fois.</span><span class="sxs-lookup"><span data-stu-id="44cfd-122">A free-form attribute named Last Review Date, which you use to track the date that an object was last reviewed by the owner.</span></span>  
  
-   <span data-ttu-id="44cfd-123">Un attribut basé sur un domaine nommé sources, que vous utilisez pour suivre et gérer les systèmes sources qui interagissent avec l' [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] instance.</span><span class="sxs-lookup"><span data-stu-id="44cfd-123">A domain-based attribute named Sources, which you use to track and manage the source systems that interact with the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] instance.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="44cfd-124">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="44cfd-124">Related Tasks</span></span>  
  
|<span data-ttu-id="44cfd-125">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="44cfd-125">Task Description</span></span>|<span data-ttu-id="44cfd-126">Rubrique</span><span class="sxs-lookup"><span data-stu-id="44cfd-126">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="44cfd-127">Ajoutez des métadonnées à un objet de modèle.</span><span class="sxs-lookup"><span data-stu-id="44cfd-127">Add metadata to a model object.</span></span>|[<span data-ttu-id="44cfd-128">Ajouter des métadonnées &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="44cfd-128">Add Metadata &#40;Master Data Services&#41;</span></span>](add-metadata-master-data-services.md)
|&nbsp;|&nbsp;|
  
## <a name="related-content"></a><span data-ttu-id="44cfd-129">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="44cfd-129">Related Content</span></span>  
  
-   [<span data-ttu-id="44cfd-130">Exportation de données &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="44cfd-130">Exporting Data &#40;Master Data Services&#41;</span></span>](overview-exporting-data-master-data-services.md)  
  
  
