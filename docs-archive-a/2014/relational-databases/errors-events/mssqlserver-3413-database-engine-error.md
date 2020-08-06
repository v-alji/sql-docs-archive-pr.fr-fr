---
title: MSSQLSERVER_3413 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3413 (Database Engine error)
ms.assetid: 3fa07637-ba93-4633-aaf2-ade7d18bc487
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a5d59ea61cff7051c3e1163a463c29443c553923
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612857"
---
# <a name="mssqlserver_3413"></a><span data-ttu-id="d8b2a-102">MSSQLSERVER_3413</span><span class="sxs-lookup"><span data-stu-id="d8b2a-102">MSSQLSERVER_3413</span></span>
    
## <a name="details"></a><span data-ttu-id="d8b2a-103">Détails</span><span class="sxs-lookup"><span data-stu-id="d8b2a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d8b2a-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="d8b2a-104">Product Name</span></span>|<span data-ttu-id="d8b2a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d8b2a-105">SQL Server</span></span>|  
|<span data-ttu-id="d8b2a-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="d8b2a-106">Event ID</span></span>|<span data-ttu-id="d8b2a-107">3413</span><span class="sxs-lookup"><span data-stu-id="d8b2a-107">3413</span></span>|  
|<span data-ttu-id="d8b2a-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="d8b2a-108">Event Source</span></span>|<span data-ttu-id="d8b2a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d8b2a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d8b2a-110">Composant</span><span class="sxs-lookup"><span data-stu-id="d8b2a-110">Component</span></span>|<span data-ttu-id="d8b2a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d8b2a-111">SQLEngine</span></span>|  
|<span data-ttu-id="d8b2a-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="d8b2a-112">Symbolic Name</span></span>|<span data-ttu-id="d8b2a-113">MARKDB</span><span class="sxs-lookup"><span data-stu-id="d8b2a-113">MARKDB</span></span>|  
|<span data-ttu-id="d8b2a-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="d8b2a-114">Message Text</span></span>|<span data-ttu-id="d8b2a-115">ID base de données %d.</span><span class="sxs-lookup"><span data-stu-id="d8b2a-115">Database ID %d.</span></span> <span data-ttu-id="d8b2a-116">Impossible de marquer la base de données comme suspecte.</span><span class="sxs-lookup"><span data-stu-id="d8b2a-116">Could not mark database as suspect.</span></span> <span data-ttu-id="d8b2a-117">Échec de l'analyse Getnext NC sur sys.databases.database_id.</span><span class="sxs-lookup"><span data-stu-id="d8b2a-117">Getnext NC scan on sys.databases.database_id failed.</span></span> <span data-ttu-id="d8b2a-118">Consultez les erreurs précédentes dans le journal des erreurs afin d'identifier la cause, puis corrigez tous les problèmes associés.</span><span class="sxs-lookup"><span data-stu-id="d8b2a-118">Refer to previous errors in the error log to identify the cause and correct any associated problems.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d8b2a-119">Explication</span><span class="sxs-lookup"><span data-stu-id="d8b2a-119">Explanation</span></span>  
 <span data-ttu-id="d8b2a-120">Une erreur inattendue s'est produite lors d'une tentative de marquage SUSPECT d'une base de données utilisateur dans le catalogue.</span><span class="sxs-lookup"><span data-stu-id="d8b2a-120">There was an unexpected failure while trying to mark a user database as SUSPECT in the catalog.</span></span> <span data-ttu-id="d8b2a-121">L'état SUSPECT ne peut pas être persistant.</span><span class="sxs-lookup"><span data-stu-id="d8b2a-121">The SUSPECT state will not be persisted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d8b2a-122">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="d8b2a-122">User Action</span></span>  
 <span data-ttu-id="d8b2a-123">Consultez les erreurs précédentes et corrigez le problème.</span><span class="sxs-lookup"><span data-stu-id="d8b2a-123">See previous errors and correct the problem.</span></span>  
  
  
