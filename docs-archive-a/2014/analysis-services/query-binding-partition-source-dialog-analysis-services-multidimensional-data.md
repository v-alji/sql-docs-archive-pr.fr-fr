---
title: Détails de la liaison de requête (boîte de dialogue source de partition) (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.partitions.partitionfilterexpression.f1
ms.assetid: 697874d4-3f7a-4126-96f5-37cc8e2ee306
author: minewiskan
ms.author: owend
ms.openlocfilehash: 59d2ae1fed9d22366786e21a287a621f08418a5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605742"
---
# <a name="query-binding-detail-partition-source-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="cd1d2-102">Détails de la liaison de requête (boîte de dialogue Source de partition) (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="cd1d2-102">Query Binding Detail (Partition Source Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="cd1d2-103">Utilisez l’option **Liaison de requête** de la boîte de dialogue **Source de partition** pour définir la requête qui fournit les données de la partition.</span><span class="sxs-lookup"><span data-stu-id="cd1d2-103">Use the **Query Binding** option in the **Partition Source** dialog box to specify the query that provides the data for the partition.</span></span> <span data-ttu-id="cd1d2-104">Vous pouvez afficher ce volet en sélectionnant **Liaison de requête** dans l’option **Type de liaison** de la boîte de dialogue **Source de partition** .</span><span class="sxs-lookup"><span data-stu-id="cd1d2-104">You can display this pane by selecting **Query Binding** from the **Binding type** option in the **Partition Source** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cd1d2-105">Options</span><span class="sxs-lookup"><span data-stu-id="cd1d2-105">Options</span></span>  
 <span data-ttu-id="cd1d2-106">**Source de données**</span><span class="sxs-lookup"><span data-stu-id="cd1d2-106">**Data source**</span></span>  
 <span data-ttu-id="cd1d2-107">Sélectionnez la source de données sur laquelle la requête est exécutée pour fournir les données de faits de la partition.</span><span class="sxs-lookup"><span data-stu-id="cd1d2-107">Select the data source on which the query is executed to provide fact data for the partition.</span></span>  
  
 <span data-ttu-id="cd1d2-108">**Requête**</span><span class="sxs-lookup"><span data-stu-id="cd1d2-108">**Query**</span></span>  
 <span data-ttu-id="cd1d2-109">Tapez ou modifiez l'instruction SQL utilisée lors de l'extraction des données de faits lors du traitement de la partition.</span><span class="sxs-lookup"><span data-stu-id="cd1d2-109">Type or modify the SQL statement used when retrieving fact data when the partition is processed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cd1d2-110">Si vous spécifiez une clause WHERE, vous pouvez utiliser un sous-ensemble d'enregistrements de cette partition.</span><span class="sxs-lookup"><span data-stu-id="cd1d2-110">By specifying a WHERE clause, a subset of records can be used for this partition.</span></span> <span data-ttu-id="cd1d2-111">Ceci est essentiel pour éviter la duplication de données lorsque plusieurs partitions sont dérivées d'une seule table de faits.</span><span class="sxs-lookup"><span data-stu-id="cd1d2-111">This is essential to prevent duplication of data when multiple partitions are based on a single fact table.</span></span> <span data-ttu-id="cd1d2-112">Pour plus d’informations, consultez [Partition Source Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](partition-source-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="cd1d2-112">For more information, see [Partition Source Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](partition-source-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="cd1d2-113">**Vérification**</span><span class="sxs-lookup"><span data-stu-id="cd1d2-113">**Check**</span></span>  
 <span data-ttu-id="cd1d2-114">Cliquez pour vérifier que l’instruction **Requête** est une instruction SQL valide.</span><span class="sxs-lookup"><span data-stu-id="cd1d2-114">Click to verify that the statement in **Query** is a valid SQL statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd1d2-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cd1d2-115">See Also</span></span>  
 [<span data-ttu-id="cd1d2-116">Boîte de dialogue source de partition &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="cd1d2-116">Partition Source Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](partition-source-dialog-box-analysis-services-multidimensional-data.md)  
  
  
