---
title: Réactiver un membre ou une collection (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services], reactivating
- consolidated members [Master Data Services], reactivating
- reactivating members [Master Data Services]
- members [Master Data Services], reactivating
- reactivating collections [Master Data Services]
- leaf members [Master Data Services], reactivating
ms.assetid: bb4884c0-3658-4763-92d1-636804278b1c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c449a5a277128bbca6ae24e848bcf12cb0881968
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612448"
---
# <a name="reactivate-a-member-or-collection-master-data-services"></a><span data-ttu-id="dcab4-102">Réactiver un membre ou une collection (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="dcab4-102">Reactivate a Member or Collection (Master Data Services)</span></span>
  <span data-ttu-id="dcab4-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], vous pouvez réactiver un membre qui a été :</span><span class="sxs-lookup"><span data-stu-id="dcab4-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can reactivate a member that was either:</span></span>  
  
-   <span data-ttu-id="dcab4-104">Désactivé par le biais du processus de site</span><span class="sxs-lookup"><span data-stu-id="dcab4-104">Deactivated by the staging process.</span></span>  
  
-   <span data-ttu-id="dcab4-105">Supprimé dans le [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)]MDS</span><span class="sxs-lookup"><span data-stu-id="dcab4-105">Deleted in the MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)].</span></span>  
  
-   <span data-ttu-id="dcab4-106">Supprimé dans l’application web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcab4-106">Deleted in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
 <span data-ttu-id="dcab4-107">La réactivation d’un membre permet de restaurer ses attributs et son appartenance aux hiérarchies et collections.</span><span class="sxs-lookup"><span data-stu-id="dcab4-107">When you reactivate a member, its attributes and its membership in hierarchies and collections are restored.</span></span>  
  
 <span data-ttu-id="dcab4-108">Vous pouvez également réactiver des collections.</span><span class="sxs-lookup"><span data-stu-id="dcab4-108">You can also reactivate collections.</span></span> <span data-ttu-id="dcab4-109">Quand vous procédez ainsi, les attributs et les membres de la collection qui appartiennent à la collection sont restaurés.</span><span class="sxs-lookup"><span data-stu-id="dcab4-109">When you do, the collection's attributes and the members that belong to the collection are restored.</span></span>  
  
 <span data-ttu-id="dcab4-110">Lorsqu'une collection ou un membre est réactivé, toutes les transactions précédentes sont restaurées.</span><span class="sxs-lookup"><span data-stu-id="dcab4-110">When either a collection or member is reactivated, all previous transactions are restored.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dcab4-111">Prérequis</span><span class="sxs-lookup"><span data-stu-id="dcab4-111">Prerequisites</span></span>  
 <span data-ttu-id="dcab4-112">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="dcab4-112">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="dcab4-113">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], vous devez avoir l’autorisation d’accéder à la zone fonctionnelle **Gestion des versions** .</span><span class="sxs-lookup"><span data-stu-id="dcab4-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], you must have permission to the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="dcab4-114">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="dcab4-114">You must be a model administrator.</span></span> <span data-ttu-id="dcab4-115">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="dcab4-115">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-reactivate-a-member-or-collection"></a><span data-ttu-id="dcab4-116">Pour réactiver un membre ou une collection</span><span class="sxs-lookup"><span data-stu-id="dcab4-116">To reactivate a member or collection</span></span>  
  
1.  <span data-ttu-id="dcab4-117">Dans la page d’accueil de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , cliquez sur **Gestion des versions**.</span><span class="sxs-lookup"><span data-stu-id="dcab4-117">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="dcab4-118">Dans la barre de menus, cliquez sur **Transactions**.</span><span class="sxs-lookup"><span data-stu-id="dcab4-118">On the menu bar, click **Transactions**.</span></span>  
  
3.  <span data-ttu-id="dcab4-119">Dans la page **Transactions** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="dcab4-119">On the **Transactions** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="dcab4-120">Dans la liste **Version** , sélectionnez une version.</span><span class="sxs-lookup"><span data-stu-id="dcab4-120">From the **Version** list, select a version.</span></span>  
  
5.  <span data-ttu-id="dcab4-121">Dans le volet **Transactions** , cliquez sur la ligne correspondant au membre ou à la collection à réactiver.</span><span class="sxs-lookup"><span data-stu-id="dcab4-121">In the **Transactions** pane, click the row for the member or collection you want to reactivate.</span></span> <span data-ttu-id="dcab4-122">Cette ligne doit afficher **Actif** dans la colonne **Valeur précédente** et **Désactivé** dans la colonne **Nouvelle valeur** .</span><span class="sxs-lookup"><span data-stu-id="dcab4-122">This row should have **Active** displayed in the **Prior Value** column and **De-Activated** in the **New Value** column.</span></span>  
  
6.  <span data-ttu-id="dcab4-123">Cliquez sur **Inverser la transaction**.</span><span class="sxs-lookup"><span data-stu-id="dcab4-123">Click **Reverse Transaction**.</span></span>  
  
7.  <span data-ttu-id="dcab4-124">Dans la boîte de dialogue de confirmation, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dcab4-124">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="dcab4-125">Une nouvelle transaction est ajoutée, affichant **Activé** dans la colonne **Nouvelle valeur** .</span><span class="sxs-lookup"><span data-stu-id="dcab4-125">A new transaction is added, showing **Active** in the **New Value** column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcab4-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dcab4-126">See Also</span></span>  
 <span data-ttu-id="dcab4-127">[Désactivez ou supprimez des membres à l’aide du processus de site &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="dcab4-127">[Deactivate or Delete Members by Using the Staging Process &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span></span>  
 <span data-ttu-id="dcab4-128">[Supprimer un membre ou une collection &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="dcab4-128">[Delete a Member or Collection &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md) </span></span>  
 <span data-ttu-id="dcab4-129">[Membres &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="dcab4-129">[Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span></span>  
 [<span data-ttu-id="dcab4-130">Collections &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dcab4-130">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)  
  
  
