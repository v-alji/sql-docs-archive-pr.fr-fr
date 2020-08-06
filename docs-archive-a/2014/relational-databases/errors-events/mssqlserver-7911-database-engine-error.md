---
title: MSSQLSERVER_7911 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7911 (Database Engine error)
ms.assetid: dd8390f3-0f77-4fb2-ba94-631a56e42bc6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6d37ce2dc11f231e8a6f8ae6cc8b95d8b2f87c12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605448"
---
# <a name="mssqlserver_7911"></a><span data-ttu-id="a632d-102">MSSQLSERVER_7911</span><span class="sxs-lookup"><span data-stu-id="a632d-102">MSSQLSERVER_7911</span></span>
    
## <a name="details"></a><span data-ttu-id="a632d-103">Détails</span><span class="sxs-lookup"><span data-stu-id="a632d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a632d-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="a632d-104">Product Name</span></span>|<span data-ttu-id="a632d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a632d-105">SQL Server</span></span>|  
|<span data-ttu-id="a632d-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="a632d-106">Event ID</span></span>|<span data-ttu-id="a632d-107">7911</span><span class="sxs-lookup"><span data-stu-id="a632d-107">7911</span></span>|  
|<span data-ttu-id="a632d-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="a632d-108">Event Source</span></span>|<span data-ttu-id="a632d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a632d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a632d-110">Composant</span><span class="sxs-lookup"><span data-stu-id="a632d-110">Component</span></span>|<span data-ttu-id="a632d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a632d-111">SQLEngine</span></span>|  
|<span data-ttu-id="a632d-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="a632d-112">Symbolic Name</span></span>|<span data-ttu-id="a632d-113">DBCC2_REPAIR_PAGE_DEALLOCATED</span><span class="sxs-lookup"><span data-stu-id="a632d-113">DBCC2_REPAIR_PAGE_DEALLOCATED</span></span>|  
|<span data-ttu-id="a632d-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="a632d-114">Message Text</span></span>|<span data-ttu-id="a632d-115">Réparation : la page P_ID a été libérée de l’ID d’objet O_ID, ID d’index I_ID, ID de partition PN_ID, ID d’unité d’allocation A_ID (type TYPE).</span><span class="sxs-lookup"><span data-stu-id="a632d-115">Repair: The page P_ID has been deallocated from object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a632d-116">Explication</span><span class="sxs-lookup"><span data-stu-id="a632d-116">Explanation</span></span>  
 <span data-ttu-id="a632d-117">Ceci est un message d'information de REPAIR qui stipule qu'une page a été libérée du tableau d'emplacement à une seule page d'une page IAM.</span><span class="sxs-lookup"><span data-stu-id="a632d-117">This is an informational message from REPAIR that states that a page has been deallocated from the single-page slot array of an Index Allocation Map (IAM) page.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a632d-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="a632d-118">User Action</span></span>  
 <span data-ttu-id="a632d-119">None</span><span class="sxs-lookup"><span data-stu-id="a632d-119">None</span></span>  
  
  
