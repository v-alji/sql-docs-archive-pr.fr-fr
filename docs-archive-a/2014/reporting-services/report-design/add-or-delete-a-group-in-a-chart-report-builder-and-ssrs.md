---
title: Ajouter ou supprimer un groupe dans une région de données (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0445b0ac-acae-4462-80fb-fe9735ac66db
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2ac558ccbd8855018877228b2b38debf769f1573
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707139"
---
# <a name="add-or-delete-a-group-in-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="e35cc-102">Ajouter ou supprimer un groupe dans un graphique (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="e35cc-102">Add or Delete a Group in a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e35cc-103">Cliquez dans la région de données de graphique pour afficher le volet **données du graphique** .</span><span class="sxs-lookup"><span data-stu-id="e35cc-103">Click in the chart data region to display the **Chart Data** pane.</span></span> <span data-ttu-id="e35cc-104">Créez des groupes en faisant glisser des champs de dataset vers les zones **Groupes de séries** et **Groupes de catégories** .</span><span class="sxs-lookup"><span data-stu-id="e35cc-104">Create groups by dragging dataset fields to the **Category Groups** and **Series Groups** areas.</span></span> <span data-ttu-id="e35cc-105">Pour ajouter des groupes imbriqués, ajoutez plusieurs champs à la zone.</span><span class="sxs-lookup"><span data-stu-id="e35cc-105">To add nested groups, add multiple fields to the area.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-parent-or-child-group-to-a-chart"></a><span data-ttu-id="e35cc-106">Pour ajouter un groupe parent ou enfant à un graphique</span><span class="sxs-lookup"><span data-stu-id="e35cc-106">To add a parent or child group to a chart</span></span>  
  
1.  <span data-ttu-id="e35cc-107">Sur l'aire de conception du rapport, cliquez n'importe où dans le graphique pour le sélectionner.</span><span class="sxs-lookup"><span data-stu-id="e35cc-107">On the report design surface, click anywhere in the chart to select it.</span></span> <span data-ttu-id="e35cc-108">Le volet **Données du graphique** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="e35cc-108">The **Chart Data** pane appears.</span></span>  
  
2.  <span data-ttu-id="e35cc-109">Faites glisser un champ de la fenêtre **Données du rapport** vers la zone **Groupes de catégories** ou **Groupes de séries** .</span><span class="sxs-lookup"><span data-stu-id="e35cc-109">Drag a field from the **Report Data** window to the **Category Groups** or **Series Groups** area.</span></span> <span data-ttu-id="e35cc-110">Pour ajouter un groupe parent, positionnez le curseur devant un groupe existant.</span><span class="sxs-lookup"><span data-stu-id="e35cc-110">To add a parent group, position the cursor in front of an existing group.</span></span> <span data-ttu-id="e35cc-111">Pour ajouter un groupe enfant, positionnez le curseur après un groupe existant.</span><span class="sxs-lookup"><span data-stu-id="e35cc-111">To add a child group, position the cursor after an existing group.</span></span>  
  
### <a name="to-edit-a-category-group-on-a-chart"></a><span data-ttu-id="e35cc-112">Pour modifier un groupe de catégories sur un graphique</span><span class="sxs-lookup"><span data-stu-id="e35cc-112">To edit a category group on a chart</span></span>  
  
1.  <span data-ttu-id="e35cc-113">Sur l'aire de conception du rapport, cliquez n'importe où dans le graphique pour le sélectionner.</span><span class="sxs-lookup"><span data-stu-id="e35cc-113">On the report design surface, click anywhere in the chart to select it.</span></span> <span data-ttu-id="e35cc-114">Le volet **Données du graphique** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="e35cc-114">The **Chart Data** pane appears.</span></span>  
  
2.  <span data-ttu-id="e35cc-115">Cliquez avec le bouton droit sur le groupe dans la zone **Groupes de catégories** , puis cliquez sur **Propriétés du groupe de catégories**.</span><span class="sxs-lookup"><span data-stu-id="e35cc-115">Right-click the group in the **Category Groups** area, and then click **Category Group Properties**.</span></span>  
  
3.  <span data-ttu-id="e35cc-116">Ajoutez ou supprimez des expressions de groupe, des filtres, des expressions de tri et des variables de groupe.</span><span class="sxs-lookup"><span data-stu-id="e35cc-116">Add or remove group expressions, filters, sort expressions, and group variables.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-edit-a-series-group-on-a-chart"></a><span data-ttu-id="e35cc-117">Pour modifier un groupe de séries sur un graphique</span><span class="sxs-lookup"><span data-stu-id="e35cc-117">To edit a series group on a chart</span></span>  
  
1.  <span data-ttu-id="e35cc-118">Sur l'aire de conception du rapport, cliquez n'importe où dans le graphique pour le sélectionner.</span><span class="sxs-lookup"><span data-stu-id="e35cc-118">On the report design surface, click anywhere in the chart to select it.</span></span> <span data-ttu-id="e35cc-119">Le volet **Données du graphique** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="e35cc-119">The **Chart Data** pane appears.</span></span>  
  
2.  <span data-ttu-id="e35cc-120">Cliquez avec le bouton droit sur le groupe dans la zone **Groupes de séries** , puis sélectionnez **Propriétés du groupe de séries**.</span><span class="sxs-lookup"><span data-stu-id="e35cc-120">Right-click the group in the **Series Groups** area, and then click **Series Group Properties**.</span></span>  
  
3.  <span data-ttu-id="e35cc-121">Ajoutez ou supprimez des expressions de groupe, des filtres, des expressions de tri et des variables de groupe.</span><span class="sxs-lookup"><span data-stu-id="e35cc-121">Add or remove group expressions, filters, sort expressions, and group variables.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-group-from-a-chart"></a><span data-ttu-id="e35cc-122">Pour supprimer un groupe d'un graphique</span><span class="sxs-lookup"><span data-stu-id="e35cc-122">To delete a group from a chart</span></span>  
  
1.  <span data-ttu-id="e35cc-123">Sur l'aire de conception du rapport, cliquez n'importe où dans le graphique pour le sélectionner.</span><span class="sxs-lookup"><span data-stu-id="e35cc-123">On the report design surface, click anywhere in the chart to select it.</span></span> <span data-ttu-id="e35cc-124">Le volet **Données du graphique** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="e35cc-124">The **Chart Data** pane appears.</span></span>  
  
2.  <span data-ttu-id="e35cc-125">Cliquez avec le bouton droit sur le groupe dans la zone **Groupes de catégories** ou **Groupes de séries** , puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="e35cc-125">Right-click the group in the **Category Groups** or **Series Groups** area, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e35cc-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e35cc-126">See Also</span></span>  
 [<span data-ttu-id="e35cc-127">Graphiques (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="e35cc-127">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
