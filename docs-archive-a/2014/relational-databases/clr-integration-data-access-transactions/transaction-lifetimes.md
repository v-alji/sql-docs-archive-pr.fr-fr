---
title: Durées de vie des transactions | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- lifetimes [SQL Server]
- Transact-SQL vs. managed code
ms.assetid: cb076fda-6488-4959-a6a4-7adaccf3f25c
author: rothja
ms.author: jroth
ms.openlocfilehash: 8c00050ee323cade7493d44c4c296ba4ce6811e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709655"
---
# <a name="transaction-lifetimes"></a><span data-ttu-id="3549a-102">Durées de vie des transactions</span><span class="sxs-lookup"><span data-stu-id="3549a-102">Transaction Lifetimes</span></span>
  <span data-ttu-id="3549a-103">Il existe une différence importante entre des transactions démarrées dans des procédures stockées [!INCLUDE[tsql](../../includes/tsql-md.md)] et celles démarrées dans du code managé : le code CLR (Common Language Runtime) ne peut pas déséquilibrer l'état des transactions lors de l'entrée ou de la sortie d'un appel au CLR.</span><span class="sxs-lookup"><span data-stu-id="3549a-103">There is an important difference between transactions started in [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures and those started in managed code: common language runtime (CLR) code cannot unbalance the transaction state on entry or exit of a CLR invocation.</span></span> <span data-ttu-id="3549a-104">Soyez conscient des implications d'une telle différence :</span><span class="sxs-lookup"><span data-stu-id="3549a-104">Be aware of the following implications of this difference:</span></span>  
  
-   <span data-ttu-id="3549a-105">Une transaction démarrée à l'intérieur d'une trame CLR doit être validée ou annulée ; dans le cas contraire, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] génère une erreur à la sortie de la trame.</span><span class="sxs-lookup"><span data-stu-id="3549a-105">A transaction started inside a CLR frame must be committed or rolled back, or else [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] generates an error when the frame is exited.</span></span>  
  
-   <span data-ttu-id="3549a-106">Une transaction externe ne peut pas être validée ni annulée au sein du code CLR.</span><span class="sxs-lookup"><span data-stu-id="3549a-106">An outer transaction cannot be committed or rolled back inside the CLR code.</span></span>  
  
-   <span data-ttu-id="3549a-107">Une tentative de validation d'une transaction non démarrée dans la même procédure provoque une erreur d'exécution.</span><span class="sxs-lookup"><span data-stu-id="3549a-107">An attempt to commit a transaction not started in the same procedure causes a run-time error.</span></span>  
  
-   <span data-ttu-id="3549a-108">Une tentative de restauration d’une transaction non démarrée dans la même procédure provoque le blocage de la transaction (empêchant toute autre opération d’effet secondaire).</span><span class="sxs-lookup"><span data-stu-id="3549a-108">An attempt to roll back a transaction not started in the same procedure causes the transaction to stop responding (preventing any other side-effecting operation from happening).</span></span> <span data-ttu-id="3549a-109">La transaction cesse jusqu'à ce que le code CLR soit hors de portée.</span><span class="sxs-lookup"><span data-stu-id="3549a-109">The transaction discontinues until the CLR code goes out of scope.</span></span> <span data-ttu-id="3549a-110">Notez que cela peut être utile lorsque vous détectez une erreur à l'intérieur de votre procédure et souhaitez vous assurer que la transaction entière se termine.</span><span class="sxs-lookup"><span data-stu-id="3549a-110">Note that this can be useful when you detect an error inside your procedure and want to make sure the whole transaction terminates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3549a-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3549a-111">See Also</span></span>  
 [<span data-ttu-id="3549a-112">Intégration et transactions du CLR</span><span class="sxs-lookup"><span data-stu-id="3549a-112">CLR Integration and Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
  
  
