---
title: Créer une vue d’abonnement (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- subscription views [Master Data Services], creating
- creating subscription views [Master Data Services]
ms.assetid: a5e28961-af16-414a-9845-d2e06aac5214
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e5e2b901e56d75e97a444fd2858ef95872f3b766
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611846"
---
# <a name="create-a-subscription-view-master-data-services"></a><span data-ttu-id="29644-102">Créer une vue d'abonnement (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="29644-102">Create a Subscription View (Master Data Services)</span></span>
  <span data-ttu-id="29644-103">Créez une vue d’abonnement lorsque vous souhaitez créer une vue de vos données dans la [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] base de données afin qu’elles soient utilisées par les systèmes d’abonnement.</span><span class="sxs-lookup"><span data-stu-id="29644-103">Create a subscription view when you want to create a view of your data in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database for use by subscribing systems.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="29644-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="29644-104">Prerequisites</span></span>  
 <span data-ttu-id="29644-105">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="29644-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="29644-106">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Gestion de l'intégration** .</span><span class="sxs-lookup"><span data-stu-id="29644-106">You must have permission to access the **Integration Management** functional area.</span></span>  
  
-   <span data-ttu-id="29644-107">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="29644-107">You must be a model administrator.</span></span> <span data-ttu-id="29644-108">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="29644-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-subscription-view"></a><span data-ttu-id="29644-109">Pour créer une vue d'abonnement</span><span class="sxs-lookup"><span data-stu-id="29644-109">To create a subscription view</span></span>  
  
1.  <span data-ttu-id="29644-110">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Gestion de l'intégration**.</span><span class="sxs-lookup"><span data-stu-id="29644-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Integration Management**.</span></span>  
  
2.  <span data-ttu-id="29644-111">Dans la barre de menus, cliquez sur **Créer des vues**.</span><span class="sxs-lookup"><span data-stu-id="29644-111">From the menu bar, click **Create Views**.</span></span>  
  
3.  <span data-ttu-id="29644-112">Sur la page **vues d’abonnement** , cliquez sur Ajouter une vue d' **abonnement**.</span><span class="sxs-lookup"><span data-stu-id="29644-112">On the **Subscription Views** page, click **Add subscription view**.</span></span>  
  
4.  <span data-ttu-id="29644-113">Dans le volet **créer une vue d’abonnement** , dans la zone nom de la vue d' **abonnement** , tapez un nom pour la vue.</span><span class="sxs-lookup"><span data-stu-id="29644-113">In the **Create Subscription View** pane, in the **Subscription view name** box, type a name for the view.</span></span>  
  
5.  <span data-ttu-id="29644-114">Dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="29644-114">From the **Model** list, select a model.</span></span>  
  
6.  <span data-ttu-id="29644-115">Sélectionnez l’option **version** ou **indicateur de version** , puis sélectionnez dans la liste correspondante.</span><span class="sxs-lookup"><span data-stu-id="29644-115">Select either the **Version** or **Version Flag** option, and then select from the corresponding list.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="29644-116">Créez une vue d'abonnement selon un indicateur de version.</span><span class="sxs-lookup"><span data-stu-id="29644-116">Create a subscription view based on a version flag.</span></span> <span data-ttu-id="29644-117">Lorsque vous verrouillez une version, vous pouvez réaffecter l'indicateur à une version ouverte sans mettre à jour la vue d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="29644-117">When you lock a version, you can reassign the flag to an open version without updating the subscription view.</span></span>  
  
7.  <span data-ttu-id="29644-118">Sélectionnez l’option **entité** ou **hiérarchie dérivée** , puis sélectionnez dans la liste correspondante.</span><span class="sxs-lookup"><span data-stu-id="29644-118">Select either the **Entity** or **Derived hierarchy** option, and then select from the corresponding list.</span></span>  
  
8.  <span data-ttu-id="29644-119">Dans la liste **Format** , sélectionnez un format de vue d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="29644-119">From the **Format** list, select a subscription view format.</span></span>  
  
9. <span data-ttu-id="29644-120">Si vous avez sélectionné **Niveaux explicites** ou **Niveaux dérivés** dans la liste **Format** , tapez le nombre de niveaux dans la hiérarchie à inclure dans la vue.</span><span class="sxs-lookup"><span data-stu-id="29644-120">If you chose **Explicit levels** or **Derived levels** from the **Format** list, type the number of levels in the hierarchy to include in the view.</span></span>  
  
10. <span data-ttu-id="29644-121">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="29644-121">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29644-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="29644-122">See Also</span></span>  
 <span data-ttu-id="29644-123">[Exportation de données &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="29644-123">[Exporting Data &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md) </span></span>  
 <span data-ttu-id="29644-124">[Supprimer une vue d’abonnement &#40;Master Data Services&#41;](delete-a-subscription-view-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="29644-124">[Delete a Subscription View &#40;Master Data Services&#41;](delete-a-subscription-view-master-data-services.md) </span></span>  
 [<span data-ttu-id="29644-125">Créer un indicateur de version &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="29644-125">Create a Version Flag &#40;Master Data Services&#41;</span></span>](create-a-version-flag-master-data-services.md)  
  
  
