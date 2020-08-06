---
title: MSSQLSERVER_7910 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7910 (Database Engine error)
ms.assetid: 017a0113-2b17-40b3-a419-30bbc43d46b8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 60e7cca3f6973374ae7aeaa959a0b31207a1258e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605450"
---
# <a name="mssqlserver_7910"></a><span data-ttu-id="ec7df-102">MSSQLSERVER_7910</span><span class="sxs-lookup"><span data-stu-id="ec7df-102">MSSQLSERVER_7910</span></span>
    
## <a name="details"></a><span data-ttu-id="ec7df-103">Détails</span><span class="sxs-lookup"><span data-stu-id="ec7df-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ec7df-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="ec7df-104">Product Name</span></span>|<span data-ttu-id="ec7df-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ec7df-105">SQL Server</span></span>|  
|<span data-ttu-id="ec7df-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="ec7df-106">Event ID</span></span>|<span data-ttu-id="ec7df-107">7910</span><span class="sxs-lookup"><span data-stu-id="ec7df-107">7910</span></span>|  
|<span data-ttu-id="ec7df-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="ec7df-108">Event Source</span></span>|<span data-ttu-id="ec7df-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ec7df-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ec7df-110">Composant</span><span class="sxs-lookup"><span data-stu-id="ec7df-110">Component</span></span>|<span data-ttu-id="ec7df-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ec7df-111">SQLEngine</span></span>|  
|<span data-ttu-id="ec7df-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="ec7df-112">Symbolic Name</span></span>|<span data-ttu-id="ec7df-113">DBCC2_REPAIR_PAGE_ALLOCATED</span><span class="sxs-lookup"><span data-stu-id="ec7df-113">DBCC2_REPAIR_PAGE_ALLOCATED</span></span>|  
|<span data-ttu-id="ec7df-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="ec7df-114">Message Text</span></span>|<span data-ttu-id="ec7df-115">Réparation : la page P_ID a été allouée à l’ID d’objet O_ID, ID d’index I_ID, ID de partition PN_ID, ID d’unité d’allocation A_ID (type TYPE).</span><span class="sxs-lookup"><span data-stu-id="ec7df-115">Repair: The page P_ID has been allocated to object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ec7df-116">Explication</span><span class="sxs-lookup"><span data-stu-id="ec7df-116">Explanation</span></span>  
 <span data-ttu-id="ec7df-117">Uniquement fourni à titre d'information à partir de REPAIR, ce message indique qu'une page a été allouée au tableau d'emplacements de page unique d'une page IAM (Index Allocation Map).</span><span class="sxs-lookup"><span data-stu-id="ec7df-117">This is an informational message from REPAIR that states that a page has been allocated to the single-page slot array of an Index Allocation Map (IAM) page.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ec7df-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="ec7df-118">User Action</span></span>  
 <span data-ttu-id="ec7df-119">None</span><span class="sxs-lookup"><span data-stu-id="ec7df-119">None</span></span>  
  
  
