---
title: Annoter une transaction (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- annotations [Master Data Services], for transactions
ms.assetid: f5a6b2ca-56de-4e42-9da8-fba0ac3e8d92
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c384f4241d0ddcd78fd8942fe28da8c0b5b1e77c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703067"
---
# <a name="annotate-a-transaction-master-data-services"></a><span data-ttu-id="6f074-102">Annoter une transaction (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="6f074-102">Annotate a Transaction (Master Data Services)</span></span>
  <span data-ttu-id="6f074-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], annotez une transaction lorsque vous souhaitez fournir des informations de prise en charge relatives à la transaction à des fins d'historique.</span><span class="sxs-lookup"><span data-stu-id="6f074-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], annotate a transaction when you want to provide supporting details about the transaction for historical purposes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6f074-104">Vous ne pouvez pas supprimer des annotations.</span><span class="sxs-lookup"><span data-stu-id="6f074-104">You cannot delete annotations.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6f074-105">Prérequis</span><span class="sxs-lookup"><span data-stu-id="6f074-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="6f074-106">Pour annoter des transactions que vous avez créées, vous devez avoir l’autorisation d’accéder à la zone fonctionnelle **Explorateur** et disposer au minimum de l’autorisation **Mettre à jour** sur l’objet de modèle que vous souhaitez annoter.</span><span class="sxs-lookup"><span data-stu-id="6f074-106">To annotate transactions that you created, you must have permission to access the **Explorer** functional area, and have a minimum of **Update** permission to the model object you want to annotate.</span></span>  
  
-   <span data-ttu-id="6f074-107">Pour annoter des transactions pour tous les utilisateurs, vous devez avoir l’autorisation d’accéder à la zone fonctionnelle **Gestion des versions** et être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="6f074-107">To annotate transactions for all users, you must have permission to access the **Version Management** functional area and be a model administrator.</span></span> <span data-ttu-id="6f074-108">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6f074-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-annotate-a-transaction-in-explorer"></a><span data-ttu-id="6f074-109">Pour annoter une transaction dans l'Explorateur</span><span class="sxs-lookup"><span data-stu-id="6f074-109">To annotate a transaction in Explorer</span></span>  
  
1.  <span data-ttu-id="6f074-110">Dans la page d'accueil de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="6f074-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="6f074-111">Dans la liste **Version** , sélectionnez une version.</span><span class="sxs-lookup"><span data-stu-id="6f074-111">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="6f074-112">Cliquez sur **Explorateur**.</span><span class="sxs-lookup"><span data-stu-id="6f074-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="6f074-113">Dans la barre de menus, pointez sur **Entités** , puis cliquez sur l’entité qui contient le membre dont vous voulez annoter une transaction.</span><span class="sxs-lookup"><span data-stu-id="6f074-113">From the menu bar, point to **Entities** and click the entity that contains the member with a transaction you want to annotate.</span></span>  
  
5.  <span data-ttu-id="6f074-114">Dans la grille, cliquez sur la ligne correspondant au membre.</span><span class="sxs-lookup"><span data-stu-id="6f074-114">In the grid, click the row of the member.</span></span>  
  
6.  <span data-ttu-id="6f074-115">Cliquez sur **Afficher les transactions**.</span><span class="sxs-lookup"><span data-stu-id="6f074-115">Click **View Transactions**.</span></span>  
  
7.  <span data-ttu-id="6f074-116">Dans la boîte de dialogue **Afficher les transactions** , cliquez sur la transaction que vous souhaitez annoter.</span><span class="sxs-lookup"><span data-stu-id="6f074-116">In the **View Transactions** dialog box, click the transaction you want to annotate.</span></span>  
  
8.  <span data-ttu-id="6f074-117">Dans la zone en bas de la boîte de dialogue, tapez votre annotation.</span><span class="sxs-lookup"><span data-stu-id="6f074-117">In the box at the bottom of the dialog box, type your annotation.</span></span>  
  
9. <span data-ttu-id="6f074-118">Cliquez sur **Ajouter une annotation**.</span><span class="sxs-lookup"><span data-stu-id="6f074-118">Click **Add Annotation**.</span></span> <span data-ttu-id="6f074-119">L’annotation s’affiche dans le volet **Annotations** .</span><span class="sxs-lookup"><span data-stu-id="6f074-119">The annotation is displayed in the **Annotations** pane.</span></span>  
  
### <a name="to-annotate-a-transaction-in-version-management-administrators-only"></a><span data-ttu-id="6f074-120">Pour annoter une transaction dans la zone Gestion des versions (administrateurs uniquement)</span><span class="sxs-lookup"><span data-stu-id="6f074-120">To annotate a transaction in Version Management (administrators only)</span></span>  
  
1.  <span data-ttu-id="6f074-121">Dans la page d’accueil de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , cliquez sur **Gestion des versions**.</span><span class="sxs-lookup"><span data-stu-id="6f074-121">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="6f074-122">Dans la barre de menus, cliquez sur **Transactions**.</span><span class="sxs-lookup"><span data-stu-id="6f074-122">On the menu bar, click **Transactions**.</span></span>  
  
3.  <span data-ttu-id="6f074-123">Dans le volet **Transactions** , cliquez sur la ligne de la grille correspondant à la transaction que vous souhaitez annoter.</span><span class="sxs-lookup"><span data-stu-id="6f074-123">In the **Transactions** pane, click the row in the grid for the transaction you want to annotate.</span></span>  
  
4.  <span data-ttu-id="6f074-124">Dans la zone **Annotation** du volet **Annotations de transaction** , tapez votre annotation.</span><span class="sxs-lookup"><span data-stu-id="6f074-124">In the **Transaction Annotations** pane, in the **Annotation** box, type your annotation.</span></span>  
  
5.  <span data-ttu-id="6f074-125">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6f074-125">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f074-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6f074-126">See Also</span></span>  
 <span data-ttu-id="6f074-127">[Annotations &#40;Master Data Services&#41;](../../2014/master-data-services/annotations-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="6f074-127">[Annotations &#40;Master Data Services&#41;](../../2014/master-data-services/annotations-master-data-services.md) </span></span>  
 [<span data-ttu-id="6f074-128">Transactions &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6f074-128">Transactions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/transactions-master-data-services.md)  
  
  
