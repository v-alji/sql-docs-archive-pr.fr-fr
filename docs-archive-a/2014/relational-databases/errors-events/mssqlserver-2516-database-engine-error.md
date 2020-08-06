---
title: MSSQLSERVER_2516 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2516 (Database Engine error)
ms.assetid: 79ed14b5-f53c-40c6-8334-8a083f732207
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6be0809b3560d94bb883cf3a4acfa3d2c484b8b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696876"
---
# <a name="mssqlserver_2516"></a><span data-ttu-id="d2f6f-102">MSSQLSERVER_2516</span><span class="sxs-lookup"><span data-stu-id="d2f6f-102">MSSQLSERVER_2516</span></span>
    
## <a name="details"></a><span data-ttu-id="d2f6f-103">Détails</span><span class="sxs-lookup"><span data-stu-id="d2f6f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d2f6f-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="d2f6f-104">Product Name</span></span>|<span data-ttu-id="d2f6f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d2f6f-105">SQL Server</span></span>|  
|<span data-ttu-id="d2f6f-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="d2f6f-106">Event ID</span></span>|<span data-ttu-id="d2f6f-107">2516</span><span class="sxs-lookup"><span data-stu-id="d2f6f-107">2516</span></span>|  
|<span data-ttu-id="d2f6f-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="d2f6f-108">Event Source</span></span>|<span data-ttu-id="d2f6f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d2f6f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d2f6f-110">Composant</span><span class="sxs-lookup"><span data-stu-id="d2f6f-110">Component</span></span>|<span data-ttu-id="d2f6f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d2f6f-111">SQLEngine</span></span>|  
|<span data-ttu-id="d2f6f-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="d2f6f-112">Symbolic Name</span></span>|<span data-ttu-id="d2f6f-113">DBCC_REPAIR_DIFF_MAP_INVALIDATED</span><span class="sxs-lookup"><span data-stu-id="d2f6f-113">DBCC_REPAIR_DIFF_MAP_INVALIDATED</span></span>|  
|<span data-ttu-id="d2f6f-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="d2f6f-114">Message Text</span></span>|<span data-ttu-id="d2f6f-115">La réparation de la bitmap différentielle pour la base de données NAME n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-115">Repair has invalidated the differential bitmap for database NAME.</span></span> <span data-ttu-id="d2f6f-116">La chaîne de sauvegarde différentielle est interrompue.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-116">The differential backup chain is broken.</span></span> <span data-ttu-id="d2f6f-117">Vous devez d'abord effectuer une sauvegarde complète de la base de données avant d'effectuer une sauvegarde différentielle.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-117">You must perform a full database backup before you can perform a differential backup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d2f6f-118">Explication</span><span class="sxs-lookup"><span data-stu-id="d2f6f-118">Explanation</span></span>  
 <span data-ttu-id="d2f6f-119">Ce message d'information est retourné lorsque l'erreur MSSQLEngine_2515 est réparée.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-119">This informational message is returned when error MSSQLEngine_2515 is repaired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d2f6f-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="d2f6f-120">User Action</span></span>  
 <span data-ttu-id="d2f6f-121">Effectuez une sauvegarde de base de données complète.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-121">Perform a full database backup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2f6f-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d2f6f-122">See Also</span></span>  
 [<span data-ttu-id="d2f6f-123">Créer une sauvegarde complète de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d2f6f-123">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../backup-restore/create-a-full-database-backup-sql-server.md)  
  
  
