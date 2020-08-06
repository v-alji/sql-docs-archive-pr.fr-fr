---
title: LOCALDB_ERROR_TOO_MANY_SHARED_INSTANCES | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: c1595263-6264-4a43-9535-5eb76ece3a57
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0896f3e70e6c65a1fcd0de4169249fb622e6b5f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600924"
---
# <a name="localdb_error_too_many_shared_instances"></a><span data-ttu-id="26eea-102">LOCALDB_ERROR_TOO_MANY_SHARED_INSTANCES</span><span class="sxs-lookup"><span data-stu-id="26eea-102">LOCALDB_ERROR_TOO_MANY_SHARED_INSTANCES</span></span>
    
## <a name="details"></a><span data-ttu-id="26eea-103">Détails</span><span class="sxs-lookup"><span data-stu-id="26eea-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="26eea-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="26eea-104">Product Name</span></span>|<span data-ttu-id="26eea-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="26eea-105">SQL Server</span></span>|  
|<span data-ttu-id="26eea-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="26eea-106">Event ID</span></span>|<span data-ttu-id="26eea-107">287</span><span class="sxs-lookup"><span data-stu-id="26eea-107">287</span></span>|  
|<span data-ttu-id="26eea-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="26eea-108">Event Source</span></span>|<span data-ttu-id="26eea-109">Runtime de base de données locale SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="26eea-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="26eea-110">Composant</span><span class="sxs-lookup"><span data-stu-id="26eea-110">Component</span></span>|<span data-ttu-id="26eea-111">API d'exécution de la base de données locale</span><span class="sxs-lookup"><span data-stu-id="26eea-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="26eea-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="26eea-112">Message Text</span></span>|<span data-ttu-id="26eea-113">Il existe un trop grand nombre d'instances partagées et il est impossible de générer un nom d'instance d'utilisateur unique.</span><span class="sxs-lookup"><span data-stu-id="26eea-113">There are too many shared instance and we cannot generate unique User Instance Name.</span></span> <span data-ttu-id="26eea-114">Annulez le partage de quelques instances partagées existantes.</span><span class="sxs-lookup"><span data-stu-id="26eea-114">Unshare some of the existing shared instances.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="26eea-115">Explication</span><span class="sxs-lookup"><span data-stu-id="26eea-115">Explanation</span></span>  
 <span data-ttu-id="26eea-116">Il existe un trop grand nombre d'instances partagées et il est impossible de générer un nom d'instance d'utilisateur unique.</span><span class="sxs-lookup"><span data-stu-id="26eea-116">There are too many shared instance and we cannot generate unique User Instance Name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="26eea-117">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="26eea-117">User Action</span></span>  
 <span data-ttu-id="26eea-118">Annulez le partage d'une ou plusieurs instances d'exécution de base de données locale partagées et réessayez.</span><span class="sxs-lookup"><span data-stu-id="26eea-118">Unshare one or more of the shared Local Database Runtime instances and try again.</span></span>  
  
  
