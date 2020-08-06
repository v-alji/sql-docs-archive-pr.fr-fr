---
title: Ajouter un groupe de détails (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5ef8efba-6d48-4aeb-a3b9-a02ba5a44614
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 24b1f6af1aaf336a69a0068636ced60c364e556d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605221"
---
# <a name="add-a-details-group-report-builder-and-ssrs"></a><span data-ttu-id="95d44-102">Ajouter un groupe de détails (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="95d44-102">Add a Details Group (Report Builder and SSRS)</span></span>
  <span data-ttu-id="95d44-103">Les données de détail d'un dataset de rapport sont spécifiées en tant que groupe sans expression de groupe.</span><span class="sxs-lookup"><span data-stu-id="95d44-103">The detail data from a report dataset is specified as a group with no group expression.</span></span> <span data-ttu-id="95d44-104">Ajoutez un groupe de détails à une région de données de tableau matriciel existante lorsque vous souhaitez afficher les données de détail d'une matrice, rajouter des données de détail que vous avez supprimées d'une table ou d'une liste ou ajouter d'autres groupes de détails.</span><span class="sxs-lookup"><span data-stu-id="95d44-104">Add a detail group to an existing tablix data region when you want to display the detail data for a matrix, add back detail data that you have deleted from a table or list, or to add additional detail groups.</span></span> <span data-ttu-id="95d44-105">Pour plus d’informations sur les groupes, consultez [Fonctionnement des groupes &#40;Générateur de rapports et SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="95d44-105">For more information about groups, see [Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-details-group-to-a-tablix-data-region"></a><span data-ttu-id="95d44-106">Pour ajouter un groupe de détails à une région de données de tableau matriciel</span><span class="sxs-lookup"><span data-stu-id="95d44-106">To add a details group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="95d44-107">Sur l'aire de conception, cliquez n'importe où dans une région de données de tableau matriciel pour la sélectionner.</span><span class="sxs-lookup"><span data-stu-id="95d44-107">On the design surface, click anywhere in a tablix data region to select it.</span></span> <span data-ttu-id="95d44-108">Le volet Regroupement affiche les groupes de lignes et de colonnes de la région de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="95d44-108">The Grouping pane displays the row and column groups for the selected data region.</span></span>  
  
2.  <span data-ttu-id="95d44-109">Dans le volet Regroupement, cliquez avec le bouton droit sur un groupe correspondant à un groupe enfant des plus profonds.</span><span class="sxs-lookup"><span data-stu-id="95d44-109">In the Grouping pane, right-click a group that is an innermost child group.</span></span> <span data-ttu-id="95d44-110">Cliquez sur **Ajouter un groupe**, puis sur **Groupe enfant**.</span><span class="sxs-lookup"><span data-stu-id="95d44-110">Click **Add Group**, and then click **Child Group**.</span></span> <span data-ttu-id="95d44-111">La boîte de dialogue **Groupe de tableaux matriciels** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="95d44-111">The **Tablix Group** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="95d44-112">Dans **Expression Groupe**, laissez l'expression vide.</span><span class="sxs-lookup"><span data-stu-id="95d44-112">In **Group expression**, leave the expression blank.</span></span> <span data-ttu-id="95d44-113">Un groupe de détails ne possède aucune expression.</span><span class="sxs-lookup"><span data-stu-id="95d44-113">A details group has no expression.</span></span>  
  
4.  <span data-ttu-id="95d44-114">Sélectionnez **Afficher les données de détail**.</span><span class="sxs-lookup"><span data-stu-id="95d44-114">Select **Show detail data**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="95d44-115">Un nouveau groupe de détails est ajouté en tant que groupe enfant dans le volet Regroupement et le descripteur de ligne du groupe que vous avez sélectionné au cours de l'étape 1 affiche l'icône du groupe de détails.</span><span class="sxs-lookup"><span data-stu-id="95d44-115">A new details group is added as a child group in the Grouping pane, and the row handle for the group you selected in step 1 displays the details group icon.</span></span> <span data-ttu-id="95d44-116">Pour plus d’informations sur les descripteurs, consultez [Cellules, lignes et colonnes de région de données de tableau matriciel &#40;Générateur de rapports et SSRS&#41;](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="95d44-116">For more information about handles, see [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95d44-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="95d44-117">See Also</span></span>  
 <span data-ttu-id="95d44-118">[Ajouter ou supprimer un groupe dans une région de données &#40;Générateur de rapports et SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="95d44-118">[Add or Delete a Group in a Data Region &#40;Report Builder and SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="95d44-119">[Fonctionnement des groupes &#40;Générateur de rapports et SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="95d44-119">[Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="95d44-120">[Région de données de tableau matriciel &#40;Générateur de rapports et SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="95d44-120">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="95d44-121">[Tables &#40;Générateur de rapports et SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="95d44-121">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="95d44-122">[Matrices &#40;Générateur de rapports et SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="95d44-122">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="95d44-123">[Répertorie &#40;Générateur de rapports et SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="95d44-123">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="95d44-124">Tables, matrices et listes &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="95d44-124">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
