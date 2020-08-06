---
title: LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: a7c5ce08-8841-49a3-b252-116807ba469a
author: stevestein
ms.author: sstein
ms.openlocfilehash: aa6db2af138bb2aeefb1a922e55db56c4ea821f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710648"
---
# <a name="localdb_error_instance_exists_with_lower_version"></a><span data-ttu-id="9b1bf-102">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span><span class="sxs-lookup"><span data-stu-id="9b1bf-102">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span></span>
    
## <a name="details"></a><span data-ttu-id="9b1bf-103">Détails</span><span class="sxs-lookup"><span data-stu-id="9b1bf-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9b1bf-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="9b1bf-104">Product Name</span></span>|<span data-ttu-id="9b1bf-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9b1bf-105">SQL Server</span></span>|  
|<span data-ttu-id="9b1bf-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="9b1bf-106">Event ID</span></span>|<span data-ttu-id="9b1bf-107">258</span><span class="sxs-lookup"><span data-stu-id="9b1bf-107">258</span></span>|  
|<span data-ttu-id="9b1bf-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="9b1bf-108">Event Source</span></span>|<span data-ttu-id="9b1bf-109">Runtime de base de données locale SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="9b1bf-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="9b1bf-110">Composant</span><span class="sxs-lookup"><span data-stu-id="9b1bf-110">Component</span></span>|<span data-ttu-id="9b1bf-111">API d'exécution de la base de données locale</span><span class="sxs-lookup"><span data-stu-id="9b1bf-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="9b1bf-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="9b1bf-112">Message Text</span></span>|<span data-ttu-id="9b1bf-113">Impossible de créer l'instance de base de données locale avec la version spécifiée.</span><span class="sxs-lookup"><span data-stu-id="9b1bf-113">Unable to create the Local Database instance with specified version.</span></span> <span data-ttu-id="9b1bf-114">Une instance du même nom existe déjà, mais sa version est inférieure à la version spécifiée.</span><span class="sxs-lookup"><span data-stu-id="9b1bf-114">An instance with the same name already exists, but it has lower version than the specified version.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9b1bf-115">Explication</span><span class="sxs-lookup"><span data-stu-id="9b1bf-115">Explanation</span></span>  
 <span data-ttu-id="9b1bf-116">L'instance spécifiée existe déjà mais sa version est inférieure à celle demandée.</span><span class="sxs-lookup"><span data-stu-id="9b1bf-116">The specified instance already exists but its version is lower than requested.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9b1bf-117">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="9b1bf-117">User Action</span></span>  
 <span data-ttu-id="9b1bf-118">Supprimez l'instance existante et retentez l'opération.</span><span class="sxs-lookup"><span data-stu-id="9b1bf-118">Delete the existing instance and retry the operation.</span></span>  
  
  
