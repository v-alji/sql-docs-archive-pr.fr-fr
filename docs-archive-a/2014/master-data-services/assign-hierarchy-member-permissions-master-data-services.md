---
title: Affecter des autorisations de membre de hiérarchie (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- permissions [Master Data Services], assigning member permissions
- members [Master Data Services], assigning permissions
ms.assetid: e1b8b46a-7cd1-4a7d-9345-dd7df081e145
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4a1602f9fe351f826b63d4447f90dcf02a10f49e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610734"
---
# <a name="assign-hierarchy-member-permissions-master-data-services"></a><span data-ttu-id="9d445-102">Affecter des autorisations de membre de hiérarchie (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9d445-102">Assign Hierarchy Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="9d445-103">Affectez des autorisations à des membres de la hiérarchie pour permettre à des utilisateurs ou des groupes d’afficher les données dans la zone fonctionnelle **Explorateur** de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9d445-103">Assign permissions to hierarchy members to give users or groups access to view data in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
 <span data-ttu-id="9d445-104">Les autorisations des membres de la hiérarchie sont facultatives.</span><span class="sxs-lookup"><span data-stu-id="9d445-104">Hierarchy member permissions are optional.</span></span> <span data-ttu-id="9d445-105">Elles améliorent la granularité des autorisations d'objet de modèle, qui sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="9d445-105">They provide added granularity to model object permissions, which are required.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9d445-106">Prérequis</span><span class="sxs-lookup"><span data-stu-id="9d445-106">Prerequisites</span></span>  
 <span data-ttu-id="9d445-107">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="9d445-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="9d445-108">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Autorisations d'accès** .</span><span class="sxs-lookup"><span data-stu-id="9d445-108">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="9d445-109">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="9d445-109">You must be a model administrator.</span></span> <span data-ttu-id="9d445-110">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9d445-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-assign-hierarchy-member-permissions"></a><span data-ttu-id="9d445-111">Pour affecter des autorisations de membre de hiérarchie</span><span class="sxs-lookup"><span data-stu-id="9d445-111">To assign hierarchy member permissions</span></span>  
  
1.  <span data-ttu-id="9d445-112">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Autorisations d'accès**.</span><span class="sxs-lookup"><span data-stu-id="9d445-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="9d445-113">Dans la page **Utilisateurs** ou **Groupes** , sélectionnez la ligne de l'utilisateur ou du groupe à modifier.</span><span class="sxs-lookup"><span data-stu-id="9d445-113">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="9d445-114">Cliquez sur **Modifier l'utilisateur sélectionné**.</span><span class="sxs-lookup"><span data-stu-id="9d445-114">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="9d445-115">Cliquez sur l'onglet **Membres de hiérarchie** .</span><span class="sxs-lookup"><span data-stu-id="9d445-115">Click the **Hierarchy Members** tab.</span></span>  
  
5.  <span data-ttu-id="9d445-116">Dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="9d445-116">From the **Model** list, select a model.</span></span>  
  
6.  <span data-ttu-id="9d445-117">Dans la liste **Version** , sélectionnez une version.</span><span class="sxs-lookup"><span data-stu-id="9d445-117">From the **Version** list, select a version.</span></span>  
  
7.  <span data-ttu-id="9d445-118">Dans la liste **Hiérarchie** , sélectionnez une hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="9d445-118">From the **Hierarchy** list, select a hierarchy.</span></span>  
  
8.  <span data-ttu-id="9d445-119">Cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="9d445-119">Click **Edit**.</span></span>  
  
9. <span data-ttu-id="9d445-120">Développez l'arborescence, puis cliquez sur le nœud de la hiérarchie auquel vous souhaitez affecter des autorisations.</span><span class="sxs-lookup"><span data-stu-id="9d445-120">Expand the tree, and click the hierarchy node you want to assign permissions to.</span></span>  
  
10. <span data-ttu-id="9d445-121">Dans le menu, sélectionnez **lecture seule**, **mettre à jour**ou **refuser**.</span><span class="sxs-lookup"><span data-stu-id="9d445-121">From the menu, select **Read-only**, **Update**, or **Deny**.</span></span>  
  
11. <span data-ttu-id="9d445-122">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9d445-122">Click **Save**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9d445-123">Les autorisations des membres de la hiérarchie n'entrent pas immédiatement en vigueur.</span><span class="sxs-lookup"><span data-stu-id="9d445-123">Hierarchy member permissions do not take effect immediately.</span></span> <span data-ttu-id="9d445-124">Pour plus d’informations, consultez [Appliquer immédiatement des autorisations de membre &#40;Master Data Services&#41;](../../2014/master-data-services/immediately-apply-member-permissions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9d445-124">See [Immediately Apply Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/immediately-apply-member-permissions-master-data-services.md) for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d445-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9d445-125">See Also</span></span>  
 <span data-ttu-id="9d445-126">[Supprimer les autorisations de membre de hiérarchie &#40;Master Data Services&#41;](../../2014/master-data-services/delete-hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9d445-126">[Delete Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/delete-hierarchy-member-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="9d445-127">[Affecter des autorisations d’objet de modèle &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9d445-127">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="9d445-128">Autorisations des membres de la hiérarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9d445-128">Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  
