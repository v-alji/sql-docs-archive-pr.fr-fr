---
title: Contourner la limitation des lignes Excel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a4c8700b-bef5-4440-a99c-bba5dcc46bfd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 128f65cf09833d23234da10bf7744c6ce30065ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602762"
---
# <a name="work-around-the-excel-row-limitation"></a><span data-ttu-id="ce1fb-102">Contournement de la limite d'Excel</span><span class="sxs-lookup"><span data-stu-id="ce1fb-102">Work Around the Excel Row Limitation</span></span>
  <span data-ttu-id="ce1fb-103">Cette rubrique explique comment contourner la limitation de ligne d'Excel 2003 lorsque vous exportez des rapports vers Excel.</span><span class="sxs-lookup"><span data-stu-id="ce1fb-103">This topic explains how to work around the Excel 2003 row limitation when you export reports to Excel.</span></span> <span data-ttu-id="ce1fb-104">Elle s'applique à un rapport qui ne contient qu'une seule table.</span><span class="sxs-lookup"><span data-stu-id="ce1fb-104">The workaround is for a report that contains only a table.</span></span>  
  
 <span data-ttu-id="ce1fb-105">Excel 2003 prend en charge 65 536 lignes au maximum par feuille.</span><span class="sxs-lookup"><span data-stu-id="ce1fb-105">Excel 2003 supports a maximum of 65,536 rows per worksheet.</span></span> <span data-ttu-id="ce1fb-106">Vous pouvez contourner cette limitation en forçant un saut de page explicite après un certain nombre de lignes.</span><span class="sxs-lookup"><span data-stu-id="ce1fb-106">You can work around this limitation by forcing an explicit page break after a certain number of rows.</span></span> <span data-ttu-id="ce1fb-107">Le convertisseur Excel crée une nouvelle feuille de calcul pour chaque saut de page explicite.</span><span class="sxs-lookup"><span data-stu-id="ce1fb-107">The Excel renderer creates a new worksheet for each explicit page break.</span></span>  
  
### <a name="to-create-an-explicit-page-break"></a><span data-ttu-id="ce1fb-108">Pour créer un saut de page explicite</span><span class="sxs-lookup"><span data-stu-id="ce1fb-108">To create an explicit page break</span></span>  
  
1.  <span data-ttu-id="ce1fb-109">Ouvrez un rapport dans [!INCLUDE[ss_dtbi](../../includes/ss-dtbi-md.md)] ou le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="ce1fb-109">Open the report in [!INCLUDE[ss_dtbi](../../includes/ss-dtbi-md.md)] or Report Manager.</span></span>  
  
2.  <span data-ttu-id="ce1fb-110">Cliquez avec le bouton droit sur la ligne de données dans la table, puis cliquez sur **Ajouter**le groupe  >  **parent** du groupe pour ajouter un groupe de tables externe.</span><span class="sxs-lookup"><span data-stu-id="ce1fb-110">Right click the Data row in the table, and then click **Add Group** > **Parent Group** to add an outer table group.</span></span>  
  
     <span data-ttu-id="ce1fb-111">![Sélectionner le groupe parent](../media/datarow-selectparentgroup.png "Sélectionner le groupe parent")</span><span class="sxs-lookup"><span data-stu-id="ce1fb-111">![Select the Parent Group](../media/datarow-selectparentgroup.png "Select the Parent Group")</span></span>  
  
3.  <span data-ttu-id="ce1fb-112">Entrez la formule suivante dans la zone d'expression **Regrouper par** , puis cliquez sur **OK** pour ajouter le groupe parent.</span><span class="sxs-lookup"><span data-stu-id="ce1fb-112">Enter the following formula in the **Group by** expression box, and then click **OK** to add the parent group.</span></span>  
  
     <span data-ttu-id="ce1fb-113">=Int((RowNumber(Nothing)-1)/65000)</span><span class="sxs-lookup"><span data-stu-id="ce1fb-113">=Int((RowNumber(Nothing)-1)/65000)</span></span>  
  
     <span data-ttu-id="ce1fb-114">La formule affecte un nombre à chaque ensemble de 65 000 lignes dans le dataset.</span><span class="sxs-lookup"><span data-stu-id="ce1fb-114">The formula assigns a number to each set of 65000 rows in the dataset.</span></span> <span data-ttu-id="ce1fb-115">Quand un saut de page est défini pour le groupe, l'expression insère un saut de page toutes les 65000 lignes.</span><span class="sxs-lookup"><span data-stu-id="ce1fb-115">When a page break is defined for the group, the expression results in a page break every 65000 rows.</span></span>  
  
     <span data-ttu-id="ce1fb-116">En ajoutant le groupe de tables externe, vous ajoutez une colonne de groupe au rapport.</span><span class="sxs-lookup"><span data-stu-id="ce1fb-116">Adding the outer table group adds a group column to the report.</span></span>  
  
4.  <span data-ttu-id="ce1fb-117">Supprimez la colonne de groupe en cliquant avec le bouton droit sur l’en-tête de la colonne, puis en cliquant sur **Supprimer des colonnes**, **Supprimer les colonnes uniquement**, et enfin sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce1fb-117">Delete the group column by right-clicking on the column header, clicking **Delete Columns**, selecting **Delete columns only**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="ce1fb-118">![Supprimer une colonne de groupe](../media/groupcolumn-delete-updated.png "Supprimer une colonne de groupe")</span><span class="sxs-lookup"><span data-stu-id="ce1fb-118">![Delete a group column](../media/groupcolumn-delete-updated.png "Delete a group column")</span></span>  
  
5.  <span data-ttu-id="ce1fb-119">Cliquez avec le bouton droit sur **Groupe 1** dans la section **Groupes de lignes** , puis cliquez sur **Propriétés du groupe**.</span><span class="sxs-lookup"><span data-stu-id="ce1fb-119">Right click **Group 1** in the **Row Groups** section, and then click **Group Properties**.</span></span>  
  
     <span data-ttu-id="ce1fb-120">![Afficher les propriétés de groupe](../media/groupproperties-updated.png "Afficher les propriétés de groupe")</span><span class="sxs-lookup"><span data-stu-id="ce1fb-120">![View group properties](../media/groupproperties-updated.png "View group properties")</span></span>  
  
6.  <span data-ttu-id="ce1fb-121">Dans la page **Tri** de la boîte de dialogue **Propriétés du groupe** , sélectionnez l'option de tri par défaut et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="ce1fb-121">On the **Sorting** page of the **Group Properties** dialog box, select the default sorting option and click **Delete**.</span></span>  
  
     <span data-ttu-id="ce1fb-122">![Supprimer le tri par défaut](../media/groupproperties-sorting-updated.png "Supprimer le tri par défaut")</span><span class="sxs-lookup"><span data-stu-id="ce1fb-122">![Delete default sorting](../media/groupproperties-sorting-updated.png "Delete default sorting")</span></span>  
  
7.  <span data-ttu-id="ce1fb-123">Dans la page **Sauts de page** , cliquez sur **Entre chaque instance d'un groupe** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce1fb-123">On the **Page Breaks** page, click **Between each instance of a group** and then click **OK**.</span></span>  
  
     <span data-ttu-id="ce1fb-124">![Définir les sauts de page](../media/groupproperties-pagebreaks-updated.png "Définir les sauts de page")</span><span class="sxs-lookup"><span data-stu-id="ce1fb-124">![Set page breaks](../media/groupproperties-pagebreaks-updated.png "Set page breaks")</span></span>  
  
8.  <span data-ttu-id="ce1fb-125">Enregistrez le rapport.</span><span class="sxs-lookup"><span data-stu-id="ce1fb-125">Save the report.</span></span> <span data-ttu-id="ce1fb-126">Lors de l'exportation vers Excel, plusieurs feuilles de calcul sont créées, chacune contenant un maximum de 65 000 lignes.</span><span class="sxs-lookup"><span data-stu-id="ce1fb-126">When you export it to Excel, it exports to multiple worksheets and each worksheet contains a maximum of 65000 rows.</span></span>  
  
  
