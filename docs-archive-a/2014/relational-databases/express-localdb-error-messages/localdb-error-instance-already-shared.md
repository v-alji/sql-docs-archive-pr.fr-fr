---
title: LOCALDB_ERROR_INSTANCE_ALREADY_SHARED | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: 35b4d6fa-ebb9-49d3-aaab-d4e37b6f3760
author: stevestein
ms.author: sstein
ms.openlocfilehash: 300f9753b721bc3e0a821a6b77929a9bec09312b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600930"
---
# <a name="localdb_error_instance_already_shared"></a><span data-ttu-id="e2d00-102">LOCALDB_ERROR_INSTANCE_ALREADY_SHARED</span><span class="sxs-lookup"><span data-stu-id="e2d00-102">LOCALDB_ERROR_INSTANCE_ALREADY_SHARED</span></span>
    
## <a name="details"></a><span data-ttu-id="e2d00-103">Détails</span><span class="sxs-lookup"><span data-stu-id="e2d00-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e2d00-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="e2d00-104">Product Name</span></span>|<span data-ttu-id="e2d00-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e2d00-105">SQL Server</span></span>|  
|<span data-ttu-id="e2d00-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="e2d00-106">Event ID</span></span>|<span data-ttu-id="e2d00-107">284</span><span class="sxs-lookup"><span data-stu-id="e2d00-107">284</span></span>|  
|<span data-ttu-id="e2d00-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="e2d00-108">Event Source</span></span>|<span data-ttu-id="e2d00-109">Runtime de base de données locale SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="e2d00-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="e2d00-110">Composant</span><span class="sxs-lookup"><span data-stu-id="e2d00-110">Component</span></span>|<span data-ttu-id="e2d00-111">API d'exécution de la base de données locale</span><span class="sxs-lookup"><span data-stu-id="e2d00-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="e2d00-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="e2d00-112">Message Text</span></span>|<span data-ttu-id="e2d00-113">L'instance de base de données locale spécifiée est déjà partagée.</span><span class="sxs-lookup"><span data-stu-id="e2d00-113">The specified Local Database Instance is already shared.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e2d00-114">Explication</span><span class="sxs-lookup"><span data-stu-id="e2d00-114">Explanation</span></span>  
 <span data-ttu-id="e2d00-115">L'instance de base de données locale spécifiée est déjà partagée avec un nom différent.</span><span class="sxs-lookup"><span data-stu-id="e2d00-115">The specified Local Database Instance is already shared with a different shared name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e2d00-116">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e2d00-116">User Action</span></span>  
 <span data-ttu-id="e2d00-117">Annulez le partage de l'instance partagée avant de la partager de nouveau avec un nom différent.</span><span class="sxs-lookup"><span data-stu-id="e2d00-117">Unshare the shared instance before sharing it again with a different shared name.</span></span>  
  
  
