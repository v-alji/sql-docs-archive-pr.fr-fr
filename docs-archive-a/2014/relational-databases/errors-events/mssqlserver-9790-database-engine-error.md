---
title: MSSQLSERVER_9790 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9790 (Database Engine error)
ms.assetid: 83fd379f-5deb-4f97-8cb4-282e3d3fed94
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6d6d065d4a0e841da3b5ecb84f902df17dcfd60c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604483"
---
# <a name="mssqlserver_9790"></a><span data-ttu-id="4942c-102">MSSQLSERVER_9790</span><span class="sxs-lookup"><span data-stu-id="4942c-102">MSSQLSERVER_9790</span></span>
    
## <a name="details"></a><span data-ttu-id="4942c-103">Détails</span><span class="sxs-lookup"><span data-stu-id="4942c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4942c-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="4942c-104">Product Name</span></span>|<span data-ttu-id="4942c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4942c-105">SQL Server</span></span>|  
|<span data-ttu-id="4942c-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="4942c-106">Event ID</span></span>|<span data-ttu-id="4942c-107">9790</span><span class="sxs-lookup"><span data-stu-id="4942c-107">9790</span></span>|  
|<span data-ttu-id="4942c-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="4942c-108">Event Source</span></span>|<span data-ttu-id="4942c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4942c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4942c-110">Composant</span><span class="sxs-lookup"><span data-stu-id="4942c-110">Component</span></span>|<span data-ttu-id="4942c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4942c-111">SQLEngine</span></span>|  
|<span data-ttu-id="4942c-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="4942c-112">Symbolic Name</span></span>|<span data-ttu-id="4942c-113">SB3_XMIT_ERROR_ENTRANCE_BROKER_SINGLE_USER</span><span class="sxs-lookup"><span data-stu-id="4942c-113">SB3_XMIT_ERROR_ENTRANCE_BROKER_SINGLE_USER</span></span>|  
|<span data-ttu-id="4942c-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="4942c-114">Message Text</span></span>|<span data-ttu-id="4942c-115">Impossible d'acheminer le message entrant.</span><span class="sxs-lookup"><span data-stu-id="4942c-115">Unable to route the incoming message.</span></span> <span data-ttu-id="4942c-116">La base de données MSDB système contenant les informations d'acheminement est en mode SINGLE USER.</span><span class="sxs-lookup"><span data-stu-id="4942c-116">The system database MSDB containing routing information is in SINGLE USER mode.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4942c-117">Explication</span><span class="sxs-lookup"><span data-stu-id="4942c-117">Explanation</span></span>  
 <span data-ttu-id="4942c-118">Une erreur s'est produite lors de la tentative de classement d'un message reçu sur le réseau : la base de données MSDB était en mode SINGLE USER.</span><span class="sxs-lookup"><span data-stu-id="4942c-118">An error occurred while trying to classify a message received off the wire because the MSDB database was in Single User mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4942c-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="4942c-119">User Action</span></span>  
 <span data-ttu-id="4942c-120">Passez MSDB en mode MULTI USER à l'aide de la commande ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="4942c-120">Change MSDB to be in MULTI USER mode with the ALTER DATABASE command.</span></span>  
  
  
