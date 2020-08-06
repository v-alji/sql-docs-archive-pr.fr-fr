---
title: Détails de la liaison de table (boîte de dialogue source de partition) (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.partitions.partitiontableselection.f1
ms.assetid: 67d05389-81ae-4a6b-947b-986d37ec72b1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 10845e18a2b7c74a8ed3aeec42f710b9706dc94a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604168"
---
# <a name="table-binding-detail-partition-source-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="714e8-102">Détails de la liaison de table (boîte de dialogue Source de partition) (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="714e8-102">Table Binding Detail (Partition Source Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="714e8-103">Utilisez l'option **Liaison de table** de la boîte de dialogue **Source de la partition** pour définir la table de faits qui fournit les données de la partition.</span><span class="sxs-lookup"><span data-stu-id="714e8-103">Use the **Table Binding** option in the **Partition Source** dialog box to specify the fact table that provides the data for the partition.</span></span> <span data-ttu-id="714e8-104">Vous pouvez afficher ce volet en sélectionnant **Liaison de table** dans l'option **Type de liaison** de la boîte de dialogue **Source de la partition** .</span><span class="sxs-lookup"><span data-stu-id="714e8-104">You can display this pane by selecting **Table Binding** from the **Binding type** option in the **Partition Source** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="714e8-105">Options</span><span class="sxs-lookup"><span data-stu-id="714e8-105">Options</span></span>  
 <span data-ttu-id="714e8-106">**Groupe de mesures**</span><span class="sxs-lookup"><span data-stu-id="714e8-106">**Measure group**</span></span>  
 <span data-ttu-id="714e8-107">Affiche le groupe de mesures de la partition.</span><span class="sxs-lookup"><span data-stu-id="714e8-107">Displays the measure group for this partition.</span></span>  
  
 <span data-ttu-id="714e8-108">**Chercher dans**</span><span class="sxs-lookup"><span data-stu-id="714e8-108">**Look in**</span></span>  
 <span data-ttu-id="714e8-109">Permet d'indiquer la source de données ou la vue de source de données contenant les tables source destinées à cette partition.</span><span class="sxs-lookup"><span data-stu-id="714e8-109">Select the data source or data source view that contains the source tables for this partition.</span></span> <span data-ttu-id="714e8-110">La vue de source de vue de données utilisée par le groupe de mesures sélectionné est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="714e8-110">The data source view used by the selected measure group is selected by default.</span></span>  
  
 <span data-ttu-id="714e8-111">**Filtrer les tables**</span><span class="sxs-lookup"><span data-stu-id="714e8-111">**Filter tables**</span></span>  
 <span data-ttu-id="714e8-112">Permet d’entrer la chaîne utilisée pour restreindre les tables affichées dans **Tables disponibles**d’après leur nom.</span><span class="sxs-lookup"><span data-stu-id="714e8-112">Type the string used to restrict, by table name, the tables displayed in **Available tables**.</span></span>  
  
 <span data-ttu-id="714e8-113">**Rechercher des tables**</span><span class="sxs-lookup"><span data-stu-id="714e8-113">**Find tables**</span></span>  
 <span data-ttu-id="714e8-114">Permet d’actualiser la liste des tables répertoriées dans **Tables disponibles**, et d’affiner la liste d’après les critères d’une chaîne indiquée dans **Filtrer les tables**, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="714e8-114">Select to refresh the list of tables in **Available tables**, further restricting the list if a string was specified in **Filter tables**.</span></span>  
  
 <span data-ttu-id="714e8-115">**Tables disponibles**</span><span class="sxs-lookup"><span data-stu-id="714e8-115">**Available tables**</span></span>  
 <span data-ttu-id="714e8-116">Cliquez pour sélectionner la table à utiliser comme table source pour la partition.</span><span class="sxs-lookup"><span data-stu-id="714e8-116">Click to select the table to use as a source table for the partition.</span></span>  
  
 <span data-ttu-id="714e8-117">Si aucun filtre n'est défini dans **Filtrer les tables**, toutes les tables dans la source de données ou la vue de source de données définie dans **Rechercher dans** , qui sont similaires, en terme de structure, à la table des faits utilisée par le groupe de mesures défini dans **Groupe de mesures** , sont affichées.</span><span class="sxs-lookup"><span data-stu-id="714e8-117">If no filter is specified in **Filter tables**, all tables in the data source or data source view specified in **Look in** that are similar in structure to the fact table used by the measure group specified in **Measure group** are listed.</span></span>  
  
 <span data-ttu-id="714e8-118">Si un filtre est défini dans **Filtrer les tables**, la liste est encore limitée en comparant le filtre aux noms de tables qui répondent aux critères ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="714e8-118">If a filter is specified in **Filter tables**, the list is further restricted by comparing the filter against the table names that meet the above criteria.</span></span> <span data-ttu-id="714e8-119">Ainsi, seules les tables contenant la chaîne spécifiée dans **Filtrer les tables** sont affichées.</span><span class="sxs-lookup"><span data-stu-id="714e8-119">Only those tables that contain the string specified in **Filter tables** are displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="714e8-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="714e8-120">See Also</span></span>  
 [<span data-ttu-id="714e8-121">Boîte de dialogue source de partition &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="714e8-121">Partition Source Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](partition-source-dialog-box-analysis-services-multidimensional-data.md)  
  
  
