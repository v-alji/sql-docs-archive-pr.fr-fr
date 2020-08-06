---
title: Restreindre les lignes (Assistant Partition) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.typefilterexpression.f1
ms.assetid: eec8da8f-eab4-4ac4-a81d-995c814f88ca
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9b0acc9ab24cfe92877d9abcd86353c85b4f8905
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602390"
---
# <a name="restrict-rows-partition-wizard"></a><span data-ttu-id="de189-102">Restreindre les lignes (Assistant Partition)</span><span class="sxs-lookup"><span data-stu-id="de189-102">Restrict Rows (Partition Wizard)</span></span>
  <span data-ttu-id="de189-103">Utilisez la page **Restreindre les lignes** pour limiter les lignes qui seront extraites de la table spécifiée et qui seront agrégées et incluses dans la partition.</span><span class="sxs-lookup"><span data-stu-id="de189-103">Use the **Restrict Rows** page to restrict the rows that will be retrieved from the specified table and will be aggregated and included in the partition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="de189-104"> Cette page s'affiche uniquement si vous avez sélectionné une seule table dans la page **Spécifier des informations sur la source** .</span><span class="sxs-lookup"><span data-stu-id="de189-104">This page is appears only if you selected a single table in the **Specify Source Information** page.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="de189-105"> Si, dans la page **Spécifier des informations sur la source** , vous avez spécifié dans **Tables disponibles** une table utilisée par une autre partition, vous devez fournir une requête dans la page **Restreindre les lignes** , faute de quoi il existe un risque de duplication des données dans le cube.</span><span class="sxs-lookup"><span data-stu-id="de189-105">If you specified a table in **Available Tables** on the **Specify Source Information** page that is used by another partition, you must provide a query in the **Restrict Rows** page or risk duplicating data in the cube.</span></span>  
  
## <a name="options"></a><span data-ttu-id="de189-106">Options</span><span class="sxs-lookup"><span data-stu-id="de189-106">Options</span></span>  
 <span data-ttu-id="de189-107">**Spécifier une requête pour restreindre les lignes**</span><span class="sxs-lookup"><span data-stu-id="de189-107">**Specify a query to restrict rows**</span></span>  
 <span data-ttu-id="de189-108">Sélectionnez cette option pour entrer dans la zone **Requête** une requête qui limite les lignes.</span><span class="sxs-lookup"><span data-stu-id="de189-108">Select to enter a query that restricts rows into the **Query** box.</span></span>  
  
 <span data-ttu-id="de189-109">Si **Fournir une clause WHERE** est vide lorsque cette option est sélectionnée, celle-ci contient une instruction SQL qui extrait toutes les colonnes et toutes les lignes de la table précédemment sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="de189-109">If **Supply a WHERE clause** is empty when this option is selected, that option is populated with an SQL statement that retrieves all columns and all rows from the previously selected table.</span></span>  
  
 <span data-ttu-id="de189-110">**Requête**</span><span class="sxs-lookup"><span data-stu-id="de189-110">**Query**</span></span>  
 <span data-ttu-id="de189-111">Tapez ou modifiez l'instruction SQL utilisée pour extraire les lignes de la table lorsque la partition est traitée.</span><span class="sxs-lookup"><span data-stu-id="de189-111">Type or modify the SQL statement used when retrieving rows from the table when the partition is processed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="de189-112">Si vous spécifiez une clause WHERE, vous pouvez utiliser un sous-ensemble d'enregistrements de cette partition.</span><span class="sxs-lookup"><span data-stu-id="de189-112">By specifying a WHERE clause, a subset of records can be used for this partition.</span></span> <span data-ttu-id="de189-113">Ceci est essentiel pour éviter la duplication de données lorsque plusieurs partitions sont dérivées d'une seule table de faits.</span><span class="sxs-lookup"><span data-stu-id="de189-113">This is essential to prevent duplication of data when multiple partitions are based on a single fact table.</span></span>  
  
 <span data-ttu-id="de189-114">**Vérification**</span><span class="sxs-lookup"><span data-stu-id="de189-114">**Check**</span></span>  
 <span data-ttu-id="de189-115">Vérifie la validité de l’instruction SQL de la zone **Requête** .</span><span class="sxs-lookup"><span data-stu-id="de189-115">Verifies that the statement in **Query** is a valid SQL statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de189-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="de189-116">See Also</span></span>  
 [<span data-ttu-id="de189-117">Partitions &#40;Analysis Services - Données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="de189-117">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
