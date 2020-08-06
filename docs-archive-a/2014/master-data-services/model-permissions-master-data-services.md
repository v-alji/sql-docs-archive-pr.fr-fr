---
title: Autorisations de modèle (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], permissions
- permissions [Master Data Services], models
ms.assetid: 210f440b-2cc1-4c49-94b1-3a97e2af7bc3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 2846918b515bba16d12d48cd7058cf25863bf569
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605528"
---
# <a name="model-permissions-master-data-services"></a><span data-ttu-id="a56f0-102">Autorisations de modèle (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="a56f0-102">Model Permissions (Master Data Services)</span></span>
  <span data-ttu-id="a56f0-103">Les autorisations de modèle s'appliquent à l'ensemble des entités, attributs, groupes d'attributs, hiérarchies dérivées, hiérarchies explicites et collections qui existent dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="a56f0-103">Model permissions apply to all entities, derived hierarchies, explicit hierarchies, and collections that exist within the model.</span></span> <span data-ttu-id="a56f0-104">Les autorisations affectées au modèle peuvent être remplacées pour tout objet individuel.</span><span class="sxs-lookup"><span data-stu-id="a56f0-104">Permissions assigned to the model can be overridden for any individual object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a56f0-105">Si l'utilisateur est administrateur de modèle, le modèle est affiché dans toutes les zones fonctionnelles de l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a56f0-105">If a user is a model administrator, the model is displayed in all functional areas of the user interface.</span></span> <span data-ttu-id="a56f0-106">Sinon, le modèle est affiché uniquement dans la zone fonctionnelle **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="a56f0-106">Otherwise, the model is displayed in the **Explorer** functional area only.</span></span> <span data-ttu-id="a56f0-107">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a56f0-107">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
|<span data-ttu-id="a56f0-108">Autorisation</span><span class="sxs-lookup"><span data-stu-id="a56f0-108">Permission</span></span>|<span data-ttu-id="a56f0-109">Description</span><span class="sxs-lookup"><span data-stu-id="a56f0-109">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="a56f0-110">**Lecture seule**</span><span class="sxs-lookup"><span data-stu-id="a56f0-110">**Read-only**</span></span>|<span data-ttu-id="a56f0-111">Dans l' **Explorateur**, le modèle est affiché, mais l’utilisateur ne peut pas ajouter ou supprimer des membres et ne peut pas mettre à jour les valeurs d’attribut, les appartenances de hiérarchie ou les appartenances de collection.</span><span class="sxs-lookup"><span data-stu-id="a56f0-111">In **Explorer**, the model is displayed but the user cannot add or remove members, and cannot update attribute values, hierarchy memberships, or collection memberships.</span></span>|  
|<span data-ttu-id="a56f0-112">**Mettre à jour**</span><span class="sxs-lookup"><span data-stu-id="a56f0-112">**Update**</span></span>|<span data-ttu-id="a56f0-113">Dans l' **Explorateur**, le modèle est affiché et l’utilisateur peut ajouter et supprimer des membres, peut mettre à jour les valeurs d’attribut, les appartenances de hiérarchie et les appartenances de collection.</span><span class="sxs-lookup"><span data-stu-id="a56f0-113">In **Explorer**, the model is displayed and the user can add and remove members, can update attribute values, hierarchy memberships, and collection memberships.</span></span>|  
|<span data-ttu-id="a56f0-114">**Deny**</span><span class="sxs-lookup"><span data-stu-id="a56f0-114">**Deny**</span></span>|<span data-ttu-id="a56f0-115">Le modèle n’est pas affiché.</span><span class="sxs-lookup"><span data-stu-id="a56f0-115">The model is not displayed.</span></span>|  
  
 <span data-ttu-id="a56f0-116">Lorsque vous affectez l'autorisation à un modèle, l'utilisateur obtient l'accès à toutes les versions du modèle.</span><span class="sxs-lookup"><span data-stu-id="a56f0-116">When you assign permission to a model, the user gets access to all versions of the model.</span></span> <span data-ttu-id="a56f0-117">Vous ne pouvez pas affecter d'autorisation à une version individuelle.</span><span class="sxs-lookup"><span data-stu-id="a56f0-117">You cannot assign permission to an individual version.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a56f0-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a56f0-118">See Also</span></span>  
 <span data-ttu-id="a56f0-119">[Affecter des autorisations d’objet de modèle &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a56f0-119">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="a56f0-120">[Autorisations d’objet de modèle &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a56f0-120">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="a56f0-121">[Autorisations d’entité &#40;Master Data Services&#41;](../../2014/master-data-services/entity-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a56f0-121">[Entity Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/entity-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="a56f0-122">Autorisations de collection &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a56f0-122">Collection Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collection-permissions-master-data-services.md)  
  
  
