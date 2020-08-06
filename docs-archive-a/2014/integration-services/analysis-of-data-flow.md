---
title: Analyse du workflow de données | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5654cb30-cad2-470c-97b3-59cb331033e5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 184b53d3e982cd80d7c9c0909538a751585ae21d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602978"
---
# <a name="analysis-of-data-flow"></a><span data-ttu-id="a7fae-102">Analyse des flux de données</span><span class="sxs-lookup"><span data-stu-id="a7fae-102">Analysis of Data Flow</span></span>
  <span data-ttu-id="a7fae-103">Vous pouvez utiliser la [catalog.execution_data_statistics](../relational-databases/statistics/statistics.md) `SSISDB` vue de base de donnéescatalog.execution_data_statistics pour analyser le workflow des packages.</span><span class="sxs-lookup"><span data-stu-id="a7fae-103">You can use the [catalog.execution_data_statistics](../relational-databases/statistics/statistics.md)`SSISDB` database view to analyze the data flow of packages.</span></span> <span data-ttu-id="a7fae-104">Cette vue affiche une ligne à chaque fois qu'un composant de flux de données envoie des données à un composant en aval.</span><span class="sxs-lookup"><span data-stu-id="a7fae-104">This view displays a row each time a data flow component sends data to a downstream component.</span></span> <span data-ttu-id="a7fae-105">Les informations peuvent être utilisées pour mieux comprendre les lignes envoyées à chaque composant.</span><span class="sxs-lookup"><span data-stu-id="a7fae-105">The information can be used to gain a deeper understanding of the rows that are sent to each component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a7fae-106">Le niveau de journalisation doit avoir la valeur **Commentaires** afin de capturer des informations avec la vue catalog.execution_data_statistics.</span><span class="sxs-lookup"><span data-stu-id="a7fae-106">The logging level must be set to **Verbose** in order to capture information with the catalog.execution_data_statistics view.</span></span>  
  
 <span data-ttu-id="a7fae-107">L'exemple suivant affiche le nombre de lignes transmises entre les composants d'un package.</span><span class="sxs-lookup"><span data-stu-id="a7fae-107">The following example displays the number of rows sent between components of a package.</span></span>  
  
```  
use SSISDB  
select package_name, task_name, source_component_name, destination_component_name, rows_sent  
from catalog.execution_data_statistics  
where execution_id = 132  
order by source_component_name, destination_component_name  
  
```  
  
 <span data-ttu-id="a7fae-108">L'exemple suivant calcule le nombre de lignes par milliseconde envoyées par chaque composant pour une exécution spécifique.</span><span class="sxs-lookup"><span data-stu-id="a7fae-108">The following example calculates the number of rows per millisecond sent by each component for a specific execution.</span></span> <span data-ttu-id="a7fae-109">Les valeurs calculées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a7fae-109">The calculated values are:</span></span>  
  
-   <span data-ttu-id="a7fae-110">**total_rows** - Somme de toutes les lignes envoyées par le composant</span><span class="sxs-lookup"><span data-stu-id="a7fae-110">**total_rows** - the sum of all the rows sent by the component</span></span>  
  
-   <span data-ttu-id="a7fae-111">**wall_clock_time_ms** - Durée d’exécution écoulée totale en millisecondes pour chaque composant</span><span class="sxs-lookup"><span data-stu-id="a7fae-111">**wall_clock_time_ms** - the total elapsed execution time, in milliseconds, for each component</span></span>  
  
-   <span data-ttu-id="a7fae-112">**num_rows_per_millisecond** - Nombre de lignes par milliseconde envoyées par chaque composant</span><span class="sxs-lookup"><span data-stu-id="a7fae-112">**num_rows_per_millisecond** - the number of rows per millisecond sent by each component</span></span>  
  
 <span data-ttu-id="a7fae-113">La `HAVING` clause est utilisée pour empêcher une erreur de division par zéro dans les calculs.</span><span class="sxs-lookup"><span data-stu-id="a7fae-113">The `HAVING` clause is used to prevent a divide-by-zero error in the calculations.</span></span>  
  
```  
use SSISDB  
select source_component_name, destination_component_name,  
    sum(rows_sent) as total_rows,  
    DATEDIFF(ms,min(created_time),max(created_time)) as wall_clock_time_ms,  
    ((0.0+sum(rows_sent)) / (datediff(ms,min(created_time),max(created_time)))) as [num_rows_per_millisecond]  
from [catalog].[execution_data_statistics]  
where execution_id = 132  
group by source_component_name, destination_component_name  
having (datediff(ms,min(created_time),max(created_time))) > 0  
order by source_component_name desc  
  
```  
  
## <a name="related-tasks"></a><span data-ttu-id="a7fae-114">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="a7fae-114">Related Tasks</span></span>  
 [<span data-ttu-id="a7fae-115">Débogage d’un flux de données</span><span class="sxs-lookup"><span data-stu-id="a7fae-115">Debugging Data Flow</span></span>](troubleshooting/debugging-data-flow.md)  
  
 [<span data-ttu-id="a7fae-116">Outils de dépannage pour l’exécution des packages</span><span class="sxs-lookup"><span data-stu-id="a7fae-116">Troubleshooting Tools for Package Execution</span></span>](troubleshooting/troubleshooting-tools-for-package-execution.md)  
  
## <a name="see-also"></a><span data-ttu-id="a7fae-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a7fae-117">See Also</span></span>  
 [<span data-ttu-id="a7fae-118">Données dans des flux de données</span><span class="sxs-lookup"><span data-stu-id="a7fae-118">Data in Data Flows</span></span>](data-flow/data-in-data-flows.md)  
  
  
