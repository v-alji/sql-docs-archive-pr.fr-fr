---
title: MSSQLSERVER_3452 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3452 (Database Engine error)
ms.assetid: bf838f02-7186-4b33-b01e-361b0c02de1f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 662d342064e8094400a6b672e21704877b4d0448
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600050"
---
# <a name="mssqlserver_3452"></a><span data-ttu-id="667ad-102">MSSQLSERVER_3452</span><span class="sxs-lookup"><span data-stu-id="667ad-102">MSSQLSERVER_3452</span></span>
    
## <a name="details"></a><span data-ttu-id="667ad-103">Détails</span><span class="sxs-lookup"><span data-stu-id="667ad-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="667ad-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="667ad-104">Product Name</span></span>|<span data-ttu-id="667ad-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="667ad-105">SQL Server</span></span>|  
|<span data-ttu-id="667ad-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="667ad-106">Event ID</span></span>|<span data-ttu-id="667ad-107">3452</span><span class="sxs-lookup"><span data-stu-id="667ad-107">3452</span></span>|  
|<span data-ttu-id="667ad-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="667ad-108">Event Source</span></span>|<span data-ttu-id="667ad-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="667ad-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="667ad-110">Composant</span><span class="sxs-lookup"><span data-stu-id="667ad-110">Component</span></span>|<span data-ttu-id="667ad-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="667ad-111">SQLEngine</span></span>|  
|<span data-ttu-id="667ad-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="667ad-112">Symbolic Name</span></span>|<span data-ttu-id="667ad-113">REC_CHECKIDENTITY</span><span class="sxs-lookup"><span data-stu-id="667ad-113">REC_CHECKIDENTITY</span></span>|  
|<span data-ttu-id="667ad-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="667ad-114">Message Text</span></span>|<span data-ttu-id="667ad-115">La récupération de la base de données '%.\*ls' (%d) a détecté une possible incohérence de valeurs d'identité dans la table ID %d.</span><span class="sxs-lookup"><span data-stu-id="667ad-115">Recovery of database '%.\*ls' (%d) detected possible identity value inconsistency in table ID %d.</span></span> <span data-ttu-id="667ad-116">Exécutez DBCC CHECKIDENT (’%.\*ls’).</span><span class="sxs-lookup"><span data-stu-id="667ad-116">Run DBCC CHECKIDENT ('%.\*ls').</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="667ad-117">Explication</span><span class="sxs-lookup"><span data-stu-id="667ad-117">Explanation</span></span>  
 <span data-ttu-id="667ad-118">Au cours de la mise à niveau vers [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], le processus de récupération des valeurs d'identité dans la base de données a détecté une incohérence dans les métadonnées.</span><span class="sxs-lookup"><span data-stu-id="667ad-118">During the upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the process to recover the identity values in the database found an inconsistency in the metadata.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="667ad-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="667ad-119">User Action</span></span>  
 <span data-ttu-id="667ad-120">Exécutez DBCC CHECKIDENT.</span><span class="sxs-lookup"><span data-stu-id="667ad-120">Run DBCC CHECKIDENT.</span></span>  
  
  
