---
title: Utilisateurs et groupes (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- users [Master Data Services]
- groups [Master Data Services]
- users [Master Data Services], about users
- groups [Master Data Services], about groups
ms.assetid: ed08dd2d-248e-4b68-91d4-e9961cb50eed
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: efad65bf273d58b4f60b98d050a8b99705cb00ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710684"
---
# <a name="users-and-groups-master-data-services"></a><span data-ttu-id="da712-102">Utilisateurs et groupes (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="da712-102">Users and Groups (Master Data Services)</span></span>
  <span data-ttu-id="da712-103">Pour accéder à l'application Web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , un utilisateur doit disposer d'un compte de domaine Windows ou d'un compte sur le serveur où [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] est installé.</span><span class="sxs-lookup"><span data-stu-id="da712-103">To access the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application a user must have a Windows domain account or an account on the server computer where [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] is installed.</span></span> <span data-ttu-id="da712-104">Pour accorder l'accès à [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , vous pouvez, au choix :</span><span class="sxs-lookup"><span data-stu-id="da712-104">To grant access to [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] you can either:</span></span>  
  
-   <span data-ttu-id="da712-105">Ajouter le compte d'utilisateur à un domaine ou à un groupe local, puis ajouter le groupe à la liste des groupes dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da712-105">Add the user account to a domain or local group and then add the group to the list of groups in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
-   <span data-ttu-id="da712-106">Ajouter le compte d'utilisateur à la liste des utilisateurs dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da712-106">Add the user account to the list of users in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="da712-107">Lorsqu’un utilisateur appartient à un groupe qui a accès à [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], le nom de l’utilisateur est ajouté automatiquement à la liste la première fois où l’utilisateur accède à [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] ou à MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da712-107">When a user belongs to a group that has access to [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], the user's name is automatically added to the list of users the first time the user accesses [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] or the MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)].</span></span>  
  
 <span data-ttu-id="da712-108">Pour agir dans la zone fonctionnelle **Explorateur** de l'interface utilisateur, le groupe ou l'utilisateur doit avoir accès à la zone fonctionnelle **Explorateur** et disposer d'une autorisation sur les objets modèle.</span><span class="sxs-lookup"><span data-stu-id="da712-108">To take action within the **Explorer** functional area of the UI, the group or user must be assigned access to the **Explorer** functional area and assigned permission to model objects.</span></span>  
  
 <span data-ttu-id="da712-109">Si un utilisateur ou un groupe nécessite l'accès à d'autres zones fonctionnelles, l'utilisateur ou le groupe doit être un administrateur.</span><span class="sxs-lookup"><span data-stu-id="da712-109">If a user or group needs access to other functional areas, the user or group must be an administrator.</span></span> <span data-ttu-id="da712-110">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="da712-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
## <a name="best-practice"></a><span data-ttu-id="da712-111">Bonne pratique</span><span class="sxs-lookup"><span data-stu-id="da712-111">Best Practice</span></span>  
 <span data-ttu-id="da712-112">Pour simplifier l'administration, créez des groupes et affectez à chaque groupe l'autorisation sur des zones fonctionnelles et objets modèles.</span><span class="sxs-lookup"><span data-stu-id="da712-112">To simplify administration, create groups and assign each group permission to functional areas and model objects.</span></span> <span data-ttu-id="da712-113">Vous pouvez ensuite ajouter et supprimer des utilisateurs dans les groupes sans accéder à l'interface utilisateur de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="da712-113">You can then add and remove users from the groups without accessing the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] UI.</span></span>  
  
 <span data-ttu-id="da712-114">N'affectez pas d'autorisations supplémentaires à un utilisateur individuel et n'incluez pas un utilisateur dans plusieurs groupes qui ont accès à [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da712-114">Do not assign additional permissions to an individual user, and do not include a user in multiple groups that have access to [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span> <span data-ttu-id="da712-115">De plus, n'utilisez pas d'autorisations des membres de la hiérarchie à moins que vous ne souhaitiez qu'un groupe ait un accès limité à des membres spécifiques.</span><span class="sxs-lookup"><span data-stu-id="da712-115">In addition, do not use hierarchy member permissions unless you want a group to have limited access to specific members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da712-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="da712-116">See Also</span></span>  
 <span data-ttu-id="da712-117">[Ajouter un &#40;d’utilisateur Master Data Services&#41;](../../2014/master-data-services/add-a-user-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="da712-117">[Add a User &#40;Master Data Services&#41;](../../2014/master-data-services/add-a-user-master-data-services.md) </span></span>  
 <span data-ttu-id="da712-118">[Ajouter un groupe &#40;Master Data Services&#41;](../../2014/master-data-services/add-a-group-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="da712-118">[Add a Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-a-group-master-data-services.md) </span></span>  
 <span data-ttu-id="da712-119">[Supprimer des utilisateurs ou des groupes &#40;Master Data Services&#41;](../../2014/master-data-services/delete-users-or-groups-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="da712-119">[Delete Users or Groups &#40;Master Data Services&#41;](../../2014/master-data-services/delete-users-or-groups-master-data-services.md) </span></span>  
 [<span data-ttu-id="da712-120">Tester les autorisations d’un utilisateur &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="da712-120">Test a User's Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/test-a-user-s-permissions-master-data-services.md)  
  
  
