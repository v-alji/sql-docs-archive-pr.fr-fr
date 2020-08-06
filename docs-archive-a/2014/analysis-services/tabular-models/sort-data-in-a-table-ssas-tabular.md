---
title: Trier des données dans une table (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5fa6ad56-bf68-4aac-a226-52556173b7e2
author: minewiskan
ms.author: owend
ms.openlocfilehash: d9a6636c2c11fc571e8d4c1bcbc25c1e02d815fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694719"
---
# <a name="sort-data-in-a-table-ssas-tabular"></a><span data-ttu-id="9d8f1-102">Trier des données dans une table (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="9d8f1-102">Sort Data in a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="9d8f1-103">Vous pouvez trier des données en fonction du texte (de A à Z ou de Z à A) ou des nombres (du plus petit au plus grand ou du plus grand au plus petit) dans une ou plusieurs colonnes.</span><span class="sxs-lookup"><span data-stu-id="9d8f1-103">You can sort data by text (A to Z or Z to A) and numbers (smallest to largest or largest to smallest) in one or more columns.</span></span>  
  
### <a name="to-sort-the-data-in-a-table-based-on-a-text-column"></a><span data-ttu-id="9d8f1-104">Pour trier les données dans une table selon une colonne de texte</span><span class="sxs-lookup"><span data-stu-id="9d8f1-104">To sort the data in a table based on a text column</span></span>  
  
1.  <span data-ttu-id="9d8f1-105">Dans le générateur de modèles, sélectionnez une colonne de données alphanumériques, une plage de cellules dans une colonne ou assurez-vous que la cellule active se trouve dans une colonne de table qui contient des données alphanumériques, puis cliquez sur la flèche dans l'en-tête de la colonne d'après lequel effectuer le filtrage.</span><span class="sxs-lookup"><span data-stu-id="9d8f1-105">In the model designer, select a column of alphanumeric data, a range of cells in a column, or make sure that the active cell is in a table column that contains alphanumeric data, and then click the arrow in the header of the column that you want to filter by.</span></span>  
  
2.  <span data-ttu-id="9d8f1-106">Dans le menu Filtre automatique, effectuez l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d8f1-106">In the AutoFilter menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="9d8f1-107">Pour trier par ordre alphanumérique croissant, cliquez sur **Trier de A à Z**.</span><span class="sxs-lookup"><span data-stu-id="9d8f1-107">To sort in ascending alphanumeric order, click **Sort A to Z**.</span></span>  
  
    -   <span data-ttu-id="9d8f1-108">Pour trier par ordre alphanumérique décroissant, cliquez sur **Trier de Z à A**.</span><span class="sxs-lookup"><span data-stu-id="9d8f1-108">To sort in descending alphanumeric order, click **Sort Z to A**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9d8f1-109">Dans certains cas, les données importées à partir d'une autre application peuvent comporter des espaces de début.</span><span class="sxs-lookup"><span data-stu-id="9d8f1-109">In some cases, data imported from another application might have leading spaces inserted before data.</span></span> <span data-ttu-id="9d8f1-110">Vous devez supprimer ces espaces de début afin de pouvoir trier correctement les données.</span><span class="sxs-lookup"><span data-stu-id="9d8f1-110">You must remove the leading spaces in order to correctly sort the data.</span></span>  
  
### <a name="to-sort-the-data-in-a-table-based-on-a-numeric-column"></a><span data-ttu-id="9d8f1-111">Pour trier les données dans une table selon une colonne numérique</span><span class="sxs-lookup"><span data-stu-id="9d8f1-111">To sort the data in a table based on a numeric column</span></span>  
  
1.  <span data-ttu-id="9d8f1-112">Dans le générateur de modèles, sélectionnez une colonne de données alphanumériques, une plage de cellules dans une colonne ou assurez-vous que la cellule active se trouve dans une colonne de table qui contient des données alphanumériques, puis cliquez sur la flèche dans l'en-tête de la colonne d'après lequel effectuer le filtrage.</span><span class="sxs-lookup"><span data-stu-id="9d8f1-112">In the model designer, select a column of alphanumeric data, a range of cells in a column, or make sure that the active cell is in a table column that contains alphanumeric data, and then click the arrow in the header of the column that you want to filter by.</span></span>  
  
2.  <span data-ttu-id="9d8f1-113">Dans le menu Filtre automatique, effectuez l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d8f1-113">In the AutoFilter menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="9d8f1-114">Pour trier par ordre croissant, cliquez sur **Trier du plus petit au plus grand**.</span><span class="sxs-lookup"><span data-stu-id="9d8f1-114">To sort from low numbers to high numbers, click **Sort Smallest to Largest**.</span></span>  
  
    -   <span data-ttu-id="9d8f1-115">Pour trier par ordre décroissant, cliquez sur **Trier du plus grand au plus petit**.</span><span class="sxs-lookup"><span data-stu-id="9d8f1-115">To sort from high numbers to low numbers, click **Sort Largest to Smallest**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9d8f1-116">Si les résultats ne sont pas ce attendus, il se peut que la colonne contienne des nombres stockés sous forme de texte plutôt que sous forme de nombres.</span><span class="sxs-lookup"><span data-stu-id="9d8f1-116">If the results are not what you expected, the column might contain numbers stored as text and not as numbers.</span></span> <span data-ttu-id="9d8f1-117">Par exemple, les nombres négatifs importés à partir de certains logiciels de comptabilité ou un nombre entré avec un signe ' (apostrophe) de début sont stockés sous forme de texte.</span><span class="sxs-lookup"><span data-stu-id="9d8f1-117">For example, negative numbers imported from some accounting systems, or a number entered with a leading ' (apostrophe), are stored as text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d8f1-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9d8f1-118">See Also</span></span>  
 <span data-ttu-id="9d8f1-119">[Filtrer et trier des données &#40;la&#41;tabulaire SSAS](../filter-and-sort-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="9d8f1-119">[Filter and Sort Data &#40;SSAS Tabular&#41;](../filter-and-sort-data-ssas-tabular.md) </span></span>  
 <span data-ttu-id="9d8f1-120">[Perspectives &#40;&#41;tabulaire SSAS](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="9d8f1-120">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="9d8f1-121">Rôles &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="9d8f1-121">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  
