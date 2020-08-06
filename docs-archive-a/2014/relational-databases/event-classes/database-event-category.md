---
title: Base de données, catégorie d’événement | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- event classes [SQL Server], Database event category
- Database event category [SQL Server]
- SQL Server event classes, Database event category
ms.assetid: b61af738-f144-4992-b0b2-d44cb7240991
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2860e1434611393c941a639280343f736073c709
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611792"
---
# <a name="database-event-category"></a><span data-ttu-id="01255-102">Catégorie d'événement Base de données</span><span class="sxs-lookup"><span data-stu-id="01255-102">Database Event Category</span></span>
  <span data-ttu-id="01255-103">La catégorie d’événement **Base de données** contient des classes d’événements pour surveiller le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="01255-103">The **Database** event category contains event classes to monitor the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="01255-104">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="01255-104">In This Section</span></span>  
  
|<span data-ttu-id="01255-105">Rubrique</span><span class="sxs-lookup"><span data-stu-id="01255-105">Topic</span></span>|<span data-ttu-id="01255-106">Description</span><span class="sxs-lookup"><span data-stu-id="01255-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="01255-107">Data File Auto Grow, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="01255-107">Data File Auto Grow Event Class</span></span>](data-file-auto-grow-event-class.md)|<span data-ttu-id="01255-108">Indique que la taille du fichier de données a augmenté automatiquement.</span><span class="sxs-lookup"><span data-stu-id="01255-108">Indicates that the data file grew automatically.</span></span> <span data-ttu-id="01255-109">Cet événement n'est pas déclenché si la taille du fichier de données augmente de manière explicite par le biais d'ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="01255-109">This event is not triggered if the data file is grown explicitly through ALTER DATABASE.</span></span>|  
|[<span data-ttu-id="01255-110">Data File Auto Shrink, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="01255-110">Data File Auto Shrink Event Class</span></span>](data-file-auto-shrink-event-class.md)|<span data-ttu-id="01255-111">Indique que la taille du fichier de données a diminué.</span><span class="sxs-lookup"><span data-stu-id="01255-111">Indicates that the data file has been shrunk.</span></span>|  
|[<span data-ttu-id="01255-112">Database Mirroring Connection, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="01255-112">Database Mirroring Connection Event Class</span></span>](database-mirroring-connection-event-class.md)|<span data-ttu-id="01255-113">Événement généré pour signaler l'état d'une connexion de transport de la mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="01255-113">An event generated to report the status of a transport connection for database mirroring.</span></span>|  
|[<span data-ttu-id="01255-114">Database Mirroring State Change, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="01255-114">Database Mirroring State Change Event Class</span></span>](database-mirroring-state-change-event-class.md)|<span data-ttu-id="01255-115">Indique l'état des modifications de la base de données en miroir.</span><span class="sxs-lookup"><span data-stu-id="01255-115">Indicates when the state of a mirrored database changes.</span></span>|  
|[<span data-ttu-id="01255-116">Database Suspect Data Page, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="01255-116">Database Suspect Data Page Event Class</span></span>](database-suspect-data-page-event-class.md)|<span data-ttu-id="01255-117">Indique qu’une page est ajoutée à la table **suspect_pages** dans la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="01255-117">Indicates when a page is added to the **suspect_pages** table in the **msdb** database.</span></span>|  
|[<span data-ttu-id="01255-118">Classe d'événements Log File Auto Grow</span><span class="sxs-lookup"><span data-stu-id="01255-118">Log File Auto Grow Event Class</span></span>](log-file-auto-grow-event-class.md)|<span data-ttu-id="01255-119">Indique que la taille du fichier journal croît automatiquement.</span><span class="sxs-lookup"><span data-stu-id="01255-119">Indicates that the log file grew automatically.</span></span> <span data-ttu-id="01255-120">Cet événement n'est pas déclenché si le fichier journal a été augmenté de manière explicite par le biais d'ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="01255-120">This event is not triggered if the log file is grown explicitly through ALTER DATABASE.</span></span>|  
|[<span data-ttu-id="01255-121">Log File Auto Shrink, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="01255-121">Log File Auto Shrink Event Class</span></span>](log-file-auto-shrink-event-class.md)|<span data-ttu-id="01255-122">Indique que la taille du fichier journal croît automatiquement.</span><span class="sxs-lookup"><span data-stu-id="01255-122">Indicates that the log file grew automatically.</span></span> <span data-ttu-id="01255-123">Cet événement n'est pas déclenché si la taille du fichier journal diminue explicitement par le biais d'ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="01255-123">This event is not triggered if the log file shrinks explicitly through ALTER DATABASE.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01255-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="01255-124">See Also</span></span>  
 [<span data-ttu-id="01255-125">Événements étendus</span><span class="sxs-lookup"><span data-stu-id="01255-125">Extended Events</span></span>](../extended-events/extended-events.md)  
  
  
