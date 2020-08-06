---
title: Autorisations de feuille (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attribute groups [Master Data Services], permissions
- members [Master Data Services], leaf member permissions
- permissions [Master Data Services], leaf members
- leaf members [Master Data Services], attribute permissions
- attributes [Master Data Services], leaf member attribute permissions
ms.assetid: bde16e8c-bcd4-4041-8130-55c5450e5f72
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 794e1d138b91e896b8df16765ae8984c6e60aca7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706551"
---
# <a name="leaf-permissions-master-data-services"></a><span data-ttu-id="51138-102">Autorisations de feuille (services de données de référence)</span><span class="sxs-lookup"><span data-stu-id="51138-102">Leaf Permissions (Master Data Services)</span></span>
  <span data-ttu-id="51138-103">Les autorisations de feuille s'appliquent aux valeurs d'attribut pour tous les membres feuille d'une entité.</span><span class="sxs-lookup"><span data-stu-id="51138-103">Leaf permissions apply to the attribute values for all leaf members of an entity.</span></span>  
  
 <span data-ttu-id="51138-104">Pour les entités sans hiérarchies explicites activées, l'affectation d'une autorisation **Feuille** revient à affecter l'autorisation à l'entité.</span><span class="sxs-lookup"><span data-stu-id="51138-104">For entities without explicit hierarchies enabled, assigning permission to **Leaf** is the same as assigning permission to the entity.</span></span>  
  
 <span data-ttu-id="51138-105">**Remarques :**</span><span class="sxs-lookup"><span data-stu-id="51138-105">**Notes:**</span></span>  
  
-   <span data-ttu-id="51138-106">Les autorisations de feuille s'appliquent à la zone fonctionnelle **Explorateur** de l'interface utilisateur uniquement.</span><span class="sxs-lookup"><span data-stu-id="51138-106">Leaf permissions apply to the **Explorer** functional area of the user interface only.</span></span>  
  
-   <span data-ttu-id="51138-107">Les autorisations attribuées à **Nom** et **Code** ne sont pas appliquées.</span><span class="sxs-lookup"><span data-stu-id="51138-107">Permissions assigned to **Name** and **Code** attributes are not enforced.</span></span>  
  
|<span data-ttu-id="51138-108">Autorisation</span><span class="sxs-lookup"><span data-stu-id="51138-108">Permission</span></span>|<span data-ttu-id="51138-109">Description</span><span class="sxs-lookup"><span data-stu-id="51138-109">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="51138-110">**Lecture seule**</span><span class="sxs-lookup"><span data-stu-id="51138-110">**Read-only**</span></span>|<span data-ttu-id="51138-111">Les membres feuille sont affichés, mais l'utilisateur ne peut ni les ajouter, ni les supprimer ni les modifier.</span><span class="sxs-lookup"><span data-stu-id="51138-111">Leaf members are displayed but the user cannot add, remove, or change them.</span></span><br /><br /> <span data-ttu-id="51138-112">Si des membres consolidés existent, les noms et codes sont affichés, mais l'utilisateur ne peut pas les ajouter, les supprimer ni les modifier.</span><span class="sxs-lookup"><span data-stu-id="51138-112">If consolidated members exist, the names and codes are displayed but the user cannot add, remove, or change them.</span></span>|  
|<span data-ttu-id="51138-113">**Mettre à jour**</span><span class="sxs-lookup"><span data-stu-id="51138-113">**Update**</span></span>|<span data-ttu-id="51138-114">Les membres feuille sont affichés et l'utilisateur peut les ajouter, les supprimer et les modifier.</span><span class="sxs-lookup"><span data-stu-id="51138-114">Leaf members are displayed and the user can add, remove, and change them.</span></span><br /><br /> <span data-ttu-id="51138-115">Si des membres consolidés existent, les noms et codes sont affichés, mais l'utilisateur ne peut pas les ajouter, les supprimer ni les modifier.</span><span class="sxs-lookup"><span data-stu-id="51138-115">If consolidated members exist, the names and codes are displayed but the user cannot add, remove, or change them.</span></span>|  
|<span data-ttu-id="51138-116">**Deny**</span><span class="sxs-lookup"><span data-stu-id="51138-116">**Deny**</span></span>|<span data-ttu-id="51138-117">Les membres feuille pour l'entité ne sont pas affichés.</span><span class="sxs-lookup"><span data-stu-id="51138-117">Leaf members for the entity are not displayed.</span></span>|  
  
## <a name="attribute-permissions"></a><span data-ttu-id="51138-118">Autorisations d'attribut</span><span class="sxs-lookup"><span data-stu-id="51138-118">Attribute Permissions</span></span>  
 <span data-ttu-id="51138-119">Les autorisations d’attribut s’appliquent aux valeurs de l’attribut pour l’entité spécifique.</span><span class="sxs-lookup"><span data-stu-id="51138-119">Attribute permissions apply to the attribute's values for the specific entity.</span></span> <span data-ttu-id="51138-120">Les utilisateurs avec des autorisations d'attribut uniquement ne peuvent pas ajouter ni supprimer des membres.</span><span class="sxs-lookup"><span data-stu-id="51138-120">Users with attribute permissions only cannot add or remove members.</span></span>  
  
|<span data-ttu-id="51138-121">Autorisation</span><span class="sxs-lookup"><span data-stu-id="51138-121">Permission</span></span>|<span data-ttu-id="51138-122">Description</span><span class="sxs-lookup"><span data-stu-id="51138-122">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="51138-123">**Lecture seule**</span><span class="sxs-lookup"><span data-stu-id="51138-123">**Read-only**</span></span>|<span data-ttu-id="51138-124">L'attribut est affiché, mais l'utilisateur ne peut pas modifier les valeurs d'attribut.</span><span class="sxs-lookup"><span data-stu-id="51138-124">The attribute is displayed but the user cannot change attribute values.</span></span>|  
|<span data-ttu-id="51138-125">**Mettre à jour**</span><span class="sxs-lookup"><span data-stu-id="51138-125">**Update**</span></span>|<span data-ttu-id="51138-126">L'attribut est affiché et l'utilisateur peut modifier les valeurs d'attribut.</span><span class="sxs-lookup"><span data-stu-id="51138-126">The attribute is displayed and the user can change attribute values.</span></span>|  
|<span data-ttu-id="51138-127">**Deny**</span><span class="sxs-lookup"><span data-stu-id="51138-127">**Deny**</span></span>|<span data-ttu-id="51138-128">L'attribut n'est pas affiché.</span><span class="sxs-lookup"><span data-stu-id="51138-128">The attribute is not displayed.</span></span><br /><br /> <span data-ttu-id="51138-129">Remarque : vous ne pouvez pas refuser explicitement l’accès aux attributs Name et Code.</span><span class="sxs-lookup"><span data-stu-id="51138-129">Note: You cannot explicitly deny access to Name and Code attributes.</span></span>|  
  
### <a name="example"></a><span data-ttu-id="51138-130">Exemple</span><span class="sxs-lookup"><span data-stu-id="51138-130">Example</span></span>  
 <span data-ttu-id="51138-131">Pour l'entité Product, affectez l'autorisation **Mise à jour** à l'attribut Subcategory.</span><span class="sxs-lookup"><span data-stu-id="51138-131">For the Product entity, assign **Update** permission to Subcategory attribute.</span></span> <span data-ttu-id="51138-132">Autorisation refuser à tous les autres attributs.</span><span class="sxs-lookup"><span data-stu-id="51138-132">Deny permission to all other attributes.</span></span>  
  
|<span data-ttu-id="51138-133">Nom</span><span class="sxs-lookup"><span data-stu-id="51138-133">Name</span></span>|<span data-ttu-id="51138-134">Code</span><span class="sxs-lookup"><span data-stu-id="51138-134">Code</span></span>|<span data-ttu-id="51138-135">Subcategory (Mise à jour)</span><span class="sxs-lookup"><span data-stu-id="51138-135">Subcategory (Update)</span></span>|  
|----------|----------|----------------------------|  
|<span data-ttu-id="51138-136">Mountain-100</span><span class="sxs-lookup"><span data-stu-id="51138-136">Mountain-100</span></span>|<span data-ttu-id="51138-137">BK-M101</span><span class="sxs-lookup"><span data-stu-id="51138-137">BK-M101</span></span>|<span data-ttu-id="51138-138">{5}VTT</span><span class="sxs-lookup"><span data-stu-id="51138-138">{5} Mountain Bikes</span></span>|  
|<span data-ttu-id="51138-139">Mountain-100</span><span class="sxs-lookup"><span data-stu-id="51138-139">Mountain-100</span></span>|<span data-ttu-id="51138-140">BK-M201</span><span class="sxs-lookup"><span data-stu-id="51138-140">BK-M201</span></span>|<span data-ttu-id="51138-141">{5}VTT</span><span class="sxs-lookup"><span data-stu-id="51138-141">{5} Mountain Bikes</span></span>|  
  
 <span data-ttu-id="51138-142">Dans l' **Explorateur**, vous pouvez mettre à jour toute valeur d'attribut de la colonne Subcategory.</span><span class="sxs-lookup"><span data-stu-id="51138-142">In **Explorer**, you can update any attribute value in the Subcategory column.</span></span> <span data-ttu-id="51138-143">Si vous n'avez pas d'autorisation sur un attribut, l'attribut n'est pas affiché.</span><span class="sxs-lookup"><span data-stu-id="51138-143">If you do not have permission to an attribute, the attribute is not displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="51138-144">Dans cet exemple, Subcategory est un attribut basé sur un domaine, basé sur l'entité SubcategoryList.</span><span class="sxs-lookup"><span data-stu-id="51138-144">In this example, Subcategory is a domain-based attribute, based on the SubcategoryList entity.</span></span> <span data-ttu-id="51138-145">Vous pouvez sélectionner une sous-catégorie différente pour Mountain-100, mais vous ne pouvez pas ajouter ni supprimer des membres dans l'entité SubcategoryList.</span><span class="sxs-lookup"><span data-stu-id="51138-145">You can select a different subcategory for Mountain-100 but you cannot add members to or delete members from the SubcategoryList entity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51138-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="51138-146">See Also</span></span>  
 <span data-ttu-id="51138-147">[Affecter des autorisations d’objet de modèle &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="51138-147">[Assign Model Object Permissions &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="51138-148">[Autorisations consolidées &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="51138-148">[Consolidated Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="51138-149">[Autorisations d’objet de modèle &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="51138-149">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="51138-150">[Membres &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="51138-150">[Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span></span>  
 [<span data-ttu-id="51138-151">Attributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="51138-151">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  
