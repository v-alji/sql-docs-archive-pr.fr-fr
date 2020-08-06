---
title: Importer à partir d’une source de données multidimensionnelles (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7f0793ea-a4c7-42e9-b722-2164a454ebca
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0b26cc8ed7237f87fa5e23c6a2fd47e18de2c165
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614229"
---
# <a name="import-from-a-multidimensional-data-source-ssas-tabular"></a><span data-ttu-id="5180d-102">Importer à partir d'une source de données multidimensionnelle (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="5180d-102">Import from a Multidimensional Data Source (SSAS Tabular)</span></span>
  <span data-ttu-id="5180d-103">Vous pouvez utiliser une base de données de cube Analysis Services comme source de données pour un modèle tabulaire.</span><span class="sxs-lookup"><span data-stu-id="5180d-103">You can use an Analysis Services cube database as a data source for a tabular model.</span></span> <span data-ttu-id="5180d-104">Pour importer des données à partir d'un cube Analysis Services, vous devez définir une requête MDX afin de sélectionner les données à importer.</span><span class="sxs-lookup"><span data-stu-id="5180d-104">In order to import data from an Analysis Services cube, you must define an MDX Query to select data to import.</span></span>  
  
 <span data-ttu-id="5180d-105">Toutes les données contenues dans une base de données SQL Server Analysis Services peuvent être importées dans un modèle.</span><span class="sxs-lookup"><span data-stu-id="5180d-105">Any data that is contained in a SQL Server Analysis Services database can be imported into a model.</span></span> <span data-ttu-id="5180d-106">Vous pouvez extraire tout ou partie d'une dimension ou obtenir des segments et des agrégats à partir du cube, tels que le cumul des ventes, mois par mois, pour l'année actuelle, etc. Toutefois, n'oubliez pas que toutes les données que vous importez à partir d'un cube sont aplaties.</span><span class="sxs-lookup"><span data-stu-id="5180d-106">You can extract all or part of a dimension, or get slices and aggregates from the cube, such as the sum of sales, month by month, for the current year, etc. However, you should keep in mind all data that you import from a cube is flattened.</span></span> <span data-ttu-id="5180d-107">Par conséquent, si vous définissez une requête qui récupère des mesures le long de plusieurs dimensions, les données sont importées avec chaque dimension dans une colonne distincte.</span><span class="sxs-lookup"><span data-stu-id="5180d-107">Therefore, if you define a query that retrieves measures along multiple dimensions, the data will be imported with each dimension in a separate column.</span></span>  
  
 <span data-ttu-id="5180d-108">Les cubes Analysis Services doivent être de version SQL Server 2005, SQL Server 2008, SQL Server 2008 R2, [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]ou [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5180d-108">Analysis Services cubes must be version SQL Server 2005, SQL Server 2008, SQL Server 2008 R2, [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], or [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span>  
  
### <a name="to-import-data-from-an-analysis-services-cube"></a><span data-ttu-id="5180d-109">Pour importer des données à partir d'un cube Analysis Services</span><span class="sxs-lookup"><span data-stu-id="5180d-109">To import data from an Analysis Services cube</span></span>  
  
1.  <span data-ttu-id="5180d-110">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], cliquez sur le menu **Modèle** , puis sur **Importer à partir de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="5180d-110">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Import from Data Source**.</span></span>  
  
2.  <span data-ttu-id="5180d-111">Sur la page **Connexion à une source de données** , sélectionnez **Microsoft Analysis Services**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="5180d-111">On the **Connect to a Data Source** page, select **Microsoft Analysis Services**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="5180d-112">Suivez les étapes de l'Assistant Importation de table.</span><span class="sxs-lookup"><span data-stu-id="5180d-112">Follow the steps in the Table Import Wizard.</span></span> <span data-ttu-id="5180d-113">Vous pouvez spécifier une requête MDX sur la page **Spécifier une requête MDX** .</span><span class="sxs-lookup"><span data-stu-id="5180d-113">You will be able to specify an MDX query on the **Specify a MDX Query** page.</span></span> <span data-ttu-id="5180d-114">Pour utiliser le concepteur de requêtes MDX, sur la page Spécifier une requête MDX, cliquez sur **Conception**.</span><span class="sxs-lookup"><span data-stu-id="5180d-114">To use the MDX Query Designer, on the Specify a MDX Query page, click **Design**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5180d-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5180d-115">See Also</span></span>  
 <span data-ttu-id="5180d-116">[Importer des données &#40;&#41;tabulaire SSAS](import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="5180d-116">[Import Data &#40;SSAS Tabular&#41;](import-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="5180d-117">Sources de données prises en charge &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="5180d-117">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)  
  
  
