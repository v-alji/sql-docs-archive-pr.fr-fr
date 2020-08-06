---
title: MSSQLSERVER_7915 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7915 (Database Engine error)
ms.assetid: 63338587-7dd3-40e6-b70e-d8ae18fff47b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1dc7a69023e49b48a10da9f0388cbd72fbe46be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610666"
---
# <a name="mssqlserver_7915"></a><span data-ttu-id="2492e-102">MSSQLSERVER_7915</span><span class="sxs-lookup"><span data-stu-id="2492e-102">MSSQLSERVER_7915</span></span>
    
## <a name="details"></a><span data-ttu-id="2492e-103">Détails</span><span class="sxs-lookup"><span data-stu-id="2492e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2492e-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="2492e-104">Product Name</span></span>|<span data-ttu-id="2492e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2492e-105">SQL Server</span></span>|  
|<span data-ttu-id="2492e-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="2492e-106">Event ID</span></span>|<span data-ttu-id="2492e-107">7915</span><span class="sxs-lookup"><span data-stu-id="2492e-107">7915</span></span>|  
|<span data-ttu-id="2492e-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="2492e-108">Event Source</span></span>|<span data-ttu-id="2492e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2492e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2492e-110">Composant</span><span class="sxs-lookup"><span data-stu-id="2492e-110">Component</span></span>|<span data-ttu-id="2492e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2492e-111">SQLEngine</span></span>|  
|<span data-ttu-id="2492e-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="2492e-112">Symbolic Name</span></span>|<span data-ttu-id="2492e-113">DBCC2_REPAIR_IAM_CHAIN_REBUILT</span><span class="sxs-lookup"><span data-stu-id="2492e-113">DBCC2_REPAIR_IAM_CHAIN_REBUILT</span></span>|  
|<span data-ttu-id="2492e-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="2492e-114">Message Text</span></span>|<span data-ttu-id="2492e-115">Réparation : la chaîne IAM pour l’ID d’objet O_ID, ID d’index I_ID, ID de partition PN_ID, ID d’unité d’allocation A_ID (type TYPE), a été tronquée avant la page P_ID et sera reconstruite.</span><span class="sxs-lookup"><span data-stu-id="2492e-115">Repair: IAM chain for object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), has been truncated before page P_ID and will be rebuilt.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2492e-116">Explication</span><span class="sxs-lookup"><span data-stu-id="2492e-116">Explanation</span></span>  
 <span data-ttu-id="2492e-117">Ceci est un message d'information envoyé par REPAIR, qui indique que la chaîne IAM (Index Allocation Map) spécifiée a été corrigée afin de pouvoir être reconstruite.</span><span class="sxs-lookup"><span data-stu-id="2492e-117">This is an information message sent by REPAIR that indicates that the specified Index Allocation Map (IAM) chain was patched so that it could be rebuilt.</span></span> <span data-ttu-id="2492e-118">Cette correction peut avoir requis l'allocation d'une nouvelle tête de la chaîne IAM ou la suppression de pages incorrectes de la chaîne.</span><span class="sxs-lookup"><span data-stu-id="2492e-118">This patching may have required the allocation of a new head of the IAM chain or the removal of bad pages from the chain.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2492e-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="2492e-119">User Action</span></span>  
 <span data-ttu-id="2492e-120">None</span><span class="sxs-lookup"><span data-stu-id="2492e-120">None</span></span>  
  
  
