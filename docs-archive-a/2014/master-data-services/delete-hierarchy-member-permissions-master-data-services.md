---
title: Supprimer des autorisations de membre de hiérarchie (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting member permissions [Master Data Services]
- members [Master Data Services], deleting permissions
- permissions [Master Data Services], deleting member permissions
ms.assetid: 7f22d5e2-70c1-422c-99c2-e995a47d812a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8b6e7fbfc4379733d5cb809ce4d46d2c12d05a48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699954"
---
# <a name="delete-hierarchy-member-permissions-master-data-services"></a><span data-ttu-id="4d534-102">Supprimer des autorisations de membre de hiérarchie (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="4d534-102">Delete Hierarchy Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="4d534-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], supprimez les autorisations d'objet de modèle pour supprimer toutes les affectations effectuées.</span><span class="sxs-lookup"><span data-stu-id="4d534-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete model object permissions to remove any assignments that have been made.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4d534-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="4d534-104">Prerequisites</span></span>  
 <span data-ttu-id="4d534-105">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="4d534-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="4d534-106">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Autorisations d'accès** .</span><span class="sxs-lookup"><span data-stu-id="4d534-106">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="4d534-107">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="4d534-107">You must be a model administrator.</span></span> <span data-ttu-id="4d534-108">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4d534-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-hierarchy-member-permissions"></a><span data-ttu-id="4d534-109">Pour supprimer des autorisations de membre de hiérarchie</span><span class="sxs-lookup"><span data-stu-id="4d534-109">To delete hierarchy member permissions</span></span>  
  
1.  <span data-ttu-id="4d534-110">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Autorisations d'accès**.</span><span class="sxs-lookup"><span data-stu-id="4d534-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="4d534-111">Dans la page **Utilisateurs** ou **Groupes** , sélectionnez la ligne de l'utilisateur ou du groupe à modifier.</span><span class="sxs-lookup"><span data-stu-id="4d534-111">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="4d534-112">Cliquez sur **Modifier l'utilisateur sélectionné**.</span><span class="sxs-lookup"><span data-stu-id="4d534-112">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="4d534-113">Cliquez sur l'onglet **Membres de hiérarchie** .</span><span class="sxs-lookup"><span data-stu-id="4d534-113">Click the **Hierarchy Members** tab.</span></span>  
  
5.  <span data-ttu-id="4d534-114">Dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="4d534-114">From the **Model** list, select a model.</span></span>  
  
6.  <span data-ttu-id="4d534-115">Dans la liste **Version** , sélectionnez une version.</span><span class="sxs-lookup"><span data-stu-id="4d534-115">From the **Version** list, select a version.</span></span>  
  
7.  <span data-ttu-id="4d534-116">Dans le volet **Résumé des autorisations des membres** de la hiérarchie, sélectionnez la ligne de l’autorisation que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="4d534-116">In the **Hierarchy Member Permission Summary** pane, select the row for the permission that you want to delete.</span></span>  
  
8.  <span data-ttu-id="4d534-117">Cliquez sur **Supprimer l’autorisation sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="4d534-117">Click **Delete selected permission**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4d534-118">Vous ne pouvez pas supprimer une autorisation d'un utilisateur si elle est héritée d'un groupe.</span><span class="sxs-lookup"><span data-stu-id="4d534-118">You cannot remove a permission from a user if the permission is inherited from a group.</span></span> <span data-ttu-id="4d534-119">Vous devez supprimer l'autorisation du groupe à la place.</span><span class="sxs-lookup"><span data-stu-id="4d534-119">You must remove the permission from the group instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d534-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4d534-120">See Also</span></span>  
 <span data-ttu-id="4d534-121">[Autorisations des membres de la hiérarchie &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="4d534-121">[Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="4d534-122">Affecter des autorisations de membre de hiérarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4d534-122">Assign Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md)  
  
  
