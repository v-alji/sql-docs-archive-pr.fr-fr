---
title: Vérifier l’intégrité de la base de données, tâche | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.checkdatabaseintegritytask.f1
helpviewer_keywords:
- data integrity [Integration Services]
- Check Database Integrity task [Integration Services]
- checking database consistency
- database consistency checks [Integration Services]
- verifying database consistency
- integrity checking [Integration Services]
ms.assetid: 5a82fe99-4503-429f-9337-e6bac7649fe4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 99a2620a6f3f6a9a73c27fe6bb1abd34af73707d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604688"
---
# <a name="check-database-integrity-task"></a><span data-ttu-id="692a8-102">Tâche Vérifier l'intégrité de la base de données</span><span class="sxs-lookup"><span data-stu-id="692a8-102">Check Database Integrity Task</span></span>
  <span data-ttu-id="692a8-103">La tâche Vérifier l'intégrité de la base de données contrôle l'allocation et l'intégrité de la structure de tous les objets de la base de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="692a8-103">The Check Database Integrity task checks the allocation and structural integrity of all the objects in the specified database.</span></span> <span data-ttu-id="692a8-104">La tâche peut vérifier une ou plusieurs bases de données et vous pouvez indiquer si vous souhaitez également contrôler les index de base de données.</span><span class="sxs-lookup"><span data-stu-id="692a8-104">The task can check a single database or multiple databases, and you can choose whether to also check the database indexes.</span></span>  
  
 <span data-ttu-id="692a8-105">La tâche Vérifier l'intégrité de la base de données encapsule l'instruction DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="692a8-105">The Check Database Integrity task encapsulates the DBCC CHECKDB statement.</span></span> <span data-ttu-id="692a8-106">Pour plus d’informations, consultez [DBCC CHECKIDENT &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="692a8-106">For more information, see [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql).</span></span>  
  
## <a name="configuration-of-the-check-database-integrity-task"></a><span data-ttu-id="692a8-107">Configuration de la tâche Vérifier l'intégrité de la base de données</span><span class="sxs-lookup"><span data-stu-id="692a8-107">Configuration of the Check Database Integrity Task</span></span>  
 <span data-ttu-id="692a8-108">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="692a8-108">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="692a8-109">Cette tâche se trouve dans la section **Tâches du plan de maintenance** de la **boîte à outils** du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="692a8-109">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="692a8-110">Pour plus d'informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="692a8-110">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="692a8-111">Tâche Vérifier l’intégrité de la base de données &#40;Plan de maintenance&#41;</span><span class="sxs-lookup"><span data-stu-id="692a8-111">Check Database Integrity Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/check-database-integrity-task-maintenance-plan.md)  
  
 <span data-ttu-id="692a8-112">Pour plus d'informations sur la définition de ces propriétés dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="692a8-112">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="692a8-113">Définir les propriétés d'une tâche ou d'un conteneur</span><span class="sxs-lookup"><span data-stu-id="692a8-113">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
