---
title: Ajouter un saut de page (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 3846cd48-2787-47e9-b13b-7fc45a205f68
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 55d6be3ae47827c5a8ff4a5b36e3ff2ce80e1034
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600545"
---
# <a name="add-a-page-break-report-builder-and-ssrs"></a><span data-ttu-id="07a59-102">Ajouter un saut de page (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="07a59-102">Add a Page Break (Report Builder and SSRS)</span></span>
  <span data-ttu-id="07a59-103">Vous pouvez ajouter un saut de page aux rectangles, régions de données ou groupes dans des régions de données pour contrôler la quantité d'informations sur chaque page.</span><span class="sxs-lookup"><span data-stu-id="07a59-103">You can add a page break to rectangles, data regions, or groups within data regions to control the amount of information on each page.</span></span> <span data-ttu-id="07a59-104">L'ajout de sauts de page peut améliorer les performances des rapports publiés, car seuls les éléments sur chaque page doivent être traités pendant que vous visualisez le rapport.</span><span class="sxs-lookup"><span data-stu-id="07a59-104">Adding page breaks can improve the performance of published reports because only the items on each page have to be processed as you view the report.</span></span> <span data-ttu-id="07a59-105">Lorsque le rapport entier est une page unique, tous les éléments doivent être traités avant de pouvoir consulter le rapport.</span><span class="sxs-lookup"><span data-stu-id="07a59-105">When the whole report is a single page, all items must be processed before you can view the report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-page-break-to-a-data-region"></a><span data-ttu-id="07a59-106">Pour ajouter un saut de page à une région de données</span><span class="sxs-lookup"><span data-stu-id="07a59-106">To add a page break to a data region</span></span>  
  
1.  <span data-ttu-id="07a59-107">Dans l’aire de conception, cliquez avec le bouton droit sur la poignée d’angle de la région de données, puis cliquez sur **Propriétés du tableau matriciel**.</span><span class="sxs-lookup"><span data-stu-id="07a59-107">On the design surface, right-click the corner handle of the data region and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="07a59-108">Sous l'onglet **Général** , sous **Options de saut de page**, sélectionnez l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="07a59-108">On the **General** tab, under **Page break options**, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="07a59-109">**Insérer un saut de page avant**.</span><span class="sxs-lookup"><span data-stu-id="07a59-109">**Add a page break before**.</span></span> <span data-ttu-id="07a59-110">Sélectionnez cette option si vous souhaitez ajouter un saut de page avant le tableau.</span><span class="sxs-lookup"><span data-stu-id="07a59-110">Select this option when you want to add a page break before the table.</span></span>  
  
    -   <span data-ttu-id="07a59-111">**Insérer un saut de page après**.</span><span class="sxs-lookup"><span data-stu-id="07a59-111">**Add a page break after**.</span></span> <span data-ttu-id="07a59-112">Sélectionnez cette option si vous souhaitez ajouter un saut de page après le tableau.</span><span class="sxs-lookup"><span data-stu-id="07a59-112">Select this option when you want to add a page break after the table.</span></span>  
  
    -   <span data-ttu-id="07a59-113">**Faire tenir le tableau sur une page si possible**.</span><span class="sxs-lookup"><span data-stu-id="07a59-113">**Fit table on one page if possible**.</span></span> <span data-ttu-id="07a59-114">Sélectionnez cette option si vous souhaitez que les données restent sur une page.</span><span class="sxs-lookup"><span data-stu-id="07a59-114">Select this option when you want the data to stay on one page.</span></span>  
  
### <a name="to-add-a-page-break-to-a-rectangle"></a><span data-ttu-id="07a59-115">Pour ajouter un saut de page à un rectangle</span><span class="sxs-lookup"><span data-stu-id="07a59-115">To add a page break to a rectangle</span></span>  
  
1.  <span data-ttu-id="07a59-116">Sur l’aire de conception, cliquez avec le bouton droit sur le rectangle où vous souhaitez ajouter un saut de page, puis cliquez sur **Propriétés du rectangle**.</span><span class="sxs-lookup"><span data-stu-id="07a59-116">On the design surface, right-click the rectangle where you want to add a page break, and then click **Rectangle Properties**.</span></span>  
  
2.  <span data-ttu-id="07a59-117">Sous l'onglet **Général** , sous **Options de saut de page**, sélectionnez l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="07a59-117">On the **General** tab, under **Page break options**, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="07a59-118">**Insérer un saut de page avant**.</span><span class="sxs-lookup"><span data-stu-id="07a59-118">**Add a page break before**.</span></span> <span data-ttu-id="07a59-119">Sélectionnez cette option si vous souhaitez ajouter un saut de page avant le rectangle.</span><span class="sxs-lookup"><span data-stu-id="07a59-119">Select this option when you want to add a page break before the rectangle.</span></span>  
  
    -   <span data-ttu-id="07a59-120">**Insérer un saut de page après**.</span><span class="sxs-lookup"><span data-stu-id="07a59-120">**Add a page break after**.</span></span> <span data-ttu-id="07a59-121">Sélectionnez cette option si vous souhaitez ajouter un saut de page après le rectangle.</span><span class="sxs-lookup"><span data-stu-id="07a59-121">Select this option when you want to add a page break after the rectangle.</span></span>  
  
    -   <span data-ttu-id="07a59-122">**Omettre la bordure sur le saut de page**.</span><span class="sxs-lookup"><span data-stu-id="07a59-122">**Omit border on page break**.</span></span> <span data-ttu-id="07a59-123">Sélectionnez cette option si vous ne souhaitez pas de bordure sur le saut de page.</span><span class="sxs-lookup"><span data-stu-id="07a59-123">Select this option when you do not want a border on the page break.</span></span>  
  
    -   <span data-ttu-id="07a59-124">**Conserver le contenu sur la même page, si possible**.</span><span class="sxs-lookup"><span data-stu-id="07a59-124">**Keep contents together on a single page, if possible**.</span></span> <span data-ttu-id="07a59-125">Sélectionnez cette option lorsque vous souhaitez que le contenu à l'intérieur du rectangle reste sur une page.</span><span class="sxs-lookup"><span data-stu-id="07a59-125">Select this option when you want contents inside the rectangle to stay on one page.</span></span>  
  
### <a name="to-add-a-page-break-to-a-row-group-in-a-table-matrix-or-list"></a><span data-ttu-id="07a59-126">Pour ajouter un saut de page à un groupe de lignes dans un tableau, une matrice ou une liste</span><span class="sxs-lookup"><span data-stu-id="07a59-126">To add a page break to a row group in a table, matrix, or list</span></span>  
  
1.  <span data-ttu-id="07a59-127">Dans le volet Regroupement, cliquez avec le bouton droit sur un groupe de lignes, puis cliquez sur **Propriétés du groupe**.</span><span class="sxs-lookup"><span data-stu-id="07a59-127">In the Grouping pane, right-click a row group, and then click **Group Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="07a59-128">Les sauts de page définis sur les groupes de colonnes sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="07a59-128">Page breaks are ignored on column groups.</span></span>  
  
2.  <span data-ttu-id="07a59-129">Sous l'onglet **Sauts de page** , sélectionnez **Entre chaque instance d'un groupe** pour ajouter un saut de page entre chaque instance d'un groupe dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="07a59-129">On the **Page Breaks** tab, select **Between each instance of a group** to add a page break between each instance of a group in the table.</span></span>  
  
3.  <span data-ttu-id="07a59-130">Si vous le souhaitez, sélectionnez **Au début d'un groupe également** ou **À la fin d'un groupe également** pour spécifier qu'un saut de page soit ajouté au début ou à la fin d'un groupe dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="07a59-130">Optionally, select **Also at the start of a group** or **Also at the end of a group** to specify that a page break be added when a group starts or ends in the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07a59-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07a59-131">See Also</span></span>  
 <span data-ttu-id="07a59-132">[Pagination dans Reporting Services &#40;Générateur de rapports et SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="07a59-132">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="07a59-133">[Comportements de rendu &#40;Générateur de rapports et SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="07a59-133">[Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="07a59-134">En-têtes et pieds de page &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="07a59-134">Page Headers and Footers &#40;Report Builder and SSRS&#41;</span></span>](page-headers-and-footers-report-builder-and-ssrs.md)  
  
  
