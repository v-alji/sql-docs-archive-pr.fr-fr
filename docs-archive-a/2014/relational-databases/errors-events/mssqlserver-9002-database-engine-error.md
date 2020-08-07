---
title: MSSQLSERVER_9002 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9002 (Database Engine error)
ms.assetid: 2e50841f-2b99-45f4-aec5-aa4add70cbeb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b40fe70db8849d09f9296a06cbeed65a9c71e5a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611804"
---
# <a name="mssqlserver_9002"></a><span data-ttu-id="30c74-102">MSSQLSERVER_9002</span><span class="sxs-lookup"><span data-stu-id="30c74-102">MSSQLSERVER_9002</span></span>
    
## <a name="details"></a><span data-ttu-id="30c74-103">Détails</span><span class="sxs-lookup"><span data-stu-id="30c74-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="30c74-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="30c74-104">Product Name</span></span>|<span data-ttu-id="30c74-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="30c74-105">SQL Server</span></span>|  
|<span data-ttu-id="30c74-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="30c74-106">Event ID</span></span>|<span data-ttu-id="30c74-107">9002</span><span class="sxs-lookup"><span data-stu-id="30c74-107">9002</span></span>|  
|<span data-ttu-id="30c74-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="30c74-108">Event Source</span></span>|<span data-ttu-id="30c74-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="30c74-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="30c74-110">Composant</span><span class="sxs-lookup"><span data-stu-id="30c74-110">Component</span></span>|<span data-ttu-id="30c74-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="30c74-111">SQLEngine</span></span>|  
|<span data-ttu-id="30c74-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="30c74-112">Symbolic Name</span></span>|<span data-ttu-id="30c74-113">LOG_IS_FULL</span><span class="sxs-lookup"><span data-stu-id="30c74-113">LOG_IS_FULL</span></span>|  
|<span data-ttu-id="30c74-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="30c74-114">Message Text</span></span>|<span data-ttu-id="30c74-115">Le journal des transactions de la base de données '%.\*ls' est plein.</span><span class="sxs-lookup"><span data-stu-id="30c74-115">The transaction log for database '%.\*ls' is full.</span></span> <span data-ttu-id="30c74-116">Pour savoir pourquoi il est impossible de réutiliser de l'espace dans le journal, consultez la colonne log_reuse_wait_desc dans sys.databases.</span><span class="sxs-lookup"><span data-stu-id="30c74-116">To find out why space in the log cannot be reused, see the log_reuse_wait_desc column in sys.databases.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="30c74-117">Explication</span><span class="sxs-lookup"><span data-stu-id="30c74-117">Explanation</span></span>  
 <span data-ttu-id="30c74-118">Le journal de la base de données est saturé.</span><span class="sxs-lookup"><span data-stu-id="30c74-118">The database log is out of space.</span></span> <span data-ttu-id="30c74-119">La colonne **log_reuse_wait_desc** dans **sys.databases** explique pourquoi il est impossible de réutiliser l’espace dans le journal.</span><span class="sxs-lookup"><span data-stu-id="30c74-119">The **log_reuse_wait_desc** column in **sys.databases** describes why space in the log cannot be reused.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="30c74-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="30c74-120">User Action</span></span>  
 <span data-ttu-id="30c74-121">Utilisez **sys.databases** pour comprendre pourquoi le journal est plein, puis corrigez la condition.</span><span class="sxs-lookup"><span data-stu-id="30c74-121">Use **sys.databases** to determine why the log is full and then correct the condition.</span></span> <span data-ttu-id="30c74-122">Pour plus d’informations, consultez « Résolution des problèmes en cas de journal des transactions saturé (erreur 9002) » dans la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="30c74-122">For more information, see "Troubleshooting a Full Transaction Log (Error 9002)" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30c74-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="30c74-123">See Also</span></span>  
 <span data-ttu-id="30c74-124">[Résoudre les problèmes liés à un journal des transactions saturé &#40;erreur SQL Server 9002&#41;](../logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md) </span><span class="sxs-lookup"><span data-stu-id="30c74-124">[Troubleshoot a Full Transaction Log &#40;SQL Server Error 9002&#41;](../logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md) </span></span>  
 [<span data-ttu-id="30c74-125">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="30c74-125">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
