---
title: Combiner des données (Complément MDS pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: a867dc15-5a0d-457c-8304-ac323bcf9377
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bc2d5bffb6d7a12164a8643e9a790b32538f8979
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698387"
---
# <a name="combine-data-mds-add-in-for-excel"></a><span data-ttu-id="ba227-102">Combiner des données (Complément MDS pour Excel)</span><span class="sxs-lookup"><span data-stu-id="ba227-102">Combine Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="ba227-103">Dans [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], combinez les données de deux feuilles de calcul lorsque vous souhaitez comparer les données avant la publication.</span><span class="sxs-lookup"><span data-stu-id="ba227-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], combine data from two worksheets when you want to compare data before publishing.</span></span> <span data-ttu-id="ba227-104">Dans cette procédure, vous combinez les données de deux feuilles de calcul en une seule.</span><span class="sxs-lookup"><span data-stu-id="ba227-104">In this procedure, you combine data from a two worksheets into one.</span></span> <span data-ttu-id="ba227-105">Vous pouvez ensuite réaliser d'autres comparaisons et déterminer les données, le cas échéant, à publier dans le référentiel MDS.</span><span class="sxs-lookup"><span data-stu-id="ba227-105">Then you can perform further comparisons and determine which data, if any, to publish to the MDS repository.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ba227-106">Prérequis</span><span class="sxs-lookup"><span data-stu-id="ba227-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="ba227-107">Vous devez disposer d'une feuille de calcul qui contient des données gérées par MDS.</span><span class="sxs-lookup"><span data-stu-id="ba227-107">You must have a worksheet that contains MDS-managed data.</span></span> <span data-ttu-id="ba227-108">Pour plus d’informations, consultez [charger des données à partir de MDS dans Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ba227-108">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="ba227-109">Vous devez disposer d'une feuille de calcul qui contient les données que vous souhaitez combiner avec les données managées MDS.</span><span class="sxs-lookup"><span data-stu-id="ba227-109">You must have a worksheet that contains data you want to combine with MDS-managed data.</span></span> <span data-ttu-id="ba227-110">Cette feuille doit avoir une ligne d'en-tête.</span><span class="sxs-lookup"><span data-stu-id="ba227-110">This sheet must have a header row.</span></span>  
  
### <a name="to-combine-non-managed-data-into-an-mds-managed-sheet"></a><span data-ttu-id="ba227-111">Pour combiner des données non managées dans une feuille managée MDS</span><span class="sxs-lookup"><span data-stu-id="ba227-111">To combine non-managed data into an MDS-managed sheet</span></span>  
  
1.  <span data-ttu-id="ba227-112">Sur la feuille qui contient les données managées MDS, dans le groupe **Publier et valider** , cliquez sur **Combiner des données**.</span><span class="sxs-lookup"><span data-stu-id="ba227-112">On the sheet that contains MDS-managed data, in the **Publish and Validate** group, click **Combine Data**.</span></span>  
  
2.  <span data-ttu-id="ba227-113">Dans la boîte de dialogue **Combiner des données** , en regard de la zone de texte **Plage à combiner avec les données MDS** , cliquez sur l'icône.</span><span class="sxs-lookup"><span data-stu-id="ba227-113">In the **Combine Data** dialog box, next to the **Range to combine with MDS data** text box, click the icon.</span></span> <span data-ttu-id="ba227-114">La boîte de dialogue se réduit.</span><span class="sxs-lookup"><span data-stu-id="ba227-114">The dialog box contracts.</span></span>  
  
3.  <span data-ttu-id="ba227-115">Cliquez sur la feuille contenant les données que vous souhaitez combiner.</span><span class="sxs-lookup"><span data-stu-id="ba227-115">Click the sheet that contains the data you want to combine.</span></span>  
  
4.  <span data-ttu-id="ba227-116">Mettez en surbrillance toutes les cellules de la feuille que vous souhaitez combiner, notamment la ligne d'en-tête.</span><span class="sxs-lookup"><span data-stu-id="ba227-116">Highlight all cells on the sheet that you want to combine, including the header row.</span></span>  
  
5.  <span data-ttu-id="ba227-117">Dans la boîte de dialogue **Combiner des données** , cliquez sur l'icône.</span><span class="sxs-lookup"><span data-stu-id="ba227-117">In the **Combine Data** dialog box, click the icon.</span></span> <span data-ttu-id="ba227-118">La boîte de dialogue se développe.</span><span class="sxs-lookup"><span data-stu-id="ba227-118">The dialog box expands.</span></span>  
  
6.  <span data-ttu-id="ba227-119">Pour une colonne répertoriée pour l'entité MDS, sélectionnez une colonne sous **Colonne correspondante**.</span><span class="sxs-lookup"><span data-stu-id="ba227-119">For a column listed for the MDS entity, select a column under **Corresponding Column**.</span></span> <span data-ttu-id="ba227-120">Toutes les colonnes MDS n'ont pas besoin de colonnes correspondantes.</span><span class="sxs-lookup"><span data-stu-id="ba227-120">All MDS columns do not need corresponding columns.</span></span>  
  
7.  <span data-ttu-id="ba227-121">Cliquez sur **Combiner**.</span><span class="sxs-lookup"><span data-stu-id="ba227-121">Click **Combine**.</span></span> <span data-ttu-id="ba227-122">Une colonne **SOURCE** s'affiche, laquelle indique si les données proviennent de MDS ou d'une source externe.</span><span class="sxs-lookup"><span data-stu-id="ba227-122">A **SOURCE** column is displayed, indicating whether the data is from MDS or an external source.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ba227-123">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="ba227-123">Next Steps</span></span>  
  
-   <span data-ttu-id="ba227-124">Pour rechercher des similitudes entre les données managées MDS et les données externes, consultez [Mettre en correspondance les données similaires &#40;Complément MDS pour Excel&#41;](match-similar-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="ba227-124">To find similarities between the MDS-managed and external data, see [Match Similar Data &#40;MDS Add-in for Excel&#41;](match-similar-data-mds-add-in-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba227-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ba227-125">See Also</span></span>  
 <span data-ttu-id="ba227-126">[Chargement de données &#40;Complément MDS pour Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="ba227-126">[Loading Data &#40;MDS Add-in for Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="ba227-127">Mise en correspondance de la qualité des données dans le complément MDS pour Excel</span><span class="sxs-lookup"><span data-stu-id="ba227-127">Data Quality Matching in the MDS Add-in for Excel</span></span>](data-quality-matching-in-the-mds-add-in-for-excel.md)  
  
  
