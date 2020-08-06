---
title: Créer un administrateur de modèle (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- administrators [Master Data Services], creating
ms.assetid: dae17afc-3b39-490e-b51f-2d8da26d429e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 24efc3961e6ed5b9f41b2321dfcc4fbf16632270
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614709"
---
# <a name="create-a-model-administrator-master-data-services"></a><span data-ttu-id="5343b-102">Créer un administrateur de modèle (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5343b-102">Create a Model Administrator (Master Data Services)</span></span>
  <span data-ttu-id="5343b-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] , créez un administrateur de modèle lorsque vous souhaitez qu’un groupe ou un utilisateur dispose de l’autorisation **mettre à jour** sur tous les objets dans un ou plusieurs modèles.</span><span class="sxs-lookup"><span data-stu-id="5343b-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a model administrator when you want a group or user to have **Update** permission to all objects in one or more models.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="5343b-104">Pour simplifier l’administration, créez un groupe Windows ou local et configurez-le en tant qu’administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="5343b-104">To simplify administration, create a Windows or local group and configure it as a model administrator.</span></span> <span data-ttu-id="5343b-105">Vous pouvez ensuite ajouter et supprimer des utilisateurs dans le groupe sans accéder à l'interface utilisateur de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5343b-105">You can then add and remove users from the group without accessing [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5343b-106">Prérequis</span><span class="sxs-lookup"><span data-stu-id="5343b-106">Prerequisites</span></span>  
 <span data-ttu-id="5343b-107">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="5343b-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="5343b-108">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Autorisations d'accès** .</span><span class="sxs-lookup"><span data-stu-id="5343b-108">You must have permission to access the **User and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="5343b-109">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="5343b-109">You must be a model administrator.</span></span> <span data-ttu-id="5343b-110">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5343b-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-model-administrator"></a><span data-ttu-id="5343b-111">Pour créer un administrateur de modèle</span><span class="sxs-lookup"><span data-stu-id="5343b-111">To create a model administrator</span></span>  
  
1.  <span data-ttu-id="5343b-112">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Autorisations d'accès**.</span><span class="sxs-lookup"><span data-stu-id="5343b-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="5343b-113">Dans la page **Utilisateurs** ou **Groupes** , sélectionnez la ligne de l'utilisateur ou du groupe à modifier.</span><span class="sxs-lookup"><span data-stu-id="5343b-113">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="5343b-114">Cliquez sur **Modifier l'utilisateur sélectionné**.</span><span class="sxs-lookup"><span data-stu-id="5343b-114">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="5343b-115">Cliquez sur l'onglet **Modèles** .</span><span class="sxs-lookup"><span data-stu-id="5343b-115">Click the **Models** tab.</span></span>  
  
5.  <span data-ttu-id="5343b-116">Dans la liste **Modèle** , sélectionnez éventuellement un modèle.</span><span class="sxs-lookup"><span data-stu-id="5343b-116">Optionally, select a model from the **Model** list.</span></span>  
  
6.  <span data-ttu-id="5343b-117">Cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="5343b-117">Click **Edit**.</span></span>  
  
7.  <span data-ttu-id="5343b-118">Cliquez sur le modèle auquel vous souhaitez affecter une autorisation.</span><span class="sxs-lookup"><span data-stu-id="5343b-118">Click the model you want to grant permission to.</span></span>  
  
8.  <span data-ttu-id="5343b-119">Dans le menu, sélectionnez **mettre à jour**.</span><span class="sxs-lookup"><span data-stu-id="5343b-119">From the menu, select **Update**.</span></span>  
  
9. <span data-ttu-id="5343b-120">Effectuez les étapes 7 et 8 pour chaque modèle que vous souhaitez que le groupe ou l'utilisateur administre.</span><span class="sxs-lookup"><span data-stu-id="5343b-120">Complete steps 7 and 8 for each model you want the group or user to be an administrator for.</span></span>  
  
10. <span data-ttu-id="5343b-121">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5343b-121">Click **Save**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5343b-122">Notes</span><span class="sxs-lookup"><span data-stu-id="5343b-122">Remarks</span></span>  
 <span data-ttu-id="5343b-123">N'affectez pas d'autres autorisations à des objets modèle ou membres de hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="5343b-123">Do not assign any other permissions to model objects or hierarchy members.</span></span> <span data-ttu-id="5343b-124">Si vous le faites, l’utilisateur n’est plus un administrateur et ne peut pas afficher le modèle dans une zone fonctionnelle autre que l' **Explorateur**.</span><span class="sxs-lookup"><span data-stu-id="5343b-124">If you do, the user is no longer an administrator and cannot view the model in any functional area other than **Explorer**.</span></span>  
  
 <span data-ttu-id="5343b-125">Il existe une exception : si l’utilisateur a l’autorisation **mise à jour** attribuée à une **racine** de la hiérarchie sous l’onglet **membres de hiérarchie** , l’utilisateur est toujours considéré comme un administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="5343b-125">There is one exception: if the user has **Update** permission assigned to a hierarchy **Root** on the **Hierarchy Members** tab, the user is still considered a model administrator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5343b-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5343b-126">See Also</span></span>  
 <span data-ttu-id="5343b-127">[Administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5343b-127">[Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md) </span></span>  
 <span data-ttu-id="5343b-128">[Affecter des autorisations d’objet de modèle &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5343b-128">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="5343b-129">[Affecter des autorisations de membre de hiérarchie &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5343b-129">[Assign Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="5343b-130">[Autorisations d’objet de modèle &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5343b-130">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="5343b-131">Autorisations des membres de la hiérarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5343b-131">Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  
