---
title: MSSQLSERVER_8642 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8642 (Database Engine error)
ms.assetid: fc498059-202f-4d0b-8599-4e784b47c186
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e30296fa569599b91ca74edc7535d330119e1680
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611811"
---
# <a name="mssqlserver_8642"></a><span data-ttu-id="2cd5a-102">MSSQLSERVER_8642</span><span class="sxs-lookup"><span data-stu-id="2cd5a-102">MSSQLSERVER_8642</span></span>
    
## <a name="details"></a><span data-ttu-id="2cd5a-103">Détails</span><span class="sxs-lookup"><span data-stu-id="2cd5a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2cd5a-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="2cd5a-104">Product Name</span></span>|<span data-ttu-id="2cd5a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2cd5a-105">SQL Server</span></span>|  
|<span data-ttu-id="2cd5a-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="2cd5a-106">Event ID</span></span>|<span data-ttu-id="2cd5a-107">8642</span><span class="sxs-lookup"><span data-stu-id="2cd5a-107">8642</span></span>|  
|<span data-ttu-id="2cd5a-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="2cd5a-108">Event Source</span></span>|<span data-ttu-id="2cd5a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2cd5a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2cd5a-110">Composant</span><span class="sxs-lookup"><span data-stu-id="2cd5a-110">Component</span></span>|<span data-ttu-id="2cd5a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2cd5a-111">SQLEngine</span></span>|  
|<span data-ttu-id="2cd5a-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="2cd5a-112">Symbolic Name</span></span>|<span data-ttu-id="2cd5a-113">EXCHNGSTART_ERR</span><span class="sxs-lookup"><span data-stu-id="2cd5a-113">EXCHNGSTART_ERR</span></span>|  
|<span data-ttu-id="2cd5a-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="2cd5a-114">Message Text</span></span>|<span data-ttu-id="2cd5a-115">Le processeur de requêtes ne peut pas démarrer les ressources de thread nécessaires pour l'exécution en parallèle de la requête.</span><span class="sxs-lookup"><span data-stu-id="2cd5a-115">The query processor could not start the necessary thread resources for parallel query execution.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2cd5a-116">Explication</span><span class="sxs-lookup"><span data-stu-id="2cd5a-116">Explanation</span></span>  
 <span data-ttu-id="2cd5a-117">Les ressources de thread sont réduites sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="2cd5a-117">Thread resources are low in the server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2cd5a-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="2cd5a-118">User Action</span></span>  
 <span data-ttu-id="2cd5a-119">Réduisez la charge sur le serveur et réexécutez la requête.</span><span class="sxs-lookup"><span data-stu-id="2cd5a-119">Reduce load on the server, and run the query again.</span></span>  
  
  
