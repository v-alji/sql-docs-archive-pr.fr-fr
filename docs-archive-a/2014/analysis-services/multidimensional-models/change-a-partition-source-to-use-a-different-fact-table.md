---
title: Modifier une source de partition pour utiliser une table de faits différente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- fact tables [Analysis Services]
- partitions [Analysis Services], fact tables
ms.assetid: 5508312f-8e46-4802-9362-6688ca03d098
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0063a6023d769dc6dccd616655d10e0bd3c65a98
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705679"
---
# <a name="change-a-partition-source-to-use-a-different-fact-table"></a><span data-ttu-id="71819-102">Modifier une source de partition afin d'utiliser une table de faits différente</span><span class="sxs-lookup"><span data-stu-id="71819-102">Change a partition source to use a different fact table</span></span>
  <span data-ttu-id="71819-103">Lorsque vous créez une partition pour un cube, vous pouvez décider d'utiliser une table de faits différente.</span><span class="sxs-lookup"><span data-stu-id="71819-103">When you create a partition for a cube, you can choose to use a different fact table.</span></span> <span data-ttu-id="71819-104">Les tables différentes peuvent provenir d'une vue de source de données unique, de différentes vues de sources de données ou de différentes sources de données.</span><span class="sxs-lookup"><span data-stu-id="71819-104">Different tables may be from a single data source view, from different data source views, or from different data sources.</span></span> <span data-ttu-id="71819-105">Une vue de source de données peut également contenir des tables différentes provenant de plusieurs sources de données.</span><span class="sxs-lookup"><span data-stu-id="71819-105">A data source view may also contain different tables from more than one data source.</span></span>  
  
 <span data-ttu-id="71819-106">Toutes les tables de faits et dimensions des partitions d'un cube doivent avoir la même structure que la table de faits et les dimensions du cube.</span><span class="sxs-lookup"><span data-stu-id="71819-106">All fact tables and dimensions for a cube's partitions must have the same structure as the fact table and dimensions of the cube.</span></span> <span data-ttu-id="71819-107">Par exemple, des tables de faits différentes peuvent avoir la même structure mais contenir des données pour différentes années ou différentes lignes de produits.</span><span class="sxs-lookup"><span data-stu-id="71819-107">For example, different fact tables can have the same structure but contain data for different years or different product lines.</span></span>  
  
 <span data-ttu-id="71819-108">Vous spécifiez une table de faits dans la page **Spécifier des informations sur la source** de l’Assistant Partition.</span><span class="sxs-lookup"><span data-stu-id="71819-108">You specify a fact table on the **Specify Source Information** page of the Partition Wizard.</span></span> <span data-ttu-id="71819-109">Dans cette page, dans le groupe Source de partition à côté de **Regarder dans**, spécifiez la source de données ou la vue de source de données à consulter.</span><span class="sxs-lookup"><span data-stu-id="71819-109">On this page, in the Partition Source group next to **Look in**, specify a data source or data source view in which to look.</span></span> <span data-ttu-id="71819-110">Ensuite, cliquez sur **Rechercher des tables**puis, sous **Tables disponibles**, sélectionnez la table à utiliser.</span><span class="sxs-lookup"><span data-stu-id="71819-110">Next, click **Find Tables**, and then, under **Available Tables**, select the table you want to use.</span></span>  
  
 <span data-ttu-id="71819-111">Lorsque vous utilisez des tables de faits différentes, assurez-vous qu'aucune donnée n'est dupliquée dans les partitions.</span><span class="sxs-lookup"><span data-stu-id="71819-111">When you use different fact tables, ensure that no data is duplicated among the partitions.</span></span> <span data-ttu-id="71819-112">Par exemple, si une table de faits contient uniquement les transactions de l'année 2012 et qu'une autre table de faits contient uniquement les transactions de l'année 2013, ces tables contiennent des données distinctes.</span><span class="sxs-lookup"><span data-stu-id="71819-112">For example, if one fact table contains transactions for 2012 only, and another fact table contains transactions for 2013 only, these tables contain independent data.</span></span> <span data-ttu-id="71819-113">De même, les tables de faits réservées à des lignes de produits ou à des régions géographiques distinctes sont totalement indépendantes.</span><span class="sxs-lookup"><span data-stu-id="71819-113">Similarly, fact tables for distinct product lines or distinct geographical areas are independent.</span></span>  
  
 <span data-ttu-id="71819-114">Il est possible, mais non conseillé, d'utiliser des tables de faits différentes contenant des données en double.</span><span class="sxs-lookup"><span data-stu-id="71819-114">It is possible, but not recommended, to use different fact tables that contain duplicated data.</span></span> <span data-ttu-id="71819-115">Dans ce cas, vous devez utiliser des filtres dans les partitions pour vous assurer que les données utilisées par une partition ne sont pas utilisées aussi par une autre partition.</span><span class="sxs-lookup"><span data-stu-id="71819-115">In this case, you must use filters in the partitions to ensure that data used by one partition is not used by any other partition.</span></span> <span data-ttu-id="71819-116">Pour plus d’informations, consultez [Créer et gérer une partition locale &#40;Analysis Services&#41;](create-and-manage-a-local-partition-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="71819-116">For more information, see [Create and Manage a Local Partition &#40;Analysis Services&#41;](create-and-manage-a-local-partition-analysis-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71819-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="71819-117">See Also</span></span>  
 [<span data-ttu-id="71819-118">Créer et gérer une partition locale &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="71819-118">Create and Manage a Local Partition &#40;Analysis Services&#41;</span></span>](create-and-manage-a-local-partition-analysis-services.md)  
  
  
