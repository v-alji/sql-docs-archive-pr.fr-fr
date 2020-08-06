---
title: Créer des requêtes d’extraction à l’aide de DMX | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 42c896ee-e5ee-4017-b66e-31d1fe66d369
author: minewiskan
ms.author: owend
ms.openlocfilehash: 618732bfe48f7b1fe777f7841d686b07877d10ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612014"
---
# <a name="create-drillthrough-queries-using-dmx"></a><span data-ttu-id="8a62d-102">Créer des requêtes d'extraction à l'aide de DMX</span><span class="sxs-lookup"><span data-stu-id="8a62d-102">Create Drillthrough Queries using DMX</span></span>
  <span data-ttu-id="8a62d-103">Pour tous les modèles qui prennent en charge l'extraction, vous pouvez récupérer les données de cas et les données de structure en créant une requête DMX dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou dans tout autre client qui prend en charge DMX.</span><span class="sxs-lookup"><span data-stu-id="8a62d-103">For all models that support drillthrough, you can retrieve case data and structure data by creating a DMX query in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or any other client that supports DMX.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="8a62d-104">Pour afficher les données, l'extraction doit avoir été activée, et vous devez disposer des autorisations nécessaires.</span><span class="sxs-lookup"><span data-stu-id="8a62d-104">To view the data, drillthrough must have been enabled, and you must have the necessary permissions.</span></span>  
  
## <a name="specifying-drillthrough-options"></a><span data-ttu-id="8a62d-105">Spécification des options d'extraction</span><span class="sxs-lookup"><span data-stu-id="8a62d-105">Specifying Drillthrough Options</span></span>  
 <span data-ttu-id="8a62d-106">La syntaxe générale pour extraire les cas de modèles et les cas de structure est la suivante :</span><span class="sxs-lookup"><span data-stu-id="8a62d-106">The general syntax is for retrieving model cases and structure cases is as follows:</span></span>  
  
```  
SELECT <model column list>, StructureColumn('<structure column name') FROM <modelname>.CASES  
```  
  
 <span data-ttu-id="8a62d-107">Pour plus d’informations sur l’utilisation de requêtes DMX pour retourner des données de cas, consultez [SELECT FROM &#60;modèle&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx) et [SELECT FROM &#60;structure&#62;.CASES](/sql/dmx/select-from-structure-cases).</span><span class="sxs-lookup"><span data-stu-id="8a62d-107">For additional information about using DMX queries to return case data, see [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx) and [SELECT FROM &#60;structure&#62;.CASES](/sql/dmx/select-from-structure-cases).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="8a62d-108">Exemples</span><span class="sxs-lookup"><span data-stu-id="8a62d-108">Examples</span></span>  
 <span data-ttu-id="8a62d-109">La requête DMX suivante retourne les données de cas pour une série de produit spécifique, à partir d'un modèle de série chronologique.</span><span class="sxs-lookup"><span data-stu-id="8a62d-109">The following DMX query returns the case data for a specific product series, from a time series model.</span></span> <span data-ttu-id="8a62d-110">La requête retourne également la colonne `Amount`, qui n'a pas été utilisée dans le modèle, mais qui est disponible dans la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="8a62d-110">The query also returns the column `Amount`, which was not used in the model but is available in the mining structure.</span></span>  
  
```  
SELECT [DateSeries], [Model Region], Quantity, StructureColumn('Amount') AS [M200 Pacific Amount]  
FROM Forecasting.CASES  
WHERE [Model Region] = 'M200 Pacific'  
```  
  
 <span data-ttu-id="8a62d-111">Notez que, dans cet exemple, un alias a été utilisé pour renommer la colonne de structure.</span><span class="sxs-lookup"><span data-stu-id="8a62d-111">Note that in this example, an alias has been used to rename the structure column.</span></span> <span data-ttu-id="8a62d-112">Si vous n'assignez pas d'alias à la colonne de structure, la colonne est retournée avec le nom 'Expression'.</span><span class="sxs-lookup"><span data-stu-id="8a62d-112">If you do not assign an alias to the structure column, the column is returned with the name 'Expression'.</span></span> <span data-ttu-id="8a62d-113">Il s'agit du comportement par défaut pour toutes les colonnes sans nom.</span><span class="sxs-lookup"><span data-stu-id="8a62d-113">This is the default behavior for all unnamed columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a62d-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8a62d-114">See Also</span></span>  
 <span data-ttu-id="8a62d-115">[Requêtes d’extraction &#40;l’exploration de données&#41;](drillthrough-queries-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="8a62d-115">[Drillthrough Queries &#40;Data Mining&#41;](drillthrough-queries-data-mining.md) </span></span>  
 [<span data-ttu-id="8a62d-116">Extraction sur des structures d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="8a62d-116">Drillthrough on Mining Structures</span></span>](drillthrough-on-mining-structures.md)  
  
  
