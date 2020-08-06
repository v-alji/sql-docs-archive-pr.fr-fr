---
title: Supprimer des autorisations d’objet de modèle (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting model object permissions [Master Data Services]
- permissions [Master Data Services], deleting model object permissions
- models [Master Data Services], deleting object permissions
ms.assetid: 859c5952-f600-4940-8064-1afd13f7f6dc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 98da869476e597d76a83b0b86cc9e6e4274a25e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699953"
---
# <a name="delete-model-object-permissions-master-data-services"></a><span data-ttu-id="6281a-102">Supprimer des autorisations d'objet de modèle (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="6281a-102">Delete Model Object Permissions (Master Data Services)</span></span>
  <span data-ttu-id="6281a-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], supprimez les autorisations d'objet de modèle pour supprimer toutes les affectations effectuées.</span><span class="sxs-lookup"><span data-stu-id="6281a-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete model object permissions to remove any assignments that have been made.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6281a-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="6281a-104">Prerequisites</span></span>  
 <span data-ttu-id="6281a-105">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="6281a-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="6281a-106">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Autorisations d'accès** .</span><span class="sxs-lookup"><span data-stu-id="6281a-106">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="6281a-107">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="6281a-107">You must be a model administrator.</span></span> <span data-ttu-id="6281a-108">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6281a-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-model-object-permissions"></a><span data-ttu-id="6281a-109">Pour supprimer des autorisations d'objet de modèle</span><span class="sxs-lookup"><span data-stu-id="6281a-109">To delete model object permissions</span></span>  
  
1.  <span data-ttu-id="6281a-110">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Autorisations d'accès**.</span><span class="sxs-lookup"><span data-stu-id="6281a-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="6281a-111">Dans la page **Utilisateurs** ou **Groupes** , sélectionnez la ligne de l'utilisateur ou du groupe à modifier.</span><span class="sxs-lookup"><span data-stu-id="6281a-111">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="6281a-112">Cliquez sur **Modifier l'utilisateur sélectionné**.</span><span class="sxs-lookup"><span data-stu-id="6281a-112">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="6281a-113">Cliquez sur l'onglet **Modèles** .</span><span class="sxs-lookup"><span data-stu-id="6281a-113">Click the **Models** tab.</span></span>  
  
5.  <span data-ttu-id="6281a-114">Dans la liste **Modèle** , sélectionnez éventuellement un modèle.</span><span class="sxs-lookup"><span data-stu-id="6281a-114">Optionally, select a model from the **Model** list.</span></span>  
  
6.  <span data-ttu-id="6281a-115">Dans le volet **Résumé des autorisations du modèle** , sélectionnez la ligne de l’autorisation que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="6281a-115">In the **Model Permission Summary** pane, select the row for the permission that you want to delete.</span></span>  
  
7.  <span data-ttu-id="6281a-116">Cliquez sur **Supprimer l’autorisation sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="6281a-116">Click **Delete selected permission**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6281a-117">Vous ne pouvez pas supprimer une autorisation d'un utilisateur si elle est héritée d'un groupe.</span><span class="sxs-lookup"><span data-stu-id="6281a-117">You cannot remove a permission from a user if the permission is inherited from a group.</span></span> <span data-ttu-id="6281a-118">Vous devez supprimer l'autorisation du groupe à la place.</span><span class="sxs-lookup"><span data-stu-id="6281a-118">You must remove the permission from the group instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6281a-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6281a-119">See Also</span></span>  
 <span data-ttu-id="6281a-120">[Autorisations d’objet de modèle &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="6281a-120">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="6281a-121">Affecter des autorisations d’objet de modèle &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6281a-121">Assign Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md)  
  
  
