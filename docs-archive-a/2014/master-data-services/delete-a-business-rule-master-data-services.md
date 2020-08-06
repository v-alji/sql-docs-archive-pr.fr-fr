---
title: Supprimer une règle d’entreprise (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting business rules [Master Data Services]
- business rules [Master Data Services], deleting
ms.assetid: b97aa4f9-569f-451d-ad62-65b81f980299
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8e6db486f71634cf025c57eabbedeeb9efdbc437
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695775"
---
# <a name="delete-a-business-rule-master-data-services"></a><span data-ttu-id="84a88-102">Supprimer une règle d'entreprise (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="84a88-102">Delete a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="84a88-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], supprimez une règle d'entreprise lorsque vous n'en avez plus besoin.</span><span class="sxs-lookup"><span data-stu-id="84a88-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete a business rule when it is no longer needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="84a88-104">Vous pouvez empêcher la validation des données par rapport à une règle d'entreprise en l'excluant, plutôt qu'en la supprimant.</span><span class="sxs-lookup"><span data-stu-id="84a88-104">You can prevent data from being validated against a business rule by excluding it, rather than deleting it.</span></span> <span data-ttu-id="84a88-105">Pour plus d’informations, consultez [Exclure une règle d’entreprise &#40;Master Data Services&#41;](exclude-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="84a88-105">For more information, see [Exclude a Business Rule &#40;Master Data Services&#41;](exclude-a-business-rule-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="84a88-106">Prérequis</span><span class="sxs-lookup"><span data-stu-id="84a88-106">Prerequisites</span></span>  
 <span data-ttu-id="84a88-107">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="84a88-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="84a88-108">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="84a88-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="84a88-109">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="84a88-109">You must be a model administrator.</span></span> <span data-ttu-id="84a88-110">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="84a88-110">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-a-business-rule"></a><span data-ttu-id="84a88-111">Pour supprimer une règle d'entreprise</span><span class="sxs-lookup"><span data-stu-id="84a88-111">To delete a business rule</span></span>  
  
1.  <span data-ttu-id="84a88-112">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="84a88-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="84a88-113">Dans la barre de menus, pointez sur **Gérer** et cliquez sur **Règles d'entreprise**.</span><span class="sxs-lookup"><span data-stu-id="84a88-113">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="84a88-114">Dans la page **Maintenance des règles d’entreprise** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="84a88-114">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="84a88-115">Dans la liste **Entité** , sélectionnez une entité.</span><span class="sxs-lookup"><span data-stu-id="84a88-115">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="84a88-116">Dans la liste **Type de membre** , sélectionnez un type de membre auquel appliquer la règle d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="84a88-116">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="84a88-117">Dans la liste **Attribut** , sélectionnez un attribut ou conservez l’option par défaut **Tout**.</span><span class="sxs-lookup"><span data-stu-id="84a88-117">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="84a88-118">Dans la grille, cliquez sur la ligne pour la règle d'entreprise à supprimer.</span><span class="sxs-lookup"><span data-stu-id="84a88-118">In the grid, click the row for the business rule you want to delete.</span></span>  
  
8.  <span data-ttu-id="84a88-119">Cliquez sur **Supprimer la règle d’entreprise sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="84a88-119">Click **Delete selected business rule**.</span></span>  
  
9. <span data-ttu-id="84a88-120">Dans la boîte de dialogue de confirmation, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="84a88-120">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="84a88-121">La valeur dans la colonne **État** est **suppression en attente**.</span><span class="sxs-lookup"><span data-stu-id="84a88-121">The value in the **Status** column is **Deletion pending**.</span></span>  
  
10. <span data-ttu-id="84a88-122">Cliquez sur **Publier les règles d’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="84a88-122">Click **Publish business rules**.</span></span>  
  
11. <span data-ttu-id="84a88-123">Dans la boîte de dialogue de confirmation, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="84a88-123">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84a88-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="84a88-124">See Also</span></span>  
 <span data-ttu-id="84a88-125">[Exclure une règle d’entreprise &#40;Master Data Services&#41;](exclude-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="84a88-125">[Exclude a Business Rule &#40;Master Data Services&#41;](exclude-a-business-rule-master-data-services.md) </span></span>  
 <span data-ttu-id="84a88-126">[Créer et publier une règle d’entreprise &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="84a88-126">[Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span></span>  
 [<span data-ttu-id="84a88-127">Règles d’entreprise &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="84a88-127">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
