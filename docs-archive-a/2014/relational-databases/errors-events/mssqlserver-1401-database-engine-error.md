---
title: MSSQLSERVER_1401 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1401 (Database Engine error)
ms.assetid: 02928770-aa63-4509-8713-406c73e4cedc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 720263939e2f1685649fc41896e8ea10907d92ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612917"
---
# <a name="mssqlserver_1401"></a><span data-ttu-id="8d5d8-102">MSSQLSERVER_1401</span><span class="sxs-lookup"><span data-stu-id="8d5d8-102">MSSQLSERVER_1401</span></span>
    
## <a name="details"></a><span data-ttu-id="8d5d8-103">Détails</span><span class="sxs-lookup"><span data-stu-id="8d5d8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8d5d8-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="8d5d8-104">Product Name</span></span>|<span data-ttu-id="8d5d8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8d5d8-105">SQL Server</span></span>|  
|<span data-ttu-id="8d5d8-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="8d5d8-106">Event ID</span></span>|<span data-ttu-id="8d5d8-107">1401</span><span class="sxs-lookup"><span data-stu-id="8d5d8-107">1401</span></span>|  
|<span data-ttu-id="8d5d8-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="8d5d8-108">Event Source</span></span>|<span data-ttu-id="8d5d8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8d5d8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8d5d8-110">Composant</span><span class="sxs-lookup"><span data-stu-id="8d5d8-110">Component</span></span>|<span data-ttu-id="8d5d8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8d5d8-111">SQLEngine</span></span>|  
|<span data-ttu-id="8d5d8-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="8d5d8-112">Symbolic Name</span></span>|<span data-ttu-id="8d5d8-113">DBM_MASTERSTARTUP</span><span class="sxs-lookup"><span data-stu-id="8d5d8-113">DBM_MASTERSTARTUP</span></span>|  
|<span data-ttu-id="8d5d8-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="8d5d8-114">Message Text</span></span>|<span data-ttu-id="8d5d8-115">Le démarrage de la routine du thread principal pour le processus de mise en miroir de la base de données a échoué pour la raison suivante : %ls.</span><span class="sxs-lookup"><span data-stu-id="8d5d8-115">Startup of the database-mirroring master thread routine failed for the following reason: %ls.</span></span> <span data-ttu-id="8d5d8-116">Corrigez la cause de cette erreur et redémarrez le service SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8d5d8-116">Correct the cause of this error, and restart the SQL Server service.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8d5d8-117">Explication</span><span class="sxs-lookup"><span data-stu-id="8d5d8-117">Explanation</span></span>  
 <span data-ttu-id="8d5d8-118">Le démarrage du thread de contrôle de la mise en miroir a échoué.</span><span class="sxs-lookup"><span data-stu-id="8d5d8-118">Startup of the mirroring control thread failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8d5d8-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="8d5d8-119">User Action</span></span>  
 <span data-ttu-id="8d5d8-120">Dans le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], recherchez l'erreur associée qui a précédé ce message.</span><span class="sxs-lookup"><span data-stu-id="8d5d8-120">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, look for the associated error that preceded this message.</span></span> <span data-ttu-id="8d5d8-121">Corrigez la cause de cette erreur, puis redémarrez le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="8d5d8-121">Correct the cause of this error, and then restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service (MSSQLSERVER).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d5d8-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8d5d8-122">See Also</span></span>  
 [<span data-ttu-id="8d5d8-123">Démarrer, arrêter, suspendre, reprendre, redémarrer le moteur de base de données, SQL Server Agent ou le service SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="8d5d8-123">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)  
  
  
