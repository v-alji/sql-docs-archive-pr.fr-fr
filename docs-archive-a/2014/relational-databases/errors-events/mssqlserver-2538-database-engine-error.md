---
title: MSSQLSERVER_2538 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2538 (Database Engine error)
ms.assetid: 0a0f7d79-f1ba-4749-8804-fb660cca3492
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9f4ae886a6fd0abee2f7aa22c6a234c0a6c2d040
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612866"
---
# <a name="mssqlserver_2538"></a><span data-ttu-id="6e99a-102">MSSQLSERVER_2538</span><span class="sxs-lookup"><span data-stu-id="6e99a-102">MSSQLSERVER_2538</span></span>
    
## <a name="details"></a><span data-ttu-id="6e99a-103">Détails</span><span class="sxs-lookup"><span data-stu-id="6e99a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6e99a-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="6e99a-104">Product Name</span></span>|<span data-ttu-id="6e99a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6e99a-105">SQL Server</span></span>|  
|<span data-ttu-id="6e99a-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="6e99a-106">Event ID</span></span>|<span data-ttu-id="6e99a-107">2538</span><span class="sxs-lookup"><span data-stu-id="6e99a-107">2538</span></span>|  
|<span data-ttu-id="6e99a-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="6e99a-108">Event Source</span></span>|<span data-ttu-id="6e99a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6e99a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6e99a-110">Composant</span><span class="sxs-lookup"><span data-stu-id="6e99a-110">Component</span></span>|<span data-ttu-id="6e99a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6e99a-111">SQLEngine</span></span>|  
|<span data-ttu-id="6e99a-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="6e99a-112">Symbolic Name</span></span>|<span data-ttu-id="6e99a-113">DBCC_ALLOCATION_SUMMARY_PER_FILE</span><span class="sxs-lookup"><span data-stu-id="6e99a-113">DBCC_ALLOCATION_SUMMARY_PER_FILE</span></span>|  
|<span data-ttu-id="6e99a-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="6e99a-114">Message Text</span></span>|<span data-ttu-id="6e99a-115">Fichier FILE.</span><span class="sxs-lookup"><span data-stu-id="6e99a-115">File FILE.</span></span> <span data-ttu-id="6e99a-116">Nombre d'extensions = EXTENTS, pages utilisées = USED_PAGES, pages réservées = RESERVED_PAGES.</span><span class="sxs-lookup"><span data-stu-id="6e99a-116">Number of extents = EXTENTS, used pages = USED_PAGES, reserved pages = RESERVED_PAGES.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6e99a-117">Explication</span><span class="sxs-lookup"><span data-stu-id="6e99a-117">Explanation</span></span>  
 <span data-ttu-id="6e99a-118">Ces informations font partie de la sortie de la commande DBCC CHECKALLOC.</span><span class="sxs-lookup"><span data-stu-id="6e99a-118">This information is part of the output from the DBCC CHECKALLOC command.</span></span> <span data-ttu-id="6e99a-119">Elles présentent le résumé fichier par fichier des extensions allouées, des pages utilisées et des pages réservées pour la base de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="6e99a-119">This information is the per-file summary of allocated extents, used pages, and reserved pages for the specified database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6e99a-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="6e99a-120">User Action</span></span>  
 <span data-ttu-id="6e99a-121">None</span><span class="sxs-lookup"><span data-stu-id="6e99a-121">None</span></span>  
  
  
