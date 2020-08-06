---
title: MSSQLSERVER_1205 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1205 (Database Engine error)
ms.assetid: 9fe3f67c-df3c-4642-a3a4-ccc0e138b632
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b6afa81a05eea37bc67cd2e9ac2433b6c82f35b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600061"
---
# <a name="mssqlserver_1205"></a><span data-ttu-id="be213-102">MSSQLSERVER_1205</span><span class="sxs-lookup"><span data-stu-id="be213-102">MSSQLSERVER_1205</span></span>
    
## <a name="details"></a><span data-ttu-id="be213-103">Détails</span><span class="sxs-lookup"><span data-stu-id="be213-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="be213-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="be213-104">Product Name</span></span>|<span data-ttu-id="be213-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="be213-105">SQL Server</span></span>|  
|<span data-ttu-id="be213-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="be213-106">Event ID</span></span>|<span data-ttu-id="be213-107">1205</span><span class="sxs-lookup"><span data-stu-id="be213-107">1205</span></span>|  
|<span data-ttu-id="be213-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="be213-108">Event Source</span></span>|<span data-ttu-id="be213-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="be213-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="be213-110">Composant</span><span class="sxs-lookup"><span data-stu-id="be213-110">Component</span></span>|<span data-ttu-id="be213-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="be213-111">SQLEngine</span></span>|  
|<span data-ttu-id="be213-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="be213-112">Symbolic Name</span></span>|<span data-ttu-id="be213-113">LK_VICTIM</span><span class="sxs-lookup"><span data-stu-id="be213-113">LK_VICTIM</span></span>|  
|<span data-ttu-id="be213-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="be213-114">Message Text</span></span>|<span data-ttu-id="be213-115">La transaction (ID de processus %d) a été bloquée sur les ressources %.\*ls par un autre processus et a été choisie comme victime.</span><span class="sxs-lookup"><span data-stu-id="be213-115">Transaction (Process ID %d) was deadlocked on %.\*ls resources with another process and has been chosen as the deadlock victim.</span></span> <span data-ttu-id="be213-116">Relancez la transaction.</span><span class="sxs-lookup"><span data-stu-id="be213-116">Rerun the transaction.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="be213-117">Explication</span><span class="sxs-lookup"><span data-stu-id="be213-117">Explanation</span></span>  
 <span data-ttu-id="be213-118">Des ressources sont accessibles dans un ordre conflictuel sur des transactions distinctes, ce qui provoque un blocage.</span><span class="sxs-lookup"><span data-stu-id="be213-118">Resources are accessed in conflicting order on separate transactions, causing a deadlock.</span></span> <span data-ttu-id="be213-119">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="be213-119">For example:</span></span>  
  
-   <span data-ttu-id="be213-120">Transaction1 met à jour **Table1.Row1**, tandis que Transaction2 met à jour **Table2.Row2**.</span><span class="sxs-lookup"><span data-stu-id="be213-120">Transaction1 updates **Table1.Row1**, while Transaction2 updates **Table2.Row2**.</span></span>  
  
-   <span data-ttu-id="be213-121">Transaction1 essaie de mettre à jour **Table2.Row2** mais est bloquée car Transaction2 n’est pas encore validée.</span><span class="sxs-lookup"><span data-stu-id="be213-121">Transaction1 tries to update **Table2.Row2** but is blocked because Transaction2 has not yet committed.</span></span>  
  
-   <span data-ttu-id="be213-122">Transaction2 essaie alors de mettre à jour **Table1.Row1** mais est bloquée car Transaction1 n’est pas encore validée.</span><span class="sxs-lookup"><span data-stu-id="be213-122">Transaction2 now tries to update **Table1.Row1** but is blocked because Transaction1 has not committed.</span></span>  
  
-   <span data-ttu-id="be213-123">Un blocage survient car Transaction1 attend que Transaction2 se termine, alors que Transaction2 attend que Transaction1 se termine.</span><span class="sxs-lookup"><span data-stu-id="be213-123">A deadlock occurs because Transaction1 is waiting for Transaction2 to complete, but Transaction2 is waiting for Transaction1 to complete.</span></span>  
  
 <span data-ttu-id="be213-124">Dans ce cas, le système détecte le blocage et choisit une des transactions impliquées en tant que « victime », pour émettre ce message tout en annulant la transaction de la victime.</span><span class="sxs-lookup"><span data-stu-id="be213-124">The system will detect this deadlock and will choose one of the transactions involved as a 'victim' and will issue this message, rolling back the victim's transaction.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="be213-125">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="be213-125">User Action</span></span>  
 <span data-ttu-id="be213-126">Exécutez de nouveau la transaction.</span><span class="sxs-lookup"><span data-stu-id="be213-126">Execute the transaction again.</span></span> <span data-ttu-id="be213-127">Vous pouvez également réviser l'application pour éviter les blocages.</span><span class="sxs-lookup"><span data-stu-id="be213-127">You can also revise the application to avoid deadlocks.</span></span> <span data-ttu-id="be213-128">La transaction qui a été choisie comme victime peut être retentée et réussira probablement, en fonction des opérations qui sont exécutées simultanément.</span><span class="sxs-lookup"><span data-stu-id="be213-128">The transaction that was chosen as a victim can be retried and will likely succeed, depending on what operations are being executed simultaneously.</span></span>  
  
 <span data-ttu-id="be213-129">Pour empêcher ou éviter l’apparition de blocages, faites en sorte que toutes les transactions accèdent aux lignes dans le même ordre (**Table1**, puis **Table2**) ; de cette manière, bien qu’un blocage puisse survenir, aucun interblocage ne se produira.</span><span class="sxs-lookup"><span data-stu-id="be213-129">To prevent or avoid deadlocks from occurring, consider having all transactions access rows in the same order (**Table1**, then **Table2**); this way, although blocking might occur, a deadlock will not occur.</span></span>  
  
  
