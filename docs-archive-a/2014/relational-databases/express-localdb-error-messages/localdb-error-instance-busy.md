---
title: LOCALDB_ERROR_INSTANCE_BUSY | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: 0ed9d0f8-3297-4e31-a3e9-4a827f381789
author: stevestein
ms.author: sstein
ms.openlocfilehash: c587ada5f08d3743f4fe7eafccfc923c38a2b7b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604451"
---
# <a name="localdb_error_instance_busy"></a><span data-ttu-id="f121c-102">LOCALDB_ERROR_INSTANCE_BUSY</span><span class="sxs-lookup"><span data-stu-id="f121c-102">LOCALDB_ERROR_INSTANCE_BUSY</span></span>
    
## <a name="details"></a><span data-ttu-id="f121c-103">Détails</span><span class="sxs-lookup"><span data-stu-id="f121c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f121c-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="f121c-104">Product Name</span></span>|<span data-ttu-id="f121c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f121c-105">SQL Server</span></span>|  
|<span data-ttu-id="f121c-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="f121c-106">Event ID</span></span>|<span data-ttu-id="f121c-107">274</span><span class="sxs-lookup"><span data-stu-id="f121c-107">274</span></span>|  
|<span data-ttu-id="f121c-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="f121c-108">Event Source</span></span>|<span data-ttu-id="f121c-109">Runtime de base de données locale SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="f121c-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="f121c-110">Composant</span><span class="sxs-lookup"><span data-stu-id="f121c-110">Component</span></span>|<span data-ttu-id="f121c-111">API d'exécution de la base de données locale</span><span class="sxs-lookup"><span data-stu-id="f121c-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="f121c-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="f121c-112">Message Text</span></span>|<span data-ttu-id="f121c-113">L'opération demandée sur l'instance de base de données locale ne peut pas être exécutée parce que l'instance spécifiée est en cours d'utilisation.</span><span class="sxs-lookup"><span data-stu-id="f121c-113">Requested operation on Local Database instance cannot be performed because specified instance is currently in use.</span></span> <span data-ttu-id="f121c-114">Arrêtez l'instance et recommencez.</span><span class="sxs-lookup"><span data-stu-id="f121c-114">Stop the instance and try again.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f121c-115">Explication</span><span class="sxs-lookup"><span data-stu-id="f121c-115">Explanation</span></span>  
 <span data-ttu-id="f121c-116">L'instance spécifiée est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="f121c-116">The specified instance is running.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f121c-117">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="f121c-117">User Action</span></span>  
 <span data-ttu-id="f121c-118">Arrêtez l'instance d'exécution de base de données locale spécifiée et recommencez.</span><span class="sxs-lookup"><span data-stu-id="f121c-118">Stop the specified Local Database Runtime instance and try again.</span></span>  
  
  
