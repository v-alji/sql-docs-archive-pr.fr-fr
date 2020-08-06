---
title: MSSQLSERVER_18752 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18752 (Database Engine error)
ms.assetid: 234c58d8-7a1e-4b07-a64b-32a311527980
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a463e4019875f4a233ae2920f32bc2252376a41c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604527"
---
# <a name="mssqlserver_18752"></a><span data-ttu-id="6faf3-102">MSSQLSERVER_18752</span><span class="sxs-lookup"><span data-stu-id="6faf3-102">MSSQLSERVER_18752</span></span>
    
## <a name="details"></a><span data-ttu-id="6faf3-103">Détails</span><span class="sxs-lookup"><span data-stu-id="6faf3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6faf3-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="6faf3-104">Product Name</span></span>|<span data-ttu-id="6faf3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6faf3-105">SQL Server</span></span>|  
|<span data-ttu-id="6faf3-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="6faf3-106">Event ID</span></span>|<span data-ttu-id="6faf3-107">18752</span><span class="sxs-lookup"><span data-stu-id="6faf3-107">18752</span></span>|  
|<span data-ttu-id="6faf3-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="6faf3-108">Event Source</span></span>|<span data-ttu-id="6faf3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6faf3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6faf3-110">Composant</span><span class="sxs-lookup"><span data-stu-id="6faf3-110">Component</span></span>|<span data-ttu-id="6faf3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6faf3-111">SQLEngine</span></span>|  
|<span data-ttu-id="6faf3-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="6faf3-112">Symbolic Name</span></span>|<span data-ttu-id="6faf3-113">REPL_INUSE</span><span class="sxs-lookup"><span data-stu-id="6faf3-113">REPL_INUSE</span></span>|  
|<span data-ttu-id="6faf3-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="6faf3-114">Message Text</span></span>|<span data-ttu-id="6faf3-115">Un seul Agent de lecture du journal ou une seule procédure liée au journal (sp_repldone, sp_replcmds et sp_replshowcmds) peut se connecter à une base de données à la fois.</span><span class="sxs-lookup"><span data-stu-id="6faf3-115">Only one Log Reader Agent or log-related procedure (sp_repldone, sp_replcmds, and sp_replshowcmds) can connect to a database at a time.</span></span> <span data-ttu-id="6faf3-116">Si vous avez exécuté une procédure liée au journal, supprimez la connexion à travers laquelle fut exécutée la procédure ou exécutez sp_replflush sur cette connexion avant de démarrer l'Agent de lecture du journal ou d'exécuter toute autre procédure liée au journal.</span><span class="sxs-lookup"><span data-stu-id="6faf3-116">If you executed a log-related procedure, drop the connection over which the procedure was executed or execute sp_replflush over that connection before starting the Log Reader Agent or executing another log-related procedure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6faf3-117">Explication</span><span class="sxs-lookup"><span data-stu-id="6faf3-117">Explanation</span></span>  
 <span data-ttu-id="6faf3-118">Un seul Agent de lecture du journal ou une seule procédure liée au journal peut se connecter à une base de données à la fois.</span><span class="sxs-lookup"><span data-stu-id="6faf3-118">Only one Log Reader agent or log-related procedure can connect to a database at a time.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6faf3-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="6faf3-119">User Action</span></span>  
 <span data-ttu-id="6faf3-120">Assurez-vous qu'aucun autre lecteur de journal ne s'exécute pour la même base de données de publication, et qu'aucune autre connexion active n'avait auparavant exécuté sp_replcmds/sp_repltrans/sp_repldone sans exécuter sp_replflush ensuite ou se déconnecter.</span><span class="sxs-lookup"><span data-stu-id="6faf3-120">Make sure no other logreader is running for the same publishing database, and no other active connection had previously run sp_replcmds/sp_repltrans/sp_repldone without running sp_replflush afterwards or disconnecting.</span></span>  
  
  
