---
title: Ajouter des graphiques sparkline et des barres de données (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0b297c2e-d48b-41b0-aabd-29680cdcdb05
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 55ec15354cdc78dd9678b9466f30d2fca0a73adc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601903"
---
# <a name="add-sparklines-and-data-bars-report-builder-and-ssrs"></a><span data-ttu-id="badba-102">Ajouter des graphiques sparkline et des barres de données (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="badba-102">Add Sparklines and Data Bars (Report Builder and SSRS)</span></span>
  <span data-ttu-id="badba-103">Les graphiques sparkline et les barres de données sont des graphiques de petite taille qui communiquent beaucoup d'informations avec peu de détails superflus.</span><span class="sxs-lookup"><span data-stu-id="badba-103">Sparklines and data bars are small, spare charts that convey a lot of information with little extraneous detail.</span></span> <span data-ttu-id="badba-104">Pour plus d’informations sur ces graphiques, consultez [Graphiques sparkline et barres de données &#40;Générateur de rapports et SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="badba-104">For more information about them, see [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="badba-105">Les graphiques sparkline et les barres de données sont généralement placés dans les cellules d'une table ou d'une matrice.</span><span class="sxs-lookup"><span data-stu-id="badba-105">Sparklines and data bars are most commonly placed in cells in a table or matrix.</span></span> <span data-ttu-id="badba-106">Les graphiques sparkline affichent habituellement une seule série chacun.</span><span class="sxs-lookup"><span data-stu-id="badba-106">Sparklines usually display only one series each.</span></span> <span data-ttu-id="badba-107">Les barres de données peuvent contenir un ou plusieurs points de données.</span><span class="sxs-lookup"><span data-stu-id="badba-107">Data bars can contain one or more data points.</span></span> <span data-ttu-id="badba-108">Les graphiques sparkline et barres de données tirent tous deux leur impact de la répétition des informations de série pour chaque ligne dans la table ou la matrice.</span><span class="sxs-lookup"><span data-stu-id="badba-108">Both sparklines and data bars derive their impact from repeating the series information for each row in the table or matrix.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-sparkline-or-data-bar-to-a-table-or-matrix"></a><span data-ttu-id="badba-109">Pour ajouter un graphique sparkline ou une barre de données à une table ou une matrice</span><span class="sxs-lookup"><span data-stu-id="badba-109">To add a sparkline or data bar to a table or matrix</span></span>  
  
1.  <span data-ttu-id="badba-110">Si vous ne l'avez pas encore fait, créez une table ou une matrice avec les données que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="badba-110">If you have not done so already, create a table or matrix with the data you want to display.</span></span> <span data-ttu-id="badba-111">Pour plus d’informations, consultez [Tables &#40;Générateur de rapports et SSRS&#41;](tables-report-builder-and-ssrs.md) ou [Matrices &#40;Générateur de rapports et SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="badba-111">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="badba-112">Insérez une colonne dans votre table ou matrice.</span><span class="sxs-lookup"><span data-stu-id="badba-112">Insert a column in your table or matrix.</span></span> <span data-ttu-id="badba-113">Pour plus d’informations, consultez [Insérer ou supprimer une colonne &#40;Générateur de rapports et SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="badba-113">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="badba-114">Sous l’onglet **Insérer** , cliquez sur **Graphique sparkline** ou sur **Barre de données**, puis cliquez dans une cellule de la nouvelle colonne.</span><span class="sxs-lookup"><span data-stu-id="badba-114">On the **Insert** tab, click **Sparkline** or **Data Bar**, and then click in a cell in the new column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="badba-115">Vous ne pouvez pas insérer de graphiques sparkline dans un groupe de détails dans une table.</span><span class="sxs-lookup"><span data-stu-id="badba-115">You cannot place sparklines in a detail group in a table.</span></span> <span data-ttu-id="badba-116">Ils doivent entrer dans une cellule associée à un groupe.</span><span class="sxs-lookup"><span data-stu-id="badba-116">They must go in a cell associated with a group.</span></span>  
  
4.  <span data-ttu-id="badba-117">Dans la boîte de dialogue **Changer le type de graphique sparkline/Changer le type de barre de données** , cliquez sur le type de graphique sparkline ou de barre de données de votre choix, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="badba-117">In the **Change Sparkline/Data Bar Type** dialog box, click the kind of sparkline or data bar you want, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="badba-118">Cliquez sur le graphique sparkline ou la barre de données.</span><span class="sxs-lookup"><span data-stu-id="badba-118">Click the sparkline or data bar.</span></span>  
  
     <span data-ttu-id="badba-119">Le volet **Données du graphique** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="badba-119">The **Chart Data** pane opens.</span></span>  
  
6.  <span data-ttu-id="badba-120">Dans la zone **Valeurs** , cliquez sur le signe plus ( **)** Ajouter des champs**+**, puis sur le champ dont vous voulez représenter les valeurs graphiquement.</span><span class="sxs-lookup"><span data-stu-id="badba-120">In the **Values** area, click the **Add Fields** plus sign (**+**), and then click the field whose values you want charted.</span></span>  
  
7.  <span data-ttu-id="badba-121">Dans la zone **Groupes de catégories** , cliquez sur le signe plus ( **)** Ajouter des champs**+**, puis sur le champ selon lequel vous voulez regrouper les valeurs.</span><span class="sxs-lookup"><span data-stu-id="badba-121">In the **Category Groups** area, click the **Add Fields** plus sign (**+**), and then click the field whose values you want to group by.</span></span>  
  
     <span data-ttu-id="badba-122">En général, pour les graphiques sparkline et les barres de données, vous n’ajoutez pas de champ à la zone **Groupes de séries** car vous voulez une seule série pour chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="badba-122">Typically for sparklines and data bars, you will not add a field to the **Series Group** area because you only want one series for each row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="badba-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="badba-123">See Also</span></span>  
 <span data-ttu-id="badba-124">[Graphiques &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="badba-124">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="badba-125">Aligner les données d’un graphique dans une table ou une matrice &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="badba-125">Align the Data in a Chart in a Table or Matrix &#40;Report Builder and SSRS&#41;</span></span>](align-the-data-in-a-chart-in-a-table-or-matrix-report-builder-and-ssrs.md)  
  
  
