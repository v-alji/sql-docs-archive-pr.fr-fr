---
title: Modifier la valeur du délai d’attente pour les requêtes d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- time-out
ms.assetid: f1add4bc-e882-440a-a98b-333cfa274c3e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9dcdcdcbb6e2aef48dd8725f10f38180c73f5f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611416"
---
# <a name="change-the-time-out-value-for-data-mining-queries"></a><span data-ttu-id="aedc6-102">Modifier la valeur du délai d'attente pour les requêtes d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="aedc6-102">Change the Time-out Value for Data Mining Queries</span></span>
  <span data-ttu-id="aedc6-103">Lorsque vous générez un graphique de courbes d'élévation ou que vous exécutez une requête de prédiction, quelquefois, la génération de toutes les données requises pour la prédiction peut prendre du temps.</span><span class="sxs-lookup"><span data-stu-id="aedc6-103">When you build a lift chart or execute a prediction query, sometimes it can take a long time to generate all the data required for the prediction.</span></span> <span data-ttu-id="aedc6-104">Pour empêcher l'expiration du délai pour la requête, vous pouvez modifier la valeur qui contrôle le délai d'attente du serveur [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] pour achever une requête.</span><span class="sxs-lookup"><span data-stu-id="aedc6-104">To prevent the query from timing out, you can change the value that controls how long the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] server waits to complete a query.</span></span>  
  
 <span data-ttu-id="aedc6-105">La valeur par défaut est 15 ; toutefois, si vos modèles sont complexes ou que la source de données est importante, cela risque de ne pas suffire.</span><span class="sxs-lookup"><span data-stu-id="aedc6-105">The default value is 15; however, if your models are complex or the data source is large, this might not be enough.</span></span> <span data-ttu-id="aedc6-106">Le cas échéant, vous pouvez augmenter cette valeur de manière significative, afin de consacrer assez de temps pour le traitement.</span><span class="sxs-lookup"><span data-stu-id="aedc6-106">If necessary, you can increase the value significantly, to enable enough time for processing.</span></span> <span data-ttu-id="aedc6-107">Si, par exemple, vous définissez **Délai de requête** avec la valeur 600, l'exécution de la requête peut continuer jusqu'à 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="aedc6-107">For example, if you set **Query Timeout** to 600, the query could continue to run for up to 10 minutes.</span></span>  
  
 <span data-ttu-id="aedc6-108">Pour plus d’informations sur les requêtes de prédiction, consultez [Tâches de requête d’exploration de données et procédures](data-mining-query-tasks-and-how-tos.md).</span><span class="sxs-lookup"><span data-stu-id="aedc6-108">For more information about prediction queries, see [Data Mining Query Tasks and How-tos](data-mining-query-tasks-and-how-tos.md).</span></span>  
  
### <a name="configure-the-time-out-value-for-data-mining-queries"></a><span data-ttu-id="aedc6-109">Configurer la valeur du délai d'attente pour les requêtes d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="aedc6-109">Configure the time-out value for data mining queries</span></span>  
  
1.  <span data-ttu-id="aedc6-110">Dans le menu [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]Outils **de** , sélectionnez **Options**.</span><span class="sxs-lookup"><span data-stu-id="aedc6-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], from the **Tools** menu, selection **Options**.</span></span>  
  
2.  <span data-ttu-id="aedc6-111">Dans le volet **Options** , développez **Concepteurs Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="aedc6-111">In the **Options** pane, expand **Business Intelligence Designers**.</span></span>  
  
3.  <span data-ttu-id="aedc6-112">Cliquez sur la zone de texte **Délai de requête** et tapez une valeur pour le nombre de secondes.</span><span class="sxs-lookup"><span data-stu-id="aedc6-112">Click the **Query Timeout** text box, and type a value for the number of seconds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aedc6-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="aedc6-113">See Also</span></span>  
 <span data-ttu-id="aedc6-114">[Tâches de requête d’exploration de données et procédures](data-mining-query-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="aedc6-114">[Data Mining Query Tasks and How-tos](data-mining-query-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="aedc6-115">Requêtes d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="aedc6-115">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
