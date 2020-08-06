---
title: MSSQLSERVER_17128 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17128 (Database Engine error)
ms.assetid: 7b15a5e6-fd41-47ce-ba87-54f72acea4bb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0e08c668acd0a8b2decb14da338b8d1f1e650de5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698268"
---
# <a name="mssqlserver_17128"></a><span data-ttu-id="74ab1-102">MSSQLSERVER_17128</span><span class="sxs-lookup"><span data-stu-id="74ab1-102">MSSQLSERVER_17128</span></span>
    
## <a name="details"></a><span data-ttu-id="74ab1-103">Détails</span><span class="sxs-lookup"><span data-stu-id="74ab1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="74ab1-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="74ab1-104">Product Name</span></span>|<span data-ttu-id="74ab1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="74ab1-105">SQL Server</span></span>|  
|<span data-ttu-id="74ab1-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="74ab1-106">Event ID</span></span>|<span data-ttu-id="74ab1-107">17128</span><span class="sxs-lookup"><span data-stu-id="74ab1-107">17128</span></span>|  
|<span data-ttu-id="74ab1-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="74ab1-108">Event Source</span></span>|<span data-ttu-id="74ab1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="74ab1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="74ab1-110">Composant</span><span class="sxs-lookup"><span data-stu-id="74ab1-110">Component</span></span>|<span data-ttu-id="74ab1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="74ab1-111">SQLEngine</span></span>|  
|<span data-ttu-id="74ab1-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="74ab1-112">Symbolic Name</span></span>|<span data-ttu-id="74ab1-113">INIT_NOBUFSPACE</span><span class="sxs-lookup"><span data-stu-id="74ab1-113">INIT_NOBUFSPACE</span></span>|  
|<span data-ttu-id="74ab1-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="74ab1-114">Message Text</span></span>|<span data-ttu-id="74ab1-115">initdata : aucune mémoire pour les tampons du noyau.</span><span class="sxs-lookup"><span data-stu-id="74ab1-115">initdata: No memory for kernel buffers.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="74ab1-116">Explication</span><span class="sxs-lookup"><span data-stu-id="74ab1-116">Explanation</span></span>  
 <span data-ttu-id="74ab1-117">Les réservations ou les allocations de mémoire initiales du pool de mémoires tampons ont échoué, et SQL Server se termine.</span><span class="sxs-lookup"><span data-stu-id="74ab1-117">The buffer pool's initial memory allocations or reservations have failed, and SQL Server exits.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="74ab1-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="74ab1-118">User Action</span></span>  
 <span data-ttu-id="74ab1-119">Provoqué généralement par le démarrage de SQL Server sur un ordinateur extrêmement petit, beaucoup plus petit que la configuration requise minimale.</span><span class="sxs-lookup"><span data-stu-id="74ab1-119">Usually caused by starting SQL Server on an extremely small machine - far smaller than the minimum system requirements.</span></span>  
  
  
