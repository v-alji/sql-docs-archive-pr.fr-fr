---
title: LOCALDB_ERROR_WAIT_TIMEOUT | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: e5b55efa-daa1-4c39-aa71-eeb7707ed601
author: stevestein
ms.author: sstein
ms.openlocfilehash: e3668b32fb48a3e12c33dc15224467307c696af4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695628"
---
# <a name="localdb_error_wait_timeout"></a><span data-ttu-id="1826a-102">LOCALDB_ERROR_WAIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1826a-102">LOCALDB_ERROR_WAIT_TIMEOUT</span></span>
    
## <a name="details"></a><span data-ttu-id="1826a-103">Détails</span><span class="sxs-lookup"><span data-stu-id="1826a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1826a-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="1826a-104">Product Name</span></span>|<span data-ttu-id="1826a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1826a-105">SQL Server</span></span>|  
|<span data-ttu-id="1826a-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="1826a-106">Event ID</span></span>|<span data-ttu-id="1826a-107">277</span><span class="sxs-lookup"><span data-stu-id="1826a-107">277</span></span>|  
|<span data-ttu-id="1826a-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="1826a-108">Event Source</span></span>|<span data-ttu-id="1826a-109">Runtime de base de données locale SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="1826a-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="1826a-110">Composant</span><span class="sxs-lookup"><span data-stu-id="1826a-110">Component</span></span>|<span data-ttu-id="1826a-111">API d'exécution de la base de données locale</span><span class="sxs-lookup"><span data-stu-id="1826a-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="1826a-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="1826a-112">Message Text</span></span>|<span data-ttu-id="1826a-113">Délai d'attente dépassé dans la méthode de l'API d'instance de base de données locale.</span><span class="sxs-lookup"><span data-stu-id="1826a-113">Timeout occurred inside the Local Database instance API method.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1826a-114">Explication</span><span class="sxs-lookup"><span data-stu-id="1826a-114">Explanation</span></span>  
 <span data-ttu-id="1826a-115">Un dépassement de délai s'est produit lors de la tentative d'acquisition des verrous de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="1826a-115">A time-out occurred while trying to acquire synchronization locks.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1826a-116">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="1826a-116">User Action</span></span>  
 <span data-ttu-id="1826a-117">Recommencez l'opération demandée.</span><span class="sxs-lookup"><span data-stu-id="1826a-117">Retry the requested operation again.</span></span>  
  
  
