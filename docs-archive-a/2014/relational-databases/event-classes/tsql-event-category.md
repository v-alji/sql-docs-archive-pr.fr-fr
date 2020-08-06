---
title: TSQL, catégorie d’événement | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, TSQL event category
- TSQL event category [SQL Server]
- event classes [SQL Server], TSQL event category
ms.assetid: 215f8747-64b5-4bf3-9845-d476b10cda3a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 763d5f31fd3562f54b274a74324ed4715b623a18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695643"
---
# <a name="tsql-event-category"></a><span data-ttu-id="c80fc-102">TSQL, catégorie d’événement</span><span class="sxs-lookup"><span data-stu-id="c80fc-102">TSQL Event Category</span></span>
  <span data-ttu-id="c80fc-103">La catégorie d’événements **TSQL** contient des événements TSQL généraux.</span><span class="sxs-lookup"><span data-stu-id="c80fc-103">The **TSQL** event category contains general TSQL events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c80fc-104">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="c80fc-104">In This Section</span></span>  
  
|<span data-ttu-id="c80fc-105">Rubrique</span><span class="sxs-lookup"><span data-stu-id="c80fc-105">Topic</span></span>|<span data-ttu-id="c80fc-106">Description</span><span class="sxs-lookup"><span data-stu-id="c80fc-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="c80fc-107">Exec Prepared SQL, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="c80fc-107">Exec Prepared SQL Event Class</span></span>](exec-prepared-sql-event-class.md)|<span data-ttu-id="c80fc-108">Indique que SqlClient, ODBC, OLE DB ou la bibliothèque de bases de données a exécuté une ou plusieurs instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] préparées.</span><span class="sxs-lookup"><span data-stu-id="c80fc-108">Indicates that the SqlClient, ODBC, OLE DB, or DB-Library has executed a prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statements.</span></span>|  
|[<span data-ttu-id="c80fc-109">Classe d'événements Prepare SQL</span><span class="sxs-lookup"><span data-stu-id="c80fc-109">Prepare SQL Event Class</span></span>](prepare-sql-event-class.md)|<span data-ttu-id="c80fc-110">Indique que SqlClient, ODBC, OLE DB ou DB-Library a préparé une ou plusieurs instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] à utiliser.</span><span class="sxs-lookup"><span data-stu-id="c80fc-110">Indicates that SqlClient, ODBC, OLE DB, or DB-Library has prepared a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statements for use.</span></span>|  
|[<span data-ttu-id="c80fc-111">Classe d'événements SQL:BatchCompleted</span><span class="sxs-lookup"><span data-stu-id="c80fc-111">SQL:BatchCompleted Event Class</span></span>](sql-batchcompleted-event-class.md)|<span data-ttu-id="c80fc-112">Indique que le traitement [!INCLUDE[tsql](../../includes/tsql-md.md)] est terminé.</span><span class="sxs-lookup"><span data-stu-id="c80fc-112">Indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch has completed.</span></span>|  
|[<span data-ttu-id="c80fc-113">Classe d'événements SQL:BatchStarting</span><span class="sxs-lookup"><span data-stu-id="c80fc-113">SQL:BatchStarting Event Class</span></span>](sql-batchstarting-event-class.md)|<span data-ttu-id="c80fc-114">Indique que le traitement [!INCLUDE[tsql](../../includes/tsql-md.md)] démarre.</span><span class="sxs-lookup"><span data-stu-id="c80fc-114">Indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch is starting.</span></span>|  
|[<span data-ttu-id="c80fc-115">Classe d'événements SQL:StmtCompleted</span><span class="sxs-lookup"><span data-stu-id="c80fc-115">SQL:StmtCompleted Event Class</span></span>](sql-stmtcompleted-event-class.md)|<span data-ttu-id="c80fc-116">Indique qu'une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] est terminée.</span><span class="sxs-lookup"><span data-stu-id="c80fc-116">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement has completed.</span></span>|  
|[<span data-ttu-id="c80fc-117">Classe d'événements SQL:StmtRecompile</span><span class="sxs-lookup"><span data-stu-id="c80fc-117">SQL:StmtRecompile Event Class</span></span>](sql-stmtrecompile-event-class.md)|<span data-ttu-id="c80fc-118">Indique des recompilations au niveau instruction provoquées par tous les types de lots : procédures stockées, déclencheurs, lots ad hoc et requêtes.</span><span class="sxs-lookup"><span data-stu-id="c80fc-118">Indicates statement-level recompilations caused by all types of batches: stored procedures, triggers, ad hoc batches, and queries.</span></span>|  
|[<span data-ttu-id="c80fc-119">Classe d'événements SQL:StmtStarting</span><span class="sxs-lookup"><span data-stu-id="c80fc-119">SQL:StmtStarting Event Class</span></span>](sql-stmtstarting-event-class.md)|<span data-ttu-id="c80fc-120">Indique qu'une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] démarre.</span><span class="sxs-lookup"><span data-stu-id="c80fc-120">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is starting.</span></span>|  
|[<span data-ttu-id="c80fc-121">Classe d'événements Unprepare SQL</span><span class="sxs-lookup"><span data-stu-id="c80fc-121">Unprepare SQL Event Class</span></span>](unprepare-sql-event-class.md)|<span data-ttu-id="c80fc-122">Indique que SqlClient, ODBC, OLE DB ou la bibliothèque de bases de données a supprimé une ou plusieurs instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] préparées.</span><span class="sxs-lookup"><span data-stu-id="c80fc-122">Indicates that the SqlClient, ODBC, OLE DB, or DB-Library has deleted a prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statements.</span></span>|  
|[<span data-ttu-id="c80fc-123">XQuery Static Type, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="c80fc-123">XQuery Static Type Event Class</span></span>](xquery-static-type-event-class.md)|<span data-ttu-id="c80fc-124">Se produit lorsque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] exécute une expression XQuery.</span><span class="sxs-lookup"><span data-stu-id="c80fc-124">Occurs when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executes an XQuery expression.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c80fc-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c80fc-125">See Also</span></span>  
 [<span data-ttu-id="c80fc-126">Référence Transact-SQL &#40;moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="c80fc-126">Transact-SQL Reference &#40;Database Engine&#41;</span></span>](/sql/t-sql/language-reference)  
  
  
