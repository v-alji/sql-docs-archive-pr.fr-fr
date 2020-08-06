---
title: Supprimer une trace (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], deleting
- removing traces
- deleting traces
ms.assetid: a5502814-b281-42dd-b885-5c9368025ae6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b3551cff36ef6e2c2e9cc6a4d9b7056ae44cb950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610560"
---
# <a name="delete-a-trace-transact-sql"></a><span data-ttu-id="d5485-102">Supprimer une trace (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d5485-102">Delete a Trace (Transact-SQL)</span></span>
  <span data-ttu-id="d5485-103">Cette rubrique explique comment utiliser des procédures stockées pour supprimer une trace.</span><span class="sxs-lookup"><span data-stu-id="d5485-103">This topic describes how to use stored procedures to delete a trace.</span></span>  
  
 <span data-ttu-id="d5485-104">Pour obtenir un exemple d’utilisation de procédures stockées de trace, consultez [Créer une trace &#40;Transact-SQL&#41;](create-a-trace-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d5485-104">For an example of using trace stored procedures, see [Create a Trace &#40;Transact-SQL&#41;](create-a-trace-transact-sql.md).</span></span>  
  
### <a name="to-delete-a-trace"></a><span data-ttu-id="d5485-105">Pour supprimer une trace</span><span class="sxs-lookup"><span data-stu-id="d5485-105">To delete a trace</span></span>  
  
1.  <span data-ttu-id="d5485-106">Exécutez **sp_trace_setstatus** en spécifiant **@status= 0** pour arrêter la trace.</span><span class="sxs-lookup"><span data-stu-id="d5485-106">Execute **sp_trace_setstatus** by specifying **@status = 0** to stop the trace.</span></span>  
  
2.  <span data-ttu-id="d5485-107">Exécutez **sp_trace_setstatus** en spécifiant **@status= 2** pour fermer la trace et supprimer du serveur les informations la concernant.</span><span class="sxs-lookup"><span data-stu-id="d5485-107">Execute **sp_trace_setstatus** by specifying **@status = 2** to close the trace and delete its information from the server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d5485-108">Une trace doit d'abord être arrêtée avant d'être fermée.</span><span class="sxs-lookup"><span data-stu-id="d5485-108">A trace must be stopped first before it can be closed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5485-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d5485-109">See Also</span></span>  
 <span data-ttu-id="d5485-110">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d5485-110">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span></span>  
 <span data-ttu-id="d5485-111">[Procédures stockées système &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d5485-111">[System Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="d5485-112">Procédures stockées de SQL Server Profiler &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d5485-112">SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql)  
  
  
