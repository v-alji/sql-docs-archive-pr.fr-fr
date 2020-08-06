---
title: Affecter des autorisations d’objet de modèle (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], assigning object permissions
- permissions [Master Data Services], assigning model object permissions
ms.assetid: 4b80148d-2318-415c-9479-28c240e48bcd
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 92ac8ef3ac63b7128c4cbb7e9305ee6bd56ca010
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610718"
---
# <a name="assign-model-object-permissions-master-data-services"></a><span data-ttu-id="283c6-102">Affecter des autorisations d'objet de modèle (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="283c6-102">Assign Model Object Permissions (Master Data Services)</span></span>
  <span data-ttu-id="283c6-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], affectez les autorisations aux objets de modèle lorsque vous devez donner à un utilisateur ou un groupe l'accès aux données dans la zone fonctionnelle **Explorateur** de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], ou lorsque vous devez faire d'un utilisateur ou d'un groupe un administrateur.</span><span class="sxs-lookup"><span data-stu-id="283c6-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], assign permissions to model objects when you need to give a user or group access to data in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], or when you need to make a user or group an administrator.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="283c6-104">Lorsque vous affectez une autorisation à un modèle, l'autorisation à tous les autres modèles est refusée implicitement.</span><span class="sxs-lookup"><span data-stu-id="283c6-104">When you assign permission to a model, permission to all other models is implicitly denied.</span></span> <span data-ttu-id="283c6-105">Si vous n'affectez pas d'autorisations d'objet de modèle, l'utilisateur ou le groupe ne peut accéder à aucune donnée dans l' **Explorateur**.</span><span class="sxs-lookup"><span data-stu-id="283c6-105">If you do not assign model object permissions, the user or group cannot access any data in **Explorer**.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="283c6-106">Prérequis</span><span class="sxs-lookup"><span data-stu-id="283c6-106">Prerequisites</span></span>  
 <span data-ttu-id="283c6-107">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="283c6-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="283c6-108">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Autorisations d'accès** .</span><span class="sxs-lookup"><span data-stu-id="283c6-108">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="283c6-109">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="283c6-109">You must be a model administrator.</span></span> <span data-ttu-id="283c6-110">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="283c6-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-assign-model-object-permissions"></a><span data-ttu-id="283c6-111">Pour affecter des autorisations d'objet de modèle</span><span class="sxs-lookup"><span data-stu-id="283c6-111">To assign model object permissions</span></span>  
  
1.  <span data-ttu-id="283c6-112">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Autorisations d'accès**.</span><span class="sxs-lookup"><span data-stu-id="283c6-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="283c6-113">Dans la page **Utilisateurs** ou **Groupes** , sélectionnez la ligne de l'utilisateur ou du groupe à modifier.</span><span class="sxs-lookup"><span data-stu-id="283c6-113">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="283c6-114">Cliquez sur **Modifier l'utilisateur sélectionné**.</span><span class="sxs-lookup"><span data-stu-id="283c6-114">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="283c6-115">Cliquez sur l'onglet **Modèles** .</span><span class="sxs-lookup"><span data-stu-id="283c6-115">Click the **Models** tab.</span></span>  
  
5.  <span data-ttu-id="283c6-116">Dans la liste **Modèle** , sélectionnez éventuellement un modèle.</span><span class="sxs-lookup"><span data-stu-id="283c6-116">Optionally, select a model from the **Model** list.</span></span>  
  
6.  <span data-ttu-id="283c6-117">Cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="283c6-117">Click **Edit**.</span></span>  
  
7.  <span data-ttu-id="283c6-118">Développez l'arborescence, puis cliquez sur l'objet de modèle auquel vous souhaitez affecter des autorisations.</span><span class="sxs-lookup"><span data-stu-id="283c6-118">Expand the tree, and click the model object you want to assign permissions to.</span></span>  
  
8.  <span data-ttu-id="283c6-119">Dans le menu, sélectionnez **lecture seule**, **mettre à jour**ou **refuser**.</span><span class="sxs-lookup"><span data-stu-id="283c6-119">From the menu, select **Read-only**, **Update**, or **Deny**.</span></span>  
  
9. <span data-ttu-id="283c6-120">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="283c6-120">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="283c6-121">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="283c6-121">Next Steps</span></span>  
  
-   <span data-ttu-id="283c6-122">(Facultatif) [Affecter des autorisations de membre de hiérarchie &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="283c6-122">(Optional) [Assign Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="283c6-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="283c6-123">See Also</span></span>  
 <span data-ttu-id="283c6-124">[Supprimer les autorisations de l’objet de modèle &#40;Master Data Services&#41;](../../2014/master-data-services/delete-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="283c6-124">[Delete Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/delete-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="283c6-125">[Autorisations d’objet de modèle &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="283c6-125">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="283c6-126">Créer un administrateur de modèle &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="283c6-126">Create a Model Administrator &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-model-administrator-master-data-services.md)  
  
  
