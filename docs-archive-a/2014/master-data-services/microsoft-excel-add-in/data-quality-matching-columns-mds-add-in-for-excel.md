---
title: Colonnes de mise en correspondance de la qualité des données (Complément MDS pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: f683fdc6-0d4c-4793-8143-567616cb2094
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 939ec9727cc81ce3b206b8bc7ca3ed8dd62c3877
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600112"
---
# <a name="data-quality-matching-columns-mds-add-in-for-excel"></a><span data-ttu-id="b8348-102">Colonnes de mise en correspondance de la qualité des données (Complément MDS pour Excel)</span><span class="sxs-lookup"><span data-stu-id="b8348-102">Data Quality Matching Columns (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="b8348-103">Dans [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] , après avoir mis en correspondance des données, dans le groupe **qualité des données** du ruban, vous pouvez cliquer sur **afficher les détails** pour afficher les colonnes qui fournissent des détails correspondants.</span><span class="sxs-lookup"><span data-stu-id="b8348-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], after you match data, in the **Data Quality** group on the ribbon, you can click **Show Details** to display columns that provide matching details.</span></span>  
  
 <span data-ttu-id="b8348-104">Le tableau suivant présente les colonnes affichées lors de la mise en correspondance des données.</span><span class="sxs-lookup"><span data-stu-id="b8348-104">The following table shows the columns that are displayed when matching data.</span></span>  
  
|<span data-ttu-id="b8348-105">Nom</span><span class="sxs-lookup"><span data-stu-id="b8348-105">Name</span></span>|<span data-ttu-id="b8348-106">Description</span><span class="sxs-lookup"><span data-stu-id="b8348-106">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="b8348-107">**CLUSTER_ID**</span><span class="sxs-lookup"><span data-stu-id="b8348-107">**CLUSTER_ID**</span></span>|<span data-ttu-id="b8348-108">Identificateur unique utilisé pour regrouper les enregistrements similaires.</span><span class="sxs-lookup"><span data-stu-id="b8348-108">A unique identifier used to group similar records.</span></span> <span data-ttu-id="b8348-109">Toutes les lignes similaires ont le même **CLUSTER_ID**.</span><span class="sxs-lookup"><span data-stu-id="b8348-109">All rows that are similar have the same **CLUSTER_ID**.</span></span> <span data-ttu-id="b8348-110">Si aucun **CLUSTER_ID** n’est affiché pour une ligne, aucun enregistrement similaire n’a été trouvé.</span><span class="sxs-lookup"><span data-stu-id="b8348-110">If no **CLUSTER_ID** is displayed for a row, then no similar records were found.</span></span>|  
|<span data-ttu-id="b8348-111">**RECORD_ID**</span><span class="sxs-lookup"><span data-stu-id="b8348-111">**RECORD_ID**</span></span>|<span data-ttu-id="b8348-112">Identificateur unique utilisé pour identifier les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="b8348-112">A unique identifier used to identify records.</span></span> <span data-ttu-id="b8348-113">Similaire à la valeur Code stockée dans le référentiel MDS, il s'agit d'une valeur utilisée pour identifier un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="b8348-113">Similar to the Code value stored in the MDS repository, it is a value used to identify a record.</span></span> <span data-ttu-id="b8348-114">Il est généré automatiquement chaque fois que la mise en correspondance a lieu.</span><span class="sxs-lookup"><span data-stu-id="b8348-114">It is generated automatically each time matching takes place.</span></span>|  
|<span data-ttu-id="b8348-115">**PIVOT_MARK**</span><span class="sxs-lookup"><span data-stu-id="b8348-115">**PIVOT_MARK**</span></span>|<span data-ttu-id="b8348-116">Enregistrement arbitraire auxquels les autres enregistrements sont comparés ; il n'a pas de valeur de score.</span><span class="sxs-lookup"><span data-stu-id="b8348-116">An arbitrary record that other records are compared to; it does not have a score value.</span></span>|  
|<span data-ttu-id="b8348-117">**ENJEU**</span><span class="sxs-lookup"><span data-stu-id="b8348-117">**SCORE**</span></span>|<span data-ttu-id="b8348-118">Représente le degré de similitude des enregistrements du groupe par rapport à l'enregistrement pivot.</span><span class="sxs-lookup"><span data-stu-id="b8348-118">Represents how similar the records in the group are to the pivot record.</span></span> <span data-ttu-id="b8348-119">Ce score est déterminé par DQS.</span><span class="sxs-lookup"><span data-stu-id="b8348-119">This score is determined by DQS.</span></span> <span data-ttu-id="b8348-120">Si aucun score n'est affiché, l'enregistrement est le tableau croisé dynamique d'autres enregistrements, ou bien aucune correspondance n'a été trouvée.</span><span class="sxs-lookup"><span data-stu-id="b8348-120">If no score is displayed, either the record is the pivot for other records, or no matches were found.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b8348-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b8348-121">See Also</span></span>  
 <span data-ttu-id="b8348-122">[Correspondance de la qualité des données dans le Complément MDS pour Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="b8348-122">[Data Quality Matching in the MDS Add-in for Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span></span>  
 <span data-ttu-id="b8348-123">[Faire correspondre les données similaires &#40;Complément MDS pour Excel&#41;](match-similar-data-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="b8348-123">[Match Similar Data &#40;MDS Add-in for Excel&#41;](match-similar-data-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="b8348-124">Correspondance de données</span><span class="sxs-lookup"><span data-stu-id="b8348-124">Data Matching</span></span>](../../data-quality-services/data-matching.md)  
  
  
