---
title: Contrôler le comportement des déclencheurs et des contraintes pendant la synchronisation (programmation Transact-SQL de la réplication) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- identities [SQL Server replication]
- constraints [SQL Server], replication
- triggers [SQL Server], replication
- triggers [SQL Server replication]
- constraints [SQL Server replication]
- NOT FOR REPLICATION option
- NFR option
ms.assetid: 7c4e0f0e-cadc-4c99-98f4-69799b9b356b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 88176f43295fe2ab1f5f5643a46db1ce6132c5f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600821"
---
# <a name="control-the-behavior-of-triggers-and-constraints-during-synchronization-replication-transact-sql-programming"></a><span data-ttu-id="492d8-102">Contrôler le comportement de déclencheurs et de contraintes au cours de la synchronisation (programmation Transact-SQL de la réplication)</span><span class="sxs-lookup"><span data-stu-id="492d8-102">Control the Behavior of Triggers and Constraints During Synchronization (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="492d8-103">Au cours de la synchronisation, les agents de réplication exécutent des instructions [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) et [DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) sur les tables répliquées, ce qui peut entraîner l’exécution de déclencheurs de langage de manipulation de données (DML) sur ces tables.</span><span class="sxs-lookup"><span data-stu-id="492d8-103">During synchronization, replication agents execute [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql), and [DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) statements on replicated tables, which can cause data manipulation language (DML) triggers on these tables to be executed.</span></span> <span data-ttu-id="492d8-104">Dans certains cas, vous pouvez avoir besoin d'empêcher l'exécution de ces déclencheurs ou l'application de contraintes au cours de la synchronisation.</span><span class="sxs-lookup"><span data-stu-id="492d8-104">There are cases when you may need to prevent these triggers from firing or constraints from being enforced during synchronization.</span></span> <span data-ttu-id="492d8-105">Ce comportement dépend de la manière dont le déclencheur ou la contrainte sont créés.</span><span class="sxs-lookup"><span data-stu-id="492d8-105">This behavior depends on how the trigger or constraint is created.</span></span>  
  
### <a name="to-prevent-triggers-from-executing-during-synchronization"></a><span data-ttu-id="492d8-106">Pour empêcher l'exécution de déclencheurs pendant la synchronisation</span><span class="sxs-lookup"><span data-stu-id="492d8-106">To prevent triggers from executing during synchronization</span></span>  
  
1.  <span data-ttu-id="492d8-107">Quand vous créez un déclencheur, spécifiez l’option NOT FOR REPLICATION de [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="492d8-107">When creating a new trigger, specify the NOT FOR REPLICATION option of [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span></span>  
  
2.  <span data-ttu-id="492d8-108">Pour un déclencheur existant, spécifiez l’option NOT FOR REPLICATION d’[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="492d8-108">For an existing trigger, specify the NOT FOR REPLICATION option of [ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql).</span></span>  
  
### <a name="to-prevent-constraints-from-being-enforced-during-synchronization"></a><span data-ttu-id="492d8-109">Pour empêcher l'application de contraintes pendant la synchronisation</span><span class="sxs-lookup"><span data-stu-id="492d8-109">To prevent constraints from being enforced during synchronization</span></span>  
  
1.  <span data-ttu-id="492d8-110">Quand vous créez une contrainte CHECK ou FOREIGN KEY, spécifiez l’option CHECK NOT FOR REPLICATION dans la définition de contrainte de [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="492d8-110">When creating a new CHECK or FOREIGN KEY constraint, specify CHECK NOT FOR REPLICATION option in the constraint definition of [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="492d8-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="492d8-111">See Also</span></span>  
 [<span data-ttu-id="492d8-112">Créer des tables &#40;moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="492d8-112">Create Tables &#40;Database Engine&#41;</span></span>](../tables/create-tables-database-engine.md)  
  
  
