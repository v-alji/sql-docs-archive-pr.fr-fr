---
title: MSSQLSERVER_7308 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7308 (Database Engine error)
- single-threaded apartment mode
ms.assetid: cca9eab9-afb9-463d-abfd-0802257e2c99
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9978f35ebe41eeda1470220772f87e83ab1ad942
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605466"
---
# <a name="mssqlserver_7308"></a><span data-ttu-id="ddbff-102">MSSQLSERVER_7308</span><span class="sxs-lookup"><span data-stu-id="ddbff-102">MSSQLSERVER_7308</span></span>
    
## <a name="details"></a><span data-ttu-id="ddbff-103">Détails</span><span class="sxs-lookup"><span data-stu-id="ddbff-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ddbff-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="ddbff-104">Product Name</span></span>|<span data-ttu-id="ddbff-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ddbff-105">SQL Server</span></span>|  
|<span data-ttu-id="ddbff-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="ddbff-106">Event ID</span></span>|<span data-ttu-id="ddbff-107">7308</span><span class="sxs-lookup"><span data-stu-id="ddbff-107">7308</span></span>|  
|<span data-ttu-id="ddbff-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="ddbff-108">Event Source</span></span>|<span data-ttu-id="ddbff-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ddbff-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ddbff-110">Composant</span><span class="sxs-lookup"><span data-stu-id="ddbff-110">Component</span></span>|<span data-ttu-id="ddbff-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ddbff-111">SQLEngine</span></span>|  
|<span data-ttu-id="ddbff-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="ddbff-112">Symbolic Name</span></span>|<span data-ttu-id="ddbff-113">RMT_STA_DISABLED</span><span class="sxs-lookup"><span data-stu-id="ddbff-113">RMT_STA_DISABLED</span></span>|  
|<span data-ttu-id="ddbff-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="ddbff-114">Message Text</span></span>|<span data-ttu-id="ddbff-115">Le fournisseur OLE DB '%ls' ne peut pas être utilisé pour les requêtes distribuées, car le fournisseur est configuré pour s'exécuter en mode STA.</span><span class="sxs-lookup"><span data-stu-id="ddbff-115">OLE DB provider '%ls' cannot be used for distributed queries because the provider is configured to run in single-threaded apartment mode.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ddbff-116">Explication</span><span class="sxs-lookup"><span data-stu-id="ddbff-116">Explanation</span></span>  
 <span data-ttu-id="ddbff-117">Vous avez utilisé un fournisseur OLE DB configuré pour s'exécuter en mode thread unique cloisonné (STA, Single-Threaded Apartment).</span><span class="sxs-lookup"><span data-stu-id="ddbff-117">You have used an OLE DB provider that is configured to run in single-threaded apartment (STA) mode.</span></span> <span data-ttu-id="ddbff-118">Les fournisseurs OLE DB qui s'exécutent en mode STA ne peuvent pas être utilisés pour les requêtes distribuées.</span><span class="sxs-lookup"><span data-stu-id="ddbff-118">OLE DB providers that run in single-threaded apartment (STA) mode cannot be used for distributed queries.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ddbff-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="ddbff-119">User Action</span></span>  
 <span data-ttu-id="ddbff-120">Pour corriger cette erreur, configurez le fournisseur afin qu'il s'exécute en mode multithread cloisonné (MTA, Multi-Threaded Apartment).</span><span class="sxs-lookup"><span data-stu-id="ddbff-120">To resolve this error, configure the provider to run in multithreaded apartment (MTA) mode.</span></span> <span data-ttu-id="ddbff-121">Si le fournisseur ne prend pas en charge le mode MTA, et qu'il ne peut pas effectuer une mise à niveau vers une version qui le prend en charge, envisagez de configurer le fournisseur pour une exécution hors processus.</span><span class="sxs-lookup"><span data-stu-id="ddbff-121">If the provider does not support MTA, and the provider cannot be upgraded to a version that supports MTA, consider configuring the provider to run out-of-process.</span></span> <span data-ttu-id="ddbff-122">Le fournisseur doit être en mesure de vous indiquer s’il prend en charge le mode MTA ou une exécution hors processus.</span><span class="sxs-lookup"><span data-stu-id="ddbff-122">The provider vendor should be able to tell you if the provider supports MTA or running out-of-process.</span></span>  
  
  
