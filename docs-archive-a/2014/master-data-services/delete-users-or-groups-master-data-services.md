---
title: Supprimer des utilisateurs ou des groupes (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting groups [Master Data Services]
- groups [Master Data Services], deleting
- users [Master Data Services], deleting
- deleting users [Master Data Services]
ms.assetid: 0bbf9d2c-b826-48bb-8aa9-9905db6e717f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: be302bc974994d0f4f17a8e61244065c76fa93ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613500"
---
# <a name="delete-users-or-groups-master-data-services"></a><span data-ttu-id="40c3f-102">Supprimer des utilisateurs ou des groupes (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="40c3f-102">Delete Users or Groups (Master Data Services)</span></span>
  <span data-ttu-id="40c3f-103">Vos pouvez supprimer des utilisateurs ou des groupes lorsque vous ne souhaitez plus qu'ils accèdent à [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40c3f-103">Delete users or groups when you no longer want them to access [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
 <span data-ttu-id="40c3f-104">Notez le comportement suivant lors de la suppression d'utilisateurs et de groupes :</span><span class="sxs-lookup"><span data-stu-id="40c3f-104">Note the following behavior when deleting users and groups:</span></span>  
  
-   <span data-ttu-id="40c3f-105">Si vous supprimez un utilisateur qui est membre d’un groupe ayant accès à [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], l’utilisateur peut toujours accéder à [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] tant que vous ne le supprimez pas du groupe Active Directory ou du groupe local.</span><span class="sxs-lookup"><span data-stu-id="40c3f-105">If you delete a user who is a member of a group that has access to [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], then the user can still access [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] until you remove the user from the Active Directory or local group.</span></span>  
  
-   <span data-ttu-id="40c3f-106">Si vous supprimez un groupe, tous les utilisateurs de ce groupe qui ont accédé à [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] sont affichés dans la liste **Utilisateurs** tant que vous ne les supprimez pas.</span><span class="sxs-lookup"><span data-stu-id="40c3f-106">If you delete a group, all users from the group who have accessed [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] are displayed in the **Users** list until you delete them.</span></span>  
  
-   <span data-ttu-id="40c3f-107">Les modifications apportées à la sécurité ne sont pas propagées à MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] pendant 20 minutes.</span><span class="sxs-lookup"><span data-stu-id="40c3f-107">Changes to security are not propagated to the MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] for 20 minutes.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="40c3f-108">Prérequis</span><span class="sxs-lookup"><span data-stu-id="40c3f-108">Prerequisites</span></span>  
 <span data-ttu-id="40c3f-109">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="40c3f-109">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="40c3f-110">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Autorisations d'accès** .</span><span class="sxs-lookup"><span data-stu-id="40c3f-110">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="40c3f-111">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="40c3f-111">You must be a model administrator.</span></span> <span data-ttu-id="40c3f-112">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="40c3f-112">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-users-or-groups"></a><span data-ttu-id="40c3f-113">Pour supprimer des utilisateurs ou des groupes</span><span class="sxs-lookup"><span data-stu-id="40c3f-113">To delete users or groups</span></span>  
  
1.  <span data-ttu-id="40c3f-114">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Autorisations d'accès**.</span><span class="sxs-lookup"><span data-stu-id="40c3f-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="40c3f-115">Pour supprimer un utilisateur, restez dans la page **Utilisateurs** .</span><span class="sxs-lookup"><span data-stu-id="40c3f-115">To delete a user, remain on the **Users** page.</span></span> <span data-ttu-id="40c3f-116">Pour supprimer un groupe, dans la barre de menus, cliquez sur **Gérer les groupes**.</span><span class="sxs-lookup"><span data-stu-id="40c3f-116">To delete a group, from the menu bar, click **ManageGroups.**</span></span>  
  
3.  <span data-ttu-id="40c3f-117">Dans la grille, sélectionnez la ligne correspondant à l’utilisateur ou au groupe à supprimer.</span><span class="sxs-lookup"><span data-stu-id="40c3f-117">In the grid,select the row for the user or group that you want to delete.</span></span>  
  
4.  <span data-ttu-id="40c3f-118">Cliquez sur **Supprimer l’utilisateur sélectionné** ou **Supprimer le groupe sélectionné**.</span><span class="sxs-lookup"><span data-stu-id="40c3f-118">Click **Delete selected user** or **Delete selected group**.</span></span>  
  
5.  <span data-ttu-id="40c3f-119">Dans la boîte de dialogue de confirmation, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="40c3f-119">On the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40c3f-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="40c3f-120">See Also</span></span>  
 [<span data-ttu-id="40c3f-121">Sécurité &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="40c3f-121">Security &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/security-master-data-services.md)  
  
  
