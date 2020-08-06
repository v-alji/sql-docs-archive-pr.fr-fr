---
title: Procédures stockées compilées en mode natif et options SET d’exécution | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c1869cf7-9030-4d18-85d6-0e419a4e9af7
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 264a2b3ab1e6f3f0bda97bfe89a4438aa641577d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709431"
---
# <a name="natively-compiled-stored-procedures-and-execution-set-options"></a><span data-ttu-id="5737c-102">Procédures stockées compilées en mode natif et options SET d'exécution</span><span class="sxs-lookup"><span data-stu-id="5737c-102">Natively Compiled Stored Procedures and Execution Set Options</span></span>
  <span data-ttu-id="5737c-103">Les options de session sont fixes dans les blocs Atomic.</span><span class="sxs-lookup"><span data-stu-id="5737c-103">Session options are fixed in atomic blocks.</span></span> <span data-ttu-id="5737c-104">L'exécution d'une procédure stockée n'est pas affectée par les options SET d'une session.</span><span class="sxs-lookup"><span data-stu-id="5737c-104">A stored procedure's execution is not affected by a session's SET options.</span></span> <span data-ttu-id="5737c-105">Toutefois, certaines options SET, telles que SET NOEXEC et SET SHOWPLAN_XML, empêchent l'exécution des procédures stockées (y compris des procédures stockées compilées en mode natif).</span><span class="sxs-lookup"><span data-stu-id="5737c-105">However, certain SET options, such as SET NOEXEC and SET SHOWPLAN_XML, cause stored procedures (including natively compiled stored procedures) to not execute.</span></span>  
  
 <span data-ttu-id="5737c-106">Lorsqu'une procédure stockée compilée en mode natif est exécutée avec une option STATISTICS activée, les statistiques sont collectées pour la procédure dans son ensemble, et non par instruction.</span><span class="sxs-lookup"><span data-stu-id="5737c-106">When a natively compiled stored procedure is executed with any STATISTICS option turned on, statistics are gathered for the procedure as a whole and not per statement.</span></span> <span data-ttu-id="5737c-107">Pour plus d’informations, consultez [SET STATISTICS IO &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-io-transact-sql), [SET STATISTICS PROFILE &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-profile-transact-sql), [SET STATISTICS TIME &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-time-transact-sql) et [SET STATISTICS XML &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-xml-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5737c-107">For more information, see [SET STATISTICS IO &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-io-transact-sql), [SET STATISTICS PROFILE &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-profile-transact-sql), [SET STATISTICS TIME &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-time-transact-sql), and [SET STATISTICS XML &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-xml-transact-sql).</span></span> <span data-ttu-id="5737c-108">Pour obtenir les statistiques d'exécution au niveau d'une instruction dans des procédures stockées compilées en mode natif, utilisez une session d'événements étendus dans l'événement sp_statement_completed, qui commence à l'issue de chaque requête individuelle exécutée dans les procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="5737c-108">To obtain execution statistics on a per-statement level in natively compiled stored procedures, use an Extended Event session on the sp_statement_completed event, which starts when each individual query in a stored procedures execution completes.</span></span> <span data-ttu-id="5737c-109">Pour plus d’informations sur la création de sessions d’événements étendus, consultez [CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5737c-109">For more information on creating Extended Event sessions, see [CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql).</span></span>  
  
 <span data-ttu-id="5737c-110">`SHOWPLAN_XML` est pris en charge pour les procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="5737c-110">`SHOWPLAN_XML` is supported for natively compiled stored procedures.</span></span> <span data-ttu-id="5737c-111">`SHOWPLAN_ALL` et `SHOWPLAN_TEXT` ne sont pas prises en charge dans les procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="5737c-111">`SHOWPLAN_ALL` and `SHOWPLAN_TEXT` are not supported with natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="5737c-112">`SET FMTONLY` n'est pas prise en charge dans les procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="5737c-112">`SET FMTONLY` in not supported with natively compiled stored procedures.</span></span> <span data-ttu-id="5737c-113">Utilisez plutôt [sp_describe_first_result_set &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-describe-first-result-set-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5737c-113">Use [sp_describe_first_result_set &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-describe-first-result-set-transact-sql) instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5737c-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5737c-114">See Also</span></span>  
 [<span data-ttu-id="5737c-115">Procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="5737c-115">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
