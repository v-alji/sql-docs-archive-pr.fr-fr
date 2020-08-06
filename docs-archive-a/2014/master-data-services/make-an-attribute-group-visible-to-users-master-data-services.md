---
title: Rendre un groupe d’attributs visible pour les utilisateurs (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: b2f6cc27-dbc9-4f3f-961e-e81e76375248
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 309ad0392cd717d4a8a11470621144ef9e604fd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600125"
---
# <a name="make-an-attribute-group-visible-to-users-master-data-services"></a><span data-ttu-id="6c720-102">Rendre un groupe d'attributs visible pour les utilisateurs (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="6c720-102">Make an Attribute Group Visible to Users (Master Data Services)</span></span>
  <span data-ttu-id="6c720-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], rendez un groupe d'attributs visible aux utilisateurs ou aux groupes lorsque vous souhaitez que les utilisateurs disposent d'onglets au-dessus de la grille dans la zone fonctionnelle **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="6c720-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], make an attribute group visible to users or groups when you want users to have tabs above the grid in the **Explorer** functional area.</span></span>  
  
 <span data-ttu-id="6c720-104">Lorsque vous créez un groupe d'attributs, il est automatiquement masqué pour tous les utilisateurs, à l'exception de son créateur.</span><span class="sxs-lookup"><span data-stu-id="6c720-104">When you create an attribute group, it is automatically hidden from all users except the one who created it.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6c720-105">Prérequis</span><span class="sxs-lookup"><span data-stu-id="6c720-105">Prerequisites</span></span>  
 <span data-ttu-id="6c720-106">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="6c720-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="6c720-107">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="6c720-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="6c720-108">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="6c720-108">You must be a model administrator.</span></span> <span data-ttu-id="6c720-109">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6c720-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="6c720-110">Au moins un groupe d'attributs doit exister.</span><span class="sxs-lookup"><span data-stu-id="6c720-110">At least one attribute group must exist.</span></span> <span data-ttu-id="6c720-111">Pour plus d’informations, consultez [Créer un groupe d’attributs &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-attribute-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6c720-111">For more information, see [Create an Attribute Group &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-attribute-group-master-data-services.md).</span></span>  
  
### <a name="to-make-an-attribute-group-visible-to-users"></a><span data-ttu-id="6c720-112">Pour rendre un groupe d'attributs visible pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6c720-112">To make an attribute group visible to users</span></span>  
  
1.  <span data-ttu-id="6c720-113">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="6c720-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="6c720-114">Dans la page **vue du modèle** , dans la barre de menus, pointez sur **gérer** , puis cliquez sur groupes d' **attributs**.</span><span class="sxs-lookup"><span data-stu-id="6c720-114">On the **Model View** page, from the menu bar, point to **Manage** and click **Attribute Groups**.</span></span>  
  
3.  <span data-ttu-id="6c720-115">Dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="6c720-115">From the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="6c720-116">Dans la liste **Entité** , sélectionnez une entité.</span><span class="sxs-lookup"><span data-stu-id="6c720-116">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="6c720-117">Cliquez sur le signe plus (+) pour développer **groupes feuille**, **groupes consolidés**ou **groupes de collections**, selon le type de groupe que vous voulez rendre visible.</span><span class="sxs-lookup"><span data-stu-id="6c720-117">Click the plus sign to expand **Leaf Groups**, **Consolidated Groups**, or **Collection Groups**, depending on the type of group you want to make visible.</span></span>  
  
6.  <span data-ttu-id="6c720-118">Cliquez sur le signe plus (+) pour développer le groupe que vous souhaitez rendre visible.</span><span class="sxs-lookup"><span data-stu-id="6c720-118">Click the plus sign to expand the group you want to make visible.</span></span>  
  
7.  <span data-ttu-id="6c720-119">Cliquez sur **utilisateurs** ou **groupes**, selon que vous rendez le groupe visible pour un utilisateur ou un groupe.</span><span class="sxs-lookup"><span data-stu-id="6c720-119">Click either **Users** or **Groups**, depending on whether you are making the group visible to a user or a group.</span></span>  
  
8.  <span data-ttu-id="6c720-120">Cliquez sur **modifier l’élément sélectionné**.</span><span class="sxs-lookup"><span data-stu-id="6c720-120">Click **Edit selected item**.</span></span>  
  
9. <span data-ttu-id="6c720-121">Cliquez sur utilisateurs ou groupes dans la zone **disponible** , puis sur la flèche **Ajouter** .</span><span class="sxs-lookup"><span data-stu-id="6c720-121">Click users or groups in the **Available** box and click the **Add** arrow.</span></span> <span data-ttu-id="6c720-122">Pour les ajouter tous, cliquez sur la flèche **Ajouter tout** .</span><span class="sxs-lookup"><span data-stu-id="6c720-122">To add all, click the **Add All** arrow.</span></span>  
  
10. <span data-ttu-id="6c720-123">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6c720-123">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c720-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6c720-124">See Also</span></span>  
 <span data-ttu-id="6c720-125">[Groupes d’attributs &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="6c720-125">[Attribute Groups &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span></span>  
 [<span data-ttu-id="6c720-126">Créer un groupe d’attributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6c720-126">Create an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-attribute-group-master-data-services.md)  
  
  
