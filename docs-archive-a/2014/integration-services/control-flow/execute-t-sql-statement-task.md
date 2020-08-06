---
title: Exécuter l’instruction T-SQL, tâche | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executetsqlstatementtask.f1
helpviewer_keywords:
- Transact-SQL statements, SSIS
- statements [Integration Services]
- Execute T-SQL Statement task [Integration Services]
ms.assetid: 7e9086ca-d27e-46c0-bfad-d61333ebd55e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7ebc73ad843ac7fcf1dfbe7699ecd8ea53edcdad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697064"
---
# <a name="execute-t-sql-statement-task"></a><span data-ttu-id="857f6-102">Tâche Exécuter l'instruction T-SQL</span><span class="sxs-lookup"><span data-stu-id="857f6-102">Execute T-SQL Statement Task</span></span>
  <span data-ttu-id="857f6-103">La tâche Exécuter l'instruction T-SQL exécute des instructions Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="857f6-103">The Execute T-SQL Statement task runs Transact-SQL statements.</span></span> <span data-ttu-id="857f6-104">Pour plus d’informations, consultez [Référence Transact-SQL &#40;moteur de base de données&#41;](/sql/t-sql/language-reference) et [Requêtes Integration Services &#40;SSIS&#41;](../integration-services-ssis-queries.md).</span><span class="sxs-lookup"><span data-stu-id="857f6-104">For more information, see [Transact-SQL Reference &#40;Database Engine&#41;](/sql/t-sql/language-reference) and [Integration Services &#40;SSIS&#41; Queries](../integration-services-ssis-queries.md).</span></span>  
  
 <span data-ttu-id="857f6-105">Cette tâche est similaire à la tâche d'exécution SQL.</span><span class="sxs-lookup"><span data-stu-id="857f6-105">This task is similar to the Execute SQL task.</span></span> <span data-ttu-id="857f6-106">Toutefois, la tâche Exécuter l'instruction T-SQL ne prend en charge que la version Transact-SQL du langage SQL et vous ne pouvez pas recourir à cette tâche pour exécuter des instructions sur les serveurs qui utilisent d'autres dialectes du langage SQL.</span><span class="sxs-lookup"><span data-stu-id="857f6-106">However, the Execute T-SQL Statement task supports only the Transact-SQL version of the SQL language and you cannot use this task to run statements on servers that use other dialects of the SQL language.</span></span> <span data-ttu-id="857f6-107">Pour exécuter des requêtes paramétrables, enregistrer les résultats des requêtes dans des variables ou utiliser des expressions de propriété, vous devez utiliser la tâche d'exécution SQL et non pas la tâche Exécuter l'instruction T-SQL.</span><span class="sxs-lookup"><span data-stu-id="857f6-107">If you need to run parameterized queries, save the query results to variables, or use property expressions, you should use the Execute SQL task instead of the Execute T-SQL Statement task.</span></span> <span data-ttu-id="857f6-108">Pour plus d'informations, consultez [Execute SQL Task](execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="857f6-108">For more information, see [Execute SQL Task](execute-sql-task.md).</span></span>  
  
## <a name="configuration-of-the-execute-t-sql-task"></a><span data-ttu-id="857f6-109">Configuration de la tâche Exécuter l'instruction T-SQL</span><span class="sxs-lookup"><span data-stu-id="857f6-109">Configuration of the Execute T-SQL Task</span></span>  
 <span data-ttu-id="857f6-110">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="857f6-110">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="857f6-111">Cette tâche se trouve dans la section **Tâches du plan de maintenance** de la **boîte à outils** du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="857f6-111">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="857f6-112">Pour plus d'informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="857f6-112">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="857f6-113">Exécuter la tâche de l’instruction T-SQL &#40;Plan de maintenance&#41;</span><span class="sxs-lookup"><span data-stu-id="857f6-113">Execute T-SQL Statement Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/execute-t-sql-statement-task-maintenance-plan.md)  
  
 <span data-ttu-id="857f6-114">Pour plus d'informations sur la définition de ces propriétés dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="857f6-114">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="857f6-115">Définir les propriétés d'une tâche ou d'un conteneur</span><span class="sxs-lookup"><span data-stu-id="857f6-115">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="857f6-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="857f6-116">See Also</span></span>  
 <span data-ttu-id="857f6-117">[Tâches Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="857f6-117">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 <span data-ttu-id="857f6-118">[Flux de contrôle](control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="857f6-118">[Control Flow](control-flow.md) </span></span>  
 [<span data-ttu-id="857f6-119">MERGE dans les packages Integration Services</span><span class="sxs-lookup"><span data-stu-id="857f6-119">MERGE in Integration Services Packages</span></span>](merge-in-integration-services-packages.md)  
  
  
