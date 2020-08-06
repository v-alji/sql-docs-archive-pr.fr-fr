---
title: Autorisations d’objet de modèle (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- permissions [Master Data Services], model objects
- models [Master Data Services], object permissions
ms.assetid: fab6335b-4cae-47de-ae7c-6c4743e0680f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4cc64d753b680cfabc3707a29c6d9de631708c20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613498"
---
# <a name="model-object-permissions-master-data-services"></a><span data-ttu-id="d091b-102">Autorisations d'objet de modèle (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d091b-102">Model Object Permissions (Master Data Services)</span></span>
  <span data-ttu-id="d091b-103">Les autorisations d'objet modèle sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="d091b-103">Model object permissions are mandatory.</span></span> <span data-ttu-id="d091b-104">Elles déterminent les attributs auxquels un utilisateur peut accéder dans la zone fonctionnelle **Explorateur** de l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d091b-104">They determine the attributes a user can access in the **Explorer** functional area of the UI.</span></span>  
  
 <span data-ttu-id="d091b-105">Par exemple, si vous affectez une autorisation **Mettre à jour** sur l'entité Product, l'utilisateur peut mettre à jour tous les attributs de l'entité Product.</span><span class="sxs-lookup"><span data-stu-id="d091b-105">For example, if you assign a user **Update** permission to the Product entity, the user can update all of the attributes of the Product entity.</span></span> <span data-ttu-id="d091b-106">Si vous affectez une autorisation **Mettre à jour** à un seul attribut, l'utilisateur peut mettre à jour cet attribut uniquement.</span><span class="sxs-lookup"><span data-stu-id="d091b-106">If you assign **Update** permission to a single attribute, the user can update that attribute only.</span></span>  
  
 <span data-ttu-id="d091b-107">Pour déterminer la sécurité affectée sur chaque valeur d'attribut individuelle, les autorisations d'objet modèle sont associées aux autorisations des membres de la hiérarchie, qui déterminent les membres auxquels un utilisateur peut accéder.</span><span class="sxs-lookup"><span data-stu-id="d091b-107">To determine security assigned on each individual attribute value, model object permissions are combined with hierarchy member permissions, which determine the members a user can access.</span></span>  
  
 <span data-ttu-id="d091b-108">Pour accorder à un utilisateur l’accès à une zone fonctionnelle autre que l' **Explorateur**, l’utilisateur doit être un administrateur de modèle, ce qui implique également l’attribution d’autorisations d’objet de modèle.</span><span class="sxs-lookup"><span data-stu-id="d091b-108">To give a user access to a functional area other than **Explorer**, the user must be a model administrator, which also involves assigning model object permissions.</span></span> <span data-ttu-id="d091b-109">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d091b-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
 <span data-ttu-id="d091b-110">Les autorisations d’objet de modèle sont affectées dans l' [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] interface utilisateur, dans la zone fonctionnelle **autorisations d’accès** sous l’onglet **modèles** . Sous cet onglet, le modèle est représenté sous la forme d’une arborescence.</span><span class="sxs-lookup"><span data-stu-id="d091b-110">Model object permissions are assigned in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] user interface (UI), in the **User and Group Permissions** functional area on the **Models** tab. On this tab, the model is represented as a tree structure.</span></span> <span data-ttu-id="d091b-111">Lorsque vous affectez une autorisation à un objet dans l'arborescence, tous les objets suivants héritent de cette autorisation.</span><span class="sxs-lookup"><span data-stu-id="d091b-111">When you assign permission to an object in the tree, all objects below inherit that permission.</span></span> <span data-ttu-id="d091b-112">Vous pouvez remplacer cet héritage en affectant l'autorisation à des objets individuels.</span><span class="sxs-lookup"><span data-stu-id="d091b-112">You can override that inheritance by assigning permission to individual objects.</span></span>  
  
 <span data-ttu-id="d091b-113">Vous pouvez assigner des autorisations de **lecture**seule, de **mise à jour**ou de **refus** à des objets de modèle.</span><span class="sxs-lookup"><span data-stu-id="d091b-113">You can assign **Read-only**, **Update**, or **Deny** permission to model objects.</span></span> <span data-ttu-id="d091b-114">Si vous n'affectez aucune autorisation sous l'onglet **Modèles** , l'utilisateur ne peut pas afficher les modèles ou données dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d091b-114">If you do not assign any permissions on the **Models** tab, the user cannot view any models or data in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
## <a name="best-practice"></a><span data-ttu-id="d091b-115">Bonne pratique</span><span class="sxs-lookup"><span data-stu-id="d091b-115">Best Practice</span></span>  
 <span data-ttu-id="d091b-116">En général, vous devez attribuer l’autorisation **mettre à jour** à l’objet de modèle, puis attribuer explicitement l’autorisation aux objets situés sous.</span><span class="sxs-lookup"><span data-stu-id="d091b-116">In general, you should assign **Update** permission to the model object, and then explicitly assign permission to objects underneath.</span></span> <span data-ttu-id="d091b-117">Si vous n'affectez pas d'autorisation aux objets en dessous, les autorisations sont héritées et l'utilisateur est un administrateur.</span><span class="sxs-lookup"><span data-stu-id="d091b-117">If you do not assign permission to objects underneath, the permissions are inherited and the user is an administrator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d091b-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d091b-118">See Also</span></span>  
 <span data-ttu-id="d091b-119">[Affecter des autorisations d’objet de modèle &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d091b-119">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="d091b-120">[Autorisations de modèle &#40;Master Data Services&#41;](../../2014/master-data-services/model-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d091b-120">[Model Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="d091b-121">[Autorisations de zone fonctionnelle &#40;Master Data Services&#41;](../../2014/master-data-services/functional-area-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d091b-121">[Functional Area Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/functional-area-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="d091b-122">[Autorisations des membres de la hiérarchie &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d091b-122">[Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="d091b-123">Mode de détermination des autorisations &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d091b-123">How Permissions Are Determined &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/how-permissions-are-determined-master-data-services.md)  
  
  
