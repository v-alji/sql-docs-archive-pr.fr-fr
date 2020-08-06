---
title: Boîte de dialogue affecter une conception d’agrégation (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.copyaggregationdesign.f1
ms.assetid: 50c26cb1-c294-4f17-8b9e-435fdbd4806d
author: minewiskan
ms.author: owend
ms.openlocfilehash: dfc4f7a0847373360a79ddda366ad7aa3f02c5de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602668"
---
# <a name="assign-aggregation-design-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="6d5b0-102">Boîte de dialogue Affecter une conception d'agrégation (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="6d5b0-102">Assign Aggregation Design Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="6d5b0-103">Utilisez la boîte de dialogue **Affecter une conception d'agrégation** dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pour affecter des conceptions d'agrégation à une ou plusieurs partitions de destination.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-103">Use the **Assign Aggregation Design** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to assign aggregation designs to one or more destination partitions.</span></span> <span data-ttu-id="6d5b0-104">Vous pouvez afficher la boîte de dialogue **Affecter une conception d’agrégation** en cliquant avec le bouton droit sur une partition ou une conception d’agrégation dans **l’Explorateur d’objets** , puis en sélectionnant **Affecter une conception d’agrégation**.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-104">You can display the **Assign Aggregation Design** dialog box by right-clicking a partition or aggregation design in **Object Explorer** and selecting **Assign Aggregation Design**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6d5b0-105">Options</span><span class="sxs-lookup"><span data-stu-id="6d5b0-105">Options</span></span>  
  
|<span data-ttu-id="6d5b0-106">Terme</span><span class="sxs-lookup"><span data-stu-id="6d5b0-106">Term</span></span>|<span data-ttu-id="6d5b0-107">Définition</span><span class="sxs-lookup"><span data-stu-id="6d5b0-107">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="6d5b0-108">**Conceptions d'agrégation**</span><span class="sxs-lookup"><span data-stu-id="6d5b0-108">**Aggregation designs**</span></span>|<span data-ttu-id="6d5b0-109">Sélectionnez une conception d'agrégation à affecter à une ou plusieurs partitions de destination.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-109">Select an aggregation design to assign to one or more destination partitions.</span></span>|  
|<span data-ttu-id="6d5b0-110">**Partitions de destination**</span><span class="sxs-lookup"><span data-stu-id="6d5b0-110">**Destination partitions**</span></span>|<span data-ttu-id="6d5b0-111">Sélectionnez les partitions auxquelles affecter la conception d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-111">Select the partitions to which to assign the aggregation design.</span></span> <span data-ttu-id="6d5b0-112">La grille suivante permet de définir les partitions de destination :</span><span class="sxs-lookup"><span data-stu-id="6d5b0-112">The following grid is used to specify destination partitions:</span></span><br /><br /> <span data-ttu-id="6d5b0-113">\<check box>: Activez ou désactivez la case à cocher dans l’en-tête de colonne pour inclure ou exclure toutes les partitions listées comme partitions de destination.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-113">\<check box>: Select or clear the check box in the column header to include or exclude all listed partitions as destination partitions.</span></span> <span data-ttu-id="6d5b0-114">Activez ou désactivez la case à cocher située en regard d'une partition pour inclure ou exclure cette partition en tant que partition de destination.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-114">Select or clear a check box next to a partition to include or exclude that partition as a destination partition.</span></span><br /><br /> <span data-ttu-id="6d5b0-115">**Partition**: affiche le nom de la partition.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-115">**Partition**: Displays the name of the partition.</span></span><br /><br /> <span data-ttu-id="6d5b0-116">**Source**: affiche la table ou la requête source de la partition.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-116">**Source**: Displays the source table or query for the partition.</span></span><br /><br /> <span data-ttu-id="6d5b0-117">**Conception d’agrégation**: affiche le nom de la conception d’agrégation existante pour la partition.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-117">**Aggregation Design**: Displays the name of the existing aggregation design for the partition.</span></span>|  
|<span data-ttu-id="6d5b0-118">**Masquer les partitions avec des conceptions d'agrégation**</span><span class="sxs-lookup"><span data-stu-id="6d5b0-118">**Hide partitions with aggregation designs**</span></span>|<span data-ttu-id="6d5b0-119">Sélectionnez pour afficher uniquement les partitions auxquelles aucune conception d'agrégation n'a été affectée.</span><span class="sxs-lookup"><span data-stu-id="6d5b0-119">Select to show only the partitions that do not have aggregation designs assigned to them.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6d5b0-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6d5b0-120">See Also</span></span>  
 [<span data-ttu-id="6d5b0-121">Agrégations et conceptions d'agrégation</span><span class="sxs-lookup"><span data-stu-id="6d5b0-121">Aggregations and Aggregation Designs</span></span>](multidimensional-models-olap-logical-cube-objects/aggregations-and-aggregation-designs.md)  
  
  
