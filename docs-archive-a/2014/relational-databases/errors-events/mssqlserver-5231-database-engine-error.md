---
title: MSSQLSERVER_5231 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5231 (Database Engine error)
ms.assetid: 6954ae84-ed0b-4f4c-9d0a-e73f3d71476c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 68f40ac3a566280526757bd8b83c784954ba3dde
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696863"
---
# <a name="mssqlserver_5231"></a><span data-ttu-id="ec494-102">MSSQLSERVER_5231</span><span class="sxs-lookup"><span data-stu-id="ec494-102">MSSQLSERVER_5231</span></span>
    
## <a name="details"></a><span data-ttu-id="ec494-103">Détails</span><span class="sxs-lookup"><span data-stu-id="ec494-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ec494-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="ec494-104">Product Name</span></span>|<span data-ttu-id="ec494-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ec494-105">SQL Server</span></span>|  
|<span data-ttu-id="ec494-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="ec494-106">Event ID</span></span>|<span data-ttu-id="ec494-107">5231</span><span class="sxs-lookup"><span data-stu-id="ec494-107">5231</span></span>|  
|<span data-ttu-id="ec494-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="ec494-108">Event Source</span></span>|<span data-ttu-id="ec494-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ec494-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ec494-110">Composant</span><span class="sxs-lookup"><span data-stu-id="ec494-110">Component</span></span>|<span data-ttu-id="ec494-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ec494-111">SQLEngine</span></span>|  
|<span data-ttu-id="ec494-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="ec494-112">Symbolic Name</span></span>|<span data-ttu-id="ec494-113">DBCC4_DEADLOCK_SKIPPED_OBJECT</span><span class="sxs-lookup"><span data-stu-id="ec494-113">DBCC4_DEADLOCK_SKIPPED_OBJECT</span></span>|  
|<span data-ttu-id="ec494-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="ec494-114">Message Text</span></span>|<span data-ttu-id="ec494-115">ID d’objet O_ID (objet 'NAME') : un blocage s’est produit lors de la tentative de verrouillage de cet objet en vue d’une vérification.</span><span class="sxs-lookup"><span data-stu-id="ec494-115">Object ID O_ID (object 'NAME'): A deadlock occurred while trying to lock this object for checking.</span></span> <span data-ttu-id="ec494-116">Cet objet a été ignoré et il ne sera pas traité.</span><span class="sxs-lookup"><span data-stu-id="ec494-116">This object has been skipped and will not be processed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ec494-117">Explication</span><span class="sxs-lookup"><span data-stu-id="ec494-117">Explanation</span></span>  
 <span data-ttu-id="ec494-118">Un blocage s'est produit lorsque DBCC essayait de verrouiller l'objet et DBCC a été choisi comme victime du blocage.</span><span class="sxs-lookup"><span data-stu-id="ec494-118">A deadlock occurred when DBCC was trying to lock the object, and DBCC was chosen as the deadlock victim.</span></span> <span data-ttu-id="ec494-119">L'objet ne sera pas traité.</span><span class="sxs-lookup"><span data-stu-id="ec494-119">The object will not be processed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ec494-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="ec494-120">User Action</span></span>  
 <span data-ttu-id="ec494-121">None</span><span class="sxs-lookup"><span data-stu-id="ec494-121">None</span></span>  
  
  
