---
title: Constructions prises en charge sur les procédures stockées compilées en mode natif | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 6b21f47e-bceb-4054-8b3c-9d39bb9583c0
author: rothja
ms.author: jroth
ms.openlocfilehash: f3bc7e28fa2a868ac39c6adbb2dea3cc5c3ace73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604002"
---
# <a name="supported-constructs-on-natively-compiled-stored-procedures"></a><span data-ttu-id="6d53d-102">Constructions prises en charge dans les procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="6d53d-102">Supported Constructs on Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="6d53d-103">Cette rubrique répertorie les constructions prises en charge dans les procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="6d53d-103">This topic lists the supported constructs on natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="6d53d-104">Pour plus d’informations sur les constructions non prises en charge, consultez [Constructions Transact-SQL non prises en charge par l’OLTP en mémoire](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="6d53d-104">For information about unsupported constructs, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
## <a name="procedure-ddl"></a><span data-ttu-id="6d53d-105">Procédure DDL</span><span class="sxs-lookup"><span data-stu-id="6d53d-105">Procedure DDL</span></span>  
 <span data-ttu-id="6d53d-106">Les constructions suivantes sont admises :</span><span class="sxs-lookup"><span data-stu-id="6d53d-106">The following are supported:</span></span>  
  
-   <span data-ttu-id="6d53d-107">CREATE PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="6d53d-107">CREATE PROCEDURE</span></span>  
  
-   <span data-ttu-id="6d53d-108">DROP PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="6d53d-108">DROP PROCEDURE</span></span>  
  
-   <span data-ttu-id="6d53d-109">SCHEMABINDING (requis pour les procédures stockées compilées en mode natif)</span><span class="sxs-lookup"><span data-stu-id="6d53d-109">SCHEMABINDING (required for natively compiled stored procedures)</span></span>  
  
-   <span data-ttu-id="6d53d-110">NATIVE_COMPILATION</span><span class="sxs-lookup"><span data-stu-id="6d53d-110">NATIVE_COMPILATION</span></span>  
  
-   <span data-ttu-id="6d53d-111">Les paramètres peuvent être déclarés NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="6d53d-111">Parameters can be declared as NOT NULL.</span></span>  
  
-   <span data-ttu-id="6d53d-112">Paramètres table.</span><span class="sxs-lookup"><span data-stu-id="6d53d-112">Table-valued parameters.</span></span>  
  
## <a name="security"></a><span data-ttu-id="6d53d-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="6d53d-113">Security</span></span>  
 <span data-ttu-id="6d53d-114">Les constructions suivantes sont admises :</span><span class="sxs-lookup"><span data-stu-id="6d53d-114">The following are supported:</span></span>  
  
-   <span data-ttu-id="6d53d-115">Pour les procédures : EXECUTE AS OWNER, SELF, et utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6d53d-115">For procedures: EXECUTE AS OWNER, SELF, and user.</span></span>  
  
-   <span data-ttu-id="6d53d-116">GRANT (accorder) et DENY (refuser) des autorisations sur les tables et les procédures.</span><span class="sxs-lookup"><span data-stu-id="6d53d-116">GRANT and DENY permissions on tables and procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d53d-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6d53d-117">See Also</span></span>  
 [<span data-ttu-id="6d53d-118">Procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="6d53d-118">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
