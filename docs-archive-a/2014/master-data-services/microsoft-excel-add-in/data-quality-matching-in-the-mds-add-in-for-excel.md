---
title: Mise en correspondance de la qualité des données dans le Complément MDS pour Excel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: be78d051-0d56-46d3-bb89-327e218dadd6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 037e535452e7f19644837e0cbcfd02efec5422b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612991"
---
# <a name="data-quality-matching-in-the-mds-add-in-for-excel"></a><span data-ttu-id="46fc1-102">Mise en correspondance de la qualité des données dans le complément MDS pour Excel</span><span class="sxs-lookup"><span data-stu-id="46fc1-102">Data Quality Matching in the MDS Add-in for Excel</span></span>
  <span data-ttu-id="46fc1-103">Au fil du temps, vous souhaiterez ajouter des données au référentiel MDS.</span><span class="sxs-lookup"><span data-stu-id="46fc1-103">Over time, you will want to add more data to the MDS repository.</span></span> <span data-ttu-id="46fc1-104">Avant d’ajouter des données, il peut être utile de comparer les nouvelles données aux données qui sont déjà managées dans MDS pour s’assurer de ne pas ajouter de données dupliquées ou incorrectes.</span><span class="sxs-lookup"><span data-stu-id="46fc1-104">Before adding data, it can be useful to compare the new data to the data that's already managed in MDS, to ensure you are not adding duplicate or inaccurate data.</span></span>  
  
 <span data-ttu-id="46fc1-105">MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] utilise la fonctionnalité Data Quality Services (DQS) de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour faire correspondre les données similaires.</span><span class="sxs-lookup"><span data-stu-id="46fc1-105">The MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] uses the Data Quality Services (DQS) feature of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to match data that's similar.</span></span> <span data-ttu-id="46fc1-106">Lorsque vous utilisez la fonctionnalité de correspondance du complément, les enregistrements similaires sont regroupés et un score qui représente la précision du résultat est affiché.</span><span class="sxs-lookup"><span data-stu-id="46fc1-106">When you use the matching functionality in the Add-in, similar records are grouped together and a score that represents the accuracy of the result is displayed.</span></span> <span data-ttu-id="46fc1-107">Pour plus d’informations sur la fonctionnalité de correspondance fournie par DQS, consultez [Correspondance de données](../../data-quality-services/data-matching.md).</span><span class="sxs-lookup"><span data-stu-id="46fc1-107">For more information about the matching functionality provided by DQS, see [Data Matching](../../data-quality-services/data-matching.md).</span></span>  
  
## <a name="workflow-for-data-quality-matching"></a><span data-ttu-id="46fc1-108">Flux de travail pour la correspondance de la qualité des données</span><span class="sxs-lookup"><span data-stu-id="46fc1-108">Workflow for Data Quality Matching</span></span>  
 <span data-ttu-id="46fc1-109">Quand vous utilisez DQS avec MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], utilisez le flux de travail suivant :</span><span class="sxs-lookup"><span data-stu-id="46fc1-109">When using DQS with the MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use the following workflow:</span></span>  
  
1.  <span data-ttu-id="46fc1-110">Récupérez une liste de données managées MDS et combinez-la avec une liste non gérée dans MDS.</span><span class="sxs-lookup"><span data-stu-id="46fc1-110">Retrieve a list of MDS-managed data and combine it with a list that is not managed in MDS.</span></span> <span data-ttu-id="46fc1-111">Pour plus d’informations, consultez [Combiner des données &#40;Complément MDS pour Excel&#41;](combine-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="46fc1-111">For more information, see [Combine Data &#40;MDS Add-in for Excel&#41;](combine-data-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="46fc1-112">Utilisez la base de connaissances DQS pour comparer les données dans la liste combinée.</span><span class="sxs-lookup"><span data-stu-id="46fc1-112">Use DQS knowledge to compare the data in the combined list.</span></span> <span data-ttu-id="46fc1-113">Pour plus d’informations, consultez [Mettre en correspondance les données similaires &#40;Complément MDS pour Excel&#41;](match-similar-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="46fc1-113">For more information, see [Match Similar Data &#40;MDS Add-in for Excel&#41;](match-similar-data-mds-add-in-for-excel.md).</span></span>  
  
3.  <span data-ttu-id="46fc1-114">Pour plus de détails sur les similitudes identifiées par DQS, affichez les colonnes de détail.</span><span class="sxs-lookup"><span data-stu-id="46fc1-114">To view more details about the similarities found by DQS, show the detail columns.</span></span>  
  
4.  <span data-ttu-id="46fc1-115">Explorez les résultats et déterminez les données qui doivent être ajoutées au référentiel MDS et celles qui sont dupliquées.</span><span class="sxs-lookup"><span data-stu-id="46fc1-115">Go through the results and determine which data should be added to the MDS repository and which data is duplicated.</span></span>  
  
5.  <span data-ttu-id="46fc1-116">Publiez les données nouvelles et/ou mises à jour dans le référentiel MDS.</span><span class="sxs-lookup"><span data-stu-id="46fc1-116">Publish the new and/or updated data to the MDS repository.</span></span>  
  
## <a name="knowledge-bases"></a><span data-ttu-id="46fc1-117">Bases de connaissances</span><span class="sxs-lookup"><span data-stu-id="46fc1-117">Knowledge Bases</span></span>  
 <span data-ttu-id="46fc1-118">Les résultats correspondants fournis dans le complément sont basés sur une base de connaissances DQS.</span><span class="sxs-lookup"><span data-stu-id="46fc1-118">The matching results provided in the Add-in are based on a DQS knowledge base.</span></span>  
  
-   <span data-ttu-id="46fc1-119">La base de connaissances par défaut (DQS Data) est créée lors de l'installation de DQS.</span><span class="sxs-lookup"><span data-stu-id="46fc1-119">The default knowledge base (DQS Data) is created when DQS is installed.</span></span> <span data-ttu-id="46fc1-120">Si vous choisissez d'utiliser la base de connaissances par défaut (sans ajouter de stratégie de correspondance à la base de connaissances par défaut dans le client de qualité des données), vous devez mapper les colonnes dans la feuille de calcul aux domaines de la base de connaissances, puis attribuer une valeur de pondération aux domaines que vous choisissez.</span><span class="sxs-lookup"><span data-stu-id="46fc1-120">If you choose to use the default knowledge base (without adding a matching policy to the default knowledge base in the Data Quality Client), you must map columns in the worksheet to domains in the knowledge base, and then assign a weight value to the domains you choose.</span></span>  
  
-   <span data-ttu-id="46fc1-121">Vous pouvez utiliser le client de qualité des données pour créer une nouvelle base de connaissances avec une stratégie de correspondance, ou pour ajouter une stratégie de correspondance à la base de connaissances par défaut.</span><span class="sxs-lookup"><span data-stu-id="46fc1-121">You can use the Data Quality Client to create a new knowledge base with a matching policy, or to add a matching policy to the default knowledge base.</span></span> <span data-ttu-id="46fc1-122">Dans ce cas, les valeurs de pondération sont déterminées par la stratégie correspondante que vous avez déjà créée et vous devez uniquement mapper les colonnes aux domaines.</span><span class="sxs-lookup"><span data-stu-id="46fc1-122">In this case, the weight values are determined by the matching policy you already created and you need only to map the columns to the domains.</span></span> <span data-ttu-id="46fc1-123">Pour plus d’informations, consultez [Créer une stratégie de correspondance](../../data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="46fc1-123">For more information, see [Create a Matching Policy](../../data-quality-services/create-a-matching-policy.md).</span></span>  
  
 <span data-ttu-id="46fc1-124">Pour plus d’informations sur les bases de connaissances, consultez [Bases de connaissances et domaines DQS](../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="46fc1-124">For more information about knowledge bases, see [DQS Knowledge Bases and Domains](../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="46fc1-125">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="46fc1-125">Related Tasks</span></span>  
  
|<span data-ttu-id="46fc1-126">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="46fc1-126">Task Description</span></span>|<span data-ttu-id="46fc1-127">Rubrique</span><span class="sxs-lookup"><span data-stu-id="46fc1-127">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="46fc1-128">Combinez les données externes avec les données managées MDS en préparation pour les comparer.</span><span class="sxs-lookup"><span data-stu-id="46fc1-128">Combine external data with MDS-managed data in preparation to compare it.</span></span>|[<span data-ttu-id="46fc1-129">Combiner des données &#40;Complément MDS pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="46fc1-129">Combine Data &#40;MDS Add-in for Excel&#41;</span></span>](combine-data-mds-add-in-for-excel.md)|  
|<span data-ttu-id="46fc1-130">Utilisez la base de connaissances DQS pour rechercher des similitudes dans vos données.</span><span class="sxs-lookup"><span data-stu-id="46fc1-130">Use DQS knowledge to find similarities in your data.</span></span>|[<span data-ttu-id="46fc1-131">Mettre en correspondance les données similaires &#40;Complément MDS pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="46fc1-131">Match Similar Data &#40;MDS Add-in for Excel&#41;</span></span>](match-similar-data-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="46fc1-132">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="46fc1-132">Related Content</span></span>  
  
-   [<span data-ttu-id="46fc1-133">Publication des Complément MDS pour Excel de &#40;de données&#41;</span><span class="sxs-lookup"><span data-stu-id="46fc1-133">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="46fc1-134">Correspondance de données</span><span class="sxs-lookup"><span data-stu-id="46fc1-134">Data Matching</span></span>](../../data-quality-services/data-matching.md)  
  
  
