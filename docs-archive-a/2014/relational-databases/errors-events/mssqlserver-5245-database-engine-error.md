---
title: MSSQLSERVER_5245 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5245 (Database Engine error)
ms.assetid: 6005c9ec-ccdd-4def-9eb4-37cdb599ddb3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f98c831642580587552bf60c604d84c38fffca8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612838"
---
# <a name="mssqlserver_5245"></a><span data-ttu-id="08382-102">MSSQLSERVER_5245</span><span class="sxs-lookup"><span data-stu-id="08382-102">MSSQLSERVER_5245</span></span>
    
## <a name="details"></a><span data-ttu-id="08382-103">Détails</span><span class="sxs-lookup"><span data-stu-id="08382-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="08382-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="08382-104">Product Name</span></span>|<span data-ttu-id="08382-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="08382-105">SQL Server</span></span>|  
|<span data-ttu-id="08382-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="08382-106">Event ID</span></span>|<span data-ttu-id="08382-107">5245</span><span class="sxs-lookup"><span data-stu-id="08382-107">5245</span></span>|  
|<span data-ttu-id="08382-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="08382-108">Event Source</span></span>|<span data-ttu-id="08382-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="08382-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="08382-110">Composant</span><span class="sxs-lookup"><span data-stu-id="08382-110">Component</span></span>|<span data-ttu-id="08382-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="08382-111">SQLEngine</span></span>|  
|<span data-ttu-id="08382-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="08382-112">Symbolic Name</span></span>|<span data-ttu-id="08382-113">DBCC4_TABLE_LOCK_TIMEOUT_EXCEEDED</span><span class="sxs-lookup"><span data-stu-id="08382-113">DBCC4_TABLE_LOCK_TIMEOUT_EXCEEDED</span></span>|  
|<span data-ttu-id="08382-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="08382-114">Message Text</span></span>|<span data-ttu-id="08382-115">ID d’objet O_ID (objet 'NAME') : DBCC n’a pas pu obtenir de verrou pour cet objet, car le délai d’attente de la requête de verrouillage a été dépassé.</span><span class="sxs-lookup"><span data-stu-id="08382-115">Object ID O_ID (object 'NAME'): DBCC could not obtain a lock on this object because the lock request time-out period was exceeded.</span></span> <span data-ttu-id="08382-116">Cet objet a été ignoré et il ne sera pas traité.</span><span class="sxs-lookup"><span data-stu-id="08382-116">This object has been skipped and will not be processed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="08382-117">Explication</span><span class="sxs-lookup"><span data-stu-id="08382-117">Explanation</span></span>  
 <span data-ttu-id="08382-118">Le délai d'attente de verrouillage a expiré pendant que DBCC attendait un verrouillage de table pour l'objet spécifié.</span><span class="sxs-lookup"><span data-stu-id="08382-118">A lock time-out occurred while DBCC was waiting on a table lock for the specified object.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="08382-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="08382-119">User Action</span></span>  
 <span data-ttu-id="08382-120">Exécutez de nouveau la commande DBCC.</span><span class="sxs-lookup"><span data-stu-id="08382-120">Rerun the DBCC command.</span></span>  
  
  
