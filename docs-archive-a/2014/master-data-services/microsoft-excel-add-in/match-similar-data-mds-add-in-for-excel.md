---
title: Mettre en correspondance les données similaires (Complément MDS pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: f6fd6fc1-3569-42a5-b6cb-87a921c88f3b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 70dea36de557c6fda909d06ee19ff8fa2ed6908d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699881"
---
# <a name="match-similar-data-mds-add-in-for-excel"></a><span data-ttu-id="99ef0-102">Mettre en correspondance les données similaires (Complément MDS pour Excel)</span><span class="sxs-lookup"><span data-stu-id="99ef0-102">Match Similar Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="99ef0-103">Dans le [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], utilisez la fonctionnalité Data Quality Services (DQS) pour rechercher des similitudes dans vos données.</span><span class="sxs-lookup"><span data-stu-id="99ef0-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use Data Quality Services (DQS) functionality to find similarities in your data.</span></span>  
  
 <span data-ttu-id="99ef0-104">Pour effectuer cette procédure, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="99ef0-104">To perform this procedure, you can:</span></span>  
  
-   <span data-ttu-id="99ef0-105">Utiliser la base de connaissances Data Quality Services par défaut, ou</span><span class="sxs-lookup"><span data-stu-id="99ef0-105">Use the default Data Quality Services knowledge base, or</span></span>  
  
-   <span data-ttu-id="99ef0-106">Créer votre propre base de connaissances DQS personnalisée et la stratégie correspondante.</span><span class="sxs-lookup"><span data-stu-id="99ef0-106">Create your own custom DQS knowledge base and matching policy.</span></span> <span data-ttu-id="99ef0-107">Pour plus d’informations, consultez [Créer une stratégie de correspondance](../../data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="99ef0-107">For more information, see [Create a Matching Policy](../../data-quality-services/create-a-matching-policy.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="99ef0-108">Prérequis</span><span class="sxs-lookup"><span data-stu-id="99ef0-108">Prerequisites</span></span>  
  
-   <span data-ttu-id="99ef0-109">Vous devez disposer d'une feuille de calcul qui contient des données gérées par MDS.</span><span class="sxs-lookup"><span data-stu-id="99ef0-109">You must have a worksheet that contains MDS-managed data.</span></span> <span data-ttu-id="99ef0-110">Pour plus d’informations, consultez [charger des données à partir de MDS dans Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="99ef0-110">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="99ef0-111">facultatif.</span><span class="sxs-lookup"><span data-stu-id="99ef0-111">Optional.</span></span> <span data-ttu-id="99ef0-112">Vous pouvez combiner d'autres données avec les données gérées par MDS avant de rechercher des similitudes.</span><span class="sxs-lookup"><span data-stu-id="99ef0-112">You can combine other data with the MDS-managed data before checking for similarities.</span></span> <span data-ttu-id="99ef0-113">Pour plus d’informations, consultez [Combiner des données &#40;Complément MDS pour Excel&#41;](combine-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="99ef0-113">For more information, see [Combine Data &#40;MDS Add-in for Excel&#41;](combine-data-mds-add-in-for-excel.md).</span></span>  
  
### <a name="to-find-similarities-by-using-the-default-knowledge-base"></a><span data-ttu-id="99ef0-114">Pour rechercher des similitudes à l'aide de la base de connaissances par défaut</span><span class="sxs-lookup"><span data-stu-id="99ef0-114">To find similarities by using the default knowledge base</span></span>  
  
1.  <span data-ttu-id="99ef0-115">Dans la feuille de calcul qui contient des données gérées par MDS, dans le groupe **Qualité des données** , cliquez sur **Faire correspondre les données**.</span><span class="sxs-lookup"><span data-stu-id="99ef0-115">From the worksheet that contains MDS-managed data, in the **Data Quality** group, click **Match Data**.</span></span>  
  
2.  <span data-ttu-id="99ef0-116">Dans la boîte de dialogue **Faire correspondre les données** , dans la liste **Base de connaissances DQS** , sélectionnez **Données DQS (par défaut)**.</span><span class="sxs-lookup"><span data-stu-id="99ef0-116">In the **Match Data** dialog box, from the **DQS Knowledge Base** list, select **DQS Data (default)**.</span></span>  
  
3.  <span data-ttu-id="99ef0-117">Pour chaque colonne contenant des données que vous souhaitez mettre en correspondance, ajoutez une ligne dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="99ef0-117">For each column that contains data you want to match, add a row in the dialog box.</span></span> <span data-ttu-id="99ef0-118">Pour plus d’informations sur les champs de cette boîte de dialogue, consultez [Comment définir des paramètres de règle de correspondance](../../data-quality-services/create-a-matching-policy.md#MatchingRules).</span><span class="sxs-lookup"><span data-stu-id="99ef0-118">For information about the fields in this dialog box, see [How to Set Matching Rule Parameters](../../data-quality-services/create-a-matching-policy.md#MatchingRules).</span></span>  
  
4.  <span data-ttu-id="99ef0-119">Lorsque le total de toutes les valeurs de pondération est égal à 100 pour cent, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="99ef0-119">When the total of all weight values equals 100 percent, click **OK**.</span></span>  
  
### <a name="to-find-similarities-by-using-a-custom-knowledge-base"></a><span data-ttu-id="99ef0-120">Pour rechercher des similitudes à l'aide d'une base de connaissances personnalisée</span><span class="sxs-lookup"><span data-stu-id="99ef0-120">To find similarities by using a custom knowledge base</span></span>  
  
1.  <span data-ttu-id="99ef0-121">Dans la feuille de calcul qui contient des données gérées par MDS, dans le groupe **Qualité des données** , cliquez sur **Faire correspondre les données**.</span><span class="sxs-lookup"><span data-stu-id="99ef0-121">From the worksheet that contains MDS-managed data, in the **Data Quality** group, click **Match Data**.</span></span>  
  
2.  <span data-ttu-id="99ef0-122">Dans la liste **Base de connaissances DQS** , sélectionnez le nom de votre base de connaissances personnalisée.</span><span class="sxs-lookup"><span data-stu-id="99ef0-122">From the **DQS Knowledge Base** list, select the name of your custom knowledge base.</span></span>  
  
3.  <span data-ttu-id="99ef0-123">Pour chaque colonne de la feuille de calcul, sélectionnez un domaine DQS.</span><span class="sxs-lookup"><span data-stu-id="99ef0-123">For each column in the worksheet, select a DQS domain.</span></span>  
  
4.  <span data-ttu-id="99ef0-124">Lorsque tous les domaines DQS sont mappés aux colonnes de la feuille de calcul, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="99ef0-124">When all DQS domains are mapped to columns in the worksheet, click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="99ef0-125">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="99ef0-125">Next Steps</span></span>  
  
-   <span data-ttu-id="99ef0-126">Affichez les informations supplémentaires pour déterminer les données similaires.</span><span class="sxs-lookup"><span data-stu-id="99ef0-126">View additional information to determine which data is similar.</span></span> <span data-ttu-id="99ef0-127">Pour plus d’informations, consultez [Colonnes de mise en correspondance de la qualité des données &#40;Complément MDS pour Excel&#41;](data-quality-matching-columns-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="99ef0-127">For more information, see [Data Quality Matching Columns &#40;MDS Add-in for Excel&#41;](data-quality-matching-columns-mds-add-in-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99ef0-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="99ef0-128">See Also</span></span>  
 <span data-ttu-id="99ef0-129">[Correspondance de la qualité des données dans le Complément MDS pour Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="99ef0-129">[Data Quality Matching in the MDS Add-in for Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="99ef0-130">Correspondance de données</span><span class="sxs-lookup"><span data-stu-id="99ef0-130">Data Matching</span></span>](../../data-quality-services/data-matching.md)  
  
  
