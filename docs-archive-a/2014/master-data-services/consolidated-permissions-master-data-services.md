---
title: Autorisations consolidées (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], consolidated member attribute permissions
- consolidated members [Master Data Services], attribute permissions
- permissions [Master Data Services], consolidated members
- members [Master Data Services], consolidated member permissions
ms.assetid: 084055a3-5fd3-43f3-b620-ac6afab42a3d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c4c93e74acc84d6e742139263bedc011c4028efb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615193"
---
# <a name="consolidated-permissions-master-data-services"></a><span data-ttu-id="ef6fb-102">Autorisations consolidées (services de données de référence)</span><span class="sxs-lookup"><span data-stu-id="ef6fb-102">Consolidated Permissions (Master Data Services)</span></span>
  <span data-ttu-id="ef6fb-103">Les autorisations consolidées s'appliquent aux valeurs d'attribut pour tous les membres consolidés d'une entité.</span><span class="sxs-lookup"><span data-stu-id="ef6fb-103">Consolidated permissions apply to the attribute values for all consolidated members of an entity.</span></span>  
  
 <span data-ttu-id="ef6fb-104">Les autorisations consolidées s'appliquent uniquement aux entités activées pour les hiérarchies explicites et les collections.</span><span class="sxs-lookup"><span data-stu-id="ef6fb-104">Consolidated permissions apply only to entities that are enabled for explicit hierarchies and collections.</span></span>  
  
 <span data-ttu-id="ef6fb-105">**Remarques :**</span><span class="sxs-lookup"><span data-stu-id="ef6fb-105">**Notes:**</span></span>  
  
-   <span data-ttu-id="ef6fb-106">Les autorisations de feuille s'appliquent à la zone fonctionnelle **Explorateur** de l'interface utilisateur uniquement.</span><span class="sxs-lookup"><span data-stu-id="ef6fb-106">Leaf permissions apply to the **Explorer** functional area of the user interface only.</span></span>  
  
-   <span data-ttu-id="ef6fb-107">Les autorisations attribuées à **Nom** et **Code** ne sont pas appliquées.</span><span class="sxs-lookup"><span data-stu-id="ef6fb-107">Permissions assigned to **Name** and **Code** attributes are not enforced.</span></span>  
  
|<span data-ttu-id="ef6fb-108">Autorisation</span><span class="sxs-lookup"><span data-stu-id="ef6fb-108">Permission</span></span>|<span data-ttu-id="ef6fb-109">Description</span><span class="sxs-lookup"><span data-stu-id="ef6fb-109">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="ef6fb-110">**Lecture seule**</span><span class="sxs-lookup"><span data-stu-id="ef6fb-110">**Read-only**</span></span>|<span data-ttu-id="ef6fb-111">Les membres consolidés sont affichés, mais l'utilisateur ne peut pas les ajouter, les supprimer ni les modifier.</span><span class="sxs-lookup"><span data-stu-id="ef6fb-111">Consolidated members are displayed but the user cannot add, remove, or change them.</span></span>|  
|<span data-ttu-id="ef6fb-112">**Mettre à jour**</span><span class="sxs-lookup"><span data-stu-id="ef6fb-112">**Update**</span></span>|<span data-ttu-id="ef6fb-113">Les membres consolidés sont affichés et l'utilisateur peut les ajouter, les supprimer et les modifier.</span><span class="sxs-lookup"><span data-stu-id="ef6fb-113">Consolidated members are displayed and the user can add, remove, and change them.</span></span>|  
|<span data-ttu-id="ef6fb-114">**Deny**</span><span class="sxs-lookup"><span data-stu-id="ef6fb-114">**Deny**</span></span>|<span data-ttu-id="ef6fb-115">Les membres consolidés pour l'entité ne sont pas affichés.</span><span class="sxs-lookup"><span data-stu-id="ef6fb-115">Consolidated members for the entity are not displayed.</span></span>|  
  
## <a name="attribute-permissions"></a><span data-ttu-id="ef6fb-116">Autorisations d'attribut</span><span class="sxs-lookup"><span data-stu-id="ef6fb-116">Attribute Permissions</span></span>  
 <span data-ttu-id="ef6fb-117">Les autorisations d’attribut s’appliquent aux valeurs de l’attribut pour l’entité spécifique.</span><span class="sxs-lookup"><span data-stu-id="ef6fb-117">Attribute permissions apply to the attribute's values for the specific entity.</span></span> <span data-ttu-id="ef6fb-118">Les utilisateurs avec uniquement des autorisations d'attribut ne peuvent pas ajouter ni supprimer des membres.</span><span class="sxs-lookup"><span data-stu-id="ef6fb-118">Users with only attribute permissions cannot add or remove members.</span></span>  
  
|<span data-ttu-id="ef6fb-119">Autorisation</span><span class="sxs-lookup"><span data-stu-id="ef6fb-119">Permission</span></span>|<span data-ttu-id="ef6fb-120">Description</span><span class="sxs-lookup"><span data-stu-id="ef6fb-120">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="ef6fb-121">**Lecture seule**</span><span class="sxs-lookup"><span data-stu-id="ef6fb-121">**Read-only**</span></span>|<span data-ttu-id="ef6fb-122">L'attribut est affiché, mais l'utilisateur ne peut pas modifier les valeurs d'attribut.</span><span class="sxs-lookup"><span data-stu-id="ef6fb-122">The attribute is displayed but the user cannot change attribute values.</span></span>|  
|<span data-ttu-id="ef6fb-123">**Mettre à jour**</span><span class="sxs-lookup"><span data-stu-id="ef6fb-123">**Update**</span></span>|<span data-ttu-id="ef6fb-124">L'attribut est affiché et l'utilisateur peut modifier les valeurs d'attribut.</span><span class="sxs-lookup"><span data-stu-id="ef6fb-124">The attribute is displayed and the user can change attribute values.</span></span>|  
|<span data-ttu-id="ef6fb-125">**Deny**</span><span class="sxs-lookup"><span data-stu-id="ef6fb-125">**Deny**</span></span>|<span data-ttu-id="ef6fb-126">L'attribut n'est pas affiché.</span><span class="sxs-lookup"><span data-stu-id="ef6fb-126">The attribute is not displayed.</span></span><br /><br /> <span data-ttu-id="ef6fb-127">Remarque : vous ne pouvez pas refuser explicitement l’accès aux attributs Name et Code.</span><span class="sxs-lookup"><span data-stu-id="ef6fb-127">Note: You cannot explicitly deny access to Name and Code attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef6fb-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ef6fb-128">See Also</span></span>  
 <span data-ttu-id="ef6fb-129">[Affecter des autorisations d’objet de modèle &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ef6fb-129">[Assign Model Object Permissions &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="ef6fb-130">[Autorisations feuille &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ef6fb-130">[Leaf Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="ef6fb-131">[Autorisations d’objet de modèle &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ef6fb-131">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="ef6fb-132">[Membres &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ef6fb-132">[Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span></span>  
 [<span data-ttu-id="ef6fb-133">Attributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ef6fb-133">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  
